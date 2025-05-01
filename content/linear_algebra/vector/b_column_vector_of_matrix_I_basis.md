+++
title = "(b) Column vector of matrix I - Basis"
weight = 6
+++

---

### 1. Matrix는 선형 변환된 열벡터 기저의 집합

행렬은 아래와 같이 표현할 수 있다.

$$
A
=\begin{bmatrix}
    A_{11} & A_{12} \\
    A_{21} & A_{22} 
\end{bmatrix}
$$

표준기저와의 연산은

$$
\begin{bmatrix}
    A_{11} \\ A_{12}
\end{bmatrix}
=\begin{bmatrix}
    A_{11} & A_{12} \\
    A_{21} & A_{22}
\end{bmatrix}
\begin{bmatrix}
    1 \\ 0
\end{bmatrix}
$$

$$
\begin{bmatrix}
    A_{21} \\ A_{22}
\end{bmatrix}
=\begin{bmatrix}
    A_{11} & A_{12} \\
    A_{21} & A_{22}
\end{bmatrix}
\begin{bmatrix}
    0 \\ 1
\end{bmatrix}
$$

따라서, **Matrix 는 선형 변환된 기저의 열벡터 집합이다.**

---

### 2. 행렬 연산은 선형 변환된 기저를 scaling 하고 더한 결과

행렬 연산은 아래와 같이 표현할 수 있다.

$$
A\vec{u}
=\begin{bmatrix}
    A_{11} & A_{12} \\
    A_{21} & A_{22} 
\end{bmatrix}
\begin{bmatrix}
    u_1 \\ u_2 
\end{bmatrix}
=u_1\begin{bmatrix}
    A_{11} \\ A_{21} 
\end{bmatrix}
+u_2\begin{bmatrix}
    A_{12} \\ A_{22} 
\end{bmatrix}
$$