+++
title = "(a) Dot products"
weight = 2
+++

---

### 1. 고차 tensor 내적

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

### 2. 대각합(trace)

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

---

### 4. 벡터의 크기

$$
||\vec{n}||
=\sqrt{n^in_i}
$$

proof)

$$
||\vec{n}||
=\sqrt{\vec{n}\cdot\vec{n}}
=\sqrt{n^i\vec{g}_i\cdot n_j\vec{g}^j}
=\sqrt{n^in_j\vec{g}_i\cdot\vec{g}^j}
=\sqrt{n^in_j\delta_i^j}
=\sqrt{n^in_i}
$$

---

### 5. 기저 벡터의 크기

$$
||\vec{g}_i||
=\sqrt{g_{\underline{i}\underline{i}}}
$$

$$
||\vec{g}^i||
=\sqrt{g^{\underline{i}\underline{i}}}
$$

여기에서 주의 해야할 점은, 지수 $i$ 는 중복 지수가 아니라는 것이다. 따라서, **$\underline{i}$ 는 지수에 대한 중복법칙을 적용하지 말라는 의미**이다. 


