# EXP 1 A : COMPUTATION OF DFT USING DIRECT AND FFT

# AIM: 
To compute DFT using direct and FFT

# To Obtain DFT and FFT of a given sequence in SCILAB. 

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
// DISCRETE FOURIER TRANSFORM 
clc;
clear;

// Input sequence
xn = [1 2 3 4 4 3 2 1];
n1 = 0:length(xn)-1;

// Plot input sequence
subplot(3,1,1);
plot2d3(n1, xn);
xlabel('Time n');
ylabel('Amplitude xn');
title('Input Sequence');

// DFT computation
j = sqrt(-1); // imaginary unit
N = length(xn);
Xk = zeros(1, N);

for k = 0:N-1
    for n = 0:N-1
        Xk(k+1) = Xk(k+1) + xn(n+1) * exp(-j*2*%pi*k*n/N);
    end
end

disp(Xk);

// Frequency axis
K1=0:1:length(Xk)-1; 

// Magnitude spectrum
magnitude = abs(Xk);
subplot(3,1,2);
plot2d3(K1, magnitude);
xlabel('Frequency (Hz)');
ylabel('Magnitude');
title('Magnitude Spectrum');

// Phase spectrum
// Phase spectrum
angle = atan(imag(Xk), real(Xk));

subplot(3,1,3);
plot2d3(K1, angle);
xlabel('Frequency (Hz)');
ylabel('Phase');
title('Phase Spectrum');







FFT 
clear; clc; close all;

// Input sequence
xn = [1 2 3 4 4 3 2 1];
n1 = 0:length(xn)-1;

// Plot input sequence
subplot(2,2,1);
plot2d3(n1, xn);
xlabel('Time n');
ylabel('Amplitude');
title('Input Sequence');

// FFT computation
Xk = fft(xn);
K1 = 0:length(Xk)-1;

// Magnitude spectrum
magnitude = abs(Xk);
subplot(2,2,2);
plot2d3(K1, magnitude);
xlabel('Frequency (Hz)');
ylabel('Magnitude');
title('Magnitude Spectrum');

// Phase spectrum
angle = atan(imag(Xk), real(Xk));
subplot(2,2,3);
plot2d3(K1, angle);
xlabel('Frequency (Hz)');
ylabel('Phase (radians)');
title('Phase Spectrum');

// Inverse FFT
y = ifft(Xk);
n2 = 0:length(y)-1;
subplot(2,2,4);
plot2d3(n2, y);
xlabel('Time n');
ylabel('Amplitude');
title('Inverse FFT of X(k)');

# OUTPUT: 
DFT ...

<img width="736" height="616" alt="output_dft" src="https://github.com/user-attachments/assets/9b270352-6c71-4716-b713-a2e727c0fb6e" />

FFT..

<img width="763" height="718" alt="Screenshot 2025-09-23 132930" src="https://github.com/user-attachments/assets/d0f15d71-b6af-436e-9fec-407dfc87836a" />


# RESULT: 
Thus the DFT and FFT of given sequence is obtained.
