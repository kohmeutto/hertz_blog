+++
title = "(b) Positive definite"
weight = 25
+++

---

### 1. 양정치 연산자(Positive definite operaton)의 정의

$$
\text{정규 연산자 (Normal)} \supset \text{허미션 연산자 (Hermitian)} \supset \text{양정치 연산자 (Positive Definite)}
$$

- 모든 양정치 연산자는 허미션이지만, 역은 성립하지 않는다.
- 양정치 연산자는 **고윳값이 전부 양수인 아주 특별한 허미션 연산자** 이다.
- 쉽게 설명하여, 벡터의 방향이 90도가 넘지 않도록 하는 연산자를 말한다.

**1) 양정치 연산자**

힐베르트 공간 $\mathcal{H}$ 상의 선형 연산자 $\hat{A}$에 대하여, 영벡터가 아닌 모든 켓 $|v\rangle \neq 0$에 대해 다음의 부등식을 만족할 때 이를 **양정치 연산자(Positive Definite Operator, $\hat{A} > 0$)** 라 한다.

$$
\langle v \vert \hat{A} \vert v \rangle > 0 \quad (\forall \vert v\rangle \in \mathcal{H} \setminus \{0\})
$$

- 복소수 체계($\mathbb{C}$)에는 대소 관계($>, <$)가 존재하지 않는다.
- 따라서 어떤 값이 $0$보다 크다($> 0$)는 표현 자체가 그 값이 이미 실수($\mathbb{R}$)라는 뜻을 내포한다.
- $\hat{A}$가 양정치 연산자라면, 정의에 의해 모든 $\vert{}v\rangle$에 대해 $\langle v \vert \hat{A} \vert v \rangle$는 당연히 실수이다.

**2) 양-반정치 연산자**

영벡터를 포함한 모든 벡터에 대해 $0$ 이상의 값을 허용하는 경우, 즉 아래를 만족하면, **양-반정치 연산자(Positive Semi-definite Operator, $\hat{A} \ge 0$)** 라 한다.

$$
\langle v \vert \hat{A} \vert v \rangle \ge 0 \quad (\forall \vert v\rangle \in \mathcal{H})
$$

---

### 2. 기저 체계에 따른 주의사항 (복소 공간 vs 실수 공간)

**1) 복소 힐베르트 공간 ($\mathbb{C}$)**

모든 $|v\rangle$에 대해 $\langle v \vert \hat{A} \vert v \rangle \in \mathbb{R}$이라는 조건만으로도 편극화 항등식(Polarization Identity)에 의해 허미션성($\hat{A} = \hat{A}^\dagger$)이 자동으로 유도된다.

{{< details summary="proof" >}}

임의의 두 켓 $\vert{}\phi\rangle, \vert{}\psi\rangle \in \mathcal{H}$와 복소수 $c \in \mathbb{C}$에 대하여 $\vert{}v\rangle = \vert{}\phi\rangle + c\vert{}\psi\rangle$를 대입한다.

$$\langle v \vert \hat{A} \vert v \rangle = \langle \phi \vert \hat{A} \vert \phi \rangle + \vert{}c\vert{}^2 \langle \psi \vert \hat{A} \vert \psi \rangle + c \langle \phi \vert \hat{A} \vert \psi \rangle + c^* \langle \psi \vert \hat{A} \vert \phi \rangle$$

모든 $\vert{}v\rangle$에 대해 기댓값이 실수이므로, $\langle \phi \vert \hat{A} \vert \phi \rangle$와 $\langle \psi \vert \hat{A} \vert \psi \rangle$ 역시 실수이다. 따라서 다음 복소수 항의 합도 실수여야 한다.

$$c \langle \phi \vert \hat{A} \vert \psi \rangle + c^* \langle \psi \vert \hat{A} \vert \phi \rangle \in \mathbb{R}$$

$c = 1$을 대입하면,

$$\langle \phi \vert \hat{A} \vert \psi \rangle + \langle \psi \vert \hat{A} \vert \phi \rangle \in \mathbb{R} \implies \operatorname{Im}(\langle \phi \vert \hat{A} \vert \psi \rangle) = -\operatorname{Im}(\langle \psi \vert \hat{A} \vert \phi \rangle) \quad \text{--- (1)}$$

