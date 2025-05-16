+++
title = "(a) Operators in quantum mechanics"
weight = 9
+++

---

- 푸리에 변환의 대수적 구조를 활용하여 연산자들 간의 관계를 깊이 있게 파악한다.
- 양자역학에서 연산자의 본질과 물리적 의미를 이해한다.

---

### 1. 시간 이동 연산자 (Time Translation Operator)

푸리에 변환의 시간 이동 속성을 통해 양자역학의 시간 이동 연산자를 유도하고 그 본질을 파악한다.

$$
\langle t|f(t-a)\rangle
=\langle t|e^{-ia\hat{\omega}}|f\rangle
$$

이때, **시간 이동 연산자** $\hat{T}(a)$를 $e^{-ia\hat{\omega}}$로 정의할 수 있습니다.

$$
\hat{T}(a) = e^{-ia\hat{\omega}}
$$

이 연산자는 함수 $|f\rangle$에 작용하여 시간적으로 $a$만큼 과거로 이동시킨 함수를 생성한다.

$$
\hat{T}(a)|f\rangle = |f(t-a)\rangle
$$

이러한 관계를 이용하면, 위치 표현 $\langle t|$에 대한 연산자의 작용도 유도할 수 있다.

$$
\langle t|\hat{T}(a) = \langle t-a|
$$

이 연산자가 시간에 대한 이동을 나타내는 것을 다음과 같이 보일 수 있습니다.

{{< details summary="연산자로의 변환 증명" >}}

주어진 관계 $\langle t|e^{-ia\omega}f(\omega)\rangle$는 푸리에 역변환의 형태입니다.
$f(\omega) = \langle\omega|f\rangle$ 이므로,
$$
\langle t|e^{-ia\omega}f(\omega)\rangle = \int d\omega \langle t|\omega\rangle e^{-ia\omega} \langle\omega|f\rangle
$$
이때, $\langle t|\omega\rangle = \frac{1}{\sqrt{2\pi}}e^{i\omega t}$ 이므로,
$$
\int d\omega \frac{1}{\sqrt{2\pi}}e^{i\omega t} e^{-ia\omega} \langle\omega|f\rangle = \int d\omega \frac{1}{\sqrt{2\pi}}e^{i\omega (t-a)} \langle\omega|f\rangle = \langle t-a|f\rangle = f(t-a)
$$
또한, 연산자 형태로 나타내면,
$$
\langle t|e^{-ia\hat{\omega}}|f\rangle = \langle t| \left( \int d\omega |\omega\rangle\langle\omega| \right) e^{-ia\hat{\omega}}|f\rangle = \langle t| \int d\omega |\omega\rangle e^{-ia\omega}\langle\omega|f\rangle
$$
위 두 식을 비교하면,
$$
\langle t|e^{-ia\hat{\omega}}|f\rangle = \langle t-a|f\rangle
$$
즉, 연산자 $e^{-ia\hat{\omega}}$는 시간 $t$를 $t-a$로 이동시키는 효과를 가집니다.

<hr>

{{< /details >}}

**유니타리 연산자로서의 시간 이동 연산자**

주파수는 물리량(에너지와 관련된)이므로, 주파수 연산자 $\hat{\omega}$는 Hermitian (에르미트) 연산자입니다 ($\hat{\omega}^\dagger = \hat{\omega}$). 따라서 시간 이동 연산자는 다음과 같은 관계를 만족합니다.

$$
\hat{T}(a)\hat{T}^{\dagger}(a) = e^{-ia\hat{\omega}}e^{ia\hat{\omega}^{\dagger}} = e^{-ia\hat{\omega}}e^{ia\hat{\omega}} = e^{i(a-a)\hat{\omega}} = e^{0} = \hat{I}
$$

이는 병진 연산자 $\hat{T}(a)$가 **유니타리(Unitary) 연산자**임을 의미합니다. 유니타리 연산자는 파동 함수의 규격화(norm)를 보존하므로, 양자역학에서 시간 진화를 비롯한 모든 변환이 확률을 보존함을 시사합니다.

**시간 진화의 생성자**

$\hat{\omega}$는 시스템의 시간 진화를 일으키는 **생성자(generator)** 역할을 합니다. 양자역학에서 해밀토니안 연산자 $\hat{H}$는 에너지 연산자이며, $\hat{\omega} = \hat{H}/\hbar$ 관계를 가집니다. 이를 이용하여 양자역학적인 시간 진화 연산자를 유도할 수 있습니다. 아주 작은 시간 변화($\delta t$)에 대한 시간 진화 연산자는 다음과 같습니다.

$$
\hat{U}(\delta t) = e^{-\frac{i}{\hbar}\delta t\hat{H}}
$$

이 연산자가 상태에 작용하면:

