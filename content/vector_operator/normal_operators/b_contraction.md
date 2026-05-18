+++
title = "(b) Contraction"
weight = 5
+++

---

### 1. Contraction 연산자

**1) 정의**

정규 연산자 $\hat{T}$ 가 임의의 벡터 $|\psi\rangle$ 에 대해 다음을 만족할 때, 이를 **contraction (수축) 연산자** 라 한다.

$$
\|\hat{T}|\psi\rangle\| \leq \|\psi\|
$$

즉 어떤 벡터에 작용해도 그 노름이 증가하지 않는다. 동등하게 작용소 노름으로 표현하면 $\|\hat{T}\| \leq 1$.

부등호가 strict 일 때 — 모든 비영벡터에 대해 $\|\hat{T}|\psi\rangle\| < \|\psi\|$ — 이를 **strict contraction** 이라 한다.

**2) 물리적 의미**

Contraction 연산자는 작용 후 벡터의 노름이 감소하는 변환을 표현한다. 양자역학에서 노름의 제곱이 확률을 의미하므로, contraction 변환은 **확률이 감소하는 변환** 을 기술한다.

이는 unitary (확률 보존) 와 대비된다. 환경과 결합된 시스템 (열린 시스템) 에서 시스템 외부로 확률이 누출되는 현상이 자연스러운 예 — NEGF 의 시간 진화가 대표적.

---

### 2. 고유값은 닫힌 단위 원판 내부에 있다

Contraction 연산자의 고유값은 모두 절댓값이 1 이하인 복소수이다.

$$
\sigma(\hat{T}) \subset \{\lambda \in \mathbb{C} : |\lambda| \leq 1\} = \overline{\mathbb{D}}
$$

복소 평면에서 닫힌 단위 원판 ($\overline{\mathbb{D}}$) 안에 위치. Strict contraction 의 경우 열린 단위 원판 (단위 원 경계 미포함) 내부.

proof)

$\hat{T}|v\rangle = \lambda|v\rangle$ 가정. 노름 계산:

$$
\|\hat{T}|v\rangle\|^2 = \|\lambda|v\rangle\|^2 = |\lambda|^2\,\|v\|^2
$$

Contraction 조건 $\|\hat{T}|v\rangle\|^2 \leq \|v\|^2$ 대입:

$$
|\lambda|^2\,\|v\|^2 \leq \|v\|^2
$$

$\|v\|^2 > 0$ 이므로 $|\lambda|^2 \leq 1$, 즉 $|\lambda| \leq 1$.

Strict contraction 의 경우 부등호가 strict 이므로 $|\lambda| < 1$.

---

### 3. 네 가지 정규 연산자의 통합

지금까지 도입한 정규 연산자들의 고유값 위치를 정리하면 다음과 같다.

| 연산자 | 정의 | 고유값 위치 | 복소 평면 |
|---|---|---|---|
| Hermitian | $\hat{H}^\dagger = \hat{H}$ | $\lambda \in \mathbb{R}$ | 실수 직선 |
| Anti-Hermitian | $\hat{A}^\dagger = -\hat{A}$ | $\lambda \in i\mathbb{R}$ | 허수 축 |
| Unitary | $\hat{U}^\dagger\hat{U} = \hat{I}$ | $\vert\lambda\vert = 1$ | 단위 원 위 |
| Contraction | $\Vert\hat{T}\psi\Vert \leq \Vert\psi\Vert$ | $\vert\lambda\vert \leq 1$ | 단위 원판 내부 |

네 가지 정의가 모두 한 단계 안에 고유값의 복소 평면 위에서의 위치를 결정한다. 각 정의가 본질적으로 spectrum 의 기하학적 제약을 표현한다.

Unitary 와 contraction 의 관계: unitary 는 contraction 의 특수 경우이다. 단위 원이 단위 원판의 경계이므로, 모든 unitary 는 자동으로 contraction (노름 보존이 노름 비증가의 특수 경우). 반대로 contraction 중에서 노름을 정확히 보존하는 것이 unitary.

---

### 4. 기본 성질

**1) 거듭제곱의 거동**

Strict contraction $\hat{T}$ ($|\lambda_n| < 1$ for all $n$) 의 거듭제곱은 0 으로 수렴.

$$
\hat{T}^n \to 0 \quad (n \to \infty)
$$

proof) Spectral 분해 $\hat{T} = \sum_n \lambda_n|v_n\rangle\langle v_n|$ 에서

$$
\hat{T}^n = \sum_k \lambda_k^n|v_k\rangle\langle v_k|
$$

$|\lambda_k| < 1$ 이므로 $\lambda_k^n \to 0$, 따라서 $\hat{T}^n \to 0$.

