+++
title = "(b) Transmission and scattering"
weight = 4
+++

---

### 1. 동기: $T(E)$ 를 어떻게 계산하는가

Landauer 와 Büttiker 공식에서 핵심적인 양은 투과 함수 $T(E)$ 이다. 그러나 두 공식 모두 $T(E)$ 가 산란 영역의 양자역학적 산란 특성에서 결정된다고만 했지, 어떻게 계산하는지는 자세히 다루지 않았다.

이 절에서 그 계산 방법을 정리한다. 핵심 도구는 1D 양자역학적 산란 이론이다. 시간 무관 Schrödinger 방정식을 풀고, 입사파 + 반사파 + 투과파의 진폭을 매칭해서 투과 확률을 얻는다.

다룰 내용:

- 산란 진폭과 투과 확률
- Transfer matrix 방법 (여러 영역을 효율적으로 합성)
- 대표적 예: 단일 barrier, 직사각 우물, 이중 barrier (공명 투과)
- NEGF 표현 $T = \text{Tr}[\Gamma_L G^R \Gamma_R G^A]$ 와의 일치 증명

처음 산란을 배우는 사람도 따라갈 수 있도록 단계적으로 진행한다.

---

### 2. 산란 진폭과 투과 확률

**1) 1D 산란 문제의 설정**

다음 구조의 1D 시스템을 다룬다.

```
       [좌측 lead]        [산란 영역]       [우측 lead]
        x < 0              0 < x < L         x > L
        V(x) = 0           V(x) = ?          V(x) = 0
```

좌측과 우측 lead 에서는 자유 입자 ($V = 0$). 산란 영역의 퍼텐셜 $V(x)$ 는 임의 형태.

**2) 각 영역의 파동 함수**

에너지 $E$ 의 입자가 좌측에서 입사하는 경우를 고려한다 (오른쪽으로 진행). $k = \sqrt{2mE}/\hbar$ 라 하면:

**좌측 lead** ($x < 0$): 자유 입자, 입사파와 반사파의 중첩.

$$
\psi_L(x) = e^{ikx} + r\,e^{-ikx}
$$

여기서 $e^{ikx}$ 가 입사파 (단위 진폭으로 정규화), $r\,e^{-ikx}$ 가 반사파. $r$ 은 **반사 진폭 (reflection amplitude)** — 복소수.

**우측 lead** ($x > L$): 자유 입자, 투과파만 (오른쪽으로 진행하는 입자만).

$$
\psi_R(x) = t\,e^{ikx}
$$

$t$ 는 **투과 진폭 (transmission amplitude)** — 복소수.

**산란 영역** ($0 < x < L$): 퍼텐셜 $V(x)$ 에 의해 결정되는 일반적 파동 함수. 자세한 형태는 $V(x)$ 의 종류에 따라 다름.

**3) 투과 확률과 반사 확률**

$T(E) = |t|^2$, $R(E) = |r|^2$.

확률 보존 — 입자가 어딘가로 (반사 또는 투과) 가야 하므로

$$
T(E) + R(E) = 1
$$

(증명은 시간 무관 Schrödinger 방정식의 확률 흐름 $j = \hbar\,\text{Im}[\psi^*\partial_x\psi]/m$ 가 모든 곳에서 일정하다는 사실에서 따라옴.)

**4) 일반 절차**

$T(E)$ 를 계산하려면:

(a) 산란 영역 안에서 Schrödinger 방정식의 해 $\psi_S(x)$ 를 구한다.
(b) 경계 ($x = 0$ 과 $x = L$) 에서 파동 함수와 그 미분의 연속성을 부과한다.
(c) 매칭 조건을 풀어 $r, t$ 를 결정한다.
(d) $T(E) = |t|^2$ 계산.

단계 (c) 가 작은 시스템에서는 직접 가능하지만, 복잡한 시스템에서는 다음에 다룰 transfer matrix 방법이 효율적이다.

---

### 3. Transfer matrix 방법

**1) 동기**

산란 영역이 여러 부분으로 구성된 경우 (예: 두 개의 barrier 사이에 우물), 각 영역의 매칭을 따로 다루는 것은 번거롭다. Transfer matrix 방법은 각 영역의 효과를 $2 \times 2$ 행렬로 표현하고, 영역들의 합성을 행렬 곱으로 처리한다.

**2) 상태 벡터의 정의**

