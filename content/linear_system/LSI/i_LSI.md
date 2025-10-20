+++
title = "(i) LSI"
weight = 1
+++

---

### 1. LSI

Linear + Shift Invarience

---

### 2. Linearity(선형성)=Superpostion

Superposition은 Linearity 와 동치이다. 따라서, 두가지 용어를 system 에서 혼용해서 사용해도 같은 의미임을 상기하라.

$$
\text{Superposition}=\text{Addictivity}+\text{Scaling}
$$

$$
\hat{H}(a|\psi_1\rangle+b|\psi_2\rangle)
=a\hat{H}|\psi_1\rangle+b\hat{H}|\psi_2\rangle
$$

---

### 3. Copy-shift invarience

(1) LSI 연산자는 copy-shift 연산자와 교환가능하다. 

- 이동 불변 시스템이란 시스템을 작동시키는 근본적인 규칙(rule)이 이동(시간,공간) 등에 따라 변하지 않는다는 의미한다. 
- 따라서 동일한 모양의 입력을 언제 넣든지 상관없이, 출력은 항상 **똑같은 모양으로 나온다.**

$$
|\varphi(t)\rangle=\hat{H}|\psi(t)\rangle
\implies
\hat{S}_\tau|\varphi(t)\rangle
=\hat{S}_\tau\hat{H}|\psi(t)\rangle
=\hat{H}\hat{S}_\tau|\psi(t)\rangle
$$

(2) 변화량은 0이다.

---

**LSI 연산자 정리**

(1) $\hat{H}|x'\rangle=|h(x-x')\rangle$

(2) $\hat{H}=|h\rangle\ast=\int dx' |h(x-x')\rangle\langle x'|$

(3) $\hat{H}=|h\rangle\ast=\int ds H(s)|s\rangle\langle s|$

---

### 1. LSI

LSI operator(system) 이 가지는 특성은 아래와 같다.

**(1) Linearity(선형성)=Superpostion**

Superposition은 Linearity 와 동치이다. 따라서, 두가지 용어를 system 에서 혼용해서 사용해도 같은 의미임을 상기하라.

$$
\text{Superposition}=\text{Addictivity}+\text{Scaling}
$$

$$
\hat{H}(a|\psi_1\rangle+b|\psi_2\rangle)
=a\hat{H}|\psi_1\rangle+b\hat{H}|\psi_2\rangle
$$

**(2) Shift invarient**

- 이동 불변 시스템이란 시스템을 작동시키는 근본적인 규칙(rule)이 이동(시간,공간) 등에 따라 변하지 않는다는 의미한다. 
- 따라서 동일한 모양의 입력을 언제 넣든지 상관없이, 출력은 항상 **똑같은 모양으로 나온다.**

$$
|\varphi(t)\rangle=\hat{H}|\psi(t)\rangle
\implies
\hat{S}_\tau|\varphi(t)\rangle
=\hat{S}_\tau\hat{H}|\psi(t)\rangle
=\hat{H}\hat{S}_\tau|\psi(t)\rangle
$$

- '똑같은 모양으로 나온다.'의 의미는 단지 출력이 **평행 이동**할 뿐이다.

$$
h(u,u')=h(u-u')
$$

proof)

$$
\langle u|\hat{S}_\tau\hat{H}|u'\rangle
=\langle u|\hat{H}\hat{S}_\tau|u'\rangle
$$


---

### 2. LSI 연산자

아래 형태는 선형이기만 하면 어떤 변환이든 표현할 수 있다. 하지만 아직 이동 불변(Shift-Invariance) 조건은 포함하지 않았다.

