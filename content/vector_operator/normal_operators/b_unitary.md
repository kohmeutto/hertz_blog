+++
title = "(b) Unitary"
weight = 4
+++

---

### 1. Unitary 연산자

**1) 정의**

연산자 $\hat{U}$ 가 자신의 에르미트 켤레 $\hat{U}^\dagger$ 와 다음 관계를 만족할 때, 이를 **유니타리 (Unitary) 연산자** 라 한다.

$$
\hat{U}^\dagger\hat{U} = \hat{U}\hat{U}^\dagger = \hat{I}
$$

즉 $\hat{U}^\dagger = \hat{U}^{-1}$, 에르미트 켤레가 역원과 같다. 이 조건은 정규 연산자의 조건 $[\hat{U}, \hat{U}^\dagger] = 0$ 을 자동으로 만족한다.

**2) 물리적 의미**

유니타리 연산자는 상태 벡터의 노름을 보존하는 모든 변환을 나타낸다. 양자역학에서 확률 보존이 필요한 모든 변환 — 시간 진화, 회전, 위상 변환, 기저 변환 — 이 유니타리 연산자로 기술된다.

---

### 2. 고유값은 단위 원 위에 있다

유니타리 연산자의 고유값은 모두 절댓값이 1 인 복소수이다. 복소 평면에서 단위 원 위에 위치한다.

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

Hermitian, anti-Hermitian, unitary 의 고유값 위치를 정리하면 다음과 같다.

| 연산자 | 정의 | 고유값 위치 | 복소 평면 |
|---|---|---|---|
| Hermitian | $\hat{H}^\dagger = \hat{H}$ | $\lambda \in \mathbb{R}$ | 실수 직선 |
| Anti-Hermitian | $\hat{A}^\dagger = -\hat{A}$ | $\lambda \in i\mathbb{R}$ | 허수 축 |
| Unitary | $\hat{U}^\dagger\hat{U} = \hat{I}$ | $\vert\lambda\vert = 1$ | 단위 원 |

세 가지 정의가 모두 한 단계 안에 고유값의 복소 평면 위에서의 위치를 결정한다. 이는 각 정의가 본질적으로 spectrum 의 기하학적 제약을 표현하기 때문이다.

복소 평면의 세 가지 특별한 부분 집합 — 실수 직선, 허수 축, 단위 원 — 이 세 가지 정규 연산자에 대응한다. §5, §6 에서 이 세 집합 사이의 매핑이 곧 세 연산자 사이의 변환임을 본다.

---

### 4. 기본 성질

**1) 내적 보존**

임의의 두 벡터 $|v\rangle, |w\rangle$ 에 대해

$$
\langle\hat{U}v|\hat{U}w\rangle = \langle v|w\rangle
$$

proof) 

$$
\langle\hat{U}v|\hat{U}w\rangle = \langle v|\hat{U}^\dagger\hat{U}|w\rangle = \langle v|\hat{I}|w\rangle = \langle v|w\rangle
$$

특히 노름 보존 $\|\hat{U}v\| = \|v\|$. 이 성질이 양자역학에서 확률 보존 (총 확률 $\langle\psi|\psi\rangle = 1$ 의 유지) 에 대응한다.

**2) 정수 거듭제곱**

$\hat{U}^n$ 도 유니타리이다 ($n$ 정수). 1-parameter 군 구조의 기초.

$$
(\hat{U}^n)^\dagger\,\hat{U}^n = (\hat{U}^\dagger)^n\,\hat{U}^n = \hat{I}^n = \hat{I}
$$
 
---

### 5. Hermitian 과의 변환 1: 지수 매핑

복소 평면의 매핑 관점에서 실수 직선과 단위 원 사이에는 자연스러운 일대일 대응이 존재한다.

$$
x \in \mathbb{R} \quad \longleftrightarrow \quad e^{ix} \in S^1
$$

이 매핑을 정규 연산자에 functional calculus 로 적용하면 Hermitian 과 unitary 사이의 변환이 도출된다.

**1) Hermitian 에서 Unitary 로**

