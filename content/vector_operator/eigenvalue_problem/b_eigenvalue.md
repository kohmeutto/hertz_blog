+++
title = "(b) Eigenvalue & Eigenvector"
weight = 2
+++

---

### 1. 고유값과 고유벡터 (Eigenvalues & Eigenvectors)

행렬(연산자) $\hat{A}$가 어떤 벡터 $|\lambda\rangle$에 작용할 때, 그 결과는 다음 세 가지 경우 중 하나로 나타난다.

- **소멸 (Annihilation)**: $\hat{A}|\lambda\rangle = 0$. 이 경우, $|\lambda\rangle$는 **고유값이 0인 고유벡터**이며, **영공간(Null Space)** 에 속한다.
- **스케일링 (Scaling)**: $\hat{A}|\lambda\rangle = \lambda|\lambda\rangle$ (단, $\lambda \neq 0$). 이 경우, $|\lambda\rangle$는 **0이 아닌 고유값을 가진 고유벡터**이다.
- **변환 (Transformation)**: $\hat{A}|\lambda\rangle = |w\rangle$ (단, $|w\rangle$는 $|\lambda\rangle$의 상수배가 아님). 이 경우, $|\lambda\rangle$는 **고유벡터가 아니다.**

영공간이 $\hat{A}|\lambda\rangle=0$이라는 특수한 경우를 다루었다면, 고유값 문제는 이를 더 일반적인 상황으로 확장한다. 즉, 변환에 의해 벡터가 '소멸'하는 것을 포함하여, '방향은 변하지 않고 크기만 변하는' 모든 경우를 찾는다. **특히, $\lambda \neq 0$ 경우, 연산자의 작용이 단순한 '스케일링'으로 나타나는 특별한 벡터(고유벡터)와 그때의 스케일 값(고유값)을 찾는 과정이다.**

---

### 2. 정의

연산자 $\hat{A}$에 대하여, 0이 아닌 벡터 $|\lambda\rangle$와 스칼라 $\lambda$가 다음의 **고유값 방정식(eigenvalue equation)** 을 만족할 때, $|\lambda\rangle$를 $\hat{A}$의 **고유벡터(Eigenvector)**, $\lambda$를 **고유값(Eigenvalue)** 이라고 한다.

$$
\hat{A}|\lambda\rangle = \lambda|\lambda\rangle
$$

---

### 3. 특성 방정식

고유값 방정식을 변형하면 $(\hat{A} - \lambda \hat{I})|\lambda\rangle = 0$ 이 된다. 0이 아닌 고유벡터 해가 존재하려면, 행렬 $(\hat{A} - \lambda \hat{I})$의 행렬식이 0이어야 한다. 이로부터 **특성 방정식(characteristic equation)** 을 얻는다. 이것을 사용하여 고유값을 구할 수 있다.

$$
\det(\hat{A} - \lambda \hat{I}) = 0
$$

---

### 4. 행렬식과 고유값

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

### 5. 역행렬 존재의 필요충분조건: 비영 고유값

역행렬이 존재하기 위한 수학적 필요충분조건은 행렬식(Determinant)이 0이 아니라는 것이다.

proof)

행렬식은 모든 고유값들의 곱으로 표현된다.

$$
\det(A) = \prod_{i=1}^n \lambda_i
$$

단 하나의 고유값이라도 0이 존재하면 $\det(A)=0$이 되어 역행렬이 존재하지 않으며, 모든 고유값이 0이 아닐 경우에만 $\det(A)\neq0$이 되어 역행렬이 존재한다. 영공간(Null space)의 관점에서는 고유값이 0인 고유벡터가 존재하지 않아야 자명한 영공간($\ker(A)=\{0\}$)을 가지게 되어 가역성이 보장된다.

---

### 6. 고유벡터의 선형독립

**고유값이 다르면, 각 고유값에 해당하는 고유벡터는 선형독립이다.** 단, 고유값이 같으면, 같은 고유값에 대한 고유벡터는 선형독립이 아닐 수 있다.

proof)

어떤 선형 연산자(operator) $\hat{A}$에 대해, 서로 다른 두 고유값 $\lambda_1$과 $\lambda_2$가 있고, 각각에 해당하는 고유벡터가 $|\lambda_1\rangle$과 $|\lambda_2\rangle$라고 가정한다. 고유값 방정식은 다음과 같이 표현할 수 있다. 여기서 $\lambda_1 \neq \lambda_2$ 이다.

$$\hat{A}|\lambda_1\rangle = \lambda_1 |\lambda_1\rangle$$
$$\hat{A}|\lambda_2\rangle = \lambda_2 |\lambda_2\rangle$$

이제 두 고유벡터가 **선형 종속이라고 가정**하고, 이 가정이 모순됨을 보여 선형 독립임을 증명한다. 선형 종속이라면, 두 벡터의 선형 결합을 0으로 만드는, 둘 다 0이 아닌 스칼라 계수 $c_1, c_2$가 존재해야 한다.

$$
c_1 |\lambda_1\rangle + c_2 |\lambda_2\rangle = 0
$$

이 식의 양변에 연산자 $\hat{A}$를 적용한다.

