+++
title = "미분형식의 적분"
weight = 10
+++

### 1. 동기: 왜 미분형식을 적분하는가

§7 의 §10 에서 미분형식이 *적분의 자연스러운 객체* 임을 살짝 언급했다. 1-form 은 곡선 적분, 2-form 은 면 적분, $n$-form 은 부피 적분과 *자연스럽게* 어울린다.

이 장에서 그 의미를 *정확히* 본다. *미분형식의 적분이 정확히 무엇인지*, *왜 그것이 다중 변수 미적분의 익숙한 적분들* (곡선 적분, 면 적분, 부피 적분) *과 일치하는지*, 그리고 *왜 이 새 언어가 더 강력한지* 를 설명한다.

핵심 메시지는 두 가지다.

첫째, *$k$-form 은 $k$-차원 영역 위에서 적분된다*. 차수와 적분 영역의 차원이 일치하는 게 우연이 아니다.

둘째, *미분형식의 적분은 자동으로 변수 변환 공식 (야코비안)을 포함* 한다. 따로 외워야 할 공식이 아니라 *외대수의 자연스러운 결과*.

이 두 가지가 §11 의 *Stokes 정리* — 다중 변수 미적분의 모든 적분 공식 (Newton-Leibniz, Green, Stokes 3D, Gauss) 을 *한 줄로 통합* 하는 정리 — 의 출발점이 된다.

### 2. 적분의 기본 문제: $k$-form 을 $k$-차원 영역에 어떻게 작용시키나?

미분형식 $\omega$ 가 *공간 안의 한 점에서* $k$ 개의 벡터를 받아 숫자를 내놓는다는 건 §7 에서 봤다. 그런데 *적분* 은 한 점이 아니라 *영역 전체에 걸친 합* 을 다룬다.

**핵심 아이디어**

영역을 *작은 조각들* 로 나누고, 각 조각을 *작은 평행체* 로 근사한 다음, *그 평행체에 미분형식이 작용한 값을 모두 합한다*. 이게 적분의 기본 발상.

$k$-차원 영역의 *작은 조각* 은 *$k$ 개의 작은 접벡터로 만든 작은 평행체*. 이 평행체에 $k$-form 을 작용시키면 *그 조각에 대한 미분형식의 값* 이 나오고, 모든 조각을 *합 (또는 적분)* 하면 영역 전체의 적분.

> **핵심 원리**: $k$-form 은 *$k$-차원 영역의 작은 평행체 조각* 에 자연스럽게 작용. 합치면 *영역 전체의 적분*.

차수와 영역 차원이 일치해야 하는 이유가 명확하다. *$k$-form 은 $k$ 개의 벡터를 받음* → *$k$ 차원 평행체 조각에 작용* → *$k$ 차원 영역에서 적분*.

### 3. 매개변수화: 영역의 정의

영역을 정확히 다루려면 *매개변수화 (parametrization)* 가 필요하다.

**$k$-차원 영역의 매개변수화**

$k$-차원 영역 $S$ 를 *매개변수 공간* $U \subset \mathbb{R}^k$ 에서 우리 공간 $\mathbb{R}^n$ 으로 가는 매끄러운 함수

$$\Phi: U \to S \subset \mathbb{R}^n$$

으로 표현한다. 매개변수 $\vec{u} = (u^1, u^2, \ldots, u^k) \in U$ 가 영역의 한 점 $\Phi(\vec{u})$ 를 결정.

**예제 (1차원, 곡선)**

곡선 $C$ 의 매개변수화: $\Phi: [a, b] \to \mathbb{R}^n$, 즉 $t \mapsto \Phi(t)$. 매개변수 $t$ 의 한 값이 곡선 위의 한 점을 결정.

예: 원 $x^2 + y^2 = 1$ 의 매개변수화는 $\Phi(t) = (\cos t, \sin t)$, $t \in [0, 2\pi]$.

**예제 (2차원, 면)**

면 $S$ 의 매개변수화: $\Phi: U \to \mathbb{R}^3$, 즉 $(u, v) \mapsto \Phi(u, v)$. 두 매개변수의 한 쌍이 면 위의 한 점을 결정.

예: 구면 $x^2 + y^2 + z^2 = 1$ 의 매개변수화는 $\Phi(\theta, \phi) = (\sin\theta \cos\phi, \sin\theta \sin\phi, \cos\theta)$.

**매개변수 공간에서의 적분으로 옮기기**

매개변수화가 주어지면, 원래 공간에서의 적분을 *매개변수 공간 $U$* 에서의 적분으로 옮길 수 있다. 매개변수 공간은 보통 $\mathbb{R}^k$ 의 단순한 영역 (구간, 사각형 등) 이라 다루기 쉽다.

