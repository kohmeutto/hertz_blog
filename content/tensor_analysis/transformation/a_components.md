+++
title = "(a) Components"
weight = 2
+++

---

**데카르트 좌표계로 간주하는 매개변수 공간 또는 데카르트 좌표계 실공간**에 대한 설명 이다. 

---

### 0. 정리

**(1) 기저 변환**

$$
\hat{u}_i'=l_{ij}\hat{u}_j
$$

**(2) 기저 역변환**

$$
\hat{u}_i=l_{ji}\hat{u}_j'
$$

**(3) 유니타리 연산자**

$$
\bar{\bar{I}}
=\bar{\bar{L}}\cdot\bar{\bar{L}}^T,\quad
\bar{\bar{L}}^T=\bar{\bar{L}}^{-1}
$$

---

### 1. 기저 벡터의 변환

$$
\hat{u}_i'=l_{ij}\hat{u}_j,\quad \text{$l_{ij}$ 는 변환 텐서의 성분이다.}
$$

변환된 좌표계 역시, 직교 좌표계로 간주할 수 있다면, $l_{ij}$ 는 다음과 같이 정의될 수 있다.

$$
\hat{u}_i'\cdot\hat{u}_j
=l_{ij}\hat{u}_j\cdot\hat{u}_j
=l_{ij}
$$

$$
l_{ij}=\cos\theta_{ij},\quad \text{$\theta_{ij}$는 $\hat{u}_i'$ 와 $\hat{u}_j$ 사이의 각도이다.}
$$

---

### 2. Orthogonal tensor

$$
\hat{u}_i\cdot\hat{u}_j=\delta_{ij}
$$

변환된 좌표계 역시 직교라면,

$$
\hat{u}_i'\cdot\hat{u}_j'=\delta_{ij}
$$

$$
l_{ik}\hat{u}_k\cdot\hat{u}_j'=\delta_{ij}\implies
\delta_{ij}=l_{ik}l_{jk}
$$

$l_{ij}$ 로 구성된 행렬은 $\bar{\bar{L}}$ 이라고 하면, 위의 식은 아래와 같이 쓸 수 있다.

$$
\delta_{ij}=l_{ik}l_{jk}
$$

$$
\implies
\bar{\bar{I}}
=\bar{\bar{L}}\cdot\bar{\bar{L}}^T
$$

$$
\implies
\bar{\bar{L}}^T=\bar{\bar{L}}^{-1}
$$

위와 같은 행렬 $\bar{\bar{L}}$ 을 **유니타리 연산자** 라고 한다. 실용적으로 중요한 특성은, **'역행렬은 전치행렬과 같다.'** 이다. 

$\operatorname{det}\bar{\bar{L}}=1$ 인 경우, 적합 직교 행렬(proper orthogonal matrix) 라고 한다. $\operatorname{det}\bar{\bar{L}}=-1$ 인 경우, 부적합 직교 행렬(improper orthogonal matrix) 라고 한다.

---

### 3. 기저의 역변환

$$
\hat{u}_i'=l_{ij}\hat{u}_j
$$

$$
\implies l_{ik}\hat{u}_i'=l_{ik}l_{ij}\hat{u}_j
$$

$$
\implies l_{ik}\hat{u}_i'
=\delta_{kj}\hat{u}_j
=\hat{u}_k
$$

지수를 조정해서 쓰면, 다음과 같다.

$$
\hat{u}_i
=l_{ji}\hat{u}_j'
$$