+++
title = "(b) Uniqueness"
weight = 4
+++

---

### 1. 시작: 두 사람이 같은 문제를 풀었다

PDE 와 BC 가 주어진 문제를 두 사람이 풀었다고 하자.

- A 의 답: $V_1(\vec{x})$
- B 의 답: $V_2(\vec{x})$

자연스러운 질문이 따라온다. **두 답이 같은가, 다른가? 또는 다를 수 있다면 얼마나 다를 수 있는가?**

이 질문이 "유일성 정리 (uniqueness theorem)" 의 의미이다. 문제 풀이의 신뢰성을 위해 답이 어떤 정도로 결정되는지 알아야 한다. 답이 완전히 하나이면 좋고, 그렇지 않더라도 어느 정도의 자유도가 있는지 명확히 알아야 한다.

본 문서에서 이 질문을 정확히 다룬다. 결론을 먼저 짚어두면, 자기수반 BC ($\mathcal{R}\hat{L} = 0$) 의 조건 하에서 두 해의 차이가 작용소의 **nullspace** 안에 있음이 보장된다. 따라서 nullspace 의 구조가 정확히 어떤 종류의 유일성이 성립하는지 결정한다. 본 문서가 이 정확한 사실을 단계별로 풀어내며, 자칫 잘못 받아들이기 쉬운 점들을 명확히 짚는다.

---

### 2. 두 답의 차이를 분석한다

A 와 B 의 답이 같은지 다른지를 묻는 가장 직접적 방법은 **차이를 보는 것**이다.

$$
W(\vec{x}) := V_1(\vec{x}) - V_2(\vec{x})
$$

이 차이 $W$ 가 어떤 함수일 수 있는지가 본 분석의 대상이다. 가능한 $W$ 들의 집합이 작을수록 (예: $W = 0$ 만 가능) 유일성이 좋고, 클수록 (예: $W$ = 임의의 상수) 자유도가 큼.

$W$ 의 성질부터 도출한다. $V_1, V_2$ 가 같은 PDE 와 같은 BC 의 해라는 사실에서 두 가지 성질이 자동으로 따라온다.

**1) $W$ 가 만족하는 PDE**

$V_1, V_2$ 가 같은 PDE 의 해이므로

$$
\hat{L}V_1 = f, \quad \hat{L}V_2 = f
$$

두 식을 빼면

$$
\hat{L}W = \hat{L}V_1 - \hat{L}V_2 = f - f = 0
$$

따라서 $W$ 는 **동질 (homogeneous) PDE** 의 해이다. 우변이 0 이라는 의미. 예를 들어 원래 문제가 Poisson 방정식 $-\nabla^2 V = \rho/\epsilon_0$ 이었다면, $W$ 는 Laplace 방정식 $\nabla^2 W = 0$ 의 해.

**2) $W$ 가 만족하는 BC**

$V_1, V_2$ 가 같은 BC 의 해이므로 boundary 에서 차이 정보가 0 이다. 어떤 BC 인지에 따라 구체적 형태가 다르다.

- Dirichlet BC ($V|_{\partial\Omega} = g$ 가 주어짐): $W|_{\partial\Omega} = g - g = 0$
- Neumann BC ($\partial_n V|_{\partial\Omega} = h$ 가 주어짐): $\partial_n W|_{\partial\Omega} = h - h = 0$
- Robin BC ($\alpha V + \beta\partial_n V|_{\partial\Omega} = g$): $\alpha W + \beta\partial_n W|_{\partial\Omega} = 0$
- Periodic BC: boundary 의 양쪽이 일치 → $W$ 도 양쪽 일치

핵심은 어떤 BC 든 $W$ 가 boundary 에서 **동질 (homogeneous) BC** — 우변이 0 인 형태 — 를 만족한다는 것.

**Nullspace 라는 개념의 도입**

지금까지 도출한 두 성질을 합치면, $W$ 는 **동질 PDE + 동질 BC** 를 만족한다. 이런 함수들의 집합을 작용소 $\hat{L}$ (해당 BC 와 함께) 의 **nullspace** 라 한다.

$$
\text{null}(\hat{L}) := \{u \in \mathcal{D}(\hat{L}) : \hat{L}u = 0\}
$$

여기서 $\mathcal{D}(\hat{L})$ 는 작용소의 정의역으로, BC 를 포함한 함수 공간이다. 즉 nullspace 는 source 가 없을 때 BC 를 만족하는 모든 가능한 해의 집합.

따라서 우리가 도출한 사실은 다음과 같이 정리된다.

> **두 해의 차이 $W$ 는 작용소의 nullspace 안에 있다**: $W \in \text{null}(\hat{L})$.

