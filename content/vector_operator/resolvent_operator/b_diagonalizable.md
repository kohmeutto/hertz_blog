+++
title = "(b) Diagonalizable"
weight = 2
+++

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