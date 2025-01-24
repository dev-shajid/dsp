# **Frequency Analysis of Signals**  
This document explores how signals can be represented and analyzed in the frequency domain using various transforms. It focuses on transforming signals between the time domain and the frequency domain.  

---

## **1. Frequency Analysis of Continuous-Time Signals**  

### **1.1 Fourier Series for Continuous-Time Periodic Signals**  
- **Representation:** Any periodic signal $ x(t) $ can be expressed as a sum of complex exponentials:  
  $$
  x(t) = \sum_{k=-\infty}^\infty c_k e^{j k \omega_0 t}
  $$  
  where $ c_k $ are the **Fourier series coefficients** given by:  
  $$
  c_k = \frac{1}{T} \int_0^T x(t) e^{-j k \omega_0 t} \, dt
  $$  
- **Fundamental frequency ($ \omega_0 $):** $ \omega_0 = 2\pi F_0 $, where $ F_0 $ is the fundamental frequency.  

### **1.2 Power Density Spectrum of Periodic Signals**  
- Periodic signals have **finite average power** but infinite energy.  
- Average power:  
  $$
  P_x = \frac{1}{T} \int_0^T |x(t)|^2 \, dt = \sum_{k=-\infty}^\infty |c_k|^2
  $$  
  (*Parseval's theorem for power signals*).  
- **Power Density Spectrum** describes power distribution across frequencies.  
- **Example:** For a rectangular pulse train:  
  - Fourier coefficients:  
    $$
    c_k = 
    \begin{cases} 
      \frac{A \tau}{T}, & k = 0 \\
      \frac{A \tau}{T} \frac{\sin(\pi k F_0 \tau)}{\pi k F_0 \tau}, & k \neq 0 
    \end{cases}
    $$  
  - Power density spectrum: $ |c_k|^2 $.  

### **1.3 Fourier Transform for Continuous-Time Aperiodic Signals**  
- **Definition:** The Fourier Transform converts an aperiodic signal $ x(t) $ into a continuous spectrum $ X(F) $:  
  $$
  X(F) = \int_{-\infty}^\infty x(t) e^{-j 2 \pi F t} \, dt
  $$  
- **Inverse Transform:**  
  $$
  x(t) = \int_{-\infty}^\infty X(F) e^{j 2 \pi F t} \, dF
  $$  
- Can also be expressed in terms of angular frequency $ \Omega = 2\pi F $.  

### **1.4 Energy Density Spectrum of Aperiodic Signals**  
- Total energy:  
  $$
  E_x = \int_{-\infty}^\infty |x(t)|^2 \, dt = \int_{-\infty}^\infty |X(F)|^2 \, dF
  $$  
- **Energy Density Spectrum** shows energy distribution across frequencies.  
- **Example:** For a rectangular pulse, the Fourier transform and energy density spectrum are:  
  $$
  S_x(F) = A^2 \left( \frac{\sin(\pi F \tau)}{\pi F} \right)^2
  $$  

---

## **2. Frequency Analysis of Discrete-Time Signals**  

### **2.1 Fourier Series for Discrete-Time Periodic Signals**  
- A periodic discrete-time signal $ x(n) $ with period $ N $ can be expressed as:  
  $$
  x(n) = \sum_{k=0}^{N-1} c_k e^{j 2 \pi k n / N}
  $$  
  where $ c_k $ are the **Fourier series coefficients**:  
  $$
  c_k = \frac{1}{N} \sum_{n=0}^{N-1} x(n) e^{-j 2 \pi k n / N}
  $$  
- **Key Property:** A discrete-time signal with period $ N $ has at most $ N $ frequency components.  

### **2.2 Power Density Spectrum of Discrete-Time Periodic Signals**  
- Average power:  
  $$
  P_x = \frac{1}{N} \sum_{n=0}^{N-1} |x(n)|^2 = \sum_{k=0}^{N-1} |c_k|^2
  $$  

### **2.3 Fourier Transform for Discrete-Time Aperiodic Signals**  
- **Definition:** The Fourier Transform of a discrete-time aperiodic signal $ x(n) $:  
  $$
  X(\omega) = \sum_{n=-\infty}^\infty x(n) e^{-j \omega n}
  $$  
- **Inverse Transform:**  
  $$
  x(n) = \frac{1}{2 \pi} \int_{-\pi}^\pi X(\omega) e^{j \omega n} \, d\omega
  $$  

### **2.4 Energy Density Spectrum of Discrete-Time Aperiodic Signals**  
- Total energy:  
  $$
  E_x = \sum_{n=-\infty}^\infty |x(n)|^2 = \frac{1}{2 \pi} \int_{-\pi}^\pi |X(\omega)|^2 \, d\omega
  $$  

### **2.5 Relationship Between Fourier Transform and z-Transform**  
- The **z-transform** of a sequence $ x(n) $:  
  $$
  X(z) = \sum_{n=-\infty}^\infty x(n) z^{-n}
  $$  
- For $ z = re^{j \omega} $, the z-transform becomes the Fourier Transform evaluated on the unit circle:  
  $$
  X(\omega) = X(z) \text{ for } |z| = 1
  $$  

---

## **3. Frequency Domain Classification of Signals**  
Signals can be categorized based on their frequency content:  
- **Low-pass signals:** Dominated by low frequencies.  
- **High-pass signals:** Dominated by high frequencies.  
- **Bandpass signals:** Concentrated in a specific frequency range.  

---

## **4. Time and Frequency Domain Properties**  
- Continuous-time signals: Aperiodic signals have **continuous spectra**.  
- Discrete-time signals:  
  - Aperiodic signals have **periodic spectra**.  
  - Periodic signals have **discrete spectra**.  

---
# Frequency Analysis of Signals: Key Formulas

| **Topic**                                    | **Formula**                                                                                           |
|----------------------------------------------|------------------------------------------------------------------------------------------------------|
| **Fourier Series (CT Periodic Signals)**     | $ x(t) = \sum_{k=-\infty}^\infty c_k e^{j k \omega_0 t} $, $ c_k = \frac{1}{T} \int_0^T x(t) e^{-j k \omega_0 t} \, dt $ |
| **Fundamental Frequency**                   | $ \omega_0 = 2\pi F_0 $                                                                            |
| **Power of Periodic Signals**               | $ P_x = \frac{1}{T} \int_0^T \|x(t)\|^2dt = \sum_{k=-\infty}^\infty \|c_k\|^2 $                     |
| **Fourier Transform (CT Aperiodic Signals)**| $$ X(F) = \int_{-\infty}^\infty x(t) e^{-j 2 \pi F t} \, dt $$ $$x(t) = \int_{-\infty}^\infty X(F) e^{j 2 \pi F t} \, dF $$ |
| **Energy of Aperiodic Signals**             | $ E_x = \int_{-\infty}^\infty \|x(t)\|^2 \, dt = \int_{-\infty}^\infty \|X(F)\|^2 \, dF $                |
| **DT Fourier Series (Periodic Signals)**    | $$ x(n) = \sum_{k=0}^{N-1} c_k e^{j 2 \pi k n / N} $$ $$ c_k = \frac{1}{N} \sum_{n=0}^{N-1} x(n) e^{-j 2 \pi k n / N} $$ |
| **Power of DT Periodic Signals**            | $ P_x = \frac{1}{N} \sum_{n=0}^{N-1} \|x(n)\|^2 = \sum_{k=0}^{N-1} \|c_k\|^2 $                          |
| **DT Fourier Transform (DTFT)**             | $$ X(\omega) = \sum_{n=-\infty}^\infty x(n) e^{-j \omega n} $$ $$ x(n) = \frac{1}{2 \pi} \int_{-\pi}^\pi X(\omega) e^{j \omega n} \, d\omega $$ |
| **Energy of DT Aperiodic Signals**          | $ E_x = \sum_{n=-\infty}^\infty \|x(n)\|^2 = \frac{1}{2 \pi} \int_{-\pi}^\pi \|X(\omega)\|^2 \, d\omega $  |
| **z-Transform and Fourier Relationship**    | $$ X(z) = \sum_{n=-\infty}^\infty x(n) z^{-n} $$ $$ X(\omega) = X(z) \text{ for } \|z\| = 1 $$          |