$\hat{H}$ 가 자기수반 (Hermitian) 이면

$$
\boxed{\hat{U} = e^{i\hat{H}}}
$$

가 유니타리이다.

proof) $\hat{H}$ 의 spectral 분해 $\hat{H} = \sum_n \lambda_n|v_n\rangle\langle v_n|$, $\lambda_n \in \mathbb{R}$. Functional calculus 로

$$
e^{i\hat{H}} = \sum_n e^{i\lambda_n}|v_n\rangle\langle v_n|
$$

각 $e^{i\lambda_n}$ 이 단위 원 위에 있다. 유니타리 검증:

$$
(e^{i\hat{H}})^\dagger\,e^{i\hat{H}} = \sum_{nm} e^{-i\lambda_n}\,e^{i\lambda_m}\,|v_n\rangle\langle v_n|v_m\rangle\langle v_m| = \sum_n |v_n\rangle\langle v_n| = \hat{I}
$$

직교성 $\langle v_n|v_m\rangle = \delta_{nm}$ 사용.

**2) Unitary 에서 Hermitian 으로 (역방향)**

모든 유니타리 $\hat{U}$ 는 $\hat{U} = e^{i\hat{H}}$ 형태로 표현 가능. 자기수반 $\hat{H}$ 를 다음과 같이 구성한다.

$\hat{U}$ 의 spectral 분해 $\hat{U} = \sum_n e^{i\theta_n}|v_n\rangle\langle v_n|$ (각 고유값을 $e^{i\theta_n}$, $\theta_n \in [0, 2\pi)$ 형태로). 그러면

$$
\hat{H} := \sum_n \theta_n\,|v_n\rangle\langle v_n|
$$

가 Hermitian 이며 ($\theta_n$ 실수), $e^{i\hat{H}} = \sum_n e^{i\theta_n}|v_n\rangle\langle v_n| = \hat{U}$ 이다.

**3) 일대일 대응의 의미**

지수 매핑 $\hat{H} \mapsto e^{i\hat{H}}$ 가 Hermitian 연산자들의 집합과 unitary 연산자들의 집합 사이의 (다중값 보정 후) 일대일 대응을 형성한다. 이 대응은

- 정의 수준에서: $\hat{U} = e^{i\hat{H}}$
- Spectrum 수준에서: $\lambda \in \mathbb{R} \leftrightarrow e^{i\lambda} \in S^1$
- 기저 수준에서: 같은 고유벡터 $|v_n\rangle$

세 차원 모두에서 자연스럽게 작동한다.

**4) 무한소 그림과의 연결**

$\hat{H}$ 가 작은 한계에서 $e^{i\hat{H}} \approx \hat{I} + i\hat{H}$ 의 1차 전개. 이를 통해 $\hat{H}$ 가 unitary 변환의 **생성자 (generator)** 로 해석된다. 그러나 이 무한소 전개는 지수 매핑의 한 가지 표현일 뿐이며, $\hat{U} = e^{i\hat{H}}$ 의 도출 자체는 spectral 수준에서 이미 완결된다.

---

### 6. Hermitian 과의 변환 2: Cayley 변환

지수 매핑 외에 또 다른 자연스러운 매핑이 있다.

$$
z \mapsto \frac{z - i}{z + i}
$$

이 Möbius 변환은 실수 직선을 단위 원 (점 $z = -i$ 의 image 점인 $\infty$ 의 image 점 $z = 1$ 제외) 으로 매핑한다. 이를 functional calculus 로 올린 것이 **Cayley 변환** 이다.

**1) 정의**

$$
\boxed{\hat{U} = (\hat{H} - i\hat{I})(\hat{H} + i\hat{I})^{-1}}
$$

여기서 $(\hat{H} + i\hat{I})^{-1}$ 은 $\hat{H}$ 의 resolvent 의 한 평가 ($z = -i$). $\hat{H}$ 의 고유값이 모두 실수이므로 $\hat{H} + i\hat{I}$ 의 고유값 $\lambda + i \neq 0$, 따라서 역연산자가 잘 정의된다.

역변환:

