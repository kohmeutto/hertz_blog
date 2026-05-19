+++
title = "(b) Uniqueness"
weight = 4
+++

---

### 1. 시작: 두 사람이 같은 문제를 풀었다

PDE 와 BC 가 주어진 문제를 두 사람이 풀었다고 하자.

- A 의 답: $V_1(\vec{x})$
- B 의 답: $V_2(\vec{x})$

자연스러운 질문: **두 답이 같은가, 다른가?**

만약 항상 같다면 (PDE 와 BC 가 적절히 주어진 경우), 그 문제의 답은 "유일하게 결정"된다. 이것이 **유일성 정리 (uniqueness theorem)** 의 의미.

문제 풀이의 신뢰성을 위해 이 유일성이 보장되어야 한다 — 답이 여러 개라면, 어떤 답을 택해야 하는지 모호해진다. 본 문서에서 유일성이 보장되는 조건을 따져본다.

---

### 2. 두 답의 차이를 분석한다

A 와 B 의 답이 같은지 물어보는 가장 직접적 방법: **차이를 계산하기**.

$$
W(\vec{x}) := V_1(\vec{x}) - V_2(\vec{x})
$$

$W = 0$ (모든 점에서) 임을 보일 수 있다면 $V_1 = V_2$ — 유일성 성립.

$W$ 의 성질부터 알아본다.

**(1) $W$ 가 만족하는 PDE**:

$V_1, V_2$ 가 같은 PDE 의 해이므로

$$
\hat{L}V_1 = f, \quad \hat{L}V_2 = f
$$

뺄셈

$$
\hat{L}W = \hat{L}V_1 - \hat{L}V_2 = f - f = 0
$$

**$W$ 는 동질 PDE 의 해** (예: Laplace 방정식 $\nabla^2 W = 0$). 우변이 0 이라는 뜻.

**(2) $W$ 가 만족하는 BC**:

$V_1, V_2$ 가 같은 BC 의 해이므로 boundary 에서 차이 0.

- Dirichlet BC ($V|_{\partial\Omega} = g$ 주어짐): $W|_{\partial\Omega} = g - g = 0$
- Neumann BC ($\partial_n V|_{\partial\Omega} = h$ 주어짐): $\partial_n W|_{\partial\Omega} = h - h = 0$
- 어떤 BC 든: **boundary 에서 $W$ 의 정보가 0**

이제 질문이 바뀐다:

> **동질 PDE 와 0 BC 를 만족하는 $W$ 가 $W = 0$ 이외에 가능한가?**

이게 "유일성 정리" 라고 부르는 객체의 실제 질문.

---

### 3. $W$ 가 0 임을 보이려면 어떻게 하는가

$W$ 가 모든 점에서 0 임을 직접 증명하기 어렵다. 무한 차원 함수이므로 모든 점을 점검할 수 없음.

대신 **적분으로 $W$ 의 정보를 압축**한다. $W$ 의 "전체 크기" 를 측정하는 적분:

$$
\int_\Omega|W|^2\,d^n x \quad \text{또는} \quad \int_\Omega|\nabla W|^2\,d^n x
$$

이런 적분이 0 이면 $W$ 가 거의 모든 점에서 0 임이 도출된다 ($|\cdot|^2 \geq 0$ 이고 적분이 0 이려면 곱이 0 이어야 하므로).

따라서 전략:

**$W$ 의 어떤 적분이 0 임을 보이자.** 그러면 $W$ 의 크기가 모든 곳에서 0 → $W = 0$ → 유일성.

---

### 4. 자연스러운 적분 — $W$ 와 $\hat{L}W$ 의 만남

어떤 적분이 유용한가? $W$ 가 만족하는 식 $\hat{L}W = 0$ 을 활용하는 적분이 자연스럽다.

$\hat{L}W = 0$ 의 양변에 $W$ 를 곱하고 영역 위에서 적분:

$$
\int_\Omega W\,(\hat{L}W)\,d^n x = \int_\Omega W\cdot 0\,d^n x = 0
$$