이 옮기기를 *정확히 어떻게* 하는지가 다음 절의 *pullback* 의 핵심.

### 4. Pullback: 미분형식을 매개변수 공간으로 끌어오기

매개변수화 $\Phi: U \to \mathbb{R}^n$ 이 주어지면, *목표 공간 $\mathbb{R}^n$ 위의 미분형식* 을 *매개변수 공간 $U$ 위의 미분형식* 으로 *끌어올* (pull back) 수 있다. 이게 미분형식 이론의 핵심 도구 중 하나.

**정의 (Pullback)**

$\Phi: U \to M$ 매끄러운 함수, $\omega$ 가 $M$ 위의 $k$-form 일 때, $\omega$ 의 *$\Phi$ 에 의한 끌어옴 (pullback)* 은 $U$ 위의 $k$-form $\Phi^* \omega$ 로, 다음 식으로 정의:

$$(\Phi^* \omega)_p (v_1, \ldots, v_k) := \omega_{\Phi(p)}(d\Phi_p(v_1), \ldots, d\Phi_p(v_k))$$

복잡해 보이지만 직관은 단순하다. *$\omega$ 를 평가하려면 그 자리에 벡터를 넣어야 하는데*, 우리는 *$U$ 의 벡터* 만 갖고 있고 *$M$ 의 벡터가 필요*. *매개변수화의 미분 $d\Phi$* 가 그 변환을 해 준다.

**$d\Phi$ 는 뭐인가**

$d\Phi_p: T_p U \to T_{\Phi(p)} M$ 은 *$\Phi$ 의 미분* — 즉 *$\Phi$ 의 야코비 행렬* 의 작용. 매개변수 공간의 작은 접벡터를 *목표 공간의 작은 접벡터* 로 보내는 선형 사상.

**좌표 표현**

좌표로 풀면 더 명확하다. 목표 공간 좌표가 $x^1, \ldots, x^n$, 매개변수 공간 좌표가 $u^1, \ldots, u^k$ 일 때, 매개변수화가

$$x^i = \Phi^i(u^1, \ldots, u^k)$$

로 주어진다. Pullback 의 작용:

$$\Phi^*(dx^i) = \sum_{j=1}^{k} \frac{\partial \Phi^i}{\partial u^j}\, du^j$$

즉 좌표 미분 $dx^i$ 의 끌어옴은 *체인 룰의 1-form 버전*. 익숙한 미적분 그대로.

함수 (0-form) 의 끌어옴:

$$\Phi^* f = f \circ \Phi$$

(*합성*. 자연스러운 정의.)

**Pullback 의 핵심 성질**

(1) *덧셈 보존*: $\Phi^*(\omega + \eta) = \Phi^* \omega + \Phi^* \eta$.

(2) *쐐기곱 보존*: $\Phi^*(\omega \wedge \eta) = (\Phi^* \omega) \wedge (\Phi^* \eta)$. 

(3) *외미분과 가환*: $\Phi^* (d\omega) = d(\Phi^* \omega)$. 

세 번째 성질이 특히 중요. *끌어옴이 외미분 연산과 가환* 한다는 사실이 §11 의 Stokes 정리의 좌표 독립성을 보장한다.

### 5. $k$-form 의 $k$-차원 영역 위 적분: 정의

이제 본격적으로 적분을 정의한다.

**정의 (미분형식의 적분)**

$k$-차원 영역 $S$ 가 매개변수화 $\Phi: U \to S$ 로 주어지고 $\omega$ 가 $k$-form 일 때, $\omega$ 의 $S$ 위 적분을

$$\int_S \omega := \int_U \Phi^* \omega$$

로 정의한다. 우변은 *매개변수 공간 위의 적분* — 결과적으로 *익숙한 다중 변수 적분*.

**이 정의가 잘 정의됨**

$\Phi^* \omega$ 가 *$U$ 위의 $k$-form*. $U \subset \mathbb{R}^k$ 가 *$k$-차원 영역* 이므로 이 $k$-form 이 $U$ 의 *최고차 형식*. 따라서 *유일한 함수 계수 × $du^1 \wedge \cdots \wedge du^k$* 형태:

$$\Phi^* \omega = g(u^1, \ldots, u^k)\, du^1 \wedge du^2 \wedge \cdots \wedge du^k$$

여기서 함수 $g$ 가 정해진다. 그러면 적분은

$$\int_U \Phi^* \omega = \int_U g(u^1, \ldots, u^k)\, du^1 du^2 \cdots du^k$$

