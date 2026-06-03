+++
title = "(b) Diagonalizable"
weight = 2
+++

---

### 1. 1차 단순 극점의 추출

레졸번트 연산자 $\hat{R}(z, \hat{A})$의 특이점 $z = \lambda_m$ 근방에서의 로랑 급수(Laurent series) 전개는 다음과 같이 정의된다.

$$
R(z, \hat{A}) = \sum_{k\ge2}\frac{\hat{C}_{-k}}{(z-\lambda_m)^k} + \frac{\hat{C}_{-1}}{z-\lambda_m} + \sum_{k\ge0}\hat{C}_k(z-\lambda_m)^k
$$

여기서 $k_m$은 고윳값 $\lambda_m$에 대응하는 공간의 멱영 지수(Index of nilpotency)이다. 임의의 정수 $n$에 대한 전개 계수 $\hat{C}_n$은 닫힌 경로 $\Gamma_m$에 대한 코시 적분 공식으로 산출된다.

$$
\hat{C}_n = \frac{1}{2\pi i}\oint_{\Gamma}\frac{dz}{z-\lambda_m}\frac{R(z)}{(z-\lambda_m)^{n}}
$$

위 급수 전개에서 주부(Principal part)의 2차 이상 극점 성분은 시스템의 결함(Defect)을 나타내며, 본 장에서는 대각화 가능한 성분을 추출하는 1차 단순 극점(Simple pole)의 해석에 집중한다.

---

### 2. 1차 단순극점 $\implies$ 사영 연산자(Projection operator) 

로랑 급수의 유수(Residue)에 해당하는 계수 $\hat{C}_{-1}$은 고윳값 $\lambda_m$ 공간으로의 스펙트럼 사영 연산자 $\hat{P}_m$으로 정의된다.

$$
\hat{P}_m = \hat{C}_{-1} = \frac{1}{2\pi i}\oint_{\Gamma_m} dz \, R(z,\hat{A})
$$

proof)

사영 연산자가 대수학적으로 성립하기 위한 필수 조건인 멱등성(Idempotence, $\hat{P}_m^2 = \hat{P}_m$)과 직교성(Orthogonality, $\hat{P}_m \hat{P}_l = \hat{0}, m \neq l$)은 레졸번트 항등식 $\hat{R}(z) - \hat{R}(w) = (w - z)\hat{R}(z)\hat{R}(w)$을 통해  증명된다.

첫째, 멱등성을 증명하기 위해 특이점 $\lambda_m$을 둘러싸는 두 개의 동심 폐곡선 $\Gamma$와 $\Gamma'$를 설정한다. 단, $\Gamma$는 $\Gamma'$를 완전히 내포한다.

