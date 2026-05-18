+++
title = "(b) Sturm-Liouville form"
weight = 5
+++

---

### 1. SL 선형 연산자 형식의 위치

자기수반 1차원 미분 연산자의 표준 형식은 **Sturm-Liouville 형식** 이다.

$$
L_p = \frac{d}{dx}\left(p(x)\frac{d}{dx}\right) + q(x) = D(p(x)D) + q(x)
$$

조건:
- $p(x) > 0$ (구간 내부에서)
- $p(x)$ 가 미분 가능
- $q(x)$ 가 실수 함수

학습자가 자연스럽게 던지는 질문: **"왜 SL 을 배우는가? 다른 미분방정식 형태도 많은데?"** 이 질문에 대한 답은 다음 도식에 압축된다.

```
              [PDE 분류]
       /        |          \
   타원형    쌍곡선형    포물선형
       \        |          /
        시간 진화 분리
              |
        [공간 고유값 문제]  ← SL form
              |
         [ODE 형태들]    ← SL = 자기수반 divergence form 표현
   (일반/표준/SL/Liouville normal/Schrödinger/Riccati)
```

SL 은 두 차원의 **통합 form**:

- **수직 통합**: 모든 PDE 분류 (타원형, 쌍곡선형, 포물선형) → 변수 분리 → 공간 부분이 SL
- **수평 통합**: 다양한 ODE 표현 (일반, 표준, Liouville normal, Schrödinger 등) → 모두 SL 로 변환 가능

이 두 통합을 풀어보면 SL 이 왜 보편적 무대인지가 드러난다.

**1) 수직 통합 — PDE 분류로부터의 환원**

물리/공학의 2계 선형 PDE 는 계수 행렬의 signature 에 따라 세 부류로 분류된다.

| 분류 | 대표 식 | 물리 |
|---|---|---|
| **타원형** | $\nabla^2 u = f$ (Poisson, Laplace) | 정상상태, 평형 |
| **쌍곡선형** | $\partial_t^2 u - c^2\nabla^2 u = 0$ (wave) | 파동 전파 |
| **포물선형** | $\partial_t u - D\nabla^2 u = 0$ (heat) | 확산, 시간 진화 |

이 세 분류 모두에 **변수 분리 (separation of variables)** 를 적용하면 **공간 부분이 SL 형태로 환원** 된다.

- **타원형 자체**: $-\nabla^2 u = \lambda u$ → 직접 SL (시간 분리 불필요)
- **쌍곡선형 시간 분리**: $u(x,t) = X(x)T(t)$ 대입 후 $X$ 부분 → SL
- **포물선형 시간 분리**: 같은 방법으로 $X$ 부분 → SL

→ **PDE 분류와 무관하게, 공간 고유값 문제는 SL** 이라는 결론.

**2) 수평 통합 — 다양한 ODE 표현들의 환원**

같은 1D 2계 ODE 도 여러 form 으로 표현 가능. 각 form 이 강조하는 측면이 다르다.

| 형태 | 식 | 강조 | 제약 |
|---|---|---|---|
| 일반 | $p_0 u'' + p_1 u' + p_2 u = f$ | 가장 유연 | 구조 안 보임 |
| 표준 (standard) | $u'' + Pu' + Qu = R$ | 깔끔한 1차 계수 | 자기수반 아님 |
| **SL (자기수반)** | $(pu')' + qu = f$ | **자기수반 + divergence form + 변분 원리** | 가중함수 필요 |
| Liouville normal | $u'' + (\lambda - V)u = 0$ | Schrödinger 와 동일 | 가변 mass 못 표현 |
| Schrödinger (물리) | $-\frac{\hbar^2}{2m}u'' + Vu = Eu$ | 양자역학 직관 | 균질 매질 가정 |
| Riccati | $w' + w^2 + Q = 0$, $w = u'/u$ | 1차 비선형 | 비선형 |

이들은 모두 서로 변환 가능 — Liouville 변환, 가중함수 곱하기 (§2). SL form 은 그 중 **자기수반 구조 + divergence form** 을 가장 잘 드러내는 표현.

**3) 왜 SL 형식이 자연스러운가**

수직/수평 통합의 중심에 SL 이 있는 이유는 네 가지.

**(a) 자기수반 구조 내장**

$L_p^\dagger = L_p$ 가 형식적으로 성립, 경계항 $\mathcal{B}_{L_p} = pW$ (§4) 만 처리하면 됨. 이로부터 b_normal_operators.md §2 의 모든 결과 적용:
- 실수 고유값
- biorthogonal 완비 기저
- 영공간-열공간 직교

