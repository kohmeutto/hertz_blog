+++
title = "(b) Dyson equation and self-energy"
weight = 5
+++

---

### 1. 동기: 환경 자유도를 어떻게 흡수하는가

이전 절들에서 self-energy $\Sigma$ 라는 객체가 반복적으로 등장했다. 표현 $G^R = (E - H_s - \Sigma^R)^{-1}$, lesser self-energy $\Sigma^<$ 의 도입 등. 그러나 $\Sigma$ 가 어디서 오는지, 어떻게 정확히 정의되는지는 자세히 다루지 않았다. 이 절에서 $\Sigma$ 의 도출과 NEGF 의 핵심 방정식인 Dyson 방정식을 정리한다.

핵심 발상은 다음과 같다. 시스템이 환경과 결합되어 있을 때, 환경의 모든 자유도를 직접 다루는 것은 일반적으로 불가능하다. Lead 가 무한 크기일 수 있기 때문이다. 그러나 우리의 실질적 관심은 시스템 영역에 한정되어 있다. 환경의 영향을 시스템에 작용하는 effective term — self-energy $\Sigma$ — 으로 흡수하면, 시스템만을 명시적으로 다루면서도 환경의 효과를 정확히 포함하는 계산이 가능하다.

수학적으로 이 절차는 다음과 같이 수행된다.

(a) 전체 시스템 (시스템 + 환경) 의 Hamiltonian 을 블록 행렬로 분해
(b) 블록 행렬 역연산 공식을 적용해 시스템 블록의 그린함수를 추출
(c) 추출된 표현이 effective Hamiltonian $H_s + \Sigma$ 의 그린함수와 동등함을 확인

이로부터 $\Sigma$ 가 자연스럽게 정의되며, 환경의 모든 영향이 $\Sigma$ 안에 압축된다. 이 절차의 결과를 Dyson 방정식이라 부른다.

---

### 2. 블록 행렬 분해

**1) 전체 시스템의 분해**

전체 시스템을 시스템 영역 (scattering region, 우리의 관심 영역) 과 환경 영역 (lead, reservoir 등) 으로 나눈다. 전체 Hamiltonian 은 다음 블록 구조를 갖는다.

$$
H_{\text{total}} = \begin{pmatrix} H_s & V \\ V^\dagger & H_e \end{pmatrix}
$$

각 블록의 의미:

- $H_s$: 시스템의 Hamiltonian (유한 행렬, 우리가 직접 다루는 영역)
- $H_e$: 환경의 Hamiltonian (일반적으로 무한 행렬, lead 의 모든 자유도)
- $V$: 시스템과 환경 사이의 결합 행렬 (시스템 끝점과 lead 표면 사이의 hopping 등)

블록의 차원: $H_s$ 는 $N_s \times N_s$ ($N_s$ = 시스템 자유도 수), $H_e$ 는 $N_e \times N_e$ ($N_e$ = 환경 자유도 수, 보통 무한대), $V$ 는 $N_s \times N_e$.

**2) 전체 그린함수도 블록 구조**

전체 retarded 그린함수

$$
G_{\text{total}}^R(E) = (E\hat{I} - H_{\text{total}} + i0^+)^{-1}
$$

도 같은 블록 구조이다.

$$
G_{\text{total}}^R = \begin{pmatrix} G^R_{ss} & G^R_{se} \\ G^R_{es} & G^R_{ee} \end{pmatrix}
$$

각 블록의 의미:

- $G^R_{ss}$: 시스템 안에서 한 점에서 다른 점으로의 응답 — 우리가 원하는 것
- $G^R_{se}, G^R_{es}$: 시스템과 환경 사이의 응답
- $G^R_{ee}$: 환경 안에서의 응답

목표: $G^R_{ss}$ 를 명시적으로 표현하기.

---

### 3. Retarded self-energy의 도출

**1) 블록 행렬 역연산 공식**

$2 \times 2$ 블록 행렬의 역연산은 잘 알려진 결과이다.

$$
\begin{pmatrix} A & B \\ C & D \end{pmatrix}^{-1} = \begin{pmatrix} \mathcal{S}^{-1} & -\mathcal{S}^{-1}BD^{-1} \\ -D^{-1}C\mathcal{S}^{-1} & D^{-1} + D^{-1}C\mathcal{S}^{-1}BD^{-1} \end{pmatrix}
$$

