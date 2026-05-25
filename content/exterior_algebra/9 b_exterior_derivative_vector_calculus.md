+++
title = "외미분과 벡터 미적분"
weight = 9
+++

### 1. 동기: 익숙한 미분들의 통일

§8 에서 외미분 $d$ 가 *모든 차수의 미분형식 사이를 잇는 통합된 연산자* 임을 봤다. 그리고 *3D 에서의 구체적 계산* 을 통해

- 0-form 의 외미분 = 그라디언트의 정보 (1-form 으로 인코딩)
- 1-form 의 외미분 ≈ 회전의 정보 (2-form 으로 인코딩)
- 2-form 의 외미분 ≈ 발산의 정보 (3-form 으로 인코딩)

이라는 *대응 관계* 도 살짝 언급했다. 

이 장에서는 *그 대응을 정확히* 본다. *왜* 외미분이 *우리가 익숙한 벡터 미적분 연산자들* 과 정확히 같은 일을 하는지, *어떤 변환* 을 통해 둘이 동일시되는지를 정리한다.

핵심 메시지는:

> 3차원 공간에서 그라디언트·회전·발산은 *외미분 $d$ 의 세 가지 다른 모습*일 뿐. 이들이 *동일한 연산자의 다른 표현*임이 외대수 언어로 명확해진다.

이게 분명해지면, *4차원 이상* 으로 가도 *회전이라는 익숙한 개념이 왜 사라지는지* 와 *그래도 외미분이 모든 차원에서 작동하는 이유* 가 자연스럽게 보인다.

### 2. 벡터와 1-form 사이의 다리: 음악적 동형사상

먼저 *익숙한 벡터장 시각* 과 *미분형식 시각* 사이의 다리를 놓아야 한다. 그게 *음악적 동형사상 (musical isomorphism)*.

**왜 다리가 필요한가?**

§6 §7 에서 강조했듯, *벡터와 1-form 은 다른 종류의 객체*다. 벡터는 *벡터 공간 $T_p M$* 에 살고, 1-form 은 *그 쌍대 공간 $T_p^* M$* 에 산다. 두 공간이 차원은 같지만 *자동으로* 동일시되지는 않는다.

그런데 *내적 (또는 더 일반적으로 메트릭)* 이 주어지면 *자연스러운 동일시* 가 가능해진다. 이게 음악적 동형사상.

**플랫과 샵 (flat and sharp)**

표준 내적이 있는 $\mathbb{R}^n$ 에서, 두 변환을 정의한다.

*플랫 $\flat$* (벡터 → 1-form): 벡터 $\vec{v}$ 에 대응하는 1-form $\vec{v}^\flat$ 을

$$\vec{v}^\flat(\vec{w}) := \vec{v} \cdot \vec{w}$$

로 정의. 즉 *벡터 $\vec{v}$ 와의 내적* 으로 정의되는 1-form. 

*샵 $\sharp$* (1-form → 벡터): 1-form $\alpha$ 에 대응하는 벡터 $\alpha^\sharp$ 를

$$\alpha(\vec{w}) = \alpha^\sharp \cdot \vec{w} \quad \forall \vec{w}$$

가 성립하도록 *유일하게* 잡는다.

**구체적 표현 (표준 좌표)**

표준 좌표에서 벡터 $\vec{v} = (v^1, v^2, \ldots, v^n)$ 의 플랫은

$$\vec{v}^\flat = v^1\, dx^1 + v^2\, dx^2 + \cdots + v^n\, dx^n$$

(*성분이 그대로 1-form 의 계수* 가 된다 — 표준 좌표에서.) 

샵은 그 역으로, 1-form $\alpha = \alpha_1\, dx^1 + \cdots + \alpha_n\, dx^n$ 의 샵은 *같은 성분을 갖는 벡터*

$$\alpha^\sharp = (\alpha_1, \alpha_2, \ldots, \alpha_n)$$

**음악 기호 이유**

기호 $\flat$ (flat) 과 $\sharp$ (sharp) 는 음악에서 따 온 것. *플랫은 인덱스를 내려서* (위 첨자 → 아래 첨자) 벡터를 1-form 으로 만들고, *샵은 인덱스를 올려서* 1-form 을 벡터로 만든다는 비유. 텐서 표기에서 *공변 (아래 인덱스)* ↔ *반변 (위 인덱스)* 변환의 의미.

**메트릭이 없으면?**