Non-strict contraction (단위 원 경계 포함) 에서는 일반적으로 수렴하지 않을 수 있다. 단위 원 위에 있는 고유값에 대응하는 부분이 영원히 진동.

**2) 노름의 감쇠율**

각 고유 상태 $|v_n\rangle$ 에 대해 $\hat{T}^n|v_k\rangle = \lambda_k^n|v_k\rangle$, 노름 $|\lambda_k|^n$. 가장 큰 $|\lambda_k|$ ($= r(\hat{T})$ = spectral radius) 가 점근적 감쇠율 결정.

$$
\|\hat{T}^n\| \approx r(\hat{T})^n \quad (n \to \infty)
$$

**3) 합성**

두 contraction 의 곱은 contraction.

$$
\|\hat{T}_1\hat{T}_2|\psi\rangle\| \leq \|\hat{T}_2|\psi\rangle\| \leq \|\psi\|
$$

두 단계의 contraction 부등식을 차례로 적용. (단, 두 contraction 이 가환할 때만 결과도 정규 contraction.)

---

### 5. Hermitian 과의 변환: 상반평면으로의 일반화

§3 의 비교표에서 보았듯, unitary 는 spectrum 이 단위 원 위 (실수 직선의 위로 휘어진 형태), contraction 은 단위 원판 내부. b_unitary.md §5 에서 Hermitian (실수 직선) 과 unitary (단위 원) 사이의 변환 $\hat{U} = e^{i\hat{H}}$ 가 spectral 매핑 $x \mapsto e^{ix}$ 의 functional calculus 표현임을 보았다.

자연스러운 일반화 질문: contraction (단위 원판 내부) 와 어떤 연산자 사이의 변환이 있는가?

**1) 복소 평면 매핑: 상반평면 → 단위 원판**

지수 함수 $f(z) = e^{iz}$ 를 복소수 $z$ 전체로 확장한다. $z = \theta + i\beta$ 라면

$$
e^{iz} = e^{i(\theta + i\beta)} = e^{i\theta}\cdot e^{-\beta}
$$

절댓값 $|e^{iz}| = e^{-\beta}$.

세 가지 경우:

| $z$ 의 위치 | $\beta$ | $|e^{iz}|$ | $e^{iz}$ 의 위치 |
|---|---|---|---|
| 실수 직선 | $\beta = 0$ | $= 1$ | 단위 원 위 |
| 상반평면 | $\beta > 0$ | $< 1$ | 단위 원판 내부 |
| 하반평면 | $\beta < 0$ | $> 1$ | 단위 원판 외부 |

따라서 $e^{iz}$ 가 상반평면을 단위 원판 내부로 매핑한다.

**2) Contraction 의 표현**

정규 연산자 $\hat{Z}$ 의 고유값이 모두 상반평면 ($\text{Im}\,\lambda_n \geq 0$) 에 있다고 가정. Functional calculus 로

$$
\hat{T} = e^{i\hat{Z}} = \sum_n e^{i\lambda_n}|v_n\rangle\langle v_n|
$$

각 $|e^{i\lambda_n}| = e^{-\text{Im}\,\lambda_n} \leq 1$. 따라서 $\hat{T}$ 의 spectrum 이 단위 원판 내부 — **contraction**.

명시적으로: $\hat{Z} = \hat{H}_1 + i\hat{H}_2$ 로 분해할 수 있을 때 ($\hat{H}_1, \hat{H}_2$ Hermitian), 정규 조건과 상반평면 조건이 다음과 같이 표현된다.

- $\hat{Z}$ 정규: $[\hat{H}_1, \hat{H}_2] = 0$
- Spectrum 상반평면: $\hat{H}_2 \geq 0$ (양의 정부호)

두 Hermitian 부분이 가환하고 허수 부분이 양의 정부호일 때 $\hat{Z}$ 가 상반평면 정규 연산자이며, $e^{i\hat{Z}}$ 가 contraction.

**3) 단위 원 경계와 strict contraction**

위 표현에서 $|e^{i\lambda_n}| < 1$ 의 조건은 $\text{Im}\,\lambda_n > 0$ (strict 상반평면). 즉 $\hat{H}_2 > 0$ (strict positive definite). 이 경우 $\hat{T}$ 가 strict contraction.

$\hat{H}_2 = 0$ 이면 $\hat{Z}$ 가 Hermitian 으로 환원되고 $e^{i\hat{Z}}$ 가 unitary (단위 원 경계). 그 사이 — 일부 고유값은 단위 원 위, 일부는 내부 — 의 경우도 가능.

**4) NEGF 의 시간 진화와의 직접 연결**

