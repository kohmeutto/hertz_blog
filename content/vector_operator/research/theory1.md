+++
title = "(b) Theory1"
weight = 1
+++

---

### 1. 연산자 Adjoint의 물리 & 공학적 의미

**측정 대상을 바꿀 것(연산자)인가. 측정 관점을 바꿀 것인가(수반 연산자)**, 수반 연산자는 대상의 변화($\hat{A}$)를 관찰자의 변화($\hat{A}^\dagger$)로 번역해주는 대칭의 거울이다. 우리는 이 거울을 통해 대상을 직접 건드리지 않고도(Ket), 우리의 시선(Bra)을 정교하게 교정함으로써 우주의 진리에 도달한다.

**1) 범함수(Functional)라는 측정 기계**

브라 $\langle v|$는 수학적으로 **켓을 넣으면 숫자를 뱉는 기계** 이다.예를 들어, 이 시스템의 에너지는 얼마인가?라고 묻는 기계가 $\langle v|$라고 가정해 보자.

(1) 시스템 $|w\rangle$에 어떤 물리적 작용 $\hat{A}$가 가해졌다.  
(2) 이때 변한 시스템의 에너지를 측정하는 식은 $\langle v | (\hat{A} | w \rangle)$ 이다.  
(3) 하지만 우리는 **변하기 전의 시스템 $|w\rangle$을 가지고도 동일한 에너지 값을 얻고 싶다** 고 생각할 수 있다.  
(4) 그러려면 우리의 측정 기계($\langle v|$)를 **$\hat{A}$가 일어날 것을 미리 감안한 새로운 기계** 로 업그레이드해야 한다.  

즉, 그 업그레이드 된 기계가 바로 **$\langle A^\dagger v |$** 이다.

**2) 왜 그냥 $\hat{A}$가 아니라 $\hat{A}^\dagger$인가** (쌍대 공간에 맞는 변화)

그냥 $\hat{A}$를 브라에 걸면 안 되나? 복소 내적 공간에서는 브라의 영역으로 넘어가려면 반드시 그에 맞는 변화가 있어야 한다. 

(1) 켓 공간에서 $2i$배 늘어났다면,  
(2) 브라 공간(거울 세계)에서는 $-2i$배로 반응해야 전체 내적값(실제 물리량)이 일그러지지 않고 유지된다.

즉, **$\hat{A}^\dagger$** 는 켓 공간에서의 작용 $\hat{A}$가 브라 공간(범함수 공간)에서 **유사하거나 똑같은** 물리적 효과를 내기 위해 변신한 모습이다.

**3) 공학적 예시: 안테나의 송수신**

- 연산자 $\hat{A}$: 송신 안테나가 전파를 쏘아 올리는 과정 (입력 $|w\rangle$에 가해지는 변형)
- 브라 $\langle v|$: 수신 안테나가 그 전파를 잡아내는 감도 (측정 도구)

우리가 송신 파워를 2배 높였을 때의 수신 신호($\langle v | \hat{A} w \rangle$)를 계산하는 것은, 송신 파워는 그대로 두고 수신 안테나의 감도를 2배 높였을 때의 신호($\langle \hat{A}^\dagger v | w \rangle$)를 계산하는 것과 수학적으로 동일하다.이때 수신 안테나 입장에서 **송신 쪽의 변화를 내 쪽의 변화로 환산한 기준** 이 바로 수반 연산자의 작용 결과이다.

---

### 2. 미분연산자의 경계항: Fundamental Residue

**1) 정의 (Definition)**

임의의 선형 연산자 $\hat{L}$에 대하여, 시스템 경계에서의 비대칭성을 추출하는 **레지듀 변환(Residue Transform)** 슈퍼 연산자(Super-operator) $\mathcal{R}$은 다음과 같이 브라-켓 안에서 정의된다. $\mathcal{R}$ 은 연산자 공간 $\mathcal{B}(\mathcal{H})$ 에서 정의된 사상(Mapping)으로, 다음과 같은 내적 관계를 통해 그 작용이 규정된다.

$$
\langle \phi | \mathcal{R} \hat{L} | \psi \rangle = \langle \phi | \hat{L} \psi \rangle - \langle \hat{L}^\dagger \phi | \psi \rangle
$$

- 여기서 $\mathcal{R}\hat{L}$ 은 연산자 $\hat{L}$ 의 경계 레지듀를 나타내는 단일 선형 연산자이며, 표기의 간결성을 위해 슈퍼 연산자의 작용에 대한 괄호는 생략한다.
- 연산자 $\hat{L}$이 물리적 상태에 작용할 때 발생하는 **정보의 총 유출량** 이자, 경계면을 통과하는 플럭스(Flux)의 총합을 의미한다.
- 시스템이 자기 수반(Self-adjoint)이고 경계 조건이 닫혀 있다면 $\langle \phi | \mathcal{R} \hat{L} | \psi \rangle = 0$이다. 즉, $\mathcal{R} \hat{L}$은 시스템의 **대칭성이 깨진 정도** 를 직접적으로 읽어내는 대수적 센서이다.

좀 더, 이 식의 의미 깊은 의미를 살펴보자. 다음과 같이 바꿔보면, 의미가 명확해 진다.

$$
\underbrace{\langle \phi | \hat{L} \psi \rangle}_{\text{total action}} = \underbrace{\langle \phi | \mathcal{R} \hat{L} | \psi \rangle}_{\text{boundary term}} + \underbrace{\langle \hat{L}^\dagger \phi | \psi \rangle}_{\substack{\text{internal observation} \\ (\text{formal Adjoint})}}
$$

| 구분 | 수식 | 성격 | 물리적 의미 | 인식론적 정의 |
| :--- | :---: | :--- | :--- | :--- |
| **전체 실재**<br>(Total Action) | $\langle \phi \mid \hat{L} \psi \rangle$ | **객관적 실재** | 내부 작용과 경계 플럭스를 모두 포함한 사건 | 시스템의 **가감 없는 진실** |
| **내부 관측**<br>(Internal Observation) | $\langle \hat{L}^\dagger \phi \mid \psi \rangle$ | **제한적 관측** | 도메인 내부에서만 수집된 데이터와 법칙 | 관측자가 **안쪽만 훑어본 행위** |
| **관측자의 예측**<br>(Theoretical Prediction) | (상동) | **이론적 모델** | 내부 법칙이 전체를 지배할 것이라는 가정 | 관측자가 가진 **불완전한 예측치** |
| **레지듀**<br>(Residue) | $\langle \phi \mid \mathcal{R} \hat{L} \mid \psi \rangle$ | **예측 오차** | 관측자가 놓쳐버린 경계의 지문(Trace) | 관측자가 보지 못한 **경계의 실체** |

**2) 조립 법칙 (The Assembly Theorem)**

두 연산자의 직렬 결합 $\hat{L} = \hat{A}\hat{B}$에 대한 레지듀 변환은 마치 미분의 곱 법칙(Leibniz Rule)과 유사한 구조를 가진다.

$$
\mathcal{R} (\hat{A} \hat{B}) = (\mathcal{R} \hat{A}) \hat{B} + \hat{A} (\mathcal{R} \hat{B})
$$

proof)

브라-켓 표기법을 통해 조립된 시스템의 레지듀를 전개한다.

$$
\langle \phi | \mathcal{R} (\hat{A} \hat{B}) | \psi \rangle = \langle \phi | \hat{A} \hat{B} \psi \rangle - \langle \hat{B}^\dagger \hat{A}^\dagger \phi | \psi \rangle
$$

중간 상태 $\langle \hat{A}^\dagger \phi | \hat{B} \psi \rangle$를 더하고 빼서 항을 분리한다.

