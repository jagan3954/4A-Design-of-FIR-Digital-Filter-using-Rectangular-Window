# FIR-FILTER-DESIGN
# EXP 4 A: Design-of-FIR-Digital-Filter-using-Rectangular-Window

# AIM 1:  To perform Design-of-LOWPASS FIR-Digital-Filter-using-Rectangular-Window using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 

``` clc;
clear;
close;

N = 21;               
wc = %pi / 2;         
alpha = (N - 1) / 2;  

hd = zeros(1, N);
for n = 0 : N-1
    if n == alpha then
        hd(n+1) = wc / %pi;
    else
        hd(n+1) = sin(wc * (n - alpha)) / (%pi * (n - alpha));
    end
end

w = ones(1, N);      

h = hd .* w;         

[H, w_freq] = frmag(h, 256); 

figure;
subplot(2, 1, 1);
plot2d3(0:N-1, h);          
plot(0:N-1, h, 'ro');       
xtitle('Impulse Response', 'n', 'h(n)');
xgrid(1);

subplot(2, 1, 2);
H_dB = 20 * log10(H);       
plot(w_freq, H_dB);
xtitle('Magnitude Response', 'Normalized Frequency', 'Magnitude (dB)');
xgrid(1);
```

# OUTPUT: 

<img width="1917" height="887" alt="image" src="https://github.com/user-attachments/assets/aa7934ce-f527-4750-a215-9237de14512d" />

# RESULT: 

Thus design of low pass FIR digital filter using-Rectangular-Window waveforms were plotted and output was verified.

# AIM 2: To perform DESIGN OF HIGH PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc;
clear;
close;

N = 21;               
wc = %pi / 2;         
alpha = (N - 1) / 2;  

hd = zeros(1, N);
for n = 0 : N-1
    if n == alpha then
        hd(n+1) = 1 - (wc / %pi);
    else
        hd(n+1) = -sin(wc * (n - alpha)) / (%pi * (n - alpha));
    end
end

w = ones(1, N);      

h = hd .* w;         

[H, w_freq] = frmag(h, 256); 

figure;
subplot(2, 1, 1);
plot2d3(0:N-1, h);          
plot(0:N-1, h, 'ro');       
xtitle('Impulse Response', 'n', 'h(n)');
xgrid(1);

subplot(2, 1, 2);
H_dB = 20 * log10(H);       
plot(w_freq, H_dB);
xtitle('Magnitude Response', 'Normalized Frequency', 'Magnitude (dB)');
xgrid(1);
```

# OUTPUT: 

<img width="1917" height="892" alt="image" src="https://github.com/user-attachments/assets/7a3f85a2-827a-4f0c-ae14-018abfd8b76d" />

# RESULT: 
Thus design of HIGH pass FIR digital filter using-Rectangular-Window waveforms were plotted and output was verified.

# AIM 3: To perform DESIGN OF BAND PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc;
clear;
close;

N = 21;               
wc1 = %pi / 4;        
wc2 = 3 * %pi / 4;    
alpha = (N - 1) / 2;  

hd = zeros(1, N);
for n = 0 : N-1
    if n == alpha then
        hd(n+1) = (wc2 - wc1) / %pi;
    else
        hd(n+1) = (sin(wc2 * (n - alpha)) - sin(wc1 * (n - alpha))) / (%pi * (n - alpha));
    end
end

w = ones(1, N);      

h = hd .* w;         

[H, w_freq] = frmag(h, 256); 

figure;
subplot(2, 1, 1);
plot2d3(0:N-1, h);          
plot(0:N-1, h, 'ro');       
xtitle('Impulse Response', 'n', 'h(n)');
xgrid(1);

subplot(2, 1, 2);
H_dB = 20 * log10(H);       
plot(w_freq, H_dB);
xtitle('Magnitude Response', 'Normalized Frequency', 'Magnitude (dB)');
xgrid(1);
```

# OUTPUT: 

<img width="1917" height="893" alt="image" src="https://github.com/user-attachments/assets/59d6ab43-24ec-41f2-842e-6fc99b869530" />

# RESULT: 
Thus design of BAND pass FIR digital filter using-Rectangular-Window waveforms were plotted and output was verified.

# AIM 4: To perform DESIGN OF BAND STOP FIR DIGITAL FILTER using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc;
clear;
close;

N = 21;               
wc1 = %pi / 4;        
wc2 = 3 * %pi / 4;    
alpha = (N - 1) / 2;  

hd = zeros(1, N);
for n = 0 : N-1
    if n == alpha then
        hd(n+1) = 1 - ((wc2 - wc1) / %pi);
    else
        hd(n+1) = (sin(wc1 * (n - alpha)) - sin(wc2 * (n - alpha))) / (%pi * (n - alpha));
    end
end

w = ones(1, N);      

h = hd .* w;         

[H, w_freq] = frmag(h, 256); 

figure;
subplot(2, 1, 1);
plot2d3(0:N-1, h);          
plot(0:N-1, h, 'ro');       
xtitle('Impulse Response', 'n', 'h(n)');
xgrid(1);

subplot(2, 1, 2);
H_dB = 20 * log10(H);       
plot(w_freq, H_dB);
xtitle('Magnitude Response', 'Normalized Frequency', 'Magnitude (dB)');
xgrid(1);
```

# OUTPUT: 

<img width="1917" height="892" alt="image" src="https://github.com/user-attachments/assets/df91a7e9-417e-46be-bc4c-1811450a318a" />

# RESULT: 
Thus design of BAND STOP FIR digital filter using-Rectangular-Window waveforms were plotted and output was verified.