$$
\hat{U}(\delta t)|\Psi(t)\rangle = |\Psi(t+\delta t)\rangle
$$

---

### 2. 위치 이동 연산자 (Position Translation Operator)

시간 이동 연산자와 동일한 논리로 위치 이동 연산자를 파악할 수 있습니다. 위치 $x$에 대한 푸리에 변환의 공간 이동 속성(시간-주파수 쌍대성)을 활용합니다.

공간 영역에서 $f(x)$를 $x-a$만큼 이동시킨 함수 $f(x-a)$의 푸리에 변환은 $e^{-ika}F(k)$로 주어집니다 (여기서 $F(k) = \mathcal{F}\{f(x)\}$). 이를 Dirac 표기법으로 표현하면 다음과 같습니다.

$$
\langle x|f(x-a)\rangle = \mathcal{F}^{-1}\{e^{-iak}\langle k|f\rangle\} = \langle x|e^{-ia\hat{k}}|f\rangle
$$

이때, **위치 이동 연산자** $\hat{U}(a)$를 $e^{-ia\hat{k}}$로 정의할 수 있습니다.

$$
\hat{U}(a) = e^{-ia\hat{k}}
$$

이 연산자는 함수 $|f\rangle$에 작용하여 공간적으로 $a$만큼 과거로 이동시킨 함수를 생성합니다.

$$
\hat{U}(a)|f\rangle = |f(x-a)\rangle
$$

마찬가지로 위치 표현 $\langle x|$에 대한 연산자의 작용은 다음과 같습니다.

$$
\langle x|\hat{U}(a) = \langle x-a|
$$

**유니타리 연산자로서의 위치 이동 연산자**

파수는 물리량에 해당하므로, 파수 연산자 $\hat{k}$는 Hermitian 연산자입니다 ($\hat{k}^\dagger = \hat{k}$). 따라서 위치 이동 연산자 $\hat{U}(a)$도 유니타리 연산자입니다.

$$
\hat{U}(a)\hat{U}^{\dagger}(a) = e^{-ia\hat{k}}e^{ia\hat{k}^{\dagger}} = \hat{I}
$$

**공간 병진의 생성자**

$\hat{k}$는 공간 병진(translation)의 생성자 역할을 합니다. 양자역학에서 운동량 연산자 $\hat{p}$는 $\hat{p} = \hbar\hat{k}$ 관계를 가집니다. 따라서 운동량 연산자 $\hat{p}$는 공간 병진의 생성자입니다. 아주 작은 공간 변화($\delta x$)에 대한 공간 병진 연산자는 다음과 같습니다.

$$
\hat{P}(\delta x) = e^{-\frac{i}{\hbar}\delta x\hat{p}}
$$

이 연산자가 상태에 작용하면:

$$
\hat{P}(\delta x)|\Psi(x)\rangle = |\Psi(x+\delta x)\rangle
$$

---

### 3. 운동량 및 위치 연산자 (Momentum & Position Operators)

Dirac 표기법과 푸리에 변환의 미분 속성을 통해 위치 공간에서의 운동량 연산자와 운동량 공간에서의 위치 연산자를 파악할 수 있습니다.

**(1) 위치 공간에 대한 운동량 연산자**

푸리에 변환의 미분 속성 중 하나인 '주파수 영역에서의 곱셈은 시간 영역에서의 미분으로 변환된다'는 관계를 활용합니다. $\mathcal{F}^{-1}\{kF(k)\} = i\frac{d}{dx}f(x)$ 이므로:

$$
\langle x|\hat{k}|f\rangle = \langle x|k|f\rangle = i\frac{d}{dx}\langle x|f\rangle
$$

파수 연산자 $\hat{k}$는 Hermitian 연산자이며, 위치 공간에서 $\hat{k}$의 표현은 다음과 같습니다.

$$
\langle x|\hat{k} = i\frac{d}{dx}\langle x| \quad \text{또는} \quad \hat{k}|x\rangle = -i\frac{d}{dx}|x\rangle
$$

운동량 연산자 $\hat{p}$는 $\hat{p} = \hbar\hat{k}$ 이므로, 위치 공간에서 운동량 연산자는 다음과 같이 대응됩니다.

$$
\langle x|\hat{p} = i\hbar\frac{d}{dx}\langle x| \quad \text{또는} \quad \hat{p}|x\rangle = -i\hbar\frac{d}{dx}|x\rangle
$$

**ℹ️ 주의사항**

미분 연산자의 에르미트 켤레 (Hermitian Adjoint)는 부분 적분과 경계 조건(무한대에서 0이 되는 함수)을 고려할 때 다음과 같이 정의됩니다.

$$
\left(\frac{d}{dx}\right)^\dagger = -\frac{d}{dx}
$$

