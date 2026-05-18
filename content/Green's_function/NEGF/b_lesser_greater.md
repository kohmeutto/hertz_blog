+++
title = "(b) Lesser and greater GF"
weight = 4
+++

---

### 1. 동기: 점유 정보의 별도 추적

이전 절에서 스펙트럼 함수 $A(E)$ 가 시스템의 어떤 상태가 어떤 에너지에 있는지를 담는 객체임을 보았다. 그러나 비평형 시스템의 관측량 계산에는 추가 정보가 필요하다 — **그 상태들이 얼마나 채워져 있는가** 에 대한 정보. 즉 점유 (occupation) 정보.

평형 시스템에서는 이 정보가 Fermi-Dirac 분포 $f(E)$ 에 의해 결정되어 외부에서 단순히 주어진다. 시스템에 대해서는 스펙트럼 정보만 계산하면 모든 관측량이 따라온다.

비평형 시스템에서는 사정이 다르다. 예를 들어 시스템이 두 reservoir 와 결합되어 있고 각 reservoir 가 서로 다른 화학 퍼텐셜 $\mu_L, \mu_R$ 을 가질 때, 시스템 내부에는 단일 분포 함수가 존재하지 않는다. 위치와 에너지에 따라 다른 점유가 형성되며, 이 분포는 두 reservoir 의 영향과 시스템 자체의 동역학에 의해 결정된다.

이 점유 정보를 담는 객체가 **lesser 그린함수** $G^<(E)$ 이다. 짝이 되는 객체로 비점유 (정공) 정보를 담는 **greater 그린함수** $G^>(E)$ 도 정의된다. 평형에서는 두 그린함수가 스펙트럼 함수와 분포 함수의 곱으로 깔끔하게 분해되지만 ($G^< = i f A$, $G^> = -i(1-f) A$), 비평형에서는 이 분해가 깨지며 두 객체가 독립적으로 추적된다.

이 절에서는 두 그린함수의 정의, 평형 분해, 그리고 비평형에서의 결정 방식을 정리한다.

---

### 2. 정의

**1) 밀도 행렬에서 출발**

먼저 친숙한 객체에서 출발한다. 시스템의 단일 입자 **밀도 행렬 (density matrix)** 은 다음으로 정의된다.

$$
\rho(x, x') = \langle\hat{\psi}^\dagger(x')\,\hat{\psi}(x)\rangle
$$