표준 내적 없이도 $\flat, \sharp$ 가 가능한가? *일반적으로 아니다*. 다양체에 *메트릭 $g_{ij}$* 가 주어져야 가능. 메트릭 없는 다양체 (예: 위상학적 다양체) 에서는 벡터와 1-form 이 *진정 다른 종류의 객체*.

이 장에서는 $\mathbb{R}^3$ 의 표준 내적을 가정하고 진행한다.

### 3. 0-form 의 외미분 = 그라디언트

가장 단순한 경우부터 다시 정리한다.

함수 $f$ (= 0-form) 의 외미분:

$$df = \frac{\partial f}{\partial x}\, dx + \frac{\partial f}{\partial y}\, dy + \frac{\partial f}{\partial z}\, dz$$

이 1-form 의 *샵* 을 취하면 (성분이 그대로):

$$(df)^\sharp = \left(\frac{\partial f}{\partial x},\, \frac{\partial f}{\partial y},\, \frac{\partial f}{\partial z}\right) = \nabla f$$

따라서:

> **대응**: $(df)^\sharp = \nabla f$, 또는 동치로 $\nabla f$ 의 1-form 표현이 $df$.

음악적 동형사상을 통해 *그라디언트의 1-form 버전이 정확히 함수의 외미분*. 

**기하학적 의미의 재확인**

§6 에서 본 것처럼, $df(v) = \nabla f \cdot v$ 가 *$v$ 방향의 방향 미분*. 그라디언트가 *함수가 가장 빠르게 증가하는 방향과 그 변화율을 담은 벡터*. 두 시각이 같은 정보 — 그러나 *언어가 다름*.

미분형식 언어의 장점: *메트릭 없이도 $df$ 가 잘 정의됨*. 그라디언트는 *내적이 있어야* 정의 가능. 

### 4. 1-form 의 외미분 = 회전 (3D)

3D 에서 1-form 의 외미분이 *어떻게 회전과 일치* 하는지 자세히 본다.

**시작: 벡터장의 1-form 버전**

벡터장 $\vec{F} = (P, Q, R)$ 의 *1-form 버전* 은 플랫:

$$\omega_F := \vec{F}^\flat = P\, dx + Q\, dy + R\, dz$$

**외미분 계산 (§8 결과)**

§8 §6 의 예제 2 에서 계산했듯:

$$d\omega_F = \left(\frac{\partial R}{\partial y} - \frac{\partial Q}{\partial z}\right) dy \wedge dz + \left(\frac{\partial P}{\partial z} - \frac{\partial R}{\partial x}\right) dz \wedge dx + \left(\frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y}\right) dx \wedge dy$$

(부호를 §7 §5 의 표준 정렬 — $dy \wedge dz, dz \wedge dx, dx \wedge dy$ — 로 맞춤.)

이 *세 계수* 가 정확히 회전 $\nabla \times \vec{F}$ 의 *세 성분*:

$$\nabla \times \vec{F} = \left(\frac{\partial R}{\partial y} - \frac{\partial Q}{\partial z},\; \frac{\partial P}{\partial z} - \frac{\partial R}{\partial x},\; \frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y}\right)$$

**2-form 의 벡터장 버전 (Hodge 별표의 미리보기)**

3D 에서 *2-form 을 벡터장에 대응시키는* 자연스러운 변환 — 이게 *Hodge 별표 $\star$*. 자세한 정의는 §13, 지금은 *결과만 사용*. 표준 좌표에서:

$$\star(dy \wedge dz) = dx, \quad \star(dz \wedge dx) = dy, \quad \star(dx \wedge dy) = dz$$

즉 *2-form 의 기저를 1-form 의 기저로* 자연스럽게 보내는 변환. (이 대응이 가능한 이유는 §4 의 *3D 차원 우연* — 2-form 의 기저 수 (3) = 1-form 의 기저 수 (3).)

**합치면**: 

$$d\omega_F = \left(\frac{\partial R}{\partial y} - \frac{\partial Q}{\partial z}\right) dy \wedge dz + \cdots$$

이 2-form 에 $\star$ 를 적용하면

$$\star d\omega_F = \left(\frac{\partial R}{\partial y} - \frac{\partial Q}{\partial z}\right) dx + \left(\frac{\partial P}{\partial z} - \frac{\partial R}{\partial x}\right) dy + \left(\frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y}\right) dz$$

이 1-form 의 샵을 다시 취하면 *벡터장*