이 사실까지는 $\mathcal{R}\hat{L} = 0$ 을 사용하지 않고 도출했다. PDE 와 BC 의 선형성만 사용. 이 사실 자체가 유일성의 의미를 새로 정의해준다.

**유일성의 정확한 의미**

원래의 질문 "두 답이 얼마나 다를 수 있는가" 가 이제 다음으로 변환된다. **$W$ 가 nullspace 안에 있을 수 있는데, nullspace 가 얼마나 큰가?**

이 nullspace 의 크기 (정확히는 차원) 가 유일성의 종류를 결정한다.

- nullspace 가 trivial (0 만 들어있음, 차원 0) → $W = 0$ 만 가능 → 두 답 완전히 같음 → **완전 유일성**
- nullspace 가 nontrivial (예: 상수 함수들, 차원 1) → $W$ 가 nullspace 의 임의 원소 → 두 답이 nullspace 만큼 다를 수 있음 → **nullspace 차이까지 유일성**

따라서 본 문서의 진짜 질문이 **nullspace 의 구조 분석** 으로 환원된다. nullspace 가 trivial 인 경우와 nontrivial 인 경우를 어떻게 판단하는지가 유일성 분석의 핵심.

§3 부터 이 nullspace 의 구조를 어떻게 분석하는지 풀어간다. 그 과정에서 $\mathcal{R}\hat{L} = 0$ 의 조건이 핵심 도구로 등장한다.

---

### 3. Nullspace 의 분석을 위한 적분 분석

Nullspace 의 구조를 직접 분석하려면 $W$ 의 거동을 따져봐야 한다. $W$ 가 함수이므로 어느 한 점에서 0 인지를 확인하는 것은 어렵다. 무한 차원 함수의 모든 점을 점검할 수는 없으니까. 대신 **적분으로 $W$ 의 정보를 압축** 하는 방식이 자연스럽다.

$W$ 의 "전체 크기" 를 측정할 수 있는 적분들을 보자.

$$
\int_\Omega|W|^2\,d^n x, \quad \int_\Omega|\nabla W|^2\,d^n x
$$

이런 비음의 적분이 0 이면 적분 안의 함수 $|W|$ 또는 $|\nabla W|$ 가 거의 모든 점에서 0 이다. 따라서 적분이 0 이라는 사실로부터 $W$ 의 구조에 대한 정보를 도출할 수 있다.

문제는 이런 적분을 어떻게 0 임을 보일 것인가이다. $W$ 가 만족하는 식 ($\hat{L}W = 0$) 을 활용하는 적분이 자연스럽다. 가장 단순한 형태부터 본다.

$$
\int_\Omega W\,(\hat{L}W)\,d^n x
$$

$\hat{L}W = 0$ 이라는 사실에서 이 적분이 0 임이 즉시 알 수 있다.

$$
\int_\Omega W\,(\hat{L}W)\,d^n x = \int_\Omega W \cdot 0\,d^n x = 0
$$

따라서 이 적분 자체는 0. 그러나 이 적분을 **다른 방식으로 계산** 했을 때 얻는 식이 의미 있다. 부분 적분을 통해 이 적분을 다른 형태로 변환하면 $W$ 의 구조에 대한 정보가 드러난다.

이 변환이 다음 절의 핵심 작업이다.

---

### 4. Green 첫 항등식의 도출

$\hat{L} = -\nabla^2$ (Laplace 작용소) 의 경우를 구체적으로 진행한다 (가장 흔한 케이스이며, 일반 자기수반 미분 작용소도 비슷한 분석이 적용됨).

$$
\int_\Omega W(-\nabla^2 W)\,d^n x
$$

이 적분을 부분 적분으로 변환한다. 다차원 부분 적분의 기본 항등식인 발산 정리 (Stokes 정리) 를 사용한다.

먼저 다음 곱셈 미분 규칙에서 시작한다.

$$
\nabla\cdot(W\nabla W) = \nabla W\cdot\nabla W + W\nabla^2 W = |\nabla W|^2 + W\nabla^2 W
$$

양변을 영역 $\Omega$ 위에서 적분한다.

$$
\int_\Omega\nabla\cdot(W\nabla W)\,d^n x = \int_\Omega|\nabla W|^2\,d^n x + \int_\Omega W\nabla^2 W\,d^n x
$$

좌변에 발산 정리를 적용하면 boundary 적분으로 변환된다.

$$
\int_\Omega\nabla\cdot(W\nabla W)\,d^n x = \int_{\partial\Omega}W(\nabla W\cdot\vec{n})\,dS = \int_{\partial\Omega}W\,\partial_n W\,dS
$$

여기서 $\vec{n}$ 은 boundary 의 outward normal 벡터, $\partial_n W := \nabla W\cdot\vec{n}$ 은 normal derivative.

