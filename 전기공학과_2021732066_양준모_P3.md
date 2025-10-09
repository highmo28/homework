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
$$x_1(t)=i_L(t), \quad x_2(t)=V_C(t), \quad V_R=V_2-V_C, \quad u(t)=\begin{bmatrix} V_1(t) \\ V_2(t) \end{bmatrix}, \quad y(t)=V_R(t)$$  

**KVL**  
$-V_1(t)+L\frac{di_L(t)}{dt}-V_c(t)+V_2(t)=0$  
$-V_1(t)+Lx'_1(t)-x_2(t)+V_2(t)=0$  
$x'_1(t)=\frac{1}{L}x_2(t)+\frac{1}{L}V_1(t)-\frac{1}{L}V_2(t)$  

**KCL**  
$C\frac{dV_c(t)}{dt}=i_R-i_L$ → $Cx'_2(t)=\frac{V}{R}-x_1(t)=-x_1(t)+\frac{V_2-x_2}{R}$  
$x'_2(t)=-\frac{1}{C}x_1(t)+\frac{V_2(t)-x_2(t)}{RC}$  

- $x'_1(t)=\frac{1}{L}x_2(t)+\frac{1}{L}V_1(t)-\frac{1}{L}V_2(t)$
- $x'_2(t)=-\frac{1}{C}x_1(t)-\frac{1}{RC}x_2(t)+\frac{1}{RC}V_2(t)$

$$y(t)=V_R(t)=V=V_2-V_C=V_2(t)-x_2(t)$$  
$$ x'(t)=\begin{bmatrix}
0 & \frac{1}{L} \\
-\frac{1}{C} & -\frac{1}{RC} \\
\end{bmatrix}x(t)+\begin{bmatrix}
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

-------
## P3.5
<img width="290" height="51" alt="image" src="https://github.com/user-attachments/assets/2c18dc6f-826f-47a9-83e4-0dd9949ade93" />  
<img width="475" height="117" alt="image" src="https://github.com/user-attachments/assets/13ee0dbc-07a2-4eef-909f-84a2b62a979a" />  

### (a) 폐루프 전달함수 T(s)=Y(s)/R(s)
$V_1(s)=(R(s)-Y(s))\times \frac{s+2}{s+8}$  
$V(s)=\frac{1}{s-3}\times V_1(s)$  
$Y(s)=\frac{1}{s}\times V(s)=\frac{1}{s}\times \frac{1}{s-3}\times \frac{s+2}{s+8}\times (R-Y)=\frac{s+2}{s(s-3)(s+8)}\times (R-Y)$  

$[s(s-3)(s+8)+(s+2)]\times Y(s)=(s+2)\times R(s)$  
$T(s)=\frac{Y(s)}{R(s)}=\frac{s+2}{s^3+5s^2-23s+2}$


### (b) 상태변수 모델
$Y(s)=(s+2)\times Z(s)$  
$R(s)=(s^3+5s^2-23s+2)\times Z(s)$

$y(t)=z'(t)+2z(t)$  
$r(t)=z'''(t)+5z''(t)-23z'(t)+2z(t)$

**state 정의**  
$x_1 = z$  
$x_2 = z'$  
$x_3 = z''$  
  
$x'_1=x_2$  
$x'_2=x_3$  
$x'_3=-2x_1+23x_2-5x_3+r$  
  
$y=2x_1+x_2+0x_3$  

$$A=\begin{bmatrix}
0 & 1 & 0 \\
0 & 0 & 1 \\
-2 & 23 & -5 \\
\end{bmatrix}$$  

$$B=\begin{bmatrix}
0 \\
0 \\
1 \\
\end{bmatrix}$$  

$$C=\begin{bmatrix}
2 & 1 & 0 \\
\end{bmatrix}$$  

$$D=0$$  

**상태공간 표현식**  
$x'=Ax+Br$  
$y=Cx+Dr$  

------
## P3.12
<img width="290" height="103" alt="image" src="https://github.com/user-attachments/assets/a6ed72e3-bcce-472f-bf3a-3410fed91346" />  

### (a) 상태공간모델을 구하라
주어진 전달함수  
$T(s)=\frac{Y(s)}{R(s)}=\frac{8(s+5)}{s^3+12s^2+44s+48}$  

보조변수 $Z(s)$를 두면,  
$Y(s)=(8s+40)Z(s),\quad R(s)=(s^3+12s^2+44s+48)Z(s)$  


**역라플라스 변환**  
$y(t) = 8z'(t)+40z(t)$  
  
$r(t) = z'''(t) + 12z''(t) + 44z'(t) + 48z(t)$  

**상태변수 정의**  
$x_1=z,\quad x_2=z',\quad x_3 = z''$
이에 따라  

$x'_1=x_2$  
$x'_2=x_3$  
$x'_3=-48x_1-44x_2-12x_3+r$  

