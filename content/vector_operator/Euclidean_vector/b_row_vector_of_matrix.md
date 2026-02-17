+++
title = "(b) Row vector of matrix"
weight = 10
+++

---

### 1. 행렬연산의 행벡터는 내적 연산의 집합이다.

- 행렬에서 행벡터는 **$v_{i,:}$** 와 같이 표현한다.
- 행렬에서 열벡터는 **$v_{:,j}$** 와 같이 표현한다.
- 일반적인 벡터는 열벡터 이며, **$x_{j}$** 와 같이 표현한다. 

행렬연산의 행벡터에 대한 **$v_{i,:}\cdot$** 는 벡터 **$x_{j}$** 대한 각각의 **내적 연산자**라고 볼 수 있다.

$$
\begin{bmatrix}
    y_{1} \\ y_{2} \\ y_{3}
\end{bmatrix}
=\begin{bmatrix}
    v_{11} & v_{12} & v_{12} \\
    v_{21} & v_{22} & v_{23} \\
    v_{31} & v_{32} & v_{33}
\end{bmatrix}
\begin{bmatrix}
    x_{1} \\ x_{2} \\ x_{3}
\end{bmatrix}=\begin{bmatrix}
    v_{1,:}\cdot x_{j} \\
    v_{2,:}\cdot x_{j} \\
    v_{3,:}\cdot x_{j}
\end{bmatrix}
$$

---

### 2. 적분변환은 행렬연산에 대응된다.

$$
\left(Tf\right)\left(v\right)=\int_{u_1}^{u_2}du\left\lbrack K\left(v,u\right)f\left(u\right)\right\rbrack
$$

위를 행렬 연산과 비교해 보면,

- **커널함수 K는 행렬과 대응되며,**
- **함수 f는 벡터에 대응된다.**

아래와 같이 라플라스 변환과 대응해 보면, 이해가 쉽다.

$$
{L}\left\lbrace f\left(t\right)\right\rbrace\left(s\right)=\int_0^{\infty}dt\left[ e^{-st}\cdot f\left(t\right)\right]
$$

$$
\begin{bmatrix}
    s_1:A_{1,:}\cdot v_{j} \\
    s_2:A_{2,:}\cdot v_{j} \\
    s_3:A_{3,:}\cdot v_{j} \\
    s_4:A_{4,:}\cdot v_{j} \\
    s_5:A_{5,:}\cdot v_{j}
\end{bmatrix}
=\begin{bmatrix}
    s_1: & A_{11} & A_{12} & A_{13} & A_{14} & A_{15} \\
    s_2: & A_{21} & A_{22} & A_{23} & A_{24} & A_{25} \\
    s_3: & A_{31} & A_{32} & A_{33} & A_{34} & A_{35} \\
    s_4: & A_{41} & A_{42} & A_{43} & A_{44} & A_{45} \\
    s_5: & A_{51} & A_{52} & A_{53} & A_{54} & A_{55}
\end{bmatrix}
\begin{bmatrix}
    v_1 \\ v_2 \\ v_3 \\ v_4 \\ v_5
\end{bmatrix}
$$

---

[적분변환론(1부)](https://www.youtube.com/watch?v=Du9KGqOwaQM)

[푸리에 변환과 라플라스 변환(Fourier Transform and Laplace Transform) 차이점 : 네이버 블로그](https://m.blog.naver.com/jjz0426/220864334042)

[Integral transform - Wikipedia](https://en.wikipedia.org/wiki/Integral_transform)