$$
= \left( \langle \phi | \hat{A} (\hat{B} \psi) \rangle - \langle \hat{A}^\dagger \phi | \hat{B} \psi \rangle \right) + \left( \langle \hat{A}^\dagger \phi | \hat{B} \psi \rangle - \langle \hat{B}^\dagger (\hat{A}^\dagger \phi) | \psi \rangle \right)
$$

각 괄호는 $\mathcal{R} \hat{A}$와 $\mathcal{R} \hat{B}$의 정의와 일치하므로 최종 식을 얻는다.

$$
= \langle \phi | \mathcal{R} \hat{A} | \hat{B} \psi \rangle + \langle \hat{A}^\dagger \phi | \mathcal{R} \hat{B} | \psi \rangle
= \langle \phi | (\mathcal{R} \hat{A}) \hat{B} | \psi \rangle + \langle \phi | \hat{A} (\mathcal{R} \hat{B}) | \psi \rangle
$$

이 정리는 아무리 복잡한 고차 연산자라도 기계적인 분배 법칙을 통해 하위 레지듀 블록으로 쪼개어 분석할 수 있음을 수학적으로 보장한다.

**3) 보존 법칙: 가산성 (Additivity)**

병렬로 연결된 연산자 $\hat{L} = \hat{L}_1 + \hat{L}_2$에 대하여, 레지듀 변환은 선형성을 유지한다.

$$
\mathcal{R} (\hat{L}_1 + \hat{L}_2) = \mathcal{R} \hat{L}_1 + \mathcal{R} \hat{L}_2
$$

proof)

레지듀 변환의 정의와 수반 연산자의 선형성을 이용한다.

$$
\langle \phi | \mathcal{R} (\hat{L}_1 + \hat{L}_2) | \psi \rangle = \langle \phi | (\hat{L}_1 + \hat{L}_2) \psi \rangle - \langle (\hat{L}_1 + \hat{L}_2)^\dagger \phi | \psi \rangle
$$

$$
= \left( \langle \phi | \hat{L}_1 \psi \rangle - \langle \hat{L}_1^\dagger \phi | \psi \rangle \right) + \left( \langle \phi | \hat{L}_2 \psi \rangle - \langle \hat{L}_2^\dagger \phi | \psi \rangle \right)
$$

$$
= \langle \phi | \mathcal{R} \hat{L}_1 | \psi \rangle + \langle \phi | \mathcal{R} \hat{L}_2 | \psi \rangle
$$

다물리(Multiphysics) 시스템에서 전체 경계 조건은 각 물리 현상이 독립적으로 만드는 레지듀 센서의 단순 합산으로 구성될 수 있다. 이는 시스템 모델링의 **모듈화(Modularity)** 를 가능케 하는 핵심 근거가 된다.

---

### 3. R(DpD+q)의 대수적 분석

$$
\mathcal{R}(\hat{D}p\hat{D}+q)
=\hat{D}\mathcal{R}(p\hat{D})+\mathcal{R}(\hat{D})p\hat{D}+\mathcal{R}(q)
=\hat{D}\mathcal{R}(p\hat{D})+\mathcal{R}(\hat{D})p\hat{D}
$$

**1) $\mathcal{R}(\hat{D}p\hat{D}+q)$**

$\mathcal{R}(\hat{D}p\hat{D}+q)$ 연산자가 **내부** 에서 수학적 사영(Projection)이 $0$이다.

proof)

$$
\mathcal{R}\hat{L} = \langle f| Lg \rangle - \langle Lf, g \rangle$$

항 A: $\langle f| \hat{D}(p\hat{D}g) \rangle$ (부분 적분 1회 수행)

$$
\int_a^b f^* \frac{d}{dx} \left( p \frac{dg}{dx} \right) dx = \underbrace{[f^* p g]_a^b}_{\text{Boundary 1}} - \int_a^b \frac{df^*}{dx} \left( p \frac{dg}{dx} \right) dx
$$

항 B: $\langle \hat{D}(p\hat{D}f), g \rangle$ (부분 적분 1회 수행)

$$
\int_a^b \left( \frac{d}{dx} (p \frac{df^*}{dx}) \right) g dx = \underbrace{[p f^* g]_a^b}_{\text{Boundary 2}} - \int_a^b \left( p \frac{df^*}{dx} \right) \frac{dg}{dx} dx
$$

최종 결합: 내부 항의 완벽한 소멸

$\mathcal{R}\hat{L} = (\text{항 A}) - (\text{항 B})$를 수행

$$
\mathcal{R}\hat{L} = \left( [f^* p g]_a^b - \int_a^b p f^* g dx \right) - \left( [p f^* g]_a^b - \int_a^b p f^* g dx \right)
$$

적분 기호($\int$)가 포함된 내부 항(Interior terms)들이 서로 완벽하게 일치하여 상쇄(Cancel)되어 사라진다.

$$
\mathcal{R}\hat{L}(f, g) = [p(x) \{ f^*(x) g(x) - f^*(x) g(x) \}]_a^b
$$

연산자 $L = \hat{D}p\hat{D} + q$는 내부에서 어떠한 레지듀도 남기지 않는 **순수 경계 연산자** 이다.

**2) $\mathcal{R}(\hat{D})$**

$\mathcal{R}\hat{D}$ 연산자가 **내부** 에서 수학적 사영(Projection)이 $0$이다.

$$
\mathcal{R}(\hat{D})=0
$$

proof)

$$
\langle f| Dg \rangle = \int_a^b f^* \frac{dg}{dx} dx
$$

부분 적분 수행

$$
\int_a^b f^* \frac{dg}{dx} dx = \underbrace{[f^* g]_a^b}_{\text{Boundary}} - \int_a^b \frac{df^*}{dx} g dx
$$

형식적 수반 연산자($D^\dagger = -D$) 관계 대입하면, 우변의 적분 항은 $\langle -Df, g \rangle$과 같다. 이를 좌변으로 넘기면,

$$
\underbrace{\langle f| Dg \rangle + \langle Df, g \rangle}_{\mathcal{R}\hat{D}(f, g)} = [f^* g]_a^b
$$

**3) $\mathcal{R}(p\hat{D})$**

$\mathcal{R}(p\hat{D})$는 물성 구배($p$) 라는 **내부** 에 명확한 물리적 양을 결과로 내놓는다.

$$
\mathcal{R}(p\hat{D}) = p\hat{D} + (p\hat{D})^\dagger = p\hat{D} - \hat{D}p = -[ \hat{D}, p ]
$$

proof)

연산자 $pD$ (물성 결합 미분)의 전개이제 동일한 과정을 $\hat{A} = p(x)\hat{D}$에 적용합니다. $p(x)$는 공간에 따라 변하는 함수이다.

$$
\langle f| pDg \rangle = \int_a^b (f^* p) \frac{dg}{dx} dx
$$

부분 적분 수행 ($f^ p$를 하나의 묶음으로 취급):

$$
\int_a^b (f^* p) \frac{dg}{dx} dx = \underbrace{[p f^* g]_a^b}_{\text{Boundary}} - \int_a^b \frac{d(f^* p)}{dx} g dx
$$

라이프니츠 법칙으로 미분 전개

$$
\frac{d(f^* p)}{dx} = \frac{df^*}{dx} p + f^* \frac{dp}{dx}$$이를 적분 식에 대입한다.

$$
\langle f| pDg \rangle = [p f^* g]_a^b - \int_a^b \left( p \frac{df^*}{dx} \right) g dx - \int_a^b \left( p f^* \right) g dx
$$

레지듀 형태로 정리

$$\underbrace{\langle f| pDg \rangle + \langle pDf, g \rangle}_{\mathcal{R}\{p\hat{D}\}(f, g)} = \underbrace{[p f^* g]_a^b}_{\text{Boundary Term}}-\underbrace{\int_a^b p(x) f^* g dx}_{\text{Interior Term}}$$

