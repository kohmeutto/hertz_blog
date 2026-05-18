+++
title = "(b) Sturm-Liouville Green's function"
weight = 6
+++

---

### 1. 동기: 1D 그린함수의 체계적 구성

지금까지 그린함수를 구성한 방식은 세 가지였다.

- **유한 차원 행렬의 역행렬** (doc 1 example 1)
- **스펙트럼 전개** (doc 2): 고유함수 합/적분
- **직접 분할 풀이** (doc 1 example 2): 좌우 영역에서 동차 해 + 연속성 + 점프 조건

세 번째 방법은 1D 박스에서 임시방편으로 적용했지만, **자기수반 1D 미분 연산자의 일반적 골격으로 정식화** 가능하다. 결과는 **Wronskian 기반 닫힌 형식 공식** 이며, 이것이 1D 그린함수 계산의 실용적 주력 도구이다.

본 문서는 doc 5 의 SL 자기수반 조건이 만족되는 상황에서 그린함수를 명시적으로 구성한다.

---

### 2. Wronskian 기반 구성

**설정**

연산자 $L = -L_p/w$, $L_p = D(pD) + q$ 를 자기수반 BC 와 함께 고려한다 (doc 5 §5). 그린함수 정의 방정식:

$$
L_x\, G(x, x') = \delta(x - x')
$$

$\delta$ 가 $x = x'$ 외에서 0 이므로, $x \neq x'$ 영역에서 $L_x G = 0$, 즉 $G$ 는 동차 방정식 $L u = 0$ 의 해이다. 동차 방정식의 두 선형 독립 해를 다음과 같이 선택한다.

- $u_1(x)$: $L u_1 = 0$ 의 해 중 **좌측 BC** ($x = x_1$ 에서) 를 만족
- $u_2(x)$: $L u_2 = 0$ 의 해 중 **우측 BC** ($x = x_2$ 에서) 를 만족

**1) 영역별 표현**

각 영역에서 $G$ 는 동차 해의 배수이다.

$$
G(x, x') = \begin{cases} A(x')\, u_1(x), & x < x' \\ B(x')\, u_2(x), & x > x' \end{cases}
$$

- $x < x'$ 영역: 좌측 BC 를 만족해야 하므로 $u_1$ 사용
- $x > x'$ 영역: 우측 BC 를 만족해야 하므로 $u_2$ 사용
- 계수 $A(x'), B(x')$ 는 source 위치 $x'$ 에 의존

**2) 연속성 조건**

$x = x'$ 에서 $G$ 가 연속이어야 한다 (그렇지 않으면 $G''$ 가 $\delta'$ 를 포함해 모순). 따라서

$$
A(x')\, u_1(x') = B(x')\, u_2(x')
$$

**3) 점프 조건**

$L G = \delta$ 를 $x' - \epsilon$ 부터 $x' + \epsilon$ 까지 적분하고 $\epsilon \to 0$ 극한을 취한다.

$$
\int_{x' - \epsilon}^{x' + \epsilon} L\, G\, dx = 1
$$

$L = -\frac{1}{w}[(pG')' + qG]$ 를 대입. $qG$ 항은 $G$ 가 유계이므로 적분 구간 → 0 에서 사라진다. $w(x) \approx w(x')$:

$$
-\frac{1}{w(x')}\int_{x'-\epsilon}^{x'+\epsilon} (pG')'\, dx = 1
$$

$$
-\frac{1}{w(x')} \cdot p(x')\,\bigl[G'(x'^+) - G'(x'^-)\bigr] = 1
$$

따라서 **점프 조건**:

$$
G'(x'^+) - G'(x'^-) = -\frac{w(x')}{p(x')}
$$

$G'$ 가 source 위치에서 $w/p$ 만큼 **아래로** 점프한다.

**4) 계수 결정**

영역별 표현으로부터 $G'(x'^-) = A u_1'(x')$, $G'(x'^+) = B u_2'(x')$. 점프 조건에 대입:

