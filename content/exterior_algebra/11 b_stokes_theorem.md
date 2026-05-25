+++
title = "Stokes 정리"
weight = 11
+++

### 1. 동기: 다중 변수 미적분의 네 정리

다중 변수 미적분에서 우리는 *네 가지 적분 정리* 를 배운다.

(1) *미적분의 기본 정리 (Newton-Leibniz)*: 1차원에서

$$\int_a^b f'(x)\, dx = f(b) - f(a)$$

미분과 적분이 *역연산* 임을 보여주는 가장 기본적인 사실.

(2) *Green 정리*: 2차원 평면의 영역 $D$ 와 그 경계 곡선 $\partial D$ 에 대해

$$\oint_{\partial D} (P\, dx + Q\, dy) = \iint_D \left(\frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y}\right) dx\, dy$$

(3) *Stokes 정리 (고전 3D)*: 3차원 공간의 면 $S$ 와 그 경계 곡선 $\partial S$ 에 대해

$$\oint_{\partial S} \vec{F} \cdot d\vec{r} = \iint_S (\nabla \times \vec{F}) \cdot d\vec{A}$$

(4) *발산 정리 (Gauss-Ostrogradsky)*: 3차원 영역 $V$ 와 그 경계 면 $\partial V$ 에 대해

$$\iiint_V (\nabla \cdot \vec{F})\, dV = \oiint_{\partial V} \vec{F} \cdot d\vec{A}$$

