+++
title = "(b) Keldysh contour formalism"
weight = 6
+++

---

### 1. 동기: 시간 영역 통합 framework 의 필요성

지금까지의 NEGF 접근은 에너지 영역에서 정상상태를 가정했다. 4 개의 그린함수 $G^R, G^A, G^<, G^>$ 를 별개의 객체로 도입하고, 각각의 Dyson 또는 Keldysh 방정식을 따로 다뤘다. 이 접근은 정상상태 비평형에서 잘 작동하지만, 두 가지 한계를 갖는다.

첫째, 시간 의존 시스템 — 시간에 따라 변하는 외부 장이 있거나, 초기 transient 응답을 관심하는 경우 — 에서는 에너지 영역으로의 단순한 Fourier 변환이 불가능하다. 시간 영역에서 직접 다뤄야 한다.

둘째, 4 그린함수가 서로 독립적인 객체가 아니라 단일 수학 구조의 서로 다른 측면이라는 사실이 명시적으로 드러나지 않는다. 이들의 통합적 처리가 가능한 framework 이 있다면 더 자연스럽고, 상호작용이 있는 다체 시스템으로의 확장도 명확해진다.

**Keldysh contour formalism** 이 이 통합 framework 을 제공한다. 핵심 아이디어는 시간을 forward 와 backward 두 방향으로 한 번씩 진행시키는 contour 위에 모든 객체를 정의하는 것이다. 이렇게 하면

- 단일 객체 $G^c(\tau, \tau')$ 가 4 그린함수 모두를 component 로 포함
- Contour 위의 Dyson 방정식이 모든 real-time 방정식을 단일로 표현
- 시간 의존 / 상호작용 시스템으로 자연스럽게 확장

이 절에서는 contour 의 도입, contour-ordered 그린함수의 정의, 그리고 4 그린함수가 어떻게 contour 위 단일 객체의 component 로 등장하는지를 정리한다.

---

### 2. Time evolution 과 Keldysh contour

**1) 비평형에서의 시간 진화 문제**

양자역학에서 시간 진화 연산자

$$
U(t, t_0) = T\exp\Bigl[-\frac{i}{\hbar}\int_{t_0}^t dt'\,H(t')\Bigr]
$$

가 시각 $t_0$ 에서 $t$ 로의 진화를 표현한다 ($T$ 는 시간 순서 정렬).

시각 $t$ 에서 임의 단일 입자 관측량의 평균값은 Heisenberg picture 에서

$$
\langle\hat O(t)\rangle = \text{Tr}\bigl[\hat\rho_0\,\hat O_H(t)\bigr] = \text{Tr}\bigl[\hat\rho_0\,U^\dagger(t, t_0)\,\hat O\,U(t, t_0)\bigr]
$$

여기서 $\hat\rho_0$ 는 초기 시각 $t_0$ 의 밀도 행렬, $\hat O_H(t) = U^\dagger(t, t_0)\hat O\,U(t, t_0)$ 는 Heisenberg 연산자.

이 표현에서 $U(t, t_0)$ 와 $U^\dagger(t, t_0) = U(t_0, t)$ 가 모두 등장하는 것에 주목하자. 오른쪽의 $U(t, t_0)$ 는 시간을 $t_0$ 에서 $t$ 로 forward 진행시키고, 왼쪽의 $U^\dagger(t, t_0)$ 는 다시 $t$ 에서 $t_0$ 로 backward 진행시킨다.

**2) Forward와 backward 시간 경로**

평형 시스템에서는 이 forward + backward 구조를 자연스럽게 압축할 수 있다. 평형 밀도 행렬 $\hat\rho_{eq} = e^{-\beta H}/Z$ 가 시간 진화 연산자와 같은 형태 ($-\beta H$ 가 허수 시간 $-i\beta\hbar$ 의 진화에 해당) 이므로, 전체를 단일 (Matsubara) 시간 적분으로 통합 가능하다.

비평형에서는 이 단순화가 불가능하다. 초기 밀도 행렬이 일반적이고, 외부 driving 이 시간 의존이므로 forward 와 backward 경로가 별개로 등장해야 한다. 이 두 시간 경로를 합쳐서 다음과 같이 시각화한다.

```
        forward branch C_+
t_0  ───────────────────────►  t
                              ║
                              ║ (turning point)
t_0  ◄───────────────────────  t
        backward branch C_-
```

