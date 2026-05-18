+++
title = "(b) Landauer formula"
weight = 2
+++

---

### 1. 동기: 양자 영역에서 전류를 어떻게 계산하는가

이전 절에서 양자수송의 그림을 직관적으로 소개했다. 두 lead 가 산란 영역에 연결된 구조, 두 lead 의 분포 차이가 전류를 일으키는 driving force, 그리고 산란 영역의 양자역학적 산란 특성이 투과 확률 $T(E)$ 로 표현된다는 그림. 마지막에 Landauer 공식

$$
I = \frac{e}{h}\int dE\,T(E)\,[f_L(E) - f_R(E)]
$$

을 미리 소개했다.

이 절에서는 이 공식이 어떻게 도출되는지를 자세히 본다. 가장 단순한 경우 — 1D 단일 채널 — 에서 시작해서 점진적으로 다채널, 일반적 경우로 확장한다.

핵심 질문은 다음과 같다.

- Lead 의 분포 차이가 어떻게 정확히 전류로 환원되는가?
- 전류 공식에 왜 Planck 상수 $h$ 가 등장하는가?
- 산란 영역의 양자역학적 정보가 어떻게 $T(E)$ 한 함수로 압축되는가?

이 질문들에 답하는 과정에서 양자수송의 핵심 개념들 — 전도도 양자, 접촉 저항, 채널 — 이 자연스럽게 등장한다.

---

### 2. 시스템 설정: 1D 단일 채널

가장 단순한 양자수송 시스템에서 시작한다.

**1) 구조**

```
       [좌측 lead]    [산란 영역]    [우측 lead]
          x < 0       0 < x < L        x > L
          
          V = 0       V = V(x)         V = 0
          
          μ_L                          μ_R
          T_L                          T_R
```

좌측 lead 와 우측 lead 는 자유 입자 영역 (단순화를 위해 일정한 퍼텐셜 0). 산란 영역 ($0 < x < L$) 은 임의의 퍼텐셜 $V(x)$ 를 갖는다.

각 lead 는 자기 자신의 평형 상태에 있으며, 화학 퍼텐셜 $\mu_{L,R}$ 과 온도 $T_{L,R}$ 에 의해 분포 함수가 결정된다.

$$
f_L(E) = \frac{1}{e^{(E-\mu_L)/k_B T_L} + 1}, \quad f_R(E) = \frac{1}{e^{(E-\mu_R)/k_B T_R} + 1}
$$

전압 $V_b$ 가 인가되면 $\mu_L - \mu_R = eV_b$ 의 차이가 형성된다.

**2) Lead 의 입자 흐름**

좌측 lead 에서 양의 방향 ($k > 0$, 오른쪽으로) 진행하는 입자를 생각한다. 자유 입자이므로

$$
\psi_k^L(x) = \frac{1}{\sqrt{2\pi}}e^{ikx}, \quad E = \frac{\hbar^2 k^2}{2m}
$$

이 입자의 속도는

$$
v(k) = \frac{1}{\hbar}\frac{dE}{dk} = \frac{\hbar k}{m}
$$

좌측 lead 안에서 $E$ 와 $E + dE$ 사이의 에너지를 가진 양의 방향 입자의 흐름 (단위 시간당 단위 면적당) 은

$$
j_L^+(E)\,dE = \text{(밀도)} \times \text{(속도)} = \frac{dk}{2\pi}\,f_L(E)\cdot v(k)
$$

여기서 $dk/(2\pi)$ 는 1D 의 모드 밀도 (단위 길이당 모드 수, 양의 $k$ 만 고려). $f_L(E)$ 는 그 모드의 점유 확률.

$dk = dE/(\hbar v)$ 의 관계 ($dE/dk = \hbar v$) 를 사용하면

$$
j_L^+(E)\,dE = \frac{1}{2\pi\hbar v}\,f_L(E)\,v\,dE = \frac{1}{h}\,f_L(E)\,dE
$$

여기서 $2\pi\hbar = h$. **속도 $v$ 가 cancel 되어 사라진다**. 이는 1D 시스템의 특징적 결과로, 모든 에너지의 입자가 같은 비율로 흐름에 기여한다는 의미이다.

마찬가지로 우측 lead 에서 음의 방향 ($k < 0$, 왼쪽으로) 진행하는 입자의 흐름은

