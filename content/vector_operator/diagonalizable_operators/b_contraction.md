+++
title = "(b) Contraction"
weight = 1
+++

---

### 1. Contraction 의 정의: 내적(확률) 감소 연산자

**1) 직관적 의미**

**이 연산자는 내적이 보존되는 Unitary 연산자에 대응된다.**

작용소 $\hat{T}$ 가 어떤 벡터에 작용했을 때 그 벡터의 길이를 늘리지 않으면 이를 contraction 이라 부른다. 어떤 벡터 $|\psi\rangle$ 에 작용해도 결과 $\hat{T}|\psi\rangle$ 의 길이가 원래의 길이보다 길어지지 않는다는 의미이다. 길이가 줄어들거나 또는 원래의 길이와 같은 상태로 유지된다.

이 조건이 작용소의 spectrum 이 어디에 있는지 또는 작용소가 정규인지 여부와는 무관하다. 단지 벡터의 길이가 어떻게 변하는지에 대한 조건이며, spectrum 의 위치나 정규성은 정의에 들어가지 않는다.

**2) 수식 형태**

벡터의 길이를 노름 $\|\cdot\|$ 으로 나타내면 contraction 의 조건이 다음 부등식의 형태로 표현된다.

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

이 정의를 사용하면 contraction 의 조건이 다음과 동등한 단일 부등식으로 표현된다.

$$
\|\hat{T}\| \leq 1
$$

작용소가 벡터를 가장 크게 늘릴 때조차 그 늘림의 크기가 원래 길이의 1배 이하라는 의미이다. 따라서 어떤 벡터도 원래의 길이보다 길어지지 않게 된다.

---

### 2. 지수화 & Upper-Hermitian

유니타리 연산자와 마찬자기로 지수 표현을 사용하여, **Upper-Hermitian** 연산자를 정의한다.

**1) 지수 표현**

$$
\hat{T} = \sum_{k=0}^{\infty} \frac{(i\hat{H}_\uparrow)^k}{k!} = e^{i\hat{H}_\uparrow}
$$

proof)

spectral 분해에서 출발한다. Contraction 의 각 고유값 $\lambda_i$ 이 단위 원판 내부 또는 경계에 위치하므로 $|\lambda_i| \leq 1$ 이 성립한다. 0 이 아닌 $\lambda_i$ 을 극형식으로 풀면 $\lambda_i = r_i e^{i\theta_i}$ 의 형태가 되며, 여기서 $0 < r_i \leq 1$ 이고 $\theta_i \in \mathbb{R}$ 이다. $r_i$ 이 1 이하인 양수이므로 $r_i = e^{-\kappa_i}$ 의 형태로 다시 쓸 수 있으며, 이때 새 매개변수 $\kappa_i$ 이 0 이상의 실수이다.

$$
\lambda_i = e^{-\kappa_i} e^{i\theta_i} = e^{i(\theta_i + i\kappa_i)} = e^{i\mu_i}, \quad \mu_i = \theta_i + i\kappa_i
$$

새 매개변수 $\mu_i$ 의 허수부가 $\text{Im}\,\mu_i = \kappa_i \geq 0$ 이므로 $\mu_i$ 이 상반평면 (실수 직선 포함) 의 점에 해당한다. spectral 분해에 대입하면 다음 형태가 된다.

$$
\hat{T} = \sum_i e^{i\mu_i} |v_i\rangle\langle v^i|, \quad \mu_i \in \text{closed upper half-plane}
$$

각 스칼라 $e^{i\mu_i}$ 이 스칼라 지수 함수이며, 그 정의가 Taylor 급수의 무한 합으로 주어진다.

$$
e^{i\mu_i} = \sum_{k=0}^{\infty} \frac{(i\mu_i)^k}{k!}
$$

이 Taylor 급수를 spectral 분해에 대입하고 합의 순서를 바꾸면 다음과 같은 형태로 정리된다.

$$
\hat{T} = \sum_{k=0}^{\infty} \frac{i^k}{k!} \sum_i \mu_i^k |v_i\rangle\langle v^i|
$$

안쪽의 합 $\sum_i \mu_i^k |v_i\rangle\langle v^i|$ 이 어떤 작용소의 $k$ 거듭제곱과 같은 형태를 가지고 있다. 이를 활용하기 위해 다음 작용소를 정의한다. 이를 **Upper-Hermitian** 이라고 하자.

$$
\hat{H}_\uparrow := \sum_i \mu_i |v_i\rangle\langle v^i|
$$

거듭제곱의 결과를 이 정의에 적용하면 다음 등식이 성립한다.

$$
\hat{H}_\uparrow^k = \sum_i \mu_i^k |v_i\rangle\langle v^i|
$$

이를 위의 합 표현에 대입하면 작용소 $\hat{H}_\uparrow$ 가 다음과 같이 표현된다.

$$
\hat{T} = \sum_{k=0}^{\infty} \frac{(i\hat{H}_\uparrow)^k}{k!} = e^{i\hat{Z}}
$$

**2) Upper-Hermitian $\hat{H}_\uparrow$**

