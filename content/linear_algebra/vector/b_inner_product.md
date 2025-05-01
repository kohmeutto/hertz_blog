+++
title = "(b) Inner product"
weight = 8
+++

---

### 1. 벡터의 내적

벡터 $\vec{a}$, 벡터 $\vec{b}$의 내적은 다음과 같다.

첫번째는 일반 벡터 표기, 두번쨰는 Dirac notation, 세번쨰는 행렬 연산의 표기이다.

$$
\vec{a}\cdot\vec{b}=\langle a| b \rangle = [a]^T[b]
$$

---

### 2. 복소내적공간에서 벡터의 내적

벡터의 크기는 내적을 사용하여 구할 수 있다. **벡터의 크기는 실수 값 이므로, 복소 벡터의 크기를 정의하기 위해서**는, 켤레복소수(asterisk)를 취한다. 아래는 sufiix notation 이다.

$$
|\vec{a}|=\sqrt{a_{i}^{*}a_{i}}
$$

---

### 3. 복소내적공간에서 함수의 내적

$$
\langle f|g \rangle=\int_{a}^{b}dx\left[f\left(x\right)^{\ast}g\left(x\right)\right]
$$

함수의 내적을 적분으로 정의하는 이유는 **수학적 벡터를, 함수 공간으로 옮겼을 때, 벡터의 각 성분들은 정의역의 간격이 1인 함수의 값이라고 볼 수 있다.**

$$
\begin{bmatrix}
    a_1 \\ a_2 \\ a_3 \\ a_4 \\ a_5
\end{bmatrix}\cdot
\begin{bmatrix}
    b_1 \\ b_2 \\ b_3 \\ b_4 \\ b_5
\end{bmatrix}
=\operatorname{SUM}\left(\begin{bmatrix}
    a_1^{\ast}b_1\cdot1 \\
    a_2^{\ast}b_2\cdot1 \\
    a_3^{\ast}b_3\cdot1 \\
    a_4^{\ast}b_4\cdot1 \\
    a_5^{\ast}b_5\cdot1
\end{bmatrix}\right)
=a_jb_j
$$

함수의 간격이 $\triangle x$라고 할 경우,

$$
\begin{bmatrix}
    f\left(x_1\right) \\
    f\left(x_2\right) \\
    f\left(x_3\right) \\
    f\left(x_4\right) \\
    f\left(x_5\right) \\
    \vdots
\end{bmatrix}\cdot
\begin{bmatrix}
    g\left(x_1\right) \\
    g\left(x_2\right) \\
    g\left(x_3\right) \\
    g\left(x_4\right) \\
    g\left(x_5\right) \\
    \vdots
\end{bmatrix}
=\operatorname{SUM}\left(\begin{bmatrix}
    f\left(x_1\right)^{\ast}g\left(x_1\right)\triangle x \\
    f\left(x_2\right)^{\ast}g\left(x_2\right)\triangle x \\
    f\left(x_3\right)^{\ast}g\left(x_3\right)\triangle x \\
    f\left(x_4\right)^{\ast}g\left(x_4\right)\triangle x \\
    f\left(x_5\right)^{\ast}g\left(x_5\right)\triangle x \\
    \vdots
\end{bmatrix}\right)
=\int_{a}^{b}dx \left[f^{\ast}\left(x\right)g\left(x\right)\right]
$$