여기서 $\mathcal{S} = A - BD^{-1}C$ 는 **Schur 보집합 (Schur complement)** 이다. 핵심: 왼쪽 위 블록이 $\mathcal{S}^{-1} = (A - BD^{-1}C)^{-1}$.

증명은 직접 곱셈으로 가능 — 위 행렬과 원 행렬을 곱하면 항등 행렬이 됨을 확인.

**2) 우리 케이스에 적용**

$(z\hat{I} - H_{\text{total}})$ 의 블록 분해, $z = E + i0^+$:

$$
A = z\hat{I}_s - H_s, \quad B = -V, \quad C = -V^\dagger, \quad D = z\hat{I}_e - H_e
$$

$D^{-1} = (E - H_e + i0^+)^{-1} = g_e^R(E)$ 가 isolated 환경 (시스템과 결합되지 않은) 의 retarded 그린함수.

Schur 보집합

$$
\mathcal{S} = (z\hat{I}_s - H_s) - (-V)\,g_e^R\,(-V^\dagger) = z\hat{I}_s - H_s - V\,g_e^R(E)\,V^\dagger
$$

따라서

$$
G^R_{ss}(E) = \mathcal{S}^{-1} = \bigl[E\hat{I}_s - H_s - V\,g_e^R(E)\,V^\dagger\bigr]^{-1}
$$

**3) Retarded self-energy의 정의**

위 표현에서 자연스럽게 다음을 정의한다.

$$
\boxed{\Sigma^R(E) := V\,g_e^R(E)\,V^\dagger}
$$

이 객체를 **retarded self-energy** 라 한다. $\Sigma^R$ 은 시스템 차원 ($N_s \times N_s$) 의 행렬 함수이며, 환경의 모든 정보 ($g_e^R, V$) 가 압축되어 들어가 있다.

그 결과로 시스템 retarded 그린함수가

$$
G^R(E) = \bigl[E\hat{I}_s - H_s - \Sigma^R(E)\bigr]^{-1}
$$

으로 표현된다 (이후 $G^R_{ss}$ 의 첨자 $ss$ 는 생략).

**4) Self-energy의 구조**

$\Sigma^R(E)$ 의 일반 구조:

$$
\Sigma^R(E) = \Delta(E) - \frac{i}{2}\Gamma(E)
$$

- $\Delta(E) = \text{Re}\,\Sigma^R$: 실수 부분, 환경 결합으로 인한 에너지 shift
- $\Gamma(E) = -2\,\text{Im}\,\Sigma^R$: 양의 정부호, 환경으로의 전이 비율

$\Gamma$ 의 양수성은 환경이 정상적인 (안정한) reservoir 라는 물리적 조건에서 나온다. 환경의 spectral function $a_e(E) = -2\,\text{Im}\,g_e^R(E)$ 가 양의 정부호이므로 $\Gamma = V\,a_e\,V^\dagger$ 도 양의 정부호.

**5) Effective Hamiltonian의 비-Hermitian 성격**

Effective Hamiltonian

$$
H_{\text{eff}}(E) = H_s + \Sigma^R(E)
$$

은 일반적으로 자기수반이 아니다 ($\Sigma^R$ 의 허수부 때문). 이전 절에서 본 것처럼:

- 모든 고유값이 복소 평면 하반평면으로 이동 (허수부 $< 0$)
- 복소 고유값의 허수부가 해당 상태의 유한 수명
- Spectral function 이 델타 함수에서 Lorentzian 으로 broadening

$\Sigma^R$ 이 $H_s$ 와 가환하면 (단순한 경우) $H_{\text{eff}}$ 가 비-Hermitian normal 이지만, 일반적으로 그렇지 않다.

---

### 4. Dyson 방정식의 두 형태

Self-energy 가 도출되었으므로, 시스템 retarded 그린함수의 관계식을 Dyson 방정식 형태로 정리한다.

**1) Closed form**

이미 §3 에서

$$
G^R(E) = \bigl[E\hat{I}_s - H_s - \Sigma^R(E)\bigr]^{-1}
$$

으로 표현했다. 이를 **closed form** 또는 **resolvent form** 이라 한다. 수치 계산에서는 보통 이 형태를 사용 — 행렬 역연산으로 $G^R$ 을 직접 얻는다.

**2) Perturbative form**

