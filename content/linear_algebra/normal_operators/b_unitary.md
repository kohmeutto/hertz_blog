+++
title = "(b) Unitary"
weight = 4
+++

---

## 2.4 유니타리 연산자 (Unitary Operator)

**정의**: 연산자 $\hat{U}$의 에르미트 켤레 $\hat{U}^\dagger$가 $\hat{U}$의 역행렬과 같을 때, 즉 $\hat{U}^\dagger\hat{U} = \hat{U}\hat{U}^\dagger = \hat{I}$일 때, 이를 **유니타리 연산자**라고 한다. 이 연산자 역시 정규 연산자의 조건을 만족한다.

**물리적 의미**: 유니타리 연산자는 상태 벡터의 길이(norm), 즉 **확률을 보존**하는 모든 물리적 변환을 나타낸다. 양자 시스템의 **시간 변화(time evolution)**나 **기저 변환(change of basis)** 등은 반드시 유니타리 연산자로 기술되어야 한다.

---
### 핵심 특성 및 증명

#### **1. 내적 보존**
> **정리**: 유니타리 연산자는 내적을 보존한다. 즉, 임의의 두 벡터 $|v\rangle, |w\rangle$에 대하여 $\langle \hat{U}v|\hat{U}w\rangle = \langle v|w\rangle$가 성립한다.

> **증명**: $\langle \hat{U}v|\hat{U}w\rangle = \langle v|\hat{U}^\dagger\hat{U}|w\rangle = \langle v|\hat{I}|w\rangle = \langle v|w\rangle$.
> **물리적 의미**: 이 성질 덕분에, 유니타리 변환 후에도 상태의 총 확률($\langle\psi|\psi\rangle=1$)이 1로 보존된다.

#### **2. 생성자를 통한 지수 함수 표현**

## 질문의 핵심: 가정인가, 유도인가?

양자역학이나 군론(Group Theory)을 공부하다 보면 유니타리 연산자 $U$를 다음과 같이 당연하다는 듯이 표현하는 경우를 자주 봅니다.

$$ U = e^{i\hat{H}} $$

이때 "왜 처음부터 저런 형태를 가정하는 거지? 오히려 유니타리 연산자의 정의로부터 저 지수 함수 형태를 유도해야 하는 것이 아닌가?" 라는 의문이 들 수 있습니다. 이는 매우 정확하고 핵심을 찌르는 질문입니다.

결론부터 말하면, 지수 함수 형태는 **가정이 아니라 유니타리 연산자의 정의와 '연속성'이라는 조건으로부터 필연적으로 유도되는 결과**입니다. 이 글에서는 그 과정을 상세히 유도해 보겠습니다.

---

### 1. 유니타리 연산자의 정의와 의미

먼저 정의부터 시작하겠습니다. 어떤 연산자 $U$가 **유니타리(Unitary)**하다는 것은 다음을 만족한다는 의미입니다.

$$ U^\dagger U = U U^\dagger = I $$

여기서 $U^\dagger$는 $U$의 **에르미트 켤레(Hermitian conjugate)**이고, $I$는 **항등 연산자(Identity operator)**입니다.

이것의 물리적/기하학적 의미는 **벡터의 내적(inner product)을 보존한다**는 것입니다. 즉, 어떤 두 벡터 $|\psi\rangle$와 $|\phi\rangle$를 유니타리 연산자 $U$로 변환했을 때, 변환된 두 벡터 사이의 내적은 원래 내적과 같습니다.

$$ \langle U\phi | U\psi \rangle = \langle \phi | U^\dagger U | \psi \rangle = \langle \phi | I | \psi \rangle = \langle \phi | \psi \rangle $$

양자역학에서는 내적의 크기 제곱이 확률을 의미하므로, 유니타리 변환은 **확률을 보존하는 변환**이라는 중요한 의미를 가집니다.

---

### 2. 정의로부터 지수 함수 형태 유도

## 질문의 핵심: 가정인가, 유도인가?

양자역학이나 군론(Group Theory)을 공부하다 보면 유니타리 연산자 $U$를 다음과 같이 당연하다는 듯이 표현하는 경우를 자주 봅니다.

