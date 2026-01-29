+++
title = "(b) Commutator"
weight = 8
+++

---

### 1. 교환자 (Commutator)

교환자는 두 연산자의 곱셈 순서가 결과에 미치는 영향을 측정하는 수학적 도구이다. 이는 행렬(연산자)들 사이의 구조적 호환성을 판별하는 데 핵심적인 역할을 한다. 두 연산자 $\hat{A}$와 $\hat{B}$의 **교환자(Commutator)** 는 다음과 같이 정의된다.

$$
[\hat{A}, \hat{B}] = \hat{A}\hat{B} - \hat{B}\hat{A}
$$

- 만약 $[\hat{A}, \hat{B}] = 0$ 이면, 두 연산자는 **교환 가능하다(commute)**
- 만약 $[\hat{A}, \hat{B}] \neq 0$ 이면, 두 연산자는 **교환 가능하지 않다(do not commute)**

---

### 2. 항등 성질

**(1) 반대칭성 (Anti-symmetry)**

$$
[\hat{A}, \hat{B}] = -[\hat{B}, \hat{A}]
$$

proof)

$$
[\hat{A}, \hat{B}]
= \hat{A}\hat{B} - \hat{B}\hat{A}
= -(\hat{B}\hat{A} - \hat{A}\hat{B})
= -[\hat{B}, \hat{A}]
$$

**(2) 선형성 (Linearity)**

$$
[\hat{A}, b\hat{B}+c\hat{C}] = b[\hat{A},\hat{B}] + c[\hat{A},\hat{C}] \text{, where b and c are scalar}
$$

proof)

$$
[\hat{A}, b\hat{B}+c\hat{C}]=\hat{A}(b\hat{B}+c\hat{C}) - (b\hat{B}+c\hat{C})\hat{A} \\
$$

$$
= (\hat{A}b\hat{B} + \hat{A}c\hat{C}) - (b\hat{B}\hat{A} + c\hat{C}\hat{A})
$$

$$
= b(\hat{A}\hat{B}) + c(\hat{A}\hat{C}) - b(\hat{B}\hat{A}) - c(\hat{C}\hat{A})
$$

$$
= b(\hat{A}\hat{B} - \hat{B}\hat{A}) + c(\hat{A}\hat{C} - \hat{C}\hat{A})
$$

$$
= b[\hat{A}, \hat{B}] + c[\hat{A}, \hat{C}]
$$

**(3) 야코비 항등식 (Jacobi Identity)**

$$
[\hat{A}, [\hat{B}, \hat{C}]] + [\hat{B}, [\hat{C}, \hat{A}]] + [\hat{C}, [\hat{A}, \hat{B}]] = 0
$$

proof)

- 첫 번째 항:

$$
[\hat{A}, [\hat{B}, \hat{C}]= [\hat{A}, (\hat{B}\hat{C} - \hat{C}\hat{B})]
$$

$$
= \hat{A}(\hat{B}\hat{C} - \hat{C}\hat{B}) - (\hat{B}\hat{C} - \hat{C}\hat{B})\hat{A}
$$

$$
= \hat{A}\hat{B}\hat{C} - \hat{A}\hat{C}\hat{B} - \hat{B}\hat{C}\hat{A} + \hat{C}\hat{B}\hat{A}
$$

- 두 번째 항 (인덱스 순환: $A \to B, B \to C, C \to A$):

$$
[\hat{B}, [\hat{C}, \hat{A}]] = \hat{B}\hat{C}\hat{A} - \hat{B}\hat{A}\hat{C} - \hat{C}\hat{A}\hat{B} + \hat{A}\hat{C}\hat{B}
$$

- 세 번째 항 (인덱스 순환: $B \to C, C \to A, A \to B$):

$$
[\hat{C}, [\hat{A}, \hat{B}]] = \hat{C}\hat{A}\hat{B} - \hat{C}\hat{B}\hat{A} - \hat{A}\hat{B}\hat{C} + \hat{B}\hat{A}\hat{C}
$$

- 이제 세 개의 결과를 모두 더하면,

$$
(\hat{A}\hat{B}\hat{C}-\hat{A}\hat{C}\hat{B}-\hat{B}\hat{C}\hat{A}+\hat{C}\hat{B}\hat{A})
$$

$$
+(\hat{B}\hat{C}\hat{A}-\hat{B}\hat{A}\hat{C}-\hat{C}\hat{A}\hat{B} + \hat{A}\hat{C}\hat{B})
$$

$$
+(\hat{C}\hat{A}\hat{B}-\hat{C}\hat{B}\hat{A}-\hat{A}\hat{B}\hat{C}+\hat{B}\hat{A}\hat{C})
$$

$$
= 0 
$$

---

### 3. 동시 스팩트럼 분해(대각화) 가능성

두 대각화 가능한 연산자 $\hat{A}$와 $\hat{B}$가 교환 가능한 것($[\hat{A}, \hat{B}]=0$)은, 두 연산자가 **공통의 완비적인 고유벡터 기저를 공유**하는 것과 동치이다.

proof)