$c = i$를 대입하면,

$$i \langle \phi \vert \hat{A} \vert \psi \rangle - i \langle \psi \vert \hat{A} \vert \phi \rangle \in \mathbb{R} \implies \operatorname{Re}(\langle \phi \vert \hat{A} \vert \psi \rangle) = \operatorname{Re}(\langle \psi \vert \hat{A} \vert \phi \rangle) \quad \text{--- (2)}$$

(1)과 (2)를 종합하면 다음과 같은 관계가 성립한다.

$$\langle \phi \vert \hat{A} \vert \psi \rangle = \langle \psi \vert \hat{A} \vert \phi \rangle^* = \langle \hat{A} \psi \vert \phi \rangle = \langle \psi \vert \hat{A}^\dagger \vert \phi \rangle^* = \langle \phi \vert \hat{A}^\dagger \vert \psi \rangle$$

이 등식이 임의의 $\vert{}\phi\rangle, \vert{}\psi\rangle$에 대해 성립하므로, 연산자 항등식 $\hat{A} = \hat{A}^\dagger$가 성립한다.

<hr>

{{< /details >}}

**2) 실수 힐베르트 공간 ($\mathbb{R}$)**

$\langle v \vert A \vert v \rangle > 0$ 조건만으로는 대칭성($A = A^T$)이 보장되지 않는다. 따라서 실수 공간에서는 **대칭(Symmetric) 조건($\hat{A} = \hat{A}^T$)을 정의의 전제 조건으로 명시** 해야 한다.

proof)

$$
A = \begin{bmatrix} 1 & 1 \\ -1 & 1 \end{bmatrix} \implies \mathbf{x}^T A \mathbf{x} = x_1^2 + x_2^2 > 0
$$

---

### 3. 물리 및 수학적 필요성

**1) 새로운 내적 및 계량 연산자(Metric Operator, $\hat{M}$)의 확립**

비직교 기저가 생성하는 공간에서 새로운 내적 $\langle \phi \vert \psi \rangle_M \equiv \langle \phi \vert \hat{M} \vert \psi \rangle$을 정의할 때, 계량 작용소 $\hat{M}$이 양정치($\hat{M} > 0$)여야만 내적의 양의 정부호성 공리($\langle \psi \vert \psi \rangle_M > 0, \forall |\psi\rangle \neq 0$)를 만족한다. 이 내용은 **Non-normal operators 문서의 전재이다.**

**2) 물리적 에너지와 안정성(Stability) 보장**

동역학계에서 운동 에너지 $T = \frac{1}{2}\langle \dot{u} \vert \hat{M} \vert \dot{u} \rangle$ 및 탄성 변형 에너지 $U = \frac{1}{2}\langle u \vert \hat{K} \vert u \rangle$가 항상 $0$보다 커야 계의 발산이나 붕괴가 없는 안정 평형 상태를 유지한다.

**3) 양자역학의 확률 보존 (밀도 연산자 $\hat{\rho}$)**

임의의 상태에 대한 측정 확률이 음수가 되지 않도록 보장하기 위해 밀도 연산자는 $\hat{\rho} \ge 0$ 및 $\mathrm{Tr}(\hat{\rho}) = 1$을 만족해야 한다.

---

### 4. 동치 조건 및 양정치 판정법

유한차원 복소 힐베르트 공간 상의 허미션 연산자 $\hat{A} = \hat{A}^\dagger$ (또는 실수 대칭 행렬)에 대하여 다음 명제들은 상호 동치이다.

| 판정 기준 | 수학적 표현 | 판정 설명 |
| :--- | :--- | :--- |
| **에너지/기댓값 기준** | $\langle v \vert \hat{A} \vert v \rangle > 0 \quad (\forall \vert v\rangle \neq 0)$ | 영벡터가 아닌 모든 상태에 대한 기댓값이 양수 |
| **스펙트럼/고윳값 기준** | $\lambda_i > 0 \quad (\forall \lambda_i \in \sigma(\hat{A}))$ | 모든 고윳값이 엄격히 양의 실수 |
| **행렬 분해 기준** | $\hat{A} = \hat{S}^\dagger \hat{S}$ (가역 연산자 $\hat{S}$) | 가역 연산자의 그람 행렬(Gramian) 형태로 분해 |
| **실베스터 판정법** | $\det(A_k) > 0 \quad (k = 1, \dots, n)$ | 모든 좌상단 주요 소행렬식(Leading Principal Minors)이 양수 |

