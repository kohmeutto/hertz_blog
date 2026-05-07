+++
title = "(b) Function of operators"
weight = 2
+++

---

본 챕터는 단순히 연산자에 함수를 대입하는 기계적 요령을 넘어, **어떻게 스칼라 함수 $f(x)$를 연산자 함수 $f(\hat{A})$로 확장할 수 있는가**에 대한 수학적 정당성을 부여하는 것을 목표로 한다. 여기에는 **해석적 접근(Taylor Series)**, **대수적 접근(Spectral Decomposition)**, 그리고 가장 일반적인 **복소 해석적 접근(Cauchy Integral)** 세 가지 방법이 존재하며, 이들이 상호 일관됨을 증명한다.

---

## X.1 서론: 문제의 제기

스칼라 변수 $x \in \mathbb{C}$에 대한 함수 $f(x)$가 주어졌을 때(예: $e^x, \sin x, \sqrt{x}$), 선형 연산자 $\hat{A}$에 대해 $f(\hat{A})$를 정의하고자 한다.

단순히 $\hat{A}$가 행렬 표현 $A_{ij}$를 갖는다고 해서, 각 성분에 함수를 적용하는 것 즉, $[f(A)]_{ij} = f(A_{ij})$로 정의하는 것은 **수학적으로 오류**이다. 이는 기저(Basis)의 선택에 따라 결과가 달라지므로, 연산자의 고유한 성질(기저 불변성)을 위배하기 때문이다.

우리는 기저의 선택과 무관한, 연산자 본연의 성질을 유지하는 엄밀한 정의가 필요하다.

---

## X.2 접근법 1: 거듭제곱 급수를 이용한 정의 (Power Series Definition)

함수 $f(z)$가 $z=0$ 근처에서 해석적(Analytic)이라고 가정하자.

### 정의 X.2.1 (다항식 연산자)
$p(z) = \sum_{k=0}^{n} c_k z^k$가 다항식일 때, 연산자 $p(\hat{A})$는 자연스럽게 다음과 같이 정의된다.

$$
p(\hat{A}) \coloneqq c_0 \hat{I} + c_1 \hat{A} + c_2 \hat{A}^2 + \dots + c_n \hat{A}^n
$$

여기서 $\hat{A}^0 = \hat{I}$ (항등 연산자)이며, $\hat{A}^k$는 연산자 곱셈을 $k$번 수행한 것이다.

### 정의 X.2.2 (테일러 급수를 통한 정의)
함수 $f(z)$가 원점을 포함하는 반경 $R$ 내에서 수렴하는 테일러 급수를 갖는다고 하자.

$$
f(z) = \sum_{k=0}^{\infty} c_k z^k \quad (|z| < R)
$$

연산자 $\hat{A}$의 **연산자 노름(Operator Norm)** $\|\hat{A}\|$가 $\|\hat{A}\| < R$을 만족한다면, $f(\hat{A})$는 다음과 같이 정의된다.

$$
f(\hat{A}) \coloneqq \sum_{k=0}^{\infty} c_k \hat{A}^k = c_0 \hat{I} + c_1 \hat{A} + c_2 \hat{A}^2 + \dots
$$

### 엄밀성 검증 (Convergence)
이 정의가 유효하려면 우변의 무한 급수가 수렴해야 한다. 힐베르트 공간 $\mathcal{H}$ 위의 유계 선형 연산자들의 공간 $\mathcal{B}(\mathcal{H})$는 **바나흐 공간(Banach Space, 완비 노름 공간)**이므로, 절대 수렴(Absolute Convergence)을 보이면 수렴성을 보장할 수 있다.

$$
\left\| \sum_{k=0}^{\infty} c_k \hat{A}^k \right\| \leq \sum_{k=0}^{\infty} |c_k| \|\hat{A}\|^k
$$

가정에 의해 $\|\hat{A}\| < R$이므로, 우변의 스칼라 급수는 수렴한다. 따라서 연산자 급수도 바나흐 공간 내에서 수렴한다.

