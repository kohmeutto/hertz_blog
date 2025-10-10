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

### 2. 정의

연산자 $\hat{A}$에 대하여, 0이 아닌 벡터 $|\lambda\rangle$와 스칼라 $\lambda$가 다음의 **고유값 방정식(eigenvalue equation)** 을 만족할 때, $|\lambda\rangle$를 $\hat{A}$의 **고유벡터(Eigenvector)**, $\lambda$를 **고유값(Eigenvalue)** 이라고 한다.

$$
\hat{A}|\lambda\rangle = \lambda|\lambda\rangle
$$

---

### 3. 특성 방정식과 고유값

**(1) 특성 방정식**

고유값 방정식을 변형하면 $(\hat{A} - \lambda \hat{I})|v\rangle = 0$ 이 된다. 0이 아닌 고유벡터 해가 존재하려면, 행렬 $(\hat{A} - \lambda \hat{I})$의 행렬식이 0이어야 한다. 이로부터 **특성 방정식(characteristic equation)** 을 얻는다.

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

### 4. 고유벡터의 선형독립

**고유값이 다르면, 각 고유값에 해당하는 고유벡터는 선형독립이다.** 단, 고유값이 같으면, 같은 고유값에 대한 고유벡터는 선형독립이 아닐 수 있다.

proof)

증명의 핵심 아이디어는 특정 고유벡터 $|lambda_j\rangle$를 제외한 **나머지 모든 고유벡터들을 정확히 0으로 만드는 '필터' 연산자**를 대수적으로 구성하는 것이다. 이 필터를 통과시키면 오직 우리가 목표로 하는 $|\lambda_j\rangle$에 대한 항만 살아남게 되어, 그 계수가 반드시 0임을 보일 수 있다.

**(1) 일반적인 선형 결합 설정**

먼저, 고유값 $\lambda_i$에 대응하는 고유벡터(고유켓) $|\lambda_i\rangle$의 일반적인 선형 결합이 0이 된다고 설정한다. 아래 식은 이산적인 합(summation)과 연속적인 적분(integral)을 모두 대표하는 일반적인 표현이다.

$$
\sum_i c_i |\lambda_i\rangle = |0\rangle
$$

만약 기저가 연속적이라면, 위 식은 $\int d\lambda \, c(\lambda) |\lambda\rangle = |0\rangle$ 의 형태로 생각할 수 있다. 증명의 논리는 동일하게 적용된다.

최종 목표는 모든 계수 $c_i$가 (또는 함수 $c(\lambda)$가) 반드시 0임을 보이는 것이다.

**(2) '선택적 제거 필터' 연산자 구성**

수많은 고유벡터 중에서, 검증하고자 하는 특정 고유벡터 $|v_j\rangle$ 하나만 남기고 나머지는 모두 제거하는 필터 연산자 $P_j$를 다음과 같이 정의한다.

$$
P_j \equiv \prod_{i \neq j} (\hat{A} - \lambda_i \hat{I})
$$

이 연산자는 $(\hat{A}-\lambda_1\hat{I})$, $(\hat{A}-\lambda_2\hat{I})$, ... 와 같은 항들의 곱으로 이루어져 있다. 가장 중요한 점은, **오직 $(\hat{A}-\lambda_j\hat{I})$ 항만 의도적으로 제외하고** 곱했다는 것이다.

**(3) 필터의 작동 방식**

이 필터 $P_j$가 임의의 고유벡터 $|v_m\rangle$에 어떻게 작용하는지 확인해 보자.

> **CASE 1** : 제거 대상 벡터 ($m \neq j$)

 필터 $P_j$의 곱셈 안에는 $(\hat{A}-\lambda_m\hat{I})$ 항이 반드시 포함되어 있다. 따라서,
    
$$
P_j |v_m\rangle = \left( \prod_{i \neq j, m} (\hat{A}-\lambda_i\hat{I}) \right) (\hat{A}-\lambda_m\hat{I}) |v_m\rangle
$$

여기서 $(\hat{A}-\lambda_m\hat{I})|v_m\rangle = \hat{A}|v_m\rangle - \lambda_m|v_m\rangle = \lambda_m|v_m\rangle - \lambda_m|v_m\rangle = |0\rangle$ 이므로,

$$
P_j |lambda_m\rangle = |0\rangle \quad (\text{for } m \neq j)
$$

즉, 이 필터는 목표인 $|\lambda_j\rangle$를 제외한 **모든 다른 고유벡터를 정확히 0으로 소멸시킨다.**

> **CASE 2: 살아남는 벡터 ($m = j$)**

필터 $P_j$에는 $(\hat{A}-\lambda_j\hat{I})$ 항이 없으므로, $|lambda_j\rangle$는 0이 되지 않고 살아남는다.
    
$$
P_j |\lambda_j\rangle = \left( \prod_{i \neq j} (\hat{A}-\lambda_i\hat{I}) \right) |\lambda_j\rangle = \left( \prod_{i \neq j} (\lambda_j-\lambda_i) \right) |\lambda_j\rangle
$$

모든 고유값 $\lambda_i$는 $\lambda_j$와 다르므로, 괄호 안의 스칼라 값은 **0이 아니다.**

**(4) 필터를 적용하여 증명 완료**

이제 처음 설정했던 선형 결합 식 $\sum_i c_i |\lambda_i\rangle = |0\rangle$ 의 양변에 우리가 만든 필터 $P_j$를 적용한다.

$$
P_j \left( \sum_i c_i |\lambda_i\rangle \right) = P_j|0\rangle
$$
$$
\sum_i c_i (P_j|\lambda_i\rangle) = |0\rangle
$$

필터의 작동 방식에 의해, $i \neq j$인 모든 항 $(P_j|\lambda_i\rangle)$은 0이 되어 사라지고, 오직 $i=j$인 항만 살아남는다.

$$
c_j (P_j |v_j\rangle) = |0\rangle
$$

위에서 계산한 **CASE 2**의 결과를 대입하면,

$$
c_j \underbrace{\left( \prod_{i \neq j} (\lambda_j-\lambda_i) \right)}_{\text{0이 아닌 스칼라}} \underbrace{|v_j\rangle}_{\text{0이 아닌 벡터}} = |0\rangle
$$

이 등식이 성립하려면, 세 항의 곱이 0이 되어야 한다. 하지만 스칼라 부분과 벡터 부분은 0이 아니므로, 유일한 가능성은 계수 **$c_j=0$** 이어야 한다는 것이다.

---

### 5. 고유벡터의 공간, 열공간과의 관계

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