$$
B u_2'(x') - A u_1'(x') = -\frac{w(x')}{p(x')}
$$

연속성 조건 $A u_1(x') = B u_2(x')$ 로부터 $A = B u_2(x')/u_1(x')$. 대입:

$$
B u_2'(x') - B\, \frac{u_2(x') u_1'(x')}{u_1(x')} = -\frac{w(x')}{p(x')}
$$

$$
\frac{B}{u_1(x')}\bigl[u_1(x') u_2'(x') - u_2(x') u_1'(x')\bigr] = -\frac{w(x')}{p(x')}
$$

대괄호는 Wronskian $W(u_1, u_2)(x') = u_1 u_2' - u_2 u_1'$ 이다. 따라서

$$
B(x') = -\frac{u_1(x')\, w(x')}{p(x')\, W(u_1, u_2)(x')}, \quad A(x') = -\frac{u_2(x')\, w(x')}{p(x')\, W(u_1, u_2)(x')}
$$

**5) Wronskian 공식**

대입하여 정리하면:

$$
G(x, x') = -\frac{u_1(x_<)\, u_2(x_>)\, w(x')}{p(x')\, W(u_1, u_2)(x')}
$$

여기서 $x_< = \min(x, x')$, $x_> = \max(x, x')$. 이것이 **Sturm-Liouville 그린함수의 일반 공식** 이다.

가중함수가 단위 ($w = 1$) 인 경우:

$$
G(x, x') = -\frac{u_1(x_<)\, u_2(x_>)}{p(x')\, W(u_1, u_2)(x')}
$$

---

### 3. SL 형식에서 $pW = $ 상수

§2 의 공식에서 $p(x') W(u_1, u_2)(x')$ 가 $x'$ 에 의존하는 듯 보인다. 그러나 **SL 형식의 강력한 성질** 은 이 곱이 상수라는 것이다.

**정리**: $u_1, u_2$ 가 $L_p u = 0$ 의 두 해이면, $p(x) W(u_1, u_2)(x) = $ 상수.

proof)

$W(u_1, u_2) = u_1 u_2' - u_1' u_2$. 미분:

$$
W' = u_1 u_2'' + u_1' u_2' - u_1'' u_2 - u_1' u_2' = u_1 u_2'' - u_1'' u_2
$$

$u_i$ 가 $L_p u_i = 0$, 즉 $(p u_i')' + q u_i = 0$ 을 만족하므로 $p' u_i' + p u_i'' = -q u_i$, 따라서

$$
u_i'' = -\frac{q u_i + p' u_i'}{p}
$$

대입:

$$
W' = u_1 \cdot \left(-\frac{q u_2 + p' u_2'}{p}\right) - \left(-\frac{q u_1 + p' u_1'}{p}\right) u_2
$$

$$
= -\frac{1}{p}\bigl[q u_1 u_2 + p' u_1 u_2' - q u_1 u_2 - p' u_1' u_2\bigr]
$$

$$
= -\frac{p'}{p}(u_1 u_2' - u_1' u_2) = -\frac{p'}{p}\, W
$$

따라서 $W'/W = -p'/p$. 적분:

$$
\ln W = -\ln p + \text{const} \implies p(x)\, W(u_1, u_2)(x) = C \quad (\text{상수})
$$

**활용**

이 결과로 §2 공식이 간략화된다.

$$
G(x, x') = -\frac{u_1(x_<)\, u_2(x_>)\, w(x')}{C}
$$

상수 $C$ 는 임의의 한 점에서 $pW$ 를 계산해 한 번에 결정. 매 $x'$ 에서 다시 계산할 필요 없다.

---

### 4. 절차 요약

자기수반 1D 미분 연산자의 그린함수 구성:

**1)** 주어진 미분 연산자를 SL 형식 $L = -\dfrac{1}{w}[D(pD) + q]$ 로 변환 (doc 5 §2 가중함수 곱하기). $p, q, w$ 추출.

**2)** 동차 방정식 $L_p u = 0$ (즉 $(pu')' + qu = 0$) 의 두 선형 독립 해 $\varphi_1, \varphi_2$ 찾기.

**3)** BC 를 만족하는 조합 선택:
- $u_1$: 좌측 BC 만족하는 $\varphi_1, \varphi_2$ 의 선형 결합
- $u_2$: 우측 BC 만족하는 $\varphi_1, \varphi_2$ 의 선형 결합