위치 $x$ 에서 파동 함수와 그 미분을 묶어 2 성분 벡터로 정의:

$$
\Psi(x) = \begin{pmatrix} \psi(x) \\ \psi'(x) \end{pmatrix}
$$

이 벡터가 시스템의 양자역학적 상태를 한 점에서 완전히 결정한다 (2차 미분방정식이므로 두 개의 초기 조건이 해를 결정).

**3) Transfer matrix 의 정의**

영역 $[x_1, x_2]$ 의 transfer matrix $M$ 은 $\Psi(x_1)$ 을 $\Psi(x_2)$ 로 보내는 행렬이다.

$$
\Psi(x_2) = M\,\Psi(x_1)
$$

$M$ 은 $2 \times 2$ 행렬이며, 그 영역의 퍼텐셜에 의해 결정된다.

**4) 합성 규칙**

여러 영역을 차례로 통과하는 경우 transfer matrix 가 곱셈으로 합성된다.

$$
\Psi(x_3) = M_{23}\,\Psi(x_2) = M_{23}\,M_{12}\,\Psi(x_1)
$$

$M_{\text{total}} = M_{23}\,M_{12}$. 순서 주의 — 오른쪽 행렬이 먼저 작용.

**5) 단순한 예: 일정 퍼텐셜 영역**

영역 $[x_1, x_2]$ 에서 퍼텐셜이 일정값 $V$ 이고 $E > V$ 인 경우. 파동 수 $k = \sqrt{2m(E - V)}/\hbar$. 일반 해

$$
\psi(x) = A\,e^{ik(x - x_1)} + B\,e^{-ik(x - x_1)}
$$

$\psi(x_1) = A + B$, $\psi'(x_1) = ik(A - B)$. 마찬가지로 $x = x_2$ 에서. 두 점 사이의 transfer matrix:

$$
M = \begin{pmatrix} \cos(k\,d) & \sin(k\,d)/k \\ -k\sin(k\,d) & \cos(k\,d) \end{pmatrix}, \quad d = x_2 - x_1
$$

$E < V$ (터널링 영역) 인 경우 $\kappa = \sqrt{2m(V - E)}/\hbar$ 로 두면 sinusoid 가 hyperbolic 함수로 교체:

$$
M = \begin{pmatrix} \cosh(\kappa d) & \sinh(\kappa d)/\kappa \\ \kappa\sinh(\kappa d) & \cosh(\kappa d) \end{pmatrix}
$$

이 두 단순 transfer matrix 가 복잡한 시스템의 빌딩 블록.

**6) 투과 진폭의 도출**

전체 시스템의 transfer matrix $M_{\text{total}}$ 이 주어지면, 좌측 lead 의 입사/반사 진폭과 우측 lead 의 투과 진폭을 매칭해 $t, r$ 을 얻는다.

좌측 lead 의 $\Psi(0) = \begin{pmatrix} 1 + r \\ ik(1 - r) \end{pmatrix}$ (입사파 단위 진폭).

우측 lead 의 $\Psi(L) = \begin{pmatrix} t \\ ikt \end{pmatrix}$ (투과파만).

매칭 $\Psi(L) = M_{\text{total}}\,\Psi(0)$ 에서 두 식이 나오고, 미지수 $r, t$ 를 결정한다.

자세한 도출은 다음 example 에서.

---

### 4. 단일 직사각 barrier

**1) 시스템 설정**

$$
V(x) = \begin{cases} V_0 & 0 < x < L \\ 0 & \text{otherwise} \end{cases}
$$

높이 $V_0$, 폭 $L$ 의 단순 barrier.

**2) Transfer matrix**

Barrier 안에서 ($E < V_0$, 터널링): $\kappa = \sqrt{2m(V_0 - E)}/\hbar$.

$$
M_{\text{barrier}} = \begin{pmatrix} \cosh(\kappa L) & \sinh(\kappa L)/\kappa \\ \kappa\sinh(\kappa L) & \cosh(\kappa L) \end{pmatrix}
$$

**3) 투과 진폭**

매칭 절차 수행 결과:

$$
t(E) = \frac{2ik\kappa}{2ik\kappa\cosh(\kappa L) + (k^2 - \kappa^2)\sinh(\kappa L)}
$$

(여기서 $k = \sqrt{2mE}/\hbar$ 는 lead 의 파동 수.)