$$
j_R^-(E)\,dE = \frac{1}{h}\,f_R(E)\,dE
$$

**3) 투과 확률**

좌측 lead 에서 양의 방향으로 입사한 입자가 산란 영역을 통과해 우측 lead 에 도달할 확률을 $T(E)$ 라 한다. 통과하지 못한 입자는 반사되어 좌측 lead 로 돌아간다. 반사 확률을 $R(E)$ 라 하면

$$
T(E) + R(E) = 1
$$

(확률 보존). $T(E)$ 는 산란 영역의 퍼텐셜 $V(x)$ 에 의해 결정되며, 양자역학적 산란 문제의 해이다. 자세한 계산은 다음 문서에서 다룬다.

시간 역전 대칭에 의해 우측에서 좌측으로의 투과 확률도 $T(E)$ 와 같다. 즉 산란 영역은 양방향으로 같은 투과를 보인다.

---

### 3. Landauer 공식의 도출

위 설정으로부터 전류를 직접 계산한다.

**1) 좌측에서 우측으로 흐르는 전자 흐름**

좌측 lead 에서 양의 방향으로 진행한 후 산란 영역을 통과해 우측 lead 에 도달하는 전자의 흐름은

$$
\text{(좌측 lead 의 입자 흐름)} \times \text{(투과 확률)}
$$

이를 모든 에너지에 대해 적분하고 전하 $e$ 를 곱하면 전류:

$$
I_{L \to R} = e\int_{-\infty}^{\infty} dE\,j_L^+(E)\,T(E) = \frac{e}{h}\int dE\,T(E)\,f_L(E)
$$

**2) 우측에서 좌측으로 흐르는 전자 흐름**

마찬가지로

$$
I_{R \to L} = \frac{e}{h}\int dE\,T(E)\,f_R(E)
$$

**3) 순 전류**

좌에서 우로 흐르는 전류에서 우에서 좌로 흐르는 전류를 빼면

$$
I = I_{L \to R} - I_{R \to L} = \frac{e}{h}\int dE\,T(E)\,[f_L(E) - f_R(E)]
$$

이것이 **단일 채널 Landauer 공식** 이다.

**4) 스핀 자유도**

전자의 스핀 (up/down) 을 고려하면 스핀당 한 채널씩, 총 2 개 채널이 동일한 기여를 한다. 인수 2 가 곱해진다.

$$
\boxed{I = \frac{2e}{h}\int dE\,T(E)\,[f_L(E) - f_R(E)]}
$$

이것이 1D 단일 채널 (양 스핀 포함) 의 Landauer 공식이다.

**5) Planck 상수의 등장**

도출 과정에서 $h$ 가 어떻게 등장하는지 주목하자. $h = 2\pi\hbar$ 는 1D 모드 밀도 $dk/(2\pi)$ 와 에너지-운동량 관계 $dE/dk = \hbar v$ 가 결합되어 나타난다. 양자역학의 fundamental 상수가 전류 공식에 직접 등장하는 것이 양자수송의 특징이다.

---

### 4. 선형 응답: 전도도 양자

작은 전압 $V_b$ 에 대한 응답을 계산한다.

**1) 화학 퍼텐셜 차의 작은 한계**

$\mu_L = \mu + eV_b/2$, $\mu_R = \mu - eV_b/2$ 라 하면 $\mu_L - \mu_R = eV_b$. 작은 $V_b$ 에서 Fermi-Dirac 분포의 차이를 전개:

$$
f_L(E) - f_R(E) = -\frac{\partial f}{\partial E}\,eV_b + O(V_b^3)
$$

여기서 $f(E) = 1/[e^{(E-\mu)/k_B T} + 1]$ 는 평균 화학 퍼텐셜 $\mu$ 의 Fermi-Dirac.

**2) 선형 응답 전류**

위 전개를 Landauer 공식에 대입:

$$
I = \frac{2e}{h}\int dE\,T(E)\,\bigl[-\frac{\partial f}{\partial E}\bigr]\,eV_b = \frac{2e^2 V_b}{h}\int dE\,T(E)\,\bigl[-\frac{\partial f}{\partial E}\bigr]
$$

저온 한계 ($k_B T \ll$ 산란 영역의 에너지 스케일) 에서 $-\partial f/\partial E \approx \delta(E - \mu)$ 이므로