이 네 정리가 *겉으로는 서로 달라 보이지만* 사실은 *모두 같은 한 정리의 특수 사례*. 이 한 정리가 **일반 Stokes 정리 (generalized Stokes' theorem)** — 외대수 언어로 표현하면 *놀라울 정도로 간단*하다.

> **일반 Stokes 정리**: $M$ 이 $k$-차원 다양체 (경계가 있을 수 있음), $\omega$ 가 $(k-1)$-form 일 때
> 
> $$\int_M d\omega = \int_{\partial M} \omega$$

오른쪽이 *경계 위의 $(k-1)$-form 적분*, 왼쪽이 *내부 위의 $k$-form (외미분) 적분*. 이 한 식이 위 네 정리를 *모두 포함* 한다.

이 장에서 이 정리의 의미·증명의 개략·특수 사례들과의 연결을 차근차근 본다.

### 2. 경계 $\partial M$ 의 정의

Stokes 정리에서 핵심적인 개념이 *경계 (boundary)*. 정확히 무엇인지 본다.

**직관**

$M$ 이 $k$-차원 다양체일 때, *그 가장자리* 가 $\partial M$. 

- *1차원 곡선 $C = [a, b]$* 의 경계는 *두 끝점* $\{a, b\}$.
- *2차원 영역 $D$* (디스크) 의 경계는 *경계 곡선* $\partial D$ (원).
- *3차원 영역 $V$* (공) 의 경계는 *경계 면* $\partial V$ (구면).

일반적으로 $k$-차원 다양체의 경계는 *$(k-1)$-차원 부분다양체*. 차원이 하나 줄어든다.

**경계의 방향 (orientation)**

여기서 미묘한 부분이 *경계의 방향* — *어느 방향이 양의 방향인지* 를 정해야 한다.

*1차원*: 곡선 $[a, b]$ 의 경계 $\{a, b\}$ 에서 *끝점이 양*, *시작점이 음*. 부호 약속으로 $\partial[a, b] = \{b\} - \{a\}$ (또는 $b - a$).

*2차원*: 영역 $D$ 의 경계 곡선 $\partial D$ 의 양의 방향은 *반시계 방향* (오른손 법칙). 즉 영역이 *왼쪽에 있도록* 도는 방향.

*3차원*: 영역 $V$ 의 경계 면 $\partial V$ 의 양의 방향은 *바깥쪽 법선*. 면의 *바깥* 방향이 양.

이 방향 약속들이 *Stokes 정리가 부호를 옳게 다루는* 핵심.

**일반 원리**

$M$ 의 방향이 주어졌을 때, $\partial M$ 의 *유도된 방향 (induced orientation)* 은 *바깥 법선 다음에 $\partial M$ 의 방향이 오면 $M$ 의 방향과 일치* 하도록 잡는다. 

좀 더 직관적으로 *오른손 법칙* 의 일반화. 손가락이 *$\partial M$ 의 양의 방향* 으로 가리키고, 엄지손가락이 *바깥 법선* 을 가리키면, 손바닥이 *$M$ 의 양의 방향* 을 향한다.

### 3. Stokes 정리: 자세한 진술

위의 정의를 갖춰 일반 Stokes 정리를 다시 진술한다.

> **정리** (일반 Stokes 정리):
> 
> $M$ 이 *방향이 잡힌, 경계가 있는 $k$-차원 매끄러운 다양체*, $\omega$ 가 *컴팩트한 받침을 가진 매끄러운 $(k-1)$-form* 일 때
> 
> $$\boxed{\;\; \int_M d\omega = \int_{\partial M} \omega \;\;}$$
> 
> 여기서 $\partial M$ 의 방향은 $M$ 의 방향에서 *유도된 방향*.

이 식의 양변을 정확히 이해해 보자.

*좌변* $\int_M d\omega$: 

- $\omega$ 가 $(k-1)$-form 이므로 $d\omega$ 가 $k$-form.
- $M$ 이 $k$-차원이므로 *$k$-form 의 $k$-차원 적분* — §10 의 정의 그대로 잘 정의.

*우변* $\int_{\partial M} \omega$:

- $\partial M$ 이 $(k-1)$-차원이고 $\omega$ 가 $(k-1)$-form 이므로 *$(k-1)$-form 의 $(k-1)$-차원 적분* — 역시 잘 정의.

*차원의 일치* 가 양변을 정합적으로 만든다. 이게 외대수 언어의 *우아함*.

### 4. 특수 사례 1: Newton-Leibniz 정리

$k = 1$, 즉 $M = [a, b]$ 가 1차원 구간일 때 Stokes 정리가 *미적분의 기본 정리* 가 된다.

**구조**

- $M = [a, b]$ : 1차원 구간.
- $\partial M = \{b\} - \{a\}$ : 두 끝점 (부호 포함).
- $\omega = f$ : 0-form (= 함수).
- $d\omega = df = f'(x)\, dx$ : 1-form.

**Stokes 정리 적용**

$$\int_M d\omega = \int_{[a,b]} f'(x)\, dx$$

$$\int_{\partial M} \omega = \int_{\{b\} - \{a\}} f = f(b) - f(a)$$

(0-form 의 0차원 적분 = 함수의 점에서의 값. 부호 따라.)

두 식을 같다고 두면

$$\int_a^b f'(x)\, dx = f(b) - f(a)$$

— *미적분의 기본 정리*. 

> Newton-Leibniz 정리는 Stokes 정리의 *1차원 사례*.

### 5. 특수 사례 2: Green 정리

$k = 2$, 즉 $M = D$ 가 2차원 평면 영역일 때 *Green 정리* 가 나온다.

**구조**

- $M = D$ : 2차원 평면 영역.
- $\partial M = \partial D$ : 경계 곡선 (반시계 방향).
- $\omega = P\, dx + Q\, dy$ : 1-form.
- $d\omega = (\partial Q / \partial x - \partial P / \partial y)\, dx \wedge dy$ : 2-form (§8 §5 의 결과).

**Stokes 정리 적용**

$$\int_M d\omega = \iint_D \left(\frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y}\right) dx \wedge dy = \iint_D \left(\frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y}\right) dx\, dy$$

(최고차 형식의 적분 = 익숙한 다중 적분.)

$$\int_{\partial M} \omega = \oint_{\partial D} (P\, dx + Q\, dy)$$

같다고 두면

$$\oint_{\partial D} (P\, dx + Q\, dy) = \iint_D \left(\frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y}\right) dx\, dy$$

— *Green 정리*.

> Green 정리는 Stokes 정리의 *2차원 평면 사례*.

### 6. 특수 사례 3: 고전 Stokes 정리 (3D)

$k = 2$, 즉 $M = S$ 가 3차원 공간의 *2차원 면* 일 때 *고전 Stokes 정리* 가 나온다.

**구조**

- $M = S$ : 3차원 공간의 2차원 면.
- $\partial M = \partial S$ : 경계 곡선.
- $\omega = P\, dx + Q\, dy + R\, dz$ : 3D 의 1-form, 벡터장 $\vec{F} = (P, Q, R)$ 에 대응.
- $d\omega$ : 회전과 관련된 2-form (§9 §4 의 결과).

