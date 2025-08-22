---
Title: Eulers Formula
Status: 
marker: 
tags: 
Date: 2025.02.06
Time: 18:57
---
# Eulers Formula

The property you're referring to is incorrect as written, but I believe you meant:  

$$
\cos(\theta) = \frac{e^{j\theta} + e^{-j\theta}}{2}
$$

This is a fundamental result derived from **Euler’s formula**, which states:  

$$
e^{j\theta} = \cos\theta + j\sin\theta
$$

$$
e^{-j\theta} = \cos\theta - j\sin\theta
$$

### Derivation of the Cosine Formula:
If we **add** these two equations:

$$
e^{j\theta} + e^{-j\theta} = (\cos\theta + j\sin\theta) + (\cos\theta - j\sin\theta)
$$

The imaginary terms \( j\sin\theta \) cancel out, leaving:

$$
e^{j\theta} + e^{-j\theta} = 2\cos\theta
$$

Dividing both sides by 2:

$$
\cos\theta = \frac{e^{j\theta} + e^{-j\theta}}{2}
$$

This shows that cosine can be written as the sum of two exponentials.

Similarly, if we subtract the two equations:

$$
e^{j\theta} - e^{-j\theta} = (\cos\theta + j\sin\theta) - (\cos\theta - j\sin\theta)
$$

The cosine terms cancel out, leaving:

$$
e^{j\theta} - e^{-j\theta} = 2j\sin\theta
$$

Dividing by \( 2j \):

$$
\sin\theta = \frac{e^{j\theta} - e^{-j\theta}}{2j}
$$

These two properties allow us to rewrite trigonometric functions in terms of exponentials, which is very useful in signals and systems, Fourier analysis, and other areas of engineering and physics.


# References


###### Information
- date: 2025.02.06
- time: 18:57


# Reference
In the image, the claim is that 2bi2^{bi} lies on a constant circle. To understand this, let's break it down mathematically.

### Step-by-step Explanation:

- **2bi2^{bi} is a complex exponential**: We know that complex exponentials have the form:
    
    ejθ=cos⁡(θ)+jsin⁡(θ)e^{j\theta} = \cos(\theta) + j\sin(\theta)
    
    In this case, we have a base of 2 raised to an imaginary exponent:
    
    2bi=ebiln⁡(2)2^{bi} = e^{bi \ln(2)}
    
    This can be written as:
    
    2bi=cos⁡(bln⁡(2))+jsin⁡(bln⁡(2))2^{bi} = \cos(b \ln(2)) + j \sin(b \ln(2))
    
    This represents a point on the unit circle in the complex plane because the magnitude of this complex number is always 1. The magnitude of ejθe^{j\theta} (or any complex exponential) is always 1, regardless of the value of θ\theta. This is why it lies on the unit circle.
    
- **The multiplication with its conjugate**: The equation 2bi⋅2−bi=12^{bi} \cdot 2^{-bi} = 1 involves multiplying a complex number by its conjugate. The conjugate of 2bi2^{bi} is 2−bi2^{-bi}, and when you multiply a complex number by its conjugate, the result is the square of the magnitude of the complex number.
    
    Since the magnitude of 2bi2^{bi} is 1, we get:
    
    2bi⋅2−bi=12^{bi} \cdot 2^{-bi} = 1
    
    This shows that the result of multiplying the complex exponential and its conjugate is indeed 1, which is a property of complex numbers where the magnitude squared equals 1.
    

### Conclusion:

Since 2bi2^{bi} lies on the unit circle (because it has magnitude 1), and its conjugate multiplicative gives 1, it confirms that the complex number 2bi2^{bi} will always stay on the unit circle in the complex plane. Thus, it moves along a constant circle centered at the origin with radius 1..