여기서 $\hat{\psi}(x)$ 는 위치 $x$ 에서의 입자 소멸 연산자, $\hat{\psi}^\dagger(x')$ 는 위치 $x'$ 에서의 입자 생성 연산자이다. 평균 $\langle\cdot\rangle$ 은 시스템의 상태 (평형이든 비평형이든) 에 대한 기댓값.

평형 시스템에서 이 밀도 행렬은 명시적으로

$$
\rho_{eq}(x, x') = \sum_n f(E_n)\,\psi_n(x)\,\psi_n^*(x')
$$

여기서 $\psi_n$ 은 $H$ 의 고유 상태, $f(E)$ 는 Fermi-Dirac 분포. 각 상태가 점유 비율 $f(E_n)$ 에 따라 가중되어 밀도 행렬에 기여한다.

대각 성분 ($x = x'$) 이 위치별 입자 밀도이다.

$$
n(x) = \rho(x, x) = \sum_n f(E_n)\,|\psi_n(x)|^2
$$

밀도 행렬은 시스템의 모든 단일 입자 관측량을 계산할 수 있는 정보를 담는다. 그러나 평형에서는 외부 변수 $\mu, T$ 와 시스템 자체의 고유 상태로 환원되므로, 사실상 스펙트럼 정보만 알면 충분하다.

**2) 시간 영역의 두 점 상관 함수**

밀도 행렬을 시간 의존 객체로 일반화한다. Heisenberg picture 에서 시간 의존 장 연산자 $\hat{\psi}(x, t) = e^{iHt/\hbar}\hat{\psi}(x)e^{-iHt/\hbar}$ 를 사용해 다음을 정의한다.

$$
G^<(x, t; x', t') := i\,\langle\hat{\psi}^\dagger(x', t')\,\hat{\psi}(x, t)\rangle
$$

이를 **lesser 그린함수** 라 한다. 두 시간 $t, t'$ 에서의 장 연산자 곱의 평균값에 $i$ 를 곱한 형태이다.

동일 시간 ($t = t'$) 한계에서

$$
G^<(x, t; x', t)\bigg|_{t=t'} = i\,\langle\hat{\psi}^\dagger(x')\,\hat{\psi}(x)\rangle = i\,\rho(x, x')
$$

즉 동일 시간 lesser 그린함수가 밀도 행렬의 $i$ 배이다. $G^<$ 가 밀도 행렬을 시간 차이로 일반화한 객체임이 확인된다.

짝이 되는 객체

$$
G^>(x, t; x', t') := -i\,\langle\hat{\psi}(x, t)\,\hat{\psi}^\dagger(x', t')\rangle
$$

을 **greater 그린함수** 라 한다. 동일 시간 한계에서

$$
G^>(x, t; x', t)\bigg|_{t=t'} = -i\,\langle\hat{\psi}(x)\,\hat{\psi}^\dagger(x')\rangle = -i\,\bigl[\delta(x - x') - \rho(x, x')\bigr]
$$

여기서 페르미온의 반-교환 관계 $\{\hat{\psi}(x), \hat{\psi}^\dagger(x')\} = \delta(x - x')$ 를 사용했다. $G^>$ 가 빈 상태 (정공) 의 정보를 담는다.

**3) 에너지 영역으로의 Fourier 변환**

시스템이 정상상태에 있으면 $G^<(x, t; x', t')$ 가 시간 차이 $t - t'$ 에만 의존한다. Fourier 변환

$$
G^<(E, x, x') = \int_{-\infty}^{\infty} d\tau\,G^<(x, \tau; x', 0)\,e^{iE\tau/\hbar}, \quad \tau = t - t'
$$

비슷한 방식으로 $G^>(E, x, x')$ 정의. 두 객체는 에너지의 행렬 함수이다.

**4) 밀도 행렬과의 관계**

역 Fourier 변환을 $\tau = 0$ 에서 평가하면

$$
G^<(\tau = 0, x, x') = \int \frac{dE}{2\pi\hbar}\,G^<(E, x, x') = i\,\rho(x, x')
$$

(여기서 Fourier 규약에 따라 $1/(2\pi\hbar)$ 또는 $1/(2\pi)$ 의 인수가 등장하며, 본 문서에서는 단위 통일을 위해 $\hbar$ 를 적분 측도에 포함시키는 관행을 따른다.)

위치별 입자 밀도는

$$
\boxed{n(x) = -i\int_{-\infty}^{\infty} \frac{dE}{2\pi}\,G^<(E, x, x)}
$$

이것이 NEGF 의 가장 기본적인 관측량 공식이다.

---

### 3. 평형에서의 분해

평형 시스템에서 $G^<$ 와 $G^>$ 가 스펙트럼 함수와 분포 함수의 곱으로 분해됨을 도출한다.

**1) 시간 영역 표현**

평형 시스템에서 장 연산자의 모드 전개

$$
\hat{\psi}(x, t) = \sum_n c_n\,\psi_n(x)\,e^{-iE_n t/\hbar}
$$

와 평형 평균값 $\langle c_n^\dagger c_m\rangle_{eq} = f(E_n)\,\delta_{nm}$ 를 사용하면

$$
G^<(x, t; x', t') = i\sum_n f(E_n)\,\psi_n(x)\,\psi_n^*(x')\,e^{-iE_n(t-t')/\hbar}
$$

각 고유 상태가 평형 점유 비율 $f(E_n)$ 으로 가중되어 시간 차이 $t-t'$ 에 대한 진동을 일으킨다.

**2) 에너지 영역에서의 평형 분해**

위 표현을 Fourier 변환하면

$$
G^<(E, x, x') = i\sum_n f(E_n)\,\psi_n(x)\,\psi_n^*(x')\,2\pi\,\delta(E - E_n)
$$

여기서 스펙트럼 함수의 표현 $A(E, x, x') = 2\pi\sum_n\delta(E - E_n)\,\psi_n(x)\,\psi_n^*(x')$ 와 비교하면

$$
\boxed{G^<(E) = i\,f(E)\,A(E)}
$$

이 분해에서 $f(E)$ 는 Fermi-Dirac 분포이며, $A(E)$ 의 델타 함수 구조에 의해 자동으로 $f(E_n)$ 의 값으로 평가된다.

비슷한 도출로

$$
\boxed{G^>(E) = -i\,[1 - f(E)]\,A(E)}
$$

**3) 분해의 의미**