**4)** Wronskian $W(u_1, u_2) = u_1 u_2' - u_1' u_2$ 를 임의의 한 점에서 계산. 상수 $C = pW$ 도출.

**5)** 공식 적용:

$$
G(x, x') = -\frac{u_1(x_<)\, u_2(x_>)\, w(x')}{C}
$$

존재 실패 조건: $C = 0$ 이면 $u_1, u_2$ 가 선형 종속, 즉 같은 동차 해가 양 끝 BC 를 모두 만족 → 고유값 $\lambda = 0$ 이 존재 → 그린함수 부재 (doc 4 §1 의 조건 위배).

---

**example1) 1D Dirichlet 박스 (재확인)**

$$
-\frac{d^2 G}{dx^2} = \delta(x - x'), \quad x \in [0, L], \quad G(0, x') = G(L, x') = 0
$$

sol)

**(1) SL 형식**

$L = -d^2/dx^2$. $L_p = d^2/dx^2$ 형식이 되려면 $p = 1, q = 0$. 가중함수 $w = 1$.

**(2) 동차 해**

$L_p u = u'' = 0$. 두 선형 독립 해: $\varphi_1 = 1$, $\varphi_2 = x$.

**(3) BC 적용**

- $u_1$ 은 좌측 BC $u_1(0) = 0$ 만족: $u_1 = x$
- $u_2$ 는 우측 BC $u_2(L) = 0$ 만족: $u_2 = L - x$

**(4) Wronskian**

$$
W(u_1, u_2) = u_1 u_2' - u_1' u_2 = x \cdot (-1) - 1 \cdot (L - x) = -L
$$

$$
C = p \cdot W = 1 \cdot (-L) = -L
$$

**(5) 공식**

$$
G(x, x') = -\frac{u_1(x_<)\, u_2(x_>) \cdot 1}{-L} = \frac{x_<\,(L - x_>)}{L}
$$

doc 1 example 2 의 결과와 정확히 일치. ✓

---

**example2) Helmholtz 방정식**

$$
-\frac{d^2 G}{dx^2} - k^2 G = \delta(x - x'), \quad x \in [0, L], \quad G(0, x') = G(L, x') = 0
$$

sol)

**(1) SL 형식**

$L = -d^2/dx^2 - k^2 = -(D^2 + k^2)$. $L_p = D^2 + k^2$, 즉 $p = 1, q = k^2, w = 1$.

**(2) 동차 해**

$L_p u = u'' + k^2 u = 0$. 두 선형 독립 해: $\sin(kx), \cos(kx)$.

**(3) BC 적용**

- $u_1(0) = 0$: $u_1 = \sin(kx)$
- $u_2(L) = 0$: $u_2 = \sin\bigl(k(L - x)\bigr)$

**(4) Wronskian**

$$
u_1' = k\cos(kx), \quad u_2' = -k\cos\bigl(k(L - x)\bigr)
$$

$$
W(u_1, u_2) = \sin(kx)\cdot\bigl[-k\cos(k(L-x))\bigr] - k\cos(kx)\cdot\sin(k(L-x))
$$

$$
= -k\bigl[\sin(kx)\cos(k(L-x)) + \cos(kx)\sin(k(L-x))\bigr]
$$

사인 덧셈 공식 ($\sin(A+B) = \sin A \cos B + \cos A \sin B$):

