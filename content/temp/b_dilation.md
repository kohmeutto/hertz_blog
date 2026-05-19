+++
title = "(b) Dilation"
weight = 6
+++

---

### 1. Dilation 연산자

**1) 정의**

정규 연산자 $\hat{D}$ 가 임의의 벡터 $|\psi\rangle$ 에 대해 다음을 만족할 때, 이를 **dilation (확장) 연산자** 라 한다.

$$
\|\hat{D}|\psi\rangle\| \geq \|\psi\|
$$

즉 어떤 벡터에 작용해도 그 노름이 감소하지 않는다. 동등하게 작용소 노름의 역 부등식으로 표현하면 $\|\hat{D}^{-1}\| \leq 1$ (역원이 존재할 때).

부등호가 strict 일 때 — 모든 비영벡터에 대해 $\|\hat{D}|\psi\rangle\| > \|\psi\|$ — 이를 **strict dilation** 이라 한다.

**2) 물리적 의미**

Dilation 연산자는 작용 후 벡터의 노름이 증가하는 변환을 표현한다. 양자역학에서 노름의 제곱이 확률을 의미하므로, dilation 변환은 **확률이 증가하는 변환** 을 기술한다.

이는 contraction (확률 감소) 의 자연스러운 쌍대. 물리적 등장 영역:

- **게인 매체 (gain medium)**: 외부에서 에너지를 공급받아 진폭이 증가하는 시스템 (레이저 매체 등).
- **시간 역행 (time reversal)**: contraction 의 역방향 진화.
- **측정 후처리**: 관측 후 정규화된 상태로의 변환.
- **점근적 분석의 한 영역**: bound state 가 아닌 발산하는 해 (예: $E < 0$ 에서의 자유 입자 영역에서 멀어지는 해).

---

### 2. 고유값은 닫힌 단위 원판 외부에 있다

Dilation 연산자의 고유값은 모두 절댓값이 1 이상인 복소수이다.

$$
\sigma(\hat{D}) \subset \{\lambda \in \mathbb{C} : |\lambda| \geq 1\}
$$

복소 평면에서 닫힌 단위 원판의 보집합 (외부). Strict dilation 의 경우 열린 외부 ($|\lambda| > 1$).

proof)

$\hat{D}|v\rangle = \lambda|v\rangle$ 가정. 노름 계산:

$$
\|\hat{D}|v\rangle\|^2 = |\lambda|^2\,\|v\|^2
$$

Dilation 조건 $\|\hat{D}|v\rangle\|^2 \geq \|v\|^2$ 대입:

$$
|\lambda|^2\,\|v\|^2 \geq \|v\|^2
$$

$\|v\|^2 > 0$ 이므로 $|\lambda|^2 \geq 1$, 즉 $|\lambda| \geq 1$.

Strict dilation 의 경우 부등호가 strict 이므로 $|\lambda| > 1$.

---

### 3. 다섯 가지 정규 연산자의 통합

지금까지 도입한 모든 정규 연산자의 spectrum 위치를 정리하면 다음과 같다.

| 연산자 | 정의 | 고유값 위치 | 복소 평면 |
|---|---|---|---|
| Hermitian | $\hat{H}^\dagger = \hat{H}$ | $\lambda \in \mathbb{R}$ | 실수 직선 |
| Anti-Hermitian | $\hat{A}^\dagger = -\hat{A}$ | $\lambda \in i\mathbb{R}$ | 허수 축 |
| Unitary | $\hat{U}^\dagger\hat{U} = \hat{I}$ | $\vert\lambda\vert = 1$ | 단위 원 위 |
| Contraction | $\Vert\hat{T}\psi\Vert \leq \Vert\psi\Vert$ | $\vert\lambda\vert \leq 1$ | 단위 원판 내부 |
| Dilation | $\Vert\hat{D}\psi\Vert \geq \Vert\psi\Vert$ | $\vert\lambda\vert \geq 1$ | 단위 원판 외부 |

다섯 가지 정의가 모두 한 단계 안에 spectrum 의 복소 평면 위에서의 위치를 결정한다.

**Unitary 의 특별한 위치**: 단위 원이 contraction 영역 (단위 원판) 과 dilation 영역의 공통 경계. Unitary 가 contraction 의 특수 경우인 동시에 dilation 의 특수 경우 — 노름 보존이 비증가 / 비감소 양쪽 조건을 동시 만족.

**Contraction 과 dilation 의 쌍대성**: 두 영역이 복소 평면을 단위 원 기준으로 안과 밖으로 분할. 대칭적 쌍대 관계 — §6 에서 자세히.

---

### 4. 기본 성질

**1) 거듭제곱의 발산**

