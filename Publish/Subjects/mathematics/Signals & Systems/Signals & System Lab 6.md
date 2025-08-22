---
Title: Signals & System Lab 5
Status: 
marker:
  - "[[Fourier Transform]]"
  - "[[Signals]]"
tags:
  - BTech
Date: 2024.08.30
Time: 12:19
---
## Aim
To find the fourier series coefficients using MATLAB and plotting them as well.

## Code
```js
% Defining the periodic signals
T = 2*pi; % Period of the signal
t = linspace(-T, T, 1000);

% Number of harmonics to compute
N = 10; 

% Initialize coefficient arrays
a_0 = 0; % DC Component

% Initialize coefficient arrays for each signal
a_n_square = zeros(1, N);
b_n_square = zeros(1, N);
a_n_sawtooth = zeros(1, N);
b_n_sawtooth = zeros(1, N);
a_n_sine = zeros(1, N);
b_n_sine = zeros(1, N);
a_n_cosine = zeros(1, N);
b_n_cosine = zeros(1, N);

% Define and analyze square wave
signal = square(t);
for n = 1:N
    a_n_square(n) = (2/T) * trapz(t, signal .* cos(n * (2*pi/T) * t));
    b_n_square(n) = (2/T) * trapz(t, signal .* sin(n * (2*pi/T) * t));
end

% Define and analyze sawtooth wave
signal = sawtooth(t, 0.5);
for n = 1:N
    a_n_sawtooth(n) = (2/T) * trapz(t, signal .* cos(n * (2*pi/T) * t));
    b_n_sawtooth(n) = (2/T) * trapz(t, signal .* sin(n * (2*pi/T) * t));
end

% Define and analyze sine wave
signal = sin(t);
for n = 1:N
    a_n_sine(n) = (2/T) * trapz(t, signal .* cos(n * (2*pi/T) * t));
    b_n_sine(n) = (2/T) * trapz(t, signal .* sin(n * (2*pi/T) * t));
end

% Define and analyze cosine wave
signal = cos(t);
for n = 1:N
    a_n_cosine(n) = (2/T) * trapz(t, signal .* cos(n * (2*pi/T) * t));
    b_n_cosine(n) = (2/T) * trapz(t, signal .* sin(n * (2*pi/T) * t));
end

% Display results for each signal
disp('Fourier Series Coefficients for Square Wave:')
disp(['a_0: ', num2str(a_0)])
for n = 1:N
    disp([num2str(n), '  ', num2str(a_n_square(n)), '    ', num2str(b_n_square(n))]);
end

disp('Fourier Series Coefficients for Sawtooth Wave:')
disp(['a_0: ', num2str(a_0)])
for n = 1:N
    disp([num2str(n), '  ', num2str(a_n_sawtooth(n)), '    ', num2str(b_n_sawtooth(n))]);
end

disp('Fourier Series Coefficients for Sine Wave:')
disp(['a_0: ', num2str(a_0)])
for n = 1:N
    disp([num2str(n), '  ', num2str(a_n_sine(n)), '    ', num2str(b_n_sine(n))]);
end

disp('Fourier Series Coefficients for Cosine Wave:')
disp(['a_0: ', num2str(a_0)])
for n = 1:N
    disp([num2str(n), '  ', num2str(a_n_cosine(n)), '    ', num2str(b_n_cosine(n))]);
end

% Plot the original signals
figure;
subplot(2,2,1);
plot(t, square(t));
title('Square Wave');
xlabel('Time (t)');
ylabel('Signal');
grid on;

subplot(2,2,2);
plot(t, sawtooth(t, 0.5));
title('Sawtooth Wave');
xlabel('Time (t)');
ylabel('Signal');
grid on;

subplot(2,2,3);
plot(t, sin(t));
title('Sine Wave');
xlabel('Time (t)');
ylabel('Signal');
grid on;

subplot(2,2,4);
plot(t, cos(t));
title('Cosine Wave');
xlabel('Time (t)');
ylabel('Signal');
grid on;

% Plot Fourier coefficients
figure;
subplot(2,2,1);
stem(1:N, a_n_square, 'r', 'DisplayName', 'a_n (cosine)');
hold on;
stem(1:N, b_n_square, 'b', 'DisplayName', 'b_n (sine)');
title('Fourier Coefficients for Square Wave');
xlabel('Harmonic Number (n)');
ylabel('Coefficient Value');
grid on;


subplot(2,2,2);
stem(1:N, a_n_sawtooth, 'r', 'DisplayName', 'a_n (cosine)');
hold on;
stem(1:N, b_n_sawtooth, 'b', 'DisplayName', 'b_n (sine)');
title('Fourier Coefficients for Sawtooth Wave');
xlabel('Harmonic Number (n)');
ylabel('Coefficient Value');
grid on;


subplot(2,2,3);
stem(1:N, a_n_sine, 'r', 'DisplayName', 'a_n (cosine)');
hold on;
stem(1:N, b_n_sine, 'b', 'DisplayName', 'b_n (sine)');
title('Fourier Coefficients for Sine Wave');
xlabel('Harmonic Number (n)');
ylabel('Coefficient Value');
grid on;


subplot(2,2,4);
stem(1:N, a_n_cosine, 'r', 'DisplayName', 'a_n (cosine)');
hold on;
stem(1:N, b_n_cosine, 'b', 'DisplayName', 'b_n (sine)');
title('Fourier Coefficients for Cosine Wave');
xlabel('Harmonic Number (n)');
ylabel('Coefficient Value');
grid on;


```

