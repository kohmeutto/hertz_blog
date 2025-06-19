+++
title = "(a) Unit tensor"
weight = 5
+++

---

### 1. 2차 단위 텐서

$$
\bar{\bar{I}}
=\left[\begin{matrix}
    1 & 0 & 0 \\
    0 & 1 & 0 \\
    0 & 0 & 1
\end{matrix}\right]
=\left[\begin{matrix}
    \delta_{11} & \delta_{12} & \delta_{13} \\
    \delta_{21} & \delta_{22} & \delta_{23} \\
    \delta_{31} & \delta_{32} & \delta_{33}
\end{matrix}\right]
=\delta_{ij}\hat{u}_i\hat{u}_j
=\hat{u}_j\hat{u}_j
$$

$$
\bar{\bar{I}}\cdot\vec{a}
=\vec{a}
$$

proof)

$$
\bar{\bar{I}}\cdot\vec{a}
=\delta_{ij}\hat{u}_i\hat{u}_j\cdot a_k\hat{u}_k
=\delta_{ij}a_k\hat{u}_i(\hat{u}_j\cdot\hat{u}_k)
=\delta_{ij}a_k\hat{u}_i\delta_{jk}
=a_j\hat{u}_j
=\vec{a}
$$

---

### 2. 대각합

$$
\bar{\bar{A}}:\bar{\bar{I}}
=\operatorname{tr}\bar{\bar{A}}
=A_{jj}=A_{11}+A_{22}+A_{33}
$$

대각합은 아래와 같은 성질을 가진다.

$$
(1)
\operatorname{tr}\bar{\bar{A}}
=\operatorname{tr}\bar{\bar{A}}^T
=A_{jj}
$$

$$
(2)
\operatorname{tr}\left\lbrace\bar{\bar{A}}+\bar{\bar{B}}\right\rbrace
=\operatorname{tr}\bar{\bar{A}}+\operatorname{tr}\bar{\bar{B}}
=A_{jj}+B_{jj}
$$

$$
(3)
\bar{\bar{A}}:\bar{\bar{B}}
=\bar{\bar{A}}\cdot\cdot\bar{\bar{B}}^T
=\left(\bar{\bar{A}}\cdot\bar{\bar I}\right)\cdot\bar{\bar{B}}^T
$$