Strict dilation $\hat{D}$ ($|\lambda_n| > 1$ for all $n$) 의 거듭제곱은 노름이 무한대로 발산.

$$
\|\hat{D}^n\| \to \infty \quad (n \to \infty)
$$

proof) Spectral 분해 $\hat{D} = \sum_n \lambda_n|v_n\rangle\langle v_n|$ 에서

$$
\hat{D}^n = \sum_k \lambda_k^n|v_k\rangle\langle v_k|
$$

$|\lambda_k| > 1$ 이므로 $|\lambda_k^n| = |\lambda_k|^n \to \infty$.

**2) 노름의 증가율**

각 고유 상태 $|v_n\rangle$ 에 대해 $\hat{D}^n|v_k\rangle = \lambda_k^n|v_k\rangle$, 노름 $|\lambda_k|^n$. 가장 큰 $|\lambda_k|$ 가 점근적 증가율 결정.

$$
\|\hat{D}^n\| \approx \max_k |\lambda_k|^n \quad (n \to \infty)
$$

**3) 합성**

두 dilation 의 곱은 dilation.

$$
\|\hat{D}_1\hat{D}_2|\psi\rangle\| \geq \|\hat{D}_2|\psi\rangle\| \geq \|\psi\|
$$

두 단계의 dilation 부등식을 차례로 적용. (두 dilation 이 가환할 때만 결과도 정규 dilation.)

---

### 5. Hermitian 과의 변환: 하반평면으로의 매핑

b_contraction.md §5 에서 정리한 복소 평면 매핑 분류를 다시 본다.

| $z$ 의 위치 | $\beta = \text{Im}\,z$ | $\vert e^{iz}\vert = e^{-\beta}$ | $e^{iz}$ 의 위치 |
|---|---|---|---|
| 실수 직선 | $\beta = 0$ | $= 1$ | 단위 원 위 |
| 상반평면 | $\beta > 0$ | $< 1$ | 단위 원판 내부 |
| 하반평면 | $\beta < 0$ | $> 1$ | 단위 원판 외부 |

세 번째 행이 dilation 의 매핑 — **하반평면 → 단위 원판 외부**.

**1) Dilation 의 표현**

정규 연산자 $\hat{Z}$ 의 고유값이 모두 하반평면 ($\text{Im}\,\lambda_n \leq 0$) 에 있다고 가정. Functional calculus 로

$$
\hat{D} = e^{i\hat{Z}} = \sum_n e^{i\lambda_n}|v_n\rangle\langle v_n|
$$

각 $|e^{i\lambda_n}| = e^{-\text{Im}\,\lambda_n} \geq 1$. 따라서 $\hat{D}$ 의 spectrum 이 단위 원판 외부 — **dilation**.

명시적으로 $\hat{Z} = \hat{H}_1 + i\hat{H}_2$ 로 분해할 수 있을 때 ($\hat{H}_1, \hat{H}_2$ Hermitian):

- $\hat{Z}$ 정규: $[\hat{H}_1, \hat{H}_2] = 0$
- Spectrum 하반평면: $\hat{H}_2 \leq 0$ (음의 정부호)

두 Hermitian 부분이 가환하고 허수 부분이 음의 정부호일 때 $\hat{Z}$ 가 하반평면 정규 연산자이며, $e^{i\hat{Z}}$ 가 dilation.

**2) Strict dilation 의 조건**

$|e^{i\lambda_n}| > 1$ 의 조건은 $\text{Im}\,\lambda_n < 0$ (strict 하반평면). 즉 $\hat{H}_2 < 0$ (strict negative definite). 이 경우 $\hat{D}$ 가 strict dilation.

$\hat{H}_2 = 0$ 이면 $\hat{Z}$ 가 Hermitian 으로 환원되고 $e^{i\hat{Z}}$ 가 unitary (단위 원 경계).

**3) Contraction 매핑과의 대칭**

| 입력 spectrum | 출력 spectrum | 종류 |
|---|---|---|
| 실수 직선 | 단위 원 위 | Unitary |
| 상반평면 ($\hat{H}_2 \geq 0$) | 단위 원판 내부 | Contraction |
| 하반평면 ($\hat{H}_2 \leq 0$) | 단위 원판 외부 | Dilation |

세 매핑이 같은 형식 $e^{i\hat{Z}}$ 의 다른 케이스이며, 입력의 spectrum 위치 ($\hat{Z}$ 의 허수부의 부호) 가 결과의 영역을 결정.

이 대칭이 정규 연산자 framework 의 통합된 그림을 완성한다.

---

### 6. Contraction 과의 쌍대 관계

Contraction 과 dilation 은 단위 원을 경계로 한 쌍대 영역. 두 영역의 관계가 역원으로 정확히 표현된다.

**1) 역원 관계**