$$
c_1 \hat{A} |\lambda_1\rangle + c_2 \hat{A} |\lambda_2\rangle = 0
$$

고유값 방정식을 이용해 $A|\lambda_1\rangle$과 $A|\lambda_2\rangle$를 치환하면 다음과 같다.

$$
c_1 \lambda_1 |\lambda_1\rangle + c_2 \lambda_2 |\lambda_2\rangle = 0
$$

이제 처음 식에 $\lambda_1$을 곱해준다.

$$
c_1 \lambda_1 |\lambda_1\rangle + c_2 \lambda_1 |\lambda_2\rangle = 0
$$

이제 바로 위의 식을 빼면, $c_1 |\lambda_1\rangle$ 항이 소거된다.

$$c_2 (\lambda_2 - \lambda_1) |\lambda_2\rangle = 0$$

여기서 고유벡터 $|\lambda_2\rangle$는 0벡터가 될 수 없다 (정의상). 또한, 맨 처음 가정에서 고유값은 서로 다르다고 했으므로 $(\lambda_2 - \lambda_1) \neq 0$ 이다. 따라서 이 등식이 성립하려면 반드시 $c_2 = 0$ 이어야 한다. $c_2 = 0$ 이라는 결과를 다시 처음 식에 대입하면,

$$c_1 |\lambda_1\rangle + (0) |\lambda_2\rangle = 0 \implies c_1 |\lambda_1\rangle = 0$$

고유벡터 $|\lambda_1\rangle$ 역시 0벡터가 아니므로, $c_1 = 0$ 이어야 한다. 결론적으로 $c_1 = 0$이고 $c_2 = 0$이라는 결과가 나왔다. 이는 처음에 '둘 다 0이 아닌 계수 $c_1, c_2$가 존재한다'는 선형 종속의 가정과 모순된다.

---

### 7. 고유벡터의 공간, 열공간과의 관계

고유값이 0이 아닌($\lambda \neq 0$) 모든 고유벡터 $|\lambda\rangle$는 반드시 행렬 $A$의 **열공간(Column Space)** 에 속한다.

proof)

고유값 방정식 $\hat{A}|\lambda\rangle = \lambda|\lambda\rangle$에서, $\lambda \neq 0$ 이므로 양변을 나누면,

$$
|v\rangle = \frac{1}{\lambda} (\hat{A}|\lambda\rangle)
$$

우변의 $(\hat{A}|\lambda\rangle)$는 정의상 $\hat{A}$의 열공간에 속하므로, 그 상수배인 $|\lambda\rangle$ 역시 열공간에 속해야 한다.

---

**example1)** 허미션(대칭) 행렬

행렬 $A$의 고유값과 고유벡터를 구하시오.

$$A = \begin{bmatrix} 2 & 1 \\ 1 & 2 \end{bmatrix}$$

sol)

- 행렬식: $\det(A) = 3$
- 고유값: 특성 방정식 $\lambda^2 - 4\lambda + 3 = 0$ 으로부터, $\lambda_1=1, \lambda_2=3$.
- 고유값의 곱: $1 \times 3 = 3$. 행렬식과 일치함을 확인
- 고유벡터:
    - $\lambda_1=1$일 때: $|\lambda_1\rangle = \begin{bmatrix} 1 \\ -1 \end{bmatrix}^T$
    - $\lambda_2=3$일 때: $|\lambda_2\rangle = \begin{bmatrix} 1 \\ 1  \end{bmatrix}^T$

---

**example2)** 일반 행렬

행렬 $A$의 고유값과 고유벡터를 구하시오.

$$A = \begin{bmatrix}1 & 1 \\ -2 & 4 \end{bmatrix}$$

sol)

- 행렬식: $\det(A) = 6$.
- 고유값: 특성 방정식 $\lambda^2 - 5\lambda + 6 = 0$ 으로부터, $\lambda_1=2, \lambda_2=3$.
- 고유값의 곱: $2 \times 3 = 6$. 행렬식과 일치함을 확인.
- 고유벡터:
    - $\lambda_1=2$일 때: $|\lambda_1\rangle = \begin{bmatrix} 1 \\ 1 \end{bmatrix}^T$
    - $\lambda_2=3$일 때: $|\lambda_2\rangle = \begin{bmatrix} 1 \\ 2 \end{bmatrix}^T$

---

**example3)** det(A)=0 행렬

$$A = \begin{bmatrix}1 & 1 \\ 1 & 1 \end{bmatrix}$$

sol)

- 행렬식: $\det(A) = 0$.
- 고유값: 특성 방정식 $\lambda^2 - 2\lambda = 0$ 으로부터, $\lambda_1=0, \lambda_2=2$.
- 고유값의 곱: $0 \times 2 = 0$. 행렬식과 일치함을 확인.
- 고유벡터:
    - $\lambda_1=0$일 때: $|\lambda_1\rangle = \begin{bmatrix} 1 \\ -1 \end{bmatrix}^T$, 즉 영공간 이다.
    - $\lambda_2=2$일 때: $|\lambda_2\rangle = \begin{bmatrix} 1 \\ 1 \end{bmatrix}^T$