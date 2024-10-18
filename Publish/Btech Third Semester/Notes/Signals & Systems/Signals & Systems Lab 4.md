---
Title: Signals & Systems Lab 3
Status: 
marker:
  - "[[Signals & System]]"
  - "[[Lab]]"
  - "[[Matlab]]"
tags:
  - BTech
Date: 2024.08.30
Time: 13:54
---
## Aim
Convolution of various signals with the help of convolution function and without to understand the logic behind the function

![[parallel Computation.excalidraw]]

## Code
### With Convolution Function
```js
clc;
clear all;
close all;
N1=4;
n=(0:N1-1);
x=[1,2,3,4];
h=[1,-1,3,4];
M=length(x);
N=length(h);
L=M+N-1;
C=(0:L-1);
y=conv(x,h);
subplot(3,1,1);
stem(n, x);
xlabel('Time');
ylabel('Amplitude');
title('Input Sequence x[n]');
subplot(3,1,2);
stem(n, h);
xlabel('Time');
ylabel('Amplitude');
title('Impulse Response h[n]');
subplot(3,1,3);
stem(C, y);
xlabel('Time');
ylabel('Amplitude');
title('Convolved Output y[n]');```


### Output
![[Pasted image 20240830135930.png]]

### With Convolution Function
```matlab
clc;
clear all;
close all;
x=[1,2,3,4,5];
h=[1,2];
m=length(x);
n=length(h);
l=m+n-1;
x1=[x,zeros(1,n)];
h1=[h,zeros(1,m)];
for i=1:l
y(i)=0;
for j = 1 : i
y(i)=y(i)+x1(j)*h1(i-j+1);
end
end
subplot(3,1,1)
grid on;
stem(x)
ylabel("Amplitude")xlabel("Time")
title("X i/p")
subplot(3,1,2)
grid on;
stem(h)
ylabel("Amplitude")
xlabel("Time")
title("h")
subplot(3,1,3)
grid on;
stem(y)
ylabel("Amplitude")
xlabel("Time")
title("h")
ASSIGNMENT
clc;
clear all;close all;
x = [2,4,6,8];
h1 = [-1,1,3,5];
h2 = [-2,0,3,5];
h3 = [1,2,3];
h4 = [3,5];
subplot(3,3,1);
stem(x);
title('Original signal x')
subplot(3,3,2);
stem(h1);
title('Original signal h1')
subplot(3,3,3);
stem(h2);
title('Original signal h2')
subplot(3,3,4);
stem(h3);
title('Original signal h3')
subplot(3,3,5);
stem(h4);
title('Original signal h4')
h5 = h1 + h2;
subplot(3,3,6);
stem(h5);
title(' signal h5 (h1 + h2)')
h6 = conv(h5, h3);
subplot(3,3,7);
stem(h6);
title('signal h6 (Convolution of h5 and h3)')
h7 = conv(h6, h4);
subplot(3,3,8);
stem(h7);
title('signal h7 (Convolution of h6 and h4)')
y = conv(x, h7);
subplot(3,3,9);
stem(y);
title('Signal h8 (Convolution of x and h7)')
```
![[Pasted image 20240830150348.png]]

### Output