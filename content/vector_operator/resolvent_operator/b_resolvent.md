+++
title = "(b) [D] Resolvent"
weight = 2
+++

---

### 1. 동기

일반화된 고유벡터를 이용한 챕터는 "만약 우리가 찌그러진 기저 벡터들을 모두 찾아낼 수 있다면, 연산자는 이렇게 분해될 것이다"라는 사후적이고 이상적인 대수학적 구조($\hat{A} = \lambda_m\hat{P}_m + \hat{N}_m$)를 보여준다. 하지만 현실의 시스템이나 무한 차원 공간에서는 고윳값을 찾기 위한 특성 방정식($\det = 0$) 자체가 붕괴하며, 설령 고윳값을 안다 해도 거듭제곱된 고유 방정식 $(\hat{A}-\lambda_m\hat{I})^k|\lambda_{m,k}\rangle = 0$ 을 풀어 조르당 사슬의 역방향으로 잉여 상태를 추적해 나가는 것은 해석학적으로 불가능에 가깝다.

**즉, Generalization 챕터는 '결과론적 구조'일 뿐, 그것을 실제로 추출해 내는 '도구'를 제공하지 못한다.** 실제적 도구는 다음 챕터에서 유수의 정리를 사용하여 구해야 한다.

---

### 2. Resolvent operator: 고유값 찾기의 일반화

행렬식을 쓸 수 없는 무한 차원 공간에서는, 고유값을 찾는 문제를 "역작용소가 존재하지 않는 지점을 찾는 문제"와 동치이다.

$$
R(z, \hat{A}) = (z \hat{I} - \hat{A})^{-1}
$$

proof)

*(1) 고유값 방정식의 이항*

$\lambda$ 가 연산자 $\hat{A}$ 의 고유값이라는 것은 0이 아닌 고유벡터 $|v\rangle$ (즉, $|v\rangle \neq 0$) 에 대하여 다음 방정식이 성립함을 뜻한다.

$$
(\lambda \hat{I} - \hat{A}) |v\rangle = 0
$$

*(2) det=0의 의미: 역작용소의 도출 불가능성*

det=0 이라는 것은 차원(정보)의 축소를 의미하여, 이것은 정보가 사라졌으므로, 역으로 온전히 되돌릴 방법이 없다는 것을 의미한다. 즉, 역행렬이 존재하지 않는 다는 의미이다.

*(3) 고유값 찾기의 일반화*

따라서 고유값을 찾는 문제는 "역작용소가 정의되지 않는 지점을 찾는 문제"로 치환된다. 이를 체계적으로 탐색하기 위해, 복소 평면 상의 임의의 변수 $z$ 에 대한 함수로서 다음과 같이 레졸번트 연산자(Resolvent Operator) $R(z, \hat{A})$ 를 정의한다.

$$
R(z, \hat{A}) = (z \hat{I} - \hat{A})^{-1}
$$

*(4) 레졸벤트에서 고유값의 거동*

고유값에서는 역작용소가 정의되지 않는 지점이라고 하였다. 그렇다면, 레졸번트 연산자가 어떻게 되길래, 정의가 되지 않는다고 하는 것일까. 어떠한 것으로 정의되지 않으려면, 무한대로 발산해야 한다.

$$
R(\lambda_i, \hat{A}) = (\lambda_i \hat{I} - \hat{A})^{-1} = \infty
$$

고유값에서 왜 발산하는 가를 알기 위해, 레졸벤트 연산자가 구체적으로 어떤 형태를 가지고 있는지를 파악해야 한다. 이는 후속 챕터에서 다룬다.

---

### 3. 연산자 분해를 통한 레졸번트의 대수적 전개

복소 평면으로 우회하는 해석학적 동기를 대수학적으로 교차 검증하기 위해, 앞서 일반화된 고유벡터 공간에서 확립한 연산자 분해 결과를 레졸번트의 정의에 직접 대입하여 전개한다. 이 과정은 왜 레졸번트가 로랑 급수(Laurent series) 형태의 다중 극점(Multiple pole) 구조를 가질 수밖에 없는지를 증명한다.

$$
R(z,\hat{A}) 
= \sum_{k \ge 2} \frac{\hat{N}_m^{k-1}}{(z-\lambda_m)^k} +  \frac{\hat{P}_m}{z-\lambda_m} + \sum_{n=0}^{\infty} (-1)^n \hat{S}_m^{n+1} (z - \lambda_m)^n
$$

proof)

*(1) $z\hat{I} - \hat{A}$*

대상 연산자 $\hat{A}$의 일반화된 스펙트럼 분해는 다음과 같다.

$$
\hat{A} = \sum_m (\lambda_m\hat{P}_m + \hat{N}_m)
$$