$$
I \approx \frac{2e^2}{h}\,T(\mu)\,V_b
$$

**3) 전도도**

$G = I/V_b$ 로 정의되는 전도도

$$
\boxed{G = \frac{2e^2}{h}\,T(\mu)}
$$

이 표현이 단일 채널의 **선형 응답 Landauer 공식** 이다. 산란 영역의 양자역학적 특성이 Fermi 에너지에서의 투과 확률 $T(\mu)$ 한 숫자로 압축되어 전도도를 결정한다.

**4) 완전 투과 한계**

$T(\mu) = 1$ (산란 영역이 입자를 완전히 통과시킴) 인 경우

$$
G_0 := \frac{2e^2}{h} \approx 7.75 \times 10^{-5}\,\text{S}
$$

또는 저항으로

$$
R_0 = \frac{h}{2e^2} \approx 12.9\,\text{k}\Omega
$$

이를 **전도도 양자 (conductance quantum)** 라 한다. 이는 단일 채널의 양자수송 한계 — 산란이 전혀 없는 1D 채널 — 에서의 최대 전도도이다.

이 값이 자연 상수 $h, e$ 로만 결정되며 물질에 무관하다는 사실이 중요한 의미를 갖는다. 양자수송에서 전도도는 물질의 성질이 아닌 **순수한 양자역학적 산란 특성** 에 의해 결정된다.

---

### 5. 다채널 일반화

실제 도체는 횡 방향 (전류 방향에 수직) 으로도 유한한 폭을 가진다. 이 폭에 따라 여러 개의 횡 모드 (transverse mode) 가 존재하며, 각 모드가 독립적인 채널로 작동한다.

**1) 횡 모드**

폭 $W$ 의 도체에서 횡 방향 양자화가 일어나면 횡 모드 $n = 1, 2, 3, \ldots$ 가 형성된다. 각 모드는 자기 자신의 횡 에너지 $E_n^\perp$ 를 가지며, 종 방향 (수송 방향) 운동 에너지는

$$
E_\parallel = E - E_n^\perp
$$

총 에너지 $E$ 의 입자가 모드 $n$ 으로 전파되려면 $E > E_n^\perp$ 이어야 한다. 이를 만족하지 않는 모드는 그 에너지에서 "닫혀 있다" (closed channel).

**2) 채널별 투과**

각 모드 $n$ 에 대해 산란 영역을 통과할 투과 확률 $T_n(E)$ 가 정의된다. 단순한 경우 (산란 영역이 모드 사이 결합을 일으키지 않음) 각 채널은 독립적으로 처리된다.

총 투과 함수

$$
T(E) = \sum_{n: E > E_n^\perp} T_n(E)
$$

(닫힌 모드 $E \leq E_n^\perp$ 는 합에서 제외.)

**3) 다채널 Landauer 공식**

각 채널이 독립적으로 단일 채널 공식을 따르므로 총 전류는 합:

$$
I = \frac{2e}{h}\int dE\,\bigl[\sum_n T_n(E)\bigr]\,[f_L(E) - f_R(E)] = \frac{2e}{h}\int dE\,T(E)\,[f_L(E) - f_R(E)]
$$

선형 응답 전도도:

$$
G = \frac{2e^2}{h}\sum_n T_n(\mu) = \frac{2e^2}{h}\,T(\mu)
$$

**4) 모드 사이 결합**

산란 영역이 모드 사이 결합을 일으키는 일반적인 경우, $T(E)$ 는 행렬 표현으로 일반화된다. 채널 $m$ 에서 채널 $n$ 으로의 투과 진폭을 $t_{nm}(E)$ 라 하면 투과 확률 행렬

$$
T_{nm}(E) = |t_{nm}(E)|^2
$$

총 투과 함수는

$$
T(E) = \sum_{nm} T_{nm}(E) = \text{Tr}[t^\dagger\,t]
$$

이 표현이 NEGF 에서 도출한 $T(E) = \text{Tr}[\Gamma_L G^R \Gamma_R G^A]$ 와 일치한다. 자세한 도출은 §7 에서.

---

### 6. 접촉 저항의 양자역학적 의미

완전 ballistic 시스템 — 산란 영역 안에서 어떠한 산란도 일어나지 않는 — 의 전도도가 무한대가 아니라는 사실은 중요한 의미를 갖는다.

**1) 한계 저항의 존재**