### 예시 (행렬 지수 함수, Matrix Exponential)
$f(z) = e^z = \sum_{k=0}^\infty \frac{z^k}{k!}$은 수렴 반경이 $R = \infty$이다. 따라서 모든 유계 연산자 $\hat{A}$에 대해 다음은 잘 정의된다.

$$
e^{\hat{A}} = \hat{I} + \hat{A} + \frac{1}{2!} \hat{A}^2 + \frac{1}{3!} \hat{A}^3 + \dots
$$

---

## X.3 접근법 2: 스펙트럼 분해를 이용한 정의 (Spectral Decomposition)

$\hat{A}$가 에르미트 연산자이거나 유니터리 연산자(일반적으로 정규 연산자, Normal Operator)인 경우, 스펙트럼 정리를 사용하는 것이 가장 강력하고 직관적이다.

**전제 조건:** $\hat{A}$는 힐베르트 공간 $\mathcal{H}$ 위에서 정규 직교 기저 $\{ |e_n\rangle \}$로 대각화 가능하다고 가정한다.

$$
\hat{A} = \sum_{n} \lambda_n |e_n\rangle \langle e_n| = \sum_{n} \lambda_n \hat{P}_n
$$

여기서 $\lambda_n$은 고유값, $\hat{P}_n = |e_n\rangle \langle e_n|$은 사영 연산자이다.

### 정리 X.3.1 (사영 연산자의 성질)
사영 연산자들은 서로 직교하며(Orthogonal), 멱등성(Idempotent)을 가진다.

$$
\hat{P}_n \hat{P}_m = \delta_{nm} \hat{P}_n
$$

이 성질을 이용하면 $\hat{A}$의 거듭제곱은 다음과 같이 간단해진다.

$$
\hat{A}^k = \left( \sum_n \lambda_n \hat{P}_n \right)^k = \sum_n \lambda_n^k \hat{P}_n
$$

### 정의 X.3.2 (스펙트럼 함수적 계산)
임의의 함수 $f: \mathbb{C} \to \mathbb{C}$가 $\hat{A}$의 스펙트럼 $\sigma(\hat{A}) = \{ \lambda_n \}$ 위에서 정의될 때,

$$
f(\hat{A}) \coloneqq \sum_{n} f(\lambda_n) |e_n\rangle \langle e_n|
$$

**장점:**
1. 급수의 수렴성을 따질 필요가 없다(유한 차원인 경우).
2. 테일러 급수로 정의하기 힘든 함수(예: 불연속 함수, 제곱근 등)도 정의할 수 있다. 단, $f(\lambda_n)$이 정의되기만 하면 된다.

### 정리 X.3.3 (스펙트럼 사상 정리, Spectral Mapping Theorem)
연산자 $f(\hat{A})$의 고유값은 $f(\lambda_n)$들이며, 고유벡터는 $\hat{A}$와 동일하다.

$$
f(\hat{A}) |e_n\rangle = f(\lambda_n) |e_n\rangle
$$

---

## X.4 접근법 3: 코시 적분 공식 (Holomorphic Functional Calculus)

이 방법은 가장 일반적이며 수학적으로 우아한 정의이다. 복소 해석학의 코시 적분 공식을 연산자로 확장한다.

**배경:** 복소수 $z_0$ 근처에서 해석적인 함수 $f(z)$에 대해 다음이 성립한다.

$$
f(z_0) = \frac{1}{2\pi i} \oint_\Gamma \frac{f(z)}{z - z_0} dz
$$

여기서 $\Gamma$는 $z_0$를 포함하는 닫힌 경로이다.

### 정의 X.4.1 (레졸벤트, Resolvent)
연산자 $\hat{A}$에 대하여, 복소수 $z$가 스펙트럼 $\sigma(\hat{A})$에 속하지 않을 때($z \notin \sigma(\hat{A})$), 연산자 $(z\hat{I} - \hat{A})$는 역연산자를 가진다. 이를 **레졸벤트 연산자** $R_z(\hat{A})$라 정의한다.

$$
R_z(\hat{A}) \coloneqq (z\hat{I} - \hat{A})^{-1}
$$