$$ U = e^{i\hat{H}} $$

이때 "왜 처음부터 저런 형태를 가정하는 거지? 오히려 유니타리 연산자의 정의로부터 저 지수 함수 형태를 유도해야 하는 것이 아닌가?" 라는 의문이 들 수 있습니다. 이는 매우 정확하고 핵심을 찌르는 질문입니다.

결론부터 말하면, 지수 함수 형태는 **가정이 아니라 유니타리 연산자의 정의와 '연속성'이라는 조건으로부터 필연적으로 유도되는 결과**입니다. 이 글에서는 그 과정을 상세히 유도해 보겠습니다.

---

### 1. 유니타리 연산자의 정의와 의미

먼저 정의부터 시작하겠습니다. 어떤 연산자 $U$가 **유니타리(Unitary)**하다는 것은 다음을 만족한다는 의미입니다.

$$ U^\dagger U = U U^\dagger = I $$

여기서 $U^\dagger$는 $U$의 **에르미트 켤레(Hermitian conjugate)**이고, $I$는 **항등 연산자(Identity operator)**입니다.

이것의 물리적/기하학적 의미는 **벡터의 내적(inner product)을 보존한다**는 것입니다. 즉, 어떤 두 벡터 $|\psi\rangle$와 $|\phi\rangle$를 유니타리 연산자 $U$로 변환했을 때, 변환된 두 벡터 사이의 내적은 원래 내적과 같습니다.

$$ \langle U\phi | U\psi \rangle = \langle \phi | U^\dagger U | \psi \rangle = \langle \phi | I | \psi \rangle = \langle \phi | \psi \rangle $$

양자역학에서는 내적의 크기 제곱이 확률을 의미하므로, 유니타리 변환은 **확률을 보존하는 변환**이라는 중요한 의미를 가집니다.

---

### 2. 정의로부터 지수(Exponential) 형태 유도

"왜 $e^{i\hat{H}}$ 형태가 되는가?"라는 질문에 답해 보겠습니다. 핵심 아이디어는 **연속적인 변환은 무한히 작은 변환(infinitesimal transformation)들을 계속해서 더해나가는 과정**으로 볼 수 있다는 것입니다.

#### 단계 1: 항등 연산자에서 아주 약간 벗어난 변환 고려

어떤 변환이 아무것도 바꾸지 않는다면 그건 항등 연산자 $I$입니다. 여기서 아주 약간, 즉 **무한소(infinitesimal)**만큼 변환하는 유니타리 연산자 $U_{inf}$를 생각해 봅시다. 이 연산자는 $I$와 거의 같을 것이므로 다음과 같이 쓸 수 있습니다.

$$ U_{inf} = I + i\epsilon \hat{G} $$

-   $\epsilon$은 아주 작은 실수($\epsilon \ll 1$)입니다.
-   $\hat{G}$는 이 무한소 변환을 특징짓는 어떤 연산자입니다. 이를 **생성자(Generator)**라고 부릅니다.
-   `i`는 왜 붙였을까? 일단 붙여놓고 계산하면 $\hat{G}$가 물리적으로 좋은 성질(에르미트)을 갖게 되기 때문인데, 잠시 후에 그 이유가 명확해집니다.

#### 단계 2: 유니타리 조건 적용

$U_{inf}$는 유니타리 연산자이므로 $U_{inf}^\dagger U_{inf} = I$를 만족해야 합니다. 위 식을 대입해서 조건을 확인해 봅시다.

먼저 $U_{inf}^\dagger$를 구하면:
$$ U_{inf}^\dagger = (I + i\epsilon \hat{G})^\dagger = I^\dagger - i\epsilon \hat{G}^\dagger = I - i\epsilon \hat{G}^\dagger $$

($I$는 에르미트이므로 $I^\dagger=I$ 이고, $(i\epsilon)^*$ = $-i\epsilon$ 이므로 부호가 바뀝니다.)

