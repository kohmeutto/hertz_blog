+++
title = "(b) Adjoint & Residue transformation"
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

---

**3) 특성 3: 에르미트/반-에르미트 부분의 교환 가능성**

> **정리**: 연산자 $\hat{A}$가 정규 연산자인 것은, 그 에르미트 부분 $\hat{H} = \frac{1}{2}(\hat{A}+\hat{A}^\dagger)$와 반-에르미트 부분 $\hat{S} = \frac{1}{2}(\hat{A}-\hat{A}^\dagger)$가 서로 교환 가능한 것($[\hat{H}, \hat{S}]=0$)과 동치이다.

> **증명**:
> 1. $\hat{A}=\hat{H}+\hat{S}$ 이고 $\hat{A}^\dagger=\hat{H}-\hat{S}$ 이다.
> 2. 교환자 $[\hat{A}, \hat{A}^\dagger]$를 계산한다.
>
$$
\begin{align*}
[\hat{A}, \hat{A}^\dagger] &= (\hat{H} + \hat{S})(\hat{H} - \hat{S}) - (\hat{H} - \hat{S})(\hat{H} + \hat{S}) \\
&= (\hat{H}^2 - \hat{H}\hat{S} + \hat{S}\hat{H} - \hat{S}^2) - (\hat{H}^2 + \hat{H}\hat{S} - \hat{S}\hat{H} - \hat{S}^2) \\
&= -\hat{H}\hat{S} + \hat{S}\hat{H} - \hat{H}\hat{S} + \hat{S}\hat{H} \\
&= 2(\hat{S}\hat{H} - \hat{H}\hat{S}) = 2[\hat{S}, \hat{H}]
\end{align*}
$$
> 3. 따라서 $[\hat{A}, \hat{A}^\dagger]=0$인 것은 $[\hat{S}, \hat{H}]=0$, 즉 $[\hat{H}, \hat{S}]=0$인 것과 동치이다.

#### **특성 4: 연산자와 수반의 동일한 '크기'**

> **정리**: 연산자 $\hat{A}$가 정규 연산자인 것은, 모든 벡터 $|v\rangle$에 대해 $||\hat{A}|v\rangle|| = ||\hat{A}^\dagger|v\rangle||$ 인 것과 동치이다.

> **증명**: $ ||\hat{A}|v\rangle||^2 = \langle v|\hat{A}^\dagger\hat{A}|v\rangle$ 이고 $ ||\hat{A}^\dagger|v\rangle||^2 = \langle v|\hat{A}\hat{A}^\dagger|v\rangle$ 이다. 따라서 두 크기가 같은 것은 $\langle v|\hat{A}^\dagger\hat{A}|v\rangle = \langle v|\hat{A}\hat{A}^\dagger|v\rangle$ 와 동치이며, 이는 $\langle v|[\hat{A}^\dagger, \hat{A}]|v\rangle=0$을 의미한다. 모든 벡터에 대해 이 식이 성립하려면 연산자 $[\hat{A}^\dagger, \hat{A}]$가 0이어야 하므로, $\hat{A}$가 정규 연산자임과 동치이다.

#### **특성 5: 영공간과 열공간의 직교성**

> **정리**: 정규 연산자 $\hat{A}$의 영공간($N(A)$)은 그 열공간($C(A)$)과 항상 서로 수직이다.

> **증명**:
> 1. **보편적 원리**: 선형대수학의 기본 정리에 따라, 모든 행렬에 대해 영공간은 **행공간(Row Space, $C(A^T)$)**과 수직이다: $N(A) \perp C(A^T)$.
> 2. **정규 연산자의 특성**: 정규 연산자는 **열공간과 행공간이 같다**: $C(A) = C(A^T)$. (이는 특성 1로부터 유도된다. 영공간의 직교 보공간은 행공간($N(A)^\perp=C(A^T)$)이고, 좌측 영공간의 직교 보공간은 열공간($N(A^\dagger)^\perp=C(A)$)이다. 특성 1에서 $N(A)=N(A^\dagger)$이므로, 그 직교 보공간인 $C(A^T)$와 $C(A)$도 같다.)
> 3. **결론**: 따라서, 1번과 2번을 종합하면, 정규 연산자에 대해서는 $N(A) \perp C(A)$가 성립함이 증명된다. ✅