$$
\hat{P}_m^2 = \left( \frac{1}{2\pi i} \oint_{\Gamma} \hat{R}(z) dz \right) \left( \frac{1}{2\pi i} \oint_{\Gamma'} \hat{R}(w) dw \right) = \frac{1}{(2\pi i)^2} \oint_{\Gamma} dz dw \oint_{\Gamma'} \hat{R}(z)\hat{R}(w) 
$$

레졸번트 항등식을 대입하여 적분을 분리한다.

$$
\hat{P}_m^2 = \frac{1}{(2\pi i)^2} \oint_{\Gamma} \oint_{\Gamma'}dw dz \frac{\hat{R}(z)}{w - z} - \frac{1}{(2\pi i)^2} \oint_{\Gamma'} \oint_{\Gamma} dz dw \frac{\hat{R}(w)}{w - z} 
$$

경로 $\Gamma'$ 내부에 $z$가 존재하지 않으므로 코시 적분 정리에 의해 첫 번째 항은 소멸한다. 두 번째 항에서 경로 $\Gamma$ 내부에 $w$가 존재하므로 $\oint_{\Gamma} \frac{dz}{w - z} = -\oint_{\Gamma} \frac{dz}{z - w} = -2\pi i$가 성립한다.

$$
\hat{P}_m^2 = -\frac{1}{(2\pi i)^2} \oint_{\Gamma'} dw \hat{R}(w) (-2\pi i)  = \frac{1}{2\pi i} \oint_{\Gamma'} dw \hat{R}(w)  = \hat{P}_m
$$

둘째, 직교성을 증명하기 위해 서로 다른 특이점 $\lambda_m$과 $\lambda_l$을 각각 둘러싸며 교차하지 않는 폐곡선 $\Gamma_m$과 $\Gamma_l$을 설정한다.

$$
\hat{P}_m \hat{P}_l = \frac{1}{(2\pi i)^2} \oint_{\Gamma_m} \oint_{\Gamma_l} dw dz \frac{\hat{R}(z) - \hat{R}(w)}{w - z}
$$

두 적분 경로가 완전히 분리되어 있으므로, $z$는 $\Gamma_l$ 내부에 존재하지 않고 $w$는 $\Gamma_m$ 내부에 존재하지 않는다. 따라서 코시 적분 정리에 의해 두 항 모두 자명하게 영연산자 $\hat{0}$으로 수렴한다.

---

### 3. 사영 연산자에 의한 대각화 성분과 비대각 성분의 대수적 분리

사영 연산자 $\hat{P}_m$은 단일 고윳값 $\lambda_m$에 대응하는 일반화된 고유공간 전체를 투영한다. 이 닫힌 공간 내부에서 시스템 연산자 $\hat{A}$가 작용할 때, 대각화가 가능한 반단순(Semisimple) 성분과 대각화가 불가능한 비대각(Off-diagonal) 성분으로 본질적인 대수적 분리가 발생한다.

$$
\hat{A}\hat{P}_m=\lambda_m\hat{P}_m+\hat{C}_{-2}
$$

- $\lambda_m\hat{P}_m$: 대각화 가능 성분
- $\hat{C}_{-2}$: 대각화 불가능 성분, 멱영 연산자

proof)

연산자 $\hat{A}=z\hat{R}(z)-\hat{I}$와 사영 연산자 $\hat{P}_m$의 곱을 적분식으로 전개해 보자. 

$$
\hat{A} \hat{P}_m = \frac{1}{2\pi i} \oint_{\Gamma_m} dz \, \hat{A} \hat{R}(z) = \frac{1}{2\pi i} \oint_{\Gamma_m} dz \, z \hat{R}(z) - \frac{1}{2\pi i} \oint_{\Gamma_m} dz \, \hat{I} 
$$

항등 연산자 $\hat{I}$의 닫힌 경로 적분은 0이므로 소거된다. 남은 적분항에 레졸번트의 로랑 급수 전개식을 대입한다. 적분 과정에서 $z = (z - \lambda_m) + \lambda_m$으로 분할하여 전개하면 유수 정리(Residue theorem)에 의해 $(z-\lambda_m)^{-1}$ 차수의 계수만이 보존된다.

$$
\frac{1}{2\pi i} \oint_{\Gamma_m} dz \, \hat{I} = 0
$$

$$
\frac{1}{2\pi i} \oint_{\Gamma_m} dz \, z \hat{R}(z) = \frac{1}{2\pi i} \oint_{\Gamma_m} dz \, \{(z-\lambda_m)+\lambda_m\} \hat{R}(z) = \lambda_m \hat{P}_m + \hat{C}_{-2}
$$

따라서,

$$
\hat{A} \hat{P}_m = \lambda_m \hat{P}_m + \hat{C}_{-2}
$$

여기서 $\hat{C}_{-2}$는 2차 극점 계수로서, 이것의 의미를 살펴보자. $\hat{P}_m$의 경우, 제곱을 하여 사영 연사자 임을 도출한것처럼, $C_{-2}$를 제곱해 본다. 특이점 $\lambda_m$을 둘러싸는 두 폐곡선 $\Gamma$와 $\Gamma'$ ($\Gamma$가 $\Gamma'$를 내포)에 대하여 $\hat{C}_{-2}^2$를 전개한다.