**1) 행렬 분해 기준**

$$\hat{A} > 0 \iff \hat{A} = \hat{S}^\dagger \hat{S}, \quad \text{가역 연산자 } \hat{S} $$

{{% details summary="proof" %}}

(1) $(\implies)$ 방향

$\hat{A} > 0$ 이므로 $\hat{A}$는 허미션 연산자이며, 스펙트럼 정리에 의해 다음과 같이 대각화된다.

$$\hat{A} = \sum_{i=1}^n \lambda_i |e_i\rangle \langle e_i| \quad (\lambda_i > 0)$$

$\lambda_i > 0$이므로 실수 제곱근 $\sqrt{\lambda_i} > 0$가 유일하게 존재한다. 연산자 $\hat{S}$를 다음과 같이 정의한다.

$$\hat{S} \equiv \sum_{i=1}^n \sqrt{\lambda_i} |e_i\rangle \langle e_i|$$

$\hat{S}$는 허미션 연산자($\hat{S}^\dagger = \hat{S}$)이며, 모든 고윳값이 $0$이 아니므로 가역(Invertible)이다. 직접 곱을 취하면 아래가 성립한다.

$$\hat{S}^\dagger \hat{S} = \hat{S}^2 = \sum_{i=1}^n \lambda_i |e_i\rangle \langle e_i| = \hat{A}$$

(2) $(\impliedby)$ 방향

임의의 가역 연산자 $\hat{S}$에 대해 $\hat{A} = \hat{S}^\dagger \hat{S}$라 하자.

- 허미션성 확인:

$$\hat{A}^\dagger = (\hat{S}^\dagger \hat{S})^\dagger = \hat{S}^\dagger (\hat{S}^\dagger)^\dagger = \hat{S}^\dagger \hat{S} = \hat{A}$$

- 양정치성 확인: 임의의 $|v\rangle \neq 0$에 대하여 기댓값을 계산한다.

$$\langle v \vert \hat{A} \vert v \rangle = \langle v \vert \hat{S}^\dagger \hat{S} \vert v \rangle = \langle \hat{S} v \vert \hat{S} v \rangle = \|\hat{S} v\|^2$$

$\hat{S}$가 가역 연산자이므로 $\ker(\hat{S}) = \{0\}$이다. 따라서 $|v\rangle \neq 0$이면 $\hat{S}|v\rangle \neq 0$이며, 노름의 성질에 의해 $\|\hat{S} v\|^2 > 0$이 된다.

즉, $\langle v \vert \hat{A} \vert v \rangle > 0$이 성립하므로 $\hat{A} > 0$이다. 

<hr>

{{% /details %}}