### 비교: 비정규 연산자


정규 연산자가 아닌 경우, 완비적인 고유벡터 기저를 갖지 못할 수 있다. 이러한 행렬을 '불완전 행렬(defective matrix)'이라고 한다. 이들은 공간을 순수하게 늘리거나 줄이는 것이 아닌, '찌그러뜨리는(shear)' 변환을 포함하여 안정적인 불변 방향이 부족하다.

- **예제 (비정규 행렬)**: $\hat{A} = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}$
    - $\hat{A}^\dagger = \begin{pmatrix} 1 & 0 \\ 1 & 1 \end{pmatrix}$
    - $[\hat{A}, \hat{A}^\dagger] = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix} \neq 0$ 이므로 정규 행렬이 아니다.
    - 이 행렬의 고유벡터는 $\begin{pmatrix} 1 \\ 0 \end{pmatrix}$ 방향 하나뿐이므로, 2차원 공간의 기저를 이룰 수 없다.

---
### 가역성 (Invertibility)

정규 연산자의 가역성은 고유값에 의해 결정된다. "가역적이다"라는 것은 "역변환이 존재한다"는 의미이며, 이는 "0으로 소멸되는 정보(영공간)가 없다"는 것과 같다.

- **가역적 정규 연산자 (Invertible Normal Operator)**
    - **조건**: **모든 고유값이 0이 아닐 때**.
    - **증명**: 행렬식은 고유값의 곱($\det(A) = \prod \lambda_i$)과 같다. 모든 고유값이 0이 아니면, 행렬식은 0이 아니므로 역행렬이 존재한다. 이 경우 영공간은 $\{0\}$ 뿐이다.
    - **물리적 의미**: 변환 과정에서 정보의 손실이 없으며, 0이 아닌 상태를 0 상태로 보내지 않는다.
    - **예제**: $\sigma_x = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}$는 정규(에르미트) 행렬이며, 고유값은 $1, -1$이므로 가역적이다.

- **비가역적 정규 연산자 (Non-invertible Normal Operator)**
    - **조건**: **적어도 하나의 고유값이 0일 때**.
    - **증명**: 고유값 중 0이 하나라도 포함되면, 행렬식($\det(A) = \prod \lambda_i$)은 0이 된다. 따라서 역행렬이 존재하지 않으며, 고유값 0에 해당하는 고유벡터들이 0이 아닌 영공간을 형성한다.
    - **물리적 의미**: 변환 과정에서 특정 상태(영공간)의 정보가 '소멸'된다.
    - **예제**: $\begin{pmatrix} 1 & 1 \\ 1 & 1 \end{pmatrix}$는 정규(에르미트) 행렬이며, 고유값은 $0, 2$이므로 비가역적이다.

---

### 심화(논문): : Derivation of Global Conservation Identities

앞선 챕터에서 언급된 바와 같이, 임의의 선형 연산자 $\hat{L}$에 대하여, 시스템의 경계 비대칭성을 추출하는 **레지듀 변환 $\mathcal{R}$** 은 힐베르트 공간 내에서 다음과 같이 정의된다. 이 정의는 모든 유도 과정의 출발점이자, 시스템의 '객관적 실재'와 '예측' 사이의 간극을 규정하는 공리이다.

$$
\langle \phi \mid \mathcal{R}\hat{L} \mid \psi \rangle \equiv \langle \phi \mid \hat{L} \psi \rangle - \langle \hat{L}^\dagger \phi \mid \psi \rangle
$$

**1) Operator Conservation Law**

아래 식은 연산자의 비정규성(Non-normality)이 상태 함수의 노름 변화와 경계 플럭스에 의해 어떻게 결정되는지 보여준다.

$$
\langle \psi \mid [\hat{L}^\dagger, \hat{L}] \mid \psi \rangle = \left( \|\hat{L}\psi\|^2 - \|\hat{L}^\dagger \psi\|^2 \right) + \langle \psi \mid \mathcal{R}_W(\hat{L}^\dagger, \hat{L}) \mid \psi \rangle
$$