$$
\hat{C}_{-2}^2 = \frac{1}{(2\pi i)^2} \oint_{\Gamma} \oint_{\Gamma'} dz dw (z-\lambda_m)(w-\lambda_m) \hat{R}(z)\hat{R}(w)
$$

레졸번트 항등식을 대입하여 적분을 분리한다.

$$
\hat{C}_{-2}^2 = \frac{1}{(2\pi i)^2} \oint_{\Gamma} dz dw \oint_{\Gamma'} \frac{(z-\lambda_m)(w-\lambda_m)}{w - z} \left( \hat{R}(z) - \hat{R}(w) \right)
$$

앞선 사영 연산자의 멱등성 증명과 동일한 코시 적분 정리 절차를 거치면, $\Gamma'$에 대한 $w$ 적분에서 경로 내부에 위치한 극점 $z$에 의해 유수(Residue)가 발생한다.

$$
\hat{C}_{-2}^2 = \frac{1}{2\pi i} \oint_{\Gamma} (z-\lambda_m)^2 \hat{R}(z) dz
$$

위 적분식은 로랑 급수의 계수 공식 정의에 의해 정확히 3차 극점의 계수 $\hat{C}_{-3}$과 일치한다. 즉, $\hat{C}_{-2}^2 = \hat{C}_{-3}$가 성립한다. 이 적분 논리를 수학적 귀납법으로 임의의 정수 $k$로 확장하면 다음의 불변량이 도출된다.

$$
\hat{C}_{-2}^k = \hat{C}_{-(k+1)}
$$

로랑 급수의 주부(Principal part)는 유한 차원 시스템에서 무한히 전개될 수 없고 반드시 종결된다($n > k_m$일 때 $\hat{C}_{-n} = \hat{0}$). 따라서 **멱영 연산자 이다.**

---





**1) 이산 스팩트럼**

$$
\hat{A}_S = \sum_{m} \lambda_m \hat{P}_m
$$

**2) 연속 스팩트럼**

$$
\hat{A}_S = \int_{\sigma(\hat{A})} \lambda d\hat{P}(\lambda)
$$

 이를 통해 전체 연산자 $\hat{A}$의 대각화 가능 성분은 다음과 같이 스펙트럼 분해(Spectral decomposition)로 표현된다.


### 3. 상태 벡터의 추출

---





이후의 장에서는 이 계수들이 각각 시스템 내에서 어떠한 대수학적 작용을 수행하는지 상술한다.







---

---

### 1. 스펙트럼의 대수적 전개와 사영 연산자 표기

**1) 이산 스펙트럼**

완비적 기저(Complete basis)를 형성하는 진성 고유벡터 $|\lambda_k\rangle$ 와 이에 직교하는 쌍대 기저(Dual basis) $\langle \lambda^{ k}|$ 를 이용해 사영 연산자 $\hat{P}_k$ 를 다음과 같이 정의한다.

$$
\hat{P}_k = |\lambda_k\rangle \langle \lambda^{ k}|
$$

이 사영 연산자를 통해 연산자 $\hat{A}$ 와 항등 연산자 $\hat{I}$ 의 스펙트럼 분해는 다음과 같이 구성된다.

$$
\hat{A} = \sum_k \lambda_k \hat{P}_k = \sum_k \lambda_k |\lambda_k\rangle \langle \lambda^{ k}|
$$

$$
\hat{I} = \sum_k \hat{P}_k = \sum_k |\lambda_k\rangle \langle \lambda^{ k}|
$$

이를 통해 유도된 레졸번트 $R(z, \hat{A}) = (z\hat{I} - \hat{A})^{-1}$ 는 사영 연산자의 선형 결합으로 전개되며, 복소 평면 상에서 고립된 1차 극점(Simple pole)만을 형성한다.

$$
R(z, \hat{A}) = \sum_k \frac{1}{z - \lambda_k} \hat{P}_k = \sum_k \frac{1}{z - \lambda_k} |\lambda_k\rangle \langle \lambda^{ k}|
$$

