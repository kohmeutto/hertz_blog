+++
title = "(b) Null space"
weight = 1
+++

---

**정의 (영공간)**

행렬 $A$의 **영공간(Null Space)**이란, 행렬 $A$와의 곱셈을 통해 0벡터가 되는 모든 벡터 $|v\rangle$들의 집합이다. 이는 $A|v\rangle = 0$ 이라는 **제차 선형 방정식(Homogeneous Linear Equation)**의 **해공간(Solution Space)**과 같다.

> $$\text{Null}(A) = \{ |v\rangle \mid A|v\rangle=0 \}$$

---
### 증명 (영공간은 부분공간이다)

영공간은 단순한 집합을 넘어, 그 자체로 벡터 공간의 조건을 만족하는 '부분 공간(subspace)'이다.

1.  **덧셈에 대한 닫힘**: $|v_1\rangle$과 $|v_2\rangle$가 영공간에 속하면, $A(|v_1\rangle+|v_2\rangle) = A|v_1\rangle+A|v_2\rangle = 0+0=0$ 이므로, 그 합 $|v_1\rangle+|v_2\rangle$도 영공간에 속한다.
2.  **스칼라 곱에 대한 닫힘**: $|v\rangle$가 영공간에 속하고 $c$가 스칼라일 때, $A(c|v\rangle) = c(A|v\rangle) = c(0)=0$ 이므로, 그 스칼라 곱 $c|v\rangle$도 영공간에 속한다.

---
### 물리적 의미

영공간은 어떤 연산자(변환)에 의해 '소멸(annihilate)'되거나 '무시'되는 상태들의 집합이다. 이는 시스템의 **평형 상태, 보존 법칙, 대칭성, 정보 손실** 등 근본적인 특성을 나타내는 매우 중요한 공간이다. 이 때문에 **소멸 공간(Annihilation Space)**이라는 직관적인 이름으로도 이해할 수 있다.



---
### 예제

#### 예제 1: 1차원 영공간 (직선)

행렬 $A = \begin{pmatrix} 1 & 2 \\ 3 & 6 \end{pmatrix}$의 영공간을 구하시오.

1.  **방정식 설정**: $A\vec{x} = \vec{0}$
    $$
    \begin{pmatrix} 1 & 2 \\ 3 & 6 \end{pmatrix} \begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \end{pmatrix}
    $$

2.  **연립방정식 풀이**: 위 식으로부터 $x + 2y = 0$, 즉 $x = -2y$ 라는 관계를 얻는다.

3.  **해 벡터 표현**: 이 관계를 만족하는 모든 벡터 $\vec{x}$는 다음과 같이 쓸 수 있다.
    $$
    \vec{x} = \begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} -2y \\ y \end{pmatrix} = y \begin{pmatrix} -2 \\ 1 \end{pmatrix}
    $$

4.  **영공간**: $y$는 임의의 실수이므로, 영공간은 벡터 $\begin{pmatrix} -2 \\ 1 \end{pmatrix}$가 생성하는 **직선**이다.
    * **영공간**: $\text{Span}\left\{\begin{pmatrix} -2 \\ 1 \end{pmatrix}\right\}$

#### 예제 2: 2차원 영공간 (평면)

행렬 $B = \begin{pmatrix} 1 & 2 & 3 \\ 0 & 0 & 0 \\ 0 & 0 & 0 \end{pmatrix}$의 영공간을 구하시오.

1.  **방정식 설정**: $B\vec{x} = \vec{0}$
    $$
    \begin{pmatrix} 1 & 2 & 3 \\ 0 & 0 & 0 \\ 0 & 0 & 0 \end{pmatrix} \begin{pmatrix} x \\ y \\ z \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \\ 0 \end{pmatrix}
    $$
2.  **연립방정식 풀이**: 위 식으로부터 $x + 2y + 3z = 0$, 즉 $x = -2y - 3z$ 라는 관계를 얻는다. $y$와 $z$는 자유 변수이다.

3.  **해 벡터 표현**: 해 벡터 $\vec{x}$를 자유 변수 $y, z$로 표현한다.
    $$
    \vec{x} = \begin{pmatrix} -2y - 3z \\ y \\ z \end{pmatrix} = y \begin{pmatrix} -2 \\ 1 \\ 0 \end{pmatrix} + z \begin{pmatrix} -3 \\ 0 \\ 1 \end{pmatrix}
    $$

4.  **영공간**: 해 벡터는 두 벡터 $\begin{pmatrix} -2 \\ 1 \\ 0 \end{pmatrix}$와 $\begin{pmatrix} -3 \\ 0 \\ 1 \end{pmatrix}$의 모든 선형 결합이다. 따라서 영공간은 이 두 벡터가 생성하는 **평면**이다.
    * **영공간**: $\text{Span}\left\{\begin{pmatrix} -2 \\ 1 \\ 0 \end{pmatrix}, \begin{pmatrix} -3 \\ 0 \\ 1 \end{pmatrix}\right\}$