위쪽 forward branch 와 아래쪽 backward branch 가 시각 $t$ 에서 만난다. 시간 변수 자체가 단순한 실수가 아니라 이 contour 위의 변수로 일반화된다.

**3) Contour 위의 시간 변수**

Contour 위의 변수 $\tau$ 는 두 가지 정보를 담는다.

- **시간 값** $t(\tau)$: 실수 시각
- **Branch 라벨**: $\tau$ 가 forward branch $C_+$ 또는 backward branch $C_-$ 중 어느 쪽에 있는가

두 점 $\tau, \tau'$ 의 contour 위에서의 순서 ($\tau >_c \tau'$ 또는 $\tau <_c \tau'$) 는 다음 규칙으로 결정된다.

- 둘 다 $C_+$ 위: 시간이 클수록 contour 위에서 나중. $t > t'$ ⇔ $\tau >_c \tau'$
- 둘 다 $C_-$ 위: 시간이 작을수록 contour 위에서 나중. $t < t'$ ⇔ $\tau >_c \tau'$
- $\tau \in C_-, \tau' \in C_+$: $C_-$ 가 항상 $C_+$ 보다 contour 위에서 나중. 시간과 무관하게 $\tau >_c \tau'$
- $\tau \in C_+, \tau' \in C_-$: 반대로 $\tau <_c \tau'$

이 ordering 을 **contour ordering** 이라 한다.

---

### 3. Contour-ordered Green's function

**1) 정의**

Contour 위에서 정의되는 단일 객체로 다음을 도입한다.

$$
\boxed{G^c(\tau, \tau'; x, x') := -i\langle T_c\bigl[\hat\psi(\tau, x)\,\hat\psi^\dagger(\tau', x')\bigr]\rangle}
$$

여기서 $T_c$ 는 **contour ordering 연산자** 로, contour 위에서 나중인 변수를 왼쪽으로 정렬한다.

$$
T_c[\hat A(\tau)\,\hat B(\tau')] = \begin{cases} \hat A(\tau)\,\hat B(\tau') & \tau >_c \tau' \\ \pm\,\hat B(\tau')\,\hat A(\tau) & \tau <_c \tau' \end{cases}
$$

부호: 페르미온 $-$, 보존 $+$.

**2) 4 가지 component**

$\tau, \tau'$ 의 branch 조합에 따라 $G^c$ 가 4 가지 case 로 나뉜다.

