+++
title = "(b) Matrix"
weight = 5
+++

---

### 1. Matrix

행렬은 아래와 같이 표현할 수 있다.

$$
A
=\begin{bmatrix}
    A_{11} & A_{12} & A_{13} & A_{14} & A_{15} \\
    A_{21} & A_{22} & A_{23} & A_{24} & A_{25} \\
    A_{31} & A_{32} & A_{33} & A_{34} & A_{35} \\
    A_{41} & A_{42} & A_{43} & A_{44} & A_{45} \\
    A_{51} & A_{52} & A_{53} & A_{54} & A_{55}
\end{bmatrix}
$$

---

### 2. Matrix operation

행렬 연산은 아래와 같이 표현할 수 있다.

$$
A\vec{u}
=\begin{bmatrix}
    A_{11} & A_{12} & A_{13} & A_{14} & A_{15} \\
    A_{21} & A_{22} & A_{23} & A_{24} & A_{25} \\
    A_{31} & A_{32} & A_{33} & A_{34} & A_{35} \\
    A_{41} & A_{42} & A_{43} & A_{44} & A_{45} \\
    A_{51} & A_{52} & A_{53} & A_{54} & A_{55}
\end{bmatrix}
\begin{bmatrix}
    u_1 \\ u_2 \\ u_3 \\ u_4 \\ u_5
\end{bmatrix}
$$

$$
=u_1\begin{bmatrix}
    A_{11} \\ A_{21} \\ A_{31} \\ A_{41} \\ A_{51}
\end{bmatrix}
+u_2\begin{bmatrix}
    A_{12} \\ A_{22} \\ A_{32} \\ A_{42} \\ A_{52}
\end{bmatrix}
+u_3\begin{bmatrix}
    A_{13} \\ A_{23} \\ A_{33} \\ A_{43} \\ A_{53}
\end{bmatrix}
+u_4\begin{bmatrix}
    A_{14} \\ A_{24} \\ A_{34} \\ A_{44} \\ A_{54}
\end{bmatrix}
+u_5\begin{bmatrix}
    A_{15} \\ A_{25} \\ A_{35} \\ A_{45} \\ A_{55}
\end{bmatrix}
$$

---

### 3. Linearity of Matrix

$$
A\left(c_1\vec{u}_1+c_2\vec{u}_2\right) = c_1 A\vec{u}_1 + c_2 A\vec{u}_2
$$

따라서, 행렬은 선형성을 만족한다.