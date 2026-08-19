+++
title = "(b) Dilation"
weight = 60
+++

---

## 1. 팽창 연산자 (Dilation Operator)

**1) 정의**

정규 연산자($[\hat{D}, \hat{D}^\dagger] = 0$) 중에서, 임의의 상태 벡터에 작용했을 때 그 벡터의 노름을 감소시키지 않는 연산자를 **팽창 (Dilation) 연산자**라고 한다.

$$
\|\hat{D}\psi\| \ge \|\psi\|
$$

이는 연산자 노름의 하한이 최소 1 이상임을 의미한다.

**2) 물리적 의미**

수축 연산자가 에너지 소산을 나타낸다면, 팽창 연산자는 외부로부터 시스템 내부로 에너지가 유입되거나 신호가 증폭(Gain)되는 능동적인 열린 계를 기술한다. 가역 조건이 보장될 때 두 연산자는 서로 역연산자($\hat{D} = \hat{T}^{-1}$) 관계를 형성한다.

---

## 2. 고유값의 위치

$\hat{D}$의 모든 고유값 $\lambda$의 절댓값은 1 이상이며, 복소 평면 상에서 닫힌 단위 원판의 외부 또는 그 경계에 구속된다.

$$
|\lambda| \ge 1
$$

proof)

연산자 $\hat{D}$의 고유값 $\lambda$와 영벡터가 아닌 고유벡터 $|\lambda\rangle$에 대하여 다음의 고유방정식이 성립한다.

$$
\hat{D}|\lambda\rangle = \lambda|\lambda\rangle
$$

위 식의 양변에 표준 노름을 취하면, 스칼라 값인 고유값은 절댓값 기호와 함께 분리된다.

$$
\|\hat{D}\lambda\| = \|\lambda\lambda\| = |\lambda| \|\lambda\|
$$

팽창 연산자의 정의 부등식인 $\|\hat{D}\psi\| \ge \|\psi\|$의 변수 $\psi$ 자리에 고유벡터 $|\lambda\rangle$를 대입한다.

$$
\|\hat{D}\lambda\| \ge \|\lambda\|
$$

좌변에 앞서 유도한 노름 분해식을 대입하여 정리한다.

$$
|\lambda| \|\lambda\| \ge \|\lambda\|
$$

고유벡터의 정의에 따라 $\|\lambda\| \neq 0$이므로, 양변을 고유벡터의 노름으로 나누면 다음 부등식이 도출된다.

$$
|\lambda| \ge 1
$$

---

## 3. 리 대수 생성자 $\hat{Z}$와 허미션 성분 분해

정규 $\hat{I}$-팽창 연산자 $\hat{D}$는 복소 우반평면에 고유값을 가지는 정규 연산자 $\hat{Z}$의 지수 사상으로 표현되며, 이는 두 개의 가환하는 허미션 연산자의 대수적 결합으로 고유하게 분해된다.

$$
\hat{D} = e^{\hat{Z}} \quad \text{where} \quad \hat{Z} = \hat{H}_R + i\hat{H}_I \quad ([\hat{H}_R, \hat{H}_I] = 0)
$$

proof)

정규 연산자 $\hat{D}$는 스펙트럼 정리에 의해 다음과 같이 정규직교 고유기저와 고유값으로 대각 분해된다.

$$
\hat{D} = \sum_n \lambda_n |\lambda_n\rangle \langle \lambda_n|
$$

단위 원판 외부 구속 조건($|\lambda_n| \ge 1$)을 만족하는 고유값 $\lambda_n$을 복소 지수 형태인 $\lambda_n = e^{Z_n}$으로 사상한다. 복소수 고유값 $Z_n$을 실수부와 허수부로 분리하여 $Z_n = X_n + iY_n$ ($X_n, Y_n \in \mathbb{R}$)로 두면 다음 관계가 성립한다.

$$
|\lambda_n| = |e^{Z_n}| = |e^{X_n + iY_n}| = e^{X_n} |e^{iY_n}| = e^{X_n}
$$

부등식 $|\lambda_n| \ge 1$에 이를 대입하면 $e^{X_n} \ge 1$이 되며, 지수 함수의 단조 증가성에 의해 실수부의 영역이 다음과 같이 확정된다.

$$
X_n \ge 0 \implies \text{Re}(Z_n) \ge 0
$$