**2) 연속 스펙트럼**

경계 조건의 확장으로 고유값이 이산적 점이 아닌 연속적 대역 $\sigma_c$ 를 형성할 때, 미소 상태 구간 $d\nu$ 에 대한 미분 사영 연산자(Differential projection operator) $d\hat{P}(\nu)$ 를 도입한다.

$$
d\hat{P}(\nu) = |\lambda(\nu)\rangle \langle \lambda^d(\nu)| d\nu
$$

연산자 $\hat{A}$ 와 항등 연산자 $\hat{I}$ 는 이 미분 사영 연산자의 연속 적분 형태로 전개된다.

$$
\hat{A} = \int_{\sigma_c} \lambda(\nu) d\hat{P}(\nu) = \int_{\sigma_c} d\nu \lambda(\nu) |\lambda(\nu)\rangle \langle \lambda^d(\nu)| 
$$

$$
\hat{I} = \int_{\sigma_c} d\hat{P}(\nu) = \int_{\sigma_c} d\nu |\lambda(\nu)\rangle \langle \lambda^d(\nu)|
$$

이에 대응하는 레졸번트는 고립된 극점이 아니라, 복소 평면 상에 연속적인 분기 절단(Branch cut) 또는 특이선(Singular line)을 형성하며 다음과 같이 미분 사영 연산자의 적분으로 표현된다.

$$
R(z, \hat{A}) = \int_{\sigma_c} \frac{d\hat{P}(\nu)}{z - \lambda(\nu)} = \int_{\sigma_c} \frac{d\nu}{z - \lambda(\nu)} |\lambda(\nu)\rangle \langle \lambda^d(\nu)| 
$$

---

### 2. 코시 선적분과 사영 연산자(Projection Operator) 도출

**1) 복소해석학의 코시 적분 공식(Cauchy integral formula)**

복소 변수 $z$ 에 대한 스칼라 함수 $f(z)$ 가 닫힌 경로 $\Gamma$ 내부에서 해석적일 때, 레졸번트 $R(z, \hat{A})$ 를 적분핵(Integral kernel)으로 도입하여 연산자 함수 $f(\hat{A})$ 를 정의한다.

$$
f(\hat{A}) = \frac{1}{2\pi i} \oint_{\Gamma} dz f(z) R(z, \hat{A}) 
$$

비유계 연산자에 다항식 급수를 직접 적용하면 정의역의 연쇄적 축소가 발생하지만, 위 공식을 활용하면 연산자 함수를 레졸번트 집합 상의 선적분으로 치환할 수 있다. 레졸번트 $R(z, \hat{A})$ 는 닫힌 경로 $\Gamma$ 위에서 유계 연산자이므로 수렴성 문제나 정의역 축소 모순이 발생하지 않는다.

**2) 이산 스펙트럼에서의 고립 공간 추출**

특정 고유 공간으로의 사영 연산자 $\hat{P}_m$ 은 단일 극점 $\lambda_m$ 만을 둘러싼 닫힌 경로 $\Gamma_m$ 의 코시 선적분을 통해 추출된다. 코시의 유수 정리(Residue theorem)를 적용하면 $\Gamma_m$ 내부의 극점($k=m$)에 대한 선적분 값은 1이 되고, 외부의 극점은 0이 된다. 이는 크로네커 델타 $\delta^k_m$ 과 동치이다.

$$
\hat{P}_m = \sum_k \left( \frac{1}{2\pi i} \oint_{\Gamma_m} \frac{dz}{z - \lambda_k} \right) \hat{P}_k = \sum_k \delta^k_m \hat{P}_k = \hat{P}_m
$$

**3) 연속 스펙트럼에서의 구간 범위(Range) 국소화**

