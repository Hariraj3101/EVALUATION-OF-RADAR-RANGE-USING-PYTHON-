# EVALUATION-OF-RADAR-RANGE-USING-PYTHON-

__Aim__:

To calculate the maximum range of a radar system using the Radar Range Equation and verify the results 
through Python programming.

__Theory__:

The Radar Range Equation is a fundamental formula used in radar system design to determine the maximum 
range at which a radar can detect a target. It is given by:

<img width="573" height="442" alt="image" src="https://github.com/user-attachments/assets/ba374d30-d11f-41e5-a4fc-a42dde71d8e7" />

__Procedure__:

1. Set Up the Python Environment: Ensure that Python is installed on your system. You can use 
Anaconda for managing Python packages and environments, or any other Python IDE of your choice. 
2. Import Necessary Libraries: Import the math library in Python. 
3. Define the Radar Range Equation Function: Create a function to calculate the maximum range using 
the Radar Range Equation. 
4. Input Parameters for the Radar System: Define the input parameters such as transmitted power, 
transmitter gain, receiver gain, radar frequency, radar cross section, and minimum detectable power. 
5. Calculate the Maximum Range: Use the function to calculate the maximum range of the radar. 
6. Execute the Program: Run the Python script to calculate and display the maximum range of the radar.


   ___Algorithm__:
  ``` 

clc
clear;
close;

Pt = 1000;
G = 40;
lambda = 0.05;
sigma = 10;
pi4 = (4*%pi)^3;

R = linspace(1e3, 200e3, 500);
Pr_R = (Pt .* G^2 .* lambda^2 .* sigma) ./ (pi4 .* R.^4);
figure(1);
Pr_R_dB = 10 .* log10(Pr_R);
plot(R/1000, Pr_R_dB);
xlabel("Power Received");
ylabel("Range");

Pt_values = linspace(100, 10000, 500);
R_fixed = 50e3;
Pr_Pt = (Pt_values .* G^2 .* lambda^2 .* sigma) ./ (pi4 .* R_fixed.^4);
figure(2);
plot(Pt_values, Pr_Pt);
xlabel("Power Received");
ylabel("Power Transmitted");

G_values = linspace(5, 60, 500);
Pt_fixed = 3000;
Pr_G = (Pt_fixed .* G_values.^2 .* lambda^2 .* sigma) ./ (pi4 .* R_fixed.^4);
figure(3);
plot(G_values, Pr_G);
xlabel("Power Received");
ylabel("Gain");
```



CALCULATION:
<img width="1508" height="969" alt="image" src="https://github.com/user-attachments/assets/101b077a-cf2e-42fd-bcfe-d349e925f178" />


   __Output__:
   
<img width="1838" height="965" alt="image" src="https://github.com/user-attachments/assets/07d67606-d370-469e-865c-192f4dd579ae" />

<img width="1841" height="972" alt="image" src="https://github.com/user-attachments/assets/a45507e6-295b-4e80-9ae0-60ae5a551fb5" />

<img width="1835" height="963" alt="image" src="https://github.com/user-attachments/assets/7ff1c3b5-f658-4c69-a2d9-d8bc5109338d" />






   __Result__:
   
<img width="1600" height="770" alt="image" src="https://github.com/user-attachments/assets/9ce460bc-2179-4db0-8c73-ed6ad3e1baad" />




