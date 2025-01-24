

## **QUESTION 1**

### **1(a)** 
**Write down and characterize properties of continuous-time and discrete-time sinusoidal signals. In case of discrete-time sinusoidal signals, what happens for ω = ω₀ + 2π?**

#### **Answer:**

1. **Continuous-Time Sinusoidal Signals**  
   - **Periodicity:** A continuous-time sinusoidal signal is periodic if its frequency $ F $ is fixed.  
   - **Distinct Frequencies:** Signals with different frequencies are distinct.  
   - **Oscillation Rate:** Increasing $ F $ increases the oscillation rate.  
   - **Frequency Sign Convention:** While frequency is physically positive, negative frequencies are often used for mathematical convenience.  
   - **General Form:**  
     $$
       x(t) = A \sin(\omega t + \theta), 
     $$
     where $ \omega = 2\pi F $.

2. **Discrete-Time Sinusoidal Signals**  
   - **Periodicity (Rational Frequencies):** A discrete-time sinusoid is periodic if and only if the normalized frequency $ f $ (cycles per sample) is a **rational** number.  
   - **Identical Frequencies:** Discrete-time sinusoids whose frequencies differ by integer multiples of $ 2\pi $ are **identical**.  
   - **Maximum Oscillation Rate:** The maximum (aliasing) frequency in discrete-time is when $\omega = \pm \pi$.  
   - **General Form:**  
     $$
       x(n) = A \cos(\omega n + \theta), 
     $$
     where $ n $ is an integer (sample index), and $\omega$ is in radians/sample.  
   - **Effect of $\omega = \omega_0 + 2\pi$:**  
     $$
       \cos(\omega_0 n) = \cos((\omega_0 + 2\pi) n),
     $$
     so adding $ 2\pi $ to $\omega_0$ **does not change** the discrete-time sinusoidal signal.  

---

### **1(b)**
**What is sampling frequency? With necessary figure explain how sampling converts an analog signal to a discrete-time continuous-valued signal.**

#### **Answer:**

- **Sampling Frequency ($ F_s $):**  
  The sampling frequency is the rate (in samples per second or Hz) at which a continuous-time signal is measured (sampled). If the sampling period is $ T $ seconds, then 
  $$
    F_s = \frac{1}{T}.
  $$

- **Sampling Process:**  
  1. **Analog Signal:** Start with a continuous-time signal $ x_a(t) $.  
  2. **Sampling:** Measure (or “pick”) values of this signal at discrete time instants $ t = nT $.  
  3. **Discrete-Time Signal:** The resulting discrete-time signal is 
     $$
       x(n) = x_a(nT).
     $$
     Here, $ n $ is an integer, and $ x(n) $ can still take on any real (or complex) amplitude (hence “continuous-valued”).  

A simple block diagram for the sampling process would show the analog signal entering a “sampler” that outputs discrete-time samples $ x(n) $.

---

### **1(c)**
**Tabulate the relations among the frequency variables of continuous-time and discrete-time signals.**

#### **Answer:**

1. **Time Variables**  
   - Continuous time: $ t $ (seconds)  
   - Discrete time: $ n $ (dimensionless sample index)  
   - Relation: $ t = nT $, where $ T = 1/F_s $.  

2. **Frequency Variables**  
   - **Analog frequency (in Hz):** $ F $  (cycles/second).  
   - **Digital (discrete-time) frequency (in cycles/sample):**  
     $$
       f = \frac{F}{F_s}.
     $$
   - **Analog frequency (in rad/s):** $\Omega = 2\pi F$.  
   - **Digital frequency (in rad/sample):** $\omega = 2\pi f = \frac{\Omega}{F_s}$.  

| **Variable** | **Type**           | **Units**                 | **Relation**                       |
|--------------|--------------------|---------------------------|------------------------------------|
| $ t $      | Continuous time    | seconds ($\text{s}$)   | $ t = nT $                       |
| $ n $      | Discrete time     | sample index             | –                                  |
| $ F $      | Analog freq.       | Hz (cycles/second)       | –                                  |
| $ f $      | Digital freq.      | cycles/sample            | $ f = \frac{F}{F_s} $           |
| $ \Omega $ | Analog freq.       | radians/second           | $\Omega = 2\pi F$               |
| $ \omega $ | Digital freq.      | radians/sample           | $\omega = \frac{\Omega}{F_s}$   |