**$\hat{D}$와는 결정적인 차이가 발생** 한다.

- Interior Term의 생존: $\hat{D}$에서는 부분 적분 후 적분 기호가 완전히 사라졌지만, $p\hat{D}$에서는 $\int_a^b dx p(x) f^*g$라는 항이 살아남았다.
- 물리적 신호의 위치: 이 살아남은 적분 항은 **내부 점 $x$에서의 물성 구배 $p(x)$** 를 포함하고 있다.
- 전체 레지듀 값을 계산하려면 경계값뿐만 아니라, 도메인 내부 전체를 훑으며 $p(x)$를 적분해야 한다. 이것이 바로 레지듀가 **내부의 정보($p$)** 를 담고 있다고 하는 수리적 이유이다.

---

### 4. 전역적 비대칭 지표

**1) 연산자 표기**

Domain 전체에 퍼져 있는 상태를 상태 벡터 $|1\rangle$로 정의한다. 이 상태는 위치 기저(Position basis)에서 $\langle x | 1 \rangle = 1$인 균일 상태를 의미한다.

- 비대칭 지표 연산자: 여기서 $\mathcal{R}(p\hat{D})$는 연산자이며, $|1\rangle$에 작용하여 하나의 **상태 벡터** 를 생성한다.

$$
\hat{S} = \mathcal{R}(p\hat{D}) | 1 \rangle
$$

- 국소적 지표 (노드 $k$에서의 값): 이는 레지듀 연산자가 균일 상태를 얼마나 뒤틀었는지를 노드 $k$라는 시선($\langle k |$)으로 측정한 기댓값(Expectation value) 혹은 사영(Projection) 이다.

$$
S_k = | \langle k | \mathcal{R}(p\hat{D}) | 1 \rangle |
$$

**2) 인덱스 표기**

$$
S_k = \left| \sum_j D_{kj} p_j \right|
$$

proof)

완비성 관계(Completeness relation) $\sum |j\rangle\langle j| = I$를 삽입하고, $\langle j | 1 \rangle = 1$임을 이용한다.

$$
S_k
= \left| \sum_{j} \langle k | \mathcal{R}(p\hat{D}) | j \rangle \langle j | 1 \rangle \right|
$$

앞의 내적에 대해 아래와 같이 전개할 수 있다.

$$
\langle k | \mathcal{R}(p\hat{D}) | j \rangle = \langle k | (p\hat{D} + \hat{D}p) | j \rangle = \underbrace{\langle k | p\hat{D} | j \rangle}_{\text{Term A}} + \underbrace{\langle k | \hat{D}p | j \rangle}_{\text{Term B}}
$$

$p$는 대각 연산자이므로 왼쪽의 브라 $\langle k |$를 만나면 고윳값 $p_k$를 뱉는다.

$$
\langle k | p \hat{D} | j \rangle = p_k \langle k | \hat{D} | j \rangle = p_k D_{kj}
$$

마찬가지로 $p$가 오른쪽의 켓 $|j\rangle$를 만나면 고윳값 $p_j$를 뱉는다.

$$
\langle k | \hat{D} p | j \rangle = \langle k | \hat{D} | j \rangle p_j = D_{kj} p_j
$$

따라서 행렬 성분은 다음과 같이 정의된다.

$$
\langle k | \mathcal{R}(p\hat{D}) | j \rangle = p_k D_{kj} + D_{kj} p_j
$$

이산 미분 연산자 $D$는 **상수 함수를 미분했을 때 0이 되어야 한다는 일관성(Consistency)** 을 가잔다. 따라서, 

$$
\langle k | \mathcal{R}(p\hat{D}) | j \rangle = D_{kj} p_j
$$

최종적으로 다음과 같은 식을 얻을 수 있다.

$$
S_k = \left| \sum_j D_{kj} p_j \right|
$$

---

### 5. 정적 스프링 평형 모델(Static Spring Equilibrium Model)

본 이론의 핵심은 수치적 비대칭량 $S_k$를 모니터 함수로 삼아, 도메인 내의 모든 격자 셀(Cell)이 동일한 **전역 비대칭량** 을 분담하도록 질점(Nodes)을 재배치하는 데 있다. 이는 단순히 격자를 촘촘하게 만드는 것을 넘어, 이산화 오차가 발생하는 진원지를 대수적으로 압착하여 연산자의 수반성(Adjointness)을 회복하는 것을 목적으로 한다.

전역 스프링 시스템은 계산 격자의 각 노드를 질량체로, 노드 사이의 구간을 **가변 강성(Variable Stiffness)** 을 가진 스프링으로 간주한다.

**1) 전역 포텐셜 에너지 ($\mathcal{E}$)**

전체 시스템의 총 탄성 에너지는 다음과 같이 정의된다.
$$
\mathcal{E} = \frac{1}{2} \sum_{i=0}^{N-1} M_i (x_{i+1} - x_i)^2
$$

여기서 $x_i$는 격자점의 좌표이며, $M_i$는 구간 $[x_i, x_{i+1}]$의 물성 구배 가중치(Spring Stiffness)이다. 시스템은 이 총 에너지가 최소화되는 평형 상태($\nabla \mathcal{E} = 0$)를 향해 격자를 재배치한다.

**2) 국소적 평형: 훅의 법칙 (Hookes Law)**

격자의 각 노드 $i$에 대해, 인접 노드 $j$와 연결된 스프링 힘의 합이 $0$이 되어야 정적 평형 상태에 도달한다.

$$
\sum_{j \in adj(i)} F_{ij} = \sum_{j \in adj(i)} k_{ij} (x_j - x_i) = 0
$$

이를 $x_i$에 대해 정리하면 다음과 같은 가중 평균 형태의 식이 도출된다.
$$
x_i \left( \sum_j k_{ij} \right) - \sum_j k_{ij} x_j = 0
$$

**3) 수리적 강성 조립 (Stiffness Assembly)**

명시적 미분 연산자 $D_{kj}$를 기반으로 한 강성 산출 과정은 다음의 단계를 거친다.

(1) 노드별 구배 산출 ($S_k$)

중앙 차분 연산자 $D_{kj}$를 통해 각 노드에서의 물리적 기울기 절대값(Residue 지표)을 구한다. 이때 $S_k$ 는 미지의 종속 변수 $h$ 에 의한 비선형 결합을 차단하기 위해, 초기 균일 격자($h^{(0)}$) 또는 해석적 배경 메트릭 위에서 사전(A Priori) 평가된 정적 상수 벡터로 취급된다. 이를 통해 $\mathbf{Kx} = \mathbf{b}$ 는 완벽한 선형 시스템을 유지한다.

$$
S_k = \left| \sum_j D_{kj} p_j \right| \approx  \left|\frac{1}{h_k + h_{k-1}} \left[ \frac{h_{k-1}}{h_k} (p_{k+1} - p_k) + \frac{h_k}{h_{k-1}} (p_k - p_{k-1}) \right]\right|
$$

(2) 구간 강성 보간

구간 강성($S_{i+1/2}$)으로의 보간스프링은 노드와 노드 사이(Edge)에 존재하므로, 인접한 두 노드의 지표를 산술 평균하여 구간 강성을 정의한다.

$$
S_{i+1/2} = \frac{S_i + S_{i+1}}{2}
$$

(3) 전역 정규화 (Normalization, $\bar{S}_i$)

도메인 전체에서 가장 급격한 변화를 보이는 곳의 강성을 $1.0$으로 맞추는 과정이다.

$$
\bar{S}_i = \frac{S_{i+1/2}}{\max_{j} (S_{j+1/2}) + \epsilon}
$$

**4) 전역적 대수 구조: 강성 행렬 (Stiffness Matrix)**

