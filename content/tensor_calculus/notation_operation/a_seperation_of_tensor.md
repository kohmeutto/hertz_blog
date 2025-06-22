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
\bar{\bar{A}}=\operatorname{sym}\bar{\bar{A}}^T-\operatorname{skew}\bar{\bar{A}}^T
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