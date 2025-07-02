+++
title = "(a) Components"
weight = 2
+++

---

- **동일** 매개변수 공간에서의 변환을 다룬다.
- 매개변수 공간은 데카르트 좌표계로 표현한다.
- **변환은 다른 단위 직교 기저로의 변환**이다.

---


### 0. 정리

**(1) 성분 변환**

$$
u_i'=C_{ij}u_j
$$


**(2) 성분 역변환**

$$
u_i=C_{ji}u_j'
$$

**(3) 유니타리 연산자**

$$
\bar{\bar{I}}
=\bar{\bar{C}}\cdot\bar{\bar{C}}^T,\quad
\bar{\bar{C}}^T=\bar{\bar{C}}^{-1}
$$

**(4) 항등 연산**

$$
\delta_{ij}=C_{ki}C_{kj}
$$

---

### 1. 텐서 성분의 변환: 텐서 표기법 사용

$$
u_i'=C_{ij}u_j,\quad \text{$C_{ij}$ 는 성분 변환 텐서의 성분이다.}
$$

$$
C_{ij}=B_{ij}^{-1}=B_{ij}^T=B_{ji}
$$

proof)

**동일 공간**에서, 텐서는 기저가 달라져도 불변임을 기억하라.  $\vec{r}$ 을 u 기저와 u' 기저에서 다음과 같이 표현할 수 있다.

$$
\vec{r}
=u_i'\hat{u}_i'
=u_j\hat{u}_j
$$

**텐서의 성분 변환**을 파악하기 위해, **기저 벡터 변환 연산자** 를 사용하자.

$$
u_i'\hat{u}_i'
=u_i'B_{ij}\hat{u}_j
$$

$$
\implies
u_i'B_{ij}\hat{u}_j
=u_j\hat{u}_j
\implies
u_i'B_{ij}
=u_j
$$

$$
\implies
u_i'B_{ij}B_{ij}^{-1}
=B_{ij}^{-1}u_j
=B_{ij}^{T}u_j
=B_{ji}u_j
$$

따라서, 위의 성분 변환 텐서와 비교하면, 아래와 같이 **성분변환은 기저변환의 역행렬 또는 전치행렬** 임을 알 수 있다.

$$
C_{ij}=B_{ij}^{-1}=B_{ij}^T=B_{ji}
$$

---

### 2. 텐서 성분의 변환: Dirac notation 사용

아래의 논의는 매개변수공간(데카르트 좌표계로 표현) 뿐만아니라, **실공간의 일반좌표계에서도 적용**할 수 있다. 다시 한번 주의해야할 사항은 여기서의 변환은 **동일 공간**에서 수행한다.

**힐베르트 공간** 에서, 텐서 r를 아래와 같이 표현할 수 있다.

$$
|r\rangle
=u_i'|u_i'\rangle
=u_j|u_j\rangle
$$

**텐서의 성분 변환**을 파악하기 위해, **기저 벡터 변환** 을 수행하자. 항등 연산자를 사용하면,

$$
|r\rangle
=u_i'|u_i'\rangle
=u_j|u_i'\rangle\langle u_i'|u_j\rangle
=\langle u_i'|u_j\rangle u_j|u_i'\rangle
$$

따라서, 성분변환은 아래와 같다.

$$
u_{i}'
=\langle u_i'|u_j\rangle u_j
$$

정리하면, **벡터의 성분 변환 연산자**를 아래와 같이 표현할 수 있다.

$$
\hat{C}_{ij}
=\langle u_i'|u_j\rangle
$$

**일반적으로 벡터의 성분 변환은 내적의 관점**으로 아래와 같이 쓸 수 있다.

$$
u_{i}'
=\langle u_i'|\vec{r}
$$




렉 표기법을 이용한 항등 연산 증명
요청하신 항등 연산 δ 
ij
​
 =C 
ki
​
 C 
kj
​
  (이는 행렬 곱 C 
T
 C=I 에 해당)을 디렉 표기법으로 증명하겠습니다.

증명:

두 개의 **정규 직교 기저(orthonormal basis)**인 $\{|u_i\rangle\}$ (옛 기저)와 $\{|u_k'\rangle\}$ (새 기저)가 있다고 가정합니다.
성분 변환 행렬의 성분은 다음과 같이 정의됩니다:
C 
ki
​
 =⟨u 
k
′
​
 ∣u 
i
​
 ⟩

우리가 증명하려는 것은 $\sum_k C_{ki}C_{kj} = \delta_{ij}$ 입니다.

C_{ki} 와 C_{kj} 의 정의를 좌변에 대입합니다:
$\sum_k C_{ki}C_{kj} = \sum_k \langle u_k'|u_i \rangle \langle u_k'|u_j \rangle$

이제, 완비성 관계(Completeness Relation), 즉 항등 연산자( 
I
^
 )의 분해를 사용합니다. 정규 직교 기저 $\{|u_k'\rangle\}$ 에 대해 항등 연산자 $\hat{I}$는 다음과 같이 표현될 수 있습니다:
$\hat{I} = \sum_k |u_k'\rangle\langle u_k'|$

우변의 $\delta_{ij}$는 옛 기저 벡터들의 내적 $\langle u_i|u_j \rangle$와 같습니다.
$\langle u_i|u_j \rangle$ 에 항등 연산자 $\hat{I}$를 삽입할 수 있습니다:
$\delta_{ij} = \langle u_i|u_j \rangle = \langle u_i| \hat{I} |u_j \rangle$

이제 항등 연산자를 완비성 관계로 대체합니다:
$\delta_{ij} = \langle u_i| \left( \sum_k |u_k'\rangle\langle u_k'| \right) |u_j \rangle$

내적의 선형성에 따라 합 기호는 밖으로 나올 수 있습니다:
$\delta_{ij} = \sum_k \langle u_i|u_k' \rangle \langle u_k'|u_j \rangle$

마지막으로, 내적의 성질 $\langle a|b \rangle = \langle b|a \rangle*$ 를 사용합니다.
$\langle u_i|u_k' \rangle = \langle u_k'|u_i \rangle^* = (C_{ki})^*$

만약 변환 행렬의 성분들이 실수라면 (예: 회전 변환이나 좌표계 변환), (C 
ki
​
 ) 
∗
 =C 
ki
​
  가 됩니다.

따라서,
$\delta_{ij} = \sum_k C_{ki} C_{kj}$

증명 완료.
이 증명은 직교 변환 행렬의 핵심적인 성질인 C 
T
 C=I 가 기저 벡터의 정규직교성 및 완비성으로부터 직접적으로 유래함을 보여줍니다.

---

**example1)** 원통좌표계에서의 변위 벡터 $\vec{v}=\hat{\rho}v_\rho+\hat{\phi}v_\phi+\hat{z}v_z$ 를 직각좌표계에서의 성분으로 표현하라.

sol)

$$
\langle e^D_i|\vec{v}
=\begin{bmatrix}
    \cos\phi & -\sin\phi & 0 \\
    \sin\phi & \cos\phi  & 0 \\
    0        & 0         & 1
\end{bmatrix}
\begin{bmatrix}
    v_\rho \\ v_\phi \\ v_z
\end{bmatrix}
=\begin{bmatrix}
    v_\rho\cos\phi-v_\phi\sin\phi \\
    v_\rho\sin\phi+v_\phi\cos\phi \\
    v_z
\end{bmatrix}
$$