도메인 전체 노드에 대해 평형식을 세우면 전역 선형 시스템 $\mathbf{Ax} = \mathbf{b}$ (또는 $\mathbf{Kx} = \mathbf{b}$)가 도출된다.

(1) 행렬의 성분

$$
M_i(\lambda) = \underbrace{(1 - \lambda)}_{\text{Uniformity Base}} + \underbrace{\lambda\cdot\bar{S}_i}_{\text{Adaptive Signal}}
$$

이 식은 $0 \le \lambda \le 1$ 범위 내에서 두 성질을 배합한다.

(2) $(1 - \lambda)$ : 기저 메트릭 (Uniformity Base)

- 의미: 도핑 농도나 물리량의 변화가 전혀 없는 진공 상태에서도 격자가 가져야 할 최소한의 강성이다.
- 역할: $\bar{S}_i$가 $0$인 벌크 영역에서 스프링이 끊어지지 않게 지탱한다. 이 항 덕분에 격자는 물리적 구배가 없어도 일정한 간격($h=\text{const}$)을 유지하려는 균일성을 확보한다.

(3) $\lambda \cdot \bar{S}_i$ : 적응형 시그널 (Adaptive Signal)
- 의미: 물리적 비대칭량($S_k$)을 정규화한 값이다.
- 역할: 계면(Junction)처럼 변화가 격심한 곳에서 스프링을 극도로 딱딱하게(Stiff) 만든다. 스프링이 딱딱해지면 평형 상태에서 격자 간격($\Delta x$)은 압착된다. 즉, 물리가 시키는 대로 격자를 모으는 힘이다.

(4) 삼중 대각 행렬의 조립 형식

예로, 경계 조건($x_0=0, x_N=1$)을 포함한 최종 시스템은 다음과 같다.

$$
\begin{bmatrix}
1 & 0 & \dots & \dots & 0 \\
-M_0 & M_0+M_1 & -M_1 & \dots & 0 \\
0 & \ddots & \ddots & \ddots & 0 \\
0 & \dots & -M_{N-2} & M_{N-2}+M_{N-1} & -M_{N-1} \\
0 & \dots & \dots & 0 & 1
\end{bmatrix}
\begin{bmatrix}
x_0 \\ x_1 \\ \vdots \\ x_{N-1} \\ x_N
\end{bmatrix} 
= \begin{bmatrix}
0 \\ 0 \\ \vdots \\ 0 \\ 1
\end{bmatrix}
$$

- 수치적 특징: 이 행렬은 대칭 양의 정부호(SPD)이며 매우 희소(Sparse)하므로, 직접법(Direct Solver)으로 $O(N)$의 복잡도로 단 한 번에 최종 좌표 $\mathbf{x}$를 산출한다.

**5) 적응형 공간 메트릭 혼합 지수(Adaptive Spatial Metric Blending Index), $\lambda$ 의 최적화**

| $\lambda$ 값 | 대수적 구성 ($M_i$) | 격자의 상태 (Physics vs Geometry) | 수치적 판결 |
| :--- | :--- | :--- | :--- |
| **$0.0$** | $M_i = 1.0$ | **완전 균일 격자.** 물리량을 무시하고 기하학적 동일성만 고집 | 안정성 극대 / 해상도 포기 |
| **$1.0$** | $M_i = \bar{S}_i$ | **수치적 폭주.** 구배가 0인 곳의 강성이 0이 되어 시스템이 붕괴 | **임계점 초과 (Singular)** |

$\mathcal{J}_{Action}(\lambda)$은 최적화된 $\lambda$를 산출하기 위한 목적함수이다. 오른쪽의 두 항은 모두 무차원(Dimensionless)이며, 평균 대비 상대적 오차의 제곱합이므로 단위나 스케일의 간섭을 받지 않는다. 

$$
\mathcal{J}_{Action}(\lambda)
= E_{geo}(\lambda) + E_{phys}(\lambda)
= \underbrace{ \sum_{i \sim j} \left( \frac{V_i}{V_j} - 1 \right)^2 }_{\text{인접 요소 간의 기하학적 찢어짐}} + \underbrace{ \sum_{k} \left( \bar{S}_k \cdot \frac{V_k}{\bar{V}} \right)^2 \quad}_{\text{물리적 변화량의 유실}}
\quad \left( \text{단, } \bar{V} = \frac{1}{N} \sum V_k \right)
$$

- 정규화($\bar{V}$ 분모)는 총 격자 수 $N$ 의 변화에 관계없이 $E_{phys}$ 가 $E_{geo}$ 와 동등한 차원의 스케일에서 길항 작용을 수행할 수 있도록 보장하는 대수적 안전장치이다.
- 최적화 루프에서 격자의 길항 작용을 계산할 때 사용되는 $V_k$는 각 개별 스프링(격자 구간) 자체가 차지하는 물리적 크기를 의미한다. 일차원의 경우 아래와 같이 표현된다.

$$
V_k = h_k = x_{k+1} - x_k
$$

위의 목적함수는

- 제 1항 (이웃과의 마찰): 내 옆 요소와 크기가 너무 다르면 찢어진다. 부드럽게 변해라! (강성 행렬 파괴 및 수반성 파괴 방어)
- 제 2항 (물리와의 마찰): 물리 구배($\bar{S}_k$)가 큰 곳에서는 네 덩치($V_k$)를 줄여서 변화를 담아내라! (물리적 해상도 방어)

---

### 6. 브렌트 방법(Brents Method): 미분 없는 지능형 최적화

목적 함수 $\mathcal{J}_{Action}(\lambda)$의 최저점을 찾기 위해 사용된 **브렌트 방법(Brents Method)** 의 수리적 구조를 다룬다. 브렌트 방법은 미분 계수(Gradient)를 사용하지 않는 **Derivative-free** 최적화 알고리즘의 정수로, 황금 분할 탐색의 안정성과 포물선 보간법의 속도를 결합한 하이브리드 방식이다.

**1) 왜 브렌트 방법인가?**

AI의 가중치 최적화에 쓰이는 경사하강법(SGD 등)은 다차원 공간에서 기울기에 의존하지만, 우리의 혼합 지수 $\lambda$는 $0$과 $1$ 사이의 **1차원 스칼라 공간** 에 존재한다. 

이러한 저차원 최적화에서는 미분 값을 계산하는 비용보다, 함수를 직접 평가하여 구간을 좁혀나가는 방식이 대수적으로 훨씬 이득이다. 브렌트 방법은 다음 두 가지 무기를 상황에 맞춰 교체하며 사용한다.

- **황금 분할 탐색 (Golden Section Search):** 수렴을 보장하는 안전 장치
- **연속 포물선 보간법 (Successive Parabolic Interpolation):** 수렴 속도를 폭발시키는 가속 장치

**2) 제 1단계: 황금 분할 탐색 (안전한 포위)**

함수의 형태를 전혀 모를 때, 브렌트 방법은 구간을 황금비($\phi \approx 1.618$)로 분할하여 탐색 범위를 축소한다.

두 점 $x_1, x_2$ 사이를 분할하는 점 $x_a, x_b$를 잡을 때, 어떤 구간을 선택하더라도 항상 동일한 비율로 구간이 축소되도록 설계된 비율이다.

$$
\phi = \frac{1 + \sqrt{5}}{2} \approx 1.618
$$

구간의 축소 비율 $w$는 다음과 같다.

$$
w = \frac{1}{\phi^2} = 1 - \frac{1}{\phi} \approx 0.382
$$

이 방식은 매 단계마다 탐색 구간을 약 $38.2\%$씩 확실하게 줄여나가므로, 목적 함수가 심하게 찌그러져 있어도 **반드시 수렴(Global Convergence)** 한다는 강력한 장점을 가진다.