이러한 특성 때문에, $\hat{k} = i\frac{d}{dx}$ (또는 $\hat{p} = i\hbar\frac{d}{dx}$) 연산자는 Hermitian이 아니며, 대신 $\hat{k} = -i\frac{d}{dx}$ (또는 $\hat{p} = -i\hbar\frac{d}{dx}$) 연산자가 Hermitian이 됩니다. 이는 양자역학에서 관측 가능한 물리량은 에르미트 연산자로 표현되어야 한다는 조건과 부합합니다.

**(2) 운동량 공간에 대한 위치 연산자**

푸리에 변환의 미분 속성 중 '시간 영역에서의 곱셈은 주파수 영역에서의 미분으로 변환된다'는 관계를 활용합니다. $\mathcal{F}\{xf(x)\} = i\frac{d}{dk}F(k)$ 이므로:

$$
\langle k|\hat{x}|f\rangle = \langle k|x|f\rangle = i\frac{d}{dk}\langle k|f\rangle
$$

위치 연산자 $\hat{x}$는 Hermitian 연산자이며, 파수 공간(k-공간)에서 $\hat{x}$의 표현은 다음과 같습니다.

$$
\langle k|\hat{x} = i\frac{d}{dk}\langle k| \quad \text{또는} \quad \hat{x}|k\rangle = -i\frac{d}{dk}|k\rangle
$$

운동량 공간(p-공간)에서 위치 연산자는 다음과 같이 대응됩니다 ($\hat{p} = \hbar\hat{k}$, 즉 $k = p/\hbar$, $dk = dp/\hbar$).

$$
\langle p|\hat{x} = i\hbar\frac{d}{dp}\langle p| \quad \text{또는} \quad \hat{x}|p\rangle = -i\hbar\frac{d}{dp}|p\rangle
$$

---

### 4. 슈뢰딩거 파동 방정식의 유도

시간 진화 연산자의 개념으로부터 양자역학의 핵심 방정식인 슈뢰딩거 방정식을 유도할 수 있습니다.

아주 작은 시간 $\delta t$ 동안의 시간 진화 연산자 $\hat{U}(t+\delta t,t)$를 다음과 같이 나타낼 수 있습니다.

$$
\hat{U}(\delta t) = e^{-\frac{i}{\hbar}\delta t\hat{H}}
$$

이 연산자를 테일러 급수 전개를 통해 1차 항까지 근사하면:

$$
\hat{U}(\delta t) \approx \hat{I}-\frac{i}{\hbar}\hat{H}\delta t
$$

이 연산자가 어떤 시각 $t$에서의 양자 상태 $|\Psi(t)\rangle$에 작용하여 시각 $t+\delta t$에서의 상태 $|\Psi(t+\delta t)\rangle$를 만듭니다.

$$
|\Psi(t+\delta t)\rangle = \hat{U}(\delta t)|\Psi(t)\rangle
$$

위의 근사식을 대입하면:

$$
|\Psi(t+\delta t)\rangle \approx \left(\hat{I}-\frac{i}{\hbar}\hat{H}\delta t\right)|\Psi(t)\rangle
$$

$$
|\Psi(t+\delta t)\rangle - |\Psi(t)\rangle \approx -\frac{i}{\hbar}\hat{H}\delta t|\Psi(t)\rangle
$$

양변을 $\delta t$로 나누고 $\delta t \to 0$ 극한을 취하면:

$$
\frac{d}{dt}|\Psi(t)\rangle = -\frac{i}{\hbar}\hat{H}|\Psi(t)\rangle
$$

이것을 재배열하면 익숙한 **시간 의존 슈뢰딩거 방정식(Time-dependent Schrödinger Equation)**이 됩니다.

$$
\hat{H}|\Psi(t)\rangle = i\hbar \frac{d}{dt}|\Psi(t)\rangle
$$

---

### 추가적인 검토 의견:

* **Dirac Notation의 일관성**: 전반적으로 Dirac Notation(`|f>`, `$\langle t|$`, `$\langle\omega|f\rangle$`)을 일관되게 잘 사용했습니다. 이는 양자역학 연산자의 본질을 다루는 데 매우 효과적인 접근입니다.
* **물리적 의미 강조**: 각 연산자가 어떤 물리적 변환을 '생성'하는지 ("생성자" 개념)를 명확히 연결하여, 단순히 수학적 형태를 나열하는 것을 넘어 심오한 물리적 통찰을 제공합니다.
* **증명 과정**: 각 섹션에서 수식의 논리적 흐름과 증명 과정을 잘 제시하여 독자가 개념을 단계적으로 이해하도록 돕습니다. 특히 슈뢰딩거 방정식 유도는 간결하면서도 명확합니다.

이 문서는 양자역학 학습자에게 연산자의 추상적인 개념을 구체적인 푸리에 변환의 맥락과 연결하여 설명하는 훌륭한 자료가 될 것입니다.