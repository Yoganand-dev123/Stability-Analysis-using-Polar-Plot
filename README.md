# Stability-Analysis-using-Polar-Plot
## Aim:
To analyse the stability of the system having open loop transfer function, G(S)=10/(S(1+0.5S)(1+0.2S)) using polar plot and verify it using MATLAB. 
## Apparatus Required:
Computer with MATLAB software

## Theory:

Stability analysis using a polar plot in MATLAB examines how the system’s frequency response encircles the critical point ((-1,0)) based on the Nyquist stability criterion. If the polar plot does not encircle the ((-1,0)) point for an open-loop stable system, the closed-loop system is considered stable.
![WhatsApp Image 2025-11-18 at 15 02 22_dcd5c7c9](https://github.com/user-attachments/assets/6c9f7384-85ab-41e5-b984-cfc1b4d15c34)

![WhatsApp Image 2025-11-18 at 15 02 09_f1805cf8](https://github.com/user-attachments/assets/bf3868a8-c375-4fa4-8784-c10cdfc2e2ea)


<img width="565" height="846" alt="image" src="https://github.com/user-attachments/assets/f3e3d3de-eacd-4139-8ab8-3cdddd156cba" />


## Procedure:
	Open MATLAB software
	Open a new script file.
	Type the program.
	Save and Execute the program.
	Determine the gain crossover frequency, phase cross over frequency, gain margin and phase margin.
	Also determine the stability.

## Program: 
```
num=[10]
den=[0.1 0.7 1 0]
sys=tf(num,den)
[mag,phase,W]=bode(sys)
mag=squeeze(mag)
phase=squeeze(phase)
phase1=deg2rad(phase)
polarplot(phase1,mag,'linewidth',1.5)
grid on
[Gm Pm Wpc Wgc]=margin(sys)
if(Wpc>Wgc)
    disp('stable')
elseif(Wpc == Wgc)
    disp('marginally stable')
else
    disp('unstable')
end
```

## Output:
<img width="702" height="629" alt="image" src="https://github.com/user-attachments/assets/84c7aa5d-d91d-4eb1-b4ae-7f410c8447f6" />



## Result:
Thus the polar plot for the given transfer function was drawn and verified using MATLAB. <br>
Gain margin = 0.7<br>
Phase Margin = -8.88 <br>
Gain crossover frequency = 3.75 <br>
Phase crossover frequency = 3.16 <br>
The system is unstable
