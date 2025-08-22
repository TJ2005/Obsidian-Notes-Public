---
Title: Signals & Systems Lab 6
Status: 
marker: 
tags: 
Date: 2024.07.31
Time: 09:43
---
# Experiment No.: 1

###### Details
Roll Number : K057
Name : Tejas Kamal Sahoo
Branch : Btech Cyber Security
Year : 2nd
Semester : 2
Date & Time : 31-07-2024 23:25

## AIM
Write a MATLAB code to plot basic signals in both continuous and discrete time domains:
1. Sinusoidal
2. Cosine wave
3. Exponential signal
4. Unit step
5. Unit Ramp
6. Unit impulse

## MATLAB CODE

```matlab
clc;
clear all;
close all;

% Sinusoidal Signal
A = 5; % amplitude
f = 3; % frequency
t = [0:0.001:2];
x = A * sin(2 * pi * f * t);
subplot(4,4,1);
plot(t, x);
xlabel('time');
ylabel('Amplitude');
title('sinusoidal signal of freq 3 Hz');

% Cosine Signal
x1 = A * cos(2 * pi * f * t);
subplot(4,4,2);
plot(t, x1);
xlabel('time');
ylabel('Amplitude');
title('cosine signal of freq 3 Hz');

% Unit Step Signal
t1 = [-1:0.1:10];
n = length(t1);
u = [];
for i = 1:n
    if (t1(i) < 0)
        u(i) = 0;
    else
        u(i) = 1;
    end
end
subplot(4,4,3);
plot(t1, u);
title('Step Signal');

% Unit Ramp Signal
t7 = [-1:0.1:10];
n = length(t7);
u = [];
for i = 1:n
    if (t7(i) < 0)
        u(i) = 0;
    else
        u(i) = t7(i);
    end
end
subplot(4,4,4);
plot(t7, u);
title('Ramp signal');

% Unit Impulse Signal
t5 = [-1:0.1:10];
n = length(t5);
u = [];
for i = 1:n
    if (t5(i) == 0)
        u(i) = 2;
    else
        u(i) = 0;
    end
end
subplot(4,4,5);
plot(t5, u);
title('Unit Impulse');

% Discrete Sinusoidal Signal
subplot(4,4,6);
stem(t, x);
xlabel('time');
ylabel('Amplitude');
title('sinusoidal signal of freq 3 Hz (discrete)');

% Discrete Cosine Signal
subplot(4,4,7);
stem(t, x1);
xlabel('time');
ylabel('Amplitude');
title('cosine signal of freq 3 Hz (discrete)');

% Discrete Unit Step Signal
subplot(4,4,8);
stem(t1, u);
title('Step signal (discrete)');

% Discrete Unit Ramp Signal
subplot(4,4,9);
stem(t7, u);
title('Ramp (discrete)');

% Exponential Signal
t2 = [0:0.001:2];
u = exp(3 * t2);
subplot(4,4,10);
plot(t2, u);
title('Exponential Signal (exp(3*t))');

u = exp(-3 * t2);
subplot(4,4,11);
plot(t2, u);
title('Exponential Signal (exp(-3*t))');

% Discrete Exponential Signal
subplot(4,4,12);
stem(t2, u);
title('Exponential Signal (exp(3*t), discrete)');

u = exp(-3 * t2);
subplot(4,4,13);
stem(t2, u);
title('Exponential Signal (exp(-3*t), discrete)');
```

## Output
The generated plots will show the following signals in both continuous and discrete forms:
1. Sinusoidal
2. Cosine
3. Exponential (both exp(3*t) and exp(-3*t))
4. Unit step
5. Unit ramp
6. Unit impulse

![[Pasted image 20240731232936.png]]
## CONCLUSION
Through this experiment, we were able to plot various signals by writing MATLAB code and understand the differences between continuous and discrete signals.