$$
\hat{H}=\iint du du' \frac{1}{\gamma_u\gamma_{u'}} h(u,u')|u\rangle\langle u'|
$$

이 일반적인 형태에 **"LSI 시스템"** 이라는 강력한 제약 조건을 걸어본다. 이동 불변은 위에서 보다 싶이, 평행이동을 의미한다.

$$
\hat{H}
=\iint du du' \frac{1}{\gamma_u\gamma_{u'}} h(u-u')|u\rangle\langle u'|
$$

임펄스 기저와의 연산을 수행해보자.

$$
\langle u|\hat{H}|f\rangle
=\iint d\tau du' \frac{1}{\gamma_\tau\gamma_{u'}} h(\tau-u')\langle u|\tau\rangle\langle u'|f\rangle
=\iint d\tau du' \frac{1}{\gamma_\tau\gamma_{u'}} h(\tau-u')\gamma_{u}\delta(u-\tau)\gamma_{u'}f(u')
$$

$$
=\int du' h(u-u') f(u')
$$

$$
=:h(u)\ast f(u)
=\langle u^d|(|h\rangle\ast|f\rangle)
=\gamma_u^{-1}\langle u|(|h\rangle\ast|f\rangle)
$$

만약, 기저가 $|x\rangle$ 또는 $|t\rangle$ 라면,

$$
\hat{H} = |h\rangle\ast
$$

---

### 3.모든 LSI 연산자는 합성곱 귀결된다.

LSI(선형 이동 불변) 연산자의 대표적인 (일부)예시들은 다음과 같다. **예외 없이 모든 LSI 연산자들은 합성곱(Convolution)으로 표현** 될 수 있다는 공통점을 가진다.

- 미분 (Differentiation)

$$
|\psi'\rangle=\hat{D}|\psi\rangle
$$

$$
\psi'(x)=\langle x|\psi'\rangle=\langle x|\hat{D}|\psi\rangle=\frac{d}{dx}\psi(x)
$$


- 적분 (Integration)

$$
|g\rangle=\hat{D}^{-1}|f\rangle
$$

$$
g(x)=\langle x|g\rangle=\langle x|\hat{D}^{-1}|f\rangle=\int dx f(x)
$$

- 이동 (Shift / Delay)

$$
|\psi(t-\tau)\rangle=\hat{S}_{\tau}|\psi(t)\rangle
$$

- 스케일링 (Scaling)

$$
|a\psi\rangle=a|\psi\rangle
$$

---

### 4. 연산자의 합성

이 내용은 선형 부품(작은 선형 시스템)이 모였을 때 만들어지는 회로 전체(큰 시스템)을 왜 선형시스템으로 볼 수 있는지에 대한 설명이 가능하다.

**(1) 선형연산자 + 선형연산자 = 선형연산자**

- 직렬합성(Series Combination)

$$
\hat{T}=\hat{L}_2\hat{L}_1
$$

$$
\hat{T}(a_1|\psi_1\rangle+a_2|\psi_2\rangle)=\hat{L}_2\hat{L}_1(a_1|\psi_1\rangle+a_2|\psi_2\rangle)
$$

$$
=\hat{L}_2(a_1\hat{L}_1|\psi_1\rangle+a_2\hat{L}_1|\psi_2\rangle)
$$

$$
=a_1\hat{L}_2\hat{L}_1|\psi_1\rangle+a_2\hat{L}_2\hat{L}_1|\psi_2\rangle
$$

$$
=a_1\hat{T}_1|\psi_1\rangle+a_2\hat{T}_1|\psi_2\rangle
$$

- 병렬합성(Parallel Combination)

$$
\hat{T}=\hat{L}_1+\hat{L}_2
$$

$$
\hat{T}(a_1|\psi_1\rangle+a_2|\psi_2\rangle)=(\hat{L}_1+\hat{L}_2)(a_1|\psi_1\rangle+a_2|\psi_2\rangle)
$$

$$
=(a_1\hat{L}_1|\psi_1\rangle+a_2\hat{L}_1|\psi_2\rangle)+(a_1\hat{L}_2|\psi_1\rangle+a_2\hat{L}_2|\psi_2\rangle)
$$

$$
=a_1(\hat{L}_1+\hat{L}_2)|\psi_1\rangle+a_2(\hat{L}_1+\hat{L}_2)|\psi_2\rangle
$$

$$
=a_1\hat{T}_1|\psi_1\rangle+a_2\hat{T}_1|\psi_2\rangle
$$

**(2) 선형연산자 + 비선형연산자 = 비선형연산자**

- 직렬합성(Series Combination)

$$
\hat{T}=\hat{L}\hat{N}
$$

$$
\hat{T}(a_1|\psi_1\rangle+a_2|\psi_2\rangle)=\hat{L}\hat{N}(a_1|\psi_1\rangle+a_2|\psi_2\rangle)
$$

$$
\ne a_1\hat{T}_1|\psi_1\rangle+a_2\hat{T}_1|\psi_2\rangle
$$

- 병렬합성(Parallel Combination)

$$
\hat{T}=\hat{L}+\hat{N}
$$

$$
\hat{T}(a_1|\psi_1\rangle+a_2|\psi_2\rangle)=(\hat{L}+\hat{N})(a_1|\psi_1\rangle+a_2|\psi_2\rangle)
$$

$$
=(a_1\hat{L}|\psi_1\rangle+a_2\hat{L}|\psi_2\rangle)+\hat{N}(a_1|\psi_1\rangle+a_2|\psi_2\rangle)
$$

$$
\ne a_1\hat{T}_1|\psi_1\rangle+a_2\hat{T}_1|\psi_2\rangle
$$

---

**example)** $|f\rangle+$ 연산자는 선형인가.



---

이동 불변성이란, 시스템 Ĥ의 작동 방식이 좌표의 원점에 의존하지 않음을 의미합니다. 🧠이것을 연산자로 표현하면,입력을 먼저 τ만큼 이동시키고 시스템에 넣는 것 (Ĥ(Ŝ_τ|ψ⟩))과,입력을 시스템에 넣은 후 그 출력을 τ만큼 이동시키는 것 (Ŝ_τ(Ĥ|ψ⟩))이,어떤 입력 |ψ⟩에 대해서도 항상 동일한 결과를 내놓는다는 뜻입니다.수학적으로 이것은 두 연산자의 순서를 바꿔도 결과가 같다는 의미이며, 이를 **교환 법칙(Commutation relation)**이 성립한다고 말합니다.