두 식을 결합하면

$$
\int_{\partial\Omega}W\,\partial_n W\,dS = \int_\Omega|\nabla W|^2\,d^n x + \int_\Omega W\nabla^2 W\,d^n x
$$

좌변과 우변을 정리하면 최종 형태

$$
\boxed{\int_\Omega W(-\nabla^2 W)\,d^n x = \int_\Omega|\nabla W|^2\,d^n x - \int_{\partial\Omega}W\,\partial_n W\,dS}
$$

이 식이 **Green 첫 항등식 (Green's first identity)**. 부분 적분의 다차원 일반화로, 다음 세 가지가 등호로 연결된다.

- 좌변: $W$ 와 $-\nabla^2 W$ 의 적분 (PDE 와 직접 관련)
- 우변 첫 항: $W$ 의 기울기 에너지 (bulk 정보, 비음)
- 우변 둘째 항: boundary 위의 적분 (boundary 정보)

---

### 5. Boundary 항이 정확히 $\mathcal{R}\hat{L}$ 이다

§4 의 boxed 식의 boundary 항

$$
\int_{\partial\Omega}W\,\partial_n W\,dS
$$

이 객체가 b_adjoint.md, b_boundary.md 에서 다룬 $\mathcal{R}\hat{L}$ 와 어떤 관계인지를 정확히 매핑한다.

**1차원 케이스로 단순화**

$\Omega = [a, b]$ 의 경우 §4 의 도출이 다음과 같이 단순화된다.

$$
\int_a^b W(-W'')\,dx = \int_a^b(W')^2\,dx - [WW']_a^b
$$

(1차원에서는 발산 정리가 단순 부분 적분이 됨.)

Boundary 항이 $[WW']_a^b = W(b)W'(b) - W(a)W'(a)$ — 양 끝점에서 평가한 값.

**b_adjoint.md §3 의 1차 미분 R 과 비교**

b_adjoint.md §3 에서 1차 미분 작용소 $\hat{D} = d/dx$ 의 레지듀가 다음과 같이 정의되었다.

$$
\mathcal{R}\hat{D}[\phi, \psi] = [\phi^*\psi]_a^b
$$

여기에 $\phi = W$, $\psi = W'$ 을 대입한다.

$$
\mathcal{R}\hat{D}[W, W'] = [W^*W']_a^b = [WW']_a^b
$$

(실수 $W$ 의 경우 $W^* = W$.)

**좌변과 우변의 직접 일치**:

$$
\boxed{\text{Green 첫 항등식의 boundary 항} = \mathcal{R}\hat{D}[W, W']}
$$

부분 적분에서 발생한 boundary term 이 사용자의 framework 의 $\mathcal{R}$ 객체와 정확히 같다.

**다차원 일반화**

다차원에서는 boundary 적분이 표면 위의 적분으로 일반화된다. 객체의 본질은 같으며 (boundary 평가), 단지 적분의 형태가 단순 평가에서 표면 적분으로 확장. b_boundary.md 의 다차원 $\mathcal{R}$ 와 일치한다.

**왜 $\mathcal{R}$ 이 등장했는가**

$W$ 의 분석을 위해 적분 $\int W(\hat{L}W)d^n x$ 를 다루었고, 그 적분을 부분 적분으로 계산하면서 boundary 항이 등장했다. 그 boundary 항이 우리가 다른 곳에서 정의한 $\mathcal{R}\hat{L}$ 의 정확한 한 형태였다. 즉 새로운 도구를 가져온 것이 아니라 **같은 객체가 다른 맥락에서 자연 등장**.

---

### 6. 적분 식의 결합 — bulk 와 boundary 의 관계

§4 의 Green 첫 항등식을 다시 쓴다.

$$
\int_\Omega W(-\nabla^2 W)\,d^n x = \int_\Omega|\nabla W|^2\,d^n x - \int_{\partial\Omega}W\,\partial_n W\,dS
$$

$W$ 가 동질 PDE $\nabla^2 W = 0$ 의 해라는 사실을 적용한다. 좌변:

$$
\int_\Omega W(-\nabla^2 W)\,d^n x = \int_\Omega W \cdot 0\,d^n x = 0
$$

따라서

$$
0 = \int_\Omega|\nabla W|^2\,d^n x - \int_{\partial\Omega}W\,\partial_n W\,dS
$$

정리하면

$$
\boxed{\int_\Omega|\nabla W|^2\,d^n x = \int_{\partial\Omega}W\,\partial_n W\,dS}
$$

**이 식의 정확한 의미**:

좌변과 우변이 모두 $W$ 의 구조에 의존하는 양이다. 좌변은 bulk 에서의 기울기 에너지 (항상 비음), 우변은 boundary 위의 $\mathcal{R}\hat{L}$ 항. 두 양이 항상 같아야 한다는 것이 동질 PDE 와 부분 적분의 결합 결과.

만약 BC 가 우변을 0 또는 비양으로 강제할 수 있다면, 좌변이 비음과 비양 사이에 끼어 0 으로 강제된다. 그 결과 $|\nabla W|^2 = 0$ → $\nabla W = 0$ → $W = \text{const}$. BC 의 역할이 정확히 이것 — 우변을 통제하여 bulk 의 결론을 강제하는 것.

따라서 다음 절에서는 각 BC 가 우변을 어떻게 통제하는지, 그리고 그 결과 어떤 nullspace 구조가 도출되는지를 분석한다.

---

### 7. BC 가 우변을 0 으로 만드는 이유 — 자기수반 BC 와 $\mathcal{R}\hat{L} = 0$

§6 의 식

$$
\int_\Omega|\nabla W|^2\,d^n x = \int_{\partial\Omega}W\,\partial_n W\,dS
$$

의 우변을 보면, boundary 위의 적분에 두 인자 ($W$ 와 $\partial_n W$) 가 들어있다. 둘 중 하나라도 boundary 에서 0 이면 적분이 0 이 된다.

**자기수반 BC (self-adjoint BC) 의 정의**

자기수반 BC 는 정확히 **$\mathcal{R}\hat{L} = 0$ 이 정의역 안의 모든 함수에 대해 성립하도록 만드는 BC** 로 정의된다. 즉 두 함수 $\phi, \psi$ 가 둘 다 BC 를 만족할 때 $\mathcal{R}\hat{L}[\phi, \psi] = 0$ 이라는 것.

지금 우리의 상황은 $\phi = W$, $\psi = W'$ (1차원) 또는 그 다차원 일반화. $W$ 가 동질 BC 를 만족하는 함수이다. 자기수반 BC 의 정의에 의해 이 경우 boundary 항이 0 이 되어야 한다.

각 표준 BC 가 이를 어떻게 보장하는지 풀어 본다.

**(a) Dirichlet BC**: $W|_{\partial\Omega} = 0$

적분 안의 첫 인자 $W$ 가 boundary 에서 0 이다. 따라서

$$
\int_{\partial\Omega}W\,\partial_n W\,dS = \int_{\partial\Omega}0\cdot\partial_n W\,dS = 0
$$

자동으로 우변 0.

**(b) Neumann BC**: $\partial_n W|_{\partial\Omega} = 0$

적분 안의 둘째 인자 $\partial_n W$ 가 boundary 에서 0 이다. 따라서

$$
\int_{\partial\Omega}W\,\partial_n W\,dS = \int_{\partial\Omega}W\cdot 0\,dS = 0
$$

자동으로 우변 0.

**(c) Robin BC**: $\alpha W + \beta\partial_n W|_{\partial\Omega} = 0$, $\alpha, \beta$ 실수, $\alpha\beta > 0$

이 경우 $\partial_n W = -(\alpha/\beta)W$ on boundary. 대입하면

$$
\int_{\partial\Omega}W\,\partial_n W\,dS = -\frac{\alpha}{\beta}\int_{\partial\Omega}W^2\,dS \leq 0
$$

($\alpha/\beta > 0$ 가정 + $W^2 \geq 0$.) 우변이 비양수.

**(d) Periodic BC**

도메인이 torus 형태. Boundary 의 양쪽 면에서 $W$ 와 $\partial_n W$ 가 일치. 양쪽에서 outward normal 의 방향이 반대이므로 boundary 항이 부호 반대의 두 기여로 정확히 상쇄.

$$
\int_{\partial\Omega}W\,\partial_n W\,dS = 0
$$

**(e) Mixed BC**: $\partial\Omega = \Gamma_D \cup \Gamma_N$

각 부분에서 따로 0:
- $\Gamma_D$ 위 (Dirichlet): $W = 0$ → 적분 0
- $\Gamma_N$ 위 (Neumann): $\partial_n W = 0$ → 적분 0

전체 boundary 적분 0.

**$\mathcal{R}\hat{L} = 0$ 의 정확한 의미**

위의 다섯 케이스 (a-e) 모두 우변이 0 (또는 비양) 이 된다. 이 사실이 자기수반 BC = $\mathcal{R}\hat{L} = 0$ 의 framework 이 활성화됨을 의미한다.

좀 더 정확히 말하면, **$\mathcal{R}\hat{L} = 0$ 이 §6 의 적분 식의 우변을 0 (또는 비양) 으로 강제** 한다. 좌변은 항상 비음. 따라서

$$
\int_\Omega|\nabla W|^2\,d^n x = 0 \text{ (또는 } \leq 0 \text{인 우변과 같음)}
$$

좌변이 비음 + 우변이 비양 → 양쪽 모두 0. 따라서 $|\nabla W|^2 = 0$ a.e. → $\nabla W = 0$ → **$W = \text{const}$**.

여기까지가 $\mathcal{R}\hat{L} = 0$ 이 보장하는 것이다. **$W$ 가 상수가 된다**는 사실까지.

---

### 8. $\mathcal{R}\hat{L} = 0$ 이 정확히 무엇을 보장하는가

§7 의 결론을 정확히 짚는다. $\mathcal{R}\hat{L} = 0$ (자기수반 BC) 의 framework 이 보장하는 것은 두 해의 차이 $W$ 가 다음 두 성질을 만족한다는 사실이다.

- **PDE**: $\hat{L}W = 0$ (동질 PDE, §2-(1) 에서 도출)
- **BC**: $W$ 가 동질 BC 를 만족 (§2-(2) 에서 도출)

그리고 §7 의 적분 분석에 의해 추가로

- **$W = \text{const}$** (공간 위에서 상수)

이 결론이 자기수반 BC 의 framework 의 결과. 그러나 **그 상수가 정확히 0 인지 아닌지는 별개의 문제**.

이 사실이 본 framework 의 정확한 한계이다. $\mathcal{R}\hat{L} = 0$ 으로부터 자동으로 "두 답이 완전히 같다" 라는 결론을 도출할 수 없다. 단지 "두 답이 상수만큼 다르다" 까지만 보장된다.

**Nullspace 의 정확한 의미**

§2 에서 정의한 nullspace 의 관점에서 보면, $W$ 가 상수가 된다는 사실이 정확히 다음을 의미한다.

> **자기수반 BC 의 framework 하에서 $W$ 는 작용소의 nullspace 안에 있다.**

여기서 nullspace 가 어떤 함수들의 집합인지는 작용소 $\hat{L}$ 과 BC 의 결합으로 결정된다. 우리가 본 적분 분석은 nullspace 의 후보가 상수 함수임을 시사 ($W = \text{const}$).

이제 정말 핵심 질문은 다음이다. **상수 함수가 실제로 nullspace 의 원소인가?** 즉 어떤 상수 함수가 동질 PDE 와 동질 BC 를 모두 만족하는가? 이 질문에 BC 의 종류가 결정적이다.

---

### 9. BC 별 nullspace 의 구조와 유일성의 종류

§7 의 각 BC 케이스에 대해 nullspace 의 구체적 구조를 분석한다. 이로부터 각 BC 에서 어떤 종류의 유일성이 보장되는지가 정확히 도출된다.

**(a) Dirichlet BC**: $W|_{\partial\Omega} = 0$

상수 함수 $W = c$ 가 동질 BC 를 만족하려면 boundary 에서 $c = 0$. 즉 **상수가 0** 이어야 함.

Nullspace 의 분석:
- $W = \text{const}$ (§7 의 결론) + $W|_{\partial\Omega} = 0$ (BC) → $W \equiv 0$
- nullspace 가 trivial (오직 0 만)

**결론**: $W = 0$ → $V_1 = V_2$ → **완전 유일성**.

> **Dirichlet 유일성 정리**: PDE $\hat{L}V = f$ 와 Dirichlet BC $V|_{\partial\Omega} = g$ 가 주어진 영역 $\Omega$ 위에서, 해 $V$ 가 존재하면 유일하게 결정된다.

**(b) Neumann BC**: $\partial_n V|_{\partial\Omega} = h$ → $\partial_n W|_{\partial\Omega} = 0$

상수 함수 $W = c$ 가 동질 BC 를 만족하는가? $\partial_n c = 0$ 이 자동 만족. 따라서 **모든 상수 함수가 nullspace 의 원소**.

Nullspace 의 분석:
- $W = \text{const} = c$ (§7 의 결론) + $\partial_n c = 0$ (자동 만족, BC)
- 따라서 임의 상수 $c$ 가 가능
- nullspace 가 1차원 (상수 함수들의 집합)

**결론**: $W = c$ (임의 상수) → $V_1 = V_2 + c$ → **상수 차이까지 유일성**.

> **Neumann 유일성 정리**: PDE $\hat{L}V = f$ 와 Neumann BC $\partial_n V|_{\partial\Omega} = h$ 가 주어진 영역 $\Omega$ 위에서, 해 $V$ 는 상수 차이까지 유일.
>
> 즉 두 해 $V_1, V_2$ 가 있으면 $V_1 = V_2 + c$ (어떤 상수 $c$).

이 모호성의 물리적 의미는 b_gauge_freedom.md 에서 자세히 풀어진다 — 전위의 zero point 선택 = 그라운드 설정의 자유도, 게이지 자유도.

**(c) Robin BC**: $\alpha V + \beta\partial_n V|_{\partial\Omega} = g$, $\alpha\beta > 0$ → $\alpha W + \beta\partial_n W|_{\partial\Omega} = 0$

상수 함수 $W = c$ 가 동질 BC 를 만족하는가? $\alpha c + \beta\cdot 0 = \alpha c = 0 \implies c = 0$ ($\alpha \neq 0$ 이므로).

또한 §7-(c) 의 분석을 다시 보면, Robin BC 에서 우변이 $-(\alpha/\beta)\int W^2\,dS$ 의 형태로 비양수가 되며, 양쪽 다 0 으로 강제되므로 $\int_{\partial\Omega}W^2\,dS = 0$. 즉 **$W|_{\partial\Omega} = 0$**.

Nullspace 의 분석:
- $W = \text{const}$ + $W|_{\partial\Omega} = 0$ → $W \equiv 0$
- nullspace 가 trivial

**결론**: $W = 0$ → $V_1 = V_2$ → **완전 유일성**.

> **Robin 유일성 정리** ($\alpha\beta > 0$): PDE $\hat{L}V = f$ 와 Robin BC $\alpha V + \beta\partial_n V = g$ 가 주어진 영역 $\Omega$ 위에서, 해 $V$ 가 존재하면 유일하게 결정.

($\alpha\beta < 0$ 의 경우 적분의 부호가 반대로 되어 본 분석이 직접 적용 안 됨. 비물리적 BC 영역.)

**(d) Periodic BC**

상수 함수 $W = c$ 가 periodic BC 를 만족? 자동 — 상수는 어디서나 같은 값.

Nullspace 의 분석:
- $W = \text{const} = c$ + periodic BC 자동 만족
- 임의 상수 $c$ 가 가능
- nullspace 가 1차원

**결론**: $W = c$ (임의 상수) → **상수 차이까지 유일성**.

> **Periodic 유일성 정리**: PDE $\hat{L}V = f$ 와 periodic BC 가 주어진 torus 영역 위에서, 해 $V$ 는 상수 차이까지 유일.

**(e) Mixed BC**: $\Gamma_D \cup \Gamma_N$, $\Gamma_D$ 가 비어있지 않음

상수 함수 $W = c$ 가 $\Gamma_D$ 위에서 0 이 되려면 $c = 0$.

Nullspace 의 분석:
- $W = \text{const} = c$ + $W|_{\Gamma_D} = 0$ → $c = 0$
- nullspace 가 trivial

**결론**: $W \equiv 0$ → **완전 유일성**.

> **Mixed 유일성 정리** ($\Gamma_D \neq \emptyset$): PDE $\hat{L}V = f$ 와 Dirichlet ($\Gamma_D$) + Neumann ($\Gamma_N$) 의 mixed BC 가 주어진 영역 $\Omega$ 위에서, 해 $V$ 가 존재하면 유일하게 결정.

---

### 10. BC 별 nullspace 와 유일성 정리 요약표

§9 의 분석을 요약하면 다음과 같다.

| BC | 동질 BC | 상수 함수가 nullspace 에 있는가? | nullspace | 유일성의 종류 |
|---|---|---|---|---|
| Dirichlet | $W\vert_{\partial\Omega} = 0$ | 0 만 가능 | trivial | **완전 유일성** |
| Neumann | $\partial_n W\vert_{\partial\Omega} = 0$ | 모든 상수 가능 | 1차원 | **상수 차이까지 유일성** |
| Robin ($\alpha\beta > 0$) | $\alpha W + \beta\partial_n W\vert_{\partial\Omega} = 0$ | 0 만 가능 | trivial | **완전 유일성** |
| Periodic | $W$ 양쪽 일치 | 모든 상수 가능 | 1차원 | **상수 차이까지 유일성** |
| Mixed ($\Gamma_D \neq \emptyset$) | $W\vert_{\Gamma_D} = 0$, $\partial_n W\vert_{\Gamma_N} = 0$ | 0 만 가능 | trivial | **완전 유일성** |

**핵심 관찰**:

자기수반 BC ($\mathcal{R}\hat{L} = 0$ 성립) 모두에서 framework 이 작동하여 $W = \text{const}$ 까지가 보장된다. 그러나 그 상수가 0 인지 nontrivial 인지는 BC 의 형태가 결정한다.

- BC 가 boundary 에서 V 의 **절대값** 정보를 제공 (Dirichlet, Robin, Mixed of Γ_D): 상수가 0 으로 강제 → 완전 유일성
- BC 가 boundary 에서 V 의 **미분 정보만** 제공 (Neumann, Periodic): 상수가 자유 → 상수 차이까지 유일성

따라서 정확히 **$\mathcal{R}\hat{L} = 0$ 은 framework 의 활성화 조건이며, nullspace 의 구체적 구조 (trivial 인가 nontrivial 인가) 가 유일성의 종류를 결정**.

---

### 11. $\mathcal{R}\hat{L} = 0$ 의 정확한 한계 — 자기 인식

이제까지의 분석을 정확히 정리하면, $\mathcal{R}\hat{L} = 0$ 의 framework 의 한계가 명확해진다.

**$\mathcal{R}\hat{L} = 0$ 이 보장하는 것**:

1. Self-adjoint 작용소의 framework 활성화 (b_adjoint.md 의 의미에서)
2. 두 해의 차이 $W$ 가 nullspace 안에 있음 (§8 의 결론)
3. 적분 분석이 가능 (§7 의 부호 분석)

**$\mathcal{R}\hat{L} = 0$ 이 보장하지 않는 것**:

1. 해의 존재성 — 별개의 조건 (compatibility) 필요할 수 있음
2. 완전 유일성 — nullspace 가 trivial 인지 별개
3. 게이지 자유도의 유무 — nullspace 의 구조에 따라

따라서 다음의 사실이 정확하다.

> **$\mathcal{R}\hat{L} = 0$ 은 nullspace 차이까지 유일성을 보장한다. 완전 유일성을 위해서는 추가로 nullspace 가 trivial 이라는 사실이 필요하다.**

이 정확한 표현이 본 framework 의 진짜 결론이다. "$\mathcal{R}\hat{L} = 0$ 이 유일성을 보장한다" 같은 단순화된 표현은 nullspace 가 trivial 인 표준 케이스 (Dirichlet, Robin, Mixed) 에 한정된 결론일 뿐, 일반적이지 않다.

**Nullspace 가 trivial 인지는 무엇이 결정하는가**

자연스러운 후속 질문이다. nullspace 의 구조 자체는 무엇이 결정하는가?

세 가지 요소의 결합이 결정한다:

1. **작용소 $\hat{L}$ 의 형태** — 어떤 미분 작용소인지, 어떤 계수
2. **BC 의 종류** — Dirichlet, Neumann, mixed 등
3. **영역 $\Omega$ 의 위상** — 단순 연결인지, 경계가 있는지

같은 작용소 $-\nabla^2$ 도 BC 가 달라지면 nullspace 가 완전히 달라진다 — §9 의 분석에서 명확히 보았다. 더 일반적으로 Schrödinger Hamiltonian $\hat{H} = -\nabla^2 + V(x)$ 같은 작용소에서는 nullspace 의 구조가 퍼텐셜 $V(x)$ 의 형태에도 결정적으로 의존한다.

따라서 시스템마다 nullspace 분석이 별도로 필요한 작업이며, 이것이 $\mathcal{R}\hat{L} = 0$ 의 framework 이 활성화된 후의 핵심 작업이다.

---

### 12. 그림 요약 — 전체 분석의 흐름

```
유일성 묻기 (두 해의 차이는?)
   ↓
W = V_1 - V_2 가 만족:
   - 동질 PDE (LW = 0)
   - 동질 BC
   ↓
이것이 의미: W ∈ nullspace(L)
   ↓
W 의 적분 분석 (∫W·LW)
   ↓
부분 적분 → Green 첫 항등식
   ↓
boundary 항 = R[W, W'] 자동 등장
   ↓
자기수반 BC (R = 0) 하에:
   ∫|∇W|² = ∫W∂_n W ≤ 0 또는 = 0
   ↓
양쪽 0 → W = const
   ↓
[여기까지가 R = 0 의 보장]
   ↓
상수의 결정 (BC 의 종류에 따라):
   ├── BC 가 V 의 절대값 정보 제공:
   │   → 상수 = 0 → 완전 유일성
   │   (Dirichlet, Robin αβ > 0, Mixed Γ_D ≠ ∅)
   │
   └── BC 가 V 의 미분 정보만 제공:
       → 상수 자유 → 상수 차이까지 유일성
       (Neumann, Periodic)
   ↓
[이게 nullspace 의 구조에 의해 결정]
```

이 그림이 본 문서의 전체 분석의 정확한 그림이다.

---

### 13. 응용

본 framework 의 적용 영역.

**1) 전자기학의 정전기**

도체의 정전 평형 분석.

도체 표면이 등전위 ($V|_{\partial\Omega} = V_0$) 라는 사실이 정확히 Dirichlet BC. 본 framework 의 §9-(a) 케이스. 따라서 도체 내부의 $V$ 가 유일하게 결정된다. 정전 평형의 정의 (자유 전자 정지, $\vec{E} = 0$) 와 결합하면 도체 내부 $V = V_0$ 이 유일한 해. Poisson 방정식 $\nabla^2 V = -\rho/\epsilon_0$ 에서 $\rho = 0$ (내부 전하 없음) 까지 도출된다.

만약 BC 가 Neumann 형 (표면 전하 분포 지정) 이었다면 §9-(b) 케이스가 되어 전위가 상수 차이까지만 유일. 이때 그라운드 노드 설정 (게이지 fix) 이 필요하다 — b_gauge_freedom.md 의 처리.

**2) 양자역학의 정상 상태**

시간 독립 Schrödinger 방정식 $\hat{H}\psi = E\psi$ 의 고유 상태 문제.

영역 $\Omega$ (예: 양자 우물) + Dirichlet BC ($\psi = 0$ on $\partial\Omega$) 가 표준. $\hat{H} - E\hat{I}$ 가 자기수반 + Dirichlet BC → $\mathcal{R} = 0$ + nullspace trivial → 각 고유값 $E_n$ 에 대해 고유 함수 $\psi_n$ 이 (상수 배까지) 유일.

여기서 "상수 배까지" 는 phase 자유도 ($\psi \to e^{i\theta}\psi$) — b_gauge_freedom.md §6 에서 다룬 U(1) 게이지.

**3) Green 함수의 유일성**

$\hat{L}G(\vec{x}, \vec{x}') = \delta(\vec{x} - \vec{x}')$ + BC 의 GF. 같은 BC 의 두 후보의 차이가 동질 PDE + 0 BC 를 만족 → 본 framework 으로 차이 0. 따라서 GF 의 표기 정당성. 자세한 내용: b_sl_greens_function.md.

**4) 변분 원리의 평형**

에너지 functional 의 최소화. 변분 $\delta U = 0$ 에서 boundary 항이 정확히 $\mathcal{R}\hat{L}$ 의 형태. 자기수반 BC 가 $\mathcal{R}\hat{L} = 0$ 보장 → 평형이 결정 (BC 의 종류에 따라 완전 또는 nullspace 차이까지).

**5) NEGF 의 $G^R$ 의 유일성**

