+++
title = "(b) Exponentiation"
weight = 6
+++

---

### 1. 왜 지수화(Exponentiation)를 하는가

리 군 이론의 가장 큰 난관은 **"우리가 다루는 대상(회전, 움직임)이 굽어있는 공간(Curved Manifold)에 산다"** 는 점이다. 굽은 공간에서는 우리가 익숙한 **직선 긋기, 덧셈, 뺄셈** 이 불가능하다. 이러한 문제를 해결하기 위해 아래와 같은 과정을 수행한다.

- **STEP1, 선형화 (Linearization):** 굽은 공간의 한 점(항등원)에 **평평한 접평면(Tangent Plane, 리 대수)** 을 만든다.
- **STEP2, 계산 (Computation):** 이 평평한 지도 위에서 모든 계산(설계)을 끝낸다.
- **STEP3, 복원 (Restoration):** 계산된 직선 경로를 다시 굽은 공간 위로 **'감아 올린다(Wrap)'**.

이때, **"평평한 직선을 굽은 곡선으로 감아 올리는 과정"** 이 바로 **지수 맵(Exponential Map)** 이다. 기하학적 직관을 위해, 지도와 지구본을 생각해 본다.

[Image of tangent plane to a sphere]


- **리 대수($\mathfrak{g}$, 평면):** 책상 위에 펼쳐진 평평한 지도. 여기서 출발점과 방향(생성자)을 정하고 직선을 긋는다.
- **지수 맵($\exp$):** 이 지도를 지구본(리 군) 위에 주름 없이 팽팽하게 붙이는 과정이다.
- **리 군($G$, 곡면):** 지도상의 직선은 지구본 위에서 **최단 경로(측지선, Geodesic)** 가 되어 나타난다.

---

### 2. 1-매개변수 부분군의 지수화

앞선 챕터에서 "1-매개변수 부분군"의 움직임이 다음 미분방정식을 따름을 보았다.

$$
\frac{d}{d\tau}\hat{S}(\tau) = \hat{G} \cdot \hat{S}(\tau)
,\quad \hat{S}(0)=\hat{I}
$$

리 군에 대한 적분을 수행하면,

$$
\hat{S}(\tau)
=e^{\tau\hat{G}}
=\sum_{k=0} \frac{\tau^k\hat{G}^k}{k!}
$$

즉, 지수화는 우리가 선택한 것이 아니라, **연속적인 움직임을 기술하기 위한 유일한 수학적 도구** 다.

---

### 3. 다변수 리 군의 지수화 

앞선 챕터에서 "다변수 리 군"의 움직임이 다음 미분방정식을 따름을 보았다.

$$
\frac{d}{dt}\hat{S}(\{\tau_i(t)\})
=\hat{G}_{total}\cdot\hat{S}(\{\tau_i(t)\})
$$

$$
\hat{G}_{total}
=\sum_i \omega_i(t)\hat{G}_i,\quad\text{where,}\quad
\omega_i=\frac{d\tau_i}{d t}\bigg|_{\tau_i=0},\quad
\hat{G}_i=\frac{\partial\hat{S}(\{\tau_i\})}{\partial\tau_i}\bigg|_{\tau_i=0}
$$

**(1) $\omega_i=\text{constant}$**

예를 들어, 회전축을 고정하고 일정한 속도로 계속 도는 경우다. 이때는 $\hat{G}_{total}$ 자체가 **시간에 무관한 상수 행렬(Constant Matrix)** 이 된다.

$$
\hat{S}(\{\tau_i(t)\})=e^{t\hat{G}_{constant}}
$$

**(2) 가환 리 군 + 시변 입력 (Abelian & Time-varying)**

$$
\hat{S}(t) = \exp\left( \int_0^t \hat{G}(\tau) d\tau \right)
$$

proof)

1계 선형 미분방정식의 해법인 변수 분리(Separation of Variables) 와 유사한 논리를 쓴다.

$$
\frac{d\hat{S}}{dt} \hat{S}^{-1}
= \hat{G}(t),\quad\text{(행렬이므로 방향 주의)}
$$

가환인 경우이므로 $\cfrac{d}{dt}(\ln \hat{S}) = \cfrac{d\hat{S}}{dt}\hat{S}^{-1}$가 성립한다. 따라서 양변을 적분하면,

