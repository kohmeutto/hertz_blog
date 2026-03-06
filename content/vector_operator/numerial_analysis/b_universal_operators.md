+++
title = "(b) Universal operators"
weight = 1
+++

---

### 1. 변분 연산자 $\delta$의 정의와 위계

변분 연산자 $\delta$는 힐베르트 공간의 벡터를 다루는 일반 연산자보다 상위 층위에 존재하는 **슈퍼 연산자(Super-operator)** 이다. 이는 연산자 대수(Operator Algebra) 위에서 정의되는 **미분 사상(Derivation)** 으로 규정된다.

변분 연산자는 다음의 세 가지 공리를 완벽하게 만족한다.

**1) 선형성 (Linearity)**

$$
\delta(c_1 \hat{A} + c_2 \hat{B}) = c_1 \delta \hat{A} + c_2 \delta \hat{B}
$$

**2) 라이프니츠 법칙 (Leibniz Rule)**

$$
\delta(\hat{A} \hat{B}) = (\delta \hat{A}) \hat{B} + \hat{A} (\delta \hat{B})
$$

이는 연산자 곱셈의 비가환 구조를 보존하면서 변화량을 측정하는 핵심 원리이다.

**3) 수반 가환성**
   
$$
(\delta \hat{A})^\dagger = \delta (\hat{A}^\dagger)
$$

---

### 2. 자코비안

**1) 슈퍼 연산자 자코비안, $\mathcal{J}$**

$\mathcal{J}$는 상태의 변화($|\delta u\rangle$)를 연산자의 변화($\delta \hat{L}$)로 사상하는 고차원 생성기이다.

(1) 정의 식: $\delta \hat{L} = \mathcal{J} \hat{L} |\delta u \rangle$  
(2) 사상 구조: $\mathcal{J} : \mathcal{V} \to \mathcal{L}(\mathcal{V})$  
(3) 물리적 의미: 시스템 연산자 $\hat{L}$이 가진 '형틀'이 해의 변동에 의해 얼마나 뒤틀리는지를 규정한다.  

**2) 연산자 자코비안의 성질**

슈퍼연산자 $\mathcal{J}$는 본질적으로 두 개의 벡터를 입력받아 하나의 벡터(유량 변화량)를 내놓는 **쌍선형 사상(Bilinear Mapping)** 이다.

$$
(\mathcal{J} \hat{L}|\delta u \rangle) |u \rangle = (\mathcal{J} \hat{L}|u \rangle) |\delta u \rangle
$$

이 식은 수학적으로 다음과 같은 교환성을 갖는다.

- $|u \rangle$를 변수로 보고 $|\delta u \rangle$를 파라미터로 볼 수도 있다.
- $|\delta u \rangle$를 변수로 보고 $|u \rangle$를 파라미터로 볼 수도 있고


**3) 상태 자코비안: 선형 연산자 $\hat{J}$**

흔히 '자코비안'이라 부르는 $\hat{J}$는, 슈퍼연산자 $\mathcal{J}$의 작용을 포함하여 최종적으로 조립된 선형 사상이다.

(1) 정의 식

$$
\hat{J}_L|\delta u\rangle = \delta (\hat{L} |u\rangle)
$$

(2) 연산자 분해:

$$
\hat{J}_L |\delta u \rangle = \delta (\hat{L} |u\rangle) = \underbrace{\hat{L} |\delta u \rangle}_{\text{1. 기하학적 항}} + \underbrace{(\delta \hat{L}) |u \rangle}_{\text{2. 연산자 변이 항}}
$$

슈퍼연산자 식 $\delta \hat{L} = \mathcal{J} \hat{L} |\delta u \rangle$을 대입하면,

$$
\hat{J}_L |\delta u \rangle
= \hat{L} |\delta u \rangle + (\mathcal{J} \hat{L} |\delta u \rangle) |u \rangle
= \underbrace{\hat{L} |\delta u \rangle}_{\text{Standard } \hat{L}} + \underbrace{(\mathcal{J} \hat{L} |u \rangle) |\delta u \rangle}_{\text{Non-linear pollution}}
$$

**4) 의미**

- 기하학적 항: $|\delta u \rangle$ 자체에 대한 순수변화
- 연산자 변이 항: 현재 흐르고 있는 **기존의 배경 흐름($|u\rangle$)** 에 작용하여 $|\delta u \rangle$ 가 연산자 자체를 흔든다.

---

### 3. 자코비안

**1) 잔차 시스템**

우리가 풀고자 하는 새로운 잔차 시스템을 정의해 본다.

$$
\hat{L}(u)|u\rangle=|f\rangle \implies |R\rangle = \hat{L}|u\rangle-|\tilde{f}\rangle
$$

 **2) 각 연산자의 1차 변분 정의**
 
 상태 벡터가 $|u\rangle$에서 $|u + \delta u\rangle$로 미소하게 변할 때, 상태에 종속된 세 가지 요소($\hat{C}, \hat{G}, |R\rangle$)는 각각 자신의 1차 편미분(프레셰 도함수)을 따라 선형적으로 변화힌다. 고차항(Higher-order terms, $\mathcal{O}(\|\delta u\|^2)$)은 이 단계에서 분리한다.

$$
|R(u+\delta u)\rangle = |R(u)\rangle + |\delta R\rangle + \mathcal{O}(\|\delta u\|^2)
$$

**3) 자코비안과의 연결**

자코비안 $\hat{J}$는 **'1차 선형 연산자'** 로 정의되므로, 2차 이상의 비선형항들은 선형화(Linearization) 가정에 의해 소거된다. 따라서 순수하게 1차 변분항만이 남게 된다.

$$
|R(u+\delta u)\rangle
\approx |R\rangle+|\delta R\rangle 
=|R\rangle+\hat{J}|\delta u\rangle
$$

$$
\hat{J}|\delta u\rangle = |\delta R\rangle 
$$

이제 이 식에 1단계에서 정의했던 편미분 표현을 적용한다.

$$
\hat{J}|\delta u\rangle = \left( \left[ \frac{\partial \hat{C}}{\partial u} \right] \hat{G} |R\rangle + \hat{C} \left[ \frac{\partial \hat{G}}{\partial u} \right] |R\rangle + \hat{C} \hat{G} \left[ \frac{\partial |R\rangle}{\partial u} \right] \right) |\delta u\rangle
$$

양변에서 임의의 미소 변위 $|\delta u\rangle$를 분리해 내면, 최종적인 진성 자코비안 연산자 $\hat{J}$의 편미분 표현이 도출된다.

$$
\hat{J} = \underbrace{ \frac{\partial \hat{C}}{\partial u} \hat{G} |R\rangle}_{\text{수반 연산자 변분}} + \underbrace{\hat{C} \frac{\partial \hat{G}}{\partial u} |R\rangle}_{\text{메트릭 연산자 변분}} + \underbrace{\hat{C} \hat{G} \frac{\partial |R\rangle}{\partial u}}_{\text{물리 연산자 변분}}
$$