### 정의 X.4.2 (던포드-테일러 적분, Dunford-Taylor Integral)
함수 $f(z)$가 $\hat{A}$의 스펙트럼 $\sigma(\hat{A})$를 포함하는 어떤 열린 집합 $D$에서 해석적(Holomorphic)이라 하자. $\sigma(\hat{A})$를 감싸는 단순 폐곡선 $\Gamma \subset D$에 대하여, $f(\hat{A})$는 다음과 같이 정의된다.

$$
f(\hat{A}) \coloneqq \frac{1}{2\pi i} \oint_\Gamma f(z) (z\hat{I} - \hat{A})^{-1} dz
$$

**해석:** 이 식에서 스칼라 분모 $(z - z_0)^{-1}$가 연산자 역원(레졸벤트) $(z\hat{I} - \hat{A})^{-1}$로 대체되었음을 주목하라. 이 정의는 $\hat{A}$가 대각화 불가능한 경우에도(예: 조르당 표준형을 가지는 경우) 완벽하게 작동한다.

---

## X.5 세 가지 정의의 일관성 (Consistency)

세 가지 정의는 조건이 겹치는 영역에서 동일한 결과를 내놓아야 한다.

**예시:** $f(z) = \frac{1}{\lambda - z}$ 라고 하자.

스펙트럼 분해 정의에 따르면:
$$
f(\hat{A}) = \sum_n \frac{1}{\lambda - \lambda_n} |e_n\rangle \langle e_n|
$$
이것은 정확히 레졸벤트 $(\lambda\hat{I} - \hat{A})^{-1}$의 스펙트럼 분해와 일치한다.

또한, 레졸벤트 $(z\hat{I} - \hat{A})^{-1}$를 $z$가 충분히 클 때 로랑 급수(Laurent Series)로 전개하면:
$$
(z\hat{I} - \hat{A})^{-1} = z^{-1} (\hat{I} - z^{-1}\hat{A})^{-1} = \frac{1}{z} \sum_{k=0}^\infty \left(\frac{\hat{A}}{z}\right)^k = \sum_{k=0}^\infty \frac{\hat{A}^k}{z^{k+1}}
$$

이를 코시 적분 식에 대입하면:
$$
\frac{1}{2\pi i} \sum_{k=0}^\infty \hat{A}^k \oint_\Gamma \frac{f(z)}{z^{k+1}} dz
$$

코시 적분 공식의 미분형 $f^{(k)}(0) = \frac{k!}{2\pi i} \oint \frac{f(z)}{z^{k+1}} dz$ 에 의해,
$$
= \sum_{k=0}^\infty \hat{A}^k \frac{f^{(k)}(0)}{k!} = \sum_{k=0}^\infty c_k \hat{A}^k
$$

이는 **접근법 1(테일러 급수)**과 정확히 일치한다.

---

## X.6 주요 응용: 베이커-캠벨-하우스도르프 공식 (BCH Formula)

연산자 함수, 특히 지수 함수 $e^{\hat{A}}$를 다룰 때 가장 주의해야 할 점은 **비가환성(Non-commutativity)**이다.

### 정리 X.6.1
일반적으로 $[\hat{A}, \hat{B}] \neq 0$인 경우,
$$
e^{\hat{A}} e^{\hat{B}} \neq e^{\hat{A} + \hat{B}}
$$

### 정리 X.6.2 (BCH 공식, Baker-Campbell-Hausdorff)
두 연산자의 곱 $e^{\hat{A}} e^{\hat{B}}$는 다음과 같은 하나의 지수 함수 $e^{\hat{Z}}$로 표현될 수 있다.

$$
e^{\hat{A}} e^{\hat{B}} = e^{\hat{Z}}
$$

여기서 $\hat{Z}$는 다음과 같이 교환자들의 무한 급수로 주어진다.

$$
\hat{Z} = \hat{A} + \hat{B} + \frac{1}{2}[\hat{A}, \hat{B}] + \frac{1}{12}([\hat{A}, [\hat{A}, \hat{B}]] - [\hat{B}, [\hat{A}, \hat{B}]]) + \dots
$$

**의미:** 이 공식은 리 군(Lie Group)의 곱셈 구조가 리 대수(Lie Algebra)의 교환자 구조(bracket)에 의해 완전히 결정됨을 보여준다.