전체 연속 스펙트럼 $\sigma_c$ 내에서 특정 구간 $\Delta = [\nu_1, \nu_2]$ 에 해당하는 상태 공간만을 대수적으로 분리(Filtering)하기 위해, 해당 연속 특이선 구간만을 둘러싸는 닫힌 경로 $\Gamma_\Delta$ 를 설정하고 선적분을 수행한다. 

$$
\hat{P}_\Delta = \frac{1}{2\pi i} \oint_{\Gamma_\Delta} R(z, \hat{A}) dz = \frac{1}{2\pi i} \oint_{\Gamma_\Delta} dz \left( \int_{\sigma_c} \frac{d\nu}{z - \lambda(\nu)} |\lambda(\nu)\rangle \langle \lambda^d(\nu)| \right)
$$

복소 변수 $z$ 에 대한 선적분과 실수 변수 $\nu$ 에 대한 공간 적분의 순서를 교환하여, 코시 적분항을 분리한다.

$$
\hat{P}_\Delta = \int_{\sigma_c} d\nu |\lambda(\nu)\rangle \langle \lambda^d(\nu)| \left[ \frac{1}{2\pi i} \oint_{\Gamma_\Delta} \frac{dz}{z - \lambda(\nu)} \right]
$$

대괄호 안의 복소 선적분은 유수 정리에 의해 대수학적 지시 함수(Indicator function)의 역할을 수행한다. 연속 변수에 의한 고유값 $\lambda(\nu)$ 가 닫힌 경로 $\Gamma_\Delta$ 내부(즉, 구간 $\Delta$)에 존재하면 적분값은 1이 되고, 구간 외부에 존재하면 특이점이 없으므로 0이 된다.

이 직교적 필터링 거동에 의해 바깥쪽 공간 적분 $\int_{\sigma_c}$ 의 범위는 전체 스펙트럼 $\sigma_c$ 에서 목표로 한 국소 구간 $\Delta$ 로 축소된다.

$$
\hat{P}_\Delta = \int_{\Delta} d\nu (1) |\lambda(\nu)\rangle \langle \lambda^d(\nu)| = \int_{\Delta} d\hat{P}(\nu)
$$

이 계산 과정을 통해 특이선 전체를 덮고 있던 연속 레졸번트가 지정된 스펙트럼 대역 $\Delta$ 의 연속 사영 연산자로 환원됨이 증명된다.

---

### 3. 상태 벡터의 추출

도출된 이산 사영 연산자 $\hat{P}_m$ 에 임의의 시험 벡터 $|\psi\rangle$ 를 입력하여 작용 결과를 확인한다.

$$
\hat{P}_m |\psi\rangle = \left( |\lambda_m\rangle \langle \lambda^{ m}| \right) |\psi\rangle = |\lambda_m\rangle \langle \lambda^{ m} | \psi \rangle
$$

좌측 쌍대 기저와 우측 상태 벡터의 내적 연산 $\langle \lambda^{ m} | \psi \rangle$ 의 결과는 복소수 스칼라 값 $c^m$ 으로 산출된다.

$$
\hat{P}_m |\psi\rangle = c^m |\lambda_m\rangle
$$

---

### 4. 대각화 가능성과 1차 극점(Simple Pole)의 보존

연산자 대수학에서 특성 방정식의 다중근(대수적 중복도)과 레졸번트의 극점 차수(Order of pole)는 동일한 개념이 아니다. **대각화가 가능한 시스템에서는 고유값이 아무리 중복되더라도, 레졸번트는 해석학적으로 필연적인 1차 극점(Simple pole)만을 유지**한다.

**1) 대수적 중복도와 사영 연산자의 차원 확장**

특성 방정식에서 다중근이 발생하여 대수적 중복도(Algebraic multiplicity)가 $\alpha_m > 1$ 인 퇴화된 고유값 $\lambda_m$ 이 존재한다고 가정한다. 시스템이 대각화 가능 조건을 만족한다면, 이는 해당 고유값에 대응하는 독립적인 진성 고유벡터의 수인 기하적 중복도(Geometric multiplicity) $\gamma_m$ 이 대수적 중복도와 일치($\gamma_m = \alpha_m$)함을 의미한다.