**2) 실베스터 판정법(Sylvester's Criterion)이란**

$n \times n$ 행렬의 고윳값을 일일이 구하지 않고, 좌상단 $1 \times 1, 2 \times 2, \dots, n \times n$ 부분행렬의 행렬식이 모두 양수인지 확인하여 양정치성을 빠르게 판정하는 방법이다.

{{% details summary="proof" %}}

(1) 기초 단계 ($n = 1$):

$A = [a_{11}]$일 때, $\mathbf{x}^* A \mathbf{x} = a_{11}\vert{}x_1\vert{}^2 > 0 \iff a_{11} = \det(A_1) > 0$. 성립한다.

(2) 귀납 가정:

$(n-1) \times (n-1)$ 허미션 행렬에 대해 정리가 성립한다고 가정한다.

(3) 귀납 단계 ($n \times n$ 행렬):

$n \times n$ 허미션 행렬 $A$를 다음과 같이 블록 행렬로 분할한다.

$$A = \begin{bmatrix} A_{n-1} & \mathbf{b} \\ \mathbf{b}^* & c \end{bmatrix} \quad (A_{n-1} \in \mathbb{C}^{(n-1)\times(n-1)}, \; \mathbf{b} \in \mathbb{C}^{n-1}, \; c \in \mathbb{R})$$

(4) $(\implies)$ 방향:

- $A > 0$이면 임의의 $\mathbf{y} \in \mathbb{C}^{n-1} \setminus {\mathbf{0}}$에 대해 $\mathbf{x} = \begin{bmatrix} \mathbf{y} \ 0 \end{bmatrix}$을 잡으면 $\mathbf{y}^* A_{n-1} \mathbf{y} = \mathbf{x}^* A \mathbf{x} > 0$이므로 부분행렬 $A_{n-1}$ 역시 양정치이다.

- 귀납 가정에 의해 $\Delta_1, \dots, \Delta_{n-1} > 0$이다.또한 $A > 0$이면 모든 고윳값 $\lambda_i > 0$이므로 $\det(A) = \prod_{i=1}^n \lambda_i > 0$이 되어 $\Delta_n > 0$이다.

(5) $(\impliedby)$ 방향:

$\Delta_1, \dots, \Delta_{n-1} > 0$이면 귀납 가정에 의해 $A_{n-1} > 0$이며, 역행렬 $A_{n-1}^{-1}$가 존재한다.슈어 보수(Schur Complement)를 이용해 $A$를 다음과 같이 합동 변환(Congruence transformation)으로 분해한다.

$$\begin{bmatrix} I & 0 \\ -\mathbf{b}^* A_{n-1}^{-1} & 1 \end{bmatrix} \begin{bmatrix} A_{n-1} & \mathbf{b} \\ \mathbf{b}^* & c \end{bmatrix} \begin{bmatrix} I & -A_{n-1}^{-1} \mathbf{b} \\ 0 & 1 \end{bmatrix} = \begin{bmatrix} A_{n-1} & \mathbf{0} \\ \mathbf{0}^* & c - \mathbf{b}^* A_{n-1}^{-1} \mathbf{b} \end{bmatrix}$$

양변에 행렬식을 취하면, 변환 행렬들의 행렬식은 $1$이므로 다음을 얻는다.

$$\det(A) = \det(A_{n-1}) \cdot (c - \mathbf{b}^* A_{n-1}^{-1} \mathbf{b})$$

조건에서 $\det(A) = \Delta_n > 0$이고 $\det(A_{n-1}) = \Delta_{n-1} > 0$이므로, 스칼라 항 $c - \mathbf{b}^* A_{n-1}^{-1} \mathbf{b} > 0$이다.

블록 대각행렬의 두 블록($A_{n-1}$ 및 스칼라 항)이 모두 양정치이므로 변환된 행렬은 양정치이며, 실베스터 관성 정리(Sylvester's Law of Inertia)에 의해 원래 행렬 $A$ 역시 양정치 행렬이다.

{{% /details %}}

---

### 5. 핵심 성질 및 수학적 증명

**1) 복소 공간에서의 필연적 허미션성 및 정규성**

복소 힐베르트 공간에서 양정치 연산자는 반드시 **허미션 연산자**이며, 이에 따라 **정규 연산자(Normal Operator)** 가 된다.

$$
\hat{A} > 0 \implies \hat{A} = \hat{A}^\dagger \implies [\hat{A}, \hat{A}^\dagger] = 0
$$

{{% details summary="proof" %}}

임의의 $|v\rangle \neq 0$에 대하여 $\langle v \vert \hat{A} \vert v \rangle > 0$이므로 내적의 결과값은 항상 실수이다. 실수의 켤레복소수는 자기 자신이므로 다음이 성립한다.

$$
\langle v \vert \hat{A} \vert v \rangle = (\langle v \vert \hat{A} \vert v \rangle)^* = \langle \hat{A} v \vert v \rangle = \langle v \vert \hat{A}^\dagger \vert v \rangle
$$

위 식이 모든 $|v\rangle \in \mathcal{H}$에 대해 성립하므로, 편극화 항등식에 의하여 임의의 두 상태 $|\phi\rangle, |\psi\rangle$에 대해서도 $\langle \phi \vert \hat{A} \vert \psi \rangle = \langle \phi \vert \hat{A}^\dagger \vert \psi \rangle$가 성립한다. 따라서 $\hat{A} = \hat{A}^\dagger$이다. 자기 자신과의 교환자는 항상 영연산자이므로 정규성을 만족한다 ($[\hat{A}, \hat{A}^\dagger] = 0$).

<hr>

{{% /details %}}

**2) 직교 대각화 가능성**

