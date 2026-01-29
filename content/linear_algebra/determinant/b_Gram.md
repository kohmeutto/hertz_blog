+++
title = "(b) Gram"
weight = 3
+++

---

### 1. 그람(Gram) 행렬 & 행렬식

- 유한 열벡터의 독립 종속 판단: 행렬식 사용
- 함수 벡터의 독립 종속 판단: 론스키안 사용
- 무한 열벡터의 독립 종속 판단: **그람** 사용
- 또는 위 3가지의 벡터의 구분 없이 독립 종속 판단: **그람** 사용 

$$
G
=\begin{bmatrix}
\langle f_1|f_1\rangle & \langle f_1|f_2\rangle & \cdots & \langle f_1|f_n\rangle \\
\langle f_2|f_1\rangle & \langle f_2|f_2\rangle  & \cdots & \langle f_2|f_n\rangle \\
\vdots & \vdots & \ddots & \vdots \\
\langle f_n|f_1\rangle & \langle f_n|f_2\rangle  & \cdots & \langle f_n|f_n\rangle
\end{bmatrix}
$$

- 독립: $|G|\ne 0$
- 종속: $|G|= 0$

proof)

- 탄생: 그람 행렬과 행렬식은 19세기 덴마크의 수학자 **예르겐 페데르센 그람(Jørgen Pedersen Gram)** 에 의해 만들어졌다.
- 동기: 그람의 목표는 유클리드 기하학의 직관적인 개념인 **'길이', '각도', '부피'** 를 추상적인 벡터 공간과 함수 공간으로 일반화하는 것이다.


상태벡터가 2개 ($\|f_1\rangle$, $|f_2\rangle$)있다.이 두 벡터의 독립 종속 여부를 판단하기 위해 아래의 식을 만든다.

$$
c_1|f_1\rangle+c_2|f_2\rangle=0
$$

위 식의 양변에 서로의 벡터를 내적해 본다.

$$
c_1\langle f_1|f_1\rangle+c_2\langle f_1|f_2\rangle=0
$$

$$
c_1\langle f_2|f_1\rangle+c_2\langle f_2|f_2\rangle=0
$$

따라서, 다음과 같은 그람 행렬을 만들 수 있다.

$$
G
=\begin{bmatrix}
\langle f_1|f_1\rangle & \langle f_1|f_2\rangle \\
\langle f_2|f_1\rangle & \langle f_2|f_2\rangle  \\
\end{bmatrix}
$$

---

### 2. 행렬식의 의미

Gram 행렬의 Determinent는 초부피의 제곱이다.

$$
|G|=\text{(Volume)}^2
$$

proof)

먼저, Ket 벡터들을 성분으로 가지는 'Ket들의 행벡터' $R$를 정의한다.

$$
R
=\begin{bmatrix}
|f_1\rangle & |f_2\rangle & \cdots & |f_n\rangle
\end{bmatrix}
$$

슈퍼 행벡터 $R$의 $\dagger$는 아래와 같다.

$$
R^{\dagger}
=\begin{bmatrix}
\langle f_1| \\ \langle f_2| \\ \vdots \\ \langle f_n|
\end{bmatrix}
$$

따라서 그람 행렬은

$$
G=R^{\dagger}R
$$

determinent 를 구한다.

$$
|G|
=|R^{\dagger}||R|
=|R|^2
$$

$|R|$는 초월공간의 부피를 의미한다. 따라서, Gram 행렬의 Determinent는 초부피의 제곱이다.

$$
|G|=\text{(Volume)}^2
$$

---

### 3. 로랑 급수 기저의 독립

---

### 4. 푸리에 급수 기저의 독립