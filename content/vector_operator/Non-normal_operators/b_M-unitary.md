+++
title = "(b) M-unitary"
weight = 5
+++

---

### 1. $\hat{M}$-유니타리 연산자 ($\hat{M}$-Unitary Operator)

**1) 정의**

연산자 $\hat{U}$가 $\hat{M}$-내적 공간에서 자신의 $\hat{M}$-수반 연산자 $\hat{U}^\sharp$와의 곱을 통해 항등 연산자 $\hat{I}$를 도출할 때, 즉 다음의 관계를 만족할 때 이를 **$\hat{M}$-유니타리 연산자**라고 정의한다.

$$
\hat{U}^\sharp\hat{U} = \hat{U}\hat{U}^\sharp = \hat{I}
$$

위 정의식은 $\hat{M}$-유니타리 연산자의 $\hat{M}$-수반 연산자가 역연산자와 동일함($\hat{U}^\sharp = \hat{U}^{-1}$)을 의미한다. $\hat{M}$-수반 연산자의 정의($\hat{U}^\sharp = \hat{M}^{-1}\hat{U}^\dagger\hat{M}$)를 대입하면 다음 동치 조건이 도출된다.

$$
\hat{M}^{-1}\hat{U}^\dagger\hat{M}\hat{U} = \hat{I} \implies \hat{U}^\dagger\hat{M}\hat{U} = \hat{M}
$$

이 조건으로부터 $\hat{M}$-유니타리 연산자는 $\hat{M}$-교환자 가환성을 자명하게 충족함을 알 수 있다.

$$
[\hat{U}, \hat{U}^\sharp] = \hat{U}\hat{U}^\sharp - \hat{U}^\sharp\hat{U} = \hat{I} - \hat{I} = 0
$$

따라서 $\hat{M}$-유니타리 연산자는 $\hat{M}$-정규 연산자의 부분집합이며, $\hat{M}$-정규 연산자의 대수학적 불변량과 기저 완비성을 그대로 상속받는다. 

**2) 물리적 의미**

계량 연산자 $\hat{M}$이 도입된 비정규 공간에서 $\hat{M}$-유니타리 연산자는 시스템 상태 벡터의 $\hat{M}$-노름을 완벽하게 보존하는 모든 선형 변환을 대변한다. 이는 힐베르트 공간의 기하학적 구조가 $\hat{M}$에 의해 왜곡되었음에도 불구하고, 그 왜곡된 공간 내에서의 물리적 확률이나 에너지가 유실 없이 닫힌 계(Closed system)로서 보존됨을 의미한다.

---

### 2. $\hat{M}$-내적 및 노름의 보존

$\hat{M}$-유니타리 연산자는 선형 공간 내의 임의의 두 상태 벡터 간의 $\hat{M}$-내적 값을 변환 전후로 오차 없이 일정하게 보존한다.

$$
\langle \hat{U}\phi | \hat{U}\psi \rangle_M = \langle \phi | \psi \rangle_M
$$

proof)

임의의 두 상태 벡터 $|\phi\rangle, |\psi\rangle$를 상정한다. 변환이 적용된 켓 벡터 $\hat{U}|\psi\rangle$와 브라 벡터 $\langle \hat{U}\phi|$ 사이의 $\hat{M}$-내적식을 분해하여 전개한다.

$$
\langle \hat{U}\phi | \hat{U}\psi \rangle_M = \langle \hat{U}\phi | \hat{M} | \hat{U}\psi \rangle = \langle \phi | \hat{U}^\dagger \hat{M} \hat{U} | \psi \rangle
$$

$\hat{M}$-유니타리 연산자의 정의에서 도출된 동치 조건 $\hat{U}^\dagger\hat{M}\hat{U} = \hat{M}$을 내부 연산 영역에 대입한다.

$$
\langle \phi | \hat{M} | \psi \rangle = \langle \phi | \psi \rangle_M
$$

동일한 상태 벡터 $|\phi\rangle = |\psi\rangle$를 대입하면 $\hat{M}$-노름의 제곱 역시 변하지 않음이 증명된다.

$$
\|\hat{U}\psi\|_M^2 = \langle \hat{U}\psi | \hat{U}\psi \rangle_M = \langle \psi | \psi \rangle_M = \|\psi\|_M^2
$$

$$
\|\hat{U}\psi\|_M = \|\psi\|_M
$$

---

### 3. 고유값은 항상 복소 평면의 단위 원 위에 존재한다

$\hat{M}$-유니타리 연산자의 모든 고유값 $\lambda$의 절대값은 정확히 1이며, 복소 평면 상에서 단위 원(Unit circle)을 형성한다.

$$
|\lambda| = 1 \implies \lambda = e^{i\theta} \quad (\theta \in \mathbb{R})
$$

proof)