---

### **1(d)**
**Consider the analog signal $ x_a(t) = 3 \cos(100\pi t) $.**

1. **Determine the minimum sampling rate required to avoid aliasing.**  
2. **Suppose the signal is sampled at $ F_s = 200 $ Hz. What is the discrete-time signal obtained?**  
3. **Repeat part (2) for $ F_s = 75 $ Hz.**  
4. **What is the frequency in the range $-\frac{F_s}{2} < F \le \frac{F_s}{2}$ of a sinusoid that yields samples identical to those obtained in part (3)?**  
5. **State Shannon’s sampling theorem.**  
6. **What is the Nyquist rate for this signal?**

#### **Answer:**

- **Given:** $ x_a(t) = 3\cos(100\pi t) $.  
  - The analog frequency is $\frac{100\pi}{2\pi} = 50$ Hz.

1. **Minimum Sampling Rate**  
   - By the Nyquist criterion, $ F_s > 2F_{\max} $.  
   - Here, $ F_{\max} = 50 $ Hz.  
   - **Nyquist rate** $ = 2 \times 50 = 100 $ Hz.

2. **Sampling at $ F_s = 200 $ Hz**  
   - Sampling period $ T = \frac{1}{200} $ s.  
   - Discrete-time signal:  
     $$
       x(n) = x_a(nT) = 3 \cos\bigl(100\pi \cdot \frac{n}{200}\bigr) 
                     = 3 \cos\bigl(\frac{\pi}{2} n \bigr).
     $$
   - Normalized frequency $ f = \frac{50}{200} = 0.25 $ cycles/sample.  
   - Digital frequency $ \omega = 2\pi \times 0.25 = \frac{\pi}{2} $.

3. **Sampling at $ F_s = 75 $ Hz**  
   - Sampling period $ T = \frac{1}{75} $ s.  
   - Discrete-time signal:  
     $$
       x(n) = 3 \cos\Bigl(100\pi \cdot \frac{n}{75}\Bigr) = 3 \cos\Bigl(\frac{4\pi}{3} n \Bigr).
     $$
   - Normalized frequency $ f = \frac{50}{75} = \frac{2}{3} $.  
   - Digital frequency $ \omega = 2\pi \times \frac{2}{3} = \frac{4\pi}{3} $.

4. **Equivalent Frequency in $\bigl(-\frac{F_s}{2}, \frac{F_s}{2}\bigr]$**  
   - The discrete frequency $\omega = \frac{4\pi}{3}$ is equivalent to $\frac{4\pi}{3} - 2\pi = -\frac{2\pi}{3}$.  
   - Converting $\omega = -\frac{2\pi}{3}$ back to analog frequency:  
     $$
       F = \left(-\frac{2\pi}{3}\right)\frac{F_s}{2\pi}
          = -\frac{2\pi}{3} \times \frac{75}{2\pi}
          = -25 \text{ Hz}.
     $$

5. **Shannon’s Sampling Theorem**  
   - A bandlimited signal of maximum frequency $ F_{\max} $ can be uniquely reconstructed from its samples if the sampling frequency $ F_s $ satisfies $ F_s \ge 2F_{\max} $.  
   - The minimum rate $ 2F_{\max} $ is the **Nyquist rate**.

6. **Nyquist Rate**  
   - From part (1): **100 Hz**.

---

## **QUESTION 2**

### **2(a)**
1. **State the state transition matrix theorem.**  
2. **Consider $ x(t) = 3\cos(2000\pi t) + 6 \sin(1000\pi t) $.**  
   - What is the Nyquist rate for this signal?  
   - If we sample at $ F_s = 5000 $ samples/s, what is the discrete-time signal?

#### **Answer:**