위 표현에서 $G^R\,(E - H_s - \Sigma^R) = \hat{I}$ 또는 $(E - H_s)\,G^R = \hat{I} + \Sigma^R\,G^R$ 을 정리하면

$$
G^R = (E - H_s)^{-1} + (E - H_s)^{-1}\,\Sigma^R\,G^R
$$

여기서 $G_0^R(E) := (E - H_s + i0^+)^{-1}$ 는 환경이 없을 때 (즉 $\Sigma^R = 0$) 의 시스템 retarded 그린함수. 이를 사용하면

$$
\boxed{G^R = G_0^R + G_0^R\,\Sigma^R\,G^R}
$$

이를 **Dyson 방정식의 perturbative form** 이라 한다. 환경 없는 그린함수 $G_0^R$ 에 환경 보정 항 $G_0^R \Sigma^R G^R$ 이 더해진 형태.

**3) 두 형태의 동등성**

두 형태는 수학적으로 완전히 동등하다. 한쪽에서 다른 쪽으로의 변환은 다음과 같다.

Perturbative → closed: $G^R = G_0^R + G_0^R \Sigma^R G^R$ 을 $G^R$ 에 대해 풀면 $G^R = (G_0^{R\,-1} - \Sigma^R)^{-1} = (E - H_s - \Sigma^R)^{-1}$.

Closed → perturbative: 위에서 도출한 그대로.

**4) 기하급수 전개**

Perturbative form 을 반복 대입하면 기하급수가 얻어진다.

$$
G^R = G_0^R + G_0^R \Sigma^R G_0^R + G_0^R \Sigma^R G_0^R \Sigma^R G_0^R + \ldots = \sum_{n=0}^{\infty} G_0^R (\Sigma^R G_0^R)^n
$$

각 항의 물리적 의미: 시스템에서 출발한 입자가 $\Sigma^R$ 의 매개로 환경과 0번, 1번, 2번, ... 상호작용한 후 응답하는 과정. 다체 NEGF 에서 이 perturbative 전개가 직접적인 산란 항을 나타내며, 다이어그램 표현으로 시각화된다.

**5) 사용 맥락**

두 형태가 동등하지만, 사용 맥락에 따라 한쪽이 편하다.

- **수치 계산**: closed form (행렬 역연산)
- **분석적 분석**: 두 형태 모두 사용
- **다체 NEGF**: perturbative form (Feynman 다이어그램과 직접 연결)

---

### 5. Lesser self-energy와 Keldysh 방정식

§3 의 도출은 retarded self-energy 에 대한 것이었다. 비슷한 절차로 lesser self-energy 가 정의되며, 이로부터 점유 정보가 시스템으로 전달되는 방식이 표현된다.

**1) Lesser self-energy의 정의**

$$
\boxed{\Sigma^<(E) := V\,g_e^<(E)\,V^\dagger}
$$

여기서 $g_e^<(E)$ 는 isolated 환경의 lesser 그린함수.

**2) 환경이 평형에 있을 때**

환경이 평형 상태이면 이전 절의 평형 분해

$$
g_e^<(E) = i\,f(E)\,a_e(E)
$$

가 성립한다. 여기서 $a_e = -2\,\text{Im}\,g_e^R$ 는 환경의 spectral function, $f(E)$ 는 환경의 분포 함수.

대입하면

$$
\Sigma^<(E) = i\,f(E)\,V\,a_e(E)\,V^\dagger = i\,f(E)\,\Gamma(E)
$$

여기서 $\Gamma(E) = V\,a_e\,V^\dagger$ 는 §3 에서 정의한 결합 강도. $\Gamma = -2\,\text{Im}\,\Sigma^R$ 의 관계가 검증된다 (양쪽 모두 $V\,a_e\,V^\dagger$).

**3) Keldysh 방정식**

블록 행렬 분해를 lesser 그린함수에도 적용하면 (Langreth 룰 등 추가 도구가 필요하나, 결과만 인용):

$$
\boxed{G^<(E) = G^R(E)\,\Sigma^<(E)\,G^A(E)}
$$

이를 **Keldysh 방정식** 또는 **lesser Dyson 방정식** 이라 한다. 우변의 각 항의 역할:

- $\Sigma^<(E)$: 환경에서 시스템으로 주입되는 점유 정보 (소스 항)
- $G^R(E), G^A(E)$: 시스템 내부의 동역학적 응답
- 곱 $G^R \Sigma^< G^A$: 환경의 점유가 시스템 안에서 어떻게 분포되는지