- 매개변수 $\mu_i$ 이 복소수 (상반평면) 이므로 $\hat{Z}$ 가 일반적으로 Hermitian 이 아니다.
- 이 경우, $\hat{H}_\uparrow$ 가 $\hat{H}_\uparrow = \hat{H}_1 + i\hat{H}_2$ 의 형태로 분해될 수 있다.
- 이 두 부분이 같은 spectral 기저를 공유하므로 가환한다.

---

### 4. spectrum: 상반평면 ↔ 단위 원판 내부

contraction $\hat{T}$ 와 generator $\hat{H}_\uparrow$ 의 spectrum 위치 사이의 관계가 직접적으로 따라 나온다. 이 관계를 정확히 풀어 짚어 본다.

$$
\hat{H}_\uparrow = \sum_i \lambda_i |\lambda_i\rangle\langle \lambda^i|, \quad \hat{U} = \sum_i e^{i\lambda_i} |\lambda_i\rangle\langle \lambda^i|
$$

Contraction 의 조건이 $\|\hat{T}\| \leq 1$ 이며, spectral radius 의 일반적 부등식 $\rho(\hat{T}) \leq \|\hat{T}\|$ 가 모든 작용소에 대해 성립한다. 따라서 contraction 인 작용소의 spectral radius 도 1 이하의 값을 가지게 된다.

$$
\rho(\hat{T}) = \max_i |\lambda_i| \leq 1
$$

$\lambda_i = e^{i\mu_i}$ 에 의해 각 고유값의 크기가 $|\lambda_i| = e^{-\text{Im}\,\mu_i}$ 으로 주어지므로, 위의 조건이 다음과 같은 형태로 바뀐다.

$$
e^{-\text{Im}\,\mu_i} \leq 1 \implies \text{Im}\,\mu_i \geq 0
$$

즉 $\hat{H}_\uparrow$ 의 모든 고유값이 상반평면 (실수 직선 포함) 에 위치하게 된다. Generator 의 spectrum 위치와 작용소의 spectrum 위치 사이의 대응을 세 가지 경계 케이스로 정리하면 다음과 같다.

| $\hat{H}_\uparrow$ spectrum | 작용소 $\hat{T} = e^{i\hat{H}_\uparrow}$ spectrum |
|---|---|
| 실수 직선 ($\text{Im}\,\mu_i = 0$) | 단위 원 위 ($\vert\lambda_i\vert = 1$) |
| 상반평면 strict ($\text{Im}\,\mu_i > 0$) | 단위 원판 strict 내부 ($\vert\lambda_i\vert < 1$) |
| 상반평면 경계 (혼합) | 일부 원 위, 일부 원 내부 |

---

### 5. 거듭제곱과 transient 거동

Strict contraction $\hat{T}$ — 모든 $n$ 에 대해 $\kappa_i > 0$ 이 성립 — 의 $m$ 거듭제곱이 다음과 같이 계산된다.

$$
\hat{T}^m = \sum_i e^{im\mu_i} |v_i\rangle\langle v^i| = \sum_i e^{im\theta_i} e^{-m\kappa_i} |v_i\rangle\langle v^i|
$$

각 사영 위에서 위상이 $m\theta_i$ 만큼 회전하고 노름이 $e^{-m\kappa_i}$ 의 배율로 감쇠하게 된다. $m$ 이 무한대로 가는 한계에서 $e^{-m\kappa_i}$ 이 0 으로 가므로 거듭제곱 $\hat{T}^m$ 이 0 작용소로 수렴한다.

**정규 케이스의 monotonic 감쇠**

정규 케이스에서는 §5 에서 확인한 대로 operator norm 이 spectral radius 와 정확히 일치한다. 따라서 거듭제곱의 노름이 다음과 같은 단일 표현으로 정리된다.

$$
\|\hat{T}^m\| = \rho(\hat{T}^m) = \rho(\hat{T})^m = e^{-m\kappa_{\min}}
$$

여기서 $\kappa_{\min} = \min_i \kappa_i$ 이 모든 $\kappa_i$ 중 가장 작은 값을 나타낸다. 이 표현이 $m$ 에 대해 monotonic 하게 감소하는 형태이므로, 시간이 갈수록 노름이 단조롭게 줄어들게 되고 어떤 시점에서도 일시적으로 증가하는 일이 발생하지 않는다.

**비-정규 케이스의 transient amplification**

비-정규 케이스에서는 operator norm 이 spectral radius 보다 큰 값을 가질 수 있기 때문에, 거듭제곱의 노름 $\|\hat{T}^m\|$ 이 $m$ 에 대해 monotonic 하지 않은 거동을 보일 수 있다. 짧은 $m$ 영역에서 노름이 1 을 넘어 증가하는 경우가 발생할 수 있으며, 이러한 거동을 transient amplification 이라 부른다.

큰 $m$ 영역에서는 점근적으로 spectral radius 의 거동으로 돌아가게 된다. Gelfand 의 공식에 따르면 다음 관계가 성립한다.