$$
= -k\sin\bigl(kx + k(L-x)\bigr) = -k\sin(kL)
$$

$C = pW = -k\sin(kL)$ (상수 ✓).

**(5) 공식**

$$
G(x, x') = -\frac{\sin(k x_<)\,\sin\bigl(k(L - x_>)\bigr)}{-k\sin(kL)} = \frac{\sin(k x_<)\,\sin\bigl(k(L - x_>)\bigr)}{k\sin(kL)}
$$

**물리적 해석**

$kL = n\pi$ ($n = 1, 2, \ldots$) 일 때 $\sin(kL) = 0$ 이고 $G \to \infty$. 이 정확히 $k^2 = (n\pi/L)^2$ 가 $-d^2/dx^2$ 의 Dirichlet 고유값일 때이며, $L = -d^2/dx^2 - k^2$ 가 영 고유값을 가지므로 그린함수 부재. doc 4 §1 의 존재 조건이 깨지는 명시적 사례. **공명(resonance)** 의 수학적 본질.

---

**example3) Modified Helmholtz 방정식**

$$
-\frac{d^2 G}{dx^2} + \kappa^2 G = \delta(x - x'), \quad x \in [0, L], \quad G(0, x') = G(L, x') = 0
$$

sol)

**(1) SL 형식**

$L = -d^2/dx^2 + \kappa^2 = -(D^2 - \kappa^2)$. $L_p = D^2 - \kappa^2$, 즉 $p = 1, q = -\kappa^2, w = 1$.

**(2) 동차 해**

$L_p u = u'' - \kappa^2 u = 0$. 두 선형 독립 해: $\sinh(\kappa x), \cosh(\kappa x)$ (또는 $e^{\pm \kappa x}$).

**(3) BC 적용**

- $u_1(0) = 0$: $u_1 = \sinh(\kappa x)$
- $u_2(L) = 0$: $u_2 = \sinh\bigl(\kappa(L - x)\bigr)$

**(4) Wronskian**

같은 방식으로 (hyperbolic 덧셈 공식 $\sinh(A+B) = \sinh A \cosh B + \cosh A \sinh B$):

$$
W = -\kappa\sinh(\kappa L)
$$

$C = pW = -\kappa\sinh(\kappa L)$.

**(5) 공식**

$$
G(x, x') = \frac{\sinh(\kappa x_<)\,\sinh\bigl(\kappa(L - x_>)\bigr)}{\kappa\sinh(\kappa L)}
$$

**물리적 해석**

$\sinh(\kappa L) > 0$ for all $\kappa > 0$, $L > 0$ 이므로 존재 실패 없음. $L_p = D^2 - \kappa^2$ 가 음의 고유값을 가지지 않기 때문 ($\lambda_n = -((n\pi/L)^2 + \kappa^2) < 0$, $\hat{A} = -L_p$ 의 고유값은 $((n\pi/L)^2 + \kappa^2) > 0$ 전부 양수). 

지수적 감쇠 ($x$ 와 $x'$ 가 떨어질수록 $G$ 가 $e^{-\kappa|x-x'|}$ 처럼 감쇠) — 차폐된 (screened) 응답. Yukawa 형 상호작용의 1D 버전.

---

### 5. 스펙트럼 표현과 Wronskian 표현의 일치

§2 의 Wronskian 공식

$$
G(x, x') = -\frac{u_1(x_<)\,u_2(x_>)\,w(x')}{p(x')\,W(u_1, u_2)(x')}
$$