평형 시스템 정보의 깔끔한 구조가 다음과 같이 드러난다.

- $A(E)$: 스펙트럼 정보 — 시스템의 어떤 상태가 어디에 있는가
- $f(E)$: 점유 분포 — 그 상태가 얼마나 채워져 있는가
- $1 - f(E)$: 비점유 분포 — 정공

두 정보의 곱이 $G^<, G^>$ 이다. 평형 시스템 전체 정보는 사실 $A(E)$ 하나와 외부 변수 $\mu, T$ 로 환원된다. $G^<, G^>$ 가 독립 객체로서 등장할 이유는 비평형 처리를 위해서이다.

**4) 합 확인**

$G^>$ 와 $G^<$ 의 합:

$$
G^>(E) + G^<(E) = -i(1-f)A + i f A = -i A + 2i f A
$$

차이:

$$
G^>(E) - G^<(E) = -i(1-f)A - i f A = -i A
$$

차이가 단순하게 $-iA$ 로 나온다는 점이 다음 절의 항등식의 기초가 된다.

---

### 4. Keldysh 항등식

평형에서 검증한 결과 $G^>(E) - G^<(E) = -iA(E)$ 가 사실 비평형에서도 일반적으로 성립한다. 이를 **Keldysh 항등식** 또는 **spectral identity** 라 한다.

**1) 일반적 도출**

시간 영역에서 $G^R$ 과 $G^A$ 의 정의를 더 기본적인 객체 $G^<, G^>$ 로 표현하면

$$
G^R(x, t; x', t') = \theta(t - t')\,\bigl[G^>(x, t; x', t') - G^<(x, t; x', t')\bigr]
$$

$$
G^A(x, t; x', t') = -\theta(t' - t)\,\bigl[G^>(x, t; x', t') - G^<(x, t; x', t')\bigr]
$$

(증명은 anti-commutator $\{\hat{\psi}(x, t), \hat{\psi}^\dagger(x', t')\}$ 의 평균값이 $-i(G^> - G^<)$ 임을 사용하고, 인과적 / 반인과적 부분을 분리.)

두 식의 차이를 취하면

$$
G^R(t, t') - G^A(t, t') = \bigl[\theta(t-t') + \theta(t'-t)\bigr]\,\bigl[G^>(t, t') - G^<(t, t')\bigr]
$$

$\theta(t-t') + \theta(t'-t) = 1$ (단, $t = t'$ 의 측도 0 의 점 제외) 이므로

$$
G^R(t, t') - G^A(t, t') = G^>(t, t') - G^<(t, t')
$$

Fourier 변환 후 에너지 영역에서

$$
\boxed{G^R(E) - G^A(E) = G^>(E) - G^<(E)}
$$

이 결과가 비평형을 포함한 모든 상황에서 성립한다. 좌변은 §3 의 스펙트럼 함수와 직접 연결 ($G^R - G^A = -iA$), 우변은 점유와 비점유의 차.

**2) 평형에서의 검증**

평형에서 $G^< = ifA$, $G^> = -i(1-f)A$ 대입하면

$$
G^>(E) - G^<(E) = -i(1-f)A - ifA = -iA
$$

이는 $G^R - G^A = -iA$ 와 일치. ✓

**3) 4 그린함수의 독립성**

Keldysh 항등식은 4 그린함수가 모두 독립이 아니라 3 개만 독립임을 의미한다. 실용적으로 보통 $G^R, G^A, G^<$ 를 1 차 객체로 다루고, $G^>$ 는 항등식으로 도출한다.

$$
G^>(E) = G^R(E) - G^A(E) + G^<(E) = -iA(E) + G^<(E)
$$

평형에서 $G^< = ifA$ 대입하면 $G^> = -iA + ifA = -i(1-f)A$ 로 자동 복귀.

비평형에서도 이 도출은 유효하다. $G^<$ 가 어떤 비평형 형태이든, $G^>$ 는 $G^<$ 와 $A$ 로부터 결정된다.

---

### 5. 비평형에서의 $G^<$

평형 분해가 비평형에서 어떻게 깨지는지, 그리고 $G^<$ 가 어떻게 결정되는지를 본다.

**1) 평형 분해 깨짐의 원인**