$$(\star d\omega_F)^\sharp = \nabla \times \vec{F}$$

따라서:

> **대응**: $(\star d \vec{F}^\flat)^\sharp = \nabla \times \vec{F}$
> 
> 즉 *플랫 → 외미분 → Hodge → 샵* 의 합성이 회전과 같음.

**왜 이렇게 복잡한가?**

벡터 미적분의 *회전 연산자* 는 *벡터장을 벡터장으로* 보낸다. 외미분 $d$ 는 *1-form 을 2-form 으로* 보낸다. 두 연산자가 *같은 정보를 다룬다* 는 걸 확인하려면 양쪽을 *공통 언어 (벡터 또는 미분형식)* 로 바꿔야 함.

위 *플랫-d-Hodge-샵* 의 체인이 그 *벡터 ↔ 미분형식 변환의 명시적 경로*.

### 5. 2-form 의 외미분 = 발산 (3D)

비슷하게 *2-form 의 외미분이 발산과 일치* 함을 본다.

**시작: 벡터장의 2-form 버전**

벡터장 $\vec{F} = (P, Q, R)$ 의 *2-form 버전* 은 Hodge 별표를 통해:

$$\eta_F := \star \vec{F}^\flat = P\, dy \wedge dz + Q\, dz \wedge dx + R\, dx \wedge dy$$

(*벡터장의 플럭스 형식* — 면 적분에서 자연스럽게 등장하는 형태.)

**외미분 계산 (§8 결과)**

§8 §6 의 예제 3 에서 계산했듯:

$$d\eta_F = \left(\frac{\partial P}{\partial x} + \frac{\partial Q}{\partial y} + \frac{\partial R}{\partial z}\right) dx \wedge dy \wedge dz$$

세 *편미분의 합* — 정확히 *발산*:

$$\nabla \cdot \vec{F} = \frac{\partial P}{\partial x} + \frac{\partial Q}{\partial y} + \frac{\partial R}{\partial z}$$

**3-form 의 함수 버전**

3D 에서 *3-form 을 함수에 대응* 시키는 변환도 Hodge 별표:

$$\star(dx \wedge dy \wedge dz) = 1$$

즉 부피 형식을 *스칼라 1* 로 보내는 변환. 이건 *최고차 외승의 1차원성* (§4) 의 자연스러운 결과.

**합치면**:

$$\star d\eta_F = \nabla \cdot \vec{F}$$

발산이 *0-form* (즉 함수) 으로 자연스럽게 나옴.

> **대응**: $\star d (\star \vec{F}^\flat) = \nabla \cdot \vec{F}$
> 
> 즉 *플랫 → Hodge → 외미분 → Hodge* 의 합성이 발산.

### 6. 3D 의 통일된 de Rham 사슬

위의 세 대응을 한 다이어그램으로 정리하면 *3D 의 통일된 구조* 가 보인다.

$$\Omega^0(\mathbb{R}^3) \;\xrightarrow{d}\; \Omega^1(\mathbb{R}^3) \;\xrightarrow{d}\; \Omega^2(\mathbb{R}^3) \;\xrightarrow{d}\; \Omega^3(\mathbb{R}^3)$$

각 단계가 정확히 *벡터 미적분의 한 연산자* 와 대응:

| 미분형식 사슬 | 벡터 미적분 |
|---|---|
| $\Omega^0$ (함수) | 스칼라장 |
| $\Omega^1$ (1-form) | 벡터장 |
| $\Omega^2$ (2-form) | 벡터장 |
| $\Omega^3$ (3-form) | 스칼라장 (밀도) |
| $d: \Omega^0 \to \Omega^1$ | 그라디언트 $\nabla f$ |
| $d: \Omega^1 \to \Omega^2$ | 회전 $\nabla \times \vec{F}$ |
| $d: \Omega^2 \to \Omega^3$ | 발산 $\nabla \cdot \vec{F}$ |

이 표가 *3D 벡터 미적분이 외미분의 세 가지 모습일 뿐* 임을 명확히 보여준다.

**$d^2 = 0$ 의 익숙한 결과들 (재확인)**

이 사슬에서 *연속된 두 $d$ 를 합성* 하면 항상 0:

$d: \Omega^0 \to \Omega^1$ 다음 $d: \Omega^1 \to \Omega^2$ 의 합성 = 0:

$$d^2 f = 0 \quad \Longleftrightarrow \quad \nabla \times (\nabla f) = \vec{0}$$