NEGF 의 effective Hamiltonian (가환 경우, 정규)

$$
\hat{H}_{\text{eff}} = \hat{H}_s + \hat{\Delta} - \frac{i}{2}\hat{\Gamma}
$$

$\hat{H}_s + \hat{\Delta}$ 가 Hermitian, $\hat{\Gamma} \geq 0$ 이 Hermitian.

시간 진화 연산자

$$
\hat{T}(t) = e^{-i\hat{H}_{\text{eff}}t/\hbar} = e^{i\hat{Z}(t)}, \quad \hat{Z}(t) = -\frac{t}{\hbar}\hat{H}_{\text{eff}}
$$

$\hat{Z}(t)$ 의 Hermitian / anti-Hermitian 분해:

$$
\hat{Z}(t) = -\frac{t}{\hbar}(\hat{H}_s + \hat{\Delta}) + i\,\frac{t}{2\hbar}\hat{\Gamma}
$$

$t > 0$ 에서 허수 부분의 계수 $t\hat{\Gamma}/(2\hbar) \geq 0$ — 상반평면 정규 연산자.

따라서 $\hat{T}(t) = e^{i\hat{Z}(t)}$ 가 contraction. NEGF 의 시간 진화가 정확히 §5-(2) 의 contraction 표현의 한 사례.

이 결과는 NEGF 의 열린 시스템 시간 진화가 contraction 구조를 가진다는 사실의 명시적 도출이다.

---

### 6. 1-Parameter Contraction Semigroup

Unitary 의 경우 시간 진화 unitary 들의 모음 $\{\hat{U}(t)\}_{t \in \mathbb{R}}$ 이 1-parameter unitary 군 (group) 을 이루었다 (b_unitary.md §7). Contraction 에서는 비슷한 구조 — 그러나 **semigroup** — 이 등장.

**1) 1-parameter semigroup 의 정의**

연산자들의 모음 $\{\hat{T}(t)\}_{t \geq 0}$ 이 다음을 만족할 때 1-parameter semigroup 이라 한다.

(a) $\hat{T}(0) = \hat{I}$
(b) $\hat{T}(t + s) = \hat{T}(t)\hat{T}(s)$ for $t, s \geq 0$
(c) $t \to s$ 일 때 $\hat{T}(t)|v\rangle \to \hat{T}(s)|v\rangle$ (연속성)

군 (group) 의 정의 (b_unitary.md §7) 와 차이는 parameter 가 $t \in [0, \infty)$ — 음수 시간이 없음. 즉 시간 역행이 가능하지 않다. 시간 진화가 단방향.

각 $\hat{T}(t)$ 가 contraction 이면 **1-parameter contraction semigroup**.

**2) 군이 아닌 semigroup 인 이유**

Contraction 의 거듭제곱은 노름을 감쇠시킨다. 만약 역연산자 $\hat{T}(t)^{-1}$ 가 존재한다면, 그것은 노름을 증가시키는 변환 — contraction 이 아님. 따라서 contraction 의 역원이 일반적으로 존재하지 않고, 역시간 진화가 불가능하다.

물리적 의미: 열린 시스템에서 환경으로 빠져나간 정보는 다시 복원할 수 없다. **비가역성** 의 수학적 표현.

**3) Generator 와 Hille-Yoshida 정리**

1-parameter 군의 경우 Stone 정리가 generator 를 Hermitian (또는 anti-Hermitian 으로) 결정했다. Contraction semigroup 에서는 비슷한 정리 — **Hille-Yoshida 정리** — 가 작동한다.

대략적 statement: 1-parameter contraction semigroup 의 generator $\hat{X}$ 는 다음 조건을 만족한다.

$$
\hat{T}(t) = e^{t\hat{X}}, \quad \hat{X} \text{ 의 spectrum } \subset \{z : \text{Re}\,z \leq 0\}
$$

Generator 의 spectrum 이 **닫힌 좌반평면** 에 위치. 양의 무한대로 발산하는 진폭이 없도록 강제하는 조건.

NEGF 의 케이스에서: $\hat{T}(t) = e^{-i\hat{H}_{\text{eff}}t/\hbar}$, generator $\hat{X} = -i\hat{H}_{\text{eff}}/\hbar$. $\hat{H}_{\text{eff}}$ 의 spectrum 이 하반평면 ($\text{Im}\,\lambda_n \leq 0$) 이면 $-i\hat{H}_{\text{eff}}/\hbar$ 의 spectrum 이 좌반평면 ($\text{Re}\,\lambda_n \leq 0$) — Hille-Yoshida 조건 만족.

---

### 7. 닫힌 시스템과 열린 시스템