평형에서 $G^<(E) = if(E)A(E)$ 의 단순 분해가 가능한 이유는 모든 상태가 단일 분포 $f(E)$ 에 따라 점유되기 때문이다.

비평형에서는 그렇지 않다. 시스템이 두 reservoir 와 결합되어 있고 각 reservoir 가 자신의 평형 분포를 가질 때:

- 좌측 reservoir: $f_L(E)$ (화학 퍼텐셜 $\mu_L$, 온도 $T_L$)
- 우측 reservoir: $f_R(E)$ (화학 퍼텐셜 $\mu_R$, 온도 $T_R$)

시스템 내부의 분포는 두 reservoir 가 주입하는 점유 흐름의 합성으로 결정된다. 위치와 에너지마다 다른 점유 비율이 형성된다. 단일 분포 $f_{\text{system}}(E)$ 가 존재하지 않는다.

**2) Keldysh 방정식**

비평형에서 $G^<$ 가 어떻게 결정되는지의 답은 다음 식이다.

$$
\boxed{G^<(E) = G^R(E)\,\Sigma^<(E)\,G^A(E)}
$$

이를 **Keldysh 방정식** 이라 한다. 우변의 $\Sigma^<(E)$ 는 **lesser self-energy** 로, 환경 (reservoir 들) 으로부터 시스템으로 주입되는 점유 정보를 담는다. 도출은 다음 절 (Dyson 방정식) 에서 자세히 다룬다.

두 reservoir 케이스에서

$$
\Sigma^<(E) = \Sigma_L^<(E) + \Sigma_R^<(E)
$$

각 reservoir 가 자신의 분포로 시스템에 점유를 주입한다.

$$
\Sigma_L^<(E) = i\,f_L(E)\,\Gamma_L(E), \quad \Sigma_R^<(E) = i\,f_R(E)\,\Gamma_R(E)
$$

여기서 $\Gamma_{L,R} = -2\,\text{Im}\,\Sigma_{L,R}^R$ 는 각 reservoir 와의 결합 강도.

이를 대입하면

$$
G^<(E) = G^R(E)\,\bigl[i\,f_L(E)\,\Gamma_L(E) + i\,f_R(E)\,\Gamma_R(E)\bigr]\,G^A(E)
$$

시스템 내부의 점유 분포가 두 reservoir 의 분포의 가중 평균으로 결정되며, 가중치는 시스템의 동역학 ($G^R, G^A$) 과 결합 강도 ($\Gamma_{L,R}$) 가 함께 만든다.

**3) 평형 극한에서의 환원**

평형 케이스 ($\mu_L = \mu_R = \mu$, $T_L = T_R = T$, 따라서 $f_L = f_R = f$) 에서 Keldysh 방정식이 평형 분해로 환원되는지 확인한다.

$\Gamma = \Gamma_L + \Gamma_R$ 라 정의하면

$$
G^<(E) = G^R\,[i f\,(\Gamma_L + \Gamma_R)]\,G^A = i f\,G^R\,\Gamma\,G^A
$$

이전 절에서 $A(E) = G^R\,\Gamma\,G^A$ 임을 보았으므로

$$
G^<(E) = i\,f(E)\,A(E)
$$

평형 분해 형태로 환원. ✓

**4) 비평형에서 분리 불가능성**

비평형에서 $f_L \neq f_R$ 일 때 위 단순화가 가능하지 않다.