$|v\rangle$가 $\hat{A}$의 고유벡터($\hat{A}|v\rangle=a|v\rangle$)라고 하자.

$$
0=[\hat{A}, \hat{B}]|v\rangle
=(\hat{A}\hat{B}-\hat{B}\hat{A})|v\rangle
$$

$$
=\hat{A}\hat{B}|v\rangle-\hat{B}\hat{A}|v\rangle
=\hat{A}\hat{B}|v\rangle-\hat{B}a|v\rangle
$$

아래와 같이 정리할 수 있다.

$$
\hat{A}\hat{B}|v\rangle=a(\hat{B}|v\rangle)
$$

이것은 $\hat{B}|v\rangle$ 가 $\hat{A}$의 고유벡터임을 의미한다. 또한 $\hat{B}|v\rangle$에 대응되는 고유값은 $a$이다. 따라서, $\hat{B}|v\rangle$는 $|v\rangle$와 종속이다.

$$
\hat{B}|v\rangle=c|v\rangle
$$

따라서, $\hat{B}$의 고유벡터는 $|v\rangle$ 이다.

---

### 4. 물리적 의미1,  CSCO

Complete Set of Commuting Observables

연산자는 고유벡터를 만나면, 고유벡터를 스케일링 한다. ~

---

### 5. 물리적 의미2, 동시측정 가능성

교환자는 두 물리량을 동시에 얼마나 정확하게 알 수 있는지를 판별하는 '측정 호환성 테스트'이다. **측정이란 어떤 고유값을 선택(중복포함하여)하는 것** 이다. 예로, $\hat{H}$ 를 기준으로 측정하여라 하면, $\hat{H}$ 고유값(중복고유값 포함) 중 하나가 임의로 선택되는 것을 말한다.

$$
|\psi\rangle \xrightarrow{\text{Measure=Pick}} \lambda^\text{중복도,3}(|\lambda_1^3\rangle+|\lambda_2^3\rangle+|\lambda_3^3\rangle)
$$


**(1) 교환하는 경우 ($[\hat{A}, \hat{B}] = 0$): 양립 가능한 측정량**

두 물리량은 **'양립 가능(compatible)'** 하며 동시에 확정된 값을 가질 수 있다. 하나의 양을 측정하는 행위가 다른 양의 상태를 교란시키지 않는다.

**(2) 교환하지 않는 경우 ($[\hat{A}, \hat{B}] \neq 0$): 양립 불가능한 측정량**

두 물리량 사이에는 **불확정성 원리(Uncertainty Principle)** 가 존재한다. 하나의 양을 정확하게 측정하면 다른 양의 정보가 필연적으로 불확실해진다.

---

**example1)** 다음 두 행렬 $A$와 $B$의 교환연산을 생각해 보자.

$$
A = \begin{bmatrix} 1 & 0 \\ 0 & -1 \end{bmatrix}, \quad
B = \begin{bmatrix} 2 & 0 \\ 0 & 5 \end{bmatrix}
$$

sol)

$$
 AB = \begin{pmatrix} 2 & 0 \\ 0 & -5 \end{pmatrix}, \quad
 BA = \begin{pmatrix} 2 & 0 \\ 0 & -5 \end{pmatrix}
 $$
 
 따라서 $[A, B] = AB - BA = 0$ 이다.

- A의 고유벡터:
  
$$\lambda=1,\quad
|u_1\rangle = \begin{bmatrix} 1 \\ 0 \end{bmatrix}
$$

$$\lambda=-1,\quad
|u_1\rangle = \begin{bmatrix} 0 \\ 1 \end{bmatrix}
$$


