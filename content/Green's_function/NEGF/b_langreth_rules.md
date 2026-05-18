+++
title = "(b) Langreth rules"
weight = 7
+++

---

### 1. 동기: Contour 에서 real-time 으로의 변환

이전 절에서 contour Dyson 방정식

$$
G^c(\tau, \tau') = G_0^c(\tau, \tau') + \int_C d\tau_1\,d\tau_2\,G_0^c(\tau, \tau_1)\,\Sigma^c(\tau_1, \tau_2)\,G^c(\tau_2, \tau')
$$

이 4 가지 real-time Dyson 방정식 (retarded, advanced, lesser, greater) 의 통합 표현임을 보았다. 그러나 위 contour 방정식에서 어떻게 각 real-time 방정식을 추출하는지는 자세히 다루지 않았다.

핵심 문제는 다음과 같다. Contour 적분 $\int_C d\tau_1$ 은 forward branch $C_+$ 와 backward branch $C_-$ 양쪽을 지난다. 따라서 contour 위 두 점 $\tau, \tau'$ 의 branch 를 지정하더라도, 내부 적분 변수 $\tau_1$ 의 branch 에 따라 $G_0^c, \Sigma^c, G^c$ 의 component 가 달라진다. 이 다양한 case 를 체계적으로 정리해서 각 real-time component 의 방정식으로 환원해야 한다.

**Langreth 룰** 이 이 변환을 정확하고 간결하게 수행한다. 룰의 본질은 다음과 같다.

Contour 위의 두 객체 $A^c, B^c$ 의 convolution $C^c = A^c \circ B^c$ 또는 곱 $C^c(\tau, \tau') = A^c(\tau, \tau') B^c(\tau, \tau')$ 가 주어질 때, $C^c$ 의 각 real-time component ($C^R, C^A, C^<, C^>$) 를 $A^c, B^c$ 의 component 로 표현하는 공식.

이 절에서는 convolution 에 대한 Langreth 룰을 도출하고, 이를 Dyson 방정식에 적용해 real-time 방정식을 도출하며, 이전 절들에서 사용한 Keldysh 방정식의 일반화된 형태를 정리한다.

---

### 2. 두 가지 contour 연산

Contour 위에서의 객체 결합은 두 가지 기본 연산으로 나타난다.

**1) Convolution (적분이 있는 경우)**

$$
C^c(\tau, \tau') = (A^c \circ B^c)(\tau, \tau') := \int_C d\tau_1\,A^c(\tau, \tau_1)\,B^c(\tau_1, \tau')
$$

내부 변수 $\tau_1$ 이 contour 전체를 지나며 적분된다. Dyson 방정식의 $G_0 \Sigma G$ 형태가 이에 해당.

**2) Product (적분이 없는 경우)**

$$
C^c(\tau, \tau') = A^c(\tau, \tau')\,B^c(\tau, \tau')
$$

같은 두 점에서 두 객체의 단순 곱. Vertex correction 의 일부 또는 일부 관측량 공식에 등장.

두 연산의 Langreth 룰이 다르므로 구분해서 다룬다.

---

### 3. Convolution 에 대한 Langreth 룰

**1) 룰의 정리**

Contour convolution $C^c = A^c \circ B^c$ 의 4 component 가 다음과 같이 real-time convolution 으로 표현된다.

$$
\boxed{\begin{aligned}
C^R(t, t') &= \int dt_1\,A^R(t, t_1)\,B^R(t_1, t') \\
C^A(t, t') &= \int dt_1\,A^A(t, t_1)\,B^A(t_1, t') \\
C^<(t, t') &= \int dt_1\,\bigl[A^R(t, t_1)\,B^<(t_1, t') + A^<(t, t_1)\,B^A(t_1, t')\bigr] \\
C^>(t, t') &= \int dt_1\,\bigl[A^R(t, t_1)\,B^>(t_1, t') + A^>(t, t_1)\,B^A(t_1, t')\bigr]
\end{aligned}}
$$

세 번째와 네 번째 식의 구조에 주목하자. Lesser 또는 greater 가 retarded 와의 convolution 으로 들어오고 (앞쪽 항), advanced 와의 convolution 으로 들어온다 (뒤쪽 항). 이 두 항이 시간 순서에 대해 인과적 / 반인과적 경로를 분담한다.

**2) Lesser 룰의 도출**

$C^<(t, t')$ 의 도출을 자세히 본다. 이는 $\tau \in C_+, \tau' \in C_-$ 의 case 이다.

Contour 적분을 두 branch 의 합으로 분해한다.

$$
C^c(\tau, \tau') = \int_{C_+} d\tau_1\,A^c(\tau, \tau_1)\,B^c(\tau_1, \tau') + \int_{C_-} d\tau_1\,A^c(\tau, \tau_1)\,B^c(\tau_1, \tau')
$$

$\tau_1$ 의 branch 에 따라 $A^c, B^c$ 의 component 가 결정된다.

**$\tau_1 \in C_+$ 의 경우** (forward branch):

$\tau \in C_+$, $\tau_1 \in C_+$: $A^c(\tau, \tau_1) = A^T(t, t_1)$ (둘 다 $C_+$).
$\tau_1 \in C_+$, $\tau' \in C_-$: $B^c(\tau_1, \tau') = B^<(t_1, t')$.

Forward branch 의 적분 측도는 $\int_{-\infty}^{\infty} dt_1$. 따라서

$$
\int_{C_+} d\tau_1\,A^c\,B^c = \int dt_1\,A^T(t, t_1)\,B^<(t_1, t')
$$

**$\tau_1 \in C_-$ 의 경우** (backward branch):

$\tau \in C_+$, $\tau_1 \in C_-$: $A^c(\tau, \tau_1) = A^<(t, t_1)$.
$\tau_1 \in C_-$, $\tau' \in C_-$: $B^c(\tau_1, \tau') = B^{\tilde T}(t_1, t')$.

Backward branch 의 적분 측도는 시간이 거꾸로 흐르므로 $\int_{\infty}^{-\infty} dt_1 = -\int_{-\infty}^{\infty} dt_1$.

$$
\int_{C_-} d\tau_1\,A^c\,B^c = -\int dt_1\,A^<(t, t_1)\,B^{\tilde T}(t_1, t')
$$

**합산**:

$$
C^<(t, t') = \int dt_1\,\bigl[A^T(t, t_1)\,B^<(t_1, t') - A^<(t, t_1)\,B^{\tilde T}(t_1, t')\bigr]
$$

**3) $A^T, A^{\tilde T}$ 의 분해 적용**

이전 절의 결과 $A^T = A^R + A^<$, $A^{\tilde T} = A^< - A^A$ 를 대입한다.

$$
C^< = \int dt_1\,\bigl[(A^R + A^<)\,B^< - A^<\,(B^< - B^A)\bigr]
$$

전개하면

$$
C^< = \int dt_1\,\bigl[A^R B^< + A^< B^< - A^< B^< + A^< B^A\bigr] = \int dt_1\,\bigl[A^R B^< + A^< B^A\bigr]
$$

즉

$$
C^<(t, t') = \int dt_1\,\bigl[A^R(t, t_1)\,B^<(t_1, t') + A^<(t, t_1)\,B^A(t_1, t')\bigr]
$$

§3-(1) 의 표준 룰과 일치. ✓

**4) Retarded 룰의 도출**

$C^R$ 의 도출은 정의 $C^R(t, t') = \theta(t-t')[C^>(t,t') - C^<(t,t')]$ 에서 직접 가능. 또는 contour formalism 에서 $\tau, \tau'$ 가 같은 (forward) branch 에 있고 contour ordering 이 일반 시간 ordering 과 같은 case 로부터.

결과: $C^R$ 가 retarded 끼리의 convolution 으로만 표현된다.

$$
C^R(t, t') = \int dt_1\,A^R(t, t_1)\,B^R(t_1, t')
$$

이 단순함은 인과율의 결과이다. Retarded function 끼리의 곱은 인과적 → 인과적 응답으로, 다른 component 의 기여가 0 이 된다.

비슷한 도출로

$$
C^A(t, t') = \int dt_1\,A^A(t, t_1)\,B^A(t_1, t')
$$

$C^>$ 는 $C^<$ 와 같은 구조로 ($<$ 를 $>$ 로 대체).

**5) 룰의 직관적 이해**

Langreth 룰을 직관적으로 이해하는 방법:

- Retarded ($R$): 시간이 한 방향으로 흐르며 모두 인과적 경로. 모든 사이 시간 점에서 retarded.
- Advanced ($A$): 모두 반인과적. 모든 사이 시간 점에서 advanced.
- Lesser ($<$): 시간이 한 방향으로 갔다가 다른 방향으로 옴. 사이의 한 점에서 "점유 정보 ($<$)" 가 등장하며, 그 점 이전은 인과적 ($R$), 이후는 반인과적 ($A$).
- Greater ($>$): 비슷한 구조, $<$ 가 $>$ 로.

이 그림은 contour 위 두 branch 사이의 경로 구조를 직접 반영한다.

---

### 4. Product 에 대한 Langreth 룰

같은 점에서의 product $C^c(\tau, \tau') = A^c(\tau, \tau')\,B^c(\tau, \tau')$ 에 대한 룰.

**1) Lesser 와 greater**

$\tau \in C_+, \tau' \in C_-$ 이면 $C^c, A^c, B^c$ 모두 lesser:

$$
C^<(t, t') = A^<(t, t')\,B^<(t, t')
$$

비슷하게

$$
C^>(t, t') = A^>(t, t')\,B^>(t, t')
$$

**2) Retarded와 advanced**

도출: $C^R(t, t') = \theta(t - t')[C^>(t, t') - C^<(t, t')] = \theta(t-t')[A^>B^> - A^<B^<]$.

$A^>B^> - A^<B^<$ 를 $A^R, B^R, A^<, B^<$ 등으로 풀어쓴다.

$$
A^>B^> - A^<B^< = (A^> - A^<)B^> + A^<(B^> - B^<)
$$

$t > t'$ 에서 $A^> - A^< = A^R$, $B^> - B^< = B^R$. 따라서

$$
C^R(t, t') = A^R(t, t')\,B^>(t, t') + A^<(t, t')\,B^R(t, t')
$$

$t < t'$ 에서 위 표현이 0 이 되는지 확인: $A^R(t, t')$ 와 $B^R(t, t')$ 모두 0. ✓

비슷한 도출로

$$
C^A(t, t') = A^A(t, t')\,B^<(t, t') + A^>(t, t')\,B^A(t, t')
$$

(또는 동등한 변형 형태들.)

Product 룰은 convolution 룰보다 덜 자주 사용되지만, vertex 보정 등 특정 맥락에서 나타난다.

---

### 5. Dyson 방정식에의 적용

이제 Langreth 룰을 contour Dyson 방정식

$$
G^c = G_0^c + G_0^c \circ \Sigma^c \circ G^c
$$

에 적용해 real-time Dyson 방정식들을 도출한다.

**1) Retarded Dyson 방정식**

Convolution rule for $C^R$:

$$
(G_0 \circ \Sigma \circ G)^R = G_0^R \circ \Sigma^R \circ G^R
$$

(여러 retarded 의 convolution.) 이를 contour Dyson 에 적용하면

$$
G^R(t, t') = G_0^R(t, t') + \int dt_1\,dt_2\,G_0^R(t, t_1)\,\Sigma^R(t_1, t_2)\,G^R(t_2, t')
$$

이는 retarded Dyson 방정식의 시간 영역 표현이다. 정상상태에서 Fourier 변환하면

$$
G^R(E) = G_0^R(E) + G_0^R(E)\,\Sigma^R(E)\,G^R(E)
$$

이전 절에서 사용한 닫힌 형태.

**2) Advanced Dyson 방정식**

비슷하게

$$
G^A(t, t') = G_0^A(t, t') + \int dt_1\,dt_2\,G_0^A(t, t_1)\,\Sigma^A(t_1, t_2)\,G^A(t_2, t')
$$

$G^A = (G^R)^\dagger$ 의 관계로 retarded 방정식으로부터 직접 도출도 가능.

**3) Lesser Dyson 방정식**

이 부분이 핵심이다. Convolution rule for $C^<$ 를 contour Dyson 의 lesser component 에 적용한다.

$C^c = G_0^c \circ \Sigma^c \circ G^c$ 를 두 단계 convolution 으로 분해: 먼저 $X^c := G_0^c \circ \Sigma^c$ 계산, 그 다음 $C^c = X^c \circ G^c$.

$X^<$:

$$
X^<(t, t_2) = \int dt_1\,\bigl[G_0^R(t, t_1)\,\Sigma^<(t_1, t_2) + G_0^<(t, t_1)\,\Sigma^A(t_1, t_2)\bigr]
$$

$C^< = (X \circ G)^<$:

$$
C^<(t, t') = \int dt_2\,\bigl[X^R(t, t_2)\,G^<(t_2, t') + X^<(t, t_2)\,G^A(t_2, t')\bigr]
$$

여기서 $X^R = G_0^R \circ \Sigma^R$. 모든 것을 풀면

$$
G^<(t, t') = G_0^<(t, t') + \int\int dt_1\,dt_2\,\bigl[G_0^R(t, t_1)\,\Sigma^R(t_1, t_2)\,G^<(t_2, t') + G_0^R(t, t_1)\,\Sigma^<(t_1, t_2)\,G^A(t_2, t') + G_0^<(t, t_1)\,\Sigma^A(t_1, t_2)\,G^A(t_2, t')\bigr]
$$

이 식이 **일반 lesser Dyson 방정식** 이다. 세 가지 종류의 항이 있다:

- $G_0^R \Sigma^R G^<$: retarded self-energy 와 lesser 그린함수의 자기일관 결합
- $G_0^R \Sigma^< G^A$: lesser self-energy 의 직접 기여 (점유 주입)
- $G_0^<\Sigma^A G^A$: 초기 lesser 의 기여

**4) 정상상태에서의 환원: Keldysh equation**

정상상태 + adiabatic switching 조건에서 $G_0^<$ 의 기여가 사라진다. 자세히는 다음과 같이 진행된다.

위 일반 lesser Dyson 방정식에서 $G_0^<$ 가 직접 0 인 경우 (초기 분포가 무시되는 한계, 또는 $t_0 \to -\infty$ 의 adiabatic 한계) 첫 두 항만 남는다.

$$
G^< = G_0^R\,\Sigma^R\,G^< + G_0^R\,\Sigma^<\,G^A
$$

이를 $G^<$ 에 대해 풀면

$$
(1 - G_0^R\,\Sigma^R)\,G^< = G_0^R\,\Sigma^<\,G^A
$$

좌변의 ($1 - G_0^R\,\Sigma^R$) 의 역연산은 retarded Dyson 방정식 $G^R = G_0^R + G_0^R \Sigma^R G^R$ 의 닫힌 형태 $G^R = (1 - G_0^R\,\Sigma^R)^{-1} G_0^R$ 에서

$$
(1 - G_0^R\,\Sigma^R)^{-1} = G^R / G_0^R = G^R\,(G_0^R)^{-1}
$$

따라서

$$
G^< = (1 - G_0^R\,\Sigma^R)^{-1}\,G_0^R\,\Sigma^<\,G^A = G^R\,(G_0^R)^{-1}\,G_0^R\,\Sigma^<\,G^A = G^R\,\Sigma^<\,G^A
$$

즉

$$
\boxed{G^<(E) = G^R(E)\,\Sigma^<(E)\,G^A(E)}
$$

이전 절들에서 사용한 **Keldysh 방정식** 의 도출. 이 방정식이 적용되는 조건은 다음 두 가지가 모두 만족될 때:

- 시스템이 정상상태
- 초기 분포가 무시 가능 (adiabatic switching 한계 또는 환경 결합으로 인한 점유 결정이 초기 조건을 압도)

이 조건이 깨지는 경우 (예: 초기 transient, 또는 시간 의존 외부 장의 갑작스러운 켜짐) 일반 lesser Dyson 방정식이 사용된다.

---

### 6. Greater Dyson 방정식과 다른 관계들

**1) Greater Dyson 방정식**

Lesser 와 비슷한 도출로

$$
G^>(t, t') = G_0^>(t, t') + \int\int dt_1\,dt_2\,\bigl[G_0^R(t, t_1)\,\Sigma^R(t_1, t_2)\,G^>(t_2, t') + G_0^R(t, t_1)\,\Sigma^>(t_1, t_2)\,G^A(t_2, t') + G_0^>(t, t_1)\,\Sigma^A(t_1, t_2)\,G^A(t_2, t')\bigr]
$$

정상상태 + adiabatic 에서

$$
G^>(E) = G^R(E)\,\Sigma^>(E)\,G^A(E)
$$

Lesser 와 같은 구조.

**2) Keldysh 항등식과의 일관성**

위 두 표현으로부터

$$
G^>(E) - G^<(E) = G^R(E)\,[\Sigma^>(E) - \Sigma^<(E)]\,G^A(E)
$$

좌변은 Keldysh 항등식으로 $G^R - G^A$ 와 같다.

$$
G^R - G^A = G^R\,(\Sigma^R - \Sigma^A)\,G^A
$$

(이전 절에서 도출한 $A(E) = G^R \Gamma G^A$ 의 도출 절차에서 사용한 결과와 일치.) 모든 결과가 일관성 있게 연결됨이 확인된다.

**3) 스펙트럼 함수**

$A(E) = i[G^R(E) - G^A(E)] = G^R(E)\,\Gamma(E)\,G^A(E)$ 도 동일한 도출로부터.

---

### 7. 정리: NEGF 의 완성된 framework

이 챕터에서 다룬 모든 결과를 종합하면 NEGF 의 완성된 framework 이 정리된다.

**1) 기본 객체**

- 시스템 Hamiltonian $H_s$, 환경 $H_e$, 결합 $V$
- 4 그린함수: $G^R, G^A, G^<, G^>$
- Self-energy: $\Sigma^R, \Sigma^A, \Sigma^<, \Sigma^>$
- 스펙트럼 함수: $A = i(G^R - G^A) = G^R \Gamma G^A$
- 결합 강도: $\Gamma = i(\Sigma^R - \Sigma^A) = -2\,\text{Im}\,\Sigma^R$

**2) Self-energy 의 도출**

블록 행렬 역연산으로

- $\Sigma^R = V\,g_e^R\,V^\dagger$
- $\Sigma^< = V\,g_e^<\,V^\dagger$

복수 reservoir 의 경우 합으로 분해:

- $\Sigma = \Sigma_L + \Sigma_R$
- $\Sigma^<_{L,R} = i\,f_{L,R}\,\Gamma_{L,R}$ (각 reservoir 평형)

**3) Dyson 방정식들 (정상상태 + adiabatic)**

- Retarded: $G^R = [E - H_s - \Sigma^R(E)]^{-1}$
- Advanced: $G^A = [G^R]^\dagger$
- Lesser (Keldysh equation): $G^< = G^R\,\Sigma^<\,G^A$
- Greater: $G^> = G^R\,\Sigma^>\,G^A$, 또는 항등식 $G^> = G^R - G^A + G^<$

**4) 관측량**

- 입자 밀도: $n(x) = -i\int dE/(2\pi)\,G^<(E, x, x)$
- 전류 (Meir-Wingreen): $I = (e/\hbar)\int dE/(2\pi)\,\text{Tr}[\Sigma^<\,G^> - \Sigma^>\,G^<]$
- 전류 (Landauer, 비상호작용): $I = (e/h)\int dE\,T(E)\,(f_L - f_R)$, $T = \text{Tr}[\Gamma_L\,G^R\,\Gamma_R\,G^A]$
- 일반: $\langle\hat O\rangle = -i\int dE/(2\pi)\,\text{Tr}[\hat O\,G^<(E)]$

**5) 시간 의존 또는 상호작용 시스템**

위 정상상태 결과들은 contour Dyson 방정식과 Langreth 룰의 자연스러운 특수 경우. 일반 시간 의존 또는 다체 상호작용 시스템에서는 contour formalism 의 일반 표현이 사용되며, 본 챕터의 framework 이 확장된다.

---

**example1) Retarded Dyson 방정식의 검증**

이전 절들에서 사용한 retarded Dyson 방정식을 Langreth 룰로 도출.

sol)

Contour Dyson $G^c = G_0^c + G_0^c \circ \Sigma^c \circ G^c$ 의 retarded component 추출.

$C^c = G_0^c \circ \Sigma^c \circ G^c$ 의 $C^R$ 은 Langreth 룰에서

$$
C^R = G_0^R \circ \Sigma^R \circ G^R
$$

(retarded convolution 끼리). 시간 영역에서

$$
G^R(t, t') = G_0^R(t, t') + \int dt_1\,dt_2\,G_0^R(t, t_1)\,\Sigma^R(t_1, t_2)\,G^R(t_2, t')
$$

정상상태에서 Fourier 변환:

$$
G^R(E) = G_0^R(E) + G_0^R(E)\,\Sigma^R(E)\,G^R(E)
$$

이는 weight 5 의 perturbative form Dyson 방정식과 일치. ✓ Closed form $G^R = (E - H_s - \Sigma^R)^{-1}$ 으로 환원.

---

**example2) Keldysh 방정식의 정상상태 도출 검증**

Steady state + adiabatic 한계에서 lesser Dyson 방정식이 Keldysh 방정식으로 환원됨을 명시적으로 확인.

sol)

일반 lesser Dyson 방정식 (§5-(3)):

$$
G^< = G_0^< + G_0^R \Sigma^R G^< + G_0^R \Sigma^< G^A + G_0^< \Sigma^A G^A
$$

$G_0^< = 0$ 가정 (adiabatic switching):

$$
G^< = G_0^R\,\Sigma^R\,G^< + G_0^R\,\Sigma^<\,G^A
$$

$G^<$ 에 대해 풀면

$$
(1 - G_0^R\,\Sigma^R)\,G^< = G_0^R\,\Sigma^<\,G^A
$$

Retarded Dyson 방정식의 닫힌 형태 $G^R = G_0^R + G_0^R\,\Sigma^R\,G^R$ 에서

$$
G^R\,(1 - \Sigma^R\,G^R) = G_0^R, \quad \text{or} \quad G_0^R = G^R\,(\Sigma^R\,G^R)^{-1}\cdot(\ldots)
$$

더 직접적으로는 $G^R = (1 - G_0^R \Sigma^R)^{-1}\,G_0^R$ 에서

$$
(1 - G_0^R\,\Sigma^R)^{-1} = G^R\,(G_0^R)^{-1}
$$

따라서

$$
G^< = (1 - G_0^R\,\Sigma^R)^{-1}\,G_0^R\,\Sigma^<\,G^A = G^R\,(G_0^R)^{-1}\,G_0^R\,\Sigma^<\,G^A = G^R\,\Sigma^<\,G^A
$$

즉

$$
G^<(E) = G^R(E)\,\Sigma^<(E)\,G^A(E)
$$

Keldysh 방정식 도출. ✓ 이전 절들에서 가정 없이 사용한 결과가 contour formalism + Langreth 룰 + adiabatic 가정으로부터 엄밀히 도출됨이 확인된다.

---

**example3) 두 reservoir 시스템의 일관된 정리**

