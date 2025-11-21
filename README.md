# Stability-Analysis-using-Polar-Plot
## Aim:
To analyse the stability of the system having open loop transfer function, G(S)=10/(S(1+0.5S)(1+0.2S)) using polar plot and verify it using MATLAB. 
## Apparatus Required:
Computer with MATLAB software

## Theory:

Stability analysis using a polar plot in MATLAB examines how the system’s frequency response encircles the critical point ((-1,0)) based on the Nyquist stability criterion. If the polar plot does not encircle the ((-1,0)) point for an open-loop stable system, the closed-loop system is considered stable.


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
<img width="690" height="607" alt="image" src="https://github.com/user-attachments/assets/cf3791e2-ba81-4f8a-9106-f71a98fafa8a" />

## Result:
Thus the polar plot for the given transfer function was drawn and verified using MATLAB. <br>
Gain margin =   0.7<br>
Phase Margin = -8.8865<br>
Gain crossover frequency = 3.7565<br>
Phase crossover frequency = 3.1623<br>
The system is unstable


