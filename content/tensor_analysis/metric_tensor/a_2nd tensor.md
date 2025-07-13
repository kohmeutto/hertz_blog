+++
title = "(a) 2nd tensor"
weight = 3
+++

---

### 1. 2차 mixed tensor 표기법

2차 혼합 텐서의 경우, 지수 순서를 파악하기 위해 아래와 같이 표기한다.

$$
\bar{\bar{A}}
=A^{i}_{.j}\vec{g}_i\vec{g}^j
=A_{i.}^{\ j}\vec{g}^i\vec{g}_j
$$

---

### 2. 2차 tensor의 전치 표기법

**(1) sym 2차 tensor**

$$
\bar{\bar{A}}^T
=(A^{ij})^T(\vec{g}_i\vec{g}_j)^T
=A^{ji}\vec{g}_j\vec{g}_i
=A^{ji}\vec{g}_i\vec{g}_j
$$

$$
(A^{ij})^T=A^{ji},\quad
(A_{ij})^T=A_{ji},\quad
(A^i_{.j})^T=A_{j.}^{\ i},\quad
$$

**(2) skew 2차 tensor**

$$
(A^{ij})^T=-A^{ji},\quad
(A_{ij})^T=-A_{ji},\quad
(A^i_{.j})^T=-A_{j.}^{\ i},\quad
$$

---

### 3. 고차 tensor 표기법

$$
\stackrel{4}{A}
=A^{ij}_{..kl}\vec{g}_i\vec{g}_j\vec{g}^k\vec{g}^l
$$

---

### 4. 성분 추출

When $\bar{\bar{A}}=A^{ij}\vec{g}_i\vec{g}_j$

**(1) covarient 성분**

$$
\vec{g}_k\cdot\bar{\bar{A}}\cdot\vec{g}_l
=\langle g_k|\bar{\bar{A}}|g_l\rangle
$$

$$
=\vec{g}_k\cdot A^{ij}\vec{g}_i\vec{g}_j\cdot\vec{g}_l
=A^{ij}(\vec{g}_k\cdot\vec{g}_i)(\vec{g}_j\cdot\vec{g}_l)
=A^{ij}g_{ki}g_{jl}
$$

$$
=A_{kl}
$$

**(2) mixed 성분**

$$
\vec{g}^k\cdot\bar{\bar{A}}\cdot\vec{g}_l
=\langle g^k|\bar{\bar{A}}|g_l\rangle
$$

$$
=\vec{g}^k\cdot A^{ij}\vec{g}_i\vec{g}_j\cdot\vec{g}_l
=A^{ij}(\vec{g}^k\cdot\vec{g}_i)(\vec{g}_j\cdot\vec{g}_l)
=A^{ij}\delta^k_ig_{jl}
$$

$$
=A^k_{.l}
$$

**(3) 여러 종류의 성분 추출**

위와 유사한 과정을 거치면, 다음과 같은 다양한 형태의 성분들을 추출술 수 있다.

$$
A^i_{.j}=g^{ik}A_{kj}=g_{jk}A^{ik}
$$

$$
A^{\ i}_{j.}=g^{ik}A_{jk}
$$

$$
A^{ij}=g^{jk}A^i_{.k}=g^{ik}g^{jl}A_{kl}
$$

$$
A_{ij}=g_{ik}A^k_{.j}
$$

---


### 5. 고차 tensor 내적

When $\bar{\bar{\sigma}}=\sigma^{ij}\vec{g}_i\vec{g}_j$ and $\vec{n}=n^k\vec{g}_k$,

$$
\vec{T}
=\bar{\bar{\sigma}}\cdot\vec{n}
=\sigma^{ij}\vec{g}_i\vec{g}_j\cdot n^k\vec{g}_k
=\sigma^{ij}n^k\vec{g}_i\vec{g}_j\cdot \vec{g}_k
$$

$$
=\sigma^{ij}n^k\vec{g}_ig_{jk}
$$

$$
=\sigma^{ij}n_j\vec{g}_i
$$

and also when $\bar{\bar{\varepsilon}}=\varepsilon_{kl}\vec{g}^k\vec{g}^l$

$$
W
=\frac12\bar{\bar{\sigma}}:\bar{\bar{\varepsilon}}
=\frac12\sigma^{ij}\vec{g}_i\vec{g}_j:\varepsilon_{kl}\vec{g}^k\vec{g}^l
=\frac12\sigma^{ij}\varepsilon_{kl}\vec{g}_i\vec{g}_j:\vec{g}^k\vec{g}^l
=\frac12\sigma^{ij}\varepsilon_{kl}(\vec{g}_i\cdot\vec{g}^k)(\vec{g}_j\cdot\vec{g}^l)
$$

$$
=\frac12\sigma^{ij}\varepsilon_{kl}\delta_i^k\delta_j^l
$$

$$
=\frac12\sigma^{ij}\varepsilon_{ij}
$$

---

### 6. 대각합(trace)

$$
\operatorname{tr}\bar{\bar{A}}
=\bar{\bar{A}}:\bar{\bar{I}}
=A^i_{.i}
$$

proof)

$$
\operatorname{tr}\bar{\bar{A}}
=\bar{\bar{A}}:\bar{\bar{I}}
=A^{ij}\vec{g}_i\vec{g}_j:\vec{g}_k\vec{g}^k
=A^{ij}(\vec{g}_i\cdot\vec{g}_k)(\vec{g}_j\cdot\vec{g}^k)
$$

$$
=A^{ij}g_{ik}\delta_j^k
=A^{ik}g_{ik}
=A^{i}_{.i}
$$