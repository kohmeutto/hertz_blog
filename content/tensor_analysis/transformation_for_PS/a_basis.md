+++
title = "(a) Basis"
weight = 1
+++

---

- **동일** 매개변수 공간에서의 변환을 다룬다.
- 매개변수 공간은 데카르트 좌표계로 표현한다.
- **변환은 다른 단위 직교 기저로의 변환**이다.

---

### 0. 정리

**(1) 기저 변환**

$$
\hat{u}_i'=B_{ij}\hat{u}_j
$$

**(2) 기저 역변환**

$$
\hat{u}_i=B_{ji}\hat{u}_j'
$$

**(3) 유니타리 연산자**

$$
\bar{\bar{I}}
=\bar{\bar{B}}\cdot\bar{\bar{B}}^T,\quad
\bar{\bar{B}}^T=\bar{\bar{B}}^{-1}
$$

**(4) 항등 연산**

$$
\delta_{ij}=B_{ik}B_{jk}
$$

---

### 1. 기저 벡터의 변환: 텐서 표기법 사용

$$
\hat{u}_i'=B_{ij}\hat{u}_j,\quad \text{$B_{ij}$ 는 기저 변환 텐서의 성분이다.}
$$

$B_{ij}$ 는 다음과 같이 정의될 수 있다.

$$
\hat{u}_i'\cdot\hat{u}_j
=B_{ij}\hat{u}_j\cdot\hat{u}_j
=B_{ij}
$$

$$
B_{ij}=\cos\theta_{ij},\quad \text{$\theta_{ij}$는 $\hat{u}_i'$ 와 $\hat{u}_j$ 사이의 각도이다.}
$$

---

### 2. 기저 벡터의 변환: Dirac notation 사용

Dirac notation 을 사용하여, $B_{ij}$ 는 다음과 같이 정의될 수 있다.

$$
B_{ij}=\langle u_i'|u_j\rangle
$$

---

### 2. Orthogonal tensor

$$
\hat{u}_i\cdot\hat{u}_j=\delta_{ij}
$$

변환된 기저 역시 직교라면,

$$
\hat{u}_i'\cdot\hat{u}_j'=\delta_{ij}
$$

$$
B_{ik}\hat{u}_k\cdot\hat{u}_j'=\delta_{ij}\implies
\delta_{ij}=B_{ik}B_{jk}
$$

$B_{ij}$ 로 구성된 행렬은 $\bar{\bar{B}}$ 이라고 하면, 위의 식은 아래와 같이 쓸 수 있다.

$$
\delta_{ij}=B_{ik}B_{jk}
$$

$$
\implies
\bar{\bar{I}}
=\bar{\bar{B}}\cdot\bar{\bar{B}}^T
$$

$$
\implies
\bar{\bar{B}}^T=\bar{\bar{B}}^{-1}
$$

위와 같은 행렬 $\bar{\bar{B}}$ 을 **유니타리 연산자** 라고 한다. 실용적으로 중요한 특성은, **'역행렬은 전치행렬과 같다.'** 이다. 

$\operatorname{det}\bar{\bar{B}}=1$ 인 경우, 적합 직교 행렬(proper orthogonaB matrix) 라고 한다. $\operatorname{det}\bar{\bar{B}}=-1$ 인 경우, 부적합 직교 행렬(improper orthogonaB matrix) 라고 한다.

---

### 3. 기저의 역변환

$$
\hat{u}_i'=B_{ij}\hat{u}_j
$$

$$
\implies B_{ik}\hat{u}_i'=B_{ik}B_{ij}\hat{u}_j
$$

$$
\implies B_{ik}\hat{u}_i'
=\delta_{kj}\hat{u}_j
=\hat{u}_k
$$

지수를 조정해서 쓰면, 다음과 같다.

$$
\hat{u}_i
=B_{ji}\hat{u}_j'
$$