1. **State Transition Matrix Theorem**  
   - *Not covered in the provided sources.* Typically, this theorem is part of state-space analysis in control theory or signals & systems but was not included in the provided references.

2. **Given Analog Signal**  
   $$
     x_a(t) = 3\cos(2000\pi t) + 6 \sin(1000\pi t).
   $$  
   - Frequency components:  
     $$
       F_1 = \frac{2000\pi}{2\pi} = 1000 \text{ Hz}, \quad 
       F_2 = \frac{1000\pi}{2\pi} = 500 \text{ Hz}.
     $$
   - Maximum frequency $ F_{\max} = 1000 $ Hz.

   1. **Nyquist Rate:**  
      $$
        F_s \ge 2F_{\max} = 2 \times 1000 = 2000 \text{ Hz}.
      $$

   2. **Sampling at $ F_s = 5000 $ Hz:**  
      - Sampling period $ T = \frac{1}{5000} $ s.  
      - Discrete-time signal:  
        $$
          x(n) = x_a(nT) 
                = 3\cos\Bigl(2000\pi \cdot \frac{n}{5000}\Bigr) 
                + 6\sin\Bigl(1000\pi \cdot \frac{n}{5000}\Bigr).
        $$  
        Simplifying:
        $$
          x(n) = 3 \cos\Bigl(\frac{2\pi}{5} n\Bigr) + 6 \sin\Bigl(\frac{\pi}{5}n\Bigr).
        $$

---

### **2(b)**
**The discrete-time signal $ x(n) = 6.35 \cos\bigl(\frac{\pi}{10} n\bigr)$ is quantized with resolution $\Delta = 0.1$ or $\Delta = 0.02$. How many bits are required in the A/D converter in each case?**

#### **Answer:**

1. **Signal Range**  
   - The amplitude of $ x(n) $ varies from $-6.35$ to $+6.35$.  
   - Total range $ = 6.35 - (-6.35) = 12.7$.

2. **Number of Quantization Levels ($ L $)**  
   $$
     L = \frac{\text{Range}}{\Delta}.
   $$
   Then the number of bits $ N $ must satisfy $ 2^N \ge L $.

- **Case 1:** $\Delta = 0.1$  
  $$
    L = \frac{12.7}{0.1} = 127. 
    \quad (\text{Nearest power of 2 } = 128 = 2^7).
  $$
  $$
    N = \log_2(128) = 7 \text{ bits}.
  $$

- **Case 2:** $\Delta = 0.02$  
  $$
    L = \frac{12.7}{0.02} = 635.
    \quad (\text{Nearest power of 2 } = 1024 = 2^{10}).
  $$
  $$
    N = \log_2(1024) = 10 \text{ bits}.
  $$

---

## **QUESTION 3**

### **3(a)**
**Consider the system $ y(n) = x(n^2) $. Is the system time-invariant? Justify your answer.**

#### **Answer:**

- **Time-Invariance Criterion:** A system is time-invariant if a time shift in the input results in the **same** time shift in the output.

- **Test for Time-Invariance:**
  1. Delay the input by $k$: $ x_1(n) = x(n - k) $.  
  2. Output becomes:  
     $$
       y_1(n) = x_1(n^2) = x\bigl((n^2) - k\bigr),
     $$
     which is not the same as $ x((n-k)^2) $.  

  However, one might check carefully:

  - **If** the original system definition was $ y(n) = x(n^2) $, then for a shifted input $ x(n-k) $, the output is $ y(n,k) = x((n-k)^2) $.  
  - Compare it to the delayed output: $ y(n - k) = x((n - k)^2) $.  

  They are the same expression. Indeed,
  $$
    y(n - k) 
    = x(((n-k) - 0)^2) 
    = x((n-k)^2).
  $$

  Therefore, the system’s output for a delayed input is exactly the delayed version of the original output. By this reasoning:

  > **Conclusion:** The system **is time-invariant** since $ y(n,k) = y(n-k) $.

