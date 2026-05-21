+++
title = '(b) I-contraction'
weight = 1
+++

---

### 1. I-contraction 의 정의: 내적(확률) 감소 연산자

**1) 직관적 의미**

**이 연산자는 내적이 보존되는 I-유니타리 연산자에 대응된다.**

작용소 $\hat{T}$ 가 어떤 벡터에 작용했을 때 그 벡터의 길이를 늘리지 않으면 이를 I-contraction 이라 부른다. 어떤 벡터 $|\psi\rangle$ 에 작용해도 결과 $\hat{T}|\psi\rangle$ 의 길이가 원래의 길이보다 길어지지 않는다는 의미이다. 길이가 줄어들거나 또는 원래의 길이와 같은 상태로 유지된다.

이 조건이 작용소의 spectrum 이 어디에 있는지 또는 작용소가 정규인지 여부와는 무관하다. 단지 벡터의 길이가 어떻게 변하는지에 대한 조건이며, spectrum 의 위치나 정규성은 정의에 들어가지 않는다.

본 작용소가 표준 inner product (즉 metric operator 가 $\hat{I}$ 인 case) 의 기준에서 norm 의 감소를 짚는 작용소이므로 I-contraction 이라 부른다. 일반화된 metric ($\hat{G}$ 또는 $\hat{J}$) 의 기준에서의 contraction 작용소가 별도 chapter 에서 다뤄진다.

**2) 수식 형태**

벡터의 길이를 노름 $\|\cdot\|$ 으로 나타내면 I-contraction 의 조건이 다음 부등식의 형태로 표현된다.

$$
\|\hat{T}|\psi\rangle\| \leq \|\psi\| \quad \text{for all } |\psi\rangle
$$

좌변이 작용소 $\hat{T}$ 가 작용한 후 벡터의 노름을 나타내고, 우변이 원래 벡터의 노름을 나타낸다. 모든 벡터 $|\psi\rangle$ 에 대해 좌변이 우변보다 작거나 같아야 한다는 조건이다.

**3) Operator norm 으로의 표현**

작용소 $\hat{T}$ 가 어떤 벡터를 가장 크게 늘리는지를 나타내는 양을 operator norm 이라 부르고, 다음과 같이 정의한다.

$$
\|\hat{T}\| := \sup_{|\psi\rangle \neq 0} \frac{\|\hat{T}|\psi\rangle\|}{\|\psi\|}
$$

이 양이 모든 비영 벡터에 대해 작용 후 노름을 원래 노름으로 나눈 값을 계산하고, 그 값들의 supremum 을 취한 것이다. 즉 작용소 $\hat{T}$ 가 어떤 벡터를 가장 크게 늘릴 때 그 늘림의 크기가 원래 길이의 몇 배인지를 나타내는 값이다.

이 정의를 사용하면 I-contraction 의 조건이 다음과 동등한 단일 부등식으로 표현된다.

$$
\|\hat{T}\| \leq 1
$$

작용소가 벡터를 가장 크게 늘릴 때조차 그 늘림의 크기가 원래 길이의 1배 이하라는 의미이다. 따라서 어떤 벡터도 원래의 길이보다 길어지지 않게 된다.

---

### 2. 지수화 & Upper-Hermitian

I-유니타리 연산자와 마찬가지로 지수 표현을 사용하여, **Upper-Hermitian** 연산자를 정의한다.

**1) 지수 표현**

$$
\hat{T} = \sum_{k=0}^{\infty} \frac{(i\hat{H}_\uparrow)^k}{k!} = e^{i\hat{H}_\uparrow}
$$

proof)

spectral 분해에서 출발한다. I-contraction 의 각 고유값 $\lambda_n$ 이 단위 원판 내부 또는 경계에 위치하므로 $|\lambda_n| \leq 1$ 이 성립한다. 0 이 아닌 $\lambda_n$ 을 극형식으로 풀면 $\lambda_n = r_n e^{i\theta_n}$ 의 형태가 되며, 여기서 $0 < r_n \leq 1$ 이고 $\theta_n \in \mathbb{R}$ 이다. $r_n$ 이 1 이하인 양수이므로 $r_n = e^{-\kappa_n}$ 의 형태로 다시 쓸 수 있으며, 이때 새 매개변수 $\kappa_n$ 이 0 이상의 실수이다.

