+++
title = "(a) Seperation of tensor"
weight = 4
+++

---

### 1. 대칭 및 비대칭 tensor

이중 bar $\bar{\bar{A}}$는 2차텐서를 의미한다.

**(1) 대칭 텐서**

아래를 만족할 때, 대칭텐서라고 한다.

$$
\bar{\bar{A}}=\bar{\bar{A}}^T,\quad
A_{ij}=A_{ji}
$$

**(2) 비대칭 텐서**

아래를 만족할 때, 비대칭 텐서라고 한다.

$$
\bar{\bar{A}}=-\bar{\bar{A}}^T,\quad
A_{ij}=-A_{ji}
$$

**(3) 대칭 텐서와 비대칭 텐서의 분리**

대칭 비대칭의 성질을 이용하여, 임의이 텐서를 아래와 같이 쓸 수 있다.

$$
\bar{\bar{A}}=\operatorname{sym}\bar{\bar{A}}+\operatorname{skew}\bar{\bar{A}}
$$

여기에서, sym과 skew는 대칭과 비대칭을 의미하며, 다음과 같이 정의된다.

$$
\operatorname{sym}\bar{\bar{A}}
=\frac{1}{2}\left(\bar{\bar{A}}+\bar{\bar{A}}^T\right)
$$

$$
\operatorname{skew}\bar{\bar{A}}
=\frac{1}{2}\left(\bar{\bar{A}}-\bar{\bar{A}}^T\right)
$$

proof)

$$
\bar{\bar{A}}=\operatorname{sym}\bar{\bar{A}}+\operatorname{skew}\bar{\bar{A}}
$$

$$
\bar{\bar{A}}^T=\operatorname{sym}\bar{\bar{A}}^T-\operatorname{skew}\bar{\bar{A}}^T
$$

따라서,

$$
\operatorname{sym}\bar{\bar{A}}
=\frac{1}{2}\left(\bar{\bar{A}}+\bar{\bar{A}}^T\right)
$$

$$
\operatorname{skew}\bar{\bar{A}}
=\frac{1}{2}\left(\bar{\bar{A}}-\bar{\bar{A}}^T\right)
$$

---

**example1)** 다음에 주어진 tensor를 대칭과 비대칭 부분으로 나누어 표시하시오.

$$
\bar{\bar{A}}
=\left[\begin{matrix}
    1  & -2 & 1 \\
    -1 &  2 & 0 \\
    1  &  1 & -1
\end{matrix}\right]
$$

sol)

$$
\bar{\bar{A}}^T
=\left[\begin{matrix}
    1  & -1 & 1 \\
    -2 &  2 & 1 \\
    1  &  0 & -1
\end{matrix}\right]
$$

$$
\operatorname{sym}\bar{\bar{A}}
=\frac{1}{2}\left(\bar{\bar{A}}+\bar{\bar{A}}^T\right)
=\frac{1}{2}\left[\begin{matrix}
    2  & -3 & 2 \\
    -3 &  4 & 1 \\
    2  &  1 & -2
\end{matrix}\right]
$$

$$
\operatorname{skew}\bar{\bar{A}}
=\frac{1}{2}\left(\bar{\bar{A}}-\bar{\bar{A}}^T\right)
=\frac{1}{2}\left[\begin{matrix}
    0  & -1 & 0 \\
    1 &  4 & -1 \\
    0  &  1 & 0
\end{matrix}\right]
$$

---

### 2. Isotropic(등방) & deviatoric(일탈) tensor

임의의 텐서는 등방 & 일탈 텐서의 합으로 표시할 수 있다.

$$
\bar{\bar{A}}=\bar{\bar{A}}^i+\bar{\bar{A}}^d
$$

**(1) 등방 텐서**

$$
\bar{\bar{A}}^i=\frac13\operatorname{tr}\left\lbrace
\bar{\bar{A}}\right\rbrace\bar{\bar{I}}
$$

**(2) 일탈 텐서**

$$
\bar{\bar{A}}^d=\bar{\bar{A}}-\frac13\operatorname{tr}\left\lbrace
\bar{\bar{A}}\right\rbrace\bar{\bar{I}}
$$

$$
A^d_{ij}=A_{ij}-\frac13 A_{kk}\delta_{ij}
$$

---

**example1)** 다음에 주어진 tensor의 일탈 tensor를 구하시오.

$$
\bar{\bar{A}}
=\left[\begin{matrix}
    1  & -2 & 1 \\
    -1 &  2 & 0 \\
    1  &  1 & -1
\end{matrix}\right]
$$

sol)

$$
\bar{\bar{A}}^d=\bar{\bar{A}}-\frac13\operatorname{tr}\left\lbrace
\bar{\bar{A}}\right\rbrace\bar{\bar{I}}
=\left[\begin{matrix}
    1  & -2 & 1 \\
    -1 &  2 & 0 \\
    1  &  1 & -1
\end{matrix}\right]
-\frac13\cdot 2\cdot
\left[\begin{matrix}
    1 & 0 & 0 \\
    0 & 1 & 0 \\
    0 & 0 & 1
\end{matrix}\right]
$$

$$
=\left[\begin{matrix}
    \frac13 & -2 & 1 \\
    -1 & \frac43 & 0 \\
    1 & 1 & -\frac53
\end{matrix}\right]
$$