**(b) Divergence form 의 물리적 의미**

$(pu')$ 자체가 **플럭스 (flux)** 로 해석:
- 양자수송: 확률 전류 $\propto W(\psi^*, \psi)$
- 전자수송: 전류
- 열수송: 열 플럭스
- 정전기학: 전기 변위장 $\mathbf{D} = \epsilon\mathbf{E}$

모두 같은 divergence-form 구조. 보존 법칙이 form 안에 내장.

**(c) 변분 원리 (variational principle)**

SL 방정식은 변분원리

$$
\delta \int_{x_1}^{x_2}\left[p(u')^2 + qu^2 - \lambda w u^2\right]dx = 0
$$

의 Euler-Lagrange 방정식. 에너지 functional 의 자연 form. 양자역학의 작용 원리와 직결.

**(d) 다차원 일반화**

1D 의 $D(pD) + q$ 가 다차원 $\nabla\cdot(p(\mathbf{r})\nabla) + q(\mathbf{r})$ 로 자연 일반화. 이는 **타원형 PDE operator** 의 일반 form.

특히 **가변 유효질량 Schrödinger 방정식**

$$
-\nabla\cdot\left[\frac{\hbar^2}{2m^*(\mathbf{r})}\nabla\psi\right] + V(\mathbf{r})\psi = E\psi
$$

가 정확히 이 form. 4H-SiC Schottky 다이오드의 계면, 가변 유효질량, 위치 의존 potential — NEGF/SBD 의 자연 무대.

**4) Poisson 등 — SL 의 특수 케이스로서**

$L_p$ 의 $p, q$ 선택에 따라 친숙한 식들이 특수 케이스로 등장:

| $p(x)$ | $q(x)$ | 식 | 물리적 해석 |
|---|---|---|---|
| $1$ | $0$ | $D^2$ | 1D Laplacian (균질 Poisson) |
| $\epsilon(x)$ | $0$ | $D(\epsilon D)$ | 불균질 매질 Poisson |
| $\hbar^2/(2m^*(x))$ | $V(x)$ | $D(pD) + V$ | **가변 유효질량 Schrödinger** |
| $1$ | $k^2$ | $D^2 + k^2$ | Helmholtz |
| $1$ | $-\kappa^2$ | $D^2 - \kappa^2$ | Modified Helmholtz (Yukawa) |

"SL 은 Poisson 의 일반화" 라는 직관이 부분적으로 옳다 — **divergence form $D(pD)$ 가 골격이고, $+q$ 가 potential 항으로 일반화**.

---

### 2. SL 형식으로의 변환과 가중함수

§1-(2) 의 수평 통합을 실제로 수행한다. 임의의 2계 미분 연산자

$$
L = p_0(x)\frac{d^2}{dx^2} + p_1(x)\frac{d}{dx} + p_2(x)
$$

를 SL 형식 $L_p = D(pD) + q$ 로 변환하는 절차.

**1) $p_0'(x) = p_1(x)$ 인 경우 — 즉시 SL**

$$
L = p_0 D^2 + p_0' D + p_2 = D(p_0 D) + p_2
$$

즉시 SL 형식 ($p = p_0$, $q = p_2$, 가중함수 불필요).

**2) $p_0'(x) \neq p_1(x)$ 인 경우 — 가중함수 곱하기**

양의 함수 $w(x) > 0$ 를 곱해 SL 형식으로 만든다:

$$
w(x)\,L = w p_0 D^2 + w p_1 D + w p_2 \to D(p D) + q
$$

조건: $p = w p_0$ 이고 $(w p_0)' = w p_1$. 두 번째 조건에서

$$
\frac{w'(x)}{w(x)} = \frac{p_1(x) - p_0'(x)}{p_0(x)}
$$

이를 풀면

$$
\boxed{w(x) = \frac{1}{p_0(x)}\exp\left(\int dx\,\frac{p_1(x)}{p_0(x)}\right)}
$$

이 양의 함수 $w(x)$ 가 **가중함수 (weight function)**.

**3) 가중함수의 두 얼굴: 적분 인자 = SL 가중**

방금 도출한 $w(x)$ 는 **두 역할을 동시에 수행하는 같은 함수**:

| 관점 | 역할 | 의미 |
|---|---|---|
| 형식 변환 | 적분 인자 (integrating factor) | $L$ 을 SL 형식 $L_p = wL$ 로 만드는 도구 |
| 스펙트럼 | 가중함수 (weight function) | §3 의 고유함수 가중 직교성의 가중 |

표준 교재들은 두 관점을 별개로 다루며 "적분 인자 $r(x)$" 와 "가중함수 $w(x)$" 를 분리해 표기하는 경우가 흔하다. 그러나 같은 함수이다. **본 책에서는 처음부터 $w(x)$ 로 표기하고 가중함수라는 이름으로 통일**.

이 통일은 단순한 표기 단축이 아니라 하나의 통찰을 명시적으로 만든다 — **ODE 형식 변환의 적분 인자가 SL 고유값 문제의 가중과 같다는 것은 우연이 아니다**. 둘 다 같은 자기수반 구조의 발현. §3 에서 이를 명시적으로 본다.

---

### 3. 가중함수와 고유함수의 직교성

§2 의 가중함수 $w(x)$ 가 고유값 문제에서 어떻게 등장하는지 본다.

**1) SL 고유값 문제의 표준 형태**

원본 ODE 의 고유값 방정식 $L u_n + \lambda_n u_n = 0$ (즉 $p_0 u_n'' + p_1 u_n' + p_2 u_n + \lambda_n u_n = 0$) 의 양변에 §2 의 가중함수 $w(x)$ 를 곱한다.

$$
w(x)\,L u_n + \lambda_n\,w(x)\,u_n = 0
$$

§2 에 의해 $wL = L_p$, 따라서 SL 고유값 문제의 **표준 형태**:

$$
L_p u_n + \lambda_n\,w(x)\,u_n = 0 \quad \text{또는 동등하게} \quad L_p u_n = -\lambda_n\,w(x)\,u_n
$$

물리에서 흔히 쓰는 standard form 으로 복원하려면 $L \equiv -L_p/w$ 정의:

$$
\boxed{L\,u_n = \lambda_n\,u_n, \quad L = -\frac{1}{w(x)}\bigl[D(p(x)D) + q(x)\bigr]}
$$

가중함수 $w(x) > 0$ 가 §2 의 변환에서 자연스럽게 등장한 후, §3 에서는 고유값 문제의 가중 역할을 수행 — **같은 함수, 두 얼굴**.

**2) 가중 직교성**

자기수반 SL 연산자의 서로 다른 고유값에 대응하는 고유함수들은 다음 직교성을 만족한다.

$$
\int_{x_1}^{x_2} w(x)\,\psi_m^*(x)\,\psi_n(x)\,dx = \delta_{mn}
$$

proof) $L_p$ 의 자기수반성 (§4) 으로부터 $\langle\psi_m|L_p\psi_n\rangle = \langle L_p\psi_m|\psi_n\rangle$. $L_p\psi_k = -\lambda_k w \psi_k$ 대입:

$$
-\lambda_n\int w\psi_m^*\psi_n\,dx = -\lambda_m^*\int w\psi_m^*\psi_n\,dx
$$

$$
(\lambda_m^* - \lambda_n)\int w\psi_m^*\psi_n\,dx = 0
$$

$m = n$ 에서 $\lambda_m^* = \lambda_m$ (실수 고유값). $m \neq n$, $\lambda_m \neq \lambda_n$ 에서 가중 적분 = 0. 정규화하면 위 식.

**3) 듀얼 기저 표기**

가중 직교성은 듀얼 기저 표기로 옮기면 자동으로 표준 biorthogonality 가 된다. 표준 L² 위치 좌표에서:

$$
\langle\psi^i|x\rangle = w(x)\,\psi_i^*(x)
$$

확인:

$$
\langle\psi^i|\psi_j\rangle = \int dx\,\langle\psi^i|x\rangle\langle x|\psi_j\rangle = \int dx\,w(x)\,\psi_i^*(x)\,\psi_j(x) = \delta^i_j
$$

가중함수는 듀얼 기저의 위치 표현 안에 자연스럽게 살아 있다. 이로부터 b_normal_operators.md §2 의 모든 결과 — 스펙트럼 분해 $L = \sum_i \lambda_i|\psi_i\rangle\langle\psi^i|$, 완비성 $\hat{I} = \sum_i|\psi_i\rangle\langle\psi^i|$, 영공간-열공간 직교 등 — 가 그대로 적용된다.

**4) 그린함수의 스펙트럼 표현**