**4) 평형 극한 확인**

환경이 평형이고 시스템이 환경과 같은 화학 퍼텐셜에 있다면

$$
G^< = G^R\,(i f\,\Gamma)\,G^A = i f\,(G^R \Gamma G^A) = i f\,A
$$

여기서 $A = G^R \Gamma G^A$ 는 §3 의 표현. 평형 분해 $G^< = i f A$ 로 환원. ✓

---

### 6. 복수 환경의 self-energy 분해

실제 NEGF 적용에서 환경은 보통 여러 개의 독립적 reservoir 로 구성된다 (예: 좌측 lead, 우측 lead). 각 reservoir 가 시스템의 다른 영역과 결합되며 서로는 결합되지 않는다 ($V_L, V_R$ 이 서로 다른 영역에 작용).

**1) Block decomposition of environment**

환경 자체가 다시 두 부분 (또는 더 많은 부분) 으로 분해되면

$$
H_e = \begin{pmatrix} H_L & 0 \\ 0 & H_R \end{pmatrix}, \quad V = \begin{pmatrix} V_L & V_R \end{pmatrix}
$$

(블록 대각, 좌-우 reservoir 사이는 직접 결합되지 않음).

**2) Self-energy의 합 형태**

이 블록 구조에서 $\Sigma^R = V\,g_e^R\,V^\dagger$ 가

$$
\Sigma^R(E) = V_L\,g_L^R(E)\,V_L^\dagger + V_R\,g_R^R(E)\,V_R^\dagger = \Sigma_L^R(E) + \Sigma_R^R(E)
$$

각 reservoir 가 독립적으로 self-energy 에 기여한다. 마찬가지로

$$
\Sigma^<(E) = \Sigma_L^<(E) + \Sigma_R^<(E)
$$

여기서 각 reservoir 가 자신의 평형 분포로 점유 정보를 주입.

$$
\Sigma_L^<(E) = i\,f_L(E)\,\Gamma_L(E), \quad \Sigma_R^<(E) = i\,f_R(E)\,\Gamma_R(E)
$$

$\Gamma_{L,R}(E) = -2\,\text{Im}\,\Sigma_{L,R}^R(E)$.

**3) Keldysh 방정식의 두 reservoir 형태**

위를 Keldysh 방정식에 대입하면

$$
G^<(E) = G^R(E)\,\bigl[i\,f_L(E)\,\Gamma_L(E) + i\,f_R(E)\,\Gamma_R(E)\bigr]\,G^A(E)
$$

이전 절에서 다룬 표현. 시스템 내부 점유가 두 reservoir 의 분포의 가중 평균으로 결정.

---

### 7. Lead self-energy의 구체적 계산

실제 NEGF 응용에서 $\Sigma_{L,R}^R$ 의 계산은 lead 의 구조에 따라 진행된다.

**1) 일반 절차**

(a) Lead Hamiltonian $H_L$ 의 정의. 보통 반복 단위 셀로 구성된 tight-binding 모델 또는 연속체 모델.

(b) Isolated lead 의 **surface 그린함수** $g_L^R(E)$ 계산. 무한 lead 의 표면 행렬 요소 — 시스템과 결합되는 끝점에서의 retarded 그린함수.

(c) Lead-시스템 결합 행렬 $V_L$ 의 정의 (lead 의 표면 셀과 시스템 끝점 사이의 결합).

(d) Self-energy 도출: $\Sigma_L^R = V_L\,g_L^R\,V_L^\dagger$.

여기서 가장 어려운 부분은 (b) — 무한 lead 의 surface 그린함수 계산이다. 직접적인 방법으로 무한 차원 행렬 역연산이 필요하지만, 일반적으로 반복적 알고리즘 (Sancho-Lopez-Rubio, recursive Green's function 등) 으로 효율적으로 계산된다.

**2) 1D tight-binding lead 의 예**

가장 단순한 lead 모델로 일정한 on-site 에너지 $\epsilon_0$ 과 nearest-neighbor hopping $-t$ 의 1D tight-binding chain 을 고려한다.

$$
H_L = \sum_{i \geq 1}\epsilon_0\,|i\rangle\langle i| - t\sum_{i \geq 1}\bigl[|i\rangle\langle i+1| + |i+1\rangle\langle i|\bigr]
$$

