+++
title = "(b) Adjoint derivation"
weight = 1.5
+++

---

수반 연산자를 구하는 과정은 시스템이 정의된 **공간의 성격(내적의 정의)** 에 따라 달라진다. 하지만 그 모든 과정은 단 하나의 목표 즉 연산자를 브라(Bra) 쪽으로 넘겼을 때 결과값(스칼라)의 불변성을 유지하는 것에 집중한다.

---

### 1. 유한 차원: 행렬 성분의 자리 바꾸기

$$
(A^\dagger)_{ij} = (A_{ji})^{\ast}
$$

proof) 

행렬 $A$의 수반 행렬 $A^\dagger$가 왜 '켤레 전치'가 되는지는 성분 단위의 비교를 통해 자명해진다.

- 좌변 (대상에 작용): $\langle v | Aw \rangle = \sum_i \sum_j v_i^* A_{ij} w_j$
- 우변 (관찰자에 작용): $\langle A^\dagger v | w \rangle = \sum_j \sum_i (A^\dagger_{ji})^* v_i^* w_j$


---

### 2. 미분 연산자, 수반연산자 도출의 부품

**1) 미분의 부품, 형식적 수반(formal adjoint) & 경계항**

$$
\hat{D}=\frac{d}{dx} \implies \hat{D}^{\dagger}=-\frac{d}{dx} \quad\text{with boundary term: } [\phi^{\ast}\psi]_a^b
$$

proof)

$$
\langle \phi|\hat{D}\psi\rangle
=\int_a^b dx\left\lbrack\phi^{\ast}\frac{d}{dx}\psi\right\rbrack
=\int_a^b dx\left\lbrack\frac{d}{dx}\phi^{\ast}\psi-\psi\frac{d}{dx}\phi^{\ast}\right\rbrack
=\left\lbrack \phi^{\ast}\psi\right\rbrack^b_a-\int_a^b dx\left\lbrack\psi\frac{d}{dx}\phi^{\ast}\right\rbrack
$$

$$
=\left\lbrack \phi^{\ast}\psi\right\rbrack^b_a+\langle\hat{D}^{\dagger}\phi|\psi\rangle
$$

위를 라그랑주 항등식(Lagrange Identity) 이라고 하며, 아래와 같이 구분한다.

$$\langle \phi | \hat{D} \psi \rangle = \underbrace{\langle-\hat{D}\phi|\psi\rangle}_{\text{formal adjoint}}+\underbrace{\left\lbrack\phi^{\ast}\psi\right\rbrack^b_a}_{\text{boundary term}}
$$

**2) 복소수 함수의 부품**

$$
q(x)^{\dagger}=q(x)^{\ast}
$$

proof)

$$
\langle \phi | p \psi \rangle = \int dx \phi^* p \psi = \int dx (p^* \phi)^* \psi = \langle p^* \phi | \psi \rangle
$$

**3) $\dagger$의 역순법칙과 선형성**

- 역순 법칙: $(\hat{A}\hat{B})^\dagger = \hat{B}^\dagger \hat{A}^\dagger$
- 선형성: $(\hat{A} + \hat{B})^\dagger = \hat{A}^\dagger + \hat{B}^\dagger$

---

### 3. 미분연산자의 경계항: Fundamental Residue

**1) 정의 (Definition)**

임의의 선형 연산자 $\hat{L}$에 대하여, 시스템 경계에서의 비대칭성을 추출하는 **레지듀 변환(Residue Transform)** 슈퍼 연산자(Super-operator) $\mathcal{R}$은 다음과 같이 **브라-켓 안** 에서 정의된다. $\mathcal{R}$ 은 연산자 공간 $\mathcal{B}(\mathcal{H})$ 에서 정의된 사상(Mapping)으로, 다음과 같은 내적 관계를 통해 그 작용이 규정된다.

$$
\langle \phi | \mathcal{R} \hat{L} | \psi \rangle = \langle \phi | \hat{L} \psi \rangle - \langle \hat{L}^\dagger \phi | \psi \rangle
$$

- 연산자 $\hat{L}$이 물리적 상태에 작용할 때 발생하는 **'정보의 총 유출량'** 이자, 경계면을 통과하는 플럭스(Flux)의 총합을 의미한다.
- 시스템이 자기 수반(Self-adjoint)이고 경계 조건이 닫혀 있다면 $\langle \phi | \mathcal{R} \hat{L} | \psi \rangle = 0$이다. 즉, $\mathcal{R} \hat{L}$은 시스템의 **'대칭성이 깨진 정도'** 를 직접적으로 읽어내는 대수적 센서이다.

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

주의: 이 등식은 brа-ket 사이에서 평가될 때 성립한다. 즉, 

$$
\langle \phi | \mathcal{R} (\hat{A} \hat{B}) | \psi \rangle = \langle \phi | (\mathcal{R} \hat{A}) \hat{B} + \hat{A} (\mathcal{R} \hat{B}) | \psi \rangle
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

### 4. 적용1: 1차 미분 혼합형, L=p(x)d/dx+q(x)

이 형태는 반도체에서의 드리프트(Drift)나 유체 역학의 대류(Advection)에 해당한다.

**1) formal adjoint**

$$
L^{\dagger}=\hat{D}^{\dagger}p^{\ast}+q^{\ast}
$$

**2) residue**

조립 법칙을 적용한다.

$$
\mathcal{R} \hat{L} = \mathcal{R}(p\hat{D} + q) = \mathcal{R}(p\hat{D}) + \mathcal{R}q
$$

여기서 $\mathcal{R}q = 0$이므로,