$$\hat{S}_\tau\hat{H} = \hat{H}\hat{S}_\tau \quad \iff \quad [\hat{S}_\tau, \hat{H}] = \hat{S}_\tau\hat{H} - \hat{H}\hat{S}_\tau = 0
$$

따라서 **"시스템이 이동 불변이다"** 라는 물리적 조건과 **"시스템 연산자 `Ĥ`가 이동 연산자 `Ŝ_τ`와 교환 가능하다"** 는 수학적 조건은 완벽하게 동일한 말입니다.

### 3. 증명: `[Ŝ_τ, Ĥ] = 0` ⇔ `h(u, u') = h(u-u')`

이제 이동 불변 조건(`LHS = RHS`)으로부터 시스템 커널의 형태를 유도해 보겠습니다.

**좌변(LHS) 계산: `⟨u|Ŝ_τĤ|u'⟩`**

1.  연산자 `Ĥ`의 정의는 `⟨α|Ĥ|β⟩ = h(α, β)` 입니다. (`γ`는 계산의 편의를 위해 생략하겠습니다. 이전 논의에서 `γ`가 최종 결과에 영향을 주지 않음을 보였습니다.)
2.  `Ĥ`와 `|u'⟩` 사이에 단위 연산자 `∫dα|α⟩⟨α|` 를 삽입합니다.

$$
\text{LHS} = \langle u|\hat{S}*\\tau \\left( \\int d\alpha |\alpha\\rangle\langle\\alpha| \\right) \\hat{H}|u'\rangle
\= \int d\\alpha \\langle u|\\hat{S}*\\tau|\\alpha\\rangle \\langle\\alpha|\\hat{H}|u'\\rangle
$$

이제 각 항을 계산합니다.⟨u|Ŝ_τ|α⟩: 이동 연산자의 작용 Ŝ_τ|α⟩ = |α+τ⟩에 의해, ⟨u|α+τ⟩가 됩니다. 이는 정규직교 기저에서 δ(u - (α+τ)) 와 같습니다.⟨α|Ĥ|u'⟩: 이것이 바로 시스템 커널의 정의인 h(α, u') 입니다.결과를 대입하고 적분합니다.

$$
\text{LHS} = \int d\alpha\\ \delta(u - \alpha - \tau) h(\alpha, u')
$$

델타 함수의 성질에 의해, 적분 내의 모든 α는 u-τ로 바뀝니다.

$$\text{LHS} = h(u-\tau, u')$$

우변(RHS) 계산: ⟨u|ĤŜ_τ|u'⟩이번에는 Ĥ와 Ŝ_τ 사이에 단위 연산자 ∫dβ|β⟩⟨β| 를 삽입합니다.

$$
\text{RHS} = \langle u|\hat{H} \left( \int d\beta |\beta\rangle\langle\beta| \right) \hat{S}*\tau|u'\rangle
\
= \int d\beta \langle u|\hat{H}|\beta\rangle \langle\beta|\hat{S}*\tau|u'\rangle
$$

각 항을 계산합니다.⟨u|Ĥ|β⟩: 커널의 정의에 따라 h(u, β) 입니다.⟨β|Ŝ_τ|u'⟩: 이동 연산자의 작용 Ŝ_τ|u'⟩ = |u'+τ⟩에 의해, ⟨β|u'+τ⟩가 됩니다. 이는 δ(β - (u'+τ)) 와 같습니다.결과를 대입하고 적분합니다.

$$\text{RHS} = \int d\beta\\ h(u, \beta) \delta(\beta - u' - \tau)$$

델타 함수의 성질에 의해, 적분 내의 모든 β는 u'+τ로 바뀝니다.

$$\text{RHS} = h(u, u'+\tau)$$

결론: 두 결과의 비교이동 불변 조건은 LHS = RHS 이므로, 우리는 다음의 함수 방정식을 얻습니다.

$$h(u-\tau, u') = h(u, u'+\tau)$$

이 등식은 **모든 `τ`에 대해** 항상 성립해야 합니다. 이제 이 방정식의 의미를 파악하기 위해 변수를 치환해 봅시다.

* `x = u-\tau`
* `y = u'`

그러면 `u = x+τ` 이므로, 위 식은 `h(x, y) = h(x+τ, y+τ)` 가 됩니다.
이것은 함수 `h`의 값이 **두 인자를 똑같이 이동시켜도 변하지 않는다**는 것을 의미합니다. 이러한 성질을 가지는 함수는 오직 **두 인자의 차이**에만 의존하는 함수뿐입니다.

따라서, 어떤 함수 `g`에 대해 다음과 같이 쓸 수 있습니다.

$$h(u, u') = g(u-u')
$$**증명 완료.** ✅

따라서, 연산자 `Ĥ`와 `Ŝτ`가 교환 가능하다는 추상적인 조건은, 시스템의 커널 `h(u, u')`가 오직 두 좌표의 차이 `u-u'`에만 의존해야 한다는 구체적인 함수 형태와 완벽하게 동일한 의미임을 증명한 것입니다.$$