$\hat{A}$는 정규 연산자이므로 스펙트럼 정리(Spectral Theorem)에 의하여 대수적 중복도와 기하적 중복도가 일치하며, 멱영 결함 성분이 발생하지 않는다. 따라서 정규직교 고유기저 $\{|\lambda_i\rangle\}$를 통해 완전한 대각화가 가능하다.

$$\hat{A} = \sum_i \lambda_i \vert\lambda_i\rangle \langle \lambda_i\vert \quad (\lambda_i > 0)$$

**3) 가역성 및 역연산자의 양정치성**

모든 고윳값이 $\lambda_i > 0$이므로 영공간(Null space)은 존재하지 않는다. ($\ker(\hat{A}) = \{0\}$). 따라서 역연산자 $\hat{A}^{-1}$가 존재하며, 역연산자 역시 양정치 연산자이다.

$$
\hat{A}^{-1} = \sum_i \frac{1}{\lambda_i} \vert\lambda_i\rangle \langle \lambda_i\vert > 0
$$

**4) 유일한 양의 제곱근 연산자 ($\sqrt{\hat{A}}$)**

각 고윳값에 대해 $\sqrt{\lambda_i} > 0$가 양의 실수로 유일하게 정의되므로, 다음을 만족하는 유일한 양정치 연산자 $\hat{S} = \sqrt{\hat{A}} > 0$가 존재한다.

$$
\hat{S}^2 = \hat{A}, \quad \hat{S} = \sum_i \sqrt{\lambda_i} \vert\lambda_i\rangle \langle \lambda_i\vert
$$

---

### 6. 응용 및 관련 개념

**1) 뢰브너 부분순서 (Löwner Partial Order)**

두 허미션 연산자 $\hat{A}, \hat{B}$에 대하여, 연산자 성분을 단순히 비교하는 것이 아니라 **임의의 상태에 대한 에너지(기댓값) 크기** 를 기준으로 부분순서 관계를 정의한다.

$$
\hat{A} \ge \hat{B} \iff \hat{A} - \hat{B} \ge 0 \iff \langle v \vert \hat{A} \vert v \rangle \ge \langle v \vert \hat{B} \vert v \rangle \quad (\forall \vert v\rangle \in \mathcal{H})
$$

**2) 극분해(Polar Decomposition)에서의 기준 모듈러스**

복소수를 극형식 $z = r e^{i\theta}$ ($r \ge 0$)로 표현하듯, 임의의 유계 선형 연산자 $\hat{T}$는 유니타리(회전) 연산자 $\hat{U}$와 양반정치(크기) 연산자 $|\hat{T}|$의 곱으로 분해된다. 
여기서 양반정치 연산자 $|\hat{T}|$는 복소수의 절댓값에 대응하는 **연산자의 크기(기준 모듈러스)** 역할을 수행한다.

$$\hat{T} = \hat{U} \vert\hat{T}\vert \quad \text{where} \quad \vert\hat{T}\vert \equiv \sqrt{\hat{T}^\dagger \hat{T}} \ge 0$$

{{% details summary="proof" %}}

(1) $\vert{}\hat{T}\vert{}$의 정의 및 성질:

연산자 $\hat{T}^\dagger \hat{T}$는 임의의 $\vert{}v\rangle$에 대해 $\langle v \vert \hat{T}^\dagger \hat{T} \vert v \rangle = \Vert{}\hat{T} v\Vert{}^2 \ge 0$이므로 허미션 양반정치 연산자이다. 따라서 양의 제곱근 연산자 $\vert{}\hat{T}\vert{} \equiv \sqrt{\hat{T}^\dagger \hat{T}} \ge 0$가 유일하게 정의된다.

(2) 노름 보존 확인:임의의 $\vert{}v\rangle \in \mathcal{H}$에 대하여,

$$\Vert{} \vert{}\hat{T}\vert{} v \Vert{}^2 = \langle \vert{}\hat{T}\vert{} v \vert \vert{}\hat{T}\vert{} v \rangle = \langle v \vert \vert{}\hat{T}\vert{}^2 \vert v \rangle = \langle v \vert \hat{T}^\dagger \hat{T} \vert v \rangle = \Vert{}\hat{T} v\Vert{}^2$$

