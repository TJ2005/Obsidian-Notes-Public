---
Title: Primes, primality testing, factorization
Status: 
marker: 
tags: 
Date: 2025.05.04
Time: 23:10
---
# Primes, primality testing, factorization
## Generating Primes
Two mersenne prime 
$$
m = 2^{p}-1
$$
**Fermats Prime:**
$$
F = 2^{2n}+1
$$
This sometimes gives composite numbers directly proportional to n

## Primality Testing 

**[[Deterministic]]**: It gives very accurate results. If a deterministic method gives you certainty that a number is prime then it can be trusted.
**[[Probabilistic]]:** It takes less time but there is a probability that means there is a chance of it being not prime.

![[Deterministic]]
![[Probabilistic]]


if a test integer is actually composite then the integer returns the probability of $1-\alpha$ and returns it as prime as $1+\alpha$

### Factorization
**Fundamental Theorem:** If $n$ is any positive integer then it can be expressed as
$$
n = p_{1}^{e_{1}}\times p_{2}^{e_{2}}\dots \times p_{k}^{e_{k}}
$$
$p_{n}$ are primes and $e_k$ are positive integers.
There are multiple ways to do factorization

#### Trial Division Method
Simplest. 
Prime $p$ exists such that. 
$$
p\leq \sqrt{ N }
$$
Its inefficient and long
#### Fermats Method
Divides $n$ into $a\times b$ where $a,b$ may or may not be prime
```js
Fermats_Factorization(n){
	X = root(n);
	while(x<n){
		a=x^2 - n;
		if(a is a perfect square){
			n=x^2 - a^2;
		}
		x=x+1;
		b =n/a
		
	}
	return a,b
}
```

#### Pollards $P-1$ method
$$P = \text{gcd}(2^{B!}-1,n)$$
#### Pollard Rho's Factorization
Assume that there are two integers $x_{}1$, $x_{}2$ such that $P|x_{1}-x_{2}$  but $n$ doesnt.
It is proven that $p = gcd(x_1-x_2,n)$

Because $p~|~x_1-x_2=p\times q$ and $q$ is not a factor of $n$.
$$P = \text{gcd}(2^{B!}-1,n) \text{ =  either 1 or a factor of n}$$
## Chinese Remainder Theorem
$$
x \equiv a_{1} (mod~m_{1})
$$
$$x \equiv a_{2} (mod~m_{2})$$
$$\dots$$
$$x \equiv a_{k} (mod~m_{k})$$
By CRT if $m_1,m_2 \dots, m_k$ are coprime then there exists a unique solution for $x$.
$$M = m_{1}\times m_{2}\times\dots \times m_{k}$$
$M_1=\frac{M}{m_{1}}$
$M_2=\frac{M}{m_{2}}$
$\dots$
$M_{k}=\frac{M}{m_{k}}$

$$M_1^{-1},M_2^{-1},M_3^{-1},\dots, M_k^{-1}$$
$$ X = a_{1} \times M_{1}^{-1}\times M_{1}+a_{2} \times M_{2}^{-1}\times M_{2}\dots+a_{k}\times M_{k}^{-1}\times M_{k}$$
## Quadratic Congruence
$x^2 \equiv a(mod~n)$ We look for an integer $x$ such that it leaves remainder a when $x^2$ is divided by $n$

## When quadratic congruence modulo is a prime
#### Quadratic Residue & non residue
If the equation has two solutions then $a$ is called quadratic residue else $a$ is non quadratic residue eqn has no solution.
If there are $p-1$ Elements in the algebraic structures eexactly $(p-1)/2$ elements are quadratic residues and $(p-1)/2$ are non quadratic residue.

To check if its a QR or QNR
**Euler's Criterion**
1. if $a^{(p-1)/2} \equiv 1~(mod~p)$ then a is a QR
2. 1. if $a^{(p-1)/2} \equiv -1~(mod~p)$ then a is a QNR

## When quadratic congruence modulo is a composite
$x^2 \equiv a~(mod~n)$
if $n$ is factorizable into $n = p_1 \times p_2\dots p_{n}$ then
$$ x_{1}^2 \equiv a~(mod~p_{1}) $$
$$x_{2}^2 \equiv a~(mod~p_{1}) $$
$$\dots$$
$$x_{k}^2 \equiv a~(mod~p_{k}) $$

$$x_{1} \equiv \pm b_{1} \text{mod} p_{1}$$
$$x_{2} \equiv \pm b_{2} \text{mod} p_{1}$$
$$\dots$$
$$x_{k} \equiv \pm b_{k} \text{mod} p_{1}$$
# References

###### Information
- date: 2025.05.04
- time: 23:10