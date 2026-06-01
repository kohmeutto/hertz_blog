+++
title = "(b) Unitary"
weight = 4
+++

---

### 1. I-Unitary 연산자

**1) 정의**

연산자 $\hat{U}$ 가 자신의 허미션 켤레 $\hat{U}^\dagger$ 와 다음 관계를 만족할 때, 이를 **$\hat{I}$-유니타리 ($\hat{I}$-Unitary) 연산자** 라 한다.

$$
\hat{U}^\dagger\hat{U} = \hat{U}\hat{U}^\dagger = \hat{I}
$$

즉 $\hat{U}^\dagger = \hat{U}^{-1}$, 허미션 켤레가 역원과 같다. 이 조건이 정규 연산자의 조건 $[\hat{U}, \hat{U}^\dagger] = 0$ 을 자동으로 만족한다.

본 작용소가 표준 inner product (즉 metric operator 가 $\hat{I}$ 인 case) 의 기준에서 norm 을 보존하는 작용소이므로 $\hat{I}$-유니타리 라 부른다. 일반화된 metric ($\hat{G}$ 또는 $\hat{J}$) 의 기준에서의 유니타리 작용소가 별도 chapter 에서 다뤄진다.

**2) 물리적 의미**

$\hat{I}$-유니타리 연산자는 상태 벡터의 길이(norm), 즉 **확률을 보존** 하는 모든 물리적 변환을 나타낸다. 양자 시스템의 **시간 변화(time evolution)** 나 **기저 변환(change of basis)** 등은 반드시 $\hat{I}$-유니타리 연산자로 기술되어야 한다.

---

### 2. 고유값은 단위 원 위에 있다

$\hat{I}$-유니타리 연산자의 고유값은 모두 절댓값이 1 인 복소수이다. 복소 평면에서 단위 원 위에 위치한다.

$$
\sigma(\hat{U}) \subset \{e^{i\theta} : \theta \in \mathbb{R}\} = S^1
$$

proof)

$\hat{U}|v\rangle = \lambda|v\rangle$ 가정. 양변에 $\langle v|\hat{U}^\dagger$ 를 내적:

$$
\langle v|\hat{U}^\dagger\hat{U}|v\rangle = \lambda^*\lambda\,\langle v|v\rangle
$$

정의 $\hat{U}^\dagger\hat{U} = \hat{I}$ 에서 좌변이 $\langle v|v\rangle$. 따라서

$$
|\lambda|^2\,\langle v|v\rangle = \langle v|v\rangle
$$

$\langle v|v\rangle \neq 0$ 이므로 $|\lambda|^2 = 1$. 이를 만족하는 복소수는 $\lambda = e^{i\theta}$ ($\theta \in \mathbb{R}$) 의 형태.

---

### 3. 세 가지 정규 연산자의 통합

Hermitian, anti-Hermitian, $\hat{I}$-unitary 의 고유값 위치:

| 연산자 | 정의 | 고유값 위치 | 복소 평면 |
|---|---|---|---|
| Hermitian | $\hat{H}^\dagger = \hat{H}$ | $\lambda \in \mathbb{R}$ | 실수 직선 |
| Anti-Hermitian | $\hat{A}^\dagger = -\hat{A}$ | $\lambda \in i\mathbb{R}$ | 허수 축 |
| $\hat{I}$-Unitary | $\hat{U}^\dagger\hat{U} = \hat{I}$ | $\vert\lambda\vert = 1$ | 단위 원 |

복소 평면의 세 가지 특별한 부분 집합 — 실수 직선, 허수 축, 단위 원 — 이 세 가지 정규 연산자에 대응한다.

---

### 4. 기본 성질

**1) 서로 다른 고유값의 고유벡터 직교성**

$\hat{U}|v_n\rangle = \lambda_n|v_n\rangle, \hat{U}|v_m\rangle = \lambda_m|v_m\rangle, \lambda_n \neq \lambda_m$ 이면

$$
\langle v_n|v_m\rangle = 0
$$

b_normal_operators.md §3 의 특성 2 의 직접 적용. ($\hat{I}$-Unitary 가 정규 연산자이고, 표준 내적에서 듀얼 기저가 자연 켤레와 일치하므로 $\langle v^n| = \langle v_n|$.)

**2) 노름 보존**

임의의 두 벡터 $|v\rangle, |w\rangle$ 에 대해

$$
\langle\hat{U}v|\hat{U}w\rangle = \langle v|\hat{U}^\dagger\hat{U}|w\rangle = \langle v|\hat{I}|w\rangle = \langle v|w\rangle
$$

내적이 보존되며, 특히 노름 $\|\hat{U}v\| = \|v\|$ 가 보존된다.