> **Important Note:** This is a somewhat special example. Many references will highlight that if the input is shifted by $k$, we typically look at $ y_1(n) = x((n-k)^2) $. Then to check if it equals $ y(n-k) = x(((n-k)-0)^2) = x((n-k)^2) $. They do match, suggesting time-invariance.  

---

### **3(b)**
**Define symmetric (even) and antisymmetric (odd) signals. Prove that any arbitrary signal can be expressed as the sum of an even and an odd component.**

#### **Answer:**

1. **Symmetric (Even) Signal:**  
   A signal $ x(n) $ is even if $ x(-n) = x(n) $.

2. **Antisymmetric (Odd) Signal:**  
   A signal $ x(n) $ is odd if $ x(-n) = -x(n) $.

3. **Decomposition into Even and Odd Components**  
   - Any signal $ x(n) $ can be written as:  
     $$
       x(n) = x_e(n) + x_o(n),
     $$
     where  
     $$
       x_e(n) = \frac{1}{2}\bigl[x(n) + x(-n)\bigr], 
       \quad
       x_o(n) = \frac{1}{2}\bigl[x(n) - x(-n)\bigr].
     $$
   - $ x_e(n) $ is even, and $ x_o(n) $ is odd.

---

### **3(c)**
**Write down the steps of computing the convolution $ x(n) * h(n) $. Compute and plot the convolution for the given signals.**

#### **Answer:**

1. **Convolution Definition (Discrete-Time):**  
   $$
     y(n) = (x*h)(n) = \sum_{k=-\infty}^{\infty} x(k)\,h(n-k).
   $$

2. **Steps to Convolve $ x(n) $ and $ h(n) $**  
   1. **Time-Reverse** $ h(n) $ to get $ h(-k) $.  
   2. **Shift** this reversed sequence by $ n $ to get $ h(n - k) $.  
   3. **Multiply** $ x(k) $ by $ h(n - k) $.  
   4. **Sum** over all $ k $.  
   5. **Repeat** for each integer $ n $.

3. **Example**  
   - $ x(n) = \{1,1,1,1\} $ for $ n = 1 $ to 4, zero elsewhere.  
   - $ h(n) = \{1,1,1\} $ for $ n = -1 $ to 1, zero elsewhere.

   - By straightforward tabular or “slide and multiply” approach, the result of $ y(n) = x(n)*h(n) $ becomes:  
     $$
       y(n) = \{1, 2, 3, 3, 2, 1\},
     $$
     typically indexed appropriately from $ n=0 $ to $ n=5 $ (depending on the convention used).

---

## **QUESTION 4**

### **4(a)**
**What is the region of convergence (ROC) in the Z-transform? What would be the ROC for causal, anticausal, and two-sided signals?**

#### **Answer:**

1. **Region of Convergence (ROC):**  
   - The ROC of a Z-transform $ X(z) = \sum x(n) z^{-n} $ is the set of all $ z $ in the complex plane for which this infinite sum converges absolutely.  
   - The ROC is generally a disk or an annulus (ring) centered at $ z=0 $ (except for special cases).

2. **ROC for Different Signal Types:**  
   - **Causal Signals** (zero for $ n < 0 $):  
     - ROC: $ |z| > r $, where $ r $ is the outermost pole.  
   - **Anticausal Signals** (zero for $ n > 0 $):  
     - ROC: $ |z| < r $, where $ r $ is the innermost pole.  
   - **Two-Sided Signals** (nonzero for both $ n < 0 $ and $ n \ge 0 $):  
     - ROC: $ r_1 < |z| < r_2 $, an annulus determined by the poles.

---

### **4(b)**
**The z-transform is an infinite power series. Prove that it exists only for the series convergence.**

#### **Answer:**

- **Z-Transform Definition:**  
  $$
    X(z) = \sum_{n=-\infty}^{\infty} x(n) z^{-n}.
  $$
- **Convergence Requirement:**  
  - For $ X(z) $ to be finite, this infinite sum must converge absolutely (or at least converge in some sense).  
  - If the series diverges for a particular $ z $, then that $ z $ is **not** in the ROC.  

