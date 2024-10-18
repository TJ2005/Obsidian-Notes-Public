---
Title: Signals & Systems Lab 7
Status: 
marker:
  - "[[Matlab]]"
  - "[[Signals & System]]"
  - "[[Laplace Transform]]"
tags: 
Date: 2024.09.27
Time: 13:17
---
# Signals & Systems Lab 7
## Aim
To compute laplace and inverse laplace using matlab with function and without

```js
clc;

clear all;

close all;

syms t s;

% Define the functions

x1 = exp(-2*t) * heaviside(t);

x2 = exp(-2*t) * heaviside(t);

x3 = exp(-2*t) * heaviside(t) + exp(-4*t) * heaviside(t);

x4 = exp(-2*t) * heaviside(t) - exp(-4*t) * heaviside(t);

% Perform Laplace transforms

X1_s = laplace(x1, t, s);

X2_s = laplace(x2, t, s);

X3_s = laplace(x3, t, s);

X4_s = laplace(x4, t, s);

% Perform Inverse Laplace transforms (just for demonstration)

inv_X1 = ilaplace(X1_s, s, t);

inv_X2 = ilaplace(X2_s, s, t);

inv_X3 = ilaplace(X3_s, s, t);

inv_X4 = ilaplace(X4_s, s, t);

% Display the results

disp('Laplace Transform of x1(t):');

disp(X1_s);

disp('Inverse Laplace Transform of x1(s):');

disp(inv_X1);

disp('Laplace Transform of x2(t):');

disp(X2_s);

disp('Inverse Laplace Transform of x2(s):');

disp(inv_X2);

disp('Laplace Transform of x3(t):');

disp(X3_s);

disp('Inverse Laplace Transform of x3(s):');

disp(inv_X3);

disp('Laplace Transform of x4(t):');

disp(X4_s);

disp('Inverse Laplace Transform of x4(s):');

disp(inv_X4);

% Manual

ml1=int(x1 * exp(-s*t), t, 0, inf);

ml2=int(x1 * exp(-s*t), t, 0, inf);

ml3=int(x1 * exp(-s*t), t, 0, inf);

ml4=int(x1 * exp(-s*t), t, 0, inf);

% Displaying Manual

disp(ml1);

disp(ml2);

disp(ml3);

disp(ml4);
```

```matlab
Laplace Transform of x1(t): 1/(s + 2) Inverse Laplace Transform of x1(s): exp(-2*t) Laplace Transform of x2(t): 1/(s + 2) Inverse Laplace Transform of x2(s): exp(-2*t) Laplace Transform of x3(t): 1/(s + 2) + 1/(s + 4) Inverse Laplace Transform of x3(s): exp(-2*t) + exp(-4*t) Laplace Transform of x4(t): 1/(s + 2) - 1/(s + 4) Inverse Laplace Transform of x4(s): exp(-2*t) - exp(-4*t)

piecewise(s < -2, Inf, real(s) ~= -2 & ~in(s, 'real'), 1/(s + 2) - limit(exp(- 2*t - t*s), t, Inf)/(s + 2), angle(s) in Dom::Interval(-pi/2, pi/2) & s ~= 0 | -2 < s, 1/(s + 2), (real(s) == -2 | in(s, 'real')) & ~angle(s) in Dom::Interval(-pi/2, pi/2) & (~in(s, 'real') | s == -2), int(exp(-2*t)*exp(-t*s), t, 0, Inf))

piecewise(s < -2, Inf, real(s) ~= -2 & ~in(s, 'real'), 1/(s + 2) - limit(exp(- 2*t - t*s), t, Inf)/(s + 2), angle(s) in Dom::Interval(-pi/2, pi/2) & s ~= 0 | -2 < s, 1/(s + 2), (real(s) == -2 | in(s, 'real')) & ~angle(s) in Dom::Interval(-pi/2, pi/2) & (~in(s, 'real') | s == -2), int(exp(-2*t)*exp(-t*s), t, 0, Inf))

piecewise(s < -2, Inf, real(s) ~= -2 & ~in(s, 'real'), 1/(s + 2) - limit(exp(- 2*t - t*s), t, Inf)/(s + 2), angle(s) in Dom::Interval(-pi/2, pi/2) & s ~= 0 | -2 < s, 1/(s + 2), (real(s) == -2 | in(s, 'real')) & ~angle(s) in Dom::Interval(-pi/2, pi/2) & (~in(s, 'real') | s == -2), int(exp(-2*t)*exp(-t*s), t, 0, Inf))

piecewise(s < -2, Inf, real(s) ~= -2 & ~in(s, 'real'), 1/(s + 2) - limit(exp(- 2*t - t*s), t, Inf)/(s + 2), angle(s) in Dom::Interval(-pi/2, pi/2) & s ~= 0 | -2 < s, 1/(s + 2), (real(s) == -2 | in(s, 'real')) & ~angle(s) in Dom::Interval(-pi/2, pi/2) & (~in(s, 'real') | s == -2), int(exp(-2*t)*exp(-t*s), t, 0, Inf))
```


# References


###### Information
- date: 2024.09.27
- time: 13:17