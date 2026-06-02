+++
title = "(c) Higher-order Poles and Nilpotent Extraction"
weight = 4
+++

---

### 1. 붕괴와 기저의 상실

시스템에 대수적 퇴화(Algebraic degeneracy)가 발생하면 특성 방정식의 다중근에 의한 대수적 중복도 $\alpha_m$ 에 비해, 독립적인 진성 고유벡터의 수인 기하적 중복도 $\gamma_m$ 이 작아진다. 

$$
\gamma_m < \alpha_m
$$

진성 고유벡터들이 상태 공간을 빈틈없이 채우는 완비적 기저(Complete basis)를 형성하지 못하므로, 이들을 행렬로 구성할 때 계수(Rank)가 결여되어 역행렬을 통한 쌍대 기저(Dual basis)의 도출이 수학적으로 완전히 차단된다. 쌍대 기저 체계가 붕괴함에 따라 사영 연산자를 순수한 1차원 텐서곱 $|u_k\rangle \langle u^{d, k}|$ 의 선형 결합으로 온전히 분해하는 대각화 작업은 불가능해진다.

---

### 2. 비대각화 시스템의 고차 극점 발현 증명

대수적 퇴화가 발생한 국소적 상태 공간은 조단 블록(Jordan block) 구조를 형성한다. 특정 고유값 $\lambda_m$ 에 대응하는 크기 $k \times k$ 의 국소 연산자 부분공간 $\hat{A}_m$ 은 스칼라 고유값과 항등 연산자 $\hat{I}$, 그리고 멱영 작용소 $\hat{N}_m$ 의 선형 결합으로 표현된다.

$$
\hat{A}_m = \lambda_m \hat{I} + \hat{N}_m
$$

여기서 멱영 작용소는 $\hat{N}_m^k = 0$ 의 대수적 불변량을 엄밀하게 만족한다. 이 공간에 대한 국소 레졸번트 $R(z, \hat{A}_m)$ 를 정의하고 역연산을 전개한다.

$$
R(z, \hat{A}_m) = (z\hat{I} - \hat{A}_m)^{-1}
$$
$$
R(z, \hat{A}_m) = \left( z\hat{I} - (\lambda_m \hat{I} + \hat{N}_m) \right)^{-1}
$$
$$
R(z, \hat{A}_m) = \left( (z - \lambda_m)\hat{I} - \hat{N}_m \right)^{-1}
$$

내부 항에서 스칼라 성분 $(z - \lambda_m)$ 을 공통 인수로 묶어 분리한다.

$$
R(z, \hat{A}_m) = \left[ (z - \lambda_m) \left( \hat{I} - \frac{1}{z - \lambda_m}\hat{N}_m \right) \right]^{-1}
$$
$$
R(z, \hat{A}_m) = \frac{1}{z - \lambda_m} \left( \hat{I} - \frac{1}{z - \lambda_m}\hat{N}_m \right)^{-1}
$$

노이만 급수(Neumann series) 전개 공리 $(\hat{I} - \hat{X})^{-1} = \sum_{j=0}^{\infty} \hat{X}^j$ 를 적용하여 역연산자를 무한 다항식 급수로 치환한다. 여기서 대입할 변수는 $\hat{X} = \frac{1}{z - \lambda_m}\hat{N}_m$ 이다.

$$
R(z, \hat{A}_m) = \frac{1}{z - \lambda_m} \sum_{j=0}^{\infty} \left( \frac{1}{z - \lambda_m}\hat{N}_m \right)^j
$$
$$
R(z, \hat{A}_m) = \sum_{j=0}^{\infty} \frac{\hat{N}_m^j}{(z - \lambda_m)^{j+1}}
$$

이 무한 급수를 멱영 작용소의 최대 차수 $k$ 를 기준으로 두 구간으로 분할한다. 인덱스 $j$ 가 $0$ 부터 $k-1$ 까지인 유한 급수 구간과, $j$ 가 $k$ 부터 무한대까지인 나머지 구간으로 나눈다.

$$
R(z, \hat{A}_m) = \sum_{j=0}^{k-1} \frac{\hat{N}_m^j}{(z - \lambda_m)^{j+1}} + \sum_{j=k}^{\infty} \frac{\hat{N}_m^j}{(z - \lambda_m)^{j+1}}
$$

