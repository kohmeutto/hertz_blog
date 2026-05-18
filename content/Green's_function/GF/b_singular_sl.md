+++
title = "(b) Singular Sturm-Liouville"
weight = 7
+++

---

### 1. 정규 SL 과 특이 SL

doc 5 §5 의 자기수반 경계 조건은 **정규 (regular) SL 문제** 에 대한 것이다. 즉:

- 정의역 $[x_1, x_2]$ 유한
- $p(x) > 0$ 가 양 끝점에서 유효
- $q(x), w(x)$ 양 끝점에서 유한
- 명시적 경계 조건 부과 가능

이 조건들을 어기는 경우를 **특이 (singular) SL 문제** 라 한다. 세 유형:

| 유형 | 조건 | 예 |
|---|---|---|
| 끝점 특이 | 끝점에서 $p \to 0$, $w \to 0$ 또는 $\infty$, $q \to \infty$ | Bessel ($x=0$), Legendre ($x = \pm 1$) |
| 무한 영역 | $(-\infty, \infty)$ 또는 $[a, \infty)$ | Hermite ($\mathbb{R}$) |
| 복합 | 두 유형의 결합 | Laguerre ($[0, \infty)$, $x=0$ 특이 + 무한 영역) |

특이 SL 에서는 명시적 BC 대신 **특이점에서 함수의 유한성** 또는 **무한 영역에서의 감쇠** 가 부과된다.

---

### 2. Frobenius 분석

ODE $L_p u + \lambda w u = 0$ 의 점 $x_0$ 근방 거동.

**1) 정규점 (regular point)**

$p(x_0) \neq 0$, $q(x_0), w(x_0)$ 유한. 두 독립 해가 $x_0$ 근방에서 해석적.

**2) 정규 특이점 (regular singular point)**

$p(x_0) = 0$, 그러나 $(x-x_0)q(x)/p(x)$, $(x-x_0)^2 q(x)/p(x)$ 등 적절한 곱이 유한.

해를 $u(x) = (x-x_0)^\alpha \sum_n a_n (x-x_0)^n$ 형태로 가정. 최저 차항에서 $\alpha$ 에 대한 이차 방정식 — **indicial equation** — 이 도출된다. 두 근 $\alpha_1, \alpha_2$ 가 두 독립 해의 거동을 결정.

**3) 두 해의 거동**

$\alpha_1 \geq \alpha_2$ 가정.

| $\alpha$ | $x \to x_0$ 거동 |
|---|---|
| $\alpha \geq 0$ | $\sim (x-x_0)^\alpha$, 유한 |
| $\alpha < 0$ | $\sim (x-x_0)^\alpha$, 발산 |
| $\alpha_1 = \alpha_2$ | 두 번째 해에 $\ln(x-x_0)$ 항 |

**4) 유한성 조건**

특이점 $x_0$ 에서 $u(x_0) < \infty$ 를 부과하면 발산 해가 자동 배제된다. 두 독립 해 중 하나가 자동 선택.

**5) 무한 영역**

$x \to \pm\infty$ 에서

$$
\int_{|x| \text{ large}} w(x)\,|u(x)|^2\,dx < \infty
$$

를 부과. 가중 $L^2_w$ 에 속하지 않는 해는 배제.

---

### 3. 자기수반성 조건의 만족

doc 5 §4 의 자기수반 조건:

$$
\bigl[p(x)\,W(\phi^*, \psi)(x)\bigr]_{x_1}^{x_2} = 0
$$

**1) 끝점 $x_i$ 에서 $p(x_i) = 0$ 인 경우**

$\phi, \psi$ 가 §2-(4) 의 유한성 조건을 만족하면 $W(\phi^*, \psi)$ 가 $x_i$ 근방에서 유계 또는 $1/p$ 보다 느리게 발산. 따라서

$$
\lim_{x \to x_i} p(x)\,W(\phi^*, \psi)(x) = 0
$$

예 (Legendre): $p = 1-x^2 \to 0$ at $x = \pm 1$, $P_l$ 양 끝점에서 유한, $P_l'$ 유한. $pW \to 0$.

**2) 무한 영역**

$\phi, \psi \in \mathcal{H}_w$ (가중 $L^2$) 이면 $x \to \pm\infty$ 에서

$$
p(x)\,W(\phi^*, \psi)(x) \to 0
$$

예 (Hermite): $p = e^{-x^2}$, $W \sim$ 다항식. $pW \sim e^{-x^2} \cdot \text{poly}(x) \to 0$.

---

### 4. 그린함수 구성

doc 6 의 Wronskian 공식을 적용. $u_1, u_2$ 의 선택만 달라진다.

**1) $u_1, u_2$ 선택**

- $u_1$: $x = x_1$ 에서의 조건 만족
  - 정규점이면 명시적 BC
  - 특이점이면 유한성 (regular 해)
- $u_2$: $x = x_2$ 에서 동일

**2) 스펙트럼의 이산/연속**

- $w$ 가 무한대에서 빠르게 감쇠 (Hermite $w = e^{-x^2}$, Laguerre $w = e^{-x}$): 이산 스펙트럼
- $w$ 가 감쇠하지 않음 (자유 입자): 연속 스펙트럼

연속 스펙트럼이면 그린함수는 적분 표현:

$$
G(x, x') = \int d\lambda\,\frac{\psi_\lambda(x)\,w(x')\,\psi_\lambda^*(x')}{\lambda}
$$

---

**example1) Bessel ODE**

$$
x^2 y'' + x y' + (\lambda x^2 - \nu^2) y = 0, \quad x \in [0, b], \quad \nu \geq 0
$$