투과 확률 $T = |t|^2$. 계산하면

$$
T(E) = \frac{1}{1 + \frac{V_0^2 \sinh^2(\kappa L)}{4E(V_0 - E)}}, \quad E < V_0
$$

**4) 두꺼운 barrier 한계**

$\kappa L \gg 1$ 인 한계 (barrier 가 두껍거나 에너지가 낮음). $\sinh(\kappa L) \approx e^{\kappa L}/2$ 이므로

$$
T(E) \approx \frac{16 E (V_0 - E)}{V_0^2}\,e^{-2\kappa L}
$$

지수 인자 $e^{-2\kappa L}$ 이 터널링 확률의 기본 의존성. $\kappa L$ 이 작아질수록 (barrier 가 얇거나 에너지가 barrier 에 가까워질수록) 투과가 커진다.

이 단순 결과가 양자수송의 가장 기본적 현상 — **터널링** — 을 정량적으로 보여준다.

**5) Barrier 위 에너지**

$E > V_0$ 인 경우. 내부 파동 수 $k' = \sqrt{2m(E - V_0)}/\hbar$.

$$
T(E) = \frac{1}{1 + \frac{V_0^2 \sin^2(k' L)}{4E(E - V_0)}}, \quad E > V_0
$$

특정 에너지에서 $\sin(k' L) = 0$, 즉

$$
k' L = n\pi, \quad n = 1, 2, 3, \ldots
$$

이 조건에서 $T(E) = 1$ — **완전 투과 (resonant transmission)**. Barrier 가 있음에도 입자가 완전히 통과.

물리적 해석: 입자의 파장 $\lambda' = 2\pi/k'$ 이 barrier 폭의 정수 배 ($L = n\lambda'/2$) 인 조건에서 barrier 양 끝의 반사파들이 정확히 상쇄 간섭. 결과적으로 반사가 0 이 되고 모든 입자가 투과한다.

---

### 5. 이중 barrier: Resonant tunneling

**1) 시스템 설정**

두 개의 barrier 사이에 우물이 있는 구조.

```
[ |V_0|       |V_0| ]
[ |----| 우물 |----| ]
[ 0    a    b    L ]
```

각 barrier 의 폭 $a$, 사이 우물의 폭 $b - a$, 전체 길이 $L$.

**2) Resonant tunneling 의 직관**

두꺼운 barrier 가 두 개 있으면 직관적으로 투과 확률이 매우 작을 것 같다 ($T \sim e^{-4\kappa a}$, 두 barrier 모두 통과). 그러나 특정 에너지에서는 **단일 barrier 보다도 큰 투과** — 심지어 완전 투과 $T = 1$ — 가 일어난다. 이를 **resonant tunneling** 이라 한다.

물리적 이유: 두 barrier 사이의 우물에 양자 우물 상태 (quasi-bound state) 가 형성됨. 입사 에너지가 그 quasi-bound 에너지와 일치하면, 우물 안에서 파동이 공명적으로 증폭되어 두 barrier 를 효과적으로 무력화한다.

**3) 정량적 결과**

전체 시스템의 transfer matrix $M_{\text{total}} = M_{\text{barrier 2}}\,M_{\text{well}}\,M_{\text{barrier 1}}$. 자세한 계산은 단순하지 않지만, 결과는 다음 형태이다.

$$
T(E) = \frac{1}{1 + F(E)\,\sin^2(\phi(E))}
$$

여기서 $F(E)$ 는 두 barrier 의 두께/높이로 결정되는 계수, $\phi(E)$ 는 우물 안에서 입자가 한 번 왕복할 때 축적되는 위상.

$\sin(\phi(E)) = 0$ 즉 $\phi(E) = n\pi$ 의 조건에서 $T(E) = 1$ — 완전 투과. 이 조건이 우물 안 quasi-bound 에너지에 대응한다.

**4) Lorentzian 모양**

공명 근처에서 $T(E)$ 가 다음 Lorentzian 모양:

$$
T(E) \approx \frac{(\Gamma/2)^2}{(E - E_n)^2 + (\Gamma/2)^2}
$$

- $E_n$: $n$ 번째 quasi-bound 에너지 (공명 중심)
- $\Gamma$: 공명 폭 — 두 barrier 의 두께/높이로 결정 ($\Gamma$ 가 작을수록 sharp 한 공명)

$E = E_n$ 에서 $T = 1$ (완전 투과), 공명에서 멀어지면 $T$ 가 빠르게 감소.

**5) NEGF 의 Lorentzian 과의 일치**