따라서 좌변 = 0. 이게 출발점.

이제 **좌변을 직접 계산** 해서 무엇을 얻는지 본다. 여기서 부분 적분이 자동으로 등장한다 ($\hat{L}$ 이 미분 작용소이므로).

$\hat{L} = -\nabla^2$ (Laplace, 가장 흔한 케이스) 로 진행:

$$
\int_\Omega W(-\nabla^2 W)\,d^n x = ?
$$

부분 적분 (Stokes 정리). $\nabla\cdot(W\nabla W) = |\nabla W|^2 + W\nabla^2 W$ 이므로

$$
\int_\Omega \nabla\cdot(W\nabla W)\,d^n x = \int_\Omega|\nabla W|^2 d^n x + \int_\Omega W\nabla^2 W\,d^n x
$$

좌변은 발산 정리로 boundary 적분:

$$
\int_\Omega\nabla\cdot(W\nabla W)d^n x = \int_{\partial\Omega}W\,\partial_n W\,dS
$$

따라서

$$
\int_{\partial\Omega}W\,\partial_n W\,dS = \int_\Omega|\nabla W|^2 d^n x + \int_\Omega W\nabla^2 W\,d^n x
$$

정리하면

$$
\boxed{\int_\Omega W(-\nabla^2 W)\,d^n x = \int_\Omega|\nabla W|^2 d^n x - \int_{\partial\Omega}W\,\partial_n W\,dS}
$$

이게 **Green 첫 항등식** — 부분 적분의 다차원 형태.

---

### 5. 등장한 boundary 항이 정확히 $\mathcal{R}\hat{L}$ 이다

§4 의 boxed 식의 boundary 항:

$$
\int_{\partial\Omega}W\,\partial_n W\,dS
$$

이 객체가 b_adjoint.md, b_boundary.md 에서 다룬 $\mathcal{R}\hat{L}$ 와 어떤 관계인가? **직접 매핑**한다.

**1차원에서 단순화**

$\Omega = [a, b]$ 의 경우 §4 의 도출이 다음과 같이 단순화된다.

$$
\int_a^b W(-W'')\,dx = \int_a^b(W')^2\,dx - [WW']_a^b
$$

