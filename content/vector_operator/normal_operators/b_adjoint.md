+++
title = "(b) Adjoint"
weight = 1
+++

---

### 1. 연산자 Adjoint의 물리 및 공학적 의미

연산자의 수반(Adjoint)은 **측정 대상을 변형할 것인가($\hat{A}$), 혹은 측정 관점을 변형할 것인가($\hat{A}^\dagger$)** 에 대한 대수적 응답이다. 수반 연산자는 대상의 변화를 관찰자의 기준 변화로 번역하는 대칭의 거울 역할을 수행한다. 이를 통해 대상(Ket)에 직접적인 연산을 가하지 않고도, 관찰자의 시선(Bra)을 정교하게 교정함으로써 시스템의 상태를 정의할 수 있다.

**1) 범함수(Functional)를 통한 상태 측정**

브라 $\langle v|$는 켓을 입력받아 스칼라를 반환하는 범함수이다. 시스템 $|w\rangle$에 물리적 작용 $\hat{A}$가 가해졌을 때, 시스템의 특정 물리량을 측정하는 과정은 다음과 같이 분해된다.

(1) 시스템 $|w\rangle$에 물리적 작용 $\hat{A}$가 가해진다.  
(2) 변형된 시스템의 측정값은 내적 $\langle v | (\hat{A} | w \rangle)$로 표현된다.  
(3) 물리적 작용이 가해지기 전의 초기 시스템 $|w\rangle$을 유지하면서 동일한 측정값을 얻기 위해서는, 측정 도구인 $\langle v|$에 $\hat{A}$의 효과를 역으로 반영해야 한다.  
(4) 이때 관찰자의 기준을 재설정한 측정 도구가 수반 연산자가 적용된 $\langle \hat{A}^\dagger v |$이다.

**2) 공학적 적용: 안테나 시스템의 상반성**

- **연산자 $\hat{A}$** : 송신단에서 신호를 변조하거나 채널을 통과시키며 발생하는 물리적 변형.
- **브라 $\langle v|$** : 수신단에서 신호를 검출하는 감도 특성 및 측정 필터.

송신 신호에 작용 $\hat{A}$가 가해진 후 수신되는 신호 $\langle v | \hat{A} w \rangle$는, 송신 조건을 고정하고 수신단의 감도 특성을 $\hat{A}^\dagger$로 보정했을 때의 결과 $\langle \hat{A}^\dagger v | w \rangle$와 수학적으로 등가이다. 이는 수신 측에서 송신 측의 물리적 변화를 자신의 측정 기준으로 환산한 결과와 같다.

---

### 2. 유한 차원: 행렬의 켤레 전치

유한 차원 벡터 공간에서 수반 연산자는 행렬의 켤레 전치(Conjugate Transpose)로 정의되며, 내적의 정의에 의해 다음 관계가 엄밀하게 성립한다.

$$
\langle v|\hat{A} w\rangle = \langle \hat{A}^\dagger v| w\rangle
$$

proof)

- 좌변: $\langle v | Aw \rangle = \sum_{i,j} v_i^{\ast} A_{ij} w_j$
- 우변: $\langle \hat{A}^\dagger v | w \rangle = \sum_{j,i} (A^\dagger)_{ji}^{\ast} v_i^{\ast} w_j$

모든 벡터 $v, w$에 대해 위 식의 등호가 유지되려면 $A_{ij} = (A^\dagger)_{ji}^{\ast}$ 조건을 만족해야 한다. 따라서 수반 행렬의 성분 정의는 다음과 같다.

$$
(A^\dagger)_{ij} = A_{ji}^{\ast}
$$

---

### 3. 무한 차원: 미분 연산자와 경계항

무한 차원 함수 공간에서 미분 연산자를 다룰 경우, 내적 적분 과정에서 부분 적분이 수반되므로 경계 적분항 $\mathcal{R}$이 발생한다.

$$
\langle \phi|\hat{A} \psi\rangle = \langle \hat{A}^\dagger \phi| \psi\rangle + \mathcal{R}_{\hat{A}}[\phi,\psi]
$$

여기서 경계항은 다음과 같이 정의된다.

$$
\mathcal{R}\hat{A}[\phi,\psi] = \int_{\partial\Omega} d^2s\, \mathcal{B}_A[\phi,\psi]
$$

$\mathcal{B}_A[\phi,\psi]$는 브라 $\phi$에 대해 켤레 선형(Conjugate linear)이고 켓 $\psi$에 대해 선형(Linear)인 반-쌍선형(Sesquilinear) 형식을 취한다. 미분 작용소의 차수가 높아질수록 부분 적분 횟수가 증가하며, $\mathcal{B}_A$에는 $\phi, \psi$ 및 그 도함수들이 결합된 형태로 나타난다.

---

### 4. 주요 성질 (Algebra of Adjoints)

수반 작용은 대합(Involution) 성질을 가지며, 이는 연산자 자체의 구조적 불변성을 정의한다.

**1) 자기 역원 (Self-inverse)**

$$
(\hat{A}^\dagger)^\dagger = \hat{A}
$$

**2) 반선형성 (Anti-linearity)**
$$
(\alpha \hat{A} + \beta \hat{B})^\dagger = \alpha^\ast \hat{A}^\dagger + \beta^\ast \hat{B}^\dagger
$$
쌍대 공간의 복소 대수 구조에 따라 스칼라 계수는 켤레 복소수로 변환된다.

**2) 곱셈 규칙 (Product rule)과 경계항의 독립성**

$$
(\hat{A}\hat{B})^\dagger = \hat{B}^\dagger \hat{A}^\dagger
$$

이 대수적 등식은 무한 차원에서도 항상 성립한다. $(\hat{A}\hat{B})^\dagger = \hat{B}^\dagger \hat{A}^\dagger$ 규칙과 경계항 $\mathcal{R}$의 발생은 서로 모순되지 않는다. 이는 **'연산자의 추상적 형태 정의'** 와 **'실제 내적 적분의 실행'** 이 다른 차원의 문제이기 때문이다.

- **형태 정의** : $(\hat{A}\hat{B})^\dagger$는 연산자 $\hat{A}$와 $\hat{B}$를 순차적으로 브라 쪽으로 넘겼을 때, 최종적으로 적분 기호 내부에 남게 되는 연산자의 대수적 형상을 의미한다. 이 형상은 반드시 작용 순서가 뒤집힌 $\hat{B}^\dagger \hat{A}^\dagger$가 된다.
- **적분 실행** : 실제 내적 $\langle \phi | \hat{A}\hat{B} \psi \rangle$를 계산하기 위해 부분 적분을 수행하면, 각 미분기를 넘길 때마다 경계 찌꺼기가 발생한다.

$$
\langle \phi | \hat{A}\hat{B} \psi \rangle = \langle \hat{B}^\dagger \hat{A}^\dagger \phi | \psi \rangle + (\mathcal{R}\hat{A} + \mathcal{R}\hat{B})
$$

따라서 곱셈 규칙은 적분 내부의 **연산자 커널(Kernel)의 모양** 을 결정하는 규칙이며, $\mathcal{R}$은 그 변환 과정에서 발생하는 물리적 경계 조건의 산물이다. 수반 연산자의 대수 규칙은 시스템의 경계 조건과 무관하게 연산자 자체의 성질로서 유지된다.