$$
\mathcal{R}_\mathcal{W} = \begin{vmatrix} \mathcal{R}\hat{L}^\dagger & \mathcal{R}\hat{L} \\ \hat{L}^\dagger & \hat{L} \end{vmatrix}
$$

proof)

교환자 기댓값의 전개상태 $|\psi\rangle$에 대한 교환자 $[\hat{L}^\dagger, \hat{L}]$의 기댓값은 다음과 같다. 순수 수학적 정의이지만 직관적으로 이해하기 위해, "소자의 공간이 뒤틀린 것($[\hat{L}^\dagger, \hat{L}]$)이라면, 그 길을 지나가던 전자($|\psi\rangle$)가 겪은 변화의 기댓값이다." 라고 비유적으로 해석할 수 있다. 

$$
\langle \psi \mid [\hat{L}^\dagger, \hat{L}] \mid \psi \rangle = \langle \psi \mid \hat{L}^\dagger \hat{L} \mid \psi \rangle - \langle \psi \mid \hat{L} \hat{L}^\dagger \mid \psi \rangle
$$

레지듀 정의의 적용첫 번째 항 $\langle \psi \mid \hat{L}^\dagger (\hat{L}\psi) \rangle$에 대해, $\hat{L}^\dagger$를 브라 쪽으로 넘기기 위해 레지듀 정의를 적용한다.

$$
\langle \psi \mid \hat{L}^\dagger (\hat{L}\psi) \rangle = \langle \hat{L}\psi \mid \hat{L}\psi \rangle + \langle \psi \mid \mathcal{R}\hat{L}^\dagger \mid \hat{L}\psi \rangle = \|\hat{L}\psi\|^2 + \langle \psi \mid \mathcal{R}\hat{L}^\dagger \mid \hat{L}\psi \rangle
$$

$$
\langle \psi \mid \hat{L} (\hat{L}^\dagger \psi) \rangle = \langle \hat{L}^\dagger \psi \mid \hat{L}^\dagger \psi \rangle + \langle \psi \mid \mathcal{R}\hat{L} \mid \hat{L}^\dagger \psi \rangle = \|\hat{L}^\dagger \psi\|^2 + \langle \psi \mid \mathcal{R}\hat{L} \mid \hat{L}^\dagger \psi \rangle
$$

두 항을 결합한다.

$$
\langle \psi \mid [\hat{L}^\dagger, \hat{L}] \mid \psi \rangle = \left( \|\hat{L}\psi\|^2 - \|\hat{L}^\dagger \psi\|^2 \right) + \underbrace{\langle \psi \mid \mathcal{R}\hat{L}^\dagger \mid \hat{L}\psi \rangle - \langle \psi \mid \mathcal{R}\hat{L} \mid \hat{L}^\dagger \psi \rangle}_{\text{Residue Wronskian}}
$$

여기서 **레지듀 론스키안(Residue Wronskian) $\mathcal{R}_\mathcal{W}$** 를 다음과 같이 정의함으로써 첫 번째 최종 식을 얻는다.

$$
\mathcal{R}_\mathcal{W} = \begin{vmatrix} \mathcal{R}\hat{L}^\dagger & \mathcal{R}\hat{L} \\ \hat{L}^\dagger & \hat{L} \end{vmatrix}$$

$$
\langle \psi \mid [\hat{L}^\dagger, \hat{L}] \mid \psi \rangle = \left( \|\hat{L}\psi\|^2 - \|\hat{L}^\dagger \psi\|^2 \right) + \langle \psi \mid \mathcal{R}_W(\hat{L}^\dagger, \hat{L}) \mid \psi \rangle
$$

**2) Bulk-Boundary Dissipation Theorem**

아래 식은 하이젠베르크 운동 방정식에 기반하여 시스템의 에너지 변화(소산)를 정량화한다. 즉, 시스템 내부의 저항적 변화량(Internal Friction)은 벌크 영역의 에너지 비대칭성과 경계면에서의 유출입량의 합으로 결정된다.