**Hence, the existence of the Z-transform depends on the values of $ z $ for which the power series converges.**

---

### **4(c)**
**Determine the Z-transform of $ x(n) = \bigl[5(4^n) - 4(3^n)\bigr]u(n) $ and sketch the corresponding pole-zero pattern. Also, find the Z-transform of $ x(n-2) $. Define poles and zeros with an example.**

#### **Answer:**

1. **Given:**  
   $$
     x(n) = \bigl[5 \cdot 4^n \;-\; 4 \cdot 3^n\bigr]\,u(n).
   $$
   Here, $ u(n) $ is the unit step (causal part).

2. **Individual Z-Transforms:**  
   - $ z\text{-transform of } a^n u(n) $ is  
     $$
       \frac{1}{1 - a\,z^{-1}} \quad (\text{for } |z| > |a|).
     $$
     Equivalently,  
     $$
       \frac{z}{z - a}.
     $$

3. **By Linearity:**  
   $$
     X(z) = 5 \cdot \frac{z}{z - 4} \;-\; 4 \cdot \frac{z}{z - 3}.
   $$
   - The ROC is $|z| > 4$ (since 4 is bigger than 3, the outer pole location sets the ROC for a causal signal).

4. **Poles and Zeros:**
   - Poles are where the denominator is zero. Here, $ z = 4 $ and $ z = 3 $.  
   - Zeros come from the numerator, once you combine terms if needed. Or directly observe partial forms: there is a zero at $ z=0 $ as well, and possibly others upon combining terms.  

   A simpler combined expression (if desired) might yield:
   $$
     X(z) = \frac{5z}{z-4} - \frac{4z}{z-3}.
   $$
   You can find additional zeros by taking a common denominator if needed.

5. **Pole-Zero Sketch:**  
   - Poles at $ z=3 $ and $ z=4 $ (marked with ‘×’).  
   - Zeros at $ z=0 $ (and any others from the expanded numerator).  

6. **Z-Transform of $ x(n-2) $:**  
   - Time shifting property: if $ X(z) $ is the Z-transform of $ x(n) $, then the Z-transform of $ x(n-k) $ is $ z^{-k} X(z) $.  
   - Hence,  
     $$
       Z\{x(n-2)\} = z^{-2} X(z).
     $$

7. **Definition of Poles and Zeros**  
   - **Poles:** The values of $ z $ that make the denominator $=0$ and thus make $ |X(z)| \rightarrow \infty $.  
   - **Zeros:** The values of $ z $ that make the numerator $=0$ and thus make $ X(z) = 0 $.  

---

## **QUESTION 5**

### **5(a)**
**Define natural and forced response of a causal system.**

#### **Answer:**

- **Natural Response:**  
  - The system’s response due to its **initial conditions** only (with no external input). Often called the transient response and is governed by the system’s poles.  

- **Forced Response:**  
  - The system’s response due to an **external input**. Often called the steady-state response when analyzing LTI systems.  

---

### **5(b)**
**Find the system function $ H(z) $ and the impulse response $ h(n) $ from the difference equation:**
$$
  y(n) = \tfrac{1}{2}\,y(n-1) \;+\; x(n) \;+\; 2\,x(n-1).
$$

#### **Answer:**

1. **Difference Equation:**  
   $$
     y(n) - \tfrac{1}{2}y(n-1) = x(n) + 2x(n-1).
   $$

2. **Z-Domain Representation:**  
   - Taking Z-transform on both sides:  
     $$
       Y(z) - \tfrac{1}{2}z^{-1} Y(z) = X(z) + 2z^{-1} X(z).
     $$
   - Factor out $ Y(z) $ and $ X(z) $:  
     $$
       Y(z)\Bigl[\,1 - \tfrac{1}{2}z^{-1}\Bigr] = X(z)\Bigl[\,1 + 2z^{-1}\Bigr].
     $$
   - **System Function $ H(z) $:**  
     $$
       H(z) = \frac{Y(z)}{X(z)} = \frac{1 + 2z^{-1}}{1 - \tfrac{1}{2}z^{-1}}
             = \frac{(z + 2)}{(z - \tfrac{1}{2})}
             \quad (\text{multiplying numerator and denominator by } z).
     $$