Strict contraction $\hat{T}$ ($|\lambda_n| < 1$ 모든 $n$) 의 역원 $\hat{T}^{-1}$ 은 strict dilation.

proof) $\hat{T}$ 의 spectral 분해 $\hat{T} = \sum_n \lambda_n|v_n\rangle\langle v_n|$ 에서

$$
\hat{T}^{-1} = \sum_n \lambda_n^{-1}|v_n\rangle\langle v_n|
$$

$|\lambda_n| < 1$ 이므로 $|\lambda_n^{-1}| > 1$ — strict dilation. ✓

이 관계는 명확한 기하학적 의미: 단위 원판 내부의 점 $\lambda$ 에 대해 $1/\lambda$ 가 단위 원판 외부에 위치 (Möbius 변환 $z \to 1/z$ 의 성질).

**2) Non-strict 의 경우 주의**

Non-strict contraction (어떤 $|\lambda_n| = 1$ 도 가능) 의 경우 역원이 항상 존재하는 것은 아니다. $|\lambda_n| = 1$ 인 부분은 $\hat{T}^{-1}$ 의 spectrum 도 $|\lambda_n^{-1}| = 1$ 이고, $|\lambda_n| < 1$ 인 부분은 dilation 영역으로 매핑.

엄밀한 contraction-dilation 쌍대성은 strict 케이스에서 정확히 작동.

**3) 생성자의 부호 변경**

§5 의 표현 $\hat{D} = e^{i\hat{Z}}$ ($\hat{Z}$ 하반평면) 와 contraction $\hat{T} = e^{i\hat{Z}'}$ ($\hat{Z}'$ 상반평면) 의 관계를 본다.

$\hat{Z}' = -\hat{Z}$ 로 두면 $\hat{Z}'$ 의 고유값이 $\hat{Z}$ 의 고유값의 부호 반전이고, 따라서 하반평면 → 상반평면 변환. 결과:

$$
\hat{D} = e^{i\hat{Z}}, \quad \hat{T} = e^{-i\hat{Z}} = \hat{D}^{-1}
$$

생성자 $\hat{Z}$ 의 부호 변경이 곧 dilation 과 contraction 의 변환. 시간 역행에 직접 대응 — $\hat{T}(t)$ 가 contraction 이면 $\hat{T}(-t)$ 가 dilation.

---

### 7. 시간 역행

§6-(3) 에서 본 generator 부호 변경 ($\hat{Z} \to -\hat{Z}$) 이 시간 역행에 직접 대응한다. 좀 더 자세히 본다.

**1) Contraction semigroup 의 양의 시간 도메인**

연속 1-parameter contraction semigroup $\{\hat{T}(t)\}_{t \geq 0}$ (b_contraction.md §6) 는 generator $\hat{X}$ 와 $\hat{T}(t) = e^{t\hat{X}}$ 의 관계. Generator $\hat{X}$ 의 spectrum 이 좌반평면 ($\text{Re}\,\lambda_n \leq 0$) 이면 contraction 이 유지된다.

이 semigroup 은 $t \geq 0$ 에서만 정의된다. 시간 역행 ($t < 0$) 은 일반적으로 정의되지 않는다 — contraction 의 역원이 dilation 이며 역시간 진화는 일반적으로 비물리적.

**2) 시간 역행 dilation**

수학적으로 $\hat{T}(t)$ 를 음의 시간으로 분석적 확장하면

$$
\hat{T}(t) = e^{t\hat{X}}, \quad t < 0
$$

$\hat{X}$ 의 spectrum 이 좌반평면이므로 $t\hat{X}$ 의 spectrum 이 ($t < 0$) 우반평면. Spectral 매핑

$$
|e^{t\lambda_n}| = e^{t\,\text{Re}\,\lambda_n}
$$

$t < 0$, $\text{Re}\,\lambda_n \leq 0$ 이면 $t\,\text{Re}\,\lambda_n \geq 0$, 따라서 $|e^{t\lambda_n}| \geq 1$ — **dilation**.

**3) 비가역성의 표현**

이 시간 역행 dilation 거동은 contraction semigroup 의 양의 시간 도메인의 자연스러운 수학적 확장이지만, 물리적으로는 환경에서 시스템으로 정보가 흘러들어오는 비물리적 시나리오. Contraction semigroup 이 $t \geq 0$ 에서만 정의되는 이유는 열린 시스템의 **비가역성** 의 표현.

수학적 정리:
- $t > 0$: contraction (노름 감쇠)
- $t = 0$: 항등
- $t < 0$: dilation (노름 증가, 비물리적)

---

### 8. Nagy-Foias Dilation 정리 (용어 주의)