두 reservoir 와 결합된 단순한 시스템 (양자수송 셋업) 에서 위의 모든 결과가 일관되게 작동함을 확인.

sol)

시스템: $H_s$ 알려진 작은 시스템. 좌우 두 reservoir, 각각 분포 $f_L, f_R$, 결합 강도 $\Gamma_L, \Gamma_R$.

**Step 1**: Self-energy 도출
- $\Sigma^R = \Sigma_L^R + \Sigma_R^R$, 각 $\Sigma_{L,R}^R = V_{L,R}\,g_{L,R}^R\,V_{L,R}^\dagger$
- $\Gamma_{L,R} = -2\,\text{Im}\,\Sigma_{L,R}^R$
- $\Sigma^< = i\,f_L\,\Gamma_L + i\,f_R\,\Gamma_R$

**Step 2**: Retarded 그린함수
$$
G^R(E) = [E - H_s - \Sigma_L^R - \Sigma_R^R]^{-1}
$$

**Step 3**: Lesser 그린함수 (Keldysh)
$$
G^<(E) = G^R\,(i f_L \Gamma_L + i f_R \Gamma_R)\,G^A
$$

**Step 4**: 관측량
- 입자 밀도: $n(x) = -i\int dE/(2\pi)\,G^<(E, x, x)$
- 전류 (Landauer): $I = (e/h)\int dE\,T(E)\,(f_L - f_R)$
- $T(E) = \text{Tr}[\Gamma_L\,G^R\,\Gamma_R\,G^A]$

**일관성 검증**:

평형 한계 ($f_L = f_R = f$):
$$
G^< = G^R\,(i f (\Gamma_L + \Gamma_R))\,G^A = i f\,G^R\,\Gamma\,G^A = i f\,A
$$

평형 분해 $G^< = i f A$ 회복.

전류: $f_L - f_R = 0$ 이므로 $I = 0$. 정상 ✓

비평형 ($\mu_L > \mu_R$): $f_L > f_R$ 의 영역에서 전류 흐름. 투과 $T(E)$ 가 시스템의 산란 특성을 결정.

이 모든 결과가 NEGF 의 일관된 framework 으로부터 자연스럽게 도출되며, 본 챕터의 모든 도구가 통합되어 작동함을 보여준다.