$$
\lambda_n = e^{-\kappa_n} e^{i\theta_n} = e^{i(\theta_n + i\kappa_n)} = e^{i\mu_n}, \quad \mu_n = \theta_n + i\kappa_n
$$

새 매개변수 $\mu_n$ 의 허수부가 $\text{Im}\,\mu_n = \kappa_n \geq 0$ 이므로 $\mu_n$ 이 상반평면 (실수 직선 포함) 의 점에 해당한다. spectral 분해에 대입하면 다음 형태가 된다.

$$
\hat{T} = \sum_n e^{i\mu_n} |v_n\rangle\langle v^n|, \quad \mu_n \in \text{closed upper half-plane}
$$

각 스칼라 $e^{i\mu_n}$ 이 스칼라 지수 함수이며, 그 정의가 Taylor 급수의 무한 합으로 주어진다.

$$
e^{i\mu_n} = \sum_{k=0}^{\infty} \frac{(i\mu_n)^k}{k!}
$$

이 Taylor 급수를 spectral 분해에 대입하고 합의 순서를 바꾸면 다음과 같은 형태로 정리된다.

$$
\hat{T} = \sum_{k=0}^{\infty} \frac{i^k}{k!} \sum_n \mu_n^k |v_n\rangle\langle v^n|
$$

안쪽의 합 $\sum_n \mu_n^k |v_n\rangle\langle v^n|$ 이 어떤 작용소의 $k$ 거듭제곱과 같은 형태를 가지고 있다. 이를 활용하기 위해 다음 작용소를 정의한다. 이를 **Upper-Hermitian** 이라고 하자.

$$
\hat{H}_\uparrow := \sum_n \mu_n |v_n\rangle\langle v^n|
$$

거듭제곱의 결과를 이 정의에 적용하면 다음 등식이 성립한다.

$$
\hat{H}_\uparrow^k = \sum_n \mu_n^k |v_n\rangle\langle v^n|
$$

이를 위의 합 표현에 대입하면 작용소 $\hat{H}_\uparrow$ 가 다음과 같이 표현된다.

$$
\hat{T} = \sum_{k=0}^{\infty} \frac{(i\hat{H}_\uparrow)^k}{k!} = e^{i\hat{H}_\uparrow}
$$

**2) Upper-Hermitian $\hat{H}_\uparrow$ 의 Cartesian decomposition**

매개변수 $\mu_n$ 이 복소수 (상반평면) 이므로 $\hat{H}_\uparrow$ 가 일반적으로 Hermitian 이 아니다. 본 작용소를 Hermitian 부분과 anti-Hermitian 부분의 합으로 분해할 수 있다. 본 분해를 Cartesian decomposition 이라 부른다.

$$
\hat{H}_\uparrow = \hat{H}_1 + i\hat{H}_2
$$

여기서 $\hat{H}_1 := (\hat{H}_\uparrow + \hat{H}_\uparrow^\dagger)/2$ 가 Hermitian (실수부) 이고, $\hat{H}_2 := (\hat{H}_\uparrow - \hat{H}_\uparrow^\dagger)/(2i)$ 도 Hermitian (허수부의 계수) 이다.

---

### 3. spectrum: 상반평면 ↔ 단위 원판 내부

I-contraction $\hat{T}$ 와 generator $\hat{H}_\uparrow$ 의 spectrum 위치 사이의 관계가 직접적으로 따라 나온다. 이 관계를 정확히 풀어 짚어 본다.

$$
\hat{H}_\uparrow = \sum_n \mu_n |v_n\rangle\langle v^n|, \quad \hat{T} = \sum_n e^{i\mu_n} |v_n\rangle\langle v^n|
$$

I-contraction 의 조건이 $\|\hat{T}\| \leq 1$ 이며, spectral radius 의 일반적 부등식 $\rho(\hat{T}) \leq \|\hat{T}\|$ 가 모든 작용소에 대해 성립한다. 따라서 I-contraction 인 작용소의 spectral radius 도 1 이하의 값을 가지게 된다.

$$
\rho(\hat{T}) = \max_n |\lambda_n| \leq 1
$$

$\lambda_n = e^{i\mu_n}$ 에 의해 각 고유값의 크기가 $|\lambda_n| = e^{-\text{Im}\,\mu_n}$ 으로 주어지므로, 위의 조건이 다음과 같은 형태로 바뀐다.

$$
e^{-\text{Im}\,\mu_n} \leq 1 \implies \text{Im}\,\mu_n \geq 0
$$