따라서 모든 $\vert{}v\rangle$에 대해 $\Vert{} \vert{}\hat{T}\vert{} v \Vert{} = \Vert{}\hat{T} v\Vert{}$가 성립한다.

(3) 등거리 사상(Isometry) 정의:

치역 $\operatorname{Ran}(\vert{}\hat{T}\vert{})$에서 $\operatorname{Ran}(\hat{T})$로 가는 선형 사상 $\hat{U}_0$를 $\hat{U}_0(\vert{}\hat{T}\vert{}\vert{}v\rangle) = \hat{T}\vert{}v\rangle$로 정의한다.

- 단사성 및 Well-definedness:

$$\vert{}\hat{T}\vert{}\vert{}v_1\rangle = \vert{}\hat{T}\vert{}\vert{}v_2\rangle \iff \Vert{} \vert{}\hat{T}\vert{}(v_1 - v_2) \Vert{} = 0 \iff \Vert{}\hat{T}(v_1 - v_2)\Vert{} = 0 \iff \hat{T}\vert{}v_1\rangle = \hat{T}\vert{}v_2\rangle$$
- $\hat{U}_0$는 치역 상에서 거리를 보존하는 등거리 사상이다.

(4) 유니타리 연산자로의 확장:

차원 정리에 의해 $\dim(\operatorname{Ran}(\vert{}\hat{T}\vert{})^\perp) = \dim(\operatorname{Ran}(\hat{T})^\perp)$이므로, 직교 여공간 사이의 정규직교 기저를 1대1 매핑하여 $\hat{U}_0$를 전체 공간 $\mathcal{H}$ 상의 유니타리 연산자 $\hat{U}$로 확장할 수 있다.

(5) 결과적으로 모든 $\vert{}v\rangle$에 대해 $\hat{T}\vert{}v\rangle = \hat{U}\vert{}\hat{T}\vert{}\vert{}v\rangle$이므로 $\hat{T} = \hat{U}\vert{}\hat{T}\vert{}$가 성립한다.

<hr>

{{% /details %}}

**3) 무한차원 함수 공간에서의 강 양정치성 (Coercivity)**

무한차원 함수 공간에서는 모든 고윳값이 양수라 하더라도 고윳값의 하한이 0에 수렴($\inf \sigma(\hat{A}) = 0$)할 수 있어 역연산자가 비유계(Unbounded)가 될 위험이 있습니다. 따라서 편미분방정식 해의 존재성과 유일성을 보장하기 위해 다음의 강 양정치성 조건을 요구한다.

$$\langle v \vert \hat{A} \vert v \rangle \ge c \|v\|^2 \quad (\exists c > 0, \; \forall \vert v\rangle \in \mathcal{H})$$

{{% details summary="proof" %}}

(1) 단사성 및 치역의 닫힘성 (Closed Range):

코시-슈바르츠 부등식에 의해 다음이 성립한다.

$$c \Vert{}v\Vert{}^2 \le \langle v \vert \hat{A} \vert v \rangle \le \Vert{}v\Vert{} \Vert{}\hat{A} v\Vert{} \implies \Vert{}\hat{A} v\Vert{} \ge c \Vert{}v\Vert{} \quad (\forall \vert{}v\rangle \in \mathcal{H})$$

만약 $\hat{A} \vert{}v\rangle = 0$이면 $c\Vert{}v\Vert{} \le 0 \implies \vert{}v\rangle = 0$이므로 $\ker(\hat{A}) = \{0\}$ (단사).

임의의 수열 $\vert{}v_n\rangle$에 대해 $\hat{A}\vert{}v_n\rangle \to \vert{}w\rangle$ (코시 수열)이면, $\Vert{}v_n - v_m\Vert{} \le \frac{1}{c}\Vert{}\hat{A}(v_n - v_m)\Vert{} \to 0$이므로 $\vert{}v_n\rangle$도 $\mathcal{H}$ 내에서 수렴한다. 따라서 치역 $\operatorname{Ran}(\hat{A})$는 닫힌 부분공간(Closed Subspace)이다.

(2) 전사성 (Surjectivity):

투영 정리(Projection Theorem)에 의해 $\mathcal{H} = \operatorname{Ran}(\hat{A}) \oplus \operatorname{Ran}(\hat{A})^\perp$이다.

