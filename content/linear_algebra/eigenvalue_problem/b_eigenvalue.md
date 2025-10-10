+++
title = "(b) Eigenvalue & Eigenvector"
weight = 2
+++

---

### 1. 고유값과 고유벡터 (Eigenvalues & Eigenvectors)

행렬(연산자) $\hat{A}$가 어떤 벡터 $|v\rangle$에 작용할 때, 그 결과는 다음 세 가지 경우 중 하나로 나타난다.

- **소멸 (Annihilation)**: $\hat{A}|v\rangle = 0$. 이 경우, $|v\rangle$는 **고유값이 0인 고유벡터**이며, **영공간(Null Space)** 에 속한다.
- **스케일링 (Scaling)**: $\hat{A}|v\rangle = \lambda|v\rangle$ (단, $\lambda \neq 0$). 이 경우, $|v\rangle$는 **0이 아닌 고유값을 가진 고유벡터**이다.
- **변환 (Transformation)**: $\hat{A}|v\rangle = |w\rangle$ (단, $|w\rangle$는 $|v\rangle$의 상수배가 아님). 이 경우, $|v\rangle$는 **고유벡터가 아니다.**

영공간이 $\hat{A}|v\rangle=0$이라는 특수한 경우를 다루었다면, 고유값 문제는 이를 더 일반적인 상황으로 확장한다. 즉, 변환에 의해 벡터가 '소멸'하는 것을 포함하여, '방향은 변하지 않고 크기만 변하는' 모든 경우를 찾는다. **특히, $\lambda \neq 0$ 경우, 연산자의 작용이 단순한 '스케일링'으로 나타나는 특별한 벡터(고유벡터)와 그때의 스케일 값(고유값)을 찾는 과정이다.**

---

### 2. 정의와 물리적 의미

**(1) 정의 (고유값과 고유벡터)**

연산자 $\hat{A}$에 대하여, 0이 아닌 벡터 $|v\rangle$와 스칼라 $\lambda$가 다음의 **고유값 방정식(eigenvalue equation)** 을 만족할 때, $|v\rangle$를 $\hat{A}$의 **고유벡터(Eigenvector)**, $\lambda$를 **고유값(Eigenvalue)** 이라고 한다.

$$
\hat{A}|v\rangle = \lambda|v\rangle
$$

**(2) 물리적 의미**

이 방정식은 양자역학에서 **측정(measurement)** 행위를 설명하는 근본적인 식이다. 연산자 $\hat{A}$가 허미션이면,

- **연산자 $\hat{A}$**: 측정 가능한 **물리량(Observable)**.
- **고유벡터 $|v\rangle$**: 안정적인 **고유 상태(Eigenstate)**.
- **고유값 $\lambda$**: 그 상태에서의 **측정값**.

---

### 3. 특성 방정식과 고유값

**(1) 특성 방정식**

고유값 방정식을 변형하면 $(\hat{A} - \lambda I)|v\rangle = 0$ 이 된다. 0이 아닌 고유벡터 해가 존재하려면, 행렬 $(\hat{A} - \lambda \hat{I})$의 행렬식이 0이어야 한다. 이로부터 **특성 방정식(characteristic equation)** 을 얻는다.

$$
\det(\hat{A} - \lambda \hat{I}) = 0
$$

**(2) 행렬식은 고유값의 곱이다.**

$\hat{A}$의 행렬식은, 모든 고유값(중복 포함)의 곱과 같다.

$$
\det(\hat{A}) = \prod_i \lambda_i
$$

proof)

특성 다항식 $p(\lambda) = \det(\hat{A} - \lambda \hat{I})$는 고유값을 근으로 가지므로,

$$
p(\lambda) = (\lambda_1 - \lambda)\cdots(\lambda_n - \lambda)
$$

이 항등식에 $\lambda=0$을 대입하면,

$$p(0)
=\det(\hat{A})
= \prod_i \lambda_i
$$

---

### 4. 고유벡터의 공간, 열공간과의 관계

고유값이 0이 아닌($\lambda \neq 0$) 모든 고유벡터 $|v\rangle$는 반드시 행렬 $A$의 **열공간(Column Space)** 에 속한다.

proof)

고유값 방정식 $\hat{A}|v\rangle = \lambda|v\rangle$에서, $\lambda \neq 0$ 이므로 양변을 나누면,

$$
|v\rangle = \frac{1}{\lambda} (\hat{A}|v\rangle)
$$

우변의 $(\hat{A}|v\rangle)$는 정의상 $\hat{A}$의 열공간에 속하므로, 그 상수배인 $|v\rangle$ 역시 열공간에 속해야 한다.

---

**example1)** 허미션(대칭) 행렬

행렬 $A$의 고유값과 고유벡터를 구하시오.

$$A = \begin{bmatrix} 2 & 1 \\ 1 & 2 \end{bmatrix}$$

sol)

- 행렬식: $\det(A) = 3$
- 고유값: 특성 방정식 $\lambda^2 - 4\lambda + 3 = 0$ 으로부터, $\lambda_1=1, \lambda_2=3$.
- 고유값의 곱: $1 \times 3 = 3$. 행렬식과 일치함을 확인
- 고유벡터:
    - $\lambda_1=1$일 때: $|v_1\rangle = \begin{bmatrix} 1 \\ -1 \end{bmatrix}^T$
    - $\lambda_2=3$일 때: $|v_2\rangle = \begin{bmatrix} 1 \\ 1  \end{bmatrix}^T$

---

**example2)** 일반 행렬

행렬 $A$의 고유값과 고유벡터를 구하시오.

$$A = \begin{bmatrix}1 & 1 \\ -2 & 4 \end{bmatrix}$$

sol)

- 행렬식: $\det(A) = 6$.
- 고유값: 특성 방정식 $\lambda^2 - 5\lambda + 6 = 0$ 으로부터, $\lambda_1=2, \lambda_2=3$.
- 고유값의 곱: $2 \times 3 = 6$. 행렬식과 일치함을 확인.
- 고유벡터:
    - $\lambda_1=2$일 때: $|v_1\rangle = \begin{bmatrix} 1 \\ 1 \end{bmatrix}^T$
    - $\lambda_2=3$일 때: $|v_2\rangle = \begin{bmatrix} 1 \\ 2 \end{bmatrix}^T$

---

**example3)** det(A)=0 행렬

$$A = \begin{bmatrix}1 & 1 \\ 1 & 1 \end{bmatrix}$$

sol)

- 행렬식: $\det(A) = 0$.
- 고유값: 특성 방정식 $\lambda^2 - 2\lambda = 0$ 으로부터, $\lambda_1=0, \lambda_2=2$.
- 고유값의 곱: $0 \times 2 = 0$. 행렬식과 일치함을 확인.
- 고유벡터:
    - $\lambda_1=0$일 때: $|v_1\rangle = \begin{bmatrix} 1 \\ -1 \end{bmatrix}^T$, 즉 영공간 이다.
    - $\lambda_2=2$일 때: $|v_2\rangle = \begin{bmatrix} 1 \\ 1 \end{bmatrix}^T$