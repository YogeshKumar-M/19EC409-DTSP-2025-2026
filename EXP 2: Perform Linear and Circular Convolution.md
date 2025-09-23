# EXP 1 : Linear and Circular Convolution

# AIM: 

# To perform Linear and Circular Convolution for two given sequence using SCILAB. 

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM (Linear Convolution): 

// Linear Convolution
clc;
clear;

// Input sequences
x = [1 1 1 1];
h = [1 2 3 4];

m = length(x);
n = length(h);
a = 0:1:m-1;
b = 0:1:n-1;

// Plot input signals
subplot(3,1,1);
plot2d(a, x);
xlabel('Time');
ylabel('Amplitude');
title('Graphical Representation of Input Signal X');

subplot(3,1,2);
plot2d(b, h);
xlabel('Time');
ylabel('Amplitude');
title('Graphical Representation of Impulse Signal h');

// Linear convolution using direct formula
y = zeros(1, m+n-1);

for i = 1:m+n-1
    conv_sum = 0;
    for j = 1:i
        if ((i-j+1 <= n) & (j <= m)) then
            conv_sum = conv_sum + x(j) * h(i-j+1);
        end
    end
    y(i) = conv_sum;
end

disp(y, 'Convolution Sum using Direct Formula Method = ');

// Plot output signal
subplot(3,1,3);
plot2d(0:1:length(y)-1, y);
xlabel('Time');
ylabel('Amplitude');
title('Graphical Representation of Output Signal y');


# PROGRAM (Circular Convolution): 

// Circular Convolution
clc;
clear;

// Input sequences
x = [1 1 1 1];
h = [1 2 3];

N1 = length(x);
N2 = length(h);
N = max(N1, N2);

// Plot input signals
n1 = 0:N1-1;
subplot(3,1,1);
plot2d(n1, x);
xlabel('Time');
ylabel('Amplitude');
title('Input Sequence');

n2 = 0:N2-1;
subplot(3,1,2);
plot2d(n2, h);
xlabel('Time');
ylabel('Amplitude');
title('Impulse Sequence');

// Zero-padding to equal length
if N1 > N2 then
    h = [h, zeros(1, N1-N2)];
elseif N2 > N1 then
    x = [x, zeros(1, N2-N1)];
end

disp(x, 'Padded x = ');
disp(h, 'Padded h = ');

// Circular convolution
y = zeros(1, N);
for n = 1:N
    sum = 0;
    for i = 1:N
        j = n - i + 1;
        if j <= 0 then
            j = N + j;
        end
        sum = sum + x(i) * h(j);
    end
    y(n) = sum;
end

disp(y, 'Circular Convolution Result = ');

// Plot output
n = 0:N-1;
subplot(3,1,3);
plot2d(n, y);
xlabel('Time');
ylabel('Amplitude');
title('Circular Convolution');
****

# OUTPUT (Linear Convolution): 

<img width="764" height="716" alt="Screenshot 2025-09-23 132038" src="https://github.com/user-attachments/assets/9aa3bee0-f96e-4216-ae9d-be3185529f29" />

# OUTPUT (Circular Convolution): 

<img width="754" height="719" alt="Screenshot 2025-09-23 132310" src="https://github.com/user-attachments/assets/bc606e18-90f3-4832-901c-ec58e2cec8bb" />


# RESULT: 
Thus the linear convolution and cirular convolution for two given sequence using scilab is done.