에서 분자에 **가중함수 $w(x')$** 가 등장한다. 이는 우연이 아니다. 같은 그린함수의 **스펙트럼 표현** (doc 2 §5, doc 5 §3-(4))

$$
G(x, x') = \sum_i \frac{\psi_i(x)\,w(x')\,\psi_i^*(x')}{\lambda_i}
$$

에도 **같은 자리에** $w(x')$ 가 등장한다.

두 표현은 같은 객체 $G(x, x') = \langle x|L^{-1}|x'\rangle$ 의 다른 좌표적 발현이며, 양쪽 모두에서 $w(x')$ 가 등장하는 이유는 **듀얼 기저 흡수** (doc 5 §3-(3))에 있다.

**1) 두 표현의 공통 기원**

표준 L² 위치 좌표에서 듀얼 기저는

$$
\langle\psi^i|x'\rangle = w(x')\,\psi_i^*(x')
$$

따라서

$$
G(x, x') = \langle x|L^{-1}|x'\rangle = \langle x|\sum_i \frac{|\psi_i\rangle\langle\psi^i|}{\lambda_i}|x'\rangle = \sum_i \frac{\psi_i(x)\,\langle\psi^i|x'\rangle}{\lambda_i} = \sum_i \frac{\psi_i(x)\,w(x')\,\psi_i^*(x')}{\lambda_i}
$$

스펙트럼 표현의 $w(x')$ 는 듀얼 기저의 두 번째 인자에서 직접 등장.

Wronskian 표현에서도 마찬가지. §2 의 도출에서 점프 조건 $\Delta G' = -1/p$ 가 아니라 $\Delta G' = -w/p$ (출처: 등식 $L_x G = \delta(x-x')$ 에 $L = -L_p/w$ 적용 시 $L_p G = -w\delta(x-x')$) 에서 가중 $w(x')$ 가 자연 흡수됨. 같은 메커니즘.

**2) 두 표현이 표상하는 것 — 표 정리**

| 표현 | 좌표 | $w(x')$ 의 출처 | 사용처 |
|---|---|---|---|
| 스펙트럼 | 고유함수 좌표 | 듀얼 기저 $\langle\psi^i\vert x'\rangle$ | 고유값/고유함수 알 때 |
| Wronskian | 위치 좌표 | 점프 조건 $\Delta G' = -w/p$ | 동차 해 알 때 |

**3) 두 표현의 동치성 — example1 에서 확인**

example1 (1D Dirichlet 박스, $w = 1$) 의 두 표현:

- **스펙트럼**: $G(x, x') = \dfrac{2L}{\pi^2}\sum_{n=1}^\infty \dfrac{\sin(n\pi x/L)\sin(n\pi x'/L)}{n^2}$ (doc 2 example 2)
- **Wronskian**: $G(x, x') = \dfrac{x_<\,(L - x_>)}{L}$ (본 문서 example 1)

이미 doc 2 example 2 에서 두 표현이 중앙점 $x = x' = L/2$ 에서 $L/4$ 로 일치함을 확인. 가중 $w = 1$ 이므로 두 표현 모두 $w(x')$ 가 사라진 단순 형태.

가중함수 비자명한 경우 (Hermite, Laguerre 등) 에서는 양쪽 모두 $w(x')$ 가 명시적으로 등장 — Sturm 진동 정리 등 SL 이론의 깊은 결과들이 이 가중 구조 위에서 작동.

**4) NEGF 로의 연결**

본 절의 메시지는 NEGF 챕터에서 직접 사용된다:

- NEGF 의 $G^R(x, x'; E)$ 가 비-Hermitian normal 연산자 $H + i\eta$ (또는 $H - \Sigma$) 의 그린함수
- 좌고유벡터 $\langle\psi^L_i|$ 와 우고유벡터 $|\psi^R_i\rangle$ 의 분리는 듀얼 기저 framework 의 일반화
- 가중 흡수 메커니즘이 self-energy $\Sigma$ 흡수로 변형
- Wronskian 형 직접 구성도 가능 (lead 모드 매칭, Datta 형)

doc 5-6 의 통일적 시야가 NEGF 의 두 접근법 (스펙트럼 vs 산란) 을 같은 framework 안에서 다룰 수 있게 한다.