sol)

**(1) SL 형식**

양변을 $x$ 로 나눈 후 가중함수 $w = x$ 를 곱하면:

$$
(x y')' + (\lambda x - \nu^2/x) y = 0
$$

$p = x, q = -\nu^2/x, w = x$.

**(2) 특이점**

$x = 0$: $p \to 0$, $w \to 0$, $q \to \infty$. 정규 특이점.

Indicial equation: $u \sim x^\alpha$ 대입, $\alpha^2 = \nu^2$, $\alpha = \pm\nu$.

**(3) 두 독립 해**

- $J_\nu(\sqrt{\lambda}\,x) \sim x^\nu$ ($x \to 0$ 유한, $\nu \geq 0$)
- $Y_\nu(\sqrt{\lambda}\,x) \sim x^{-\nu}$ 또는 $\ln x$ ($\nu = 0$ 일 때, $x \to 0$ 발산)

**(4) 조건**

$x = 0$ 유한성 → $J_\nu$ 선택. $x = b$ 에서 Dirichlet $J_\nu(\sqrt{\lambda_n}\,b) = 0$ → 고유값 $\lambda_n$ 결정.

**(5) 가중 직교성**

$$
\int_0^b x\,J_\nu(\sqrt{\lambda_m}\,x)\,J_\nu(\sqrt{\lambda_n}\,x)\,dx = \mathcal{N}_n\,\delta_{mn}
$$

**(6) 자기수반성**

$x = 0$: $J_\nu \sim x^\nu$, $J_\nu' \sim \nu x^{\nu-1}$. $pW \sim x \cdot x^{\nu-1} \cdot x^\nu = x^{2\nu} \to 0$ ($\nu > 0$).

$x = b$: Dirichlet $\to W = 0$.

---

**example2) Hermite ODE**

$$
(e^{-x^2} y')' + 2n\, e^{-x^2} y = 0, \quad x \in (-\infty, \infty)
$$

(doc 5 example 1 참조.)

sol)

**(1) 특이성 유형**

무한 영역. $x \to \pm\infty$ 에서 $p = w = e^{-x^2} \to 0$.

**(2) 두 독립 해**

- $H_n(x)$: $n$ 차 Hermite 다항식. $x \to \pm\infty$ 에서 다항식 성장.
- 두 번째 해: $h_n(x) \sim e^{x^2}$ 폭발.

**(3) 조건**

$\int_{-\infty}^\infty e^{-x^2} |u|^2 dx < \infty$ → $H_n$ 만 유효. 정수 $n = 0, 1, 2, \ldots$ 에서 $\lambda_n = 2n$.

**(4) 가중 직교성**

$$
\int_{-\infty}^\infty e^{-x^2}\,H_m(x)\,H_n(x)\,dx = 2^n\,n!\,\sqrt{\pi}\,\delta_{mn}
$$

**(5) 자기수반성**

$x \to \pm\infty$: $pW = e^{-x^2}(H_m^* H_n' - H_m^{*\prime} H_n) \sim e^{-x^2} \cdot \text{poly}(x) \to 0$.

---

**example3) Laguerre ODE**

$$
(x e^{-x} y')' + a\, e^{-x} y = 0, \quad x \in [0, \infty)
$$

(doc 5 example 2 참조.)

sol)

**(1) 특이성 유형**

복합: $x = 0$ 정규 특이점 + 무한 영역.

**(2) 두 독립 해**

$x = 0$ 근방 indicial: $\alpha = 0$ 중근.
- $L_n(x)$: $n$ 차 Laguerre 다항식, $x = 0$ 유한.
- 두 번째 해: $\ln x$ 항 포함, $x = 0$ 발산.

**(3) 조건**

$x = 0$ 유한성 + $x \to \infty$ 가중 $L^2_w$ 유한 → $L_n$ 선택. 정수 $n = 0, 1, 2, \ldots$ 에서 $a = \lambda_n = n$.

**(4) 가중 직교성**

$$
\int_0^\infty e^{-x}\,L_m(x)\,L_n(x)\,dx = \delta_{mn}
$$

**(5) 자기수반성**

$x = 0$: $p = xe^{-x} \to 0$, $L_n, L_n'$ 유한 → $pW \to 0$.

$x \to \infty$: $pW \sim xe^{-x} \cdot \text{poly}(x) \to 0$.

---

**example4) Legendre ODE**

$$
((1-x^2) y')' + l(l+1) y = 0, \quad x \in [-1, 1]
$$

(doc 5 example 3 참조.)

sol)

**(1) 특이성 유형**

양 끝점 $x = \pm 1$ 정규 특이점. $p = 1 - x^2 \to 0$. $w = 1$.

**(2) 두 독립 해**

$x = 1$ 근방 ($1-x =$ small): $\alpha = 0$ 중근.

- $P_l(x)$: 정수 $l$ 에서 $l$ 차 다항식, $x = \pm 1$ 유한.
- $Q_l(x)$: $x \to \pm 1$ 에서 $\ln(1 \mp x)$ 발산.

**(3) 조건**

양 끝점 유한성 → $P_l$ 선택. 정수 $l = 0, 1, 2, \ldots$ 에서 $\lambda_l = l(l+1)$.

**(4) 직교성**

$$
\int_{-1}^1 P_m(x)\,P_n(x)\,dx = \frac{2}{2n+1}\delta_{mn}
$$

**(5) 자기수반성**

$x = \pm 1$: $p = 1 - x^2 \to 0$, $P_l, P_l'$ 유한 → $pW \to 0$.