$L^{-1} = \sum_i \lambda_i^{-1}|\psi_i\rangle\langle\psi^i|$ 의 표준 L² 위치 좌표 표현:

$$
G(x,x') = \langle x|L^{-1}|x'\rangle = \sum_i \frac{\psi_i(x)\,w(x')\,\psi_i^*(x')}{\lambda_i}
$$

가중 $w(x')$ 는 듀얼 기저 $\langle\psi^i|x'\rangle = w(x')\psi_i^*(x')$ 에서 자연 발생. 이 형태가 doc 6 의 Wronskian 공식과 일치한다 — 같은 객체의 두 표현.

---

### 4. 자기수반 조건: 쌍선형 경계 형식의 소실

§3 의 가중 직교성과 모든 후속 결과는 $L_p$ 의 자기수반성에 의존한다. 언제 $L_p$ 가 자기수반인지 b_adjoint.md §3 의 일반 framework 으로 답한다.

**1) b_adjoint.md §3 의 일반 결과**

무한 차원 함수 공간에서 임의의 미분 연산자에 대해

$$
\langle\phi|\hat{A}\psi\rangle = \langle\hat{A}^\dagger\phi|\psi\rangle + \mathcal{R}_{\hat{A}}[\phi, \psi]
$$

경계항 $\mathcal{R}_{\hat{A}}$ 는 **쌍선형 경계 형식 (sesquilinear boundary form)** $\mathcal{B}_{\hat{A}}$ 의 경계 적분.

$$
\mathcal{R}_{\hat{A}}[\phi, \psi] = \int_{\partial\Omega} d^2s\,\mathcal{B}_{\hat{A}}[\phi, \psi]
$$

$\mathcal{B}_{\hat{A}}$ 는 $\phi$ 에 대해 conjugate linear, $\psi$ 에 대해 linear.

$L_p$ 에 대해 형식적 자기수반성 $L_p^\dagger = L_p$ (다음 계산에서 자동으로 확인됨) 가 성립하므로, 자기수반 여부는 전적으로 $\mathcal{R}_{L_p}$ 의 소실 여부에 달려있다.

**2) $L_p$ 의 쌍선형 경계 형식**

$L_p = D(pD) + q$ ($p, q$ 실수) 에 대한 $\mathcal{B}_{L_p}$ 를 직접 계산한다.

$$
\langle\phi|L_p\psi\rangle - \langle L_p\phi|\psi\rangle = \int_{x_1}^{x_2} dx\,\bigl[\phi^*\,L_p\psi - (L_p\phi)^*\,\psi\bigr]
$$

피적분함수를 풀어 쓰면 ($q$ 항 소거, $p$ 실수):

$$
\phi^*\,L_p\psi - (L_p\phi)^*\,\psi = \phi^*(p\psi')' - (p\phi^{*\prime})'\,\psi
$$

핵심 관찰: 이 식은 **전미분**.

$$
\phi^*(p\psi')' - (p\phi^{*\prime})'\,\psi = \frac{d}{dx}\bigl[p(x)\bigl(\phi^*\psi' - \phi^{*\prime}\psi\bigr)\bigr]
$$

따라서 1차원 영역 $[x_1, x_2]$ 에서 $L_p$ 의 쌍선형 경계 형식은:

