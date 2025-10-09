+++
title = "(b) Commutator"
weight = 8
+++

---

## 3. 교환자 (Commutator)

교환자는 두 연산자의 곱셈 순서가 결과에 미치는 영향을 측정하는 수학적 도구이다. 이는 행렬(연산자)들 사이의 구조적 호환성을 판별하는 데 핵심적인 역할을 한다.

### 3.1 정의와 기본 성질

**정의 (교환자)**
두 연산자 $\hat{A}$와 $\hat{B}$의 **교환자(Commutator)**는 다음과 같이 정의된다.
> $$[\hat{A}, \hat{B}] = \hat{A}\hat{B} - \hat{B}\hat{A}$$
- 만약 $[\hat{A}, \hat{B}] = 0$ 이면, 두 연산자는 **교환 가능하다(commute)**고 한다.
- 만약 $[\hat{A}, \hat{B}] \neq 0$ 이면, 두 연산자는 **교환 가능하지 않다(do not commute)**고 한다.

네, 알겠습니다. 교환자의 기본 성질 세 가지(반대칭성, 선형성, 야코비 항등식)에 대한 완전한 증명을 포함하여 Hugo 마크다운 문서로 작성해 드리겠습니다.

## 3.1 교환자의 정의와 기본 성질

**정의 (교환자)**

두 연산자 $\hat{A}$와 $\hat{B}$의 **교환자(Commutator)**는 두 연산자의 곱셈 순서를 바꾸어 뺐을 때의 차이로 정의된다.
> $$[\hat{A}, \hat{B}] = \hat{A}\hat{B} - \hat{B}\hat{A}$$
- 만약 $[\hat{A}, \hat{B}] = 0$ 이면, 두 연산자는 **교환 가능하다(commute)**고 한다.
- 만약 $[\hat{A}, \hat{B}] \neq 0$ 이면, 두 연산자는 **교환 가능하지 않다(do not commute)**고 한다.

---
### 기본 성질 및 증명

#### **1. 반대칭성 (Anti-symmetry)**
> $$[\hat{A}, \hat{B}] = -[\hat{B}, \hat{A}]$$

> **증명**:
> $$
\begin{align*}
[\hat{A}, \hat{B}] &= \hat{A}\hat{B} - \hat{B}\hat{A} \\
&= -(\hat{B}\hat{A} - \hat{A}\hat{B}) \\
&= -[\hat{B}, \hat{A}] \quad \blacksquare
\end{align*}
> $$

#### **2. 선형성 (Linearity)**
> $$[\hat{A}, b\hat{B}+c\hat{C}] = b[\hat{A},\hat{B}] + c[\hat{A},\hat{C}]$$
> (여기서 $b, c$는 스칼라)

> **증명**:

$$
\begin{align*}
[\hat{A}, b\hat{B}+c\hat{C}] &= \hat{A}(b\hat{B}+c\hat{C}) - (b\hat{B}+c\hat{C})\hat{A} \\
&= (\hat{A}b\hat{B} + \hat{A}c\hat{C}) - (b\hat{B}\hat{A} + c\hat{C}\hat{A}) \\
&= b(\hat{A}\hat{B}) + c(\hat{A}\hat{C}) - b(\hat{B}\hat{A}) - c(\hat{C}\hat{A}) \\
&= b(\hat{A}\hat{B} - \hat{B}\hat{A}) + c(\hat{A}\hat{C} - \hat{C}\hat{A}) \\
&= b[\hat{A}, \hat{B}] + c[\hat{A}, \hat{C}] \quad \blacksquare
\end{align*}
$$

#### **3. 야코비 항등식 (Jacobi Identity)**
> $$[\hat{A}, [\hat{B}, \hat{C}]] + [\hat{B}, [\hat{C}, \hat{A}]] + [\hat{C}, [\hat{A}, \hat{B}]] = 0$$

> **증명**: 각 항을 교환자의 정의에 따라 전개한다.
>
> 1. 첫 번째 항:

$$
\begin{align*}
[\hat{A}, [\hat{B}, \hat{C}]] &= [\hat{A}, (\hat{B}\hat{C} - \hat{C}\hat{B})] \\
&= \hat{A}(\hat{B}\hat{C} - \hat{C}\hat{B}) - (\hat{B}\hat{C} - \hat{C}\hat{B})\hat{A} \\
&= \hat{A}\hat{B}\hat{C} - \hat{A}\hat{C}\hat{B} - \hat{B}\hat{C}\hat{A} + \hat{C}\hat{B}\hat{A}
\end{align*}
$$

> 2. 두 번째 항 (인덱스 순환: $A \to B, B \to C, C \to A$):