(1차원 부분 적분 한 번.) Boundary 항 = $[WW']_a^b$ — 양 끝점에서 평가한 값.

이걸 b_adjoint.md §3 의 1차 미분 레지듀와 비교한다.

$$
\mathcal{R}\hat{D}[\phi, \psi] = [\phi^*\psi]_a^b
$$

여기에 $\phi = W$, $\psi = W'$ 을 대입:

$$
\mathcal{R}\hat{D}[W, W'] = [WW']_a^b
$$

**좌변과 우변이 정확히 일치**. 따라서

$$
\boxed{\text{Green 첫 항등식의 boundary 항} = \mathcal{R}\hat{D}[W, W']}
$$

부분 적분에서 발생한 boundary term 이 정확히 우리가 정의해온 $\mathcal{R}$ 객체.

**다차원 일반화**

다차원에서는 boundary 적분이 표면 위의 적분으로 일반화된다 (b_boundary.md §2 의 다차원 R).

$$
\mathcal{R}\hat{D}_n[W, \partial_n W] = \int_{\partial\Omega}W\,\partial_n W\,dS
$$

1차원의 양 끝점 평가가 다차원에서는 boundary 표면 위의 적분으로 확장. 객체의 본질은 같음.

**왜 $\mathcal{R}$ 이 등장했는가**

$W$ 가 0 임을 보이려고 적분 ($\int W(\hat{L}W)d^n x$) 을 했고, 그 적분을 계산하려고 부분 적분을 했다. 부분 적분이 boundary term 을 만들었고, 그 boundary term 이 정확히 $\mathcal{R}\hat{L}$ 의 한 형태.

순서를 보면:

```
W = 0 보이고 싶음
   ↓
W 의 적분 분석 (∫W(LW))
   ↓
적분 계산하려 부분 적분
   ↓
부분 적분이 boundary term 만듦
   ↓
그 boundary term = R[W, W']
```

마지막 단계가 핵심: 부분 적분의 boundary term 이 우리의 $\mathcal{R}$ 정의와 정확히 같은 객체. 새 도구를 가져온 게 아니라 같은 객체가 다른 맥락에서 등장.

---

### 6. 좌변과 우변을 결합

§4 의 boxed 식의 좌변:

$$
\int_\Omega W(-\nabla^2 W)\,d^n x
$$

$W$ 가 동질 PDE $\nabla^2 W = 0$ 의 해이므로 **좌변 = 0**.

따라서

$$
0 = \int_\Omega|\nabla W|^2 d^n x - \int_{\partial\Omega}W\,\partial_n W\,dS
$$

즉

$$
\int_\Omega|\nabla W|^2 d^n x = \int_{\partial\Omega}W\,\partial_n W\,dS
$$

**핵심 식**: bulk 의 기울기 에너지가 boundary 위의 $\mathcal{R}\hat{L}$ 항과 같다.

만약 우변이 0 이면 좌변도 0. 그러면 $W$ 가 모든 곳에서 상수 (기울기 0).

---

### 7. BC 조건별 유일성 정리

$W$ 가 BC 에서 0 의 정보 (§2-(2)) 를 갖는다는 사실이 이제 결정적으로 사용된다.

§6 의 식

$$
\int_\Omega|\nabla W|^2 d^n x = \int_{\partial\Omega}W\,\partial_n W\,dS
$$

의 우변 적분에 두 인자 ($W$ 와 $\partial_n W$) 가 들어가 있다. **둘 중 하나라도 boundary 에서 0** 이면 적분 0. 각 BC 가 이를 어떻게 보장하는지, 그리고 결과적으로 어떤 유일성이 도출되는지 정리한다.

---

**1) Dirichlet BC**

PDE: $\hat{L}V = f$ in $\Omega$
BC: $V|_{\partial\Omega} = g$ (boundary 에서 값 주어짐)

차이 $W$ 의 BC: $W|_{\partial\Omega} = g - g = 0$.

$\mathcal{R}$ 의 거동:

$$
\int_{\partial\Omega}W\,\partial_n W\,dS = 0 \cdot \int_{\partial\Omega}\partial_n W\,dS = 0
$$

($W$ 인자가 boundary 에서 0 이므로 적분 자동 0.)

따라서 §6 의 식에서 $\int_\Omega|\nabla W|^2 = 0$ → $\nabla W = 0$ → $W = \text{const}$.

Boundary 에서 $W = 0$ 이므로 그 상수 = 0 → **$W \equiv 0$ → $V_1 = V_2$**.

> **Dirichlet 유일성 정리**: PDE $\hat{L}V = f$ 와 Dirichlet BC $V|_{\partial\Omega} = g$ 가 주어진 영역 $\Omega$ 위에서 해 $V$ 가 존재하면 **유일하게 결정**된다.

(완전 유일성. 상수 모호성 없음.)

---

**2) Neumann BC**

PDE: $\hat{L}V = f$ in $\Omega$
BC: $\partial_n V|_{\partial\Omega} = h$ (boundary 에서 normal 미분 주어짐)

차이 $W$ 의 BC: $\partial_n W|_{\partial\Omega} = h - h = 0$.

$\mathcal{R}$ 의 거동:

$$
\int_{\partial\Omega}W\,\partial_n W\,dS = \int_{\partial\Omega}W\cdot 0\,dS = 0
$$

($\partial_n W$ 인자가 boundary 에서 0 이므로 적분 자동 0.)

따라서 $\int_\Omega|\nabla W|^2 = 0$ → $\nabla W = 0$ → $W = \text{const}$.

이번에는 boundary 에서 상수 0 이라는 정보가 없음 — Neumann BC 는 미분 형태이므로 상수에 대한 정보 부족. 따라서 $W = c$ (임의의 상수).

> **Neumann 유일성 정리**: PDE $\hat{L}V = f$ 와 Neumann BC $\partial_n V|_{\partial\Omega} = h$ 가 주어진 영역 $\Omega$ 위에서 해 $V$ 는 **상수 차이까지 유일**.
>
> 즉 두 해 $V_1, V_2$ 가 있으면 $V_1 = V_2 + c$ (어떤 상수 $c$).

(이 모호성은 물리적으로 자연스러움 — 전위의 zero point 를 어디로 잡을지의 선택. 그라운드 설정의 자유도.)

추가 조건 ($\int_\Omega V\,d^n x = 0$ 같은 normalization) 을 부과하면 완전 유일성 회복.

---

**3) Robin BC**

