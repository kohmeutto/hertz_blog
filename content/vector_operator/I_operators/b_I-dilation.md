+++
title = '(b) I-dilation'
weight = 2
+++

---

### 1. I-dilation 의 정의: 내적(확률) 증가 연산자

**1) 직관적 의미**

**이 연산자는 내적이 보존되는 I-유니타리 연산자에 대응되는 쌍대 관계의 연산자이다.**

작용소 $\hat{D}$ 가 어떤 벡터에 작용했을 때 그 벡터의 길이를 줄이지 않으면 이를 I-dilation 이라 부른다. 어떤 벡터 $|\psi\rangle$ 에 작용해도 결과 $\hat{D}|\psi\rangle$ 의 길이가 원래의 길이보다 짧아지지 않는다는 의미이다. 길이가 늘어나거나 또는 원래의 길이와 같은 상태로 유지된다.

이 조건이 작용소의 spectrum 이 어디에 있는지 또는 작용소가 정규인지 여부와는 무관하다. 단지 벡터의 길이가 어떻게 변하는지에 대한 조건이며, spectrum 의 위치나 정규성은 정의에 들어가지 않는다.

본 작용소가 표준 inner product (즉 metric operator 가 $\hat{I}$ 인 case) 의 기준에서 norm 의 증가를 짚는 작용소이므로 I-dilation 이라 부른다. 일반화된 metric ($\hat{G}$ 또는 $\hat{J}$) 의 기준에서의 dilation 작용소가 별도 chapter 에서 다뤄진다.

**2) 수식 형태**

벡터의 길이를 노름 $\|\cdot\|$ 으로 나타내면 I-dilation 의 조건이 다음 부등식의 형태로 표현된다.

$$
\|\hat{D}|\psi\rangle\| \geq \|\psi\| \quad \text{for all } |\psi\rangle
$$

좌변이 작용소 $\hat{D}$ 가 작용한 후 벡터의 노름을 나타내고, 우변이 원래 벡터의 노름을 나타낸다. 모든 벡터 $|\psi\rangle$ 에 대해 좌변이 우변보다 크거나 같아야 한다는 조건이다.

**3) Operator norm 의 역 으로의 표현**

I-contraction 의 경우 작용소가 벡터를 가장 크게 늘리는 비율 (supremum) 이 1 이하의 조건이었다. I-dilation 의 경우 작용소가 벡터를 가장 작게 줄이는 비율 (infimum) 이 1 이상이 되어야 한다.

작용소 $\hat{D}$ 의 minimal operator norm 을 다음과 같이 정의한다.

$$
m(\hat{D}) := \inf_{|\psi\rangle \neq 0} \frac{\|\hat{D}|\psi\rangle\|}{\|\psi\|}
$$

이 양이 모든 비영 벡터에 대해 작용 후 노름을 원래 노름으로 나눈 값을 계산하고, 그 값들의 infimum 을 취한 것이다. 즉 작용소 $\hat{D}$ 가 어떤 벡터를 가장 작게 줄일 때조차 그 결과의 노름이 원래 노름의 몇 배 이상인지를 나타내는 값이다.

이 정의를 사용하면 I-dilation 의 조건이 다음과 동등한 단일 부등식으로 표현된다.

$$
m(\hat{D}) \geq 1
$$

작용소가 벡터를 가장 작게 줄일 때조차 그 결과의 노름이 원래 길이의 1배 이상이라는 의미이다. 따라서 어떤 벡터도 원래의 길이보다 짧아지지 않게 된다.

**4) Contraction 과의 쌍대 관계**

I-dilation 작용소 $\hat{D}$ 가 가역이라면 (invertible) 그 역작용소 $\hat{D}^{-1}$ 가 I-contraction 이 된다. 이 사실이 두 framework 의 쌍대 관계를 직접 보여준다.

proof) I-dilation 의 조건 $\|\hat{D}|\psi\rangle\| \geq \|\psi\|$ 에서 $|\psi\rangle = \hat{D}^{-1}|\phi\rangle$ 의 치환을 적용하면 $\|\hat{D}\hat{D}^{-1}|\phi\rangle\| \geq \|\hat{D}^{-1}|\phi\rangle\|$ 즉 $\|\phi\| \geq \|\hat{D}^{-1}|\phi\rangle\|$. 본 부등식이 $\hat{D}^{-1}$ 의 I-contraction 의 조건과 정확히 일치한다.