임의의 $\vert{}w\rangle \in \operatorname{Ran}(\hat{A})^\perp$를 잡으면, 정의상 모든 $\vert{}v\rangle \in \mathcal{H}$에 대해 $\langle w \vert \hat{A} \vert v \rangle = 0$이다.

여기에 $\vert{}v\rangle = \vert{}w\rangle$를 대입하면,

$$0 = \langle w \vert \hat{A} \vert w \rangle \ge c \Vert{}w\Vert{}^2 \implies \Vert{}w\Vert{} = 0 \implies \vert{}w\rangle = 0$$

따라서 $\operatorname{Ran}(\hat{A})^\perp = \{0\}$이며, 치역은 전체 공간이다 ($\operatorname{Ran}(\hat{A}) = \mathcal{H}$).

(3) 역연산자의 유계성:

$\hat{A}$가 전단사이므로 역연산자 $\hat{A}^{-1}: \mathcal{H} \to \mathcal{H}$가 존재한다.모든 $\vert{}w\rangle \in \mathcal{H}$에 대해 $\vert{}w\rangle = \hat{A}\vert{}v\rangle$로 두면,

$$\Vert{}\hat{A}^{-1} w\Vert{} = \Vert{}v\Vert{} \le \frac{1}{c} \Vert{}\hat{A} v\Vert{} = \frac{1}{c} \Vert{}w\Vert{}$$

연산자 노름의 정의에 의해 $\Vert{}\hat{A}^{-1}\Vert{} = \sup_{\Vert{}w\Vert{} \neq 0} \frac{\Vert{}\hat{A}^{-1} w\Vert{}}{\Vert{}w\Vert{}} \le \frac{1}{c} < \infty$이므로 역연산자는 유계이다.

{{% /details %}}

---

### 7. 구체적 예시

**1) $2 \times 2$ 행렬 공간**

$$A = \begin{bmatrix} 2 & 1 \\ 1 & 2 \end{bmatrix}$$

* 대칭/허미션 확인: $A^\dagger = A^T = A$
* 고윳값 계산: $\det(A - \lambda I) = (2-\lambda)^2 - 1 = \lambda^2 - 4\lambda + 3 = 0 \implies \lambda_1 = 1, \; \lambda_2 = 3 > 0$
* 실베스터 판정법 적용: $\Delta_1 = 2 > 0, \quad \Delta_2 = \det(A) = (2)(2) - (1)(1) = 3 > 0$
* 기댓값 계산 ($\forall \mathbf{v} = [x, y]^T \neq 0$): $\mathbf{v}^T A \mathbf{v} = 2x^2 + 2y^2 + 2xy = (x+y)^2 + x^2 + y^2 > 0$


**2) 미분 연산자 공간 (1차원 음의 라플라시안)**

디리클레 경계조건($u(0) = u(L) = 0$)을 만족하는 소볼레프 공간 $H_0^1(0, L)$ 상에서 미분 연산자 $\hat{K} = -\frac{d^2}{dx^2}$의 양정치성을 확인한다.

$$\langle u \vert \hat{K} \vert u \rangle = \int_0^L u^*(x) \left( -\frac{d^2 u}{dx^2} \right) dx$$

부분적분을 수행하면 경계항이 소거된다.

$$\left[ -u^*(x) \frac{du}{dx} \right]_0^L + \int_0^L \left\vert \frac{du}{dx} \right\vert^2 dx = \int_0^L \left\vert \frac{du}{dx} \right\vert^2 dx$$

* 만약 $\int_0^L |u'(x)|^2 dx = 0$이라면 거의 모든 곳에서 $u'(x) = 0$이 되어 $u(x) = C$ (상수)여야 한다.
* 경계조건 $u(0) = u(L) = 0$에 의해 $C = 0$이므로, $u(x)$가 영함수가 아닌 한($|u\rangle \neq 0$) 항상 적분값은 $0$보다 엄격히 크다.
* 푸앵카레 부등식($\int_0^L |u'|^2 dx \ge \frac{\pi^2}{L^2} \int_0^L |u|^2 dx$)에 의해 강 양정치성(Coercivity) 또한 만족한다.
* 따라서 디리클레 경계 하의 음의 라플라시안은 양정치 미분 연산자이다.