$$
\begin{align*}
[\hat{B}, [\hat{C}, \hat{A}]] &= \hat{B}\hat{C}\hat{A} - \hat{B}\hat{A}\hat{C} - \hat{C}\hat{A}\hat{B} + \hat{A}\hat{C}\hat{B}
\end{align*}
$$

> 3. 세 번째 항 (인덱스 순환: $B \to C, C \to A, A \to B$):

$$
\begin{align*}
[\hat{C}, [\hat{A}, \hat{B}]] &= \hat{C}\hat{A}\hat{B} - \hat{C}\hat{B}\hat{A} - \hat{A}\hat{B}\hat{C} + \hat{B}\hat{A}\hat{C}
\end{align*}
$$

> 4. 이제 세 개의 결과를 모두 더하면,

$$
\begin{align*}
(\hat{A}\hat{B}\hat{C}-\hat{A}\hat{C}\hat{B}-\hat{B}\hat{C}\hat{A}+\hat{C}\hat{B}\hat{A}) \\
+&(\hat{B}\hat{C}\hat{A}-\hat{B}\hat{A}\hat{C}-\hat{C}\hat{A}\hat{B} + \hat{A}\hat{C}\hat{B}) \\
+&(\hat{C}\hat{A}\hat{B}-\hat{C}\hat{B}\hat{A}-\hat{A}\hat{B}\hat{C}+\hat{B}\hat{A}\hat{C}) \\
= & \quad 0 
\end{align*}
$$

> 모든 항이 서로 상쇄되어 0이 된다.

---
### 3.2 핵심 정리: 동시 대각화 가능성

교환자의 가장 중요한 수학적 의미는 **동시 대각화 가능성(simultaneous diagonalizability)**과 연결된다.

> **정리**: 두 대각화 가능한 행렬 $\hat{A}$와 $\hat{B}$가 교환 가능한 것($[\hat{A}, \hat{B}]=0$)은, 두 행렬이 **공통의 완비적인 고유벡터 기저를 공유**하는 것과 동치이다.

**증명 요약)**
$|v\rangle$가 $\hat{A}$의 고유벡터($\hat{A}|v\rangle=a|v\rangle$)라고 하자. $[\hat{A}, \hat{B}]|v\rangle=0$ 으로부터 $\hat{A}(\hat{B}|v\rangle) = a(\hat{B}|v\rangle)$를 보일 수 있다. 이는 $\hat{B}|v\rangle$라는 새로운 벡터 역시 $\hat{A}$의 고유값 $a$에 대한 고유벡터임을 의미한다. 만약 고유값이 겹치지 않는다면(non-degenerate), $\hat{B}|v\rangle$는 $|v\rangle$의 상수배여야 하므로, $|v\rangle$는 $\hat{B}$의 고유벡터이기도 하다. (겹치는 경우에도 이 논리는 확장 가능하다.)

**의미**: 교환자가 0이라는 것은, 두 변환의 '자연스러운 좌표축'(고유벡터)이 서로 같아서, **하나의 좌표계에서 두 변환을 모두 가장 간단한 형태(대각 행렬)로 동시에 표현할 수 있다**는 의미이다. 이는 두 연산자의 구조적 '호환성'을 판별하는 근본적인 도구임을 보여준다.

---

### 3.3 물리적 의미 1: 동시 측정 가능성과 불확정성 원리

교환자는 두 물리량을 동시에 얼마나 정확하게 알 수 있는지를 판별하는 '측정 호환성 테스트'이다.

> **정리 (동시 대각화)**: 두 에르미트 연산자 $\hat{A}$와 $\hat{B}$가 교환 가능할 때($[\hat{A}, \hat{B}]=0$), 두 연산자를 **동시에 대각화**할 수 있다. 즉, $\hat{A}$의 고유벡터이면서 동시에 $\hat{B}$의 고유벡터인 완벽한 기저가 존재한다.

> **증명 요약**:
> $|a\rangle$가 $\hat{A}$의 고유벡터($\hat{A}|a\rangle=a|a\rangle$)라고 하자. $[\hat{A}, \hat{B}]|a\rangle=0$ 으로부터 $\hat{A}(\hat{B}|a\rangle) = a(\hat{B}|a\rangle)$를 보일 수 있다. 이는 $\hat{B}|a\rangle$라는 새로운 벡터 역시 $\hat{A}$의 고유값 $a$에 대한 고유벡터임을 의미한다. 만약 고유값이 겹치지 않는다면, $\hat{B}|a\rangle$는 $|a\rangle$의 상수배여야 하므로, $|a\rangle$는 $\hat{B}$의 고유벡터이기도 하다.