- B의 고유벡터:
 
 $$\lambda=2,\quad
 |u_1\rangle = \begin{bmatrix} 1 \\ 0 \end{bmatrix}
 $$

 $$
 \lambda=5,\quad
 |u_2\rangle = \begin{bmatrix} 0 \\ 1 \end{bmatrix}
 $$

두 행렬은 교환 가능하며, 그 결과 $\{|u_1\rangle, |u_2\rangle\}$라는 **공통의 완비적인 고유벡터 기저를 공유**함을 확인할 수 있다.

---

**example2)** convolution 연산자와 Laplace transform 연산자가 교환가능함을 보여라. 교환가능함은 고유벡터가 동일함을 의미한다. 이 고유벡터를 구하여라.


---

아주 핵심적인 질문입니다. **"교환 가능하다($XY=YX$)"**는 조건 하나가 어떻게 마법처럼 지수 법칙($e^X e^Y = e^{X+Y}$)을 성립시키는지, 그 수학적 메커니즘을 **'이항 정리(Binomial Theorem)'**를 통해 명쾌하게 보여드리겠습니다.결론부터 말씀드리면, **"교환이 가능해야만 우리가 아는 곱셈 공식($(A+B)^2 = A^2+2AB+B^2$)이 성립하기 때문"**입니다.1. 핵심 이유: 곱셈 공식의 부활지수 함수 $e^X$는 거듭제곱($X, X^2, X^3 \dots$)들의 합입니다. 따라서 지수 법칙이 성립하려면, 그 재료인 거듭제곱의 법칙이 먼저 성립해야 합니다.가장 쉬운 **2제곱(제곱)**을 예로 들어보겠습니다.$$(X+Y)^2 = (X+Y)(X+Y) = X^2 + \mathbf{XY + YX} + Y^2$$여기서 **교환 가능($XY=YX$)**하다면?중간항 $XY$와 $YX$가 똑같은 놈이 되어 합쳐집니다.$$X^2 + \mathbf{XY + XY} + Y^2 = X^2 + \mathbf{2XY} + Y^2$$우리가 중학교 때 배운 완전제곱식이 드디어 성립합니다. 이것이 바로 **이항 정리(Binomial Theorem)**입니다.교환 가능의 힘:순서가 상관없으므로($XY=YX$), 흩어져 있던 항들을 종류별로 모아서 깔끔한 계수(2, 3, 4...)로 묶을 수 있습니다.2. 지수 함수에 적용 (증명)이제 이 원리를 지수 함수 $e^{X+Y}$에 적용해 보겠습니다. 지수 함수의 정의에 따라 전개하면:$$e^{X+Y} = I + (X+Y) + \frac{1}{2!}(X+Y)^2 + \frac{1}{3!}(X+Y)^3 + \cdots$$교환 법칙($XY=YX$)이 성립한다면, 위에서 본 대로 $(X+Y)^n$을 이항 정리로 쪼갤 수 있습니다.$$\frac{1}{2!}(X+Y)^2 = \frac{1}{2!}(X^2 + 2XY + Y^2) = \frac{1}{2!}X^2 + \mathbf{XY} + \frac{1}{2!}Y^2$$이 결과는 $e^X$와 $e^Y$를 따로 곱했을 때 나오는 항들과 완벽하게 일치합니다.$$\begin{aligned}
e^X \cdot e^Y &= \left( I + X + \frac{1}{2}X^2 + \cdots \right) \left( I + Y + \frac{1}{2}Y^2 + \cdots \right) \\
&= I + (X+Y) + \frac{1}{2}X^2 + \mathbf{XY} + \frac{1}{2}Y^2 + \cdots
\end{aligned}$$Shutterstock탐색3. 요약: 왜 성립하는가?섞을 수 있다: 교환 가능하다는 것은 $X$와 $Y$의 순서를 마음대로 바꿔도 된다는 뜻입니다.묶을 수 있다: 순서를 바꿀 수 있으니, $XY$와 $YX$를 $2XY$로 합칠 수 있습니다. (이항 정리 성립)일치한다: 이항 정리가 성립하면, $(e^X \cdot e^Y)$의 전개식과 $(e^{X+Y})$의 전개식이 토씨 하나 안 틀리고 똑같아집니다.그래서 **"교환 가능하면($[X,Y]=0$), 파라미터 덧셈($e^{X+Y}$)이 성립"**하는 것입니다. 마치 실수($2^a 2^b = 2^{a+b}$)처럼 말이죠.