$$
\boxed{\mathcal{B}_{L_p}[\phi, \psi] = p(x)\bigl[\phi^*\psi' - \phi^{*\prime}\psi\bigr] = p(x)\,W(\phi^*, \psi)}
$$

여기서 $W(\phi^*, \psi) := \phi^*\psi' - \phi^{*\prime}\psi$ 는 두 함수의 **Wronskian**. 1차원에서 $\partial\Omega = \{x_1, x_2\}$ 이므로 경계항은 두 끝점에서의 평가:

$$
\mathcal{R}_{L_p}[\phi, \psi] = \bigl[\mathcal{B}_{L_p}\bigr]_{x_1}^{x_2} = \bigl[p(x)\,W(\phi^*, \psi)(x)\bigr]_{x_1}^{x_2}
$$

**쌍선형 구조 확인**: $\mathcal{B}_{L_p}$ 에서 $\phi$ 는 conjugate 로만 등장 ($\phi^*, \phi^{*\prime}$), $\psi$ 는 직접 등장 ($\psi, \psi'$) — b_adjoint.md §3 의 sesquilinear 구조와 정확히 일치.

proof of 전미분 등식)

$\dfrac{d}{dx}[p(\phi^*\psi' - \phi^{*\prime}\psi)]$ 를 직접 미분:

$$
= (p\phi^*)'\psi' + p\phi^*\psi'' - (p\phi^{*\prime})'\psi - p\phi^{*\prime}\psi'
$$

$(p\phi^*)' = p'\phi^* + p\phi^{*\prime}$:

$$
= p'\phi^*\psi' + p\phi^{*\prime}\psi' + p\phi^*\psi'' - (p\phi^{*\prime})'\psi - p\phi^{*\prime}\psi'
$$

$\pm p\phi^{*\prime}\psi'$ 항 소거:

$$
= p'\phi^*\psi' + p\phi^*\psi'' - (p\phi^{*\prime})'\psi = \phi^*(p\psi')' - (p\phi^{*\prime})'\psi
$$

(마지막에서 $p'\psi' + p\psi'' = (p\psi')'$ 사용.) 검증 완료.

**3) 자기수반 조건**

$L_p$ 가 자기수반 ($\langle\phi|L_p\psi\rangle = \langle L_p\phi|\psi\rangle$) 이려면 정의역의 모든 $\phi, \psi$ 에 대해

$$
\bigl[p(x)\,W(\phi^*, \psi)(x)\bigr]_{x_1}^{x_2} = 0
$$

이 성립해야 한다. 즉 **쌍선형 경계 형식이 양 끝점의 차로 사라져야 한다**. 이 조건을 만족시키는 경계 조건의 분류가 §5 의 주제이다.

---

### 5. 자기수반을 보장하는 경계 조건

§4 의 조건 $[p\,W(\phi^*, \psi)]_{x_1}^{x_2} = 0$ 을 만족시키는 표준 경계 조건들.

**1) Separable (분리형, Robin) 경계 조건**

각 끝점에서 함수와 도함수의 선형 결합이 0:

$$
a_1\,u(x_1) + a_2\,u'(x_1) = 0, \quad (a_1, a_2) \neq (0, 0)
$$

$$
b_1\,u(x_2) + b_2\,u'(x_2) = 0, \quad (b_1, b_2) \neq (0, 0)
$$

여기서 $a_1, a_2, b_1, b_2$ 는 실수.

$x_1$ 에서 이 조건이 어떻게 경계 형식을 소실시키는지 확인 ($a_1 \neq 0$ 가정):

$$
\phi(x_1) = -\frac{a_2}{a_1}\phi'(x_1), \quad \psi(x_1) = -\frac{a_2}{a_1}\psi'(x_1)
$$

Wronskian:

$$
W(\phi^*, \psi)(x_1) = \phi^*(x_1)\psi'(x_1) - \phi^{*\prime}(x_1)\psi(x_1)
$$

$$
= -\frac{a_2}{a_1}\phi^{*\prime}(x_1)\psi'(x_1) + \frac{a_2}{a_1}\phi^{*\prime}(x_1)\psi'(x_1) = 0
$$

$\mathcal{B}_{L_p}[\phi, \psi](x_1) = p(x_1)\,W(\phi^*, \psi)(x_1) = 0$. 같은 논리로 $x_2$ 에서도 0. 경계항 사라짐. ✓

**2) Dirichlet, Neumann은 Separable의 특수 경우**

| BC | $a_1, a_2$ | $b_1, b_2$ | 의미 |
|---|---|---|---|
| Dirichlet ($u=0$) | $a_1=1, a_2=0$ | $b_1=1, b_2=0$ | 양 끝 고정 |
| Neumann ($u'=0$) | $a_1=0, a_2=1$ | $b_1=0, b_2=1$ | 양 끝 자유 (도함수=0) |
| Robin (혼합) | 일반 | 일반 | 양 끝에서 혼합 |

**3) Periodic (주기) 경계 조건**

$$
u(x_1) = u(x_2), \quad u'(x_1) = u'(x_2), \quad p(x_1) = p(x_2)
$$

이 경우 $\phi, \psi$ 모두 양 끝에서 같은 값과 같은 도함수를 가지므로

$$
W(\phi^*, \psi)(x_1) = W(\phi^*, \psi)(x_2)
$$

$p$ 도 양 끝에서 같으므로

$$
[pW]_{x_1}^{x_2} = p(x_2)W(x_2) - p(x_1)W(x_1) = 0
$$

**4) 충분 조건이지 필요 조건은 아니다**

