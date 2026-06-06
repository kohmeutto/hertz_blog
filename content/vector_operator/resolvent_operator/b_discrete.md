+++
title = "(b) Discrete"
weight = 3
+++

---

### 1. 로랑 급수

레졸번트 연산자 $\hat{R}(z, \hat{A})$의 특이점 $z = \lambda_m$ 근방에서의 로랑 급수(Laurent series) 전개는 다음과 같이 정의된다.

$$
R(z, \hat{A}) = \sum_{k\ge2}\frac{\hat{C}_{-k}}{(z-\lambda_m)^k} + \frac{\hat{C}_{-1}}{z-\lambda_m} + \sum_{k\ge0}\hat{C}_k(z-\lambda_m)^k
$$

여기서 $k_m$은 고윳값 $\lambda_m$에 대응하는 공간의 멱영 지수(Index of nilpotency)이다. 임의의 정수 $n$에 대한 전개 계수 $\hat{C}_n$은 닫힌 경로 $\Gamma_m$에 대한 코시 적분 공식으로 산출된다.

$$
\hat{C}_n = \frac{1}{2\pi i}\oint_{\Gamma}\frac{dz}{z-\lambda_m}\frac{R(z)}{(z-\lambda_m)^{n}}
$$

---

### 2. (주부) 1차 단순극점 $\implies$ 사영 연산자(Projection operator) 

위 급수 전개에서 주부(Principal part)의 2차 이상 극점 성분은 시스템의 결함(Defect)을 나타낸다. 로랑 급수의 유수(Residue)에 해당하는 계수 $\hat{C}_{-1}$은 고윳값 $\lambda_m$ 공간으로의 스펙트럼 사영 연산자 $\hat{P}_m$으로 정의된다.

$$
\hat{P}_m = \hat{C}_{-1} = \frac{1}{2\pi i}\oint_{\Gamma_m} dz \, R(z,\hat{A})
$$

$$
\hat{P}_m^k = \hat{P}_m
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

### 3. (주부) 2차 극점 $\implies$ 멱영 연산자(Nilpotent operator), 비대각

본 장에서는 스케일 불변 측도 $\frac{dz}{z-\lambda_m}$를 적용한 로랑 급수의 일반 계수 산출 공식으로부터, 주부(Principal part)에 존재하는 모든 다중 극점(Multiple poles) 성분이 단 하나의 연산자 거듭제곱으로 표현됨을 보여준다.

$$
\hat{N}_m \equiv \hat{C}_{-2}
= \frac{1}{2\pi i} \oint_{\Gamma_m} dz (z-\lambda_m) \hat{R}(z, \hat{A})
$$

$$
\hat{N}_{m}^{k_m} = 0 
$$

proof)

로랑 급수의 일반항 정의에 따라, 임의의 고차 극점 계수 $\hat{C}_{-n}$ ($n \ge 2$)은 불변 측도 $\frac{dz}{z-\lambda_m}$를 도입한 코시 닫힌 경로 적분으로 다음과 같이 기술된다.

$$
\hat{C}_{-n} = \frac{1}{2\pi i} \oint_{\Gamma_m} \frac{dz}{z-\lambda_m} \hat{R}(z, \hat{A}) (z-\lambda_m)^n
$$

따라서 시스템 내에서 대각화를 방해하는 모든 비대각 결함 성분을 생성해 내는 이 근원적인 2차 극점 계수 $\hat{C}_{-2}$를 멱영 연산자(Nilpotent operator) $\hat{N}_m$으로 확정하여 정의한다.

$$
\hat{N}_m \equiv \hat{C}_{-2} = \frac{1}{2\pi i} \oint_{\Gamma_m} \frac{dz}{z-\lambda_m} \hat{R}(z, \hat{A}) (z-\lambda_m)^2
= \frac{1}{2\pi i} \oint_{\Gamma_m} dz (z-\lambda_m) \hat{R}(z, \hat{A})
$$

$\hat{P}_m$의 경우, 제곱을 하여 사영 연사자 임을 도출한것처럼, $C_{-2}$를 제곱해 본다. 특이점 $\lambda_m$을 둘러싸는 두 폐곡선 $\Gamma$와 $\Gamma'$ ($\Gamma$가 $\Gamma'$를 내포)에 대하여 $\hat{C}_{-2}^2$를 전개한다.

$$
\hat{N}_{m}^2 = \hat{C}_{-2}^2 = \frac{1}{(2\pi i)^2} \oint_{\Gamma} \oint_{\Gamma'} dz dw (z-\lambda_m)(w-\lambda_m) \hat{R}(z)\hat{R}(w)
$$

레졸번트 항등식을 대입하여 적분을 분리한다.

$$
\hat{N}_{m}^2 = \hat{C}_{-2}^2 = \frac{1}{(2\pi i)^2} \oint_{\Gamma} dz dw \oint_{\Gamma'} \frac{(z-\lambda_m)(w-\lambda_m)}{w - z} \left( \hat{R}(z) - \hat{R}(w) \right)
$$

앞선 사영 연산자의 멱등성 증명과 동일한 코시 적분 정리 절차를 거치면, $\Gamma'$에 대한 $w$ 적분에서 경로 내부에 위치한 극점 $z$에 의해 유수(Residue)가 발생한다.

$$
\hat{N}_{m}^2 = \hat{C}_{-2}^2 = \frac{1}{2\pi i} \oint_{\Gamma} dz (z-\lambda_m)^2 \hat{R}(z)
$$

위 적분식은 로랑 급수의 계수 공식 정의에 의해 정확히 3차 극점의 계수 $\hat{C}_{-3}$과 일치한다. 즉, $\hat{C}_{-2}^2 = \hat{C}_{-3}$가 성립한다. 이 적분 논리를 수학적 귀납법으로 임의의 정수 $k$로 확장하면 다음의 불변량이 도출된다.

$$
\hat{N}_{m}^k = \hat{C}_{-2}^k = \frac{1}{2\pi i} \oint_{\Gamma} dz (z-\lambda_m)^k \hat{R}(z) 
$$

**유한 차원 시스템의 대수학적 제약(유계**)에 의해 레졸번트의 로랑 급수 주부가 특정 차수인 멱영 지수 $k_m$에서 반드시 종결된다.

---

### 4. (주부) 대각화 성분과 비대각 성분의 대수적 분리

사영 연산자 $\hat{P}_m$은 단일 고윳값 $\lambda_m$에 대응하는 일반화된 고유공간 전체를 투영한다. 이 닫힌 공간 내부에서 시스템 연산자 $\hat{A}$가 작용할 때, 대각화가 가능한 반단순(Semisimple) 성분과 대각화가 불가능한 비대각(Off-diagonal) 성분으로 본질적인 대수적 분리가 발생한다. **이것은 일반화 챕터와 동일한 결과를 레졸벤트를 사용하여 그대로 도출되는지를 확인하기 위함이다.**

$$
\hat{A}\hat{P}_m=\lambda_m\hat{P}_m+\hat{N}_{m}
$$

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
\hat{A} \hat{P}_m = \lambda_m \hat{P}_m + \hat{N}_{m}
$$

---

### 5. (정칙부) (?)








---

### 6. 예제: 비정규 대각화 가능 연산자

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