— 정확히 *익숙한 다중 변수 적분*.

**왜 매개변수화 선택에 무관한가**

자연스러운 질문: *다른 매개변수화* 를 잡으면 적분 값이 달라지지 않을까?

답: *방향이 일관되면* 값이 같다. 두 매개변수화 사이의 변환의 *야코비안* 이 양수면 같은 값, 음수면 부호 반전.

이 점이 *방향이 붙은 적분* 의 핵심. 미분형식의 적분은 *자동으로 방향성을 추적* 한다 — §3 에서 본 쐐기곱의 반대칭성이 *자연스럽게 방향 정보를 인코딩* 하기 때문.

### 6. 예제: 1-form 의 곡선 적분

가장 단순한 경우를 구체적으로 본다.

**설정**: $\mathbb{R}^3$ 의 곡선 $C$ 가 $\Phi: [a, b] \to \mathbb{R}^3$, $t \mapsto (x(t), y(t), z(t))$ 로 매개변수화됨. 1-form $\omega = P\, dx + Q\, dy + R\, dz$ 의 $C$ 위 적분.

**Pullback 계산**

$\Phi^* (dx) = \frac{dx}{dt}\, dt = x'(t)\, dt$. 비슷하게 $\Phi^*(dy) = y'(t)\, dt$, $\Phi^*(dz) = z'(t)\, dt$. 

함수 계수도 끌어와야 함: $\Phi^* P = P(\Phi(t)) = P(x(t), y(t), z(t))$. (보통 $P(t)$ 로 줄여 씀.)

합치면:

$$\Phi^* \omega = P(\Phi(t))\, x'(t)\, dt + Q(\Phi(t))\, y'(t)\, dt + R(\Phi(t))\, z'(t)\, dt$$