PDE: $\hat{L}V = f$ in $\Omega$
BC: $\alpha V + \beta\,\partial_n V|_{\partial\Omega} = g$ (선형 결합 주어짐), $\alpha, \beta$ 실수, 같은 부호 ($\alpha\beta > 0$ 가정).

차이 $W$ 의 BC: $\alpha W + \beta\,\partial_n W|_{\partial\Omega} = 0$. 정리하면

$$
\partial_n W = -\frac{\alpha}{\beta}W \quad \text{on } \partial\Omega
$$

$\mathcal{R}$ 의 거동:

$$
\int_{\partial\Omega}W\,\partial_n W\,dS = -\frac{\alpha}{\beta}\int_{\partial\Omega}W^2\,dS
$$

$\alpha/\beta > 0$ 이므로 우변 비양수: $\int_{\partial\Omega}W\,\partial_n W\,dS \leq 0$.

§6 식의 좌변은 비음 ($|\nabla W|^2 \geq 0$). 우변은 비양. **양쪽 모두 0**.

- $\int_\Omega|\nabla W|^2 = 0$ → $W = \text{const}$
- $\int_{\partial\Omega}W^2\,dS = 0$ → $W|_{\partial\Omega} = 0$ → 상수 = 0

**$W \equiv 0$ → $V_1 = V_2$**.

> **Robin 유일성 정리**: PDE $\hat{L}V = f$ 와 Robin BC $\alpha V + \beta\,\partial_n V = g$ ($\alpha\beta > 0$) 가 주어진 영역 $\Omega$ 위에서 해 $V$ 는 **유일하게 결정**된다.

($\alpha\beta < 0$ 의 경우 적분의 부호가 반대로 — 유일성이 깨질 수 있는 영역. 비물리적 BC.)

---

**4) Periodic BC**

도메인이 torus 형태 (예: $[0, L]^n$ 의 양쪽 끝이 동일시).

BC: $V(0) = V(L)$, $\partial_n V(0) = \partial_n V(L)$ on 대응되는 boundary 쌍.

차이 $W$ 도 같은 periodic BC 만족.

$\mathcal{R}$ 의 거동: boundary 표면 위의 적분이 양쪽이 정확히 상쇄.

$$
\int_{\partial\Omega}W\,\partial_n W\,dS = 0
$$

(양쪽 끝의 기여가 부호 반대로 정확히 상쇄.)

따라서 $\nabla W = 0$ → $W = \text{const}$.

> **Periodic 유일성 정리**: PDE $\hat{L}V = f$ 와 periodic BC 가 주어진 torus 영역 위에서 해 $V$ 는 **상수 차이까지 유일**.

Neumann 과 비슷하게 상수 모호성 — periodic BC 도 미분 형태로만 정보를 주므로 상수 fixing 안 됨.

---

**5) Mixed BC**

영역의 boundary 가 여러 부분으로 나뉘고, 각 부분에 다른 종류의 BC.

$$
\partial\Omega = \Gamma_D \cup \Gamma_N, \quad V|_{\Gamma_D} = g, \quad \partial_n V|_{\Gamma_N} = h
$$

$\mathcal{R}$ 의 거동: 각 부분에서 따로 0.

