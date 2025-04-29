---
Title: Signals & System Transforms
Status: 
marker: 
tags: 
Date: 2024.11.25
Time: 13:37
---
# Signals & System Transforms

## List of Transforms in Signals and Systems

### 1. **Fourier Transform**
   - Converts a time-domain signal to its frequency-domain representation.
   - Continuous-Time Fourier Transform (CTFT):  
     $$X(j\omega) = \int_{-\infty}^{\infty} x(t)e^{-j\omega t}dt$$
   - Discrete-Time Fourier Transform (DTFT):  
     $$X(e^{j\omega}) = \sum_{n=-\infty}^{\infty} x[n]e^{-j\omega n}$$

### 2. **Inverse Fourier Transform**
   - Recovers the time-domain signal from its frequency-domain representation.
   - CTFT Inverse:  
     $$x(t) = \frac{1}{2\pi} \int_{-\infty}^{\infty} X(j\omega)e^{j\omega t}d\omega$$
   - DTFT Inverse:  
     $$x[n] = \frac{1}{2\pi} \int_{-\pi}^{\pi} X(e^{j\omega})e^{j\omega n}d\omega$$

### 3. **Laplace Transform**
   - Analyzes signals in the $s$-domain (complex frequency domain).
   - Definition:  
     $$X(s) = \int_{0}^{\infty} x(t)e^{-st}dt$$

### 4. **Inverse Laplace Transform**
   - Converts back to the time-domain from the $s$-domain.
   - Definition:  
     $$x(t) = \frac{1}{2\pi j} \int_{\sigma-j\infty}^{\sigma+j\infty} X(s)e^{st}ds$$

### 5. **Z-Transform**
   - Discrete counterpart of the Laplace Transform, useful for discrete signals.
   - Definition:  
     $$X(z) = \sum_{n=-\infty}^{\infty} x[n]z^{-n}$$

### 6. **Inverse Z-Transform**
   - Recovers the discrete-time signal from the $z$-domain.
   - Definition:  
     $$x[n] = \frac{1}{2\pi j} \oint X(z)z^{n-1}dz$$

### 7. **Discrete Fourier Transform (DFT)**
   - Frequency representation of discrete-time finite-duration signals.
   - Definition:  
     $$X[k] = \sum_{n=0}^{N-1} x[n]e^{-j\frac{2\pi}{N}kn}$$

### 8. **Inverse Discrete Fourier Transform (IDFT)**
   - Converts back from frequency-domain to discrete-time domain.
   - Definition:  
     $$x[n] = \frac{1}{N} \sum_{k=0}^{N-1} X[k]e^{j\frac{2\pi}{N}kn}$$

### 9. **Fast Fourier Transform (FFT)**
   - Algorithm to compute the DFT efficiently.

### 10. **Hilbert Transform**
   - Generates the analytic signal by introducing a phase shift of $90^\circ$.
   - Definition:  
     $$\hat{x}(t) = \frac{1}{\pi} \int_{-\infty}^{\infty} \frac{x(\tau)}{t-\tau}d\tau$$

### 11. **Wavelet Transform**
   - Analyzes signals in both time and frequency domains simultaneously.
   - Continuous Wavelet Transform (CWT):  
     $$W(a,b) = \int_{-\infty}^{\infty} x(t)\psi^{*}_{a,b}(t)dt$$
   - Discrete Wavelet Transform (DWT): Computed via filters.

### 12. **Short-Time Fourier Transform (STFT)**
   - Analyzes signals in small time segments for time-frequency representation.
   - Definition:  
     $$X(t, \omega) = \int_{-\infty}^{\infty} x(\tau)w(\tau-t)e^{-j\omega\tau}d\tau$$

### 13. **Hadamard Transform**
   - Used for signal compression and data processing.
   - Recursive definition using Walsh functions.

### 14. **Cosine Transform**
   - Variant of Fourier Transform using cosine basis.
   - Discrete Cosine Transform (DCT):  
     $$X[k] = \sum_{n=0}^{N-1} x[n]\cos\left[\frac{\pi}{N}\left(n+\frac{1}{2}\right)k\right]$$

### 15. **Radon Transform**
   - Projects a 2D function onto a 1D space.

### 16. **Chirp Z-Transform**
   - Computes Z-transform over a specified contour in the $z$-domain.

### 17. **Hartley Transform**
   - Alternative to Fourier Transform using cosine and sine simultaneously.
   - Definition:  
     $$H(\omega) = \int_{-\infty}^{\infty} x(t)[\cos(\omega t) + \sin(\omega t)]dt$$

### 18. **S-Transform**
   - Time-frequency localization similar to Wavelet Transform.

## References
Include proper citations for books or articles if needed.](<# Signals & System Transforms



# References


###### Information
- date: 2024.11.25
- time: 13:37>)