$$= \big[P\, x'(t) + Q\, y'(t) + R\, z'(t)\big]\, dt$$

**적분**

$$\int_C \omega = \int_a^b \big[P\, x'(t) + Q\, y'(t) + R\, z'(t)\big]\, dt$$

이게 정확히 *익숙한 곡선 적분 (line integral)*. 벡터 미적분의 표기로

$$\int_C \omega = \int_C \vec{F} \cdot d\vec{r}$$

여기서 $\vec{F} = (P, Q, R)$ 이 1-form 의 음악적 변환에 대응하는 벡터장 (§9), $d\vec{r} = (dx, dy, dz)$ 가 곡선의 접선 무한소.

> *1-form 의 곡선 적분 = 벡터장의 곡선 적분*. 미분형식 언어로 자연스럽게 일반화.

**구체적 예**

$\omega = -y\, dx + x\, dy$ 의 단위원 $\Phi(t) = (\cos t, \sin t)$, $t \in [0, 2\pi]$ 위 적분:

$\Phi^* \omega = -\sin t \cdot (-\sin t)\, dt + \cos t \cdot \cos t\, dt = (\sin^2 t + \cos^2 t)\, dt = dt$

$$\int_C \omega = \int_0^{2\pi} dt = 2\pi$$

(이 결과는 *원의 둘레의 두 배* 가 아니라 *원의 내부 넓이의 두 배*. Green 정리 (§11) 와의 연결을 미리 보여주는 예.)

### 7. 예제: 2-form 의 면 적분

다음으로 *2-form 의 면 위 적분*. 

**설정**: $\mathbb{R}^3$ 의 면 $S$ 가 $\Phi: U \to \mathbb{R}^3$, $(u, v) \mapsto \Phi(u, v) = (x(u, v), y(u, v), z(u, v))$ 로 매개변수화. 2-form $\omega = P\, dy \wedge dz + Q\, dz \wedge dx + R\, dx \wedge dy$ 의 적분.

**Pullback 의 계산**

$\Phi^*(dx) = \frac{\partial x}{\partial u}\, du + \frac{\partial x}{\partial v}\, dv = x_u\, du + x_v\, dv$ (편미분 약식 표기). 비슷하게 $\Phi^*(dy), \Phi^*(dz)$.

$\Phi^*(dx \wedge dy)$ 를 계산하면 (pullback 이 쐐기곱과 가환하므로)

$$\Phi^*(dx \wedge dy) = (x_u\, du + x_v\, dv) \wedge (y_u\, du + y_v\, dv)$$

분배하면:

$$= x_u y_u\, du \wedge du + x_u y_v\, du \wedge dv + x_v y_u\, dv \wedge du + x_v y_v\, dv \wedge dv$$

$du \wedge du = dv \wedge dv = 0$, $dv \wedge du = -du \wedge dv$ 로 정리하면

$$\Phi^*(dx \wedge dy) = (x_u y_v - x_v y_u)\, du \wedge dv$$

**$2 \times 2$ 야코비안의 등장**

여기서 *놀라운 사실*. 위 결과의 계수가 정확히 *야코비 행렬의 부분 행렬식*:

$$x_u y_v - x_v y_u = \det \begin{pmatrix} x_u & x_v \\ y_u & y_v \end{pmatrix} = \frac{\partial(x, y)}{\partial(u, v)}$$

즉:

$$\Phi^*(dx \wedge dy) = \frac{\partial(x, y)}{\partial(u, v)}\, du \wedge dv$$

이게 *쐐기곱이 자동으로 야코비안을 만들어내는* 마법. *외워야 할 변수변환 공식이 외대수 안에 내장* 되어 있다.

**전체 적분**

비슷하게 $\Phi^*(dy \wedge dz), \Phi^*(dz \wedge dx)$ 도 각각 *야코비안 형태*. 합치면

$$\Phi^* \omega = \left[ P \cdot \frac{\partial(y, z)}{\partial(u, v)} + Q \cdot \frac{\partial(z, x)}{\partial(u, v)} + R \cdot \frac{\partial(x, y)}{\partial(u, v)} \right] du \wedge dv$$

적분:

$$\int_S \omega = \int_U \left[ P\, \frac{\partial(y, z)}{\partial(u, v)} + Q\, \frac{\partial(z, x)}{\partial(u, v)} + R\, \frac{\partial(x, y)}{\partial(u, v)} \right] du\, dv$$

대괄호 안의 식이 정확히 *$\vec{F} \cdot (\Phi_u \times \Phi_v)$* — 익숙한 *면 적분 공식*. 

> *2-form 의 면 적분 = 벡터장의 플럭스 (flux)*. $\int_S \omega = \int_S \vec{F} \cdot d\vec{A}$.

**물리적 의미**

이게 *전기장의 가우스 법칙* 등에서 자연스럽게 등장하는 적분의 정확한 외대수적 표현. 미분형식 언어가 *물리의 자연스러운 도구* 임이 다시 확인됨.

### 8. 일반 $k$-form 의 적분: 변수 변환 공식의 자동 등장

위의 1-form 과 2-form 예제에서 본 패턴이 *일반 $k$-form* 에서도 작동한다.

**일반 결과**

$\Phi: U \subset \mathbb{R}^k \to M \subset \mathbb{R}^n$ 매개변수화, $\omega = f\, dx^{i_1} \wedge \cdots \wedge dx^{i_k}$ 단항 $k$-form 의 pullback:

$$\Phi^*(f\, dx^{i_1} \wedge \cdots \wedge dx^{i_k}) = f(\Phi(u)) \cdot \det\left( \frac{\partial x^{i_a}}{\partial u^b} \right)_{a, b = 1, \ldots, k}\, du^1 \wedge \cdots \wedge du^k$$

여기서 *행렬식이 자동으로 등장*. 이게 §5 의 *행렬식 = 쐐기곱의 자연스러운 결과* 의 적분 버전.

**다중 변수 적분의 변수 변환 공식**

이 결과를 보면 *익숙한 변수 변환 공식*

$$\int f(\vec{y})\, dV_y = \int f(\Phi(\vec{u}))\, |\det J_\Phi|\, dV_u$$

이 *외대수 안에 내장* 되어 있음이 분명. 미분형식의 적분에서는 *행렬식이 절댓값 없이* 등장하므로 *방향이 붙은 적분* — 익숙한 적분의 자연스러운 일반화.

### 9. 방향 (orientation) 의 중요성

미분형식의 적분은 *자동으로 방향에 민감* 하다는 점이 *기존의 다중 변수 적분과의 본질적 차이*.

**1차원 예제로 보기**

곡선 $C$ 를 *반대 방향* 으로 매개변수화하면 — 예를 들어 $t \in [a, b]$ 가 아니라 $\Phi(s) = \Phi(a + b - s)$, $s \in [a, b]$ 로 — 적분 결과는?

미분형식 표기로: $ds = -dt$ 이므로 $\Phi^*\omega$ 의 부호가 반전. 따라서

$$\int_{-C} \omega = -\int_C \omega$$

(여기서 $-C$ 는 $C$ 의 반대 방향.)

이게 *방향이 붙은 적분* 의 정확한 의미. 익숙한 적분에서는 *적분 한계의 순서* ($\int_a^b$ vs $\int_b^a$) 로 표현되던 부호가, 외대수에서는 *매개변수화의 방향* 으로 자연스럽게 인코딩.

**고차원에서**

면 적분에서도 같은 일이 일어난다. 면을 *어느 쪽이 "위"* 인지 정해야 하고, 그 방향이 *쐐기곱의 순서* 와 일관되어야 한다. 

방향을 뒤집으면 ($dx \wedge dy \to dy \wedge dx = -dx \wedge dy$) 적분 결과의 부호가 반전.

> 미분형식의 적분은 *항상 방향이 붙은 적분*. 방향을 무시하면 익숙한 절댓값 부피.

### 10. 익숙한 적분 공식들과의 통일

위에서 본 대응을 정리해 본다.

**$k = 1$ (1-form, 곡선 적분)**

미분형식: $\int_C \omega_F$, 여기서 $\omega_F = \vec{F}^\flat$.

벡터 미적분: $\int_C \vec{F} \cdot d\vec{r}$.

**$k = 2$ (2-form, 면 적분, 3D)**

미분형식: $\int_S \omega_F$, 여기서 $\omega_F = \star \vec{F}^\flat$.

벡터 미적분: $\int_S \vec{F} \cdot d\vec{A}$ (플럭스).

**$k = n$ ($n$-form, 부피 적분, $n$ 차원)**

미분형식: $\int_M f\, dx^1 \wedge \cdots \wedge dx^n$.

다중 변수 미적분: $\int_M f\, dV$.

이 세 가지 *익숙한 적분* 들이 *모두 미분형식의 적분의 특수 사례*. 통일된 언어가 *모든 차원, 모든 종류의 적분* 을 *한 식* 으로 표현.

### 11. 적분의 결합 / 합성 성질

미분형식의 적분이 갖는 두 중요한 성질을 정리한다.

**1) 선형성**

$\int_S (\alpha \omega + \beta \eta) = \alpha \int_S \omega + \beta \int_S \eta$ — 익숙한 선형성.

**2) 영역의 분할**

