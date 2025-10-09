## P3.1
<img width="292" height="74" alt="image" src="https://github.com/user-attachments/assets/7f140dd6-fa05-4f62-a63b-c28de60283c2" />  
<img width="290" height="140" alt="image" src="https://github.com/user-attachments/assets/a479e0e8-1565-4eb3-8365-b3e8b84f895e" />


### (a) 상태변수 설정  
$x_1(t)=y(t)$  
$x_2(t)=\frac{dy(t)}{dt}=y'(t)$  
$F(t)=u(t)$

### (b) 상태변수로 표현한 1차 미분방정식  
$M\frac{d^{2}y(t)}{dt^2}+b\frac{dy(t)}{dt}+ky(t)=F(t)$  
$Mx'_2(t)+bx_2(t)+kx_1(t)=F(t)$  
→ $Mx'_2(t)=-bx_2(t)-kx_1(t)+F(t)$  
$x'_2(t)=-\frac{b}{M}x_2(t)-\frac{k}{M}x_1(t)+\frac{F(t)}{M}$  
$x'_1(t)=x_2(t)$  

### (c) 상태미분방정식
$$x'=Ax + BF(t)$$  
$$y=Cx+DF(t)$$  

$$
A = \begin{bmatrix}
0 & 1 \\
-\frac{k}{M} & -\frac{b}{M} \\
\end{bmatrix}
$$  
$$
B = \begin{bmatrix}
0 \\
\frac{1}{M} \\
\end{bmatrix}
$$  
$$
C = \begin{bmatrix}
1 & 0
\end{bmatrix}
$$  
$$
D = 0
$$  

--------
## P3.3
<img width="294" height="107" alt="image" src="https://github.com/user-attachments/assets/3359388e-c4c6-48ff-a86b-31e54349930d" />  
<img width="1717" height="654" alt="image" src="https://github.com/user-attachments/assets/dfcbee4b-52eb-4244-8a23-869d2fbdcf9f" />  


### 상태미분방정식 구하기
$$x_1(t)=i_L(t), x_2(t)=V_C(t), V_R=V_2-V_C, u(t)=\begin{bmatrix} V_1(t) \\ V_2(t) \end{bmatrix}, y(t)=V_R(t)$$  

**KVL**  
$-V_1(t)+L\frac{di_L(t)}{dt}-V_c(t)+V_2(t)=0$  
$-V_1(t)+Lx'_1(t)-x_2(t)+V_2(t)=0$  
$x'_1(t)=\frac{1}{L}x_2(t)+\frac{1}{L}V_1(t)-\frac{1}{L}V_2(t)$  

**KCL**  
$C\frac{dV_c(t)}{dt}=i_R-i_L$ → $Cx'_2(t)=\frac{V}{R}-x_1(t)=-x_1(t)-\frac{x_2}{R}+\frac{V_2}{R}$  
$x'_2(t)=-\frac{1}{C}x_1(t)-\frac{1}{RC}x_2(t)+\frac{1}{RC}v_2(t)$  

- $x'_1(t)=\frac{1}{L}x_2(t)+\frac{1}{L}V_1(t)-\frac{1}{L}V_2(t)$
- $x'_2(t)=-\frac{1}{C}x_1(t)-\frac{1}{RC}x_2(t)+\frac{1}{RC}V_2(t)$

$$y(t)=V_R(t)=V=V_2-V_C=V_2(t)-x_2(t)$$  
$$ X'(t)=\begin{bmatrix}
0 & \frac{1}{L} \\
-\frac{1}{L} & -\frac{1}{RC} \\
\end{bmatrix}X(t)+\begin{bmatrix}
\frac{1}{L} & -\frac{1}{L} \\
0 & \frac{1}{RC} \\
\end{bmatrix}u(t)
$$  
$$y(t)=\begin{bmatrix}
0 & -1 \\
\end{bmatrix}X(t)+\begin{bmatrix}
0 & 1 \\
\end{bmatrix}u(t)
$$  