모든 열린 채널이 완전 투과 ($T_n = 1$) 일 때

$$
G = \frac{2e^2}{h}\,N
$$

여기서 $N$ 은 열린 채널 수. 저항은

$$
R = \frac{h}{2e^2 N}
$$

이 한계 저항은 0 이 아니다 (유한). 즉 ballistic 시스템에서도 유한한 저항이 존재한다. 옴의 법칙 $R = \rho L/A$ 에 따르면 산란이 없으면 ($\rho = 0$) 저항이 0 이어야 하므로 모순.

**2) Lead 와 시스템의 mismatch**

이 한계 저항의 양자역학적 기원은 lead 와 산란 영역 사이의 mismatch 에 있다.

Lead 는 (이상적으로) 무한 크기의 reservoir 이며, 무한히 많은 모드를 가진다. 산란 영역은 유한한 폭이므로 유한한 모드 수 $N$ 만 가진다. 전자가 lead 에서 산란 영역으로 진입할 때, 무한 모드 공간에서 유한 모드 공간으로의 사영이 일어난다.

이 사영 과정 자체가 양자역학적 산란 — 정보 손실 — 을 일으킨다. 무한 모드 중 일부만이 산란 영역의 채널과 결합되며, 나머지는 lead 안에서 반사된다.

**3) 접촉 저항의 정량적 해석**

$N$ 개 모드를 가진 ballistic 시스템의 한계 저항

$$
R = \frac{h}{2e^2 N}
$$

은 전체 회로의 접촉 (contact) 에서 발생한다. 두 lead-시스템 접촉을 각각 $R_{\text{contact}}/2 = h/(4e^2 N)$ 으로 균등 분담하는 그림으로 해석 가능하다.

채널 수가 늘어나면 ($N$ 증가) 접촉 저항이 감소한다. 무한 채널 한계 ($N \to \infty$) 에서 $R \to 0$ — 옴 영역으로의 환원.

**4) 거시적 시스템과의 부드러운 연결**

거시적 시스템에서 채널 수가 $N \sim A/\lambda_F^2 \gg 1$ 이고, 산란 영역 안의 산란이 추가되어 각 채널의 $T_n < 1$. 옴의 법칙은 큰 $N$ 한계에서 부드럽게 회복된다.

거시적 옴의 법칙과 ballistic Landauer 공식이 같은 framework 의 양 극한 한계임을 보여주는 결과.

---

### 7. NEGF 표현과의 연결

위에서 도출한 1D 단일 채널 공식이 NEGF 챕터의 일반 표현 $T(E) = \text{Tr}[\Gamma_L G^R \Gamma_R G^A]$ 와 일치함을 확인한다.

**1) 단일 사이트 시스템**

가장 단순한 NEGF 시스템: 한 개의 사이트가 두 lead 와 결합 (산란 영역 차원 $N_s = 1$).

$H_s = \epsilon_0$ (스칼라).

Wide-band 근사: $\Sigma_L^R = -i\Gamma_L/2$, $\Sigma_R^R = -i\Gamma_R/2$. ($\Gamma_{L,R}$ 도 스칼라.)

Retarded 그린함수:

$$
G^R(E) = \frac{1}{E - \epsilon_0 + i(\Gamma_L + \Gamma_R)/2}
$$

투과 함수 (단일 사이트라 trace 가 곱 = 곱):

$$
T(E) = \Gamma_L\,G^R\,\Gamma_R\,G^A = \frac{\Gamma_L\,\Gamma_R}{(E - \epsilon_0)^2 + (\Gamma_L + \Gamma_R)^2/4}
$$

대칭 결합 ($\Gamma_L = \Gamma_R = \Gamma$) 에서

$$
T(E) = \frac{\Gamma^2}{(E - \epsilon_0)^2 + \Gamma^2}
$$

$E = \epsilon_0$ 에서 $T = 1$ (완전 투과). 에너지가 $\epsilon_0$ 에서 멀어지면 $T$ 가 Lorentzian 으로 감소.

**2) Landauer 공식과의 통합**

전류:

$$
I = \frac{2e}{h}\int dE\,T(E)\,[f_L(E) - f_R(E)]
$$

저온 + 작은 $V_b$ 한계의 전도도:

$$
G = \frac{2e^2}{h}\,T(\mu) = \frac{2e^2}{h}\cdot\frac{\Gamma^2}{(\mu - \epsilon_0)^2 + \Gamma^2}
$$