영역 $S$ 를 두 영역 $S_1$ 과 $S_2$ 로 분할하면 (적절히 방향 일치):

$$\int_{S_1 \cup S_2} \omega = \int_{S_1} \omega + \int_{S_2} \omega$$

이건 *적분의 가법성* — 영역을 자유롭게 쪼개고 합칠 수 있다. 

이 가법성이 *Stokes 정리* (§11) 의 증명에서 핵심 역할을 한다. 영역을 *작은 조각으로 쪼개고*, *각 조각에 대해 결과를 검증한 다음 합치는* 전략.

### 12. 정리

이 장에서 다룬 내용을 정리한다.

**1)** *$k$-form 은 $k$-차원 영역 위에서 적분된다*. 차수와 영역 차원의 일치가 *자연스러운 짝지음*.

**2)** *매개변수화* $\Phi: U \subset \mathbb{R}^k \to S$ 가 영역을 *익숙한 매개변수 공간 위의 적분으로* 옮긴다.

**3)** *Pullback* $\Phi^* \omega$ 는 *목표 공간의 미분형식을 매개변수 공간으로 끌어오는* 도구. 좌표 표현:

$$\Phi^*(dx^i) = \sum_j \frac{\partial x^i}{\partial u^j}\, du^j$$

**4)** *Pullback 의 성질*: 덧셈 보존, 쐐기곱 보존, 외미분과 가환 ($\Phi^* d = d \Phi^*$).

**5)** *적분의 정의*: $\int_S \omega := \int_U \Phi^* \omega$. 우변은 익숙한 다중 변수 적분.

**6)** *1-form 의 곡선 적분* = 벡터장의 곡선 적분 (line integral).

**7)** *2-form 의 면 적분* = 벡터장의 플럭스. *야코비안이 쐐기곱에서 자동 등장*.

**8)** *변수 변환 공식*: 일반 $k$-form 의 pullback 에 *행렬식이 자동으로* 들어감 — 외대수의 본질.

**9)** *방향 (orientation)* 이 자동으로 추적됨. 미분형식의 적분은 *항상 방향이 붙은 적분*. 

**10)** *모든 익숙한 적분* (곡선 적분, 면 적분, 부피 적분) 이 *미분형식 적분의 특수 사례* — 통일된 언어.

다음 §11 에서 *Stokes 정리* — *모든 적분 공식 (Newton-Leibniz, Green, Stokes 3D, Gauss) 을 한 식으로 통일* 하는 위대한 정리 — 를 본다. 이 장에서 닦은 기반 (적분의 정의, pullback, 방향) 이 모두 거기서 활용된다.