*그라디언트의 회전은 0*. 

$d: \Omega^1 \to \Omega^2$ 다음 $d: \Omega^2 \to \Omega^3$ 의 합성 = 0:

$$d^2 \omega = 0 \quad \Longleftrightarrow \quad \nabla \cdot (\nabla \times \vec{F}) = 0$$

*회전의 발산은 0*.

두 *익숙한 부호 항등식이 $d^2 = 0$ 하나로 통합*. 우아함의 정점.

### 7. 4차원 이상에서는 어떻게?

위의 통일된 그림이 *3차원에서만* 작동한다는 게 *결정적인 차이*.

**$n$ 차원의 일반 사슬**

$$\Omega^0 \xrightarrow{d} \Omega^1 \xrightarrow{d} \Omega^2 \xrightarrow{d} \cdots \xrightarrow{d} \Omega^n$$

각 $\Omega^k$ 의 차원이 $\binom{n}{k}$. *모든 차원에서* 이 사슬이 잘 정의되고, *$d^2 = 0$* 도 항상 성립.

**4D 에서의 어려움**

4D 에서:

- $\Omega^0$ : 1 차원 (스칼라)
- $\Omega^1$ : 4 차원 (벡터 같은 객체)
- $\Omega^2$ : 6 차원 (2-form, *벡터가 아님*)
- $\Omega^3$ : 4 차원
- $\Omega^4$ : 1 차원

$d: \Omega^1 \to \Omega^2$ 의 결과가 *6차원 2-form* — *벡터로 표현 안 됨*. 따라서 *회전 같은 단일 벡터 연산자* 가 존재하지 않는다.

대신 *전자기 텐서 (electromagnetic tensor) $F_{\mu\nu}$* 가 등장. 이게 *4D 시공간 위의 2-form* 이고, *전기장과 자기장이 한 객체로 통합* 됨. §14 에서 자세히.

**일반 차원에서**

회전이 *3D 만의 우연* 임이 분명해진다. *외미분은 모든 차원에서 작동* 하지만, *그것을 벡터 미적분 언어로 번역하는 게 3D 에서만 깔끔* 함.

이게 *미분형식 언어가 더 근본적* 인 이유. 벡터 미적분은 *3D 의 특수 사례*. 미분형식은 *모든 차원의 일반 언어*.

### 8. 응용: 보존 벡터장, 비회전 벡터장

이 대응이 *흔히 배우는 벡터장의 분류* 에 즉시 응용된다.

**보존 벡터장 (conservative field)**

벡터장 $\vec{F}$ 가 *보존적 (conservative)* — 즉 어떤 스칼라 포텐셜 $f$ 에 대해 $\vec{F} = \nabla f$ — 인지 판정.

미분형식 언어로: $\vec{F}^\flat = df$ 인 함수 $f$ 의 존재 여부.

즉 *1-form $\vec{F}^\flat$ 이 완전형식 (exact form)* 인지의 문제.

**비회전 벡터장 (irrotational field)**

벡터장 $\vec{F}$ 가 *비회전적* — $\nabla \times \vec{F} = 0$ — 인지 판정.

미분형식 언어로: *$d \vec{F}^\flat = 0$* — 즉 *1-form $\vec{F}^\flat$ 이 폐형식 (closed form)* 인지의 문제.

**핵심 관계**

§8 에서 본 *폐형식 vs 완전형식* 의 차이:

- *완전 → 폐*: 항상 성립 ($d^2 = 0$). 따라서 *보존 → 비회전*.
- *폐 → 완전*: *공간의 위상에 따라 다름*. 따라서 *비회전 → 보존* 은 *공간에 따라 다름*.

**예: 볼록 영역과 도넛 영역**

볼록한 영역 (예: $\mathbb{R}^3$ 전체, 공) 에서는 *비회전 ⟹ 보존* (Poincaré 보조정리). 이게 흔히 배우는 사실.

하지만 *원점을 뺀 평면* 같은 *비단순한 영역* 에서는 *비회전이지만 보존이 아닌* 벡터장이 존재. 대표적인 예가

$$\vec{F} = \left(-\frac{y}{x^2 + y^2},\, \frac{x}{x^2 + y^2}\right)$$

(소위 *각도 함수의 그라디언트* 같은 벡터장.) 