$$y=\begin{bmatrix}
40 & 8 & 0 \\
\end{bmatrix}\begin{bmatrix}
x_1 \\
x_2 \\
x_3 \\
\end{bmatrix}
$$  

**상태공간모델**  

$$
A=\begin{bmatrix}
0 & 1 & 0 \\
0 & 0 & 1 \\
-48 & -44 & -12
\end{bmatrix},
\quad
B=\begin{bmatrix}
0 \\
0 \\
1
\end{bmatrix},
\quad
C=\begin{bmatrix}
40 & 8 & 0
\end{bmatrix}
\quad
D = 0
$$  

### (b) 상태천이행렬 $\Phi(t)$를 구하라  
입력이 $u(t)$일 때  

$sX(s)=AX(s)+BU(s)$  

즉,  

$X(s) = (sI-A)^{-1}BU(s)$  

여기서 정의되는  

$\Phi(s) = (sI-A)^{-1}$  

을 상태천이행렬의 라플라스 영역 표현이라 부르며,  
역라플라스를 취하면 시간영역에서 다음과 같은 형태가 된다:

$\Phi(t) = e^{At}$  

**특성방정식**  

$$
sI - A =
\begin{bmatrix}
s & -1 & 0 \\
0 & s & -1 \\
48 & 44 & s+12
\end{bmatrix}
$$

분자  

$$
adj(sI-A) =
\begin{bmatrix}
s^2+12s+44 & s+12 & 1 \\
-48 & s^2+12s & s \\
-48s & -(44s+48) & s^2
\end{bmatrix}
$$  

분모  

$$
\det(sI - A) = s^3 + 12s^2 + 44s + 48 = (s + 2)(s + 4)(s + 6)
$$  

라플라스 영역에서  
$\Phi(s)=(sI-A)^{-1}$  
이며, 각 원소를 부분분수 전개 후 역라플라스 변환하면 다음과 같다:

$$
\Phi(t) = e^{At} =
\begin{bmatrix}
3e^{-2t} - 3e^{-4t} + e^{-6t} & \tfrac{5}{4}e^{-2t} - 2e^{-4t} + \tfrac{3}{4}e^{-6t} & \tfrac{1}{8}e^{-2t} - \tfrac{1}{4}e^{-4t} + \tfrac{1}{8}e^{-6t} \\
-6e^{-2t} + 12e^{-4t} - 6e^{-6t} & -\tfrac{5}{2}e^{-2t} + 8e^{-4t} - \tfrac{9}{2}e^{-6t} & -\tfrac{1}{4}e^{-2t} + e^{-4t} - \tfrac{3}{4}e^{-6t} \\
12e^{-2t} - 48e^{-4t} + 36e^{-6t} & 5e^{-2t} - 32e^{-4t} + 27e^{-6t} & \tfrac{1}{2}e^{-2t} - 4e^{-4t} + \tfrac{9}{2}e^{-6t}
\end{bmatrix}
$$  

----
## P3.17  
<img width="291" height="147" alt="image" src="https://github.com/user-attachments/assets/35c315fc-2c1e-4922-8172-f7634562b504" />  

**전달함수**  
$sX(s)=AX(s)+BU(s) \rightarrow X(s)=(sI-A)^{-1}BU(s),\quad \Phi(s)=(sI-A)^{-1}$  
$Y(s)=CX(s) \rightarrow Y(s)=C\Phi(s)BU(s)$  
$G(s)=\frac{Y(s)}{U(s)}=C(sI-A)^{-1}B+D$  

$$
A =
\begin{bmatrix}
1 & 1 & -1 \\
4 & 3 & 0 \\
-2 & 1 & 10
\end{bmatrix},
\quad
B =
\begin{bmatrix}
0 \\
0 \\
4
\end{bmatrix},
\quad
C =
\begin{bmatrix}
1 & 0 & 0
\end{bmatrix},
\quad
D = 0
$$  

$$
M = sI-A =
\begin{bmatrix}
s - 1 & -1 & 1 \\
-4 & s - 3 & 0 \\
2 & -1 & s - 10
\end{bmatrix}
$$  

**분모**  
$det(M)=s^3-14s^2+37s+20$  

**분자**  
$adj(M)$는 B에 의해 3열만 계산이 되는것을 알 수 있다.  

$$
C_{31} = -s + 3, \quad
C_{32} = -4, \quad
C_{33} = s^2 - 4s - 1
$$  

$$
adj(M) =4\begin{bmatrix}
C_{31} \\
C_{32} \\
C_{33}
\end{bmatrix}
= 4
\begin{bmatrix}
-s + 3 \\
-4 \\
s^2 - 4s - 1
\end{bmatrix}
$$  

이렇게 계산된 이후 C에 의해 1행만 남게되므로 결국 분자는 다음과 같은 식이 된다.  
$-4(s-3)$


**최종 전달함수 G(s)=Y(s)/U(s)**

$G(s) = \frac{-4s + 12}{s^3 - 14s^2 + 37s + 20}$