따라서 I-contraction 과 I-dilation 이 작용소의 역 관계로 자연스럽게 연결된다.

---

### 2. 지수화 & Lower-Hermitian

I-유니타리 연산자와 마찬가지로 지수 표현을 사용하여, **Lower-Hermitian** 연산자를 정의한다.

**1) 지수 표현**

$$
\hat{D} = \sum_{k=0}^{\infty} \frac{(i\hat{H}_\downarrow)^k}{k!} = e^{i\hat{H}_\downarrow}
$$

proof)

spectral 분해에서 출발한다. I-dilation 의 각 고유값 $\lambda_n$ 이 단위 원판 외부 또는 경계에 위치하므로 $|\lambda_n| \geq 1$ 이 성립한다. 0 이 아닌 $\lambda_n$ 을 극형식으로 풀면 $\lambda_n = r_n e^{i\theta_n}$ 의 형태가 되며, 여기서 $r_n \geq 1$ 이고 $\theta_n \in \mathbb{R}$ 이다. $r_n$ 이 1 이상인 양수이므로 $r_n = e^{\kappa_n}$ 의 형태로 다시 쓸 수 있으며, 이때 새 매개변수 $\kappa_n$ 이 0 이상의 실수이다.

$$
\lambda_n = e^{\kappa_n} e^{i\theta_n} = e^{i(\theta_n - i\kappa_n)} = e^{i\mu_n}, \quad \mu_n = \theta_n - i\kappa_n
$$

새 매개변수 $\mu_n$ 의 허수부가 $\text{Im}\,\mu_n = -\kappa_n \leq 0$ 이므로 $\mu_n$ 이 하반평면 (실수 직선 포함) 의 점에 해당한다. spectral 분해에 대입하면 다음 형태가 된다.

$$
\hat{D} = \sum_n e^{i\mu_n} |v_n\rangle\langle v^n|, \quad \mu_n \in \text{closed lower half-plane}
$$

각 스칼라 $e^{i\mu_n}$ 이 스칼라 지수 함수이며, 그 정의가 Taylor 급수의 무한 합으로 주어진다.

$$
e^{i\mu_n} = \sum_{k=0}^{\infty} \frac{(i\mu_n)^k}{k!}
$$

이 Taylor 급수를 spectral 분해에 대입하고 합의 순서를 바꾸면 다음과 같은 형태로 정리된다.

$$
\hat{D} = \sum_{k=0}^{\infty} \frac{i^k}{k!} \sum_n \mu_n^k |v_n\rangle\langle v^n|
$$

안쪽의 합 $\sum_n \mu_n^k |v_n\rangle\langle v^n|$ 이 어떤 작용소의 $k$ 거듭제곱과 같은 형태를 가지고 있다. 이를 활용하기 위해 다음 작용소를 정의한다. 이를 **Lower-Hermitian** 이라고 하자.

$$
\hat{H}_\downarrow := \sum_n \mu_n |v_n\rangle\langle v^n|
$$

거듭제곱의 결과를 이 정의에 적용하면 다음 등식이 성립한다.

$$
\hat{H}_\downarrow^k = \sum_n \mu_n^k |v_n\rangle\langle v^n|
$$

이를 위의 합 표현에 대입하면 작용소 $\hat{H}_\downarrow$ 가 다음과 같이 표현된다.

$$
\hat{D} = \sum_{k=0}^{\infty} \frac{(i\hat{H}_\downarrow)^k}{k!} = e^{i\hat{H}_\downarrow}
$$

**2) Lower-Hermitian $\hat{H}_\downarrow$ 의 Cartesian decomposition**

매개변수 $\mu_n$ 이 복소수 (하반평면) 이므로 $\hat{H}_\downarrow$ 가 일반적으로 Hermitian 이 아니다. 본 작용소를 Hermitian 부분과 anti-Hermitian 부분의 합으로 분해할 수 있다. 본 분해를 Cartesian decomposition 이라 부른다.

$$
\hat{H}_\downarrow = \hat{H}_1 + i\hat{H}_2
$$