이 Lorentzian 모양은 NEGF 챕터에서 본 단일 사이트 시스템의 결과

$$
T(E) = \frac{\Gamma_L \Gamma_R}{(E - \epsilon_0)^2 + ((\Gamma_L + \Gamma_R)/2)^2}
$$

와 정확히 같은 구조이다. Resonant tunneling 의 양자 우물 quasi-bound state 가 NEGF 의 단일 사이트 시스템의 에너지 레벨 $\epsilon_0$ 와 대응, 우물의 lifetime 이 lead 와의 결합 강도 $\Gamma_{L,R}$ 과 대응.

이 일치가 우연이 아니라, 두 framework 이 같은 양자역학적 현상의 다른 표현임을 보여준다.

**6) 응용**

Resonant tunneling 은 양자수송의 가장 흥미로운 현상 중 하나이며, 응용도 다양하다.

- **Resonant tunneling diode (RTD)**: 이중 barrier 헤테로구조에서 공명 투과를 이용한 디바이스. 음의 미분 저항 (negative differential resistance) 특성을 가져 고주파 oscillator 등에 응용.
- **양자점 수송**: 두 lead 사이의 양자점이 본질적으로 이중 barrier 구조이며, 공명 투과가 양자점 transport 의 핵심.

---

### 6. NEGF 표현과의 일치

이 절의 핵심 결과인 양자역학적 산란 진폭으로부터의 $T(E)$ 계산과, NEGF 챕터의 $T = \text{Tr}[\Gamma_L G^R \Gamma_R G^A]$ 가 같은 양을 표현한다는 사실을 검증한다.

**1) 단일 사이트 NEGF**

NEGF 챕터의 가장 단순한 예: 산란 영역이 한 사이트, $H_s = \epsilon_0$. Wide-band 근사 $\Sigma_{L,R}^R = -i\Gamma_{L,R}/2$.

Retarded Green's function:

$$
G^R(E) = \frac{1}{E - \epsilon_0 + i(\Gamma_L + \Gamma_R)/2}
$$

투과:

$$
T(E) = \Gamma_L \Gamma_R\,|G^R(E)|^2 = \frac{\Gamma_L \Gamma_R}{(E - \epsilon_0)^2 + ((\Gamma_L + \Gamma_R)/2)^2}
$$

Lorentzian.

**2) 1D 산란 해석과의 대응**

위 단일 사이트 NEGF 시스템을 1D 산란 그림으로 재해석. 산란 영역이 한 점 ($x = 0$) 의 quasi-bound state, 에너지 $\epsilon_0$. 두 lead 와 결합 강도 $\Gamma_{L,R}$.

1D 산란 진폭으로부터 $T(E)$ 도출 (Breit-Wigner 형태): 공명 산란 이론에서

$$
T(E) = \frac{\Gamma_L \Gamma_R}{(E - \epsilon_0)^2 + ((\Gamma_L + \Gamma_R)/2)^2}
$$

NEGF 결과와 정확히 일치. ✓

**3) 일반 도출의 스케치**

다채널 1D 시스템에서도 같은 일치가 성립한다. 자세한 일반 도출은 다음 절차를 따른다.

(a) 1D Schrödinger 방정식의 산란 해를 $\psi = \psi_0 + \psi_{\text{scattered}}$ 로 분해.
(b) Lippmann-Schwinger 방정식 $\psi = \psi_0 + G_0\,V\,\psi$ 의 해는 retarded Green's function 으로 표현 가능.
(c) 투과 진폭 $t$ 가 $G$ 의 행렬 요소에 비례.
(d) $|t|^2$ 가 $\text{Tr}[\Gamma_L G^R \Gamma_R G^A]$ 형태로 정리.

자세한 도출은 양자 산란 이론의 표준 결과이며, NEGF 와 산란 이론이 같은 framework 임을 보여준다.

**4) 두 관점의 통합**

| 산란 이론 | NEGF |
|---|---|
| 입사 + 반사 + 투과 진폭 | $G^R, G^A$ 의 행렬 요소 |
| 산란 영역 안의 quasi-bound state | $H_s$ 의 고유 상태 |
| Quasi-bound state 의 수명 | $\Gamma_{L,R}$ |
| $T(E) = \vert t(E)\vert^2$ | $T(E) = \text{Tr}[\Gamma_L G^R \Gamma_R G^A]$ |