지금까지의 결과를 종합하면 정규 연산자 framework 안에서 닫힌 / 열린 시스템의 자연스러운 비교가 가능하다.

| | 닫힌 시스템 | 열린 시스템 |
|---|---|---|
| Hamiltonian | $\hat{H}$ Hermitian | $\hat{H}_{\text{eff}} = \hat{H} + \hat{\Sigma}^R$ 비-Hermitian normal |
| Spectrum 위치 | 실수 직선 | 하반평면 ($\text{Im}\,\lambda_n \leq 0$) |
| 시간 진화 | $e^{-i\hat{H}t/\hbar}$ Unitary | $e^{-i\hat{H}_{\text{eff}}t/\hbar}$ Contraction |
| 노름 거동 | 보존 | 감쇠 |
| 진화 구조 | 1-parameter 군 (Stone) | 1-parameter semigroup (Hille-Yoshida) |
| 가역성 | 가역 | 비가역 |
| 물리적 의미 | 확률 보존 | 환경으로 확률 누출 |

두 시스템이 정규 연산자 framework 안의 두 극단 (단위 원 위 vs 단위 원판 내부). 각자의 generator 가 다른 spectrum 위치 (실수 직선 vs 하반평면) 를 갖는 정규 연산자.

이 비교가 NEGF 의 수학적 위치를 명확히 한다. NEGF 의 시간 진화는 정규 contraction semigroup 의 특수한 경우 — $\hat{H}_{\text{eff}}$ 의 Hermitian/anti-Hermitian 부분이 가환할 때.

비가환 경우 (일반 NEGF) 는 비정규 영역으로 들어가며, 별도 framework (다음 챕터) 가 필요하다.

---

### 8. 예

**1) 가장 단순한 strict contraction**

$$
\hat{T} = c\hat{I}, \quad 0 < c < 1
$$

스칼라 곱. 고유값 = $c$, 모든 고유벡터가 단일 고유공간.

거듭제곱: $\hat{T}^n = c^n\hat{I} \to 0$. 모든 벡터의 노름이 $c^n$ 으로 감쇠.

Hermitian generator 와의 관계: $\hat{T} = e^{i\hat{Z}}$ where $\hat{Z} = -i\ln(c)\hat{I}$. 즉 $\hat{Z}$ 의 고유값 = $-i\ln(c) = i\ln(1/c)$ (순허수, 상반평면 — $c < 1$ 이므로 $\ln(1/c) > 0$).

**2) 2-레벨 damped 시스템**

상태 공간 $\mathbb{C}^2$, contraction 연산자:

$$
\hat{T} = e^{-\gamma_1/2}|0\rangle\langle 0| + e^{-\gamma_2/2}|1\rangle\langle 1|
$$

$\gamma_1, \gamma_2 > 0$. 두 고유값 $e^{-\gamma_1/2}, e^{-\gamma_2/2}$ 모두 단위 원판 내부 (양의 실수 직선의 한 부분).

물리적 의미: $|0\rangle, |1\rangle$ 두 상태가 각각 다른 비율로 환경으로 누출. 노름 감쇠 비율이 다름. 

NEGF 와의 연결: 두 lead 와 결합된 2-level system 의 시간 진화의 한 모형. $\gamma_{1,2}$ 가 각 상태의 lifetime 의 역수.

**3) NEGF 시간 진화 (가환 케이스)**

§5-(4) 에서 도출한 결과를 명시적으로 본다.

시스템 $\hat{H}_s$ 의 고유 상태 $\{\psi_n, \epsilon_n\}$, 가환 결합 $\hat{\Gamma}$ 의 같은 고유 기저에서의 고유값 $\gamma_n$.

시간 진화:

$$
\hat{T}(t)|\psi_n\rangle = e^{-i\epsilon_n t/\hbar}\,e^{-\gamma_n t/(2\hbar)}|\psi_n\rangle
$$

진폭 $e^{-\gamma_n t/(2\hbar)}$ 으로 시간에 따라 감쇠. 평균 수명 $\tau_n = \hbar/\gamma_n$.

거듭제곱 거동: $\hat{T}(t)^k = \hat{T}(kt)$ 이므로 $t \to \infty$ 한계에서 모든 상태가 0 으로 수렴 — 결국 시스템 전체가 환경으로 누출.

이 결과가 NEGF 의 산란 영역의 입자가 시간이 지나면 결국 모두 환경 (lead) 으로 빠져나간다는 사실의 수학적 표현. 정상상태에서는 lead 가 동시에 입자를 주입하기 때문에 평형이 형성되며, 이것이 lesser self-energy $\hat{\Sigma}^<$ 가 표현하는 정보 (NEGF 챕터 참조).