**3) 제 2단계: 연속 포물선 보간법 (초고속 저격)**

탐색 구간이 어느 정도 좁혀져 목적 함수가 국소적으로 볼록(Convex)해지면, 알고리즘은 가속 모드로 전환한다.

세 개의 점 $(x_1, f_1), (x_2, f_2), (x_3, f_3)$이 주어졌을 때, 이 세 점을 지나는 유일한 2차 함수(포물선) $P(x)$를 구성할 수 있다. 이 포물선의 꼭짓점 좌표 $x^*$는 다음과 같은 대수 방정식으로 명시된다.

$$
x^* = x_2 - \frac{1}{2} \frac{(x_2 - x_1)^2 [f_2 - f_3] - (x_2 - x_3)^2 [f_2 - f_1]}{(x_2 - x_1) [f_2 - f_3] - (x_2 - x_3) [f_2 - f_1]}
$$

알고리즘은 다음 탐색 점으로 황금 분할 점이 아닌, 이 포물선의 꼭짓점 $x^*$를 선택한다. 만약 함수가 매끄러운 2차 함수에 가깝다면, 브렌트 방법은 단 몇 번의 연산만으로 **초월적 수렴 속도(Superlinear Convergence)** 를 보여준다.

**4) 브렌트의 결정 로직 (The Logic)**

브렌트 방법이 위대한 이유는 의심과 신뢰 사이의 균형이다.

- **신뢰:** 포물선 보간법으로 예측한 $x^\ast$가 현재 탐색 구간 내에 존재하고, 오차를 유의미하게 줄인다면 $x^*$를 채택한다.
- **의심:** 만약 $x^*$가 구간 밖으로 튀어나가거나 수렴 속도가 느려진다면, 즉시 포물선 보간을 버리고 **황금 분할 탐색** 으로 돌아가 안전하게 구간을 좁힌다.
- **DpD 엔진에서의 의미**: 목적 함수 $\mathcal{J}_{Action}(\lambda)$ 는 양 끝단에서 발산하는 U자형 곡선이므로, 브렌트 방법은 초기에 황금 분할로 안전하게 내려오다가 바닥 부근에서 포물선 보간으로 급가속하여 최적의 $\lambda^*$를 1e-16 정밀도로 낚아채게 된다.

**5) 요약 테이블**

| 특징 | 황금 분할 탐색 (GSS) | 포물선 보간법 (SPI) |
| :--- | :--- | :--- |
| **수렴 속도** | 선형 (Linear) | 초선형 (Superlinear) |
| **안정성** | 절대적 (구간 내 보장) | 조건부 (함수가 부드러울 때) |
| **미분 사용** | 사용 안 함 (Derivative-free) | 사용 안 함 (Derivative-free) |
| **주된 역할** | 초기 포위 및 발산 방어 | 최적점 정밀 타격 및 가속 |

---

### 7. 효율적 연산을 위한, 실수 대각 가중 연산자의 도입

가중치 연산자 $\hat{M}$ 을 사용한다.

$$
\langle \phi|\hat{L}|\psi\rangle \stackrel{M}{\to} \langle\phi|\tilde{L}|\psi\rangle =\langle\phi|\hat{M}\hat{L}|\psi\rangle 
$$

$\mathcal{R}\tilde{L}$ 를 구해본다.

$$
\mathcal{R}\tilde{L}=\mathcal{R}(\hat{M}\hat{L})=\hat{M}\mathcal{R}(\hat{L})+\mathcal{R}(\hat{M})\hat{L}
$$

여기서 실수 대각행렬을 가중행렬로 사용하면,

$$
\mathcal{R}\tilde{L}=\hat{M}\mathcal{R}(\hat{L})-\mathcal{R}(\hat{M})\hat{L}=\hat{M}(\hat{L}-\hat{L}^\dagger)
$$

아래식과 비교해 보자.

$$
\mathcal{R}\tilde{L}=\tilde{L}-\tilde{L}^\dagger
$$

이것이 의미하는 바는 명확하다. 계산의 효율을 높이기 위해 도입한 $\tilde{L}$에서, **$\mathcal{R}\tilde{L}$ 행렬 내부 원소를 0으로 만드는 것은 $\mathcal{R}\hat{L}$ 의 내부를 0으로 만드는 것과 동일하다.** 결과적으로 아래와 같이 표현할 수 있다.

$$
\mathcal{R}\hat{L}=\hat{M}^{-1}\mathcal{R}\tilde{L}
$$

좀 더 아이디어를 확장해 보자. 가중치 연산자 $\hat{M}$을 두개로 분리해 보자. 하나는 grid 가중치 연산자 $\hat{G}$ 이며, 나머지 하나는 강제 가중치 연산자 $\hat{C}$ 이다. grid 가중치 연산자는 항상 실수 대각 행렬이므로, $\hat{C}$ 역시 실수 대각 행렬이어야 한다.

$$
\hat{M}=\hat{C}\hat{G}
$$

반드시, $\hat{C}$와  $\hat{G}$의 대각성분이 0이 없다는 조건하에는 역행렬이 반드시 존재한다. 그리고 교환법칙이 항상 성립한다. 따라서, 아래와 같이 정리할 수 있다.

$$
\mathcal{R}\hat{L}=\hat{C}^{-1}\hat{G}^{-1}\mathcal{R}\tilde{L}=\hat{C}_I\hat{G}_I\mathcal{R}\tilde{L}
$$

위의 식에서 $\hat{G}_I$ 는 격자 이동에 의해 자동으로 결정되는 연산자이므로 강제로 값을 건드릴 수 없다. 이 와 반대로 $\hat{C}_I$는 0이 아닌 실수 대각 행렬만 유지된다면, 강제로 값을 건드릴 수 있기 때문에 $\mathcal{R}\tilde{L}$ 내부의 값을 0과 가깝게 수정할 수 있다.

---

### 8. 격자 가중 행렬 (Grid Weighting Matrix, $\hat{G}$)

**1) 정의**

듀얼 체적 메트릭(Dual Volume Metric) $\hat{G}$는 각 노드가 지배하는 기하학적 영토의 크기를 정의하는 **대각 행렬(Diagonal Matrix)** 이다. 이는 이산화된 유한체적법(FVM) 시스템을 점 미분 형태(Point-wise)에서 물리적 적분 형태(Integral-wise)로 변환하는 메트릭 연산자 역할을 수행한다. $N$개의 노드를 가진 시스템에서 $\hat{G} \in \mathbb{R}^{N \times N}$은 다음과 같이 정의된다.

$$
\hat{G} = \text{diag}(V_0^*, V_1^*, V_2^*, \dots, V_{N-1}^*)
$$

여기서 **$V_k^*$ (Dual Control Volume)** 는 최적화된 격자 $x_{opt}$ 위에서 다음과 같이 계산된다.

- 요소의 길이: 역할: 구간 안에서 물리량의 구배(Gradient)가 계산된다. 즉, 흐름(Flux)이 정의되는 공간이다.

$$
V_k = x_{k+1} - x_k = h_k
$$

- 내부 노드 ($0 < k < N-1$): 두 인접 요소 체적의 절반씩을 점유한다.

$$
V_k^* = \frac{x_{k+1} - x_{k-1}}{2} = \frac{V_k + V_{k-1}}{2}
$$

- 경계 노드 ($k=0, N-1$): 반쪽짜리 체적만 가진다. (Dirichlet/Neumann 조건에 따라 조정 가능)

$$
V_0^* = \frac{x_1 - x_0}{2}, \quad V_{N-1}^* = \frac{x_{N-1} - x_{N-2}}{2}
$$

**2) 비대칭성의 기하학적 제거** 

일반적인 FVM 전위 방정식은 다음과 같은 형태를 가진다.