(여기서 $i = 1$ 이 lead 의 표면, $i = 2, 3, \ldots$ 가 내부.)

이 lead 의 surface 그린함수 $g_L^R(E) = \langle 1|G_L^R|1\rangle$ 는 명시적으로

$$
g_L^R(E) = \frac{E - \epsilon_0 - i\sqrt{(2t)^2 - (E - \epsilon_0)^2}}{2t^2}
$$

(에너지 $|E - \epsilon_0| < 2t$ 영역, 즉 lead 의 band 안에서.) 이 결과는 무한 chain 의 그린함수의 반복적 정의 $g(E) = 1/(E - \epsilon_0 - t^2 g(E))$ 의 해 (이차 방정식) 에서 도출된다.

Band 안에서 허수부가 유한: $\text{Im}\,g_L^R = -\sqrt{(2t)^2 - (E-\epsilon_0)^2}/(2t^2) < 0$. 이는 lead 가 산란 영역의 입자를 받을 수 있다는 사실 — 즉 산란 영역 → lead 로의 전이가 가능함을 의미.

Band 밖에서 ($|E - \epsilon_0| > 2t$) 허수부가 0 — lead 가 입자를 받지 않음. 결정학적 band gap 영역.

**3) 시스템과의 결합**

시스템의 끝점이 lead 의 표면과 결합 강도 $-t'$ 으로 연결되어 있다면 ($V_L = -t'\,|x_{\text{end}}\rangle\langle 1|$ 형태)

$$
\Sigma_L^R(E) = t'^2\,g_L^R(E)\,|x_{\text{end}}\rangle\langle x_{\text{end}}|
$$

시스템 끝점에서 작용하는 self-energy. 일반적으로 시스템의 lead 와 결합된 영역에만 작용한다.

---

### 8. Wide-band 근사

복잡한 lead self-energy 계산을 피하는 단순화 방법.

**1) 근사의 내용**

Lead 의 DOS 가 산란 영역의 에너지 스케일에서 천천히 변하는 경우, $\Sigma_L^R(E)$ 를 에너지 독립 상수로 근사할 수 있다.

$$
\Sigma_L^R(E) \approx \Delta_L - \frac{i}{2}\Gamma_L
$$

여기서 $\Delta_L, \Gamma_L$ 가 모두 에너지 독립 상수. 보통 실수 shift 는 chemical potential 정의에 흡수되어 $\Delta_L = 0$ 으로 다룬다.

$$
\boxed{\Sigma_L^R \approx -\frac{i}{2}\Gamma_L \quad (\text{wide-band 근사})}
$$

비슷하게 우측 lead 도 $\Sigma_R^R \approx -i\Gamma_R/2$.

**2) 적용 조건**

근사가 유효한 조건:

- Lead 의 band 폭이 산란 영역의 관련 에너지 스케일보다 훨씬 큼
- 관심 에너지 영역이 lead 의 band edge 에서 멀리 떨어져 있음
- Lead 의 DOS 가 관심 에너지 영역에서 평탄함

응용에서 자주 만족된다 — 큰 금속 전극이나 두꺼운 반도체 lead 가 wide-band 한계에 잘 부합.

**3) 장점과 한계**

장점:

- $\Gamma$ 가 상수: 모든 에너지에서 동일한 수명, 계산 단순화
- $\Sigma^R = -i\Gamma/2$ 가 단순한 비-Hermitian normal: 효과 Hamiltonian 분석이 쉬움
- Spectral function 의 명확한 Lorentzian 구조

한계:

- 결합 강도의 에너지 의존성을 무시
- Band edge 근처에서 부정확 (DOS 가 급격히 변화)
- Lead 의 미세 구조 (Van Hove 특이점 등) 효과를 놓침

NEGF 의 첫 분석에서는 wide-band 근사로 직관을 얻고, 정확한 결과를 위해서는 전체 $\Sigma^R(E)$ 의 에너지 의존성을 고려한다.

---

**example1) 단일 레벨 시스템 + 두 reservoir**

가장 단순한 NEGF 시스템: 한 개의 에너지 레벨 $\epsilon_0$ 가 두 reservoir 와 결합 (단위 자유도 $N_s = 1$).

$$
H_s = \epsilon_0
$$

Wide-band 근사: $\Sigma_L^R = -i\Gamma_L/2$, $\Sigma_R^R = -i\Gamma_R/2$.

sol)

Retarded 그린함수:

$$
G^R(E) = \frac{1}{E - \epsilon_0 + i(\Gamma_L + \Gamma_R)/2}
$$

스펙트럼 함수:

$$
A(E) = -2\,\text{Im}\,G^R(E) = \frac{\Gamma_L + \Gamma_R}{(E - \epsilon_0)^2 + (\Gamma_L + \Gamma_R)^2/4}
$$

폭 $\Gamma = \Gamma_L + \Gamma_R$ 의 Lorentzian. 두 reservoir 가 각각 broadening 에 기여하며, 합이 총 broadening.

Lesser 그린함수:

$$
G^<(E) = G^R(E)\,\bigl[i f_L \Gamma_L + i f_R \Gamma_R\bigr]\,G^A(E) = \frac{i(f_L\Gamma_L + f_R\Gamma_R)}{(E - \epsilon_0)^2 + (\Gamma_L + \Gamma_R)^2/4}
$$

평형에서 ($f_L = f_R = f$): $G^< = i f\,A$ 회복.

비평형 점유 (효과 분포 함수):

$$
f_{\text{neq}}(E) = -i\,\frac{G^<(E)}{A(E)} = \frac{f_L(E)\,\Gamma_L + f_R(E)\,\Gamma_R}{\Gamma_L + \Gamma_R}
$$

두 reservoir 분포의 결합-강도 가중 평균.

전류 (Landauer-Büttiker):

$$
I = \frac{e}{h}\int dE\,T(E)\,[f_L(E) - f_R(E)], \quad T(E) = \frac{\Gamma_L\,\Gamma_R}{(E - \epsilon_0)^2 + (\Gamma_L + \Gamma_R)^2/4}
$$

투과 함수 $T(E)$ 도 Lorentzian. 최대 투과는 $E = \epsilon_0$ 에서 $T_{\max} = 4\Gamma_L\Gamma_R/(\Gamma_L + \Gamma_R)^2$. $\Gamma_L = \Gamma_R$ 일 때 $T_{\max} = 1$ (완전 투과).

---

**example2) 1D tight-binding 시스템의 Dyson 방정식**

시스템: 1D tight-binding chain 의 $N$ 개 사이트 ($H_s$ = nearest-neighbor hopping $-t_s$, on-site $\epsilon_s$).

Lead: 양쪽에 1D tight-binding lead (on-site $\epsilon_L$, hopping $-t_L$), 시스템과의 결합 강도 $-t'$.

sol)

좌측 lead self-energy (시스템의 첫 번째 사이트에 작용):

$$
\Sigma_L^R(E)_{11} = (t')^2\,g_L^R(E)
$$

다른 행렬 요소는 0.

우측 lead self-energy (시스템의 마지막 사이트에 작용):

$$
\Sigma_R^R(E)_{NN} = (t')^2\,g_R^R(E)
$$

총 self-energy

$$
\Sigma^R(E) = \begin{pmatrix} (t')^2 g_L^R & 0 & \cdots & 0 \\ 0 & 0 & \cdots & 0 \\ \vdots & & & \vdots \\ 0 & \cdots & 0 & (t')^2 g_R^R \end{pmatrix}
$$

만 두 끝점에서만 0 아닌 행렬.

System retarded 그린함수

$$
G^R(E) = \bigl[E\hat{I} - H_s - \Sigma^R(E)\bigr]^{-1}
$$

$N \times N$ 행렬의 역연산. 작은 $N$ 에서는 직접 계산, 큰 $N$ 에서는 recursive Green's function 알고리즘이 효율적이다.

투과 함수

$$
T(E) = \text{Tr}\bigl[\Gamma_L\,G^R\,\Gamma_R\,G^A\bigr] = \Gamma_L\,\Gamma_R\,|G^R_{1N}(E)|^2
$$

여기서 $\Gamma_{L,R}(E) = -2\,\text{Im}\,\Sigma_{L,R}^R$, 그리고 $G^R_{1N}$ 은 시스템의 첫 사이트에서 마지막 사이트로의 그린함수 행렬 요소. $|G^R_{1N}|^2$ 가 양 끝점 사이의 양자 산란 진폭의 제곱이다.

이 결과는 chain 의 양 끝점 사이의 양자 수송 ballistic 전류를 정확히 기술한다. 양 lead 가 충분히 평탄한 band 를 가지면 wide-band 근사로 더 단순화 가능.