$$
\mathcal{R}(p\hat{D}) = (\mathcal{R}p)\hat{D} + p(\mathcal{R}\hat{D})
$$

스칼라 함수 $p$는 미분이 포함되지 않은 단순 곱 연산자이므로 $\mathcal{R}p = 0$이다.

$$
\mathcal{R} \hat{L} = p\mathcal{R}\hat{D}
$$

브라-켓을 적용한다.

$$
\langle \phi | \mathcal{R} \hat{L} | \psi \rangle = \langle \phi | p \mathcal{R}\hat{D} | \psi \rangle = \langle p^* \phi | \mathcal{R}\hat{D} | \psi \rangle
$$

미분 센서 $\mathcal{R}\hat{D}$의 정의($[\phi^* \psi]_a^b$)를 적용하면:

$$
\mathcal{R} \hat{L} = [ (p^* \phi)^* \psi ]_a^b = [ p \phi^* \psi ]_a^b
$$

---

### 5. 적용2: 스텀-리우빌, L=-1/w(x){d/dx p(x) d/dx+q(x)}

연산자 정의

$$
\hat{L} = \hat{w} \hat{K} = -\frac{1}{w(x)} \{ \hat{D} p(x) \hat{D} + q(x) \}
$$

**1) 표준 내적 ($L^2$ Space)**

내적을 $\langle \phi | \psi \rangle = \int dx \phi^* \psi $ 로 정의하는 일반적인 관찰자 시점이다.

(1) formal adjoint

먼저 내부 블록 $\hat{K} = \hat{D} p \hat{D} + q$의 수반 연산자를 구한다.

$$
\hat{K}^\dagger = (\hat{D} p \hat{D})^\dagger + q^\dagger = \hat{D}^\dagger p^\dagger \hat{D}^\dagger + q^\dagger
$$

$\hat{D}^\dagger = -\hat{D}$ 이고 $p, q$는 실수 함수(Self-adjoint)이므로 다음을 얻는다.

$$
\hat{K}^\dagger = (-\hat{D}) p (-\hat{D}) + q = \hat{D} p \hat{D} + q
$$

따라서,

$$
\hat{L}^{\dagger} = \hat{K}^{\dagger}\hat{w}^{\dagger} = -\{ \hat{D} p \hat{D} + q \} \frac{1}{w^\ast}
$$

(2) residue

조립 법칙 $\mathcal{R}(\hat{A}\hat{B}) = (\mathcal{R}\hat{A})\hat{B} + \hat{A}(\mathcal{R}\hat{B})$를 $\hat{L} = \hat{w}\hat{K}$에 적용한다.

$$
\mathcal{R} \hat{L} = (\mathcal{R} \hat{w}) \hat{K} + \hat{w} (\mathcal{R} \hat{K})
$$

함수 $\hat{w}$는 $\mathcal{R}\hat{w}=0$이므로, $\mathcal{R} \hat{L} = \hat{w} \mathcal{R} \hat{K}$가 된다. 내부의 $\mathcal{R}\hat{K}$를 전개하면 다음과 같다.

$$
\mathcal{R} \hat{L} = \hat{w} \{ (\mathcal{R} \hat{D}) p \hat{D} + \hat{D} p \mathcal{R} \hat{D} \}
$$

이 연산자를 브라-켓 $\langle \phi | \dots | \psi \rangle$ 사이에 넣고 계산한다.

$$
\langle \phi | \mathcal{R} \hat{L} | \psi \rangle = \langle \phi | \hat{w} (\mathcal{R} \hat{D}) p \hat{D} | \psi \rangle + \langle \phi | \hat{w} \hat{D} p \mathcal{R} \hat{D} | \psi \rangle
$$

항 1: $\hat{w}$와 $\phi$를 묶어 브라로 인식하면 $\hat{w}$는 실수 함수이므로 그대로 나온다.

$$
\langle \phi | \hat{w} (\mathcal{R} \hat{D}) p \hat{D} | \psi \rangle = [ \hat{w} \phi^* (p \psi') ]_a^b
$$

항 2: 브라 쪽에 있는 $\hat{w} \phi$에 $\hat{D}$가 작용해야 한다. $\hat{D}^\dagger = -\hat{D}$

$$
\langle -\hat{D}(\hat{w} \phi) | p \mathcal{R} \hat{D} | \psi \rangle = - [ (\hat{w}' \phi + \hat{w} \phi')^* (p \psi) ]_a^b
$$

최종 결과 (Honest Residue)

$$
\langle \phi | \mathcal{R} \hat{L} | \psi \rangle = -\frac{1}{w} [ p(x) (\phi^* \psi' - \phi'^* \psi) ]_a^b - \left[ p(x) \frac{w'(x)}{w(x)^2} \phi^* \psi \right]_a^b
$$

따라서, 매질의 가중치 변화($w'$)가 직접적인 레지듀 항으로 노출된다.

**2) 가중 내적 ($L^2_w$ Space)**

내적을 $\langle \phi | \psi \rangle_w = \int dx w \phi^* \psi$ 로 정의하는 일반적인 관찰자 시점이다. 가중내적이 곱해지므로 $\hat{K} = \hat{D} p \hat{D} + q$의 수반 연산자를 구하는것과 동일하다. 위의 결과에다가 $w(x)=1$과 동일하게 간주할 수 있다. 따라서,

$$
\text{formal adjoint: }
\hat{L}^{\dagger} = -( \hat{D} p \hat{D} + q ) 
$$

$$
\text{residue: }
\langle \phi | \mathcal{R} \hat{L} | \psi \rangle = - [ p (\phi^* \psi' - \phi'^* \psi) ]_a^b
$$