**A) 교환하는 경우 ($[\hat{A}, \hat{B}] = 0$): 양립 가능한 측정량**
두 물리량은 **'양립 가능(compatible)'**하며 동시에 확정된 값을 가질 수 있다. 하나의 양을 측정하는 행위가 다른 양의 상태를 교란시키지 않는다.
- **예제**: 자유 입자의 에너지($\hat{H}=\hat{P}^2/2m$)와 운동량($\hat{P}$)
    > $$[\hat{H}, \hat{P}] = 0$$
    따라서 '확정된 에너지'를 가지면서 동시에 '확정된 운동량'을 가지는 상태(운동량 고유 상태)가 존재할 수 있다.

**B) 교환하지 않는 경우 ($[\hat{A}, \hat{B}] \neq 0$): 양립 불가능한 측정량**
두 물리량 사이에는 **불확정성 원리(Uncertainty Principle)**가 존재한다. 하나의 양을 정확하게 측정하면 다른 양의 정보가 필연적으로 불확실해진다.
- **예제**: 위치($\hat{X}$)와 운동량($\hat{P}$)
    > $$[\hat{X}, \hat{P}] = i\hbar$$
    교환자가 0이 아니므로, 위치와 운동량을 동시에 정확하게 측정할 수 없다. 이는 $\sigma_x \sigma_p \ge \hbar/2$ 라는 하이젠베르크 불확정성 관계로 이어진다.

---

### 3.4 물리적 의미 2: 대칭성과 보존 법칙

어떤 물리량이 시간에 따라 변하지 않고 '보존'되는지 여부는, 그 물리량의 연산자가 **해밀토니안 연산자($\hat{H}$)**와 교환 가능한지에 따라 결정된다.

> **정리 (하이젠베르크 운동방정식)**: 어떤 물리량 $\hat{A}$의 시간에 따른 변화율은 다음과 같다.
> $$\frac{d\hat{A}}{dt} = \frac{1}{i\hbar}[\hat{A}, \hat{H}] + \frac{\partial\hat{A}}{\partial t}$$

> **증명 (보존 법칙)**: 만약 연산자 $\hat{A}$가 시간에 직접적으로 의존하지 않고($\frac{\partial\hat{A}}{\partial t}=0$), 해밀토니안과 교환 가능하다면($[\hat{A}, \hat{H}]=0$), 위 방정식의 우변은 0이 된다.
> $$\frac{d\hat{A}}{dt} = 0$$
> 이는 물리량 $\hat{A}$의 기댓값이 시간에 따라 변하지 않음, 즉 **보존됨**을 의미한다.

- **에너지 보존**: 해밀토니안이 시간에 무관하면, 자기 자신과는 항상 교환 가능하므로($[\hat{H}, \hat{H}]=0$) **에너지가 보존된다.**
- **운동량 보존**: 시스템이 공간적 대칭성(위치에 따라 포텐셜이 변하지 않음)을 가지면, $[\hat{P}, \hat{H}]=0$ 이 되어 **운동량이 보존된다.**
- **각운동량 보존**: 시스템이 회전 대칭성(방향에 따라 포텐셜이 변하지 않음)을 가지면, $[\hat{L}, \hat{H}]=0$ 이 되어 **각운동량이 보존된다.**

---

### 3.3 예제

다음 두 행렬 $A$와 $B$를 고려해 보자.
$$
A = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}, \quad
B = \begin{pmatrix} 2 & 0 \\ 0 & 5 \end{pmatrix}
$$

1.  **교환자 계산**: 두 행렬이 모두 대각 행렬이므로, 곱셈 순서를 바꾸어도 결과가 같다.
    $$
    AB = \begin{pmatrix} 2 & 0 \\ 0 & -5 \end{pmatrix}, \quad
    BA = \begin{pmatrix} 2 & 0 \\ 0 & -5 \end{pmatrix}
    $$
    따라서 $[A, B] = AB - BA = 0$ 이다.

2.  **각 행렬의 고유벡터 찾기**:
    * **A의 고유벡터**:
        * $\lambda=1$: $|e_1\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix}$
        * $\lambda=-1$: $|e_2\rangle = \begin{pmatrix} 0 \\ 1 \end{pmatrix}$
    * **B의 고유벡터**:
        * $\lambda=2$: $|e_1\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix}$
        * $\lambda=5$: $|e_2\rangle = \begin{pmatrix} 0 \\ 1 \end{pmatrix}$

3.  **결론**: 두 행렬은 교환 가능하며, 그 결과 $\{|e_1\rangle, |e_2\rangle\}$라는 **공통의 완비적인 고유벡터 기저를 공유**함을 확인할 수 있다.