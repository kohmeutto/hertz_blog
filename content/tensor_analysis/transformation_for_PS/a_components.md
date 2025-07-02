+++
title = "(a) Components"
weight = 1
+++

---

- **동일** 매개변수 공간에서의 변환을 다룬다.
- 매개변수 공간은 데카르트 좌표계로 표현한다.
- **변환은 다른 단위 직교 기저로의 변환**이다.

---

### 1. 텐서 성분의 변환: Dirac notation 사용

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

---

### 2. 텐서 성분의 변환: 텐서 표기법 사용

기저의 성분은 모두 실수이다.

$$
u_i'=C_{ij}u_j,\quad \text{$C_{ij}$ 는 성분 변환 텐서의 성분이다.}
$$

$$
C_{ij}
=\langle u_i'|u_j\rangle
=\langle u_j|u_i'\rangle^\ast
=C_{ji}'
$$

이번에는 역변환을 생각해 보자.

$$
u_i=C_{ij}'u_j',\quad \text{$C_{ij}'$ 는 성분 변환 텐서의 성분이다.}
$$

$$
C_{ij}'
=\langle u_i|u_j'\rangle
=\langle u_j'|u_i\rangle^\ast
=C_{ji}
$$

---

### 3. 항등 연산

$$
\delta_{ij}=\langle u_i | u_j \rangle
= \langle u_i |\left(| u_k'\rangle \langle u_k'|\right)| u_j \rangle
= \langle u_i | u_k'\rangle \langle u_k'| u_j \rangle
= C_{ik}'C_{kj}
$$

여기에서,

$$
\langle u_i | u_k'\rangle=\langle u_k' | u_i\rangle^\ast
$$

기저의 성분이 실수라면,

$$
C'_{ik}=C_{ki}
$$

따라서,

$$
\delta_{ij}
=C_{ik}'C_{kj}
=C_{ki}C_{kj}
$$

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