비-Hermitian $\hat{H}_{\text{eff}}$ 의 $G^R(E) = (E - \hat{H}_{\text{eff}} + i\eta)^{-1}$. Self-energy 의 적절한 구조가 self-adjoint extension 의 일반화. $E$ 가 $\hat{H}_{\text{eff}}$ 의 spectrum 위에 있지 않으면 (resolvent 가 정의된 영역) GF 유일. Resonance 위치에서는 nullspace 가 nontrivial 이 되어 GF 가 발산 — sharp resonance 의 정확한 의미.

---

### 14. 핵심 메시지

본 문서의 정확한 결론을 정리한다.

| 객체 | 역할 |
|---|---|
| $W = V_1 - V_2$ | 두 해의 차이 |
| $\hat{L}W = 0$ + 동질 BC | $W \in \text{null}(\hat{L})$ |
| Green 첫 항등식 | $\int\|\nabla W\|^2 = \int_{\partial\Omega}W\partial_n W$ |
| Boundary 항 = $\mathcal{R}\hat{L}[W, W']$ | 부분 적분에서 자동 등장 |
| 자기수반 BC ($\mathcal{R} = 0$) | 우변 $\leq 0$ → 양쪽 0 → $W = \text{const}$ |
| Nullspace 구조 | 상수 0 인지 nontrivial 인지 결정 |

**핵심 사실의 정확한 표현**:

> $\mathcal{R}\hat{L} = 0$ (자기수반 BC) 의 framework 은 **두 해의 차이가 nullspace 의 원소** 임을 보장한다. 유일성의 정확한 종류 (완전 유일성 또는 nullspace 차이까지 유일성) 는 nullspace 가 trivial 인지 nontrivial 인지에 의해 결정되며, 이는 BC 와 작용소와 영역의 결합에 의해 결정된다.

§9 의 BC 별 분석에서:
- nullspace trivial: Dirichlet, Robin ($\alpha\beta > 0$), Mixed ($\Gamma_D \neq \emptyset$) → 완전 유일성
- nullspace nontrivial (1차원, 상수 함수): Neumann, Periodic → 상수 차이까지 유일성

이 framework 이 다양한 응용 (전자기학, 양자역학, GF, 변분 원리, NEGF) 의 공통 토대이며, 각 응용에서 BC 와 nullspace 의 구체적 분석이 추가로 필요하다.

본 문서의 framework 의 자연스러운 후속이 b_gauge_freedom.md — nullspace 가 nontrivial 인 경우의 모호성을 게이지 자유도로 해석하고, 수치적으로 어떻게 처리하는지 풀어낸다.