$$
\underbrace{\langle \psi \mid [\hat{H}, \hat{A}] \mid \psi \rangle}_{\text{Internal Friction}} = \frac{1}{2} \underbrace{\left( \|\hat{L}\psi\|^2 - \|\hat{L}^\dagger \psi\|^2 \right)}_{\text{Net Energy Gap}} + \underbrace{\langle \psi \mid \mathcal{R}_W (\hat{H}, \hat{A}) \mid \psi \rangle}_{\text{Residue Wronskian}}
$$

proof)

해밀토니안 소산 구조를 설정한다. 임의의 연산자 $\hat{L}$ 에 대하여, 허미션 파트 $\hat{H}$ 와 반-허미션 파트 $\hat{A}$ 는 다음과 같이 정의된다.

$$\hat{L} = \hat{H} + \hat{A}$$
$$\hat{L}^\dagger = \hat{H} - \hat{A} \quad (\text{단, } \hat{H}^\dagger = \hat{H}, \hat{A}^\dagger = -\hat{A})$$

교환자의 내적 전개 (Expansion of Commutator)를 한다. 에너지로 비유를 하면, 순간 내부 마찰에 의해 에너지가 열로 전환되고 있는 소산율(Dissipation Rate)의 기댓값을 의미한다. 예시가 아닌 식 자체로의 본질적인 해석은 시스템의 동역학적 불일치를 보여주는 핵심 지표이다.
 
$$
\langle \psi \mid [\hat{H}, \hat{A}] \mid \psi \rangle = \langle \psi \mid \hat{H}\hat{A} \mid \psi \rangle - \langle \psi \mid \hat{A}\hat{H} \mid \psi \rangle
$$
  
여기서 우리가 이전에 정의한 **레지듀 변환($\mathcal{R}$)** 을 사용한다. 연산자를 브라(Bra) 쪽으로 넘길 때 발생하는 경계 오차를 보정해주는 규칙이다.

$$
\langle \psi \mid \hat{H}(\hat{A}\psi) \rangle = \langle \hat{H}^\dagger \psi \mid \hat{A}\psi \rangle + \langle \psi \mid \mathcal{R}\hat{H} \mid \hat{A}\psi \rangle$$

$$\langle \psi \mid \hat{A}(\hat{H}\psi) \rangle = \langle \hat{A}^\dagger \psi \mid \hat{H}\psi \rangle + \langle \psi \mid \mathcal{R}\hat{A} \mid \hat{H}\psi \rangle$$

두 식을 빼면 다음과 같다.

$$
\langle \psi \mid [\hat{H}, \hat{A}] \mid \psi \rangle = \left( \langle \hat{H} \psi \mid \hat{A} \psi \rangle + \langle \hat{A} \psi \mid \hat{H} \psi \rangle \right) + \left( \langle \psi \mid \mathcal{R} \hat{H} (\hat{A}\psi) \rangle - \langle \psi \mid \mathcal{R} \hat{A} (\hat{H}\psi) \rangle \right)
$$

위 식에서 첫번째 괄호는 복소 내적의 성질을 이용해 다음과 같이 변환된다.

$$
\langle \hat{H} \psi \mid \hat{A} \psi \rangle + \langle \hat{A} \psi \mid \hat{H} \psi \rangle = 2 \text{Re} \langle \hat{H} \psi \mid \hat{A} \psi \rangle
$$

여기서 $\hat{L} = \hat{H} + \hat{A}$ 와 $\hat{L}^\dagger = \hat{H} - \hat{A}$ 의 노름(Norm) 차이를 계산해 본다.

$$
\|\hat{L}\psi\|^2 = \|\hat{H}\psi + \hat{A}\psi\|^2 = \|\hat{H}\psi\|^2 + \|\hat{A}\psi\|^2 + 2 \text{Re} \langle \hat{H} \psi \mid \hat{A} \psi \rangle
$$

$$\|\hat{L}^\dagger\psi\|^2 = \|\hat{H}\psi - \hat{A}\psi\|^2 = \|\hat{H}\psi\|^2 + \|\hat{A}\psi\|^2 - 2 \text{Re} \langle \hat{H} \psi \mid \hat{A} \psi \rangle
$$