이 조건 하에서, 퇴화된 고유값 $\lambda_m$ 에 대응하는 국소적 상태 공간은 $\gamma_m$ 개의 상호 직교하는 쌍대 기저 쌍 $\{|u_{m, j}\rangle, \langle u^{ m, j}|\}_{j=1}^{\gamma_m}$ 으로 온전히 채워진다. 연산자의 스펙트럼 분해 식에서 해당 고유 공간에 대한 전체 사영 연산자 $\hat{P}_m$ 은 단일 차원 사영들의 선형 결합으로 구성된다.

$$
\hat{P}_m = \sum_{j=1}^{\gamma_m} |u_{m, j}\rangle \langle u^{ m, j}|
$$

**2) 레졸번트의 로랑 급수 전개와 극점의 차수 확정**

이 확장된 사영 연산자를 레졸번트 $R(z, \hat{A}) = (z\hat{I} - \hat{A})^{-1}$ 의 정의에 대입하여, 복소 평면상 특이점 $z = \lambda_m$ 근방에서의 해석학적 거동을 전개한다.

$$
R(z, \hat{A}) = \frac{\hat{P}_m}{z - \lambda_m} + \sum_{\lambda_k \neq \lambda_m} \frac{\hat{P}_k}{z - \lambda_k}
$$

위 식의 두 번째 항은 $z = \lambda_m$ 근방에서 특이점이 없는 해석 함수 $\hat{S}(z)$ 로 취급할 수 있으므로, 식을 다음과 같이 축약한다.

$$
R(z, \hat{A}) = \frac{\hat{P}_m}{z - \lambda_m} + \hat{S}(z)
$$

유도된 수식은 스펙트럼 이론의 핵심적인 해석학적 성질을 증명한다. 시스템의 기하적 완비성이 보장되는 한, 고유값의 대수적 퇴화(중복)는 복소 평면상에서 분모의 차수를 2차 이상으로 높이는 고차 극점(Higher-order pole)을 절대 형성하지 않는다.

분모는 수학적으로 $(z - \lambda_m)^1$ 이라는 1차 극점을 확정적으로 유지하며, 고유값의 중복도는 오직 분자에 위치한 사영 연산자 $\hat{P}_m$ 의 대수적 차원(Rank)을 $\gamma_m$ 으로 확장하는 데에만 기여한다.

---

### 5. 예제: 비정규 대각화 가능 연산자

2차원 비정규 행렬 연산자 $\hat{A}$ 가 대각화 가능성을 가질 때, 스펙트럼을 추출하는 과정을 대수학적 방법과 해석학적 방법으로 교차 검증한다.

$$
\hat{A} = \begin{bmatrix} 1 & 2 \\ 0 & 3 \end{bmatrix}
$$

**1) 특성 방정식을 이용한 풀이**

동차 방정식의 행렬식이 0이 되는 조건을 통해 고유값을 산출한다.

$$
\det(\hat{A} - \lambda\hat{I}) = \det \begin{bmatrix} 1 - \lambda & 2 \\ 0 & 3 - \lambda \end{bmatrix} = (1 - \lambda)(3 - \lambda) = 0
$$

산출된 고유값은 $\lambda_1 = 1$, $\lambda_2 = 3$ 이다. 각 고유값에 대한 고유 방정식 $(\hat{A} - \lambda_k\hat{I})|\lambda_k\rangle = 0$ 을 전개한다.

*(1) $\lambda_1=1$ 일 때:*

$$
\begin{bmatrix} 0 & 2 \\ 0 & 2 \end{bmatrix} \begin{bmatrix} x \\ y \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \end{bmatrix} \implies 2y = 0 \implies |\lambda_1\rangle = \begin{bmatrix} 1 \\ 0 \end{bmatrix}
$$

*(2) $\lambda_2=3$ 일 때:*