- $\Gamma_D$ 위: $W = 0$ → 적분 0
- $\Gamma_N$ 위: $\partial_n W = 0$ → 적분 0

전체 boundary 적분 0. 따라서 $W = \text{const}$.

$\Gamma_D$ 가 비어 있지 않으면 (Dirichlet 영역이 있으면) 상수 = 0 → 완전 유일성.

> **Mixed 유일성 정리**: PDE $\hat{L}V = f$ 와 $\Gamma_D$ 위의 Dirichlet BC + $\Gamma_N$ 위의 Neumann BC 가 주어진 영역 $\Omega$ 위에서, $\Gamma_D$ 가 비어 있지 않으면 해 $V$ 는 **유일하게 결정**된다.

(Dirichlet 영역이 상수 모호성을 fix.)

---

**BC 별 정리 비교표**

| BC | $\mathcal{R}$ 가 0 되는 이유 | 유일성 종류 |
|---|---|---|
| Dirichlet | $W\vert_{\partial\Omega} = 0$ | **완전 유일** ($V_1 = V_2$) |
| Neumann | $\partial_n W\vert_{\partial\Omega} = 0$ | **상수 차이까지** ($V_1 = V_2 + c$) |
| Robin ($\alpha\beta > 0$) | 우변 $\leq 0$, 좌변 $\geq 0$ → 양쪽 0 | **완전 유일** |
| Periodic | 양쪽 boundary 기여 상쇄 | **상수 차이까지** |
| Mixed (with $\Gamma_D \neq \emptyset$) | 각 부분에서 따로 0 | **완전 유일** |

**모두 $\mathcal{R}\hat{L} = 0$ 의 자기수반 BC**. Self-adjoint extension 의 framework 안의 표준 케이스들. 비자기수반 BC (복소 Robin 등) 는 $\mathcal{R}\hat{L} \neq 0$ 이 되어 유일성 깨질 수 있음.

---

### 8. 전체 메커니즘의 정리

§6 의 핵심 식

$$
\underbrace{\int_\Omega|\nabla W|^2 d^n x}_{\geq 0 \text{ (제곱 적분)}} = \underbrace{\int_{\partial\Omega}W\,\partial_n W\,dS}_{\leq 0 \text{ 또는 } = 0 \text{ (BC 종류에 따라)}}
$$

좌변은 항상 비음, 우변은 자기수반 BC 의 모든 케이스에서 비양 또는 0. 양쪽이 같으려면 **둘 다 0**.

좌변 = 0 → $|\nabla W| = 0$ → $W$ 가 상수.

상수의 결정:
- **Dirichlet 또는 Mixed (with $\Gamma_D \neq \emptyset$)**: boundary 에서 $W = 0$ → 상수 = 0 → 완전 유일성.
- **Neumann 또는 Periodic**: boundary 가 미분만 주므로 상수 fix 불가 → 상수 차이까지 유일성.
- **Robin (자기수반 케이스)**: §7-(3) 의 적분 분석으로 상수 = 0 → 완전 유일성.

---

### 9. 그림 요약 — 왜 $\mathcal{R}\hat{L} = 0$ 이 유일성을 보장하는가

전체 흐름을 한 그림으로:

```
유일성 묻기
   ↓
두 해의 차이 W 분석
   ↓
W 의 적분 (분석에 필요)
   ↓
부분 적분 (미분 작용소이므로)
   ↓
boundary term 자동 등장 = R_L[W,W]
   ↓
BC 가 자기수반 → R_L = 0
   ↓
적분 식: bulk 에너지 = 0
   ↓
W = const
   ↓
유일성
```

**$\mathcal{R}\hat{L}$ 의 역할**: $W$ 분석에서 자동으로 등장하는 boundary 항. 이 항이 0 이 되도록 BC 가 잡혀 있으면 (자기수반 BC), bulk 에너지도 0 으로 강제되어 $W$ 가 상수가 되고, 결국 0. 유일성 보장.