위의 BC들은 자기수반성을 보장하는 **충분 조건**. 표준 SL 형태가 깨지는 특수 케이스 (예: 끝점에서 $p \to 0$, 정의역이 무한 영역) 에도 자기수반성이 성립할 수 있다. 이때는 BC 대신 **특이점에서 함수의 유한성/감소** 조건이 같은 역할을 한다. 자세한 내용은 doc 7 (Singular Sturm-Liouville) 참조.

---

**example1) Hermite ODE**

$$
y'' - 2xy' + 2ny = 0
$$

sol)

$p_0 = 1, p_1 = -2x, p_2 = 0$. 우변에 고유값 형식 $-2ny$.

$p_0' = 0 \neq p_1 = -2x$ 이므로 가중함수 필요.

$$
w(x) = \exp\left(\int -2x\, dx\right) = e^{-x^2}
$$

곱하면

$$
e^{-x^2}(D^2 - 2xD)u_n = -2n\, e^{-x^2}\, u_n
$$

$$
\implies D\bigl[e^{-x^2}\, D\bigr] u_n = -2n\, e^{-x^2}\, u_n
$$

읽어내면

$$
p(x) = e^{-x^2}, \quad q(x) = 0, \quad w(x) = e^{-x^2}, \quad \lambda_n = 2n
$$

**가중함수 = $p(x)$** 인 점이 흥미롭다 (이 ODE 의 특수성). 일반적으로 둘은 다름.

(특이 SL: 정의역이 $(-\infty, \infty)$ 이며 무한대에서 $p \to 0$. doc 7 참조.)

---

**example2) Laguerre ODE**

$$
xy'' + (1-x)y' + a y = 0
$$

sol)

$p_0 = x, p_1 = 1-x$. $p_0' = 1 \neq p_1 = 1-x$. 가중함수:

$$
w(x) = \frac{1}{x}\exp\left(\int \frac{1-x}{x}\, dx\right) = \frac{1}{x}\exp(\ln x - x) = e^{-x}
$$

곱하면

$$
e^{-x}\bigl[x D^2 + (1-x)D\bigr] u_n = -a\, e^{-x}\, u_n
$$

$$
\implies D\bigl[xe^{-x}\, D\bigr] u_n = -a\, e^{-x}\, u_n
$$

읽어내면

$$
p(x) = xe^{-x}, \quad q(x) = 0, \quad w(x) = e^{-x}, \quad \lambda_n = a
$$

(특이 SL: 정의역이 $[0, \infty)$, $x=0$ 에서 $p \to 0$, $x \to \infty$ 에서 $p \to 0$.)

---

**example3) Legendre ODE**

$$
(1-x^2)y'' - 2xy' + l(l+1)y = 0
$$

sol)

$p_0 = 1-x^2, p_1 = -2x$. $p_0' = -2x = p_1$ ✓. 즉시 SL 형식 — **가중함수 불필요** ($w = 1$):

$$
D\bigl[(1-x^2)\, D\bigr] u_n = -l(l+1)\, u_n
$$

읽어내면

$$
p(x) = 1-x^2, \quad q(x) = 0, \quad w(x) = 1, \quad \lambda_n = l(l+1)
$$

(특이 SL: 정의역이 $[-1, 1]$ 이며 양 끝점 $x = \pm 1$ 에서 $p \to 0$.)

---

**example4) Chebyshev ODE**

$$
(1-x^2)y'' - xy' + n^2 y = 0
$$

sol)

$p_0 = 1-x^2, p_1 = -x$. $p_0' = -2x \neq p_1 = -x$. 가중함수:

$$
w(x) = \frac{1}{1-x^2}\exp\left(\int \frac{-x}{1-x^2}\, dx\right) = \frac{1}{1-x^2}\sqrt{1-x^2} = \frac{1}{\sqrt{1-x^2}}
$$

곱하면

$$
\frac{1}{\sqrt{1-x^2}}\bigl[(1-x^2)D^2 - xD\bigr] u_n = -\frac{n^2}{\sqrt{1-x^2}}\, u_n
$$

$$
\implies D\bigl[\sqrt{1-x^2}\, D\bigr] u_n = -\frac{n^2}{\sqrt{1-x^2}}\, u_n
$$

읽어내면

$$
p(x) = \sqrt{1-x^2}, \quad q(x) = 0, \quad w(x) = \frac{1}{\sqrt{1-x^2}}, \quad \lambda_n = n^2
$$

(특이 SL: 정의역이 $[-1, 1]$ 이며 양 끝점에서 $p \to 0$, $w \to \infty$.)
