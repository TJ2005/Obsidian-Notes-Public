---
Title: Probability & Statistics Lecture 11
Status: 
marker: 
tags: 
Date: 2025.01.31
Time: 11:07
---
> [!Continued From]
> [[Probability and Statistics Lecture 10]]


## Snippet on general form for $U.V$
$$
\int u.v~dx=u\int v.dx - \frac{du}{dv}\int v.dx + \frac{d^2u}{dx^2}\int v~+....
$$

# Question on Raw Moment
### Question 1
$$
F(X)=
\begin{cases} 
\frac{1}{4}e^{-\frac{x}{4}}, & x > 0 \\
0, & \text{otherwise}
\end{cases}
$$

#### Calculating $\mu'_1$
The first raw moment is:

$$
\mu'_1 = E(X) = \int_{0}^{\infty} x f(x) dx
$$
Substituting the PDF:

$$
\mu'_1 = \int_{0}^{\infty} x \frac{e^{-\frac{x}{4}}}{4} dx
$$
Simplifying:

$$
\mu'_1 = \frac{1}{4} \int_{0}^{\infty} x e^{-\frac{x}{4}} dx
$$

Using integration by parts:

$$
\mu'_1 = \frac{1}{4} \left[ (-4) x e^{-\frac{x}{4}} - \int e^{-\frac{x}{4}} \right]_{0}^{\infty}
$$

Evaluating the integral:

$$
\mu'_1 = \frac{1}{4} \left[ 0 + 16 e^{-\frac{x}{4}} \right]_{0}^{\infty}
$$

Final value:

$$
\mu'_1 = 4
$$

#### Calculating $\mu'_2$ (Second Raw Moment)

The second raw moment is:

$$
\mu'_2 = E(X^2) = \int_{0}^{\infty} x^2 f(x) dx
$$
Substituting the PDF:

$$
\mu'_2 = \int_{0}^{\infty} x^2 \frac{e^{-\frac{x}{4}}}{4} dx
$$

Simplifying:

$$
\mu'_2 = \frac{1}{4} \int_{0}^{\infty} x^2 e^{-\frac{x}{4}} dx
$$

Using integration by parts twice:

$$
\mu'_2 = \frac{1}{4} \left[ (-4) x^2 e^{-\frac{x}{4}} - 8 x e^{-\frac{x}{4}} + 8 e^{-\frac{x}{4}} \right]_{0}^{\infty}
$$

Evaluating:

$$
\mu'_2 = 32
$$

#### Calculating $\mu'_3$ (Third Raw Moment)

The third raw moment is:

$$
\mu'_3 = E(X^3) = \int_{0}^{\infty} x^3 f(x) dx
$$
Substituting the PDF:

$$
\mu'_3 = \frac{1}{4} \int_{0}^{\infty} x^3 e^{-\frac{x}{4}} dx
$$

Using integration by parts three times:

$$
\mu'_3 = \frac{1}{4} \left[ (-4) x^3 e^{-\frac{x}{4}} - 12 x^2 e^{-\frac{x}{4}} + 48 x e^{-\frac{x}{4}} - 48 e^{-\frac{x}{4}} \right]_{0}^{\infty}
$$

Evaluating:

$$
\mu'_3 = 192
$$

#### Calculating $\mu'_4$ (Fourth Raw Moment)

The fourth raw moment is:

$$
\mu'_4 = E(X^4) = \int_{0}^{\infty} x^4 f(x) dx
$$
Substituting the PDF:

$$
\mu'_4 = \frac{1}{4} \int_{0}^{\infty} x^4 e^{-\frac{x}{4}} dx
$$

Using integration by parts four times:

$$
\mu'_4 = \frac{1}{4} \left[ (-4) x^4 e^{-\frac{x}{4}} - 16 x^3 e^{-\frac{x}{4}} + 48 x^2 e^{-\frac{x}{4}} - 192 x e^{-\frac{x}{4}} + 192 e^{-\frac{x}{4}} \right]_{0}^{\infty}
$$

Evaluating:

$$
\mu'_4 = 768
$$

### Central Moments

The central moment $\mu_r$ is given by:

$$
\mu_r = E[(X - \mu'_1)^r] = \int_{0}^{\infty} (x - \mu'_1)^r f(x) dx
$$

#### Calculating the Central Moment $\mu_2$ (Variance)

$$
\mu_2 = E[(X - \mu'_1)^2] = \mu'_2 - (\mu'_1)^2
$$

Using the values for \( \mu'_1 \) and \( \mu'_2 \):

$$
\mu_2 = 32 - 4^2 = 32 - 16 = 16
$$

#### Calculating the Central Moment $\mu_3$

$$
\mu_3 = E[(X - \mu'_1)^3] = \mu'_3 - 3 \mu'_2 \mu'_1 + 2 (\mu'_1)^3
$$

Substitute the values:

$$
\mu_3 = 192 - 3 \cdot 32 \cdot 4 + 2 \cdot 4^3 = 192 - 384 + 128 = -64
$$

#### Calculating the Central Moment $\mu_4$

$$
\mu_4 = E[(X - \mu'_1)^4] = \mu'_4 - 4 \mu'_3 \mu'_1 + 6 \mu'_2 (\mu'_1)^2 - 3 (\mu'_1)^4
$$

Substitute the values:

$$
\mu_4 = 768 - 4 \cdot (-64) \cdot 4 + 6 \cdot 32 \cdot 4^2 - 3 \cdot 4^4
$$
$$
\mu_4 = 768 + 1024 + 1536 - 768 = 2560
$$


> [!Continued To]
>  [[Probability and Statistics Lecture 12]]

