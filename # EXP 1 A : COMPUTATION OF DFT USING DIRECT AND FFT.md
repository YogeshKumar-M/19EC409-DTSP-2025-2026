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

# OUTPUT: 

<img width="736" height="616" alt="output_dft" src="https://github.com/user-attachments/assets/9b270352-6c71-4716-b713-a2e727c0fb6e" />


# RESULT: 
Thus the DFT and FFT of given sequence is obtained.
