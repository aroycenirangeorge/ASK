# ASK
# Aim
Write a Python program for the modulation and demodulation of ASK.
# Tools required
- Python IDE
# Program
```python
import numpy as np
import matplotlib.pyplot as plt

# Parameters
fs = 1000  # Sampling frequency
fc = 100   # Carrier frequency
bit_rate = 10  # Bit rate
t = np.arange(0, 1, 1/fs)  # Time vector

# Generating Random Binary Data
data = np.random.randint(0, 2, bit_rate)
bit_duration = 1 / bit_rate
bit_t = np.linspace(0, bit_duration, int(fs / bit_rate), endpoint=False)
signal = np.concatenate([np.ones_like(bit_t) * bit for bit in data])

# Carrier Signal
carrier = np.sin(2 * np.pi * fc * np.linspace(0, 1, len(signal), endpoint=False))

# ASK Modulation
ask_signal = signal * carrier

# Plot Signals
plt.figure(figsize=(12, 6))

plt.subplot(3, 1, 1)
plt.step(np.linspace(0, 1, len(signal)), signal, where='mid', label="Binary Data")
plt.legend()
plt.grid(True)

plt.subplot(3, 1, 2)
plt.plot(np.linspace(0, 1, len(carrier)), carrier, label="Carrier Signal")
plt.legend()
plt.grid(True)

plt.subplot(3, 1, 3)
plt.plot(np.linspace(0, 1, len(ask_signal)), ask_signal, label="ASK Modulated Signal")
plt.legend()
plt.grid(True)

plt.tight_layout()
plt.show()
```
---
# Output Waveform
![image](https://github.com/user-attachments/assets/e6390bfa-5e31-40e0-b8b1-1d56455a5a6c)

# Results
Thus, the Amplitude Shift Keying (ASK) modulation was successfully performed using Python.

# Output Waveform- Hardware Experiment


