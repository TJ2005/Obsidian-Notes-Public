---
Title: "Introduction to Cryptography Lecture 12"
Status: 
marker: 
tags: 
Date: "2025.03.01"
Time: "11:15"
---
# Factorisation Method
## Trial Division method
Factorising any number we start with the smallest prime number and keep dividing the number until it becomes 1. We keep track of the prime numbers that divide the number.
Example 231:
$$
231 = 3 * 77 = 3 * 7 * 11
$$
## Fermat's Factorisation Method
Fermat's factorisation method is based on the formula:
$$
n=x^2-y^2=(x+y)(x-y)
$$
If n is a composite number, then it can be expressed as the difference of two squares. We can find the value of x and y by solving the equation.
Example: 
$$
5959=77^2-4*36^2
$$
Find Factors of 5959
1. Compute $a=\sqrt{n}$
	1.  $a=\sqrt{5959}=77$
	2. $y^2=a^2-n=77^2-5959=6084-5959=125$
	3. $125$ is not a perfect square
	4. $y=\sqrt{125}=5\sqrt{5}$
	5. $x=a+y=77+5\sqrt{5}$
	6. $x-y=77-5\sqrt{5}$
	7. $x+y=77+5\sqrt{5}$
	8. $5959=(77+5\sqrt{5})(77-5\sqrt{5})$


Find factors of 10403
1. Compute $a=\sqrt{n}$
	1.  $a=\sqrt{10403}=102$
	2. $y^2=a^2-n=102^2-10403=10404-10403=1$
	3. $1$ is a perfect square
	4. $y=1$
	5. $x=a+y=102+1=103$
	6. $x-y=103-1=102$
	7. $x+y=103+1=104$
	8. $10403=104*102$

In the above question
- $a$ is the nearest integer to $\sqrt{n}$
- $y$ is the difference between $a$ and $\sqrt{n}$
- - $x$ is the sum of $a$ and $y$


## Pollard's Method
Pollard's rho method is based on the Floyd's cycle finding algorithm. The algorithm is as follows:
$$
p=gcd(2^{B!}-1,n)
$$
Factorising 10403 using Pollard's Rho Method
1. Choose a = 2
2. Compute $gcd(a^{k!}-1,10403)$ for increasing values of $k$
3. At $k=5$, $gcd(2^{5!}-1,10403)=gcd(2^{120}-1,10403)=$

## Pollard Rho Method
Pollard's rho method is based on the Floyd's cycle finding algorithm. The algorithm is as follows:
formula:
$$
gcd(|x_{2}-y_{2},10403)=gcd(|x_{2}-y_{2},10403)$$
Factorising $8051$ using Pollard's Rho Method
1. Choose x=2, y=2
2. Compute $x^2+1$ and $y^2+1$
	1. $x=2^2+1=5 ~ mod(10403)$
	2. $y=2^2+1=5~$
	3. $x=5^2+1=26$
	4. $y=5^2+1=26$
	5. $x=26^2+1=677$
	6. how to know when to stop?
		1. $x=677$
		2. $y=26$
		3. $x-y=651$
		4. $gcd(651,8051)=59$
		5. $8051=59*137$
3. Compute $d = gcd(x-y,n)$
	1. $d=gcd(677-26,8051)=gcd(651,8051)=59$
	2. $8051=59*137$

Factorising $10403$ using Pollard's Rho Method
1. Choose x=2, y=2
2. 




# References


###### Information
- date: 2025.03.01
- time: 11:15