$$
\lim_{m \to \infty} \|\hat{T}^m\|^{1/m} = \rho(\hat{T}) = e^{-\kappa_{\min}}
$$

이 한계가 의미하는 것이 충분히 큰 $m$ 에서 노름이 spectral radius 의 거듭제곱처럼 감쇠하게 된다는 사실이다. 그러나 유한한 $m$ 의 영역에서는 $\|\hat{T}^m\| > \rho(\hat{T})^m$ 가 성립할 수 있으며, 특히 작은 $m$ 영역에서 노름이 1 을 초과하는 일이 가능하다.

이러한 transient 거동의 크기가 spectral 분해의 사영 $|v_i\rangle\langle v^i|$ 이 얼마나 정규 직교에 가까운지에 의존한다. 사영들이 거의 정규 직교에 가까운 경우에는 transient 가 작게 나타나고, 사영들이 매우 nonorthogonal 일수록 transient 가 크게 나타나게 된다.

---

### 8. NEGF 응용

NEGF 의 효과 Hamiltonian 이 다음과 같은 형태로 주어진다.

$$
\hat{H}_{\text{eff}}(E) = \hat{H}_s + \hat{\Sigma}^R(E), \quad \hat{\Sigma}^R(E) = \hat{\Delta}(E) - i\hat{\eta}_0(E)
$$

여기서 $\hat{H}_s$ 가 시스템의 Hermitian Hamiltonian 이고, $\hat{\Sigma}^R$ 이 lead 와의 결합에서 발생하는 retarded self-energy 에 해당한다. Self-energy 의 실수부 $\hat{\Delta}$ 가 Hermitian 이며, 허수부 $\hat{\eta}_0$ 가 positive semi-definite 한 Hermitian 작용소이다.

이 작용소의 정규성을 점검하기 위해 dual 을 계산하면 다음과 같다.

$$
\hat{H}_{\text{eff}}^\dagger = \hat{H}_s + \hat{\Delta} + i\hat{\eta}_0 = \hat{H}_{\text{eff}} + 2i\hat{\eta}_0
$$

이로부터 commutator 를 계산하면 다음 형태로 정리된다.

$$
[\hat{H}_{\text{eff}}, \hat{H}_{\text{eff}}^\dagger] = 2i[\hat{H}_{\text{eff}}, \hat{\eta}_0] = 2i[\hat{H}_s + \hat{\Delta}, \hat{\eta}_0]
$$

표준적인 NEGF 의 상황에서는 $\hat{\eta}_0$ 가 시스템의 경계 site 에만 비영인 sparse 행렬이고 $\hat{H}_s$ 가 시스템 전체 site 사이의 hopping 을 가진 행렬이므로, 두 작용소가 일반적으로 서로 가환하지 않는다. 따라서 commutator 가 0 이 되지 않으며, 효과 Hamiltonian $\hat{H}_{\text{eff}}$ 가 비-정규 작용소가 된다.

효과 Hamiltonian 의 spectrum 이 하반평면에 위치하게 된다. 즉 모든 고유값 $\mathcal{E}_i$ 에 대해 $\text{Im}\,\mathcal{E}_i \leq 0$ 이 성립한다. 이는 self-energy 의 음허수 부분 $-i\hat{\eta}_0$ 이 spectrum 을 음허수 방향으로 이동시킨 결과이다. 시간 진화 작용소가 다음과 같이 주어진다.

$$
\hat{U}(t) = e^{-i\hat{H}_{\text{eff}}t/\hbar}
$$

이 작용소의 spectrum 이 $e^{-i\mathcal{E}_i t/\hbar}$ 이며 그 크기가 $|e^{-i\mathcal{E}_i t/\hbar}| = e^{\text{Im}\,\mathcal{E}_i \cdot t/\hbar} \leq 1$ 의 형태로 1 이하의 값을 가진다 ($t \geq 0$ 이고 $\text{Im}\,\mathcal{E}_i \leq 0$ 이므로). 즉 시간 진화 작용소의 spectrum 이 단위 원판 내부에 위치하게 된다.

그러나 $\hat{U}(t)$ 가 비-정규 작용소이므로 §5 에서 확인한 결과가 그대로 적용된다. 즉 spectrum 이 단위 원판 내부에 있는 것이 contraction 의 필요 조건이지만 충분 조건이 되지 못한다. Operator norm $\|\hat{U}(t)\|$ 가 spectral radius 보다 큰 값을 가질 수 있으며, 짧은 시간 영역에서 transient amplification 이 발생할 수 있다.

물리적으로 이 transient amplification 이 의미하는 거동이 다음과 같이 나타난다. 짧은 시간 영역에서 시스템의 노름이 일시적으로 1 을 초과하여 증가하는 일이 발생할 수 있으며, 그 후에 점근적으로 spectral radius 의 거동에 따라 감쇠하게 된다. 이러한 거동이 비-Hermitian 양자 시스템에서 등장하는 특징적 현상이며, 표준 양자역학 (Hermitian 시스템) 의 monotonic 감쇠와는 다른 형태로 나타난다.
