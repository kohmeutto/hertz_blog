+++
title = "(b) M-contraction"
weight = 6
+++

---

## 1. $\hat{M}$-수축 연산자 ($\hat{M}$-Contraction Operator)

**1) 정의**

$\hat{M}$-정규 연산자($[\hat{T}, \hat{T}^\sharp] = 0$) 중에서, 임의의 상태 벡터에 작용했을 때 그 벡터의 $\hat{M}$-노름을 증가시키지 않는 연산자를 **$\hat{M}$-수축 연산자**라고 정의한다.

$$
\|\hat{T}\psi\|_M \le \|\psi\|_M
$$

**2) 물리적 의미**

표준 힐베르트 공간의 계량이 $\hat{M}$으로 확장된 비정규 공간에서, 에너지가 소산되거나 시스템의 진폭이 감쇠하는 열린 계를 기술한다.

---

## 2. 고유값의 위치

$\hat{T}$의 모든 고유값 $\lambda$의 절댓값은 1 이하이며, 복소 평면 상에서 닫힌 단위 원판 내부에 구속된다.

$$
|\lambda| \le 1
$$

proof)

연산자 $\hat{T}$의 고유값 $\lambda$와 영벡터가 아닌 고유벡터 $|\lambda\rangle$에 대하여 고유방정식이 성립한다.

$$
\hat{T}|\lambda\rangle = \lambda|\lambda\rangle
$$

위 식의 양변에 $\hat{M}$-노름을 취하면, 스칼라 값인 고유값은 절댓값 기호와 함께 분리된다.

$$
\|\hat{T}\lambda\|_M = \|\lambda\lambda\|_M = |\lambda| \|\lambda\|_M
$$

$\hat{M}$-수축 연산자의 정의 부등식인 $\|\hat{T}\psi\|_M \le \|\psi\|_M$의 변수 $\psi$ 자리에 고유벡터 $|\lambda\rangle$를 대입한다.

$$
\|\hat{T}\lambda\|_M \le \|\lambda\|_M
$$

좌변에 앞서 유도한 노름 분해식을 대입하여 정리한다.

$$
|\lambda| \|\lambda\|_M \le \|\lambda\|_M
$$

고유벡터의 정의에 따라 $\|\lambda\|_M \neq 0$이므로, 양변을 고유벡터의 $\hat{M}$-노름으로 나누면 다음 부등식이 도출된다.

$$
|\lambda| \le 1
$$

---

## 3. 리 대수 생성자 $\hat{Z}$와 $\hat{M}$-허미션 성분 분해

$\hat{M}$-수축 연산자 $\hat{T}$는 복소 좌반평면에 고유값을 가지는 $\hat{M}$-정규 연산자 $\hat{Z}$의 지수 사상으로 표현되며, 이는 두 개의 가환하는 $\hat{M}$-허미션 연산자의 결합으로 분해된다.

$$
\hat{T} = e^{\hat{Z}} \quad \text{where} \quad \hat{Z} = \hat{H}_R + i\hat{H}_I \quad ([\hat{H}_R, \hat{H}_I] = 0)
$$

proof)

$\hat{M}$-정규 연산자 $\hat{T}$는 스펙트럼 정리에 의해 다음과 같이 대각 분해된다.

$$
\hat{T} = \sum_n \lambda_n |\lambda_n\rangle \langle \lambda_n| \hat{M}
$$

단위 원판 내부 구속 조건($|\lambda_n| \le 1$)을 만족하는 고유값 $\lambda_n$을 복소 지수 형태인 $\lambda_n = e^{Z_n}$으로 사상한다. 복소수 고유값 $Z_n$을 실수부와 허수부로 분리하여 $Z_n = X_n + iY_n$ ($X_n, Y_n \in \mathbb{R}$)로 두면 다음 관계가 성립한다.

$$
|\lambda_n| = |e^{Z_n}| = |e^{X_n + iY_n}| = e^{X_n} |e^{iY_n}| = e^{X_n}
$$

부등식 $|\lambda_n| \le 1$에 이를 대입하면 $e^{X_n} \le 1$이 되며, 지수 함수의 단조 증가성에 의해 실수부의 영역이 다음과 같이 확정된다.

$$
X_n \le 0 \implies \text{Re}(Z_n) \le 0
$$