레졸번트 연산자 $R(z, \hat{A}) = (z\hat{I} - \hat{A})^{-1}$를 구성하기 위해, 먼저 항등 연산자 $\hat{I}$를 사영 연산자의 완비성 관계(Resolution of identity, $\hat{I} = \sum_m \hat{P}_m$)로 치환하여 식을 결합한다.

$$
z\hat{I} - \hat{A}
= z\sum_m \hat{P}_m - \sum_m (\lambda_m\hat{P}_m + \hat{N}_m) = \sum_m \left[ (z - \lambda_m)\hat{P}_m - \hat{N}_m \right]
= \sum_m \hat{B}_m
$$

*(2)  서로 다른 공간의 블록 연산자 간에 직교성 ($\hat{B}_m \hat{B}_l = \hat{0}, m \neq l$)*

$$
\hat{B}_m\hat{B}_l
= \left[ (z - \lambda_m) \hat{P}_m - \hat{N}_m \right] \left[ (z - \lambda_l) \hat{P}_l - \hat{N}_l \right]
$$

$$
= (z - \lambda_m)(z - \lambda_l) \hat{P}_m\hat{P}_l - (z - \lambda_m)\hat{P}_m\hat{N}_l - (z - \lambda_l)\hat{P}_l\hat{N}_m + \hat{N}_m\hat{N}_l
$$

$$
= 0
$$

*(3) $[z\hat{I} - \hat{A}]^{-1}$*

$$
R(z, \hat{A}) = \left( \sum_m \hat{B}_m \right)^{-1} = \sum_m \hat{B}_m^{-1}
$$

*(4) 성분간의 분해*

특정성분 $m$ 에 대해 분리해서 적용하면,

$$
R(z, \hat{A})
=\hat{B}_m^{-1} + \sum_{l \ne m} \hat{B}_l^{-1}
$$

*(5) $\hat{B}_m^{-1}$ 전개*

$$
\hat{B}_m^{-1}
= [(z-\lambda_m)\hat{P}_m-\hat{N}_m]^{-1}
= \frac{1}{z-\lambda_m}\left( \hat{P}_m- \frac{\hat{N}_m}{z-\lambda_m} \right)^{-1}
$$

$$
= \frac{1}{z-\lambda_m}\left( \hat{P}_m + \frac{\hat{N}_m}{z-\lambda_m} +  \frac{\hat{N}_m^2}{(z-\lambda_m)^2} + \cdots \right)
$$

$$
= \sum_{k \ge 2} \frac{\hat{N}_m^{k-1}}{(z-\lambda_m)^k} +  \frac{\hat{P}_m}{z-\lambda_m}
$$

*(6) $\sum_{l \ne m} \hat{B}_l^{-1}$ 전개*

$$
\sum_{l \neq m} \hat{B}_l^{-1}
= \sum_{l \neq m} \left[ (z - \lambda_l + \lambda_m - \lambda_m)\hat{P}_l - \hat{N}_l \right]^{-1}
= \sum_{l \neq m} \left[ (\lambda_m - \lambda_l)\hat{P}_l - \hat{N}_l + (z - \lambda_m)\hat{P}_l \right]^{-1}
$$

관측점 $z \to \lambda_m$ 극한에서 발산하지 않는 지배적인 상수항 연산자를 $\hat{Y}_l$로 정의한다. 멱영 연산자 $\hat{N}_l$은 사영 공간 $\hat{P}_l$에 완전히 종속되므로, $\hat{Y}_l$ 역시 국소 공간 $l$ 내부에 한정된다.

$$
\hat{Y}_l \equiv (\lambda_m - \lambda_l)\hat{P}_l - \hat{N}_l
$$

정의된 $\hat{Y}_l$을 사용하여 국소 블록 연산자를 표현하면 다음과 같다.$$\hat{B}_l = \hat{Y}_l + (z - \lambda_m)\hat{P}_l$$이 국소 공간 $l$ 내에서 $\hat{P}_l$은 항등원으로 작용하며, $\hat{Y}_l$의 역작용소 $\hat{Y}_l^{-1}$ 역시 존재한다($\hat{Y}_l \hat{Y}_l^{-1} = \hat{P}_l$). 이를 이용하여 공통 인수 $\hat{Y}_l$을 괄호 밖으로 묶어낸다.

$$
\hat{B}_l = \hat{Y}_l \left[ \hat{P}_l + (z - \lambda_m)\hat{Y}_l^{-1} \right]
$$

이제 단일 공간 $l$에 대한 역작용소 $\hat{B}_l^{-1}$을 구하기 위해 역수를 취한다. 연산자의 곱셈 순서에 유의하여 분배한다.