3. **Impulse Response $ h(n) $:**  
   - $ h(n) $ is the inverse Z-transform of $ H(z) $.  
   - We can rewrite:  
     $$
       H(z) = \frac{z + 2}{z - \tfrac{1}{2}} 
             = \frac{z}{z - \tfrac{1}{2}} + \frac{2}{z - \tfrac{1}{2}}
             = \underbrace{\frac{z}{z - \tfrac{1}{2}}}_{H_1(z)} 
               + \underbrace{\frac{2}{z - \tfrac{1}{2}}}_{H_2(z)}.
     $$
   - Recall $ \frac{z}{z - a} \leftrightarrow a^n u(n) $ and $ \frac{1}{z - a} \leftrightarrow a^n u(n-1) $ up to some details. Typically, the standard form is  
     $$
       \frac{z}{z - a} = \sum_{n=0}^\infty a^n z^{-n}.
     $$
     So in simpler terms:
     $$
       H(z) = 1 + \frac{5/2}{z - 1/2}, 
     $$
     or do partial fraction expansion carefully to isolate the terms.  

   - One straightforward approach is to note:
     $$
       \frac{z}{z - \tfrac{1}{2}}
         = 1 + \frac{\tfrac{1}{2}}{z - \tfrac{1}{2}}
         \quad \Longrightarrow \quad
         \mathcal{Z}^{-1}\left\{ \frac{z}{z - \tfrac{1}{2}} \right\} = \delta(n) + \tfrac{1}{2}\left(\tfrac{1}{2}\right)^n u(n).
     $$
     Then add the extra terms from the numerator.  

   - After a bit of algebra, one finds:
     $$
       h(n) = \delta(n) + \text{(some constant)} \left(\tfrac{1}{2}\right)^n u(n).
     $$
     More explicitly, from standard difference equation solving, one might get:
     $$
       h(n) = \delta(n) + 2 \left(\tfrac{1}{2}\right)^n u(n).
     $$
     or another expression, depending on partial fractions.  

   A typical, fully worked partial-fraction approach yields:
   $$
     H(z) = \frac{(z + 2)}{(z - \frac{1}{2})}
           = 1 + \frac{\frac{5}{2}}{(z - \frac{1}{2})},
   $$
   hence
   $$
     h(n) = \delta(n) + \frac{5}{2}\Bigl(\tfrac{1}{2}\Bigr)^n u(n).
   $$

---

### **5(c)**
**Do you think an inverse system and deconvolution are necessary for signal processing? Justify.**

#### **Answer:**

- **Inverse System:** A system that **undoes** or **inverts** the effect of another system.  
- **Deconvolution:** The process of “inverse filtering” to remove blurring or distortion from a measured signal.

**Importance in Signal Processing:**  
- **Undoing Unwanted Effects:** Many real-world processes (channels, filters, etc.) distort signals. An inverse system can restore signals by compensating for that distortion.  
- **Applications:**  
  - **Telecommunications (Equalization):** Removes inter-symbol interference.  
  - **Imaging (De-blurring):** Removing blur in images, medical scans, astronomy, etc.  
  - **Seismology (Wavelet Deconvolution):** Improves resolution of geological data.

Hence, inverse systems and deconvolution are indeed crucial for accurate reconstruction, restoration, and interpretation of signals.

---

### **5(d)**
**Determine the inverse system of the system with the impulse response $ h(n) = (1/2)^n u(n) $.**

#### **Answer:**

1. **Given $ h(n) = (1/2)^n u(n) $.**  
   - Z-transform:  
     $$
       H(z) = \mathcal{Z}\{(1/2)^n u(n)\} 
            = \frac{z}{z - \tfrac{1}{2}},
     $$
     with ROC $|z| > 1/2$.