$$
G^<(E) = G^R\,[i f_L \Gamma_L + i f_R \Gamma_R]\,G^A
$$

이 표현은 일반적으로 $i\,f_{\text{eff}}(E)\,A(E)$ 형태로 환원되지 않는다. 이유는 $f_L \Gamma_L + f_R \Gamma_R$ 가 $\Gamma_L + \Gamma_R = \Gamma$ 의 단일 배수가 아니기 때문이다. 두 reservoir 의 분포가 결합 행렬 $\Gamma_L, \Gamma_R$ 의 구조에 따라 혼합되는데, 이 혼합이 위치와 에너지에 의존하므로 단일 분포로 줄어들 수 없다.

---

### 6. 관측량

$G^<$ 가 단일 입자 정보의 완전한 담지체이며, 모든 단일 입자 관측량은 $G^<$ 로부터 계산된다.

**1) 입자 밀도**

이미 §2-4 에서 보았다.

$$
n(x) = -i\int_{-\infty}^{\infty} \frac{dE}{2\pi}\,G^<(E, x, x)
$$

평형에서

$$
n(x) = \int \frac{dE}{2\pi}\,f(E)\,A(E, x, x) = \int dE\,f(E)\,\rho(E, x)
$$

LDOS $\rho(E, x) = A(E, x, x)/(2\pi)$ 에 Fermi-Dirac 가중치를 곱한 적분. 비평형에서 $G^<$ 가 사용되어 일반화된다.

**2) 전류 밀도**

1D 시스템에서 전류 밀도는

$$
J(x) = \frac{e\hbar}{2m}\,\lim_{x'\to x}\bigl[\partial_{x'} - \partial_x\bigr]\,n(x, x')
$$

여기서 $n(x, x') = -i\int dE/(2\pi)\,G^<(E, x, x')$ 는 비대각 밀도 행렬. 두 점 사이의 운동량 전이 정보가 $G^<$ 의 비대각 성분에 담겨 있다.

평형에서는 $G^<(E, x, x')$ 가 대칭성에 의해 미분 후 0 — 정상상태 전류가 0 (자명). 비평형에서 두 reservoir 의 분포 차이로 인해 $G^<$ 가 비대칭이 되어 유한 전류가 흐른다.

**3) Reservoir 사이의 전류: Meir-Wingreen 공식**

좌측 reservoir 에서 시스템으로 들어오는 전류 (정상상태) 는

$$
I_L = \frac{e}{\hbar}\int \frac{dE}{2\pi}\,\text{Tr}\bigl[\Sigma_L^<(E)\,G^>(E) - \Sigma_L^>(E)\,G^<(E)\bigr]
$$

이를 **Meir-Wingreen 공식** 이라 한다. 두 항의 물리적 의미:

- $\Sigma_L^<\,G^>$: 좌측 reservoir 가 채워진 상태로 시스템의 빈 상태에 입자를 주입
- $\Sigma_L^>\,G^<$: 좌측 reservoir 의 빈 상태로 시스템의 채워진 상태에서 입자가 빠져나감

두 항의 차이가 정상상태 전류이다. 이 공식은 상호작용이 있는 일반 시스템에서도 성립한다.

**4) 비상호작용 극한: Landauer-Büttiker**

상호작용이 없는 시스템에서는 Meir-Wingreen 공식이 단순화된다.

$$
I = \frac{e}{h}\int dE\,T(E)\,[f_L(E) - f_R(E)]
$$

여기서

$$
T(E) = \text{Tr}\bigl[\Gamma_L(E)\,G^R(E)\,\Gamma_R(E)\,G^A(E)\bigr]
$$

가 **투과 함수 (transmission function)** 이다. 좌우 reservoir 의 분포 차이 $f_L - f_R$ 이 전류를 발생시키는 driving force 이고, $T(E)$ 가 그 에너지에서 전자가 좌에서 우로 통과할 확률을 나타낸다.

비상호작용 한계에서 $T(E)$ 가 시스템의 양자역학적 산란 특성으로 환원되며, 닫힌 시스템 그린함수의 Wronskian 공식과 직접 연결된다.

**5) 일반 단일 입자 관측량**