따라서, 두 노름의 차이는 다음과 같이 정의된다.

$$
\frac{1}{2} \left( \|\hat{L}\psi\|^2 - \|\hat{L}^\dagger \psi\|^2 \right) = 2 \text{Re} \langle \hat{H} \psi \mid \hat{A} \psi \rangle
$$

이것이 바로 시스템의 벌크 영역에서 발생하는 Net Energy Gap (순수 에너지 불균형) 항이다. 유도 과정에서 남은 경계 보정 항들을 묶어 레지듀 론스키안 $\mathcal{R}_W$로 정의한다.

$$
\langle \psi \mid \mathcal{R}_W (\hat{H}, \hat{A}) \mid \psi \rangle = \langle \psi \mid \mathcal{R}\hat{H} \mid \hat{A} \psi \rangle - \langle \psi \mid \mathcal{R}\hat{A} \mid \hat{H} \psi \rangle
$$

이 항은 연산자의 비가환성(Non-commutativity)이 경계면(Boundary)에서 어떻게 소산으로 나타나는지를 수학적으로 포착한다. 위의 과정들을 병합하면 최종 정리 형태가 도출된다.

$$
\langle \psi \mid [\hat{H}, \hat{A}] \mid \psi \rangle = \frac{1}{2} \left( \|\hat{L}\psi\|^2 - \|\hat{L}^\dagger \psi\|^2 \right) + \langle \psi \mid \mathcal{R}_W (\hat{H}, \hat{A}) \mid \psi \rangle
$$

**3) 레지듀 론스키안의 물리적 의미**

레지듀 론스키안은 단순한 수학적 잔여항이 아니라, 시스템의 **실재(Reality)** 와 이를 수용하는 경계의 관측(Observation) 사이의 위상적 불일치를 정량화하는 지표이다. 이를 **'위상적 틀어짐(Topological Skewness)'** 의 관점에서 기술한다.

(1) 열벡터 구조와 위상 공간의 축 정의

레지듀 론스키안 행렬 $\mathcal{R}_\mathcal{W}$를 구성하는 두 열벡터는 시스템을 기술하는 두 개의 독립적인 위상 축(Basis)으로 해석된다.

$$
\mathcal{R}_\mathcal{W} = \begin{vmatrix} \mathbf{v}_1 & \mathbf{v}_2 \end{vmatrix} = \begin{vmatrix} \mathcal{R}\hat{L}^\dagger & \mathcal{R}\hat{L} \\ \hat{L}^\dagger & \hat{L} \end{vmatrix}
$$

- 제1열 ($\mathbf{v}_1$, 관측 축): 전극(Contact)이 전자를 받아들이기 위해 설정한 **수용 조건(Lens Profile)** 이다. 이는 시스템이 외부와 소통하는 관측의 기준선을 의미한다.
- 제2열 ($\mathbf{v}_2$, 실재 축): 채널(Channel) 내부에서 전자가 실제로 보여주는 **물리적 거동(Object Profile)** 이다. 이는 관측자와 무관하게 존재하는 시스템의 실재를 의미한다.

(2) 행렬식(Determinant)과 에너지 소산의 메커니즘

행렬식 $\mathcal{R}_\mathcal{W}$은 두 위상 축이 이루는 평행사변형의 면적을 의미하며, 이는 곧 '관측'과 '실재'가 경계면에서 얼마나 어긋나 있는지를 나타내는 **'위상적 마찰 계수'** 가 된다.

- 정합 상태 ($\text{det} \approx 0$): 관측 축과 실재 축이 평행하거나 직교성을 유지하여, 전자가 자신의 파동 형태를 바꾸지 않고 전극으로 부드럽게 전이되는 상태이다.
- 뒤틀림 상태 ($\text{det} \neq 0$): 두 축 사이의 각도가 좁아지며 위상 공간이 찌그러지는 상태이다. 전자는 전극의 수용 조건에 맞추기 위해 자신의 양자 상태를 억지로 변형시켜야 하며, 이 과정에서 발생하는 **'수학적 불일치의 총량'** 이 물리적인 **에너지 소산(Dissipation)** 으로 치환된다.