## Output
![[Screenshot 2024-08-30 133934.png]]

![[Screenshot 2024-08-30 134003.png]]

## Output Text
```bash
Fourier Series Coefficients for Square Wave:
a_0: 0
1  0.004004    2.5465
2  0.004004    -1.2592e-05
3  0.004004    0.84882
4  0.004004    -2.5183e-05
5  0.004004    0.50929
6  0.004004    -3.7776e-05
7  0.004004    0.36377
8  0.004004    -5.0369e-05
9  0.004004    0.28292
10  0.004004    -6.2963e-05
Fourier Series Coefficients for Sawtooth Wave:
a_0: 0
1  -1.6211    -1.2338e-18
2  -4.0081e-06    8.369e-18
3  -0.18013    1.0457e-17
4  -4.0082e-06    -8.8349e-18
5  -0.064847    -1.7256e-18
6  -4.0084e-06    -2.0017e-18
7  -0.033086    -5.3147e-18
8  -4.0086e-06    5.5908e-18
9  -0.020015    4.9696e-18
10  -4.009e-06    3.7272e-18
Fourier Series Coefficients for Sine Wave:
a_0: 0
1  1.0345e-17    2
2  1.182e-18    -9.1174e-18
3  -6.005e-18    -4.3154e-17
4  -4.892e-18    1.0095e-18
5  6.8419e-18    6.4407e-18
6  1.4667e-19    -5.1978e-17
7  -9.7494e-18    8.2068e-17
8  -4.521e-18    -4.0378e-18
9  3.3476e-18    3.3063e-16
10  -1.7946e-18    -4.3398e-18
Fourier Series Coefficients for Cosine Wave:
a_0: 0
1  2    1.0345e-17
2  -1.6345e-16    -2.8058e-17
3  -1.9382e-16    9.2145e-18
4  -1.5848e-16    -1.553e-17
5  -1.4136e-16    8.6278e-19
6  -1.524e-16    -6.4191e-18
7  -3.048e-16    -1.056e-17
8  -1.4301e-16    -2.0707e-19
9  -2.5621e-16    -2.1397e-18
10  -1.3473e-16    -1.8636e-18
>> k057
Fourier Series Coefficients for Square Wave:
a_0: 0
1  0.004004    2.5465
2  0.004004    -1.2592e-05
3  0.004004    0.84882
4  0.004004    -2.5183e-05
5  0.004004    0.50929
6  0.004004    -3.7776e-05
7  0.004004    0.36377
8  0.004004    -5.0369e-05
9  0.004004    0.28292
10  0.004004    -6.2963e-05
Fourier Series Coefficients for Sawtooth Wave:
a_0: 0
1  -1.6211    -1.2338e-18
2  -4.0081e-06    8.369e-18
3  -0.18013    1.0457e-17
4  -4.0082e-06    -8.8349e-18
5  -0.064847    -1.7256e-18
6  -4.0084e-06    -2.0017e-18
7  -0.033086    -5.3147e-18
8  -4.0086e-06    5.5908e-18
9  -0.020015    4.9696e-18
10  -4.009e-06    3.7272e-18
Fourier Series Coefficients for Sine Wave:
a_0: 0
1  1.0345e-17    2
2  1.182e-18    -9.1174e-18
3  -6.005e-18    -4.3154e-17
4  -4.892e-18    1.0095e-18
5  6.8419e-18    6.4407e-18
6  1.4667e-19    -5.1978e-17
7  -9.7494e-18    8.2068e-17
8  -4.521e-18    -4.0378e-18
9  3.3476e-18    3.3063e-16
10  -1.7946e-18    -4.3398e-18
Fourier Series Coefficients for Cosine Wave:
a_0: 0
1  2    1.0345e-17
2  -1.6345e-16    -2.8058e-17
3  -1.9382e-16    9.2145e-18
4  -1.5848e-16    -1.553e-17
5  -1.4136e-16    8.6278e-19
6  -1.524e-16    -6.4191e-18
7  -3.048e-16    -1.056e-17
8  -1.4301e-16    -2.0707e-19
9  -2.5621e-16    -2.1397e-18
10  -1.3473e-16    -1.8636e-18
>> 
```

# References


###### Information
- date: 2024.08.30
- time: 12:19