이제 $U_{inf}^\dagger U_{inf} = I$ 에 대입합니다.
$$ (I - i\epsilon \hat{G}^\dagger)(I + i\epsilon \hat{G}) = I $$
$$ I + i\epsilon \hat{G} - i\epsilon \hat{G}^\dagger - \epsilon^2 \hat{G}^\dagger \hat{G} = I $$

여기서 $\epsilon$은 무한히 작은 값이므로, $\epsilon^2$ 항은 다른 항들에 비해 무시할 수 있을 정도로 작습니다. 따라서 $\epsilon^2$ 항을 무시하면 (1차 근사):

$$ I + i\epsilon (\hat{G} - \hat{G}^\dagger) \approx I $$
$$ i\epsilon (\hat{G} - \hat{G}^\dagger) = 0 $$

이 식이 성립하려면,

$$ \hat{G} = \hat{G}^\dagger $$

결론적으로, 무한소 유니타리 변환의 생성자 $\hat{G}$는 반드시 **에르미트 연산자(Hermitian Operator)**여야 합니다. (만약 처음에 `i`를 붙이지 않고 $U_{inf} = I + \epsilon \hat{K}$로 시작했다면, $\hat{K} = -\hat{K}^\dagger$ 라는 조건, 즉 반-에르미트(anti-Hermitian) 연산자라는 결론을 얻게 됩니다. 물리학에서는 에르미트 연산자가 관측 가능한 물리량에 해당하므로, 생성자를 에르미트 연산자로 만들기 위해 관습적으로 `i`를 붙여주는 것입니다.)

#### 단계 3: 무한소 변환을 유한한 변환으로 확장

이제 작은 변환이 아닌, 유한한(finite) 크기의 변환을 만들어 봅시다. 유한한 변환은 무한소 변환을 아주 많이, $N$번 반복 적용하는 것으로 생각할 수 있습니다.

어떤 파라미터 $\theta$에 의해 결정되는 유한한 변환 $U(\theta)$가 있다고 합시다. 이 변환을 $N$개의 작은 조각으로 나누면, 각 조각은 $\delta\theta = \theta/N$ 만큼의 변환에 해당합니다. $N$을 무한대로 보내면 $\delta\theta$는 무한소 $\epsilon$이 됩니다.

따라서 유한한 변환 $U(\theta)$는 무한소 변환을 $N$번 곱한 것과 같습니다.

$$ U(\theta) = \lim_{N\to\infty} \left( I + i\frac{\theta}{N} \hat{G} \right)^N $$

이것이 바로 **지수 함수의 정의**입니다.

$$ \lim_{N\to\infty} \left( 1 + \frac{x}{N} \right)^N = e^x $$

따라서, 우리는 유니타리 연산자를 다음과 같은 형태로 쓸 수 있습니다.

$$ U(\theta) = e^{i\theta \hat{G}} $$

여기서 $\theta$는 변환의 크기를 나타내는 실수 파라미터(예: 회전 각도, 시간)이며, $\hat{G}$는 그 변환의 종류를 결정하는 **에르미트 연산자인 생성자(Hermitian Generator)**입니다. 양자역학에서는 보통 생성자를 $\hat{H}$ (해밀토니안) 등으로 표기합니다.

---

### 결론

$U = e^{i\hat{H}}$ 라는 형태는 임의의 가정이 아니라,
1.  **유니타리($U^\dagger U = I$)라는 근본적인 성질**과
2.  변환이 **연속적**이라는 개념이 결합하여
3.  필연적으로 만들어내는 **수학적 귀결**입니다.

이처럼 근본적인 원리로부터 개념을 유도해 나가는 것은 물리와 수학을 더 깊이 이해하는 가장 올바른 방법입니다.


---
### 예제
- **시간 변화 연산자**: $\hat{U}(t) = e^{-i\hat{H}t/\hbar}$. 여기서 생성자는 에르미트 연산자인 해밀토니안 $\hat{H}$이다.
- **회전 연산자**: $\hat{R}(\theta) = e^{-i\hat{J}\theta/\hbar}$. 여기서 생성자는 에르미트 연산자인 각운동량 연산자 $\hat{J}$이다.