$$
\ln \hat{S}(t) - \ln \hat{S}(0) = \int_0^t \hat{G}(\tau) d\tau
$$

$\hat{S}(0)=I$ 이므로 $\ln I = 0$,

$$
\ln \hat{S}(t) = \int_0^t \hat{G}(\tau) d\tau
$$

양변에 지수(exp)를 취하면,

$$
\hat{S}(t) = \exp\left( \int_0^t \hat{G}(\tau) d\tau \right)
$$

---




입력 $\omega_i(t)$가 계속 변하더라도, 기저 생성자끼리 서로 교환 가능한 경우다. (예: 2차원 평면 이동)이 경우, 전체 생성자 $\hat{G}_{total}(t)$는 서로 다른 시간 $t_1, t_2$에서도 교환 가능하다.

$$
[\hat{G}_{total}(t_1), \hat{G}_{total}(t_2)]
= \left[ \sum_i \omega_i(t_1)\hat{G}_i, \sum_j \omega_j(t_2)\hat{G}_j \right]
= \sum_{i,j} \omega_i \omega_j \underbrace{[\hat{G}_i, \hat{G}_j]}_{0}
= 0
$$

따라서 미소 구간의 곱(적층)을 순서 상관없이 합칠 수 있으며, 각 성분별로 따로따로 적분하여 합치는 것이 가능하다.

$$
\hat{S}(t)=\exp\left( \int_0^t dt' \hat{G}_{total}(t')  \right)
=\exp\left( \int_0^t dt' \sum_i \omega_i(t')\hat{G}_i \right) 
=\exp\left( \sum_i \left( \int_0^t dt' \omega_i(t') \right) \hat{G}_i \right)
$$

**(3) 비가환 리 군 + 시변 입력 (Non-Abelian & Time-varying)**

입력 $\omega_i(t)$가 변하면서 기저 생성자끼리 교환되지 않는($\lbrack\hat{G}_i, \hat{G}_j\rbrack\neq 0$) 경우다. (예: 3차원 회전에서 회전축을 계속 바꿀 때) 따라서, 위처럼 $\sum$을 지수 안에서 적분($\int$)으로 합치는 것이 불가능하다.따라서 단순 지수화 대신, 시간 순서를 엄격히 지키며 곱해 나가는 다이슨 급수(Dyson Series) 가 해가 된다.

$$
\hat{S}(t) = \mathcal{T} \exp\left( \int_0^t dt'\sum_i \omega_i(t')\hat{G}_i \right)
$$

---

### 1. 일반적 설정: 비직교 기저와 듀얼 브라 (Biorthogonal System)

앞서 우리는 생성자 $\hat{G}$가 에르미트(대칭) 행렬일 때를 가정했다. 하지만 현실의 시스템(제어, 로보틱스 등)에서는 **비대칭(Non-symmetric) 행렬**이 생성자가 되는 경우가 많다. 이 경우 고유벡터들 $|n\rangle$은 서로 수직(Orthogonal)하지 않기 때문에, 일반적인 투영($|n\rangle\langle n|$)을 사용할 수 없다.

이 문제를 해결하기 위해 **듀얼 기저(Dual Basis, $\langle n^d |$)**를 도입한다.

**(1) 듀얼 기저의 정의**

우리는 원래의 기저 $|m\rangle$과 내적했을 때 크로네커 델타가 되는 새로운 기저 $\langle n^d |$를 정의할 수 있다.

$$
\hat{G} |n\rangle = g_n |n\rangle \quad (\text{우측 고유벡터})
$$
$$
\langle n^d | m \rangle = \delta_{nm} \quad (\text{듀얼 기저의 조건})
$$

실제 계산에서 듀얼 기저 $\langle n^d |$는 고유벡터 행렬 $P$의 **역행렬($P^{-1}$)의 행(Row)**들이다.

**(2) 스펙트럼 분해 (Spectral Decomposition)**

이를 이용하면, 에르미트 가정이 없어도 생성자 $\hat{G}$를 완벽하게 분해할 수 있다.

$$
\hat{G} = \sum_n g_n |n\rangle \langle n^d|
$$

- **$|n\rangle$:** 변환의 축 (기저)
- **$\langle n^d|$:** 성분을 추출하는 필터 (듀얼 기저)

---

### 2. 일반화된 거듭제곱의 유도