**Case 1: 둘 다 forward branch ($\tau, \tau' \in C_+$)**

이 경우 $\tau$ 와 $\tau'$ 의 contour ordering 이 일반 시간 ordering 과 같다. 따라서

$$
G^c(\tau, \tau') = G^T(t, t') := -i\,\langle T[\hat\psi(t, x)\,\hat\psi^\dagger(t', x')]\rangle
$$

여기서 $T$ 는 일반 시간 ordering 연산자. 이 객체를 **time-ordered 그린함수** 라 한다.

**Case 2: 둘 다 backward branch ($\tau, \tau' \in C_-$)**

이 경우 contour ordering 이 시간 ordering 과 반대이다. 따라서

$$
G^c(\tau, \tau') = G^{\tilde T}(t, t') := -i\,\langle\bar T[\hat\psi(t, x)\,\hat\psi^\dagger(t', x')]\rangle
$$

여기서 $\bar T$ 는 anti-time ordering 연산자 (시간이 작은 변수를 왼쪽으로 정렬). 이 객체를 **anti-time-ordered 그린함수** 라 한다.

**Case 3: $\tau \in C_+, \tau' \in C_-$**

이 경우 $\tau <_c \tau'$ 이므로 contour ordering 으로 페르미온이 swap with sign:

$$
G^c(\tau, \tau') = -i\cdot(-\langle\hat\psi^\dagger(t', x')\,\hat\psi(t, x)\rangle) = i\,\langle\hat\psi^\dagger(t', x')\,\hat\psi(t, x)\rangle = G^<(t, t')
$$

(이전 절에서 정의한 lesser 그린함수.)

**Case 4: $\tau \in C_-, \tau' \in C_+$**

이 경우 $\tau >_c \tau'$ 이므로 contour ordering 이 그대로 유지:

$$
G^c(\tau, \tau') = -i\,\langle\hat\psi(t, x)\,\hat\psi^\dagger(t', x')\rangle = G^>(t, t')
$$

(greater 그린함수.)

**3) 4 component 의 정리**

| Branch 조합 | $G^c$ | 이름 |
|---|---|---|
| $(C_+, C_+)$ | $G^T(t, t')$ | Time-ordered |
| $(C_-, C_-)$ | $G^{\tilde T}(t, t')$ | Anti-time-ordered |
| $(C_+, C_-)$ | $G^<(t, t')$ | Lesser |
| $(C_-, C_+)$ | $G^>(t, t')$ | Greater |

4 개의 그린함수가 모두 single $G^c$ 안에 component 로 포함된다.

---

### 4. 4 GFs 사이의 관계

Contour formalism 에서 도입된 $G^T, G^{\tilde T}$ 는 새로운 객체이지만, $G^<, G^>$ 와 단순한 관계로 연결된다.

**1) Time-ordered 와 anti-time-ordered 의 분해**

$G^T(t, t') = -i\langle T[\hat\psi(t)\hat\psi^\dagger(t')]\rangle$ 을 시간 순서에 따라 풀어쓴다.

$t > t'$ 일 때: $T$ 가 ordering 유지. $G^T = -i\langle\hat\psi(t)\hat\psi^\dagger(t')\rangle = G^>(t, t')$.

$t < t'$ 일 때: $T$ 가 swap with sign. $G^T = -i\cdot(-\langle\hat\psi^\dagger(t')\hat\psi(t)\rangle) = i\langle\hat\psi^\dagger\hat\psi\rangle = G^<(t, t')$.

종합하면

$$
G^T(t, t') = \theta(t - t')\,G^>(t, t') + \theta(t' - t)\,G^<(t, t')
$$

비슷한 도출로 anti-time-ordered:

$$
G^{\tilde T}(t, t') = \theta(t - t')\,G^<(t, t') + \theta(t' - t)\,G^>(t, t')
$$

**2) Retarded 와 advanced 그린함수와의 관계**

$G^R(t, t') = \theta(t - t')[G^>(t, t') - G^<(t, t')]$ (이전 절의 정의).

$G^T - G^<$ 를 계산하면

$$
G^T - G^< = \theta(t-t')G^> + \theta(t'-t)G^< - G^< = \theta(t-t')G^> - \theta(t-t')G^< = \theta(t-t')[G^> - G^<] = G^R
$$

비슷하게

$$
G^A(t, t') = G^<(t, t') - G^{\tilde T}(t, t')
$$

**3) 4 component 의 독립성**

위 관계들을 정리하면 다음과 같은 관계 표가 얻어진다.

| 관계 | 표현 |
|---|---|
| $G^T + G^{\tilde T}$ | $G^> + G^<$ |
| $G^T - G^{\tilde T}$ | $(G^> - G^<)\,\text{sgn}(t-t')$ |
| $G^R$ | $G^T - G^< = G^> - G^{\tilde T}$ |
| $G^A$ | $G^< - G^{\tilde T} = G^T - G^>$ |
| $G^R - G^A$ | $G^> - G^<$ (Keldysh 항등식) |

4 component 중 독립은 3 개 — 보통 $G^R, G^A, G^<$ 를 1 차 객체로 다루고 $G^>, G^T, G^{\tilde T}$ 를 도출한다.

**4) Keldysh 항등식의 재확인**

이전 절에서 도입한 Keldysh 항등식

$$
G^R(t, t') - G^A(t, t') = G^>(t, t') - G^<(t, t')
$$

이 contour formalism 의 자연스러운 귀결로 얻어진다. $G^R = G^> - G^{\tilde T}$ 와 $G^A = G^< - G^{\tilde T}$ 에서 $G^R - G^A = G^> - G^<$.

---

### 5. Contour Dyson 방정식

**1) Contour 위에서의 self-energy**

시스템이 환경과 결합되어 있을 때, contour 위에서의 self-energy $\Sigma^c(\tau, \tau')$ 가 정의된다. $G^c$ 와 마찬가지로 4 component 를 갖는다.

$$
\Sigma^T(t, t'), \quad \Sigma^{\tilde T}(t, t'), \quad \Sigma^<(t, t'), \quad \Sigma^>(t, t')
$$

각 component 는 환경의 contour-ordered 그린함수로부터 도출된다 — 이전 절의 $\Sigma^R = V\,g_e^R\,V^\dagger$ 와 비슷한 표현이 contour 위에서 일반화된다.

**2) Contour Dyson 방정식의 형태**

Contour 위에서의 Dyson 방정식은 다음 단일 표현이다.

$$
\boxed{G^c(\tau, \tau') = G_0^c(\tau, \tau') + \int_C d\tau_1\,d\tau_2\,G_0^c(\tau, \tau_1)\,\Sigma^c(\tau_1, \tau_2)\,G^c(\tau_2, \tau')}
$$

여기서 $\int_C$ 는 contour 위에서의 적분 — forward branch 적분 + backward branch 적분.

이 단일 방정식이 4 가지 real-time Dyson 방정식 (retarded, advanced, lesser, greater) 의 통합 표현이다. 각 real-time 방정식은 contour Dyson 방정식의 component 를 추출하면 얻어진다.

**3) Real-time 방정식의 도출**

Contour Dyson 방정식에서 $\tau, \tau'$ 의 branch 를 지정하면 real-time 방정식이 도출된다. 그러나 contour 적분 $\int_C d\tau_1$ 이 forward 와 backward 양쪽 branch 를 지나므로, 단순히 branch 를 지정하는 것 이상의 분석이 필요하다 — 이것이 **Langreth 룰** 이다.

예를 들어 contour Dyson 방정식의 $(C_+, C_+)$ component 를 추출하면

$$
G^T = G_0^T + (\text{내부 적분} \quad \tau_1\,\text{이} \quad C_+ \quad \text{또는} \quad C_- \quad \text{을 지나는 모든 경우의 합})
$$

내부 변수 $\tau_1$ 이 $C_+$ 일 때와 $C_-$ 일 때를 모두 합쳐야 하며, 이 합의 결과가 retarded Dyson 방정식 $G^R = G_0^R + G_0^R \Sigma^R G^R$ 의 자연스러운 표현이 된다. 자세한 룰은 다음 절에서 다룬다.

**4) 정상상태에서의 환원**

시스템이 정상상태에 있고 시간 의존성이 없으면, $G^c(\tau, \tau')$ 가 시간 차이 $t - t'$ 에만 의존한다. Fourier 변환 후 에너지 영역에서

- $(C_+, C_+)$: $G^T(E)$
- $(C_-, C_-)$: $G^{\tilde T}(E)$
- $(C_+, C_-)$: $G^<(E)$
- $(C_-, C_+)$: $G^>(E)$

이전 절에서 다룬 방정식들 — 에너지 영역 Dyson 방정식과 Keldysh 방정식 — 이 회복된다.

---

### 6. Contour formalism 의 확장성

Keldysh formalism 의 강점은 정상상태가 아닌 상황에서도 일관된 framework 으로 작동한다는 점이다.

**1) 시간 의존 외부 장**

$H(t) = H_0 + V_{\text{ext}}(t)$ — 외부 장 $V_{\text{ext}}(t)$ 가 시간 의존인 시스템. 예: gate voltage switching, AC bias, 펄스 레이저 자극.

이 경우 $G^c(\tau, \tau')$ 가 두 시간 $t, t'$ 의 일반 함수 (시간 차이만의 함수 아님). 그러나 contour Dyson 방정식의 구조는 그대로 유지된다. 시간 영역에서 직접 풀이가 필요하며, 에너지 영역의 단순 Fourier 변환은 가능하지 않다.

**2) Transient 응답**

특정 시각 $t_0$ 에서 외부 장이 켜졌을 때, $t > t_0$ 의 transient 응답. 정상상태로의 수렴 과정이 $G^c$ 의 시간 의존성에 담긴다.

특히 시간 의존 분포 함수의 진화가 $G^<$ 를 통해 추적된다. 정상상태로 가는 동안 분포가 어떻게 변화하는지의 자세한 정보가 얻어진다.

**3) 상호작용 시스템 (다체 NEGF)**

Keldysh formalism 의 가장 강력한 응용은 상호작용이 있는 다체 시스템이다. 상호작용 self-energy $\Sigma^c$ 가 perturbative 다이어그램으로 계산되며, 평형 양자장 이론의 Feynman 다이어그램 룰이 contour 위로 일반화된다.

이러한 확장된 응용은 후속 챕터에서 자세히 다룬다.

---

### 7. 정리: 두 가지 동등한 perspective

NEGF 는 두 가지 동등한 접근으로 정리된다.

**(1) Energy-domain perspective** (이전 절들에서 다룬 것)

- 정상상태 가정에서 Fourier 변환 사용
- $G^R(E), G^A(E), G^<(E), G^>(E)$ 가 1 차 객체
- Dyson 방정식과 Keldysh 방정식이 분리된 형태
- 수치 계산에 직접적
- 비상호작용 정상상태 문제에 효율적

**(2) Contour-time perspective** (이 절에서 도입)

- Forward + backward time contour
- 단일 $G^c(\tau, \tau')$ 로 4 그린함수 통합
- Contour Dyson 방정식이 단일 표현
- 시간 의존 / 상호작용 시스템으로 자연 확장
- 다체 NEGF 의 표준 framework

두 perspective 는 같은 물리를 기술하지만, 사용 맥락에 따라 한쪽이 편하다.

- **정상상태 + 비상호작용**: energy domain (이전 절들)
- **시간 의존 또는 상호작용**: contour time
- **두 perspective 의 연결**: 다음 절의 Langreth 룰

---

**example1) 평형 시스템에서 contour 그린함수 components 확인**

평형 시스템에서 4 그린함수 의 components 가 contour formalism 의 결과와 일치하는지 확인.

sol)

평형 분해로부터

$$
G^<(t, t') = i\sum_n f(E_n)\,\psi_n(x)\psi_n^*(x')\,e^{-iE_n(t-t')/\hbar}
$$

$$
G^>(t, t') = -i\sum_n (1-f(E_n))\,\psi_n(x)\psi_n^*(x')\,e^{-iE_n(t-t')/\hbar}
$$

$G^T$ 를 §4 의 표현에서 도출:

$$
G^T(t, t') = \theta(t-t')\,G^>(t,t') + \theta(t'-t)\,G^<(t,t')
$$

$t > t'$ 에서

$$
G^T(t, t') = -i\sum_n (1-f(E_n))\,\psi_n(x)\psi_n^*(x')\,e^{-iE_n(t-t')/\hbar}
$$

$t < t'$ 에서

$$
G^T(t, t') = i\sum_n f(E_n)\,\psi_n(x)\psi_n^*(x')\,e^{-iE_n(t-t')/\hbar}
$$

이는 평형 양자장 이론의 표준 time-ordered 그린함수 표현과 일치. ✓

**Sanity check**: $G^T - G^<$:

$$
G^T(t > t', t) - G^<(t > t', t) = -i\sum_n (1-f(E_n))(\ldots) - i\sum_n f(E_n)(\ldots) = -i\sum_n(\ldots)
$$

이는 $G^>(t > t', t) - G^<(t > t', t) = -i\sum_n(\ldots)$ ($G^R$ 의 $t > t'$ 영역) 과 일치. $G^R = \theta(t-t')[G^> - G^<]$ 검증.

---

**example2) 시간 의존 외부 장의 영향**

평형 시스템 ($t < t_0$ 에서) 에 $t = t_0$ 에서 외부 장 $V_{\text{ext}}(t > t_0)$ 가 켜진 경우. Transient 응답을 분석.

sol)

$t < t_0$ 의 평형에서 $G^<(E) = i f(E) A(E)$ 의 표준 평형 분해.

$t \geq t_0$ 에서 시스템은 비평형. $G^c(t, t')$ 가 시간 차이가 아닌 두 시간의 일반 함수.

Contour Dyson 방정식

$$
G^c(\tau, \tau') = G_0^c(\tau, \tau') + \int_C d\tau_1 d\tau_2\,G_0^c(\tau, \tau_1)\,\Sigma^c(\tau_1, \tau_2)\,G^c(\tau_2, \tau')
$$

에서 $\Sigma^c$ 가 환경 결합과 시간 의존 장 $V_{\text{ext}}(t)$ 의 기여를 합친 형태.

특히 lesser 그린함수의 시간 진화:

$$
G^<(t, t')\,\,\text{at} \,\,t, t' > t_0: \,\,\text{외부 장과 환경의 상호작용으로 진화}
$$

정상상태로의 수렴 시간 ($t \to \infty$): 환경 결합 강도 $\Gamma$ 의 역수 $\tau_{\text{relax}} = \hbar/\Gamma$ 정도.

이러한 시간 의존 문제는 Energy-domain 접근으로는 다룰 수 없으며, contour formalism 의 시간 영역 처리가 필수적이다. 자세한 계산은 후속 챕터에서 다룬다.
