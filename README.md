# -Amplitude-Modulation-and-Demodulation-using-NumPy-and-Matplotlib

__Aim__: 

To implement and analyze amplitude modulation (AM) using Python's NumPy and Matplotlib libraries. 

__Apparatus Required__: 

Software: Python with NumPy and Matplotlib libraries 
Hardware: Personal Computer 

__Theory__: 

Amplitude Modulation (AM) is a technique used in electronic communication, primarily for transmitting 
information via a radio carrier wave. In AM, the amplitude of the carrier wave is varied in proportion to that of 
the message signal. The general form of an AM signal is: 


__Algorithm__:
1. Initialize Parameters: Set the values for carrier frequency, message frequency, and sampling frequency. 
2. Generate Time Axis: Create a time vector for the signal duration. 
3. Generate Message Signal: Define the message signal as a cosine wave. 
4. Generate Carrier Signal: Define the carrier signal as a cosine wave. 
5. Modulate Signal: Apply the AM formula to obtain the modulated signal. 
6. Plot the Signals: Use Matplotlib to plot the message signal, carrier signal, and modulated signal.

__Program__:

    import numpy as np 
    import matplotlib.pyplot as plt 
    from scipy.signal import hilbert 

    A_c = 1.0  
    f_c = 100 
    f_m = 5    
    A_m = 0.5   
    sampling_frequency = 1000  
    dura on = 1  

    t = np.linspace(0, dura on, int(sampling_frequency * dura on)) 

    m_t = A_m * np.cos(2 * np.pi * f_m * t)  
    c_t = A_c * np.cos(2 * np.pi * f_c * t) 

    s_t = (1 + m_t) * c_t  
    analy c_signal = hilbert(s_t) 
    envelope = np.abs(analy c_signal)
    demodulated_message = (envelope - A_c) / A_m 
    plt.figure(figsize=(12, 10)) 
    plt.subplot(4, 1, 1) 
    plt.plot(t, m_t) 
    plt. tle('Original Message Signal') 
    plt.xlabel('Time [s]') 
    plt.ylabel('Amplitude') 
    plt.grid(True) 

    plt.subplot(4, 1, 2) 
    plt.plot(t, c_t) 
    plt. tle('Carrier Signal') 
    plt.xlabel('Time [s]') 
    plt.ylabel('Amplitude') 
    plt.grid(True) 

    plt.subplot(4, 1, 3) 
    plt.plot(t, s_t) 
    plt. tle('Amplitude Modulated (AM) Signal') 
    plt.xlabel('Time [s]') 
    plt.ylabel('Amplitude') 
    plt.grid(True) 

    plt.subplot(4, 1, 4) 
    plt.plot(t, demodulated_message) 
    plt. tle('Demodulated Signal') 
    plt.xlabel('Time [s]') 
    plt.ylabel('Amplitude') 
    plt.grid(True)  
    plt. ght_layout() 
    plt.show()

__Tabulation__:

![WhatsApp Image 2025-11-26 at 22 43 14_54397275](https://github.com/user-attachments/assets/6937c442-1526-4a34-8ec3-7ffdd4b8a5bc)



 __Output__:
<img width="1198" height="990" alt="image" src="https://github.com/user-attachments/assets/30c20494-ca0b-4795-acc3-8a6f8b69b954" />


 __Result__:
Thus the AM demodulation and modulation is verified using python successfully.