**왜 BC 가 self-adjoint 여야 하는가**: $\mathcal{R}\hat{L} = 0$ 의 조건이 사실 self-adjoint BC 의 정의 그 자체. 두 가지가 같은 사실의 다른 표현.

| 표현 1 | 표현 2 |
|---|---|
| BC 가 self-adjoint | $\mathcal{R}\hat{L} = 0$ on $\mathcal{D}(\hat{L})$ |
| 유일성 보장 | 위 증명의 마지막 단계 도달 |

세 가지 모두 등가.

---

### 10. 응용

본 분석의 적용 영역.

**1) 전자기학의 정전기**

도체의 정전 평형 분석.

- 도체 표면 = Dirichlet BC ($V|_{\partial\Omega} = V_0$, 등전위)
- 이 BC 가 self-adjoint → $\mathcal{R}\hat{L} = 0$
- 따라서 도체 내부의 $V$ 가 유일하게 결정
- 정전 평형의 정의 (자유 전자 정지, $\vec{E} = 0$) 와 결합 → 도체 내부 $V = V_0$ 이 유일한 해
- Poisson 방정식 $\nabla^2 V = -\rho/\epsilon_0$ 에서 $\rho = 0$ (내부 전하 없음)

**2) 양자역학의 정상 상태**

시간 독립 Schrödinger 방정식 $\hat{H}\psi = E\psi$ 의 고유 상태.

영역 (예: 양자 우물) + Dirichlet BC ($\psi = 0$ on $\partial\Omega$) → 각 고유값에 대해 고유 함수가 유일 (상수 배까지).

$\hat{H}$ 가 self-adjoint → $\mathcal{R}\hat{H} = 0$ → 유일성. 양자역학의 측정 가능 상태 해석의 토대.

**3) Green 함수의 유일성**

$\hat{L}G(\vec{x}, \vec{x}') = \delta(\vec{x} - \vec{x}')$ + BC. 같은 BC 의 두 후보의 차이가 동질 PDE + 0 BC → 유일성으로 차이 0.

이 유일성이 표준 GF 표기의 정당성. 자세한 내용: b_sl_greens_function.md.

**4) 변분 원리의 평형**

에너지 functional 의 최소화. 변분 $\delta U = 0$ 에서 발생하는 boundary 항이 정확히 $\mathcal{R}\hat{L}$. Self-adjoint BC 가 $\mathcal{R}\hat{L} = 0$ 보장 → 평형이 유일하게 결정.

**5) NEGF 의 GF**

비-Hermitian $\hat{H}_{\text{eff}}$ 의 $G^R(E) = (E - \hat{H}_{\text{eff}} + i\eta)^{-1}$. Self-energy 의 적절한 구조가 $\mathcal{R}\hat{L} = 0$ 의 일반화를 만족 → GF 가 유일.

---

### 11. 핵심 메시지

| 객체 | 역할 |
|---|---|
| $W = V_1 - V_2$ | 두 해의 차이 |
| $\int W(\hat{L}W)d^n x$ | $W$ 의 자연스러운 분석 적분 |
| 부분 적분 | bulk 에너지 + boundary 항으로 분해 |
| Boundary 항 = $\mathcal{R}\hat{L}[W,W]$ | 부분 적분에서 자동 등장 |
| Self-adjoint BC | $\mathcal{R}\hat{L} = 0$ 보장 |
| $W = 0$ | 위 적분이 0 → bulk 에너지 0 → $W$ 상수 → 유일성 |

**$\mathcal{R}\hat{L}$ 이 유일성과 닿아 있는 이유**: 두 해의 차이 $W$ 를 적분으로 분석하려면 부분 적분이 필요하고, 부분 적분은 boundary 항을 만들고, 그 boundary 항이 $\mathcal{R}\hat{L}$. 자기수반 BC 가 그것을 0 으로 만들면 bulk 까지 0 으로 강제되어 $W = 0$ — 유일성.

$\mathcal{R}\hat{L} = 0$ 이 유일성의 충분 + 필요 조건이며, 이게 self-adjoint BC 의 진정한 의미.