멱영 작용소의 정의에 의해 $\hat{N}_m^k = 0$ 이므로, $j \ge k$ 인 모든 고차항 $\hat{N}_m^j$ 는 대수적으로 완벽하게 영작용소(Zero operator)로 소멸한다. 따라서 뒤쪽의 무한 급수 항은 $0$ 이 되며, 레졸번트는 유한한 차수에서 종결되는 확정된 급수로 축소된다.

$$
R(z, \hat{A}_m) = \sum_{j=0}^{k-1} \frac{\hat{N}_m^j}{(z - \lambda_m)^{j+1}}
$$

극점의 차수와 인덱스를 직관적으로 일치시키기 위해 치환 $n = j + 1$ 을 적용한다. $j=0$ 일 때 $n=1$ 이며, $j=k-1$ 일 때 $n=k$ 이다.

$$
R(z, \hat{A}_m) = \sum_{n=1}^{k} \frac{\hat{N}_m^{n-1}}{(z - \lambda_m)^n}
$$

이 수식은 기하적 결함을 가진 비대각화 연산자가 레졸번트를 형성할 때, 분모의 차수가 $1$ 인 1차 극점을 넘어 결여된 차원의 크기 $k$ 에 도달할 때까지 $(z - \lambda_m)^k$ 형태의 고차 극점(Higher-order pole)을 수학적 필연으로서 발생시킴을 명증하게 증명한다.

---

### 3. 로랑 급수 전개와 작용소의 해석학적 추출

전체 시스템의 레졸번트 $R(z, \hat{A})$ 는 특이점 $\lambda_m$ 근방에서 특수부(Principal part)와 해석적 부분(Analytic part) $\hat{S}_m(z)$ 을 포함하는 일반화된 로랑 급수로 전개된다.

$$
R(z, \hat{A}) = \sum_{n=1}^{k} \frac{\hat{N}_m^{n-1}}{(z - \lambda_m)^n} + \sum_{n=0}^{\infty} (z - \lambda_m)^n \hat{S}_m^{n+1}
$$

복소 평면상에서 $\lambda_m$ 만을 내부에 포함하는 닫힌 경로 $\Gamma_m$ 의 코시 선적분을 통해 멱영 작용소들을 역으로 추출한다. 임의의 정수 $p \ge 0$ 에 대하여 전체 항에 $(z - \lambda_m)^p$ 를 곱하고 선적분 연산을 취한다.

$$
\frac{1}{2\pi i} \oint_{\Gamma_m} (z - \lambda_m)^p R(z, \hat{A}) dz = \frac{1}{2\pi i} \oint_{\Gamma_m} (z - \lambda_m)^p \left( \sum_{n=1}^{k} \frac{\hat{N}_m^{n-1}}{(z - \lambda_m)^n} \right) dz
$$

합 기호와 작용소는 복소 변수 $z$ 와 무관하므로 적분 기호 외부로 분리된다. (해석적 부분은 다항식이 되어 선적분 시 항상 $0$ 이 되므로 소거된다.)

$$
= \sum_{n=1}^{k} \hat{N}_m^{n-1} \left( \frac{1}{2\pi i} \oint_{\Gamma_m} (z - \lambda_m)^{p-n} dz \right)
$$

코시의 유수 정리(Residue theorem)에 의해, 괄호 안의 선적분은 지수 $p - n = -1$ 인 경우(즉, $n = p + 1$ 인 경우)에만 $1$ 이 되고, 그 외의 모든 정수 지수에 대해서는 $0$ 이 된다. 이 직교적 특성에 의해 합 기호 내에서 단 하나의 항 $\hat{N}_m^{(p+1)-1} = \hat{N}_m^p$ 만이 살아남는다.

**1) 일반화된 사영 연산자의 추출 ($p=0$ 대입):**

$$
\frac{1}{2\pi i} \oint_{\Gamma_m} (z - \lambda_m)^0 R(z, \hat{A}) dz = \hat{N}_m^0 = \hat{P}_m
$$

도출된 $\hat{P}_m$ 은 진성 고유벡터 공간을 넘어, 조단 사슬에 묶인 일반화된 고유벡터 전체로 상태를 투영하는 부분 공간 사영 연산자이다.

**2) 멱영 작용소의 추출 ($p=1$ 대입):**

$$
\frac{1}{2\pi i} \oint_{\Gamma_m} (z - \lambda_m)^1 R(z, \hat{A}) dz = \hat{N}_m^1 = \hat{N}_m
$$

도출된 $\hat{N}_m$ 은 사영 연산자에 의해 분리된 공간 내부에서 일반화된 고유벡터를 하위 계층 방향으로 붕괴시키는 동역학적 공간 사상(Shift)을 수행한다.