이게 *비회전이지만 보존이 아니다* — 왜냐하면 *영역의 위상 (구멍이 있음)* 때문에 *전체에서 정의된 포텐셜이 존재하지 않음*.

이 *위상적 효과* 를 *측정* 하는 것이 *de Rham cohomology* (§12). 외미분 언어가 *위상학과 미적분을 잇는다*.

### 9. 발산이 0 인 벡터장 (incompressible)

비슷한 분류로 *발산이 0 인 벡터장*.

**비압축 벡터장 (incompressible / solenoidal field)**

$\nabla \cdot \vec{F} = 0$ 인 벡터장. 미분형식 언어로:

$$d(\star \vec{F}^\flat) = 0$$

즉 *2-form $\star \vec{F}^\flat$ 가 폐형식*.

**$\vec{F}$ 가 다른 벡터장의 회전인지?**

벡터장 $\vec{F}$ 가 *어떤 벡터장 $\vec{G}$ 의 회전* — 즉 $\vec{F} = \nabla \times \vec{G}$ — 인지 판정.

미분형식 언어로: *2-form $\star \vec{F}^\flat$ 가 완전형식* — 즉 어떤 1-form $\eta$ 에 대해 $\star \vec{F}^\flat = d\eta$.

같은 관계:

- *어떤 $\vec{G}$ 의 회전* → *발산 0* (완전 → 폐).
- 역은 *공간 위상에 따라 다름* (예: 자기 모노폴이 없을 조건 = $\nabla \cdot \vec{B} = 0$ 이지만 글로벌한 벡터 포텐셜 존재 여부는 *위상에 따라 다름*).

**물리적 의미**

이게 *Maxwell 방정식* 의 *위상학적 측면*과 연결됨. $\nabla \cdot \vec{B} = 0$ (자기 모노폴이 없음) 으로부터 $\vec{B} = \nabla \times \vec{A}$ (벡터 포텐셜의 존재) 가 *공간이 단순할 때만* 자동으로 따라 나온다.

(예외적으로 *자기 모노폴이 있는 공간* 에서는 글로벌한 $\vec{A}$ 가 존재하지 않음 — Dirac monopole 의 위상학적 해석.)

이 모든 게 *외미분과 위상수학의 깊은 연관* 이며, §12 의 *de Rham cohomology* 의 자연스러운 동기.

### 10. 정리

이 장에서 다룬 내용을 정리한다.

**1)** *3D 벡터 미적분의 세 연산자* (그라디언트, 회전, 발산) 가 *외미분 $d$ 의 세 가지 표현*. 

**2)** *음악적 동형사상* (플랫 $\flat$ 과 샵 $\sharp$) 가 벡터와 1-form 사이의 다리.

**3)** *0-form 의 외미분*: $df$ 의 샵 = 그라디언트.

$$\nabla f = (df)^\sharp$$

**4)** *1-form 의 외미분* (3D): 회전과 정확한 대응 — Hodge 별표 매개로.

$$\nabla \times \vec{F} = (\star d \vec{F}^\flat)^\sharp$$

**5)** *2-form 의 외미분* (3D): 발산과 정확한 대응.

$$\nabla \cdot \vec{F} = \star d (\star \vec{F}^\flat)$$

**6)** *3D de Rham 사슬*:

$$\Omega^0 \xrightarrow{d = \text{grad}} \Omega^1 \xrightarrow{d \approx \text{curl}} \Omega^2 \xrightarrow{d \approx \text{div}} \Omega^3$$

**7)** *$d^2 = 0$* 이 *두 익숙한 항등식* 을 통합: $\nabla \times \nabla f = 0$ 와 $\nabla \cdot (\nabla \times \vec{F}) = 0$.

**8)** *4D 이상* 에서는 회전이 단일 벡터로 표현되지 않음. 외미분은 여전히 작동 — *미분형식이 더 근본적인 언어*.

**9)** *보존·비회전 벡터장* 의 분류가 *완전형식·폐형식* 의 분류와 정확히 일치. 둘의 차이가 *공간의 위상*.

**10)** *비압축 벡터장과 회전의 존재성* 도 같은 식의 폐형식·완전형식 차이.

이 장에서 외대수가 *벡터 미적분의 자연스러운 일반화* 임이 명확해졌다. 다음 §10 부터는 *적분* 으로 가서, *Stokes 정리* 가 어떻게 모든 *적분 공식 (기본 정리, Green, Stokes 3D, Gauss)* 을 통합하는지 본다.