생성자 고유값 $Z_n$은 복소 좌반평면에 존재해야 한다. 지수 함수의 매클로린 급수 정의를 고유기저 전개식에 대입한다.

$$
\hat{T} = \sum_n e^{Z_n} |\lambda_n\rangle \langle \lambda_n| \hat{M} = \sum_n \left( \sum_{k=0}^{\infty} \frac{Z_n^k}{k!} \right) |\lambda_n\rangle \langle \lambda_n| \hat{M}
$$

새로운 $\hat{M}$-정규 연산자 $\hat{Z}$를 다음과 같이 정의한다.

$$
\hat{Z} := \sum_n Z_n |\lambda_n\rangle \langle \lambda_n| \hat{M}
$$

기저의 $\hat{M}$-직교성에 의해 $k$차 멱연산은 고유값의 거듭제곱으로 전개되므로, 합산 순서의 전환을 통해 다음 사상이 성립한다.

$$
e^{\hat{Z}} = \sum_{k=0}^{\infty} \frac{\hat{Z}^k}{k!} = \sum_n e^{Z_n} |\lambda_n\rangle \langle \lambda_n| \hat{M} = \hat{T}
$$

생성자 연산자 $\hat{Z}$에 카테시안 분해를 적용한다. 여기서 수반 연산자는 $\hat{M}$-수반 연산자($\sharp$)를 사용한다.

$$
\hat{Z} = \frac{\hat{Z} + \hat{Z}^\sharp}{2} + \frac{\hat{Z} - \hat{Z}^\sharp}{2} = \frac{\hat{Z} + \hat{Z}^\sharp}{2} + i \left( \frac{\hat{Z} - \hat{Z}^\sharp}{2i} \right) \equiv \hat{H}_R + i\hat{H}_I
$$

정의된 두 연산자 $\hat{H}_R$과 $\hat{H}_I$의 $\hat{M}$-수반을 각각 계산한다.

$$
\hat{H}_R^\sharp = \left( \frac{\hat{Z} + \hat{Z}^\sharp}{2} \right)^\sharp = \frac{\hat{Z}^\sharp + \hat{Z}}{2} = \hat{H}_R
$$

$$
\hat{H}_I^\sharp = \left( \frac{\hat{Z} - \hat{Z}^\sharp}{2i} \right)^\sharp = \frac{\hat{Z}^\sharp - \hat{Z}}{-2i} = \frac{\hat{Z} - \hat{Z}^\sharp}{2i} = \hat{H}_I
$$

$\hat{H}_R$과 $\hat{H}_I$는 모두 $\hat{M}$-허미션 연산자이다. 이들의 스펙트럼 분해 형식은 원래 고유값의 실수부와 허수부를 고유값으로 가진다.

$$
\hat{H}_R = \sum_n X_n |\lambda_n\rangle \langle \lambda_n| \hat{M}, \quad \hat{H}_I = \sum_n Y_n |\lambda_n\rangle \langle \lambda_n| \hat{M}
$$

동일한 고유기저를 공유하므로 두 $\hat{M}$-허미션 연산자는 가환한다.

$$
[\hat{H}_R, \hat{H}_I] = 0
$$

스펙트럼 구속 조건에 의해 $X_n \le 0$이므로, $\hat{M}$-허미션 연산자 $\hat{H}_R$은 음의 반정부호 연산자이다.

$$
\hat{H}_R \le 0
$$

---

## 4. 스펙트럼의 기하학적 대응

| 생성자 고유값 실수부 ($X_n$) | 생성자 고유값 허수부 ($Y_n$) | 수축 연산자 고유값 ($\lambda_n$) | 시스템 상태 |
| :--- | :--- | :--- | :--- |
| $X_n = 0$ | $Y_n \in \mathbb{R}$ | $\vert\lambda_n\vert = 1$ | 순수 회전 ($\hat{M}$-유니타리 보존 상태) |
| $X_n < 0$ | $Y_n = 0$ | $0 < \lambda_n < 1$ | 순수 감쇠 (과감쇠 소산 상태) |
| $X_n < 0$ | $Y_n \in \mathbb{R}$ | $0 < \vert\lambda_n\vert < 1$ | 감쇠 진동 (일반 개방계 소산 상태) |