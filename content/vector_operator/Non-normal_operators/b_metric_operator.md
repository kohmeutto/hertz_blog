+++
title = "(b) Metric Operator"
weight = 1
+++

---

### 1. 비정규 공간과 쌍대 기저 (Bi-dual Basis)

정규성(Normality)을 상실한 비정규 연산자 $\hat{A}$의 우측 고유벡터 집합 $\{|\lambda_n\rangle\}$은 유클리드 내적 공간 하에서 상호 직교하지 않는다($\langle \lambda_m | \lambda_n \rangle \neq \delta_{mn}$). 이 비직교 공간에서 기저의 완비성(Completeness)을 확보하기 위하여, 우측 고유벡터와 양방향 직교성(Bi-orthogonality)을 맺는 쌍대 공간(Dual space)의 좌측 고유벡터 집합, 즉 쌍대 기저(Bi-dual basis) $\{\langle \lambda^i|\}$를 이미보았다. 이 특성을 다시 정리한다. 

$$
\langle \lambda^i | \lambda_j \rangle = \delta^i_j, \quad \langle \lambda^d | \lambda' \rangle = \delta(\lambda - \lambda')
$$

이 양방향 직교성에 의하여 항등 연산자 $\hat{I}$는 다음과 같이 사영 연산자의 총합으로 전개된다.

$$
\hat{I} = \sum_i |\lambda_i\rangle \langle \lambda^i| = \sum_i |\lambda^i\rangle \langle \lambda_i|,\quad\hat{I} = \int d\lambda \, |\lambda\rangle \langle \lambda^d| = \int d\lambda \, |\lambda^d\rangle \langle \lambda|$$

---

### 2. 계량 연산자 $\hat{M}$의 대수적 실체와 스펙트럼 분해

**1) 계량 연산자 $\hat{M}$의 정의**

비정규 공간의 기하학적 왜곡을 보정하는 계량 연산자 $\hat{M}$은 외부에서 임의로 주어지는 가중치 행렬이 아니다. 이는 시스템의 쌍대 기저를 매개로 하여 대수적으로 고유하게 유도되는 **내재적 정규화 텐서(Normalizing tensor)** 이다. 쌍대 사상 관계에 의해, 쌍대 브라 기저 $\langle \lambda^i|$는 우측 고유벡터에 $\hat{M}$이 작용하여 변환된 상태로 정의된다.

$$
\langle \lambda^i | = \langle \lambda_i | \hat{M}\iff |\lambda^i\rangle = \hat{M} |\lambda_i\rangle
$$

$$
\langle \lambda^d | = \langle \lambda | \hat{M}\iff |\lambda^d\rangle = \hat{M} |\lambda\rangle
$$

**2) 역계량 연산자 $\hat{M}^{-1}$의 분해**

$$
\hat{M}^{-1} = \sum_j |\lambda_j\rangle \langle \lambda_j|,\quad\hat{M}^{-1} = \int d\lambda \, |\lambda\rangle \langle \lambda|
$$

proof)

쌍대 사상식의 양변 우측에 역연산자 $\hat{M}^{-1}$을 결합하여 $\langle \lambda^i | \hat{M}^{-1} = \langle \lambda_i |$ 및 $\hat{M}^{-1} |\lambda^i\rangle = |\lambda_i\rangle$를 도출한다. 항등 연산자의 완비성 식의 좌측에 $\hat{M}^{-1}$을 곱하여 전개한다.

$$
\hat{M}^{-1} = \hat{M}^{-1} \hat{I} = \hat{M}^{-1} \left( \sum_j |\lambda^j\rangle \langle \lambda_j| \right) = \sum_j (\hat{M}^{-1}|\lambda^j\rangle) \langle \lambda_j|
$$

유도된 관계식을 대입하면, 역계량 연산자 $\hat{M}^{-1}$은 우측 고유벡터들의 순수 외적 합으로 확정된다.

$$
\hat{M}^{-1} = \sum_j |\lambda_j\rangle \langle \lambda_j|
$$

**3) 계량 연산자 $\hat{M}$의 분해**

$$
\hat{M} = \sum_i |\lambda^i\rangle \langle \lambda^i|,\quad\hat{M} = \int d\lambda \, |\lambda^d\rangle \langle \lambda^d|
$$

proof)

동일한 방식으로 항등 연산자의 좌측에 $\hat{M}$을 곱하여 전개한다.

$$
\hat{M} = \hat{M} \hat{I} = \hat{M} \left( \sum_i |\lambda_i\rangle \langle \lambda^i| \right) = \sum_i (\hat{M}|\lambda_i\rangle) \langle \lambda^i|
$$

쌍대 켓 벡터의 관계식을 대입하면, 계량 연산자 $\hat{M}$은 쌍대 기저 벡터들의 순수 외적 합으로 확정된다.

$$
\hat{M} = \sum_i |\lambda^i\rangle \langle \lambda^i|
$$

---

## 3. 대수적 정합성과 정규직교성의 회복

**1) 도출된 두 연산자의 대수적 가역성을 검증**

$$
\hat{M} \hat{M}^{-1} = \left( \sum_i |\lambda^i\rangle \langle \lambda^i| \right) \left( \sum_j |\lambda_j\rangle \langle \lambda_j| \right) = \sum_i \sum_j |\lambda^i\rangle \langle \lambda^i | \lambda_j \rangle \langle \lambda_j|
$$

$$
= \sum_i \sum_j |\lambda^i\rangle \delta^i_j \langle \lambda_j| = \sum_i |\lambda^i\rangle \langle \lambda_i| = \hat{I}
$$

**2) 정규직교성의 회복**

가역성이 보장된 양의 정부호 허미션 연산자 $\hat{M}$을 이용하여 새로운 내적 체계인 $\hat{M}$-내적($\langle \phi | \psi \rangle_{\hat{M}} \equiv \langle \phi | \hat{M} | \psi \rangle$)을 정의한다. 이를 통해 유클리드 공간에서 비직교했던 우측 고유벡터들은 $\hat{M}$-내적 공간 내에서 완벽한 정규직교성(Orthonormality)을 회복하게 된다.

$$
\langle \lambda_m | \lambda_n \rangle_{\hat{M}}
= \langle \lambda_m | \hat{M} | \lambda_n \rangle = \langle \lambda_m | \left( \sum_i |\lambda^i\rangle \langle \lambda^i| \right) | \lambda_n \rangle
= \sum_i \langle \lambda_m | \lambda^i \rangle \langle \lambda^i | \lambda_n \rangle
$$

$$
= \sum_i \delta_{mi} \delta^i_n = \delta_{mn}
$$