**3) 정수 거듭제곱**

$\hat{U}^n$ 도 $\hat{I}$-유니타리이다 ($n$ 정수).

$$
(\hat{U}^n)^\dagger\,\hat{U}^n = (\hat{U}^\dagger)^n\,\hat{U}^n = \hat{I}^n = \hat{I}
$$

---

### 4. 허미션 연산자와의 대수적 지수 사상 관계

모든 유니타리 연산자 $\hat{U}$는 허미션 연산자 $\hat{H}$를 이용하여 복소 지수 함수 형식으로 유일하게 표현될 수 있다.

$$
\hat{U} = e^{i\hat{H}} \quad \text{where} \quad \hat{H} = \hat{H}^\dagger
$$

proof)

유니타리 연산자는 정규 연산자이므로 스펙트럼 분해 형식을 사용한다.

$$
\hat{U} = \sum_n e^{i\theta_n} |\lambda_n\rangle \langle \lambda_n|
$$

연산자에 작용하는 해석적 복소 함수를 거듭제곱 매클로린 급수(Maclaurin series) 정의에 입각하여 다음과 같이 무한 합의 형태로 전개한다.

$$
e^{i\hat{H}} = \sum_{k=0}^{\infty} \frac{i^k}{k!} \hat{H}^k
$$

여기서 선형 연산자 $\hat{H}$를 정규직교 고유기저 ${|\lambda_n\rangle}$와 고유값으로 실수 위상값인 $\theta_n$을 직접 부여하여 대각 분해 형식으로 정의한다.

$$
\hat{H} := \sum_n \theta_n |\lambda_n\rangle \langle \lambda_n|
$$

매개변수 $\theta_n$이 모두 실수이므로, 위 정의식에 허미션 수반을 취하면 고유값의 변질 없이 자기 자신과 동일해진다.

$$
\hat{H}^\dagger = \sum_n \theta_n^\ast |\lambda_n\rangle \langle \lambda_n| = \sum_n \theta_n |\lambda_n\rangle \langle \lambda_n| = \hat{H}
$$

따라서 선형 연산자 $\hat{H}$는 엄밀한 허미션 연산자이다. 기저들의 정규직교성($\langle \lambda_n | \lambda_m \rangle = \delta_{nm}$) 공리에 의하여, 연산자 $\hat{H}$의 $k$차 멱연산 구조는 각 고유값의 거듭제곱 형태로 적층된다.

$$
\hat{H}^k = \sum_n \theta_n^k |\lambda_n\rangle \langle \lambda_n|
$$

이 멱연산 전개식을 지수 함수의 거듭제곱 급수 정의식에 대입하고, 선형 결합의 대수적 교환 가능성에 따라 합산의 순서를 상호 전환하여 연산한다.

$$
e^{i\hat{H}} = \sum_{k=0}^{\infty} \frac{i^k}{k!} \left( \sum_n \theta_n^k |\lambda_n\rangle \langle \lambda_n| \right)
$$

$$
e^{i\hat{H}} = \sum_n \left( \sum_{k=0}^{\infty} \frac{(i\theta_n)^k}{k!} \right) |\lambda_n\rangle \langle \lambda_n|
$$

괄호 내부의 무한 스칼라 급수는 정확히 스칼라 지수 함수 $e^{i\theta_n}$의 테일러 전개식과 일치하므로,

$$
e^{i\hat{H}} = \sum_n e^{i\theta_n} |\lambda_n\rangle \langle \lambda_n| = \hat{U}
$$

---

### 6. 회전의 양과 측정 가능한 양의 동일성

$$
\hat{H} = \sum_n \lambda_n |v_n\rangle\langle v^n|, \quad \hat{U} = \sum_n e^{i\lambda_n} |v_n\rangle\langle v^n|
$$

두 식의 의미를 자세하게 살펴보자. 두 작용소가 같은 사영 $|v_n\rangle\langle v^n|$ 위에 자리잡혀 있다. 사영 부분이 동일하고, 사영에 곱해지는 스칼라가 한쪽에서 $\lambda_n$, 다른 쪽에서 $e^{i\lambda_n}$. 같은 실수 $\lambda_n$ 이 두 표현에 등장한다. 한 표현에서는 그대로, 다른 표현에서는 지수 안의 phase 각도로 표현된다.

같은 $\lambda_n$ 이 두 작용소에서 서로 다른 역할을 한다. $\hat{U}$ 에서는 회전의 양, $\hat{H}$ 에서는 측정값. **회전의 양 자체가 측정 가능한 양을 의미하는 것** 이다. 이것은 $\hat{H}$ 가 $\hat{U}$ 와 무관하게 외부에서 정의된 작용소가 아니다.