$$
\hat{H} = i(\hat{I} + \hat{U})(\hat{I} - \hat{U})^{-1}
$$

(단, $\hat{U}$ 가 고유값 1 을 갖지 않는 경우에만.)

**2) Spectral 검증**

$\hat{H}$ 의 spectral 분해를 사용하면

$$
\hat{U} = \sum_n \frac{\lambda_n - i}{\lambda_n + i}|v_n\rangle\langle v_n|
$$

각 $(\lambda_n - i)/(\lambda_n + i)$ 의 절댓값:

$$
\left|\frac{\lambda_n - i}{\lambda_n + i}\right|^2 = \frac{\lambda_n^2 + 1}{\lambda_n^2 + 1} = 1
$$

단위 원 위. Unitary 의 spectrum 조건 만족.

**3) 지수 매핑과의 비교**

| | 지수 매핑 | Cayley 변환 |
|---|---|---|
| 함수 | $z \mapsto e^{iz}$ | $z \mapsto (z-i)/(z+i)$ |
| 매핑 | $\mathbb{R} \to S^1$ | $\mathbb{R} \to S^1 \setminus \{1\}$ |
| 다중값성 | $\theta_n \in [0, 2\pi)$ 선택 필요 | 일대일 (점 1 제외) |
| 무한 차원 | 유계 self-adjoint 만 직접 적용 | 비유계 self-adjoint 도 잘 정의 |
| 사용 맥락 | 양자역학 1-parameter 군 | 작용소 이론, von Neumann |

두 매핑 모두 실수 직선과 단위 원 사이의 일대일 대응을 형성하며, 서로 다른 응용 맥락에서 우위를 가진다. Cayley 변환의 강점은 자기수반 작용소가 비유계 (예: 위치 연산자, 운동량 연산자) 인 경우에도 잘 정의된 unitary 를 도출한다는 점이다.

---

### 7. Stone 정리: 시간 진화와 Hamiltonian

§1 부터 §6 까지는 한 쌍의 Hermitian-unitary 사이의 정적 관계를 다뤘다. 이 절에서는 **시간에 따라 연속적으로 변하는 unitary 들** 의 모음을 다루며, 이로부터 양자역학의 가장 기본적인 식 — Schrödinger 방정식 — 이 어떻게 도출되는지를 본다.

**1) 동기: 시간이 흐르는 시스템**

양자역학에서 시간은 연속적으로 흐르는 변수이다. 시각 $t = 0$ 에서 상태 $|\psi(0)\rangle$ 이었던 시스템이 시각 $t$ 에서 어떤 상태 $|\psi(t)\rangle$ 이 되는지를 unitary 변환으로 기술한다.

$$
|\psi(t)\rangle = \hat{U}(t)\,|\psi(0)\rangle
$$

시간 $t$ 가 매 순간 다른 값을 가지므로, 다뤄야 할 객체는 **한 개의 unitary 가 아니라 시간 $t$ 마다 하나씩 대응되는 unitary 들의 모음**

$$
\{\hat{U}(t)\}_{t \in \mathbb{R}}
$$

이다. $t = 0$ 의 unitary $\hat{U}(0)$, $t = 1$ 의 unitary $\hat{U}(1)$, $t = 2.5$ 의 unitary $\hat{U}(2.5)$, ... 모두가 이 모음의 원소.

이러한 unitary 들의 모음이 시간 변수의 자연스러운 성질을 반영해야 한다.

**2) 시간 진화 unitary 들이 만족하는 세 성질**

(a) **$t = 0$ 에서 항등** :

$$
\hat{U}(0) = \hat{I}
$$

시간이 0 만큼 흐르면 시스템이 변하지 않는다.

(b) **시간 합성 규칙**:

$$
\hat{U}(t + s) = \hat{U}(t)\,\hat{U}(s)
$$

먼저 $s$ 만큼 시간이 흐르고, 그 후 $t$ 만큼 시간이 흐르는 것은, 처음부터 $t + s$ 만큼 시간이 흐르는 것과 같다.

(c) **연속성**:

