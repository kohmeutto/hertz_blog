+++
title = "(a) Inverse & Determinant"
weight = 6
+++

---

**Tensor 방정식을 사용하여 연산을 하는 많은 경우에 tensor의 역을 구해야 할 필요가 있다.**

역행렬을 손으로 계산하기에 적당한 크기는 3X3의 행렬식으로 표시가 가능한 2차 tensor 정도이며,
그 이상은 계산량의 증가로 인하여 해석적인 방법은 실제 사용하지 않는다.

---

### 1. Tensor의 역(inverse)

$$
\bar{\bar{A}}\cdot\bar{\bar{A}}^{-1}
=\bar{\bar{I}}
$$

$\bar{\bar{A}}^{-1}$의 지수표현은 

$$
\left[A_{ij}\right]^{-1}
$$

---

### 2. 행렬식(determinant)

$$
\operatorname{det}\bar{\bar{A}}
=\operatorname{det}\left[\begin{matrix}
    A_{11} & A_{12} & A_{13} \\
    A_{21} & A_{22} & A_{23} \\
    A_{31} & A_{32} & A_{33}
\end{matrix}\right]
$$

$$
=A_{11}\hat{A}_{11}+A_{11}\hat{A}_{12}+A_{11}\hat{A}_{13}
$$

$$
=A_{21}\hat{A}_{21}+A_{22}\hat{A}_{22}+A_{23}\hat{A}_{23}
$$

$$
=A_{31}\hat{A}_{31}+A_{32}\hat{A}_{32}+A_{33}\hat{A}_{33}
$$

여기에서,

$$
\hat{A}_{11}
=\left|\begin{matrix}
    A_{22} & A_{23} \\
    A_{32} & A_{33}
\end{matrix}\right|,\quad
\hat{A}_{12}
=-\left|\begin{matrix}
    A_{21} & A_{23} \\
    A_{31} & A_{33}
\end{matrix}\right|,\quad
\hat{A}_{13}
=\left|\begin{matrix}
    A_{21} & A_{22} \\
    A_{31} & A_{32}
\end{matrix}\right|
$$

$$
\hat{A}_{21}
=-\left|\begin{matrix}
    A_{12} & A_{13} \\
    A_{32} & A_{33}
\end{matrix}\right|,\quad
\hat{A}_{22}
=\left|\begin{matrix}
    A_{11} & A_{13} \\
    A_{31} & A_{33}
\end{matrix}\right|,\quad
\hat{A}_{23}
=-\left|\begin{matrix}
    A_{11} & A_{12} \\
    A_{31} & A_{32}
\end{matrix}\right|
$$

$$
\hat{A}_{31}
=\left|\begin{matrix}
    A_{11} & A_{12} \\
    A_{21} & A_{22}
\end{matrix}\right|,\quad
\hat{A}_{32}
=-\left|\begin{matrix}
    A_{11} & A_{13} \\
    A_{21} & A_{23}
\end{matrix}\right|,\quad
\hat{A}_{33}
=\left|\begin{matrix}
    A_{11} & A_{12} \\
    A_{21} & A_{22}
\end{matrix}\right|
$$

$\hat{A}_{ij}$를 여인자라고 한다.

$$
\hat{A}_{ij}
=(-1)^{i+j}A_{ij}
$$

---

### 3. 행렬식의 성질

$$
\operatorname{det}\bar{\bar{A}}^T
=\operatorname{det}\bar{\bar{A}}
$$

$$
\operatorname{det}\bar{\bar{A}}\bar{\bar{B}}
=\operatorname{det}\bar{\bar{A}}\operatorname{det}\bar{\bar{B}}
$$

$$
\operatorname{det}\bar{\bar{A}}^{-1}
=\frac{1}{\operatorname{det}\bar{\bar{A}}}
$$

---

### 4. 역행렬(inverse matrix)

임의의 정방행렬을 아래와 같이 표현하였을 때,

$$
\bar{\bar{A}}
=[A_{ij}]
=\left[\begin{matrix}
    A_{11} & A_{12} & A_{13} & \cdots \\
    \vdots &        &        & \vdots \\
    A_{n1} & \cdots & \cdots & A_{nn}
\end{matrix}\right]
$$

역행렬은 다음과 같이 구한다.

$$
\bar{\bar{A}}^{-1}
=\frac{\left[\hat{A}_{ij}\right]^T}{\operatorname{det}\bar{\bar{A}}}
$$

2X2, 2차 텐서에 대한 역행렬은 다음과 같이 쓸 수 있다.

$$
\bar{\bar{A}}^{-1}
=\frac{1}{\operatorname{det}\bar{\bar{A}}}
\left[\begin{matrix}
    \hat{A}_{11} & \hat{A}_{21} & \hat{A}_{31} \\
    \hat{A}_{12} & \hat{A}_{22} & \hat{A}_{32} \\
    \hat{A}_{13} & \hat{A}_{23} & \hat{A}_{33}
\end{matrix}\right]
$$