$$
\begin{bmatrix} -2 & 2 \\ 0 & 0 \end{bmatrix} \begin{bmatrix} x \\ y \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \end{bmatrix} \implies -2x + 2y = 0 \implies |\lambda_2\rangle = \begin{bmatrix} 1 \\ 1 \end{bmatrix}
$$

**2) 레졸번트를 이용한 풀이**

대수적 고유 방정식을 배제하고, 연산자의 레졸번트 $R(z, \hat{A}) = (z\hat{I} - \hat{A})^{-1}$ 의 복소 선적분만을 이용하여 동일한 고유 상태를 직접 계산하여 추출한다. 역행렬을 계산하여 레졸번트를 전개한다.

$$
R(z, \hat{A}) = \begin{bmatrix} z - 1 & -2 \\ 0 & z - 3 \end{bmatrix}^{-1} = \frac{1}{(z - 1)(z - 3)} \begin{bmatrix} z - 3 & 2 \\ 0 & z - 1 \end{bmatrix}
$$

복소 평면 상의 특이점 $\lambda_1 = 1$ 과 $\lambda_2 = 3$ 에 대한 코시 선적분을 통해 사영 연산자를 도출한다. 1차 극점이므로 극한 연산 $\lim_{z \to \lambda} (z - \lambda) R(z, \hat{A})$ 을 적용하여 유수(Residue)를 산출한다.

*(1) $\lambda_1=1$ 에 대한 사영 연산자 $\hat{P}_1$:*

$$
\hat{P}_1 = \frac{1}{2\pi i}\oint_{\Gamma_1} dz R(z,\hat{A}) = \lim_{z \to 1} (z - 1) R(z, \hat{A}) = \lim_{z \to 1} \frac{1}{z - 3} \begin{bmatrix} z - 3 & 2 \\ 0 & z - 1 \end{bmatrix}
$$

$$
\hat{P}_1 = -\frac{1}{2} \begin{bmatrix} -2 & 2 \\ 0 & 0 \end{bmatrix} = \begin{bmatrix} 1 & -1 \\ 0 & 0 \end{bmatrix}
$$

임의의 시험 벡터를 입력하여 고유 상태를 추출한다.

$$
\hat{P}_1 \begin{bmatrix} a \\ b \end{bmatrix} = \begin{bmatrix} 1 & -1 \\ 0 & 0 \end{bmatrix} \begin{bmatrix} a \\ b \end{bmatrix} = \begin{bmatrix} a-b \\ 0 \end{bmatrix} = (a-b)\begin{bmatrix} 1 \\ 0 \end{bmatrix} \implies |\lambda_1\rangle = \begin{bmatrix} 1 \\ 0 \end{bmatrix}
$$

*(2) $\lambda_2=3$ 에 대한 사영 연산자 $\hat{P}_2$:*

$$
\hat{P}_2 = \frac{1}{2\pi i}\oint_{\Gamma_2} dz R(z,\hat{A}) = \lim_{z \to 3} (z - 3) R(z, \hat{A}) = \lim_{z \to 3} \frac{1}{z - 1} \begin{bmatrix} z - 3 & 2 \\ 0 & z - 1 \end{bmatrix}
$$

$$
\hat{P}_2 = \frac{1}{2} \begin{bmatrix} 0 & 2 \\ 0 & 2 \end{bmatrix} = \begin{bmatrix} 0 & 1 \\ 0 & 1 \end{bmatrix}
$$

동일하게 시험 벡터를 입력하여 투영한다.

$$
\hat{P}_2 \begin{bmatrix} a \\ b \end{bmatrix} = \begin{bmatrix} 0 & 1 \\ 0 & 1 \end{bmatrix} \begin{bmatrix} a \\ b \end{bmatrix} = \begin{bmatrix} b \\ b \end{bmatrix} = b\begin{bmatrix} 1 \\ 1 \end{bmatrix} \implies |\lambda_2\rangle = \begin{bmatrix} 1 \\ 1 \end{bmatrix}
$$