**Stokes 정리 적용**

$$\int_M d\omega = \int_S d\omega = \int_S \star (\nabla \times \vec{F})^\flat \quad \text{(§9 의 대응)}$$

벡터 미적분 표기로 옮기면 *플럭스 적분*:

$$= \int_S (\nabla \times \vec{F}) \cdot d\vec{A}$$

$$\int_{\partial M} \omega = \oint_{\partial S} \vec{F} \cdot d\vec{r}$$

같다고 두면

$$\oint_{\partial S} \vec{F} \cdot d\vec{r} = \int_S (\nabla \times \vec{F}) \cdot d\vec{A}$$

— *고전 Stokes 정리*.

> 고전 Stokes 정리 = 일반 Stokes 정리의 *3D 면 사례* + 음악적 동형사상 변환.

### 7. 특수 사례 4: 발산 정리 (Gauss-Ostrogradsky)

$k = 3$, 즉 $M = V$ 가 3차원 공간의 3차원 영역일 때 *발산 정리* 가 나온다.

**구조**

- $M = V$ : 3차원 영역.
- $\partial M = \partial V$ : 경계 면 (바깥 법선 방향).
- $\omega = P\, dy \wedge dz + Q\, dz \wedge dx + R\, dx \wedge dy$ : 2-form, 벡터장 $\vec{F}$ 에 대응.
- $d\omega = (\partial P / \partial x + \partial Q / \partial y + \partial R / \partial z)\, dx \wedge dy \wedge dz$ : 3-form (§8 §6 의 결과).

**Stokes 정리 적용**

$$\int_M d\omega = \iiint_V \left(\frac{\partial P}{\partial x} + \frac{\partial Q}{\partial y} + \frac{\partial R}{\partial z}\right) dV = \iiint_V (\nabla \cdot \vec{F})\, dV$$

$$\int_{\partial M} \omega = \oiint_{\partial V} \vec{F} \cdot d\vec{A}$$

같다고 두면

$$\iiint_V (\nabla \cdot \vec{F})\, dV = \oiint_{\partial V} \vec{F} \cdot d\vec{A}$$

— *발산 정리 (Gauss-Ostrogradsky)*.

> 발산 정리 = 일반 Stokes 정리의 *3D 부피 사례*.

### 8. 통일 정리

위의 네 특수 사례를 한 표로 정리하면:

| 차원 $k$ | $M$ | $\partial M$ | $\omega$ ($(k-1)$-form) | $d\omega$ ($k$-form) | 익숙한 정리 |
|---|---|---|---|---|---|
| 1 | 구간 $[a,b]$ | 두 끝점 | 함수 $f$ | $f'\, dx$ | Newton-Leibniz |
| 2 (평면) | 평면 영역 $D$ | 경계 곡선 | $P\,dx + Q\,dy$ | $(\partial_x Q - \partial_y P)\,dx\wedge dy$ | Green |
| 2 (공간) | 3D 의 면 $S$ | 경계 곡선 | 벡터장 1-form | 회전 2-form | 3D Stokes |
| 3 | 3D 영역 $V$ | 경계 면 | 벡터장 2-form | 발산 3-form | 발산 정리 |

*한 식이 네 정리를 통합* — 이게 외대수 언어의 우아함의 정점. 

> $$\int_M d\omega = \int_{\partial M} \omega$$
> 
> 이 한 줄이 *모든 적분 정리* 를 표현. 

### 9. 증명의 개략

일반 Stokes 정리의 *완전한 증명* 은 다양체 이론의 기술적 도구들을 필요로 한다. 여기선 *왜 이 정리가 성립하는지의 직관* 을 짚는다.

**단계 1: 단순한 영역에서의 증명**

먼저 $M$ 이 *$\mathbb{R}^k$ 의 단위 정육면체 (또는 단위 구간)* 인 가장 단순한 경우를 본다. 

$k = 1$ (구간) 의 경우, 1-form $\omega = f'\, du$ ($u$ 가 구간 매개변수) 의 적분. *미적분의 기본 정리* 가 정확히 이 식이므로 자명. 

$k \ge 2$ 의 경우, *부분 적분 (integration by parts)* 으로 증명. $\omega$ 가 좌표 미분의 한 인자 ($du^i$) 가 빠진 형태일 때, $d\omega$ 는 *$\partial / \partial u^i$ 의 적분* 형태를 가지며, *경계에서의 평가* 로 환원. 다른 $du^j$ 자리에서의 적분은 *내부의 항* 으로 정확히 상쇄.

