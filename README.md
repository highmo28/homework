# 전기공학과 2021732066 양준모 5주차 과제  
## 1. State Variables  
문제를 해결하는 과정은 보통 Input, System, Output을 거치게 된다. 여기에 System의 State라는 개념을 정의하면, 시스템이 시간에 따라 어떻게 변하는지를 더 명확하게 표현할 수 있다.  
  
즉, State Variable은 과거 정보(이전 상태)와 현재 Input을 함께 고려하여 시스템의 Output과 새로운 State를 결정하는 데 사용된다.  
이 개념을 도입하면 시스템을 수학적으로 모델링하고 분석하기 훨씬 쉬워진다.  
- State는 여러 Input과 State에 의해 결정된다.  
- Output은 Input과 State의 조합으로 구성된다.  
- State는 서로 독립적인 값으로 설정해야 한다.  
  

## 2. Example 1: spring-mass-damper system  
![spring-mass-damper](https://drive.google.com/uc?id=1eBS-bpgIs0NFTZRPJ4jeGwl1ImEhJLjy)  
  
(1) $M\frac{d^2y(t)}{dt^2}+b\frac{dy(t)}{dt}+ky(t)=r(t)$  
  
(2) $x_1(t)=y(t), x_2(t)=\frac{dy(t)}{dt}$
  
(3) $\frac{dx_1(t)}{dt}=x_2(t)}$  
  
(4) $\frac{dx_2(t)}{dt}=-\frac{b}{M}x_1(t)+\frac{1}{M}r(t)$ 
  
(5) $y(t)=x_1(t)$  
  








## 3. Example 2: R-L-C circuit system  
![RLC 회로](https://drive.google.com/uc?id=1O8A6dEUWiXf7Kmyx3uaxxJDDp5iMdhEV)  
  
(1) $x_1(t)=v_c(t), x_2(t)=i_L(t)$  
  
**By KCL**  
$u(t)=C\frac{dx_1(t)}{dt}+x_2(t) &rarr; \frac{dx_1(t)}{dt}=\frac{1}{C}[-x_2(t)+u(t)]$  
  
**By KVL**  
$L\frac{x_2(t)}{dt}+Rx_2(t)-x_1(t)=0 &rarr; \frac{x_2(t)}{dt}=\frac{1}{L}[x_1(t)-Rx_2(t)]$  
  
(2) $\frac{dx_1(t)}{dt}=\frac{1}{C}[-x_2(t)+u(t)]$,  
  
(3) $\frac{dx_2(t)}{dt}=\frac{1}{L}[x_1(t)-Rx_2(t)]$,  
(4) $y(t)=Rx_2(t)$  
  
RLC 회로는 2차 미분방정식으로 표현되므로, 서로 독립적인 두 개의 state를 설정한다. 이때 state는 식 (1)과 다르게 잡을 수도 있지만 반드시 독립적이어야 한다.  
state를 정의한 후 KCL을 적용해 식 하나를 세운다. 이 식은 다시 $x_1(t)$의 1차 미분방정식으로 정리한다. 이렇게 하면 다음과 같은 일반 형태로 나타낼 수 있다.  
$x_1'(t)=ax_1(t)+bu(t)$  
실제로 KCL로부터 얻어지는 식은 **By KCL**의 우측에서 확인할 수 있다.  
다음으로 KVL을 적용하여 또 다른 식을 세우고, 이를 $x_2(t)$의 1차 미분방정식으로 정리한다. 이 역시 동일한 이유로 상태방정식 형태로 표현하기 위함이다. 그 식은 **By KVL**의 우측에서 확인할 수 있다.  
결과적으로, 두 개의 1차 미분방정식으로 이루어진 연립방정식으로 정리할 수 있게되고 식 (4)에서 출력에 대한 식을 확인할 수 있다.
