$t$ 가 연속적으로 변할 때 $\hat{U}(t)|v\rangle$ 도 연속적으로 변한다. 즉 시간이 약간 흐르면 시스템도 약간 변한다 (도약하지 않는다).

위 세 조건을 만족하는 unitary 들의 모음을 **1-parameter unitary 군** 이라 한다. (a) 와 (b) 가 군 (group) 의 조건이고, parameter 가 한 개 ($t$) 라는 점에서.

**3) Stone 정리**

위 세 조건을 만족하는 모든 1-parameter unitary 군 $\{\hat{U}(t)\}$ 는 **하나의 Hermitian 연산자** $\hat{H}$ 와 일대일 대응되며, 다음 관계를 만족한다.

$$
\boxed{\hat{U}(t) = e^{-it\hat{H}/\hbar}}
$$

여기서 $\hbar$ 는 물리에서 자주 등장하는 상수 (수학적 결과로는 $\hbar = 1$ 로 두어도 무방). $\hat{H}$ 는 unitary 군에 의해 **유일하게** 결정된다.

이 정리가 말하는 사실: 시간에 따라 연속적으로 변하는 무수히 많은 unitary 변환들의 전체 집합이 사실은 **단 하나의 Hermitian 연산자** 로 압축된다. 시간을 0 으로 두고 미분 한 번을 취하면 모든 시각 $t$ 의 unitary 가 복원되는 것이다.

**4) Hamiltonian 의 등장**

$\hat{U}(t) = e^{-it\hat{H}/\hbar}$ 의 형태로부터 $\hat{H}$ 의 의미가 직접 나온다. 작은 시간 $t$ 에서 1차 전개:

$$
\hat{U}(t) \approx \hat{I} - \frac{it}{\hbar}\hat{H} + O(t^2)
$$

매 순간 시스템의 **변화율** 을 결정하는 연산자가 $\hat{H}$. 이를 **(infinitesimal) 생성자** 라 한다. 시스템에 본질적으로 어떤 변화의 "엔진" 이 있고, 그 엔진을 표현하는 것이 $\hat{H}$.

수학적으로 $\hat{H}$ 는 $\hat{U}(t)$ 의 시각 $t = 0$ 에서의 미분으로 정의된다.

$$
\hat{H} = i\hbar\,\frac{d\hat{U}(t)}{dt}\bigg|_{t=0}
$$

양자역학에서 이 $\hat{H}$ 가 시스템의 **에너지** 를 나타내는 연산자 — **Hamiltonian** — 이다. 즉 시간 진화의 생성자가 곧 에너지 연산자. 이 일치가 우연이 아니라 Stone 정리의 직접 귀결이다.

**5) Schrödinger 방정식의 도출**

상태 $|\psi(t)\rangle = \hat{U}(t)|\psi(0)\rangle$ 의 양변을 $t$ 에 대해 미분.

$$
\frac{d|\psi(t)\rangle}{dt} = \frac{d\hat{U}(t)}{dt}\,|\psi(0)\rangle
$$

$\hat{U}(t) = e^{-it\hat{H}/\hbar}$ 의 미분:

$$
\frac{d\hat{U}(t)}{dt} = -\frac{i}{\hbar}\hat{H}\,\hat{U}(t)
$$

대입:

$$
\frac{d|\psi(t)\rangle}{dt} = -\frac{i}{\hbar}\hat{H}\,\hat{U}(t)|\psi(0)\rangle = -\frac{i}{\hbar}\hat{H}\,|\psi(t)\rangle
$$

양변에 $i\hbar$ 를 곱하면

$$
\boxed{i\hbar\,\frac{d|\psi(t)\rangle}{dt} = \hat{H}|\psi(t)\rangle}
$$

이것이 **Schrödinger 방정식**. 시간 변수에 대해 연속적으로 변하는 unitary 라는 수학적 구조 (Stone 정리) 의 직접적 귀결이다.

**6) 기존 무한소 도출과의 관계**