**단계 2: 분할 (partition of unity)**

일반 다양체 $M$ 은 *작은 조각들 (coordinate patches)* 로 덮을 수 있다. *분할 (partition of unity)* 이라는 도구로 $\omega$ 를 *각 조각에 받침을 가진 형식들의 합* 으로 쓴다.

$$\omega = \sum_i \rho_i \omega$$

각 $\rho_i \omega$ 는 *한 조각 안에 받침을 가진* 형식이고, 위의 단순 영역 경우로 환원되어 *Stokes 정리가 각 항에 대해 성립*. 

선형성으로 합하면 *전체 $\omega$ 에 대한 Stokes 정리*. ∎

**증명의 핵심: 부분 적분 + 경계 효과의 누적**

근본적으로 *Stokes 정리는 미적분의 부분 적분의 일반화*. 내부에서의 $d$ 효과가 *경계로 모이는* 일반 원리.

### 10. 적분의 좌표 독립성

Stokes 정리는 *좌표 선택에 무관* 하다. 다른 좌표계를 잡아도 결과가 같다.

증명 아이디어: *pullback 이 외미분과 가환* ($\Phi^* d = d \Phi^*$) 이므로, 좌표를 바꾸면 양변이 정확히 같은 방식으로 변환. 따라서 등식이 보존.

이 *좌표 독립성* 이 *Stokes 정리의 진정한 자연스러움*. 우리는 좌표를 도입해 계산하지만, *정리 자체는 좌표를 사용하지 않는 객체* 들 (다양체, 미분형식, 외미분) 사이의 관계.

### 11. 응용 1: 보존 벡터장과 경로 독립성

Stokes 정리가 *경로 독립성 (path independence)* 의 정확한 의미를 준다.

**문제**: $\vec{F}$ 가 *어떤 함수의 그라디언트* — 즉 *보존 벡터장* — 일 때, 곡선 적분 $\int_C \vec{F} \cdot d\vec{r}$ 는 *경로에 의존하지 않고 끝점만으로 결정* 된다.

**Stokes 로 증명**: $\vec{F} = \nabla f$ 이면 1-form 으로 $\vec{F}^\flat = df$. $C = \partial$(어떤 영역) 이지만 단순한 경로에서는 $\partial = \{B\} - \{A\}$ (시작점과 끝점). Stokes 정리로

$$\int_C \vec{F} \cdot d\vec{r} = \int_C df = \int_{\partial C} f = f(B) - f(A)$$

*끝점과 시작점의 함수 값의 차* — 경로 독립.

**역의 경우 (Poincaré 보조정리)**

거꾸로 *$\nabla \times \vec{F} = 0$* 인 벡터장이 (단순한 영역에서) *항상 어떤 함수의 그라디언트* 인지? 

*단순한 영역* (예: 볼록 영역) 에서는 *그렇다* — Poincaré 보조정리. 

증명 아이디어: 영역 안의 한 점을 *기준점* 으로 잡고

$$f(P) := \int_{\text{기준점}}^{P} \vec{F} \cdot d\vec{r}$$

이 적분이 *경로에 무관* 하려면 *임의의 폐곡선 위의 적분이 0*. Stokes 정리로 

$$\oint_C \vec{F} \cdot d\vec{r} = \int_S \nabla \times \vec{F} \cdot d\vec{A} = 0 \quad (\text{since } \nabla \times \vec{F} = 0)$$

(단, $S$ 가 *영역 안에 들어가는* 면이어야 함 — 영역의 단순함 가정.) 따라서 $f$ 가 잘 정의되고 $\vec{F} = \nabla f$.

**위상적 효과**

단순하지 않은 영역 (예: 원점이 빠진 평면) 에서는 *비회전이지만 보존이 아닌* 벡터장이 존재. §9 §8 에서 본 예. 

이게 *de Rham 코호몰로지* (§12) 의 자연스러운 동기 — Stokes 정리가 위상학적 효과를 *측정* 하는 도구.

### 12. 응용 2: 보존 법칙과 Noether 정리

Stokes 정리가 *물리의 보존 법칙* 을 정확히 표현하는 도구.