$$
\hat{B}_l^{-1} = \left[ \hat{P}_l + (z - \lambda_m)\hat{Y}_l^{-1} \right]^{-1} \hat{Y}_l^{-1}
$$

대괄호 내부는 국소 공간 $\hat{P}_l$에 대한 노이만 급수 $(\hat{P}_l - \hat{X})^{-1} = \sum_{n=0}^{\infty} \hat{X}^n$의 형태를 갖춘다. 여기서 대입되는 연산자 $\hat{X}$는 $-(z - \lambda_m)\hat{Y}_l^{-1}$이다. 이를 전개한다.

$$
\hat{B}_l^{-1} = \left( \sum_{n=0}^{\infty} (-1)^n (z - \lambda_m)^n (\hat{Y}_l^{-1})^n \right) \hat{Y}_l^{-1}
$$

우측의 $\hat{Y}_l^{-1}$을 시그마 내부로 결합하여 단일 타 공간 $l$에 대한 역작용소 전개를 완료한다.

$$
\hat{B}_l^{-1} = \sum_{n=0}^{\infty} (-1)^n (z - \lambda_m)^n (\hat{Y}_l^{-1})^{n+1}
$$

최종적으로, 관측 공간 $\lambda_m$을 제외한 모든 타 공간($l \neq m$)에 대하여 시그마 합산($\sum_{l \neq m}$)을 수행한다.

$$
\sum_{l \neq m} \hat{B}_l^{-1} = \sum_{l \neq m} \sum_{n=0}^{\infty} (-1)^n (z - \lambda_m)^n (\hat{Y}_l^{-1})^{n+1}
$$

합산의 순서를 교환하여 상수항 연산자 부분만을 독립적으로 묶어낸다.

$$
\sum_{l \neq m} \hat{B}_l^{-1} = \sum_{n=0}^{\infty} (-1)^n (z - \lambda_m)^n \left[ \sum_{l \neq m} (\hat{Y}_l^{-1})^{n+1} \right]
$$

이때 서로 다른 고유공간의 연산자들은 완벽하게 직교하므로($\hat{Y}_l^{-1} \hat{Y}_p^{-1} = \hat{0}, \; l \neq p$), 각 거듭제곱의 합은 전체 합의 거듭제곱과 대수적으로 완전히 동치이다.

$$
\sum_{l \neq m} (\hat{Y}_l^{-1})^{n+1} = \left( \sum_{l \neq m} \hat{Y}_l^{-1} \right)^{n+1}
$$

여기서 괄호 내부의 1차 합산 결과를 환원 레졸번트(Reduced resolvent) $\hat{S}_m$으로 확정하여 정의한다. 즉, $\hat{S}_m$은 단일 공간이 아닌 '관측점을 제외한 모든 타 공간들의 배경장 역작용소 합'으로 유도된다.

$$
\hat{S}_m \equiv \sum_{l \neq m} \hat{Y}_l^{-1} = \sum_{l \neq m} \left[ (\lambda_m - \lambda_l)\hat{P}_l - \hat{N}_l \right]^{-1}
$$

이를 본래의 급수 식에 대입하면, 해석학적 비약 없이 연산자 대수학만으로 정칙부(Regular part)의 무한 멱급수가 도출된다.

$$
\sum_{l \neq m} \hat{B}_l^{-1} = \sum_{n=0}^{\infty} (-1)^n \hat{S}_m^{n+1} (z - \lambda_m)^n
$$

---

### 4. 복소 평면의 분할: 레졸번트 집합과 스펙트럼

레졸번트 연산자 $R(z, \hat{A}) = (z\hat{I} - \hat{A})^{-1}$ 는 임의의 복소 변수 $z$ 를 도입하여 정의되었으나, $z$ 의 값에 따라 그 수학적 성질이 극명하게 달라진다. 역작용소의 유계성(Boundedness)을 기준으로 복소 평면 $\mathbb{C}$ 는 두 개의 영역으로 분할된다.

**1) 레졸번트 집합 (Resolvent Set, $\rho(\hat{A})$)**

복소수 $z$ 를 대입했을 때, 레졸번트 연산자 $R(z, \hat{A})$ 가 유계 연산자(Bounded Operator)로서 안정적으로 존재하는 $z$ 의 집합이다. 이 영역에서 역작용소는 특정 입력 벡터를 공간 밖으로 이탈시키거나 증폭률을 무한대로 발산시키지 않으며, 복소해석학적 함수로서 안전하게 다뤄질 수 있다.

**2) 스펙트럼 (Spectrum, $\sigma(\hat{A})$)**

복소 평면에서 레졸번트 집합을 제외한 나머지 영역이다.

