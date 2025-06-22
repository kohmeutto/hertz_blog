+++
title = "(a) Unit tensor"
weight = 3
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

### 2. 2차 단위 텐서 점곱

$$
\bar{\bar{I}}:\bar{\bar{I}}
=\hat{u}_i\hat{u}_i:\hat{u}_j\hat{u}_j
=(\hat{u}_i\cdot\hat{u}_j)(\hat{u}_i\hat{u}_j)
=\delta_{ij}\delta_{ij}
=\delta_{ii}
=3
$$

---

### 3. 대각합

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
=\operatorname{tr}\left\lbrace \bar{\bar{A}}^T\cdot\bar{\bar{B}}\right\rbrace
=\operatorname{tr}\left\lbrace \bar{\bar{A}}\cdot\bar{\bar{B}^T}\right\rbrace
=\operatorname{tr}\left\lbrace \bar{\bar{B}}^T\cdot\bar{\bar{A}}\right\rbrace
=\operatorname{tr}\left\lbrace \bar{\bar{B}}\cdot\bar{\bar{A}^T}\right\rbrace
$$

$$
(4)
\operatorname{tr}\left\lbrace \bar{\bar{A}}^2\right\rbrace
=\operatorname{tr}\left\lbrace \bar{\bar{A}}\cdot\bar{\bar{A}}\right\rbrace
=\bar{\bar{A}}:\bar{\bar{A}}
$$

proof3)

$$
\bar{\bar{A}}:\bar{\bar{B}}
=A_{ij}B_{ij}
$$

$$
\bar{\bar{A}}^T\cdot\bar{\bar{B}}
=A^T_{ij}B_{jk}\implies
\operatorname{tr}\left\lbrace\bar{\bar{A}}^T\cdot\bar{\bar{B}}\right\rbrace
=\operatorname{tr}\left\lbrace A^T_{ij}B_{jk}\right\rbrace
=A^T_{ij}B_{ji}
=A_{ji}B_{ji}
$$

---