여기서 $\hat{H}_1 := (\hat{H}_\downarrow + \hat{H}_\downarrow^\dagger)/2$ 가 Hermitian (실수부) 이고, $\hat{H}_2 := (\hat{H}_\downarrow - \hat{H}_\downarrow^\dagger)/(2i)$ 도 Hermitian (허수부의 계수) 이다.

**3) Upper-Hermitian 과의 쌍대 관계**

I-contraction 의 generator 인 Upper-Hermitian $\hat{H}_\uparrow$ 와 I-dilation 의 generator 인 Lower-Hermitian $\hat{H}_\downarrow$ 가 서로 부호 반대의 쌍대 관계를 가진다. 즉 같은 generator $\hat{H}_\uparrow$ 의 부호 반대 $-\hat{H}_\uparrow$ 가 Lower-Hermitian 의 form 이 된다. 본 사실이 I-contraction 과 I-dilation 의 작용소 측의 역 관계 ($\hat{D} = \hat{T}^{-1}$) 와 일치한다.

---

### 3. spectrum: 하반평면 ↔ 단위 원판 외부

I-dilation $\hat{D}$ 와 generator $\hat{H}_\downarrow$ 의 spectrum 위치 사이의 관계가 직접적으로 따라 나온다. 이 관계를 정확히 풀어 짚어 본다.

$$
\hat{H}_\downarrow = \sum_n \mu_n |v_n\rangle\langle v^n|, \quad \hat{D} = \sum_n e^{i\mu_n} |v_n\rangle\langle v^n|
$$

I-dilation 의 조건이 $m(\hat{D}) \geq 1$ 이며, 모든 고유값의 크기가 1 이상이 되어야 한다. 따라서 I-dilation 인 작용소의 모든 고유값이 1 이상의 값을 가지게 된다.

$$
|\lambda_n| \geq 1
$$

$\lambda_n = e^{i\mu_n}$ 에 의해 각 고유값의 크기가 $|\lambda_n| = e^{-\text{Im}\,\mu_n}$ 으로 주어지므로, 위의 조건이 다음과 같은 형태로 바뀐다.

$$
e^{-\text{Im}\,\mu_n} \geq 1 \implies \text{Im}\,\mu_n \leq 0
$$

즉 $\hat{H}_\downarrow$ 의 모든 고유값이 하반평면 (실수 직선 포함) 에 위치하게 된다. Generator 의 spectrum 위치와 작용소의 spectrum 위치 사이의 대응을 세 가지 경계 케이스로 정리하면 다음과 같다.

| $\hat{H}_\downarrow$ spectrum | 작용소 $\hat{D} = e^{i\hat{H}_\downarrow}$ spectrum |
|---|---|
| 실수 직선 ($\text{Im}\,\mu_n = 0$) | 단위 원 위 ($\vert\lambda_n\vert = 1$) |
| 하반평면 strict ($\text{Im}\,\mu_n < 0$) | 단위 원판 strict 외부 ($\vert\lambda_n\vert > 1$) |
| 하반평면 경계 (혼합) | 일부 원 위, 일부 원 외부 |

---

### 4. I-contraction 과 I-dilation 의 통합 정리

세 작용소 (I-unitary, I-contraction, I-dilation) 의 generator 의 spectrum 의 위치와 작용소의 spectrum 의 위치 사이의 대응이 다음과 같이 자리잡힌다.

| 작용소 | Generator | Generator spectrum | 작용소 spectrum |
|---|---|---|---|
| I-unitary $\hat{U}$ | Hermitian $\hat{H}$ | 실수 직선 | 단위 원 위 |
| I-contraction $\hat{T}$ | Upper-Hermitian $\hat{H}_\uparrow$ | 상반 평면 | 단위 원판 내부 |
| I-dilation $\hat{D}$ | Lower-Hermitian $\hat{H}_\downarrow$ | 하반 평면 | 단위 원판 외부 |

세 작용소가 같은 form 의 지수 표현 ($\hat{T} = e^{i\hat{Z}}$, $\hat{Z}$ 가 각각의 generator) 으로 generator 와 연결되며, generator 의 spectrum 위치 (실수 직선, 상반 평면, 하반 평면) 가 작용소의 종류 (unitary, contraction, dilation) 를 결정한다. 본 framework 이 표준 inner product 의 기준에서의 작용소 분류의 통합 구조이다.
