# **Introduction to Frequency Domain Analysis**

- **Frequency domain analysis** examines signals based on their **frequency components** rather than their time characteristics. This approach is used to understand how systems respond to different frequencies.
- **LTI systems** produce outputs that are **linearly related** to their inputs, and their properties **do not change over time**, making them fundamental in signal processing.

---

### **Key Mathematical Concepts in Frequency Domain Analysis**

#### **1. Frequency Response Function: H(ω)**

- The frequency response function, **H(ω)**, describes how an LTI system responds to each frequency component of an input signal. 
- When a complex exponential signal, **$x(n) = e^{jωn}$**, is input into an LTI system, the output, **y(n)**, is also a complex exponential at the same frequency, scaled by a factor:
  - **$y(n) = H(ω)e^{jωn}$**.
  
- The input complex exponential, **$x(n) = e^{jωn}$**, is an **eigenfunction** of the system.
- The scaling factor, **H(ω)**, is the **eigenvalue** of the system at that specific frequency.
  
- **H(ω)** is a complex-valued function and can be expressed in polar form as:
  - **$ H(ω) = |H(ω)|e^{j∠H(ω)} $**
    - **|H(ω)|** is the **magnitude**, showing how much the system amplifies or attenuates a frequency.
    - **∠H(ω)** is the **phase**, representing the phase shift applied to that frequency.
  
- **H(ω)** is the **Fourier transform** of the system and is **periodic** with a period of **2π**.

---

#### **2. System Effects on Signals**

- LTI systems affect input signals by **scaling their amplitude** and **shifting their phase**, and these effects depend on the frequency.
- The amount of **scaling** and **phase shift** is **frequency-dependent**.
- For an aperiodic input signal, **x(n)**, the output in the frequency domain is:
  - **Y(ω) = H(ω)X(ω)**,
    where **X(ω)** and **H(ω)** are the Fourier transforms of the input and the system, respectively.
- The output’s magnitude is:
  - **|Y(ω)| = |H(ω)||X(ω)|**.
- The output’s phase is:
  - **$∠Y(ω) = ∠H(ω) + ∠X(ω)$**.

---

#### **3. Rational System Function**

- The **Fourier transform** can be viewed as the **z-transform** evaluated on the **unit circle**.
- The system function, **H(z)**, is typically a **rational function**:
  - **H(z) = B(z)/A(z)**, where **B(z)** and **A(z)** are polynomials.
    - **B(z) = b₀ + b₁z⁻¹ + b₂z⁻² + ... + bₘz⁻ᵐ**
    - **A(z) = a₀ + a₁z⁻¹ + a₂z⁻² + ... + aₙz⁻ⁿ**
- The system's behavior is analyzed using its **poles** and **zeros** in the **z-plane**.

---

### **LTI Systems as Frequency-Selective Filters**

- LTI systems can act as **filters**, designed to pass or block specific frequencies in a signal.
- The frequency response, **H(ω)**, modifies the spectrum of the input signal by altering the amplitude of different frequency components.

---

#### **Types of Ideal Filters**

- **Lowpass filters**: Pass low frequencies and block high frequencies.
- **Highpass filters**: Pass high frequencies and block low frequencies.
- **Bandpass filters**: Pass frequencies within a certain range and block others.
- **Bandstop filters**: Block frequencies within a certain range and pass others.
- **All-pass filters**: Pass all frequencies but may alter their phase, maintaining a constant magnitude response.
- **Digital Resonators**: Two-pole bandpass filters with a pair of complex-conjugate poles near the unit circle.
- **Notch filters**: Filters with one or more nulls in their frequency response. These nulls are created by pairs of complex-conjugate zeros on the unit circle.
- **Comb filters**: Notch filters with nulls spaced periodically across the spectrum.

---

#### **Characteristics of Ideal Filters**

- **Flat (unity) frequency response magnitude** in the **passband**:
  - **|H(ω)| = C** (typically, **C = 1**) in the passband.
- **Zero frequency response** in the **stopband**:
  - **|H(ω)| = 0** in the stopband.
- **Linear phase**:
  - **∠H(ω) = -ωn₀** for constant *n₀*.

---

### **Inverse Systems and Deconvolution**

- In many applications, it is necessary to undo unwanted processing of a signal.
- **Inverse systems** are used to reverse the effects of a system on a signal.
- **Invertible systems** have a one-to-one correspondence between inputs and outputs, enabling the reversal of the transformation.
- **Deconvolution** is used to improve signal resolution.
  
#### **Examples:**
- **Equalization**: Reverses intersymbol interference in telecommunications.
- **Restoration/Enhancement**: Corrects blurring effects in biomedical imaging.
- **Deconvolution**: Increases signal resolution in reflection seismology.

- The goal is to find the inverse system, **h₁(n)**, such that when convolved with the original system’s impulse response, **h(n)**, it results in a unit impulse:
  - **$h(n) * h₁(n) = δ(n)$**.
  
- In the **z-domain**, the inverse system is given by the reciprocal of the original system’s transfer function:
  - **$ H₁(z) = \frac{1}{H(z)} $**.

---

### **Key Mathematical Concepts Defined**

- **Frequency Domain**: The analysis of signals based on their frequency components.
- **LTI Systems**: Systems where the behavior does not change over time and is linear.
- **Eigenfunction**: An input to a system that results in an output that is just a scaled version of the input.
  - **$x(n) = e^{jωn}$**.
- **Eigenvalue**: The scaling factor associated with an eigenfunction.
  - **H(ω)**.
- **Frequency Response**: How a system responds to different frequencies, showing magnitude and phase shift.
  - **$H(ω) = |H(ω)|e^{j∠H(ω)}$**.
- **Passband**: The range of frequencies that a filter allows to pass through.
- **Stopband**: The range of frequencies that a filter blocks.
- **Deconvolution**: The process of reversing the effects of a system to recover the original input.