작용소 이론에 같은 이름이지만 다른 의미의 정리가 있다 — **Nagy-Foias unitary dilation theorem**. 헷갈리지 않도록 짧게 정리.

**1) 정리의 statement**

모든 contraction $\hat{T}$ ($\|\hat{T}\| \leq 1$) 는 더 큰 Hilbert 공간 $\mathcal{K} \supset \mathcal{H}$ 의 unitary 연산자 $\hat{U}$ 의 **compression** (사영) 으로 표현 가능.

$$
\hat{T}^n = \hat{P}_\mathcal{H}\,\hat{U}^n\,\hat{P}_\mathcal{H}, \quad n \geq 0
$$

$\hat{P}_\mathcal{H}$ 는 $\mathcal{H}$ 로의 사영. 즉 contraction 의 거듭제곱을 큰 공간의 unitary 의 거듭제곱으로 "확장" 한 후 다시 작은 공간으로 사영한 것.

**2) 두 가지 의미의 "Dilation"**

| 의미 | 본 절의 dilation | Nagy-Foias dilation |
|---|---|---|
| 정의 | Spectrum 이 단위 원판 외부 | Contraction 을 unitary 로 확장 |
| 대상 | 개별 정규 연산자 | Contraction 의 확장된 표현 |
| 결과 | 노름 증가 변환 | 큰 공간의 unitary |
| 용도 | Contraction 의 쌍대 | Contraction 의 unitary 모델링 |

두 용어가 같은 단어이지만 다른 개념. 본 절의 dilation 은 spectrum 의 기하학적 위치로 정의된 정규 연산자의 한 종류. Nagy-Foias 의 dilation 은 contraction 을 더 큰 공간의 unitary 로 끌어올리는 (lifting) 과정.

---

### 9. 예

**1) 가장 단순한 strict dilation**

$$
\hat{D} = c\hat{I}, \quad c > 1
$$

스칼라 곱. 고유값 = $c > 1$, 모든 고유벡터가 단일 고유공간.

거듭제곱: $\hat{D}^n = c^n\hat{I} \to \infty$. 모든 벡터의 노름이 $c^n$ 으로 증가.

Hermitian generator 와의 관계: $\hat{D} = e^{i\hat{Z}}$ where $\hat{Z} = -i\ln(c)\hat{I}$. 고유값 = $-i\ln(c)$ (순허수, 하반평면 — $c > 1$ 이므로 $\ln(c) > 0$).

역원: $\hat{D}^{-1} = c^{-1}\hat{I}$ ($0 < c^{-1} < 1$), strict contraction. b_contraction.md §8-(1) 예제의 정확한 역.

**2) 2-레벨 amplified 시스템**

상태 공간 $\mathbb{C}^2$, dilation 연산자:

$$
\hat{D} = e^{\gamma_1/2}|0\rangle\langle 0| + e^{\gamma_2/2}|1\rangle\langle 1|
$$

$\gamma_1, \gamma_2 > 0$. 두 고유값 $e^{\gamma_1/2}, e^{\gamma_2/2}$ 모두 단위 원판 외부 (양의 실수 직선의 한 부분, 1 보다 큰 영역).

물리적 의미: $|0\rangle, |1\rangle$ 두 상태가 각각 다른 비율로 진폭 증폭. 게인 매체의 두 모드.

대칭성: b_contraction.md §8-(2) 의 damped 시스템과 역원 관계. 한쪽이 contraction (감쇠) 이면 반대쪽이 dilation (증폭).

**3) Contraction semigroup 의 음의 시간 확장**

§7 의 결과를 명시적으로 본다.

Contraction semigroup $\hat{T}(t) = e^{t\hat{X}}$ ($t \geq 0$, $\hat{X}$ 의 spectrum 좌반평면) 의 음의 시간 분석적 확장. 공통 고유 기저에서

$$
\hat{T}(t)|v_n\rangle = e^{t\lambda_n}|v_n\rangle, \quad \lambda_n = \alpha_n + i\beta_n,\;\alpha_n \leq 0
$$

진폭 $|e^{t\lambda_n}| = e^{t\alpha_n}$.

세 가지 시간 영역:

| 시간 | $t\alpha_n$ | 진폭 거동 | 종류 |
|---|---|---|---|
| $t > 0$ | $\leq 0$ | $\leq 1$ (감쇠) | Contraction |
| $t = 0$ | $0$ | $= 1$ | 항등 |
| $t < 0$ | $\geq 0$ | $\geq 1$ (증가) | Dilation |

이 분류가 contraction-dilation-unitary 의 통합된 그림에서 1-parameter semigroup 의 정확한 위치. 음의 시간 도메인의 dilation 거동은 양의 시간 contraction 의 수학적 역원이며, 물리적으로는 비가역성으로 인해 일반적으로 정의되지 않는다.