**연속 방정식 (continuity equation)**

밀도 $\rho$ 와 흐름 $\vec{J}$ 가 보존 법칙을 만족하면

$$\frac{\partial \rho}{\partial t} + \nabla \cdot \vec{J} = 0$$

이게 *국소적 보존 법칙*. 이걸 *적분 형태* 로 옮기면 (발산 정리 적용)

$$\frac{d}{dt} \iiint_V \rho\, dV = -\oiint_{\partial V} \vec{J} \cdot d\vec{A}$$

— *영역 안의 총량의 변화율 = 경계를 통과해 빠져나가는 흐름*. 직관적인 *보존 법칙*.

**Noether 흐름의 미분형식 표현**

상대성이론에서 *4 차원 시공간* 의 연속 방정식은

$$\partial_\mu j^\mu = 0$$

이걸 미분형식으로 옮기면 *$(d-1)$-form 의 외미분 = 0*. 즉

$$d \star j = 0$$

여기서 $\star j$ 가 *4 차원에서의 3-form*. Stokes 정리로 *적분 형태의 보존 법칙* 이 자동으로 따라 나옴.

> *Noether 정리* 의 보존 법칙들이 *모두 Stokes 정리의 응용* 으로 표현 가능. 

이게 *외대수 언어의 물리적 의미* — Noether 정리, Maxwell 방정식, 보존 법칙이 모두 *Stokes 정리의 자연스러운 결과*.

### 13. 응용 3: 적분과 위상

Stokes 정리의 가장 깊은 응용 중 하나가 *위상학적 양의 적분 표현*.

**원 위의 1-form**

원 $S^1$ 위에서 *각도 1-form* $d\theta$ 를 생각하자. 이건 *국소적으로는* $f(\theta)$ 의 미분처럼 보이지만, *글로벌로는* $\theta$ 가 *함수가 아님* ($2\pi$ 의 모호함 때문).

원의 *둘레 적분*:

$$\oint_{S^1} d\theta = 2\pi$$

만약 $d\theta = df$ 인 *글로벌 함수* $f$ 가 있다면 Stokes 정리로

$$\oint_{S^1} d\theta = \oint_{S^1} df = \int_{\partial S^1} f = 0$$

($S^1$ 이 경계가 없으므로). 그런데 실제는 $2\pi \neq 0$. 모순!

따라서 *$d\theta$ 는 글로벌 함수의 미분이 아니다* — *폐형식이지만 완전형식이 아닌* 1-form 의 대표적 예.

이 차이가 *원의 1차 de Rham 코호몰로지가 자명하지 않음* 을 의미. §12 의 자연스러운 동기.

### 14. 정리

이 장에서 다룬 내용을 정리한다.

**1)** *일반 Stokes 정리*:

$$\int_M d\omega = \int_{\partial M} \omega$$

*$k$-차원 다양체 위의 $k$-form 적분 = 그 경계 위의 $(k-1)$-form 적분*.

**2)** 다중 변수 미적분의 *네 적분 정리* (Newton-Leibniz, Green, Stokes 3D, Gauss) 가 *모두 이 한 정리의 특수 사례*.

**3)** *경계의 방향* 은 유도된 방향 (induced orientation) — 바깥 법선과 일관된 방향.

**4)** *증명의 핵심*: 단순 영역에서 부분 적분으로 증명, 분할 (partition of unity) 로 일반 다양체에 확장.

**5)** *좌표 독립성*: pullback 이 외미분과 가환하므로 좌표 선택에 무관.

**6)** *응용 1*: 보존 벡터장의 경로 독립성. Poincaré 보조정리로 단순 영역에서 *비회전 → 보존*.

**7)** *응용 2*: 보존 법칙 (연속 방정식) 과 Noether 정리의 자연스러운 표현.

**8)** *응용 3*: 위상학적 양의 적분 표현 — 폐형식과 완전형식의 차이가 *공간의 위상*.

**9)** 외대수 언어의 *우아함의 정점*: $d^2 = 0$ + Stokes 정리 = 모든 부호 항등식 + 모든 적분 정리.

다음 §12 에서 *de Rham 코호몰로지* — 폐형식과 완전형식의 차이가 *공간의 위상학적 정보를 정확히 인코딩* 한다는 놀라운 사실 — 를 본다. 외대수가 *위상수학의 도구* 로 변신.