$$
\sigma(\hat{A}) = \mathbb{C} \setminus \rho(\hat{A})
$$

스펙트럼 내의 $z$ 에 대해서는 작용소 $(z\hat{I} - \hat{A})$ 의 역연산이 불가능해지거나, 결과값이 무한대로 발산하여 비유계(Unbounded) 특성을 띠게 된다. 이 발산하는 특이점(Singularity)들이 바로 무한 차원 공간에서 행렬식 없이 찾아낸 연산자 $\hat{A}$ 의 본질적인 고유값 집합이다.

---

### 5. 제1 레졸번트 항등식

앞선 노이만 급수는 변수 $z$ 가 $|z| > \lVert \hat{A} \rVert$ 조건을 만족할 때만 성립한다. 1차 미분 연산자 $\hat{D}$ 처럼 본질적으로 비유계인 연산자는 노름이 무한대로 발산하므로($\lVert \hat{D} \rVert = \infty$), 이 급수 수렴 조건을 만족하는 $z$ 가 복소 평면 상에 존재할 수 없다. 즉, $\hat{A}$ 의 거듭제곱( $\hat{A}^n$ )을 직접 전개하는 방식은 무한 차원 공간에서 여전히 정의역의 연쇄적 붕괴를 초래한다.

이 한계를 극복하기 위해, 비유계 연산자 $\hat{A}$ 를 직접 거듭제곱하는 대신 레졸번트 집합 내부에 존재하는 두 레졸번트 사이의 대수적 관계를 유도한다. 복소수 $z$ 와 $w$ 가 발산 영역인 스펙트럼 $\sigma(\hat{A})$ 를 제외한 레졸번트 집합 $\rho(\hat{A})$ 에 속할 때, 역작용소 $R(z, \hat{A})$ 와 $R(w, \hat{A})$ 는 명확한 유계 연산자로 확정된다. 이 유계성이 대수적으로 보장된 조건 하에서 다음의 항등식이 성립한다.

$$
R(z, \hat{A}) - R(w, \hat{A}) = -(z - w) R(z, \hat{A}) R(w, \hat{A}) \quad (z, w \in \rho(\hat{A}))
$$

proof)

역작용소의 정의에 의해, 레졸번트 집합 내의 $z, w$ 에 대하여 다음 관계가 성립한다.

$$
(z \hat{I} - \hat{A}) R(z, \hat{A}) = \hat{I},\quad 
(w \hat{I} - \hat{A}) R(w, \hat{A}) = \hat{I}
$$

두 식을 상호 교차하여 빼기 위해, 항등 연산자 $\hat{I}$ 를 공통 매개로 결합한다.

$$
R(z, \hat{A}) = R(z, \hat{A}) (w \hat{I} - \hat{A}) R(w, \hat{A}),\quad
R(w, \hat{A}) = R(z, \hat{A}) (z \hat{I} - \hat{A}) R(w, \hat{A})
$$

첫 번째 식에서 두 번째 식을 차감하고 공통 인수로 묶어 분배 법칙을 역으로 적용한다.

$$
R(z, \hat{A}) - R(w, \hat{A})
= R(z, \hat{A}) [ (w \hat{I} - \hat{A}) - (z \hat{I} - \hat{A}) ] R(w, \hat{A})
= R(z, \hat{A}) [ (w - z)\hat{I} ] R(w, \hat{A})
$$

스칼라 성분 $(w - z)$ 는 선형 연산자와의 교환 법칙이 성립하므로 식의 외부로 분리되어 증명이 완료된다.

$$
R(z, \hat{A}) - R(w, \hat{A}) = -(z - w) R(z, \hat{A}) R(w, \hat{A})
$$

---

### 6. 도함수로의 확장

유도된 항등식의 양변을 $(z - w)$ 로 나누고 극한 $w \to z$ 를 취하면, 레졸번트 연산자의 복소 미분이 대수적으로 도출된다.

$$
\frac{d}{dz}R(z, \hat{A}) = \lim_{w \to z} \frac{R(z, \hat{A}) - R(w, \hat{A})}{z - w} = -[R(z, \hat{A})]^2
$$

도함수가 정의역 붕괴를 유발하는 비유계 연산자 $\hat{A}$ 의 거듭제곱이 아니라, $\rho(\hat{A})$ 내부에서 유계임이 보장된 레졸번트 자신의 거듭제곱 $[R(z, \hat{A})]^2$ 으로 산출되었다. 유계 연산자의 거듭제곱은 무한대 발산이나 정의역의 축소 없이 정의되므로, 이는 레졸번트가 레졸번트 집합 $\rho(\hat{A})$ 내부에서 모든 차수의 미분이 수학적으로 보장되는 해석 함수(Analytic function)이다. 

---