즉 $\hat{H}_\uparrow$ 의 모든 고유값이 상반평면 (실수 직선 포함) 에 위치하게 된다. Generator 의 spectrum 위치와 작용소의 spectrum 위치 사이의 대응을 세 가지 경계 케이스로 정리하면 다음과 같다.

| $\hat{H}_\uparrow$ spectrum | 작용소 $\hat{T} = e^{i\hat{H}_\uparrow}$ spectrum |
|---|---|
| 실수 직선 ($\text{Im}\,\mu_n = 0$) | 단위 원 위 ($\vert\lambda_n\vert = 1$) |
| 상반평면 strict ($\text{Im}\,\mu_n > 0$) | 단위 원판 strict 내부 ($\vert\lambda_n\vert < 1$) |
| 상반평면 경계 (혼합) | 일부 원 위, 일부 원 내부 |

---

### 4. 정규성과의 무관함

I-contraction 의 정의가 작용소의 norm 의 조건 ($\|\hat{T}\| \leq 1$) 만 짚으며, 작용소의 정규성 ($[\hat{T}, \hat{T}^\dagger] = 0$) 의 조건을 포함하지 않는다. 따라서 I-contraction 인 작용소가 정규일 수도 있고, 비-정규일 수도 있다. 본 사실을 두 예로 직접 보인다.

**example1) 정규**

대각 행렬 $\hat{T} = \text{diag}(1/2, 1/3)$ 가 정규 (사실 Hermitian) 이고 $\|\hat{T}\| = 1/2 \leq 1$ 이므로 I-contraction 이다. 본 예가 정규인 I-contraction 의 존재를 보인다.

**example2) 비-정규**

상삼각 행렬을 다음과 같이 두자.

$$
\hat{T} = \begin{pmatrix} 1/2 & 1/4 \\ 0 & 1/3 \end{pmatrix}
$$

본 작용소의 정규성을 점검하기 위해 commutator $[\hat{T}, \hat{T}^\dagger]$ 를 계산한다.

sol)

$\hat{T}^\dagger \hat{T}$ 와 $\hat{T} \hat{T}^\dagger$ 를 각각 계산.

$$
\hat{T}^\dagger \hat{T} = \begin{pmatrix} 1/2 & 0 \\ 1/4 & 1/3 \end{pmatrix} \begin{pmatrix} 1/2 & 1/4 \\ 0 & 1/3 \end{pmatrix} = \begin{pmatrix} 1/4 & 1/8 \\ 1/8 & 25/144 \end{pmatrix}
$$

$$
\hat{T} \hat{T}^\dagger = \begin{pmatrix} 1/2 & 1/4 \\ 0 & 1/3 \end{pmatrix} \begin{pmatrix} 1/2 & 0 \\ 1/4 & 1/3 \end{pmatrix} = \begin{pmatrix} 5/16 & 1/12 \\ 1/12 & 1/9 \end{pmatrix}
$$

(1,1) 성분이 $1/4 \neq 5/16$ 이므로 두 행렬이 같지 않다. 따라서 $[\hat{T}, \hat{T}^\dagger] \neq 0$, 즉 본 작용소가 비-정규.

다음으로 본 작용소의 operator norm 을 계산한다. $\|\hat{T}\| = \sqrt{\lambda_{\max}(\hat{T}^\dagger \hat{T})}$ 의 form 으로 자리잡힌다. $\hat{T}^\dagger \hat{T}$ 의 고유값을 계산하면:

(1) trace = $1/4 + 25/144 = 36/144 + 25/144 = 61/144 \approx 0.4236$  
(2) det = $(1/4)(25/144) - (1/8)^2 = 25/576 - 1/64 = 25/576 - 9/576 = 16/576 = 1/36 \approx 0.0278$  
(3) 두 고유값이 $\lambda_\pm = (\text{trace} \pm \sqrt{\text{trace}^2 - 4\text{det}})/2$. 계산하면 $\lambda_+ \approx 0.3425$.  
(4) Operator norm 이 $\|\hat{T}\| = \sqrt{0.3425} \approx 0.585$.

본 값이 1 이하이므로 I-contraction 의 조건을 만족한다. 본 작용소 $\hat{T}$ 가 비-정규이면서 I-contraction 이다. 따라서 비-정규인 I-contraction 의 예가 존재한다. 두 예 (정규, 비-정규) 가 모두 I-contraction 의 조건을 만족하므로 본 framework 이 작용소의 정규성에 무관하다.
