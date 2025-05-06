# ASK

# Aim

To perform Amplitude Shift Keying (ASK) using Python.

# Tools required

Python 3.x
NumPy
Matplotlib

# Program
```
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
plt.title("Message Signal (Binary)")
plt.legend()
plt.grid(True)

plt.subplot(3, 1, 2)
plt.plot(np.linspace(0, 1, len(carrier)), carrier, label="Carrier Signal")
plt.title("Carrier Signal")
plt.legend()
plt.grid(True)

plt.subplot(3, 1, 3)
plt.plot(np.linspace(0, 1, len(ask_signal)), ask_signal, label="ASK Modulated Signal")
plt.title("ASK Modulated Signal")
plt.legend()
plt.grid(True)

plt.tight_layout()
plt.show()
```
# Output Waveform

The following waveforms are generated upon executing the program:

Binary Input Signal

Carrier Signal

ASK Modulated Signal

![image](https://github.com/user-attachments/assets/5c3708dd-eb0e-4c32-b891-a71cbbef6eeb)


These plots visually represent the Amplitude Shift Keying process.


# GRAPH :
 ![ask graph](https://github.com/user-attachments/assets/2ac1da11-8a17-4670-8ce9-7bc746d30365)



# RESULT:
The simulation of Amplitude Shift Keying (ASK) was successfully performed. The modulated and demodulated waveforms were observed, confirming accurate transmission and recovery of binary data using amplitude variations.