생성자 고유값 $Z_n$은 복소 우반평면(Right half-plane)에 존재해야 한다. 지수 함수의 매클로린 급수 정의를 정규직교 고유기저 전개식에 대입한다.

$$
\hat{D} = \sum_n e^{Z_n} |\lambda_n\rangle \langle \lambda_n| = \sum_n \left( \sum_{k=0}^{\infty} \frac{Z_n^k}{k!} \right) |\lambda_n\rangle \langle \lambda_n|
$$

새로운 정규 연산자 $\hat{Z}$를 다음과 같이 정의한다.

$$
\hat{Z} := \sum_n Z_n |\lambda_n\rangle \langle \lambda_n|
$$

기저의 정규직교성에 의해 $k$차 멱연산은 고유값의 거듭제곱으로 전개되므로, 합산 순서의 전환을 통해 다음 사상이 성립한다.

$$
e^{\hat{Z}} = \sum_{k=0}^{\infty} \frac{\hat{Z}^k}{k!} = \sum_n e^{Z_n} |\lambda_n\rangle \langle \lambda_n| = \hat{D}
$$

이제 생성자 연산자 $\hat{Z}$를 허미션 성분과 반-허미션 성분으로 분해하는 카테시안 분해를 적용한다.

$$
\hat{Z} = \frac{\hat{Z} + \hat{Z}^\dagger}{2} + \frac{\hat{Z} - \hat{Z}^\dagger}{2} = \frac{\hat{Z} + \hat{Z}^\dagger}{2} + i \left( \frac{\hat{Z} - \hat{Z}^\dagger}{2i} \right) \equiv \hat{H}_R + i\hat{H}_I
$$

여기서 정의된 두 연산자 $\hat{H}_R$과 $\hat{H}_I$의 허미션 수반을 각각 계산한다.

$$
\hat{H}_R^\dagger = \left( \frac{\hat{Z} + \hat{Z}^\dagger}{2} \right)^\dagger = \frac{\hat{Z}^\dagger + \hat{Z}}{2} = \hat{H}_R
$$

$$
\hat{H}_I^\dagger = \left( \frac{\hat{Z} - \hat{Z}^\dagger}{2i} \right)^\dagger = \frac{\hat{Z}^\dagger - \hat{Z}}{-2i} = \frac{\hat{Z} - \hat{Z}^\dagger}{2i} = \hat{H}_I
$$

$\hat{H}_R$과 $\hat{H}_I$는 모두 허미션 연산자이다. 이들의 스펙트럼 분해 형식은 원래 고유값의 실수부와 허수부를 고유값으로 가짐이 유도된다.

$$
\hat{H}_R = \sum_n X_n |\lambda_n\rangle \langle \lambda_n|, \quad \hat{H}_I = \sum_n Y_n |\lambda_n\rangle \langle \lambda_n|
$$

동일한 고유기저를 공유하므로 두 허미션 연산자는 가환한다.

$$
[\hat{H}_R, \hat{H}_I] = 0
$$

스펙트럼 구속 조건에 의해 $X_n \ge 0$이므로, 허미션 연산자 $\hat{H}_R$은 양의 반정부호(Positive semi-definite) 연산자이다.

$$
\hat{H}_R \ge 0
$$

결론적으로 생성자 $\hat{Z}$는 시스템의 증폭을 제어하는 양의 허미션 연산자 $\hat{H}_R$과 위상 회전을 제어하는 허미션 연산자 $\hat{H}_I$의 결합으로 분리된다.

---

## 4. 스펙트럼의 기하학적 대응

생성자 $\hat{Z}$를 구성하는 두 허미션 연산자의 고유값 성분과 팽창 연산자 $\hat{D}$의 고유값 사이의 기하학적 매칭 관계는 다음과 같다.

| 생성자 고유값 실수부 ($X_n$) | 생성자 고유값 허수부 ($Y_n$) | 팽창 연산자 고유값 ($\lambda_n$) | 시스템 상태 |
| :--- | :--- | :--- | :--- |
| $X_n = 0$ | $Y_n \in \mathbb{R}$ | $|\lambda_n| = 1$ | 순수 회전 (유니타리 보존 상태) |
| $X_n > 0$ | $Y_n = 0$ | $\lambda_n > 1$ | 순수 증폭 (무회전 증폭 상태) |
| $X_n > 0$ | $Y_n \in \mathbb{R}$ | $|\lambda_n| > 1$ | 증폭 진동 (일반 개방계 증폭 상태) |