두 표현이 같은 물리를 다른 각도에서 본다. 산란 이론은 입사/투과의 입자 흐름 그림에 직관적이고, NEGF 는 시스템 안의 그린함수와 결합 강도로 일반적 framework 을 제공한다.

---

**example1) 직사각 barrier 의 transfer matrix 계산**

단일 직사각 barrier 의 $T(E)$ 를 transfer matrix 방법으로 명시적으로 계산.

sol)

$V(x) = V_0$ for $0 < x < L$, 0 elsewhere. $E < V_0$ 가정 (터널링).

내부 파동 수: $\kappa = \sqrt{2m(V_0 - E)}/\hbar$. 외부 파동 수: $k = \sqrt{2mE}/\hbar$.

Barrier 내부 transfer matrix:

$$
M_{\text{barrier}} = \begin{pmatrix} \cosh(\kappa L) & \sinh(\kappa L)/\kappa \\ \kappa\sinh(\kappa L) & \cosh(\kappa L) \end{pmatrix}
$$

좌측 lead 의 $\Psi(0)$:

$$
\Psi(0) = \begin{pmatrix} 1 + r \\ ik(1 - r) \end{pmatrix}
$$

우측 lead 의 $\Psi(L)$:

$$
\Psi(L) = \begin{pmatrix} t\,e^{ikL} \\ ik\,t\,e^{ikL} \end{pmatrix}
$$

(여기서 $e^{ikL}$ 은 우측 lead 에서의 위상 진행. 실제 매칭은 $x = L^-$ 와 $x = L^+$ 의 매칭으로, 더 자세히 보면 우측 lead 의 transfer matrix 도 고려해야 함. 표준적 처리는 lead 의 perfect transparency 를 가정하고 위 형태로 진행.)

매칭 $\Psi(L) = M_{\text{barrier}}\,\Psi(0)$ 에서 두 방정식이 나오고, 두 미지수 $r, t$ 를 풀 수 있다.

상세 대수 계산 (생략) 후:

$$
t(E) = \frac{2ik\kappa\,e^{-ikL}}{2ik\kappa\cosh(\kappa L) + (k^2 - \kappa^2)\sinh(\kappa L)}
$$

투과 확률

$$
T(E) = |t(E)|^2 = \frac{4k^2\kappa^2}{4k^2\kappa^2\cosh^2(\kappa L) + (k^2 - \kappa^2)^2\sinh^2(\kappa L)}
$$

이를 정리하면 §4-(3) 의 결과

$$
T(E) = \frac{1}{1 + \frac{V_0^2 \sinh^2(\kappa L)}{4E(V_0 - E)}}
$$

와 일치. ✓

---

**example2) 1D 직사각 우물의 공명 산란**

우물 (즉 $V_0 < 0$, attractive potential) 에서의 산란. Quasi-bound state 가 자연스럽게 등장.

sol)

$V(x) = -V_0$ for $0 < x < L$ (우물), $V_0 > 0$. 외부 lead 는 $V = 0$.

내부 파동 수: $k' = \sqrt{2m(E + V_0)}/\hbar$ (입사 에너지가 양수이므로 우물 안에서 더 큰 운동에너지). 외부: $k = \sqrt{2mE}/\hbar$.

투과 확률 (계산 결과):

$$
T(E) = \frac{1}{1 + \frac{V_0^2\sin^2(k'L)}{4E(E + V_0)}}
$$

특별한 에너지에서 $\sin(k' L) = 0$, 즉

$$
k'L = n\pi, \quad n = 1, 2, 3, \ldots
$$

이 조건에서 $T = 1$ — 우물이 있음에도 입자가 완전 투과.

물리적 의미: $k' L = n\pi$ 의 조건은 우물 안에서 양자 우물 상태의 quantization 조건과 같다. 입사 에너지가 우물의 quasi-bound 에너지와 일치할 때 우물 안에서 파동이 공명적으로 증폭되어 산란이 사라진다.

이 결과가 §5 의 이중 barrier 공명 투과의 단순화된 버전. 우물 양쪽이 무한 lead 가 아니라 두꺼운 barrier 라면 공명이 더 sharp 해지며 RTD 의 특성에 도달.