$$
\frac{1}{V_k^*} \left[ J_{k+1/2} - J_{k-1/2} \right] = \rho_k
$$

이 식을 행렬 형태로 쓰면, $V_k^*$가 일정하지 않은 불균일 격자에서 $\hat{L}$은 **비대칭(Non-symmetric)** 이 된다. $\hat{L} \mathbf{u} = \mathbf{f}$를 푸는 대신, 양변에 그리드 행렬 $\hat{G}$를 사전 곱(Pre-multiplication) 하여 시스템을 재조립한다. $\hat{G}$과 $\hat{L}$가 결합하면, 결과 행렬 $\tilde{L} = \hat{G}\hat{L}$는

$$
\hat{G}\hat{L}\mathbf{u} = \hat{G}\mathbf{f} \implies \tilde{L}\mathbf{u} = \tilde{\mathbf{f}}
$$

$\tilde{L}$의 성분 $\tilde{L}_{i,j}$는 노드 간의 유량(Flux) 결합을 나타낸다.

$$
\tilde{L}_{i, i+1} = - \frac{p_{i+1/2}}{h_i}, \quad \tilde{L}_{i+1, i} = - \frac{p_{i+1/2}}{h_i}
$$

**3) 격자 가중 행렬 적용의 결과**

(1) 자기 수반성

그리드 행렬 $\hat{G}$는 분모에 있던 비대칭 요소인 $1/V_k^*$를 상쇄시켜 버린다. 그 결과, $A_{i, i+1} = A_{i+1, i}$ 가 기계적 오차 $10^{-16}$ 내에서 완벽하게 성립하며 **자기 수반성(Self-adjointness)** 이 복원된다.

(2) 양의 정부호성 (Positive Definiteness) 보장

$\hat{G}$는 체적 행렬이므로 모든 대각 성분이 양수($V_k^* > 0$)이다. 따라서 $\hat{G}$는 Symmetric Positive Definite이다. $\hat{L}$은 타원형 PDE(Poisson)에서 유도된 확산 행렬이므로, $\hat{G}$와의 결합을 통해 전체 시스템의 고윳값(Eigenvalues)이 모두 양수임을 대수적으로 확정한다.

---

### 9. 강제 압착 연산자 (Forced Compress Operator, $\hat{C}$)

**1) 강제 압착 연산자 존재의 필요성**

**그리드 가중 연산자($\hat{G}$)** 가 공간의 기하학적 메트릭(Metric)에 의한 수반성 파괴를 복원했다면, **강제 수반 연산자($\hat{C}$)** 는 해($|u\rangle$)의 동적 변이가 초래하는 대수적 왜곡을 최종적으로 정화하기 위해 존재한다.

$\hat{G}$가 골조를 세운 후에도 내부 레지듀 $\mathcal{R}\hat{G}\hat{J}_{int}\neq 0$ 인 상태가 유지된다. $\hat{C}$는 이 잔여 비대칭성을 대수적으로 압착하여, 시스템을 $10^{-16}$의 무균 대칭 상태로 강제 전이시키는 역할을 수행한다.

**2) 잔차 시스템**

우리가 풀고자 하는 새로운 잔차 시스템을 정의해 본다.

$$
\tilde{L}(u)|u\rangle=|\tilde{f}\rangle, \text{ where } \tilde{L}=\hat{C}\hat{G}\hat{L},\,\tilde{f}=\hat{C}\hat{G}|f\rangle
$$

$$
|\tilde{R}(u)\rangle = \tilde{L}|u\rangle-|\tilde{f}\rangle = \hat{C}(u)\hat{G}(u)|R(u)\rangle
$$

**3) 각 연산자의 1차 변분 정의**
 
상태 벡터가 $|u\rangle$에서 $|u + \delta u\rangle$로 미소하게 변할 때, 상태에 종속된 세 가지 요소($\hat{C}, \hat{G}, |R\rangle$)는 각각 자신의 1차 편미분(프레셰 도함수)을 따라 선형적으로 변화힌다. 고차항(Higher-order terms, $\mathcal{O}(\|\delta u\|^2)$)은 이 단계에서 분리한다.
 
- 수반 연산자의 변화: $\hat{C}(u+\delta u) = \hat{C}(u) + \delta\hat{C} + \mathcal{O}(\|\delta u\|^2)$
- 메트릭 연산자의 변화: $\hat{G}(u+\delta u) = \hat{G}(u) + \delta\hat{G} + \mathcal{O}(\|\delta u\|^2)$
- 물리 잔차 벡터의 변화: $|R(u+\delta u)\rangle = |R(u)\rangle + |\delta R\rangle + \mathcal{O}(\|\delta u\|^2)$

식 $|\tilde{R}(u+\delta u)\rangle$에 위에서 정의한 1차 변분 형태를 대입하여 순수하게 대수적 전개를 수행한다.
 
$$
|\tilde{R}(u+\delta u)\rangle = \left( \hat{C} + \delta\hat{C} \right) \left( \hat{G} + \delta\hat{G} \right) \left( |R\rangle + |\delta R\rangle \right)
$$

이 세 괄호의 곱을 완전히 전개하면 총 8개의 항이 도출된다.

$$
|\tilde{R}(u+\delta u)\rangle = \hat{C}\hat{G}|R\rangle \quad \text{(0차항)}
$$

$$
+(\delta\hat{C})\hat{G}|R\rangle+\hat{C}(\delta\hat{G})|R\rangle+\hat{C}\hat{G}|\delta R\rangle \quad \text{(1차 변분항)}
$$

$$
+(\delta\hat{C})(\delta\hat{G})|R\rangle + (\delta\hat{C})\hat{G}|\delta R\rangle + \hat{C}\delta\hat{G})|\delta R\rangle \quad \text{(2차 비선형항)}
$$

$$
+(\delta\hat{C})(\delta\hat{G})|\delta R\rangle \quad \text{(3차 비선형항)}
$$

여기서 1차 변분항들은 상태 $u$에 대한 편미분 연산자가 $|\delta u\rangle$에 작용하여 만들어진 선형 사영 결과물이다.

$$
\delta\hat{C} = \frac{\partial \hat{C}}{\partial u} |\delta u\rangle
,\quad \delta\hat{G} = \frac{\partial \hat{G}}{\partial u} |\delta u\rangle
,\quad |\delta R\rangle = \frac{\partial |R\rangle}{\partial u} |\delta u\rangle = \hat{J} |\delta u\rangle
$$

**4) 자코비안과의 연결**

$$
|\tilde{R}(u+\delta u)\rangle
\approx |\tilde{R}\rangle+|\delta\tilde{R}\rangle 
=|\tilde{R}\rangle+\hat{J}_{new}|\delta u\rangle
\implies \hat{J}_{new}|\delta u\rangle = |\tilde{R}(u+\delta u)\rangle -|\tilde{R}(u)\rangle
$$

자코비안 $\hat{J}$는 **1차 선형 연산자** 로 정의되므로, 2차 이상의 비선형항($\delta^2, \delta^3$)들은 선형화(Linearization) 가정에 의해 소거된다. 따라서 순수하게 1차 변분항만이 남게 된다.

$$
\hat{J}_{new}|\delta u\rangle = (\delta\hat{C})\hat{G}|R\rangle + \hat{C}(\delta\hat{G})|R\rangle + \hat{C}\hat{G}|\delta R\rangle
$$

이제 이 식에 1단계에서 정의했던 편미분 표현을 적용한다.

$$
\hat{J}_{new}|\delta u\rangle = \left( \left[ \frac{\partial \hat{C}}{\partial u} \right] \hat{G} |R\rangle + \hat{C} \left[ \frac{\partial \hat{G}}{\partial u} \right] |R\rangle + \hat{C} \hat{G} \left[ \frac{\partial |R\rangle}{\partial u} \right] \right) |\delta u\rangle
$$