$\mu = \epsilon_0$ 에서 (Fermi 에너지가 시스템의 에너지 레벨과 일치) $G = 2e^2/h$ — 전도도 양자에 도달.

**3) 1D 산란 시스템에서의 검증**

1D 산란 시스템 (barrier 또는 더 복잡한 퍼텐셜) 에서 양자역학적 산란 진폭 $t(E)$ (transmission amplitude) 이 정의되며, 그 절댓값 제곱이 투과 확률.

$$
T(E) = |t(E)|^2
$$

NEGF 표현 $T = \text{Tr}[\Gamma_L G^R \Gamma_R G^A]$ 가 단일 채널 시스템에서 정확히 $|t|^2$ 와 일치함이 도출된다. 자세한 도출은 다음 문서 (transmission and scattering) 에서.

두 표현 — 직관적 입자 흐름 분석에서 도출한 Landauer 공식과 NEGF 의 추상적 framework — 이 양자수송의 같은 현상을 다른 관점에서 기술한다.

---

**example1) 자유 1D 채널**

산란 영역이 없는 (또는 산란 영역 = 자유 입자) 1D 시스템. $V(x) = 0$ 모든 곳에서.

sol)

산란이 없으므로 모든 에너지에서 $T(E) = 1$. Landauer 공식

$$
I = \frac{2e}{h}\int dE\,[f_L(E) - f_R(E)]
$$

저온 ($k_B T \to 0$) 에서 $f_{L,R}(E) = \theta(\mu_{L,R} - E)$. 따라서

$$
I = \frac{2e}{h}\int_{\mu_R}^{\mu_L} dE = \frac{2e}{h}(\mu_L - \mu_R) = \frac{2e^2}{h}\,V_b
$$

전도도

$$
G = \frac{I}{V_b} = \frac{2e^2}{h} = G_0
$$

전도도 양자 한계에 정확히 도달.

저항 $R = 12.9\,\text{k}\Omega$.

물리적 그림: 산란이 전혀 없는데도 유한 저항이 존재. 이 저항은 lead 와 시스템 사이의 양자역학적 접촉에서 발생한다.

---

**example2) 1D 직사각 barrier 의 투과**

산란 영역이 직사각 barrier:

$$
V(x) = \begin{cases} V_0 & 0 < x < L \\ 0 & \text{otherwise} \end{cases}
$$

투과 확률을 양자역학으로 직접 계산하고 Landauer 공식에 대입.

sol)

표준 양자역학 결과 (1D 직사각 barrier scattering):

$E < V_0$ (barrier 아래, 터널링) 의 경우:

$$
T(E) = \bigl[1 + \frac{V_0^2 \sinh^2(\kappa L)}{4E(V_0 - E)}\bigr]^{-1}, \quad \kappa = \frac{\sqrt{2m(V_0 - E)}}{\hbar}
$$

$\kappa L \gg 1$ (두꺼운 barrier) 의 한계에서

$$
T(E) \approx \frac{16 E(V_0 - E)}{V_0^2}\,e^{-2\kappa L}
$$

지수 $e^{-2\kappa L}$ 의 인자가 터널링 확률의 기본 의존성.

$E > V_0$ (barrier 위, 부분 반사) 의 경우:

$$
T(E) = \bigl[1 + \frac{V_0^2 \sin^2(k' L)}{4E(E - V_0)}\bigr]^{-1}, \quad k' = \frac{\sqrt{2m(E - V_0)}}{\hbar}
$$

특정 에너지에서 $\sin(k' L) = 0$, 즉 $k' L = n\pi$ 의 조건에서 $T = 1$ (완전 투과, **resonant transmission**).

선형 응답 전도도

$$
G(\mu) = \frac{2e^2}{h}\,T(\mu)
$$

$\mu < V_0$ (Fermi 에너지가 barrier 아래): 터널링 영역. $G$ 가 매우 작음.

$\mu > V_0$ (Fermi 에너지가 barrier 위): 부분 반사 영역. $G$ 가 에너지에 따라 진동하며, 특정 에너지에서 $G = 2e^2/h$ 의 양자화된 한계에 도달.

이 단순 예제가 양자수송의 두 핵심 현상 — 터널링과 공명 투과 — 을 모두 보여준다.