임의의 단일 입자 연산자 $\hat{O}$ 의 평균값은

$$
\langle\hat{O}\rangle = -i\int \frac{dE}{2\pi}\,\text{Tr}[\hat{O}\,G^<(E)]
$$

이 공식이 NEGF 의 모든 관측량 계산의 토대이다. 운동량 분포, 에너지 분포, 자기 모멘트 등 모든 단일 입자 관측량이 적절한 $\hat{O}$ 의 선택으로 도출된다.

---

**example1) 평형 양자 우물에서 $G^<$ 의 평형 분해**

1D 무한 우물 $H = -\hbar^2/(2m)\,d^2/dx^2$, $x \in [0, L]$, Dirichlet BC. 평형 시스템에서 $G^<$ 를 직접 계산하고 평형 분해를 확인.

sol)

고유 상태 $\psi_n(x) = \sqrt{2/L}\,\sin(n\pi x/L)$, 고유값 $E_n = (n\pi\hbar)^2/(2mL^2)$.

스펙트럼 함수

$$
A(E, x, x') = \frac{4\pi}{L}\sum_n \sin(n\pi x/L)\,\sin(n\pi x'/L)\,\delta(E - E_n)
$$

평형 분해 공식 $G^<(E) = if(E)\,A(E)$ 에서

$$
G^<(E, x, x') = \frac{4\pi i}{L}\,f(E)\sum_n \sin(n\pi x/L)\,\sin(n\pi x'/L)\,\delta(E - E_n)
$$

위치별 입자 밀도

$$
n(x) = -i\int \frac{dE}{2\pi}\,G^<(E, x, x) = \frac{2}{L}\sum_n f(E_n)\,\sin^2(n\pi x/L)
$$

각 고유 상태가 평형 점유 $f(E_n)$ 으로 가중되어 위치 분포에 기여. 표준 양자 통계 결과와 일치.

전체 입자 수

$$
N = \int_0^L dx\,n(x) = \sum_n f(E_n)
$$

각 고유 상태가 0 또는 1 의 점유 비율로 채워진다는 페르미온의 기본 결과.

---

**example2) 비대칭 두 reservoir 시스템**

두 reservoir 와 결합된 작은 시스템. 좌측 분포 $f_L$, 우측 분포 $f_R$, 두 reservoir 의 결합 강도 $\Gamma_L, \Gamma_R$ (행렬). 평형 분해가 어떻게 깨지는지 확인.

sol)

Keldysh 방정식

$$
G^<(E) = G^R(E)\,[i f_L \Gamma_L + i f_R \Gamma_R]\,G^A(E)
$$

$f_L = f_R = f$ 인 평형 극한에서

$$
G^<(E) = i f\,G^R\,(\Gamma_L + \Gamma_R)\,G^A = i f\,A(E)
$$

평형 분해 회복.

$f_L \neq f_R$ 인 비평형에서 시스템 내부의 효과적 점유 분포가 단일 함수로 표현되지 않는다. 그러나 한 가지 유용한 표현이 가능하다. **비평형 분포 함수** $f_{\text{neq}}(E, x)$ 를 다음으로 정의

$$
f_{\text{neq}}(E, x) := -i\,\frac{G^<(E, x, x)}{A(E, x, x)}
$$

(분자와 분모 모두 잘 정의된 양). 평형에서 $f_{\text{neq}} = f$, 비평형에서 위치와 에너지에 따라 변하는 분포 함수.

특히 단순한 모형 — 결합 강도가 위치 독립이며 비례 ($\Gamma_L = \alpha\,\Gamma, \Gamma_R = (1-\alpha)\,\Gamma$) — 에서는

$$
f_{\text{neq}}(E) = \alpha\,f_L(E) + (1-\alpha)\,f_R(E)
$$

두 reservoir 분포의 가중 평균. 시스템 내부 분포가 두 reservoir 분포의 보간 형태로 형성됨을 보여주는 직관적 결과.

일반 경우 ($\Gamma_L, \Gamma_R$ 비비례) 에서는 가중 평균이 위치와 에너지에 따라 변하며, 단일 분포 함수로 환원되지 않는다.