양변에서 임의의 미소 변위 $|\delta u\rangle$를 분리해 내면, 최종적인 진성 자코비안 연산자 $\hat{J}$의 편미분 표현이 도출된다.

$$
\hat{J}_{new} = \underbrace{ \frac{\partial \hat{C}}{\partial u} \hat{G} |R\rangle}_{\text{수반 연산자 변분}} + \underbrace{\hat{C} \frac{\partial \hat{G}}{\partial u} |R\rangle}_{\text{메트릭 연산자 변분}} + \underbrace{\hat{C} \hat{G} \frac{\partial |R\rangle}{\partial u}}_{\text{물리 연산자 변분}}
= \underbrace{\left( \frac{\partial \hat{C}}{\partial u} \hat{G} + \hat{C} \frac{\partial \hat{G}}{\partial u} \right)}_{\text{Framework Variation}} \mathbf{|R\rangle} + \hat{C} \hat{G} \hat{J}$$

**5) $\hat{C}$의 도출 원리**

위 식에서, 앞의 두 항에는 물리적 불평형량인 **순수 잔차 $|R\rangle$** 이 인자(Factor)로 곱해져 있다.결과적으로 뉴턴 루프가 진행되어 해($u^*$)에 가까워질수록 $|R\rangle \to 10^{-16}$으로 소멸한다.즉, 해 근처에서 자코비안의 거동을 지배하는 것은 오직 마지막 항($\hat{C}\hat{G}\hat{J}$)뿐이다.
다음 조건을 만족하는 대각 가중 연산자(Diagonal Operator) $\hat{C}$를 찾는 것이다.

(1) 연산자 분해 및 수반성 조건

조립된 자코비안의 임의의 노드 결합 $|i\rangle, |j\rangle$에 대해, 변환된 연산자 $\tilde{J} = \hat{C}\hat{G}\hat{J}$의 수반성을 선형 사상으로 표현하면 다음과 같다.

$$
\langle i | \hat{C}\hat{G}\hat{J}_L | j \rangle = \langle j | \hat{C}\hat{G}\hat{J}_L | i \rangle
$$

$\hat{C}$가 대각 연산자($\hat{C} |i\rangle = c_i |i\rangle$)임을 이용하면

$$
c_i \langle i | \hat{G}\hat{J} | j \rangle = c_j \langle j | \hat{G}\hat{J} | i \rangle
$$

(2) 로그-변환 사상 (Log-Mapping)

위의 비선형 결합 식을 선형 대수 시스템으로 변환하기 위해 로그 사상을 적용힌다. (모든 결합 계수가 같은 부호를 가짐을 전제함)

$$
\ln(c_i) - \ln(c_j) = \ln\left( \frac{\langle j | \hat{G}\hat{J} | i \rangle}{\langle i | \hat{G}\hat{J} | j \rangle} \right) \implies x_i - x_j = b_{ij}
$$

(3) 행렬 시스템 $Ax=b$의 조립 (Assembly)

격자 상의 모든 연결 고리(Edge)에 대해 위 식을 세우면 다음과 같은 선형 시스템이 구축 된다.

- 변수 벡터 ($x$): 우리가 구하고자 하는 모든 노드의 가중치 로그 값 $[\ln c_1, \ln c_2, \dots, \ln c_N]^T$
- 계수 행렬 ($A$): 각 행(Edge)마다 연결된 노드 $i$ 위치에는 $1$, 노드 $j$ 위치에는 $-1$이 들어가는 매우 희소한(Sparse) 행렬
- 결과 벡터 ($b$): 각 연결 고리에서의 **비대칭 오염도(Log-ratio)** 를 모아놓은 벡터.

**6) 최소자승법(LLS)을 통한 대수적 압착**

(1) 최소 자승법 사용 

1차원에서는 이 시스템의 해가 완벽하게 존재하지만, 2차원 이상의 복잡한 격자에서는 완벽한 해가 없을 수도 있다. 이때 **최소자승법(Least Squares)** 을 사용하여 **전체적인 비대칭 에너지를 최소화하는 최적의 $c_i$** 를 찾아낸다.

$$
\min_x \| \mathbf{A}x - \mathbf{b} \|^2
$$

이 연산을 통해 얻은 $x$를 다시 지수 함수로 되돌리면($c_i = e^{x_i}$), 드디어 **강제 수반 연산자 $\hat{C}$** 의 대각 성분들이 완성된다.

(2) $\hat{C}$ 연산자의 대수적 앵커링 (Boundary Anchoring)

$\hat{C}$ 연산자의 스케일링이 도메인 경계까지 침범하게 되면, 보존되어야 할 외부와의 상호작용(Boundary Flux)마저 지수 형태로 오염됩니다. 이는 물리적 실재를 부정하는 치명적인 대수적 오류이다.

최소자승법(LLS)을 통해 $\hat{C}$ 행렬의 가중치 로그 값($\ln c_i$)을 구할 때, $\hat{C}$가 전역적으로 부유(Floating)하지 않도록 경계 노드를 완벽한 $1.0$으로 고정(Anchor)해야 한다.

$$
c_0 = 1.0, \quad c_{N-1} = 1.0 \quad \implies \quad \ln(c_0) = 0, \quad \ln(c_{N-1}) = 0
$$

선형 시스템 $\mathbf{A}x = \mathbf{b}$를 풀 때 경계 노드에 해당하는 행을 디리클레(Dirichlet) 조건처럼 강제 구속한다. 이렇게 하면 $\hat{C}$ 행렬의 양 끝단 대각 성분은 반드시 $1.0$이 된다. 결과적으로 $\tilde{J} = \hat{C}\hat{G}\hat{J}$ 연산이 수행되더라도, 경계에서의 레지듀($\mathcal{R}$) 스케일은 원래의 기하학적 유량 상태를 그대로 유지하게 된다.

---

### 10. T+K spliting

비균일 격자 및 고차 비선형 미분 방정식 시스템에서 연산자의 수반성(Adjointness)을 복원하고, 수치적 안정성을 극대화하기 위한 T+K 분리 및 적출법을 정의한다.

**핵심 원칙:** 내부 도메인에서는 완벽한 자기 수반성을 회복(멸균)하되, 우변의 잔차(Residue)에는 시스템의 모든 물리적 비대칭성을 온전히 보존하여 진성 해(Intrinsic Solution)를 타격한다.

**1) 설계의 배경**

T+K 체계는 비대칭 성분을 연산자 내부에서 발라내어 격리하는 덧셈형 적출(Additive Isolation) 방식을 취한다. 이는 수치적 강성(Stiffness)을 확보함과 동시에 물리적 보존 법칙을 훼손하지 않기 위함이다.

**2) 대수적 정의 (Decomposition)**

이산화된 미분 연산자 $\hat{L}$은 비균일 격자에서 기하학적 비대칭성을 갖는다. 이를 정화하기 위해 **그리드 가중 행렬($\hat{G}$)**과 **강제 수반 연산자($\hat{C}$)** 를 도입하여 시스템 연산자 $\tilde{L}$을 재구성한다.

$$
\tilde{L} = \hat{C}\hat{G}\hat{L}
$$

- $\hat{G}$: 기하학적 체적 변동에 의한 비대칭 소거.
- $\hat{C}$: 비선형 변이에 의한 동적 비대칭성 압착.

**3) 대수적 분해**

$T$와 $K$의 정의재조립된 연산자 $\tilde{L}$은 수학적으로 유일한 대칭 성분($\hat{T}$)과 반대칭 성분($\hat{K}$)의 합으로 분해된다.

$$
\tilde{L} = \hat{T} + \hat{K}
$$