이제 지수 맵을 계산하기 위해 $\hat{G}^k$를 구해본다. 듀얼 기저의 위력이 여기서 발휘된다.

$$
\begin{aligned}
\hat{G}^2 &= \left( \sum_n g_n |n\rangle \langle n^d| \right) \cdot \left( \sum_m g_m |m\rangle \langle m^d| \right) \\
&= \sum_{n,m} g_n g_m |n\rangle \underbrace{\langle n^d | m \rangle}_{\delta_{nm}} \langle m^d| \\
&= \sum_n g_n^2 |n\rangle \langle n^d|
\end{aligned}
$$

즉, **일반적인 연산자라도 듀얼 기저를 사용하면 거듭제곱 시 고유값만 $k$승이 된다.**

$$
\hat{G}^k = \sum_n g_n^k |n\rangle \langle n^d|
$$

---

### 3. 일반화된 지수 맵 (Exponential Map)

테일러 급수에 대입하면, 지수 맵의 가장 일반적인 형태가 유도된다.

$$
e^{\tau \hat{G}} = \sum_{k=0}^{\infty} \frac{\tau^k}{k!} \hat{G}^k = \sum_n \left( \sum_{k=0}^{\infty} \frac{(\tau g_n)^k}{k!} \right) |n\rangle \langle n^d|
$$

$$
\therefore \hat{S}(\tau) = \sum_n e^{\tau g_n} |n\rangle \langle n^d|
$$

**[물리적/기하학적 해석]**
이 식은 리 군 연산자 $\hat{S}(\tau)$의 작동 원리를 완벽하게 보여준다.

1.  **$\langle n^d|$ (Analysis):** 입력 벡터를 듀얼 기저를 이용해 성분별로 분해한다. (공간이 찌그러져 있어도 정확한 성분을 뽑아냄)
2.  **$e^{\tau g_n}$ (Growth):** 각 성분을 고유값($g_n$)에 따라 지수적으로 성장/회전시킨다.
3.  **$|n\rangle$ (Synthesis):** 다시 원래의 기저 방향으로 재조립한다.

---

### 4. 예제: 비대칭 행렬의 지수 맵 계산

듀얼 기저의 위력을 확인하기 위해, 대칭이 아닌 생성자 $\hat{G}$의 지수 맵을 직접 구해본다.

$$
\hat{G} = \begin{pmatrix} 1 & 1 \\ 0 & 2 \end{pmatrix}
$$

**(1) 고유값과 기저 찾기 (Eigenvalues & Kets)**
- 고유값: $\lambda_1 = 1, \quad \lambda_2 = 2$
- 고유벡터 (Ket, $|n\rangle$):
    - $|1\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix}$
    - $|2\rangle = \begin{pmatrix} 1 \\ 1 \end{pmatrix}$

**(2) 듀얼 기저 찾기 (Dual Bras, $\langle n^d |$)**
고유벡터 행렬 $P = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}$ 의 역행렬 $P^{-1} = \begin{pmatrix} 1 & -1 \\ 0 & 1 \end{pmatrix}$ 을 구한다.
- $\langle 1^d| = \begin{pmatrix} 1 & -1 \end{pmatrix}$
- $\langle 2^d| = \begin{pmatrix} 0 & 1 \end{pmatrix}$

**(3) 지수 맵 계산**
공식 $\hat{S}(\tau) = e^{\tau \lambda_1} |1\rangle \langle 1^d| + e^{\tau \lambda_2} |2\rangle \langle 2^d|$ 에 대입한다.

$$
\begin{aligned}
e^{\tau \hat{G}} &= e^\tau \begin{pmatrix} 1 \\ 0 \end{pmatrix} \begin{pmatrix} 1 & -1 \end{pmatrix} + e^{2\tau} \begin{pmatrix} 1 \\ 1 \end{pmatrix} \begin{pmatrix} 0 & 1 \end{pmatrix} \\
&= e^\tau \begin{pmatrix} 1 & -1 \\ 0 & 0 \end{pmatrix} + e^{2\tau} \begin{pmatrix} 0 & 1 \\ 0 & 1 \end{pmatrix}
\end{aligned}
$$

**(4) 최종 결과**
$$
\hat{S}(\tau) = \begin{pmatrix} e^\tau & e^{2\tau} - e^\tau \\ 0 & e^{2\tau} \end{pmatrix}
$$
(검산: $\tau=0$ 대입 시 단위 행렬 $\hat{I}$가 정확히 나온다.)

