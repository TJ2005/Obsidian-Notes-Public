---
Title: "Probabilistic"
Status: 
marker: 
tags: 
Date: "2025.05.04"
Time: "23:19"
---
# Probabilistic
**Fermat Test:** If n is prime then $$A^{n-1} \equiv 1 ~\text{mod}(n)$$
**Square Root Test:** If $n$ is prime then
$$
\sqrt{ 1}{~\text{mod}(n) }=\pm 1
$$
if $n$ is composite then
$$
\sqrt{ 1}{~\text{mod}(n) }=\pm 1
$$
And Possibly other values?

**Miller Rabin Test:** Miller Rabin combines the Fermats test and Square Root Test
$$
n-1 = m\times {2}^k
$$
$$
A^{m\times {2}^k} \equiv 1 ~\text{mod}(n)
$$
Instead of performing fermats test we do it $K+1$ Times that if the number is prime or not. If the square root test fails even once we consider $n$ a composite number.
(Congruence holds true for every prime number but the converse is not true. Thus probabilistic.)



# References


###### Information
- date: 2025.05.04
- time: 23:19