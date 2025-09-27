# 전기공학과 2021732066 양준모 5주차 과제  
## 1. State Variables  
문제를 해결하는 과정은 보통 Input, System, Output을 거치게 된다. 여기에 System의 State라는 개념을 정의하면, 시스템이 시간에 따라 어떻게 변하는지를 더 명확하게 표현할 수 있다.  
  
즉, State Variable은 과거 정보(이전 상태)와 현재 Input을 함께 고려하여 시스템의 Output과 새로운 State를 결정하는 데 사용된다.  
이 개념을 도입하면 시스템을 수학적으로 모델링하고 분석하기 훨씬 쉬워진다.  
- State는 여러 Input과 State에 의해 결정된다.  
- Output은 Input과 State의 조합으로 구성된다.  
- State는 서로 독립적인 값으로 설정해야 한다.  
  
## 2. Example 2: R-L-C circuit system  
![RLC 회로](https://drive.google.com/file/d/1O8A6dEUWiXf7Kmyx3uaxxJDDp5iMdhEV/view?usp=sharing)