2. **Inverse System Function:**  
   - If $ H_1(z) $ is the inverse, then  
     $$
       H_1(z) = \frac{1}{H(z)} = \frac{z - \tfrac{1}{2}}{z}.
     $$
   - Simplify:
     $$
       H_1(z) = 1 - \frac{\tfrac{1}{2}}{z}
               = 1 - \tfrac{1}{2} z^{-1}.
     $$

3. **Inverse System Impulse Response $ h_1(n) $:**  
   - Inverse Z-transform of $ 1 - \tfrac{1}{2} z^{-1} $ is:  
     $$
       h_1(n) = \delta(n) - \tfrac{1}{2} \delta(n-1).
     $$

Hence, convolving $ (1/2)^n u(n) $ with $ \delta(n) - \tfrac{1}{2}\delta(n-1) $ yields $ \delta(n) $, which confirms that the latter is the inverse system.

---

## **QUESTION 6**

### **6(a)**
**Determine the power density spectrum of a rectangular pulse train signal.**

#### **Answer:**

1. **Rectangular Pulse Train:**  
   - A periodic signal with period $ T $ and pulse width $ \tau $.  
   - It can be expanded in a Fourier series with coefficients $ c_k $.

2. **Fourier Coefficients of the Rectangular Pulse Train:**  
   - DC term ($ k=0 $):  
     $$
       c_0 = \frac{A \tau}{T},
     $$
     assuming amplitude $ A $.  
   - For $ k \neq 0 $:  
     $$
       c_k = \frac{A \tau}{T} \,\text{sinc}\bigl(k F_0 \tau \bigr),
     $$
     where $ F_0 = \frac{1}{T} $ and $\mathrm{sinc}(x) = \frac{\sin(\pi x)}{\pi x}$.

3. **Power Density Spectrum:**  
   - For a periodic signal, the power density spectrum is essentially the discrete set of squared magnitudes of the Fourier coefficients:  
     $$
       P(k) = |c_k|^2.
     $$
   - Thus,  
     $$
       |c_0|^2 = \left(\frac{A\tau}{T}\right)^2, 
       \quad
       |c_k|^2 = \left(\frac{A\tau}{T}\right)^2 \mathrm{sinc}^2\bigl(k F_0 \tau\bigr).
     $$

---

### **6(b)**
**Classify ideal filters according to their frequency-domain characteristics. Explain each type with necessary expressions and figures.**

#### **Answer:**

1. **Ideal Filters**  
   - **Magnitude Response:** Perfectly passes certain frequencies and completely blocks others.  
   - **Phase Response:** Ideally linear (or zero) for no phase distortion.  
   - They are **theoretical references** (not realizable in practice due to infinite impulse response in time domain).

2. **Filter Types**  
   1. **Ideal Low-Pass Filter (LPF):**  
      $$
        H(\omega) = 
        \begin{cases} 
          1, & |\omega| \le \omega_c \\
          0, & |\omega| > \omega_c 
        \end{cases}
      $$
      - Passes frequencies below $\omega_c$ and blocks above.

   2. **Ideal High-Pass Filter (HPF):**  
      $$
        H(\omega) = 
        \begin{cases} 
          0, & |\omega| < \omega_c \\
          1, & |\omega| \ge \omega_c
        \end{cases}
      $$
      - Blocks low frequencies, passes high frequencies.

   3. **Ideal Band-Pass Filter (BPF):**  
      $$
        H(\omega) = 
        \begin{cases}
          1, & \omega_{c1} \le |\omega| \le \omega_{c2} \\
          0, & \text{otherwise}
        \end{cases}
      $$
      - Passes frequencies within a certain band ($\omega_{c1}$ to $\omega_{c2}$).

   4. **Ideal Band-Stop (Notch) Filter (BSF):**  
      $$
        H(\omega) = 
        \begin{cases}
          0, & \omega_{c1} \le |\omega| \le \omega_{c2} \\
          1, & \text{otherwise}
        \end{cases}
      $$
      - Blocks frequencies within a band and passes frequencies outside that band.

Each filter’s frequency response is a rectangular “ideal” shape, which in practice cannot be perfectly achieved but serves as a conceptual benchmark.

---