기존 교재에서 자주 보는 도출 — $\hat{U}(\epsilon) = \hat{I} + i\epsilon\hat{G}$ 의 무한소 전개에서 시작해서 unitarity 조건으로 $\hat{G}$ 가 Hermitian 임을 도출 — 은 위 (4) 항의 1차 전개 ($\hat{U}(t) \approx \hat{I} - it\hat{H}/\hbar$) 와 본질적으로 같은 식이다.

차이는 출발점과 도달점:

- **무한소 도출**: 무한소 전개에서 출발 → 1차 항이 Hermitian 이라는 조건 도출
- **Stone 정리**: 1-parameter 군의 연속성과 군 성질에서 출발 → 모든 시각의 unitary 가 단일 Hermitian 연산자에서 도출됨

둘은 같은 결과의 두 가지 관점이지만, Stone 정리가 spectral 측면에서 본질적 사실 (시간 진화 전체가 단일 Hermitian 에 압축) 을 명확히 보여준다. §1-§6 에서 정리한 정적 관계 (Hermitian 과 unitary 사이의 변환) 가 시간 의존 버전으로 자연스럽게 확장된 것.

---

### 8. 예

**1) 시간 진화 연산자**

양자 시스템의 시간 진화

$$
\hat{U}(t) = e^{-i\hat{H}t/\hbar}
$$

생성자 $\hat{H}$ 는 자기수반 Hamiltonian (에너지 연산자). Stone 정리의 직접 응용.

검증: $\hat{H}$ 의 고유 상태 $|n\rangle$ (에너지 $E_n$) 에 대해

$$
\hat{U}(t)|n\rangle = e^{-iE_nt/\hbar}|n\rangle
$$

각 고유 상태가 위상 $e^{-iE_nt/\hbar}$ 로 회전. 확률 $|\langle n|\psi(t)\rangle|^2$ 가 시간에 보존됨을 확인 가능.

**2) 회전 연산자**

3D 공간에서 축 $\hat{\mathbf{n}}$ 주위 각도 $\theta$ 회전

$$
\hat{R}(\theta) = e^{-i\theta\,\hat{\mathbf{n}}\cdot\hat{\mathbf{J}}/\hbar}
$$

생성자 $\hat{\mathbf{n}}\cdot\hat{\mathbf{J}}$ 는 각운동량 연산자 (자기수반). 회전 각도 $\theta$ 가 1-parameter 군의 parameter.

**3) 위상 회전**

전체 위상 $\hat{P}(\phi) = e^{i\phi\hat{I}}$. 생성자가 항등 연산자 $\hat{I}$ (가장 단순한 자기수반).

**4) 푸리에 변환**

푸리에 변환 $\mathcal{F}: L^2(\mathbb{R}) \to L^2(\mathbb{R})$ 도 unitary. $\mathcal{F}^4 = \hat{I}$ 의 관계가 성립 (4 번 적용하면 항등).

Spectral 분해: $\mathcal{F}$ 의 고유값은 $\{1, i, -1, -i\}$ (단위 원 위 네 점), 각각의 고유 함수는 Hermite 함수. Spectrum 이 단위 원 위에 있다는 일반 unitary 의 성질을 명시적으로 확인할 수 있는 예.

---

### 9. 정리

유니타리 연산자의 핵심을 한 줄로 요약하면 다음과 같다.

**Spectrum 이 단위 원 위에 있는 정규 연산자.**

Hermitian (spectrum 이 실수 직선) 과 anti-Hermitian (허수 축) 의 자연스러운 동반자이며, 복소 평면의 세 가지 특별한 부분 집합 — 실수 직선, 허수 축, 단위 원 — 이 세 정규 연산자에 대응된다.

Hermitian 과 unitary 사이의 두 가지 자연스러운 변환:

- **지수 매핑**: $\hat{U} = e^{i\hat{H}}$. 양자역학 1-parameter 군 (Stone 정리).
- **Cayley 변환**: $\hat{U} = (\hat{H} - i\hat{I})(\hat{H} + i\hat{I})^{-1}$. 비유계 자기수반 작용소.

두 변환 모두 복소 평면 매핑 (실수 직선 ↔ 단위 원) 의 functional calculus 형태이며, 정규 연산자의 spectral 측면이 변환의 본질을 결정한다.