---

### 5. 비가환성의 원인: "듀얼 기저의 불일치"

이 표기법을 쓰면 $[\hat{A}, \hat{B}] \neq 0$인 이유가 **기저 간의 간섭(Interference)** 때문임이 더 명확해진다.

$$
\hat{A}\hat{B} \sim \sum_{n,m} (\dots) |a_n\rangle \underbrace{\langle a_n^d | b_m \rangle}_{\text{Overlap}} \langle b_m^d|
$$

- **가환:** 두 연산자가 기저를 공유하므로, $\langle a_n^d | b_m \rangle = \delta_{nm}$처럼 깔끔하게 떨어진다.
- **비가환:** 기저가 서로 뒤틀려 있으므로, **$\hat{A}$의 듀얼 기저 $\langle a_n^d|$가 $\hat{B}$의 기저 $|b_m\rangle$을 걸러내지 못하고 복잡한 내적 값(Overlap)을 남긴다.**

**결론:**
비가환 상황에서는 **$\hat{A}$의 필터(Dual Basis)가 $\hat{B}$의 성분을 깔끔하게 걸러내지 못하고(Leakage), 서로 뒤섞인다.** 이 때문에 단순 변수 분리($e^{A+B}$)가 불가능하며, 새로운 기저를 찾아야만 계산이 가능하다.

---

### 5. 준동형 연산자(고유함수 대응) & 생성자(고유값 대응)

**proof1) '미분방정식' 사용**

미소 변화 정의 (생성자의 도입)위 식의 양변을 $\tau_1$에 대해 미분한 뒤, $\tau_1 = 0$을 대입해보자. 이때 $\tau_1=0$에서의 미분계수(변화율)를 생성자 $\hat{G}$ 라고 정의한다. ($\hat{G} \equiv \hat{S}'(0)$)

$$
\underbrace{\hat{S}'(0)}_{\hat{G}} \cdot \hat{S}(\tau_2) 
= \hat{S}'(\tau_2)
$$

미분방정식 수립변수 $\tau_2$를 일반적인 $\tau$로 바꾸면, 연산자 $\hat{S}(\tau)$는 다음의 1계 미분방정식을 만족해야 한다.

$$
\frac{d}{d\tau}\hat{S}(\tau)
= \hat{G} \cdot \hat{S}(\tau)
$$

유일한 해 (Solution)우리는 미분했을 때 자기 자신이 나오고 상수 $\hat{G}$가 튀어나오는 함수가 무엇인지 안다. 바로 지수함수다. 초기 조건 $\hat{S}(0)=\hat{I}$(항등원)을 만족하는 해는 유일하게 결정된다.

$$
\hat{S}(\tau) = e^{\tau \hat{G}}
$$

**proof2) '무한히 작은 움직임의 누적' 사용**

아주 작은 움직임 $\Delta \tau$를 생각해보자. 아무것도 안 했을 때($\hat{I}$)보다 아주 살짝 변했을 것이다. 그 변화율(기울기)을 $\hat{G}$라고 하자. 여기서 $\hat{G} = \hat{S}'(0)$이며, 이를 생성자라고 부른다.

$$
\hat{S}(\Delta \tau) \approx \hat{I} + \Delta \tau \cdot \hat{G}
$$

이제 큰 움직임 $\tau$를 만들기 위해, 이 미소 변환을 $N$번 반복해서 쌓아보자 ($\Delta \tau = \tau/N$). 움직임을 잘게 쪼개서 곱하면 전체 움직임이 된다.

$$
\hat{S}(\tau) = \underbrace{\hat{S}\left(\frac{\tau}{N}\right) \cdot \hat{S}\left(\frac{\tau}{N}\right) \cdots \hat{S}\left(\frac{\tau}{N}\right)}_{N \text{ times}} = \left( \hat{I} + \frac{\tau \hat{G}}{N} \right)^N
$$

움직임을 무한히 잘게 쪼개면($N \to \infty$), 이것은 자연상수 $e$의 정의가 된다.

$$
\lim_{N \to \infty} \left( 1 + \frac{x}{N} \right)^N = e^x \quad \Longrightarrow \quad \lim_{N \to \infty} \left( \hat{I} + \frac{\tau \hat{G}}{N} \right)^N = e^{\tau \hat{G}}
$$