- $\hat{T}$ (Symmetric Part): 시스템의 안정적 탐색을 담당하는 대칭 골격.
- $\hat{K}$ (Skew-symmetric Part): 이산화 오차와 비선형 회전성이 만든 수치적 찌꺼기.

**4) 내부의 멸균과 외부의 실재 (The Sterile Principle)**

단순히 $\hat{K}$ 전체를 제거하는 것이 아니라, **레지듀($\mathcal{R}$)** 의 관점에서 오차와 물리를 판별하여 선택적으로 적출한다.

- 내부 (Interior) → 멸균 대상: 도메인 내부에서 발생하는 비대칭성($\hat{K}_{int}$)은 물리 법칙의 왜곡(Noise)이다. 이를 적출하여 좌변의 계산 경로에서 제외한다.
- 외부 (Boundary) → 보존 대상: 경계에서의 비대칭성은 외부 세계와의 상호작용(Flux)이므로, 이를 제거하는 것은 물리적 실재를 부정하는 것이다. 따라서 경계 성분은 마스킹 없이 보존한다.

**5) 구현: 마스킹을 통한 선택적 적출**

대각 마스킹 연산자 $\hat{M}_{B}$ (경계 노드=1, 내부=0)를 사용하여, 내부 오염원 $\hat{K}_{int}$ 을 분리한다.

$$
\hat{K}_{int} = (I - \hat{M}_B) \cdot \hat{K} \cdot (I - \hat{M}_B)
$$

이 투영 과정을 통해 최종 시스템 행렬 $\tilde{L}$는 다음과 같이 삼분된다.

$$
\tilde{L} = \underbrace{\hat{T}}_{\text{Sterile Law}} + \underbrace{\hat{K}_{int}}_{\text{Numerical Noise}} + \underbrace{\hat{B}}_{\text{Boundary Reality}}
$$

**6) 실행: Newton-K 루프의 수렴 메커니즘**

좌변은 대칭화된 강성을 사용하되, 우변은 물리적 잔차를 유지한다.

$$
\underbrace{(\hat{T} + \hat{B})}_{\text{LHS (Symmetric Pointer)}} \Delta \mathbf{u}^{(n+1)} = - \underbrace{\hat{C}\hat{G}\mathbf{Res}^{(n)}}_{\text{RHS (Pure Physics)}}
$$

- 좌변의 역할: 내부가 멸균된 대칭 행렬($\hat{T}$)은 매우 낮은 조건수(Condition Number)를 제공하며, 해를 찾기 위한 최단거리 방향타 역할을 수행한다.
- 우변의 역할: $\mathbf{Res}$ 내부에는 이미 $\hat{K}_{int}$를 포함한 모든 물리적 결합이 반영되어 있다. 따라서 우변에는 어떠한 추가 섭동항도 더하지 않으며, 오직 순수 레지듀만을 잣대로 삼는다.결과: 루프가 진행됨에 따라 $\Delta \mathbf{u} \to 0$이 되면, $\mathbf{Res}$는 거짓 평형점 없이 **정확히 $0$** 으로 수렴하여 물리적 진실에 도달한다.

**7) 기존 보정 알고리즘과의 차별성**

- 무결성: 외부에서 가짜 항(Artificial term)을 주입하지 않는다. 비대칭성을 좌변에서 분리했을 뿐, 물리적 근(Root)은 변하지 않는다.
- 초월적 수렴: 기하학적 텐서(MACRO)가 비대칭성을 선제 흡수하고, 무균 대칭 행렬(MICRO)이 탐색을 주도하므로 기계적 오차 영역까지 거침없이 도달한다.

---

### 11. C & T-K flowchart

```text
[초기 셋업 (Initialization & Anchoring)]
 1. 물리적 도메인 진단: 물성 급변 구간 및 계면 파악
 2. [★ 앵커 삽입]: 불연속점 및 주요 경계에 절대 앵커 노드 고정
 3. 초기 격자(X_0) 생성: 앵커 사이 구역 임의 격자 배치
 4. 초기 추정해(u_0) 셋업
       │
       ▼
======================================================================= 
[MACRO LOOP: 물리적 격자 도약 (Physical Grid Adaptation)]
======================================================================= 
엔진 구동: 해의 형태를 추적하여 기하학적 비대칭 오차(G)를 원천 차단하라.
       │
       ├──▶ 1. [상태 진단] 현재 해 u_m 기반 전역 비대칭 지표 S_k 산출
       │
       ├──▶ 2. [스프링 엔진 가동] 앵커 고정 하에 구역별 최적 λ* 탐색 (Brents Method)
       │       → 기하학적 K가 최소화된 새 격자 X_new 
       │       → 격자 체적을 대각화한 실수 행렬 G(Grid Weighting) 도출
       │
       ├──▶ 3. [초기해 강제 이식] u_m을 새 격자 X_new에 스플라인 보간
       │
       │    ============================================================
       │    [MICRO LOOP: 대수적 해의 정화 (C-Forced T+K Newton)]
       │    ============================================================
       │    목표: 비선형 변이(J)가 만든 대수왜곡을 C로 압착하고, T+K로 1e-16 멸균하라.
       │          │
       │          ├──▶ a. 정확한 잔차 Res 및 원시 자코비안 J 계산
       │          │
       │          ├──▶ b. [★ 동적 비대칭성 압착: 강제 수반 연산자 C 산출]
       │          │        1) 임시 행렬 조립: J_G = G * J 
       │          │        2) 오염도 추출: 모든 엣지에서 b_ij = ln(<j|J_G|i> / <i|J_G|j>)
       │          │        3) 최소자승법(LLS) 직접 풀이: min ||Ax - b||^2 → 해 x 도출
       │          │        4) C 행렬 조립: C = diag(e^x)
       │          │
       │          ├──▶ c. 완벽한 메트릭 결합 시스템 조립 (A = C * G * J)
       │          │        (이 단계에서 시스템 행렬 A는 해석적으로 도달 가능한 최대 대칭성을 확보함)
       │          │
       │          ├──▶ d. [★ T+K 대수적 분해 및 K_int 적출]
       │          │        T = (A + A^T) / 2  → (내부 멸균 골격, 대칭 양의 정부호성 유지)
       │          │        K_int = (I-Mb)*K*(I-Mb) → (경계를 제외한 내부 잔여 비대칭 찌꺼기)
       │          │
       │          ├──▶ e. 하이브리드 시스템 풀이 (조건수 분석 표기 병행)
       │          │        (T+B) * Δu = - C * G * Res - K_int * u
       │          │        (T의 강력한 대칭성을 무기로 BiCGSTAB/직접법 초고속 구동)
       │          │
       │          ├──▶ f. 해 업데이트 (u_{n+1} = u_n + Δu)
       │          │
       │          ├──▶ g. [Micro 수렴 판정]: 기계적 오차 ||Res|| < 1.0e-16 도달 여부
       │          │        ├─ (NO) a번으로 돌아가 갱신된 J에 대해 C 재산출 및 정화 반복
       │          │        └─ (YES) 무균 상태 도달. MICRO LOOP 즉시 탈출 (Break)
       │    ============================================================
       │
       └──▶ 4. [이중 평형 수렴 판정] 격자 최대 이동량 ||X_new - X_old|| < 1.0e-16 인가?
               ├─ (NO) X_old = X_new 로 갱신 후 MACRO 1번으로 복귀
               └─ (YES) 격자(물리)와 해(대수) 평형 도달. MACRO LOOP 탈출

=======================================================================
[탐색 종료: 궁극의 정해 u* 및 최적 격자 X* 동시 확정]
=======================================================================
[출력: 수렴 로그, 행렬 T의 조건수(Condition Number), 각 노드별 C 행렬 가중치 스펙트럼]
```

---