$\hat{M}$-유니타리 연산자 $\hat{U}$의 임의의 고유값 $\lambda$와 고유벡터 $|\lambda\rangle$에 대하여 고유방정식이 성립한다.

$$
\hat{U}|\lambda\rangle = \lambda|\lambda\rangle
$$

위 식에 의해 변환된 상태 벡터 $\hat{U}|\lambda\rangle$의 자체 $\hat{M}$-내적 공식을 전개한다.

$$
\langle \hat{U}\lambda | \hat{U}\lambda \rangle_M = \langle \lambda\lambda | \hat{M} | \lambda\lambda \rangle = \lambda^\ast \lambda \langle \lambda | \hat{M} | \lambda \rangle = |\lambda|^2 \langle \lambda | \lambda \rangle_M
$$

동시에 앞서 증명된 $\hat{M}$-내적 보존 법칙에 의하여 다음이 성립한다.

$$
\langle \hat{U}\lambda | \hat{U}\lambda \rangle_M = \langle \lambda | \lambda \rangle_M
$$

두 결과식을 등치시킨 후 이항하여 정리한다.

$$
|\lambda|^2 \langle \lambda | \lambda \rangle_M = \langle \lambda | \lambda \rangle_M
$$

$$
(|\lambda|^2 - 1) \langle \lambda | \lambda \rangle_M = 0
$$

고유벡터는 영벡터가 될 수 없고 $\hat{M}$은 양의 정부호이므로, $\langle \lambda|\lambda\rangle_M$는 결코 0이 아니다. 따라서 위 대수 방정식이 성립하기 위한 유일한 조건은 다음과 같다.

$$
|\lambda|^2 - 1 = 0 \implies |\lambda| = 1
$$

---

### 4. $\hat{M}$-허미션 연산자와의 대수적 지수 사상 관계

모든 $\hat{M}$-유니타리 연산자 $\hat{U}$는 $\hat{M}$-허미션 연산자 $\hat{H}$를 이용하여 복소 지수 함수 형식으로 표현될 수 있다.

$$
\hat{U} = e^{i\hat{H}} \quad \text{where} \quad \hat{H} = \hat{H}^\sharp
$$

proof)

$\hat{M}$-유니타리 연산자는 $\hat{M}$-정규 연산자이므로 스펙트럼 분해의 지배를 받는다. 특성 3의 고유값 조건($\lambda_n = e^{i\theta_n}$)과 특성 5의 브라 기저 일치성($\langle \lambda^n| = \langle \lambda_n|\hat{M}$)을 반영하여 정식화한다.

$$
\hat{U} = \sum_n e^{i\theta_n} |\lambda_n\rangle \langle \lambda_n| \hat{M}
$$

지수 함수의 매클로린 급수(Maclaurin series) 정의에 입각하여 연산자 $\hat{H}$를 대각 분해 형식으로 정의한다.

$$
\hat{H} := \sum_n \theta_n |\lambda_n\rangle \langle \lambda_n| \hat{M}
$$

매개변수 $\theta_n$이 모두 실수이므로, 이 연산자의 $\hat{M}$-수반을 취하면 고유값의 변질 없이 자기 자신과 동일해진다.

$$
\hat{H}^\sharp = \sum_n \theta_n^\ast |\lambda_n\rangle \langle \lambda_n| \hat{M} = \sum_n \theta_n |\lambda_n\rangle \langle \lambda_n| \hat{M} = \hat{H}
$$

따라서 선형 연산자 $\hat{H}$는 $\hat{M}$-허미션 연산자이다. 기저들의 직교성($\langle \lambda_n | \hat{M} | \lambda_m \rangle = \delta_{nm}$)에 의하여 멱연산 구조는 다음과 같이 적층된다.

$$
\hat{H}^k = \sum_n \theta_n^k |\lambda_n\rangle \langle \lambda_n| \hat{M}
$$

이 멱연산 전개식을 지수 함수의 거듭제곱 급수 정의식에 대입하고 합산의 순서를 상호 전환하여 연산한다.

$$
e^{i\hat{H}} = \sum_{k=0}^{\infty} \frac{i^k}{k!} \left( \sum_n \theta_n^k |\lambda_n\rangle \langle \lambda_n| \hat{M} \right)
$$

$$
e^{i\hat{H}} = \sum_n \left( \sum_{k=0}^{\infty} \frac{(i\theta_n)^k}{k!} \right) |\lambda_n\rangle \langle \lambda_n| \hat{M}
$$

괄호 내부의 무한 스칼라 급수는 스칼라 지수 함수 $e^{i\theta_n}$의 전개식과 일치하므로 다음과 같이 환원된다.

$$
e^{i\hat{H}} = \sum_n e^{i\theta_n} |\lambda_n\rangle \langle \lambda_n| \hat{M} = \hat{U}
$$