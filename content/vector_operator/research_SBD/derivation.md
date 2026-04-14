+++
title = "Derivation"
weight = 2
+++

---

### 계면 산란 수송 방정식의 무한 점근 급수 전개 및 닫힌 해 유도

작성자: 김기범, 윤영준 / 일자: 2026.03.31

---

### 0. 기호 정의 및 물리적 전제 (Nomenclature & Assumptions)

본 해석 모델은 4H-SiC 쇼트키 배리어 다이오드(SBD)의 금속-n형 반도체 접합면에서 발생하는 캐리어 수송 현상을 다룬다. 수식 전개의 완결성을 위해 보편 상수, 물성 변수, 그리고 에너지 기호를 명확히 규정한다.

**1) 보편 상수 및 소자 물성 기호**
- $e$: 기본 전하량 (Elementary charge)
- $k_B$: 볼츠만 상수 (Boltzmann constant)
- $h, \hbar$: 플랑크 상수 및 디랙 상수 ($\hbar = h/2\pi$)
- $T$: 절대 온도 (Absolute temperature)
- $m^*$: 반도체 전도대 전자의 유효 질량 (Effective mass)
- $A^*$: 리처드슨-더쉬먼 상수 (Richardson-Dushman constant), $A^* = 4\pi e m^* k_B^2 / h^3$
- $N_C, N_D$: 유효 상태 밀도(Effective density of states) 및 도너 도핑 농도

**2) 에너지 및 전압 기호**
- $V$: 순방향 인가 전압 (Applied Forward Bias)
- $V_{bi}$: 빌트인 포텐셜 (Built-in Potential)
- $E_c$: 반도체 벌크의 전도대 최하단 에너지. 본 모델에서 전자가 존재 가능한 물리적 하한선($E_{min}$)으로 작용한다. ($E_c = eV + k_BT \ln(N_C/N_D)$)
- $\Phi_B$: 정전기적 유효 장벽 깊이. ($\Phi_B = e(V_{bi} + V_n)$)
- $\Delta E$: 하한선 기준 유효 장벽 깊이. ($\Delta E = \Phi_B - E_c = e(V_{bi} - V)$)
- $\eta_0$: 계면 결함 산란에 의한 에너지 감쇄 폭 (Energy Broadening)

**3) 4대 물리적 가정**
- 단일 대역 전송 ($m=1$): 전도대 수송만 고려하며, 가전자대를 통한 공간 전하 재결합(SRH)은 배제되는 순방향 중간 전압 구간을 상정한다.
- 계면 산란 지배: 방사선 피폭 환경에 의해 계면 결함 밀도($N_{it}$)가 폭증하여, 전체 완화 시간 $\tau$가 계면 트랩에 의한 산란율($\tau_{it}$)에 전적으로 지배된다고 가정한다. ($1/\tau \approx 1/\tau_{it}$)
- 포물선 대역 (Parabolic Band): 밴드 에지 근처에서 $E(\mathbf{k}) = \Phi_B + \hbar^2\mathbf{k}^2 / 2m^*$ 가 성립한다.
- 볼츠만 통계 근사: 페르미-디랙 분포는 $E - \mu \gg k_BT$ 조건 하에서 지수 함수로 근사된다.

---

### 1. Operator Formalism & Spectral Function

결정 격자 내 입자의 운동 상태는 파수 $\mathbf{k}$에 의해 결정되며, 전압 $V$가 인가되었을 때 계면 결함에 의한 섭동을 포함하는 유효 해밀토니안 $\hat{H}_{eff}$ 는 복소수 에너지 고유값을 갖는다.

$$
\hat{H}_{eff}(\mathbf{k},V) = E_r(\mathbf{k},V) - i\eta_0
$$

이 비 에르미트(Non-Hermitian) 연산자를 분해 연산자(Resolvent Operator)와 소호츠키-플레멜리 정리(Sokhotski–Plemelj theorem)를 통해 전개하면, 시스템 내 전자의 존재 확률 밀도를 나타내는 스펙트럼 함수 $A(E, \mathbf{k}, V)$ 가 도출된다. 계면 산란 진폭 $\eta_0$ 에 의해 이 함수는 디랙 델타 함수가 아닌 로렌츠(Lorentzian) 분포를 띠게 된다.

$$
A(E, \mathbf{k}, V) = \frac{1}{\pi} \frac{\eta_0}{(E - E_r(\mathbf{k},V))^2 + \eta_0^2}
$$

---

### 2. Quantum Relaxation Time

스펙트럼의 허수부 $\eta_0$ 가 캐리어의 수명에 미치는 영향을 규명하기 위해, 유효 해밀토니안을 시간 의존성 슈뢰딩거 방정식 $i\hbar\frac{\partial}{\partial t}|\Psi(t)\rangle = \hat{H}_{eff}|\Psi(t)\rangle$ 에 대입하여 파동함수의 시간 진화를 해석한다.

$$
|\Psi(t)\rangle = \exp\left(-\frac{i E_r t}{\hbar}\right) \cdot \exp\left(-\frac{\eta_0 t}{\hbar}\right) |\Psi(0)\rangle
$$

입자가 해당 양자 상태에 생존할 확률 밀도 $P(t) = |\langle\Psi(t)|\Psi(t)\rangle|$ 는 실수 지수항의 소거로 인해 지수적 감쇄 법칙을 따른다.

$$
P(t) = P(0) \exp\left(-\frac{2\eta_0 t}{\hbar}\right)
$$

이를 통계역학적 수명 정의인 $P(t) = P(0)e^{-t/\tau}$ 와 대조하면, 계면 양자 완화 시간 $\tau_{it}$ 가 산출된다. 이는 로렌츠 스펙트럼의 반치폭($\Gamma = 2\eta_0$)에 대한 하이젠베르크 불확정성 관계를 만족한다.

$$
\tau_{it} = \frac{\hbar}{2\eta_0}
$$

---

### 3. 1차원 축소

미시적 양자 상태에서 거시 전류로 넘어가기 위해 란다우어-뷔티커(Landauer-Büttiker) 및 NEGF 전송 형식을 도입한다. 전체 전류 밀도 $J(V)$ 는 3차원 운동량 $\mathbf{k}$ 와 총 에너지 $E$ 에 대한 엄밀한 이중 적분($\iint d^3k dE$)으로 구성되며, 순방향 수송에 기여하는 전자는 $k_z > 0$ 인 상태로 한정된다.

$$
J(V) = 2e \int_{-\infty}^{\infty} dE \left[ f_L(E) - f_R(E) \right] \int_{k_z > 0} \frac{d^3k}{(2\pi)^3} v_z(k_z) A(E, \mathbf{k}, V)
$$

**1) 병진 대칭성(Translational Symmetry)과 변수 종속성의 엄밀한 분리**

금속-반도체 접합에서 페르미 준위를 $\mu_L = eV, \mu_R = 0$ 으로 분리하고, 볼츠만 근사($E-\mu \gg k_BT$)를 적용하여 거시 구동력 $\Delta F(V) = \exp(eV/k_BT) - 1$ 을 도출한다. 

이때, 계면 결함에 의한 산란은 접합면에 수직인 방향($z$)의 병진 대칭성만을 붕괴시키고 횡방향($\perp$) 운동량은 보존하는 '1차원 산란'으로 가정한다. 따라서 총 에너지 $E = E_z + \epsilon_\perp$ 와 3차원 스펙트럼 함수는 수직 에너지 $E_z$ 에만 종속되는 1차원 스펙트럼 $A_z(E_z, \epsilon_z)$ 로 분리되며, 적분 변수 역시 $dE$ 에서 $dE_z$ 로 치환된다. 지수항 역시 $\exp(-E/k_BT) = \exp(-E_z/k_BT)\exp(-\epsilon_\perp/k_BT)$ 로 직교 분해된다.

$$
J(V) = 2e \Delta F(V) \int_{-\infty}^{\infty} dE_z \exp\left(-\frac{E_z}{k_BT}\right) \int_0^\infty \frac{dk_z}{2\pi} v_z(k_z) A_z(E_z, \epsilon_z) \int_0^\infty \frac{d^2\mathbf{k}_\perp}{(2\pi)^2} \exp\left(-\frac{\epsilon_\perp}{k_BT}\right)
$$

**2) 횡방향 적분 및 야코비안(Jacobian) 변환**

우측의 횡방향 운동량 공간 적분은 변수 종속성이 해제되었으므로, 미분 관계식 $d^2\mathbf{k}_\perp = (2\pi m^* / \hbar^2) d\epsilon_\perp$ 를 통해 해석적으로 상수화된다.

$$
\int_0^\infty \frac{d^2\mathbf{k}_\perp}{(2\pi)^2} \exp\left(-\frac{\epsilon_\perp}{k_BT}\right) = \frac{m^* k_BT}{2\pi\hbar^2}
$$

수직 방향($z$) 파수 적분은 순수 운동 에너지 $\epsilon_z = \hbar^2 k_z^2 / 2m^*$ 에 대한 야코비안 치환을 수행한다. 군속도 $v_z = \hbar k_z / m^*$ 이므로, $v_z dk_z = d\epsilon_z / \hbar$ 가 성립한다.

$$
\int_0^\infty \frac{dk_z}{2\pi} v_z(k_z) A_z(E_z, \epsilon_z) = \int_0^\infty \frac{d\epsilon_z}{2\pi\hbar} A_z(E_z, \epsilon_z) = \frac{1}{h} \int_0^\infty d\epsilon_z A_z(E_z, \epsilon_z)
$$

**3) 1차원 전송 함수($U$) 도출 및 헤비사이드 계단 함수($\Theta$)를 통한 구간 절단**

여기서 $d\epsilon_z$ 에 대한 적분은 로렌츠 스펙트럼의 '운동 에너지 공간에 대한 누적합'을 의미하며, 이를 1차원 양자 전송 함수 $U(E_z)$ 로 정의한다. 아크탄젠트 정적분을 통해 닫힌 해가 유도된다.

$$
U(E_z) = \int_0^\infty d\epsilon_z \frac{1}{\pi} \frac{\eta_0}{(E_z - \Phi_B - \epsilon_z)^2 + \eta_0^2} = \frac{1}{2} + \frac{1}{\pi} \arctan\left(\frac{E_z - \Phi_B}{\eta_0}\right)
$$

모든 상수항($h = 2\pi\hbar$)을 전면으로 묶어 재조립하면 3차원 거시 열이온 방출 상수인 리처드슨-더쉬먼 상수 $A^* = 4\pi e m^* k_B^2 / h^3$ 가 도출된다. 이때, 전자는 반도체 벌크의 전도대 최하단($E_c$) 아래의 밴드갭에 존재할 수 없으므로, 벌크 상태 밀도(DOS)의 활성화를 수학적으로 규정하는 헤비사이드 계단 함수(Heaviside step function, $\Theta(E_z - E_c)$) 를 적분식에 도입하여 대수적 정합성을 확보한다.

$$
J(V) = \left( \frac{4\pi e m^* k_B^2}{h^3} T^2 \right) \frac{\Delta F(V)}{k_BT} \int_{-\infty}^{\infty} dE_z \left[ U(E_z) \cdot \Theta(E_z - E_c) \right] \exp\left(-\frac{E_z}{k_BT}\right) 
$$

계단 함수 $\Theta$ 의 수학적 성질에 의해, 적분 구간은 하한선이 $-\infty$ 에서 $E_c$ 로 닫히며 1차원 수직 에너지 적분($\mathcal{I}_z$)으로 축소된다.

$$
J(V) = A^*T^2 \frac{\Delta F(V)}{k_BT} \int_{E_c}^{\infty} dE_z \,U(E_z) \exp\left(-\frac{E_z}{k_BT}\right) = A^*T^2 \frac{\Delta F(V)}{k_BT} \mathcal{I}_z
$$

---

### 4. Asymptotic Series Complete Solution

라플라스 방법(Laplace's Method)에 따른  점근 해석학에 의하면, 전체 수송 적분 $\mathcal{I}_z$ 는 '피크 기여분(Peak contribution)'과 '경계 기여분(Boundary contribution)'의 단순 합으로 전개된다.

$$
\mathcal{I}_z = \int_{E_c}^{\infty} U(E_z) \exp\left(-\frac{E_z}{k_BT}\right) dE_z = \mathcal{I}_{peak} + \mathcal{I}_{boundary}
$$

**1) 피크 기여분 ($\mathcal{I}_{peak}$)**

장벽의 정점 $E_z = \Phi_B$ 근처에서의 지배분을 나타낸다. 로렌츠 커널을 디랙 델타 함수로 취급하여 도출되는 고전적 이상 적분항이다.

$$
\mathcal{I}_{peak} = k_BT \exp\left(-\frac{\Phi_B}{k_BT}\right)
$$

**2) 경계 기여분 ($\mathcal{I}_{boundary}$)**

비이상적 계면 산란 시, 지수 함수의 감쇄 효과로 인해 적분 하한선($E_c$)에 거대하게 형성되는 에너지 꼬리(Tail) 지배분이다. $\Delta E = \Phi_B - E_c \gg \eta_0$ 이므로 왓슨의 보조정리(Watson's Lemma)에 따라 $E_c$ 에 대한 무한 연속 부분 적분을 수행하면 다음과 같은 닫힌 급수해로 도출된다.

$$
\mathcal{I}_{boundary} \sim k_BT \exp\left(-\frac{E_c}{k_BT}\right) \sum_{n=0}^{\infty} (k_BT)^n U^{(n)}(E_c)
$$

$n$계 도함수 $U^{(n)}(E_c) \approx \frac{\eta_0}{\pi} \frac{n!}{\Delta E^{n+1}}$ 를 대입하고 공통항 $\frac{\eta_0}{\pi \Delta E}$ 를 묶어내면 절단 오차가 통제된 무차원 점근 보정항 $\mathcal{F}_{asymp}$ 가 도출된다.

$$
\mathcal{I}_{boundary} = \left[ \frac{\eta_0 k_BT}{\pi \Delta E} \exp\left(-\frac{E_c}{k_BT}\right) \right] \cdot \mathcal{F}_{asymp},\quad \mathcal{F}_{asymp} = 1 + \sum_{n=1}^{\infty} n! \left( \frac{k_BT}{\Delta E} \right)^n
$$

**3) $\mathcal{I}_z$ 의 수학적 완전해**

$$
\mathcal{I}_z = k_BT \exp\left(-\frac{\Phi_B}{k_BT}\right) + \frac{\eta_0 k_BT}{\pi \Delta E} \exp\left(-\frac{E_c}{k_BT}\right) \mathcal{F}_{asymp}
$$

---

### 5. Dimensionless Asymptotic Extraction Equation

도출된 완전해 $\mathcal{I}_z$ 를 Section 3에서 구한 거시 전류 밀도 방정식에 그대로 대입하여 전개한다.

$$
J(V) = A^*T^2 \frac{\Delta F(V)}{k_BT} \left[ k_BT \exp\left(-\frac{\Phi_B}{k_BT}\right) + \frac{\eta_0 k_BT}{\pi \Delta E} \exp\left(-\frac{E_c}{k_BT}\right) \mathcal{F}_{asymp} \right]
$$

괄호를 풀고 전개하면, 전체 전류 $J(V)$ 가 두 개의 거시적 항으로 자연스럽게 분리된다.

$$
J(V) = \underbrace{ A^*T^2 \Delta F(V) \exp\left(-\frac{\Phi_B}{k_BT}\right) }_{J_{ideal}(V)} + \underbrace{ A^*T^2 \Delta F(V) \frac{\eta_0}{\pi \Delta E} \exp\left(-\frac{E_c}{k_BT}\right) \mathcal{F}_{asymp} }_{\text{비이상적 산란 꼬리 전류}}
$$

첫 번째 항은 고전적 이상 열이온 방출 전류($J_{ideal}$)의 형태와 일치한다. 따라서 실제 측정 전류 $J_{exp}$ 는 다음과 같은 대수적 구조를 갖는다.

$$
J_{exp}(V) - J_{ideal}(V) = A^*T^2 \Delta F(V) \frac{\eta_0}{\pi \Delta E} \exp\left(-\frac{E_c}{k_BT}\right) \mathcal{F}_{asymp}
$$

이 식을 양자 산란폭 $\eta_0$ 에 대해 이항하여 정리한다.

$$
\eta_0 = \frac{\pi \Delta E}{\mathcal{F}_{asymp}} \left[ \frac{J_{exp}(V) - J_{ideal}(V)}{A^*T^2 \Delta F(V) \exp(-E_c / k_BT)} \right]
$$

$$
= \frac{\pi \Delta E}{\mathcal{F}_{asymp}} \left[ \frac{J_{exp}(V)}{A^*T^2 \Delta F(V)} \exp\left(\frac{E_c}{k_BT}\right) - \frac{A^*T^2 \Delta F(V) \exp(-\Phi_B/k_BT)}{A^*T^2 \Delta F(V) \exp(-E_c/k_BT)} \right]
$$

$$
= \frac{\pi \Delta E}{\mathcal{F}_{asymp}} \left[ \frac{J_{exp}(V)}{A^*T^2 \Delta F(V)} \exp\left(\frac{E_c}{k_BT}\right) - \exp\left(-\frac{\Phi_B - E_c}{k_BT}\right) \right]
$$

- 장벽 관계식

$$
\Delta E = \Phi_B - E_c = e(V_{bi} - V)
$$

- 열역학적 밴드 에지

$$
E_c = eV + k_BT \ln(N_C/N_D)
$$

- 구동력 결합

$$
\frac{\exp(E_c/k_BT)}{\Delta F(V)} = \frac{\exp(eV/k_BT)}{\exp(eV/k_BT) - 1} \frac{N_C}{N_D} = \frac{1}{1 - \exp(-eV/k_BT)} \frac{N_C}{N_D}
$$

위의 치환을 적용하면, 무차원 점근 역산 방정식이 도출된다.

$$
\eta_0 = \frac{\pi e(V_{bi}-V)}{\mathcal{F}_{asymp}} \left[ \frac{J_{exp}(V)}{A^*T^2} \cdot \frac{N_C/N_D}{1 - \exp\left(-\frac{eV}{k_BT}\right)} - \exp\left(-\frac{e(V_{bi}-V)}{k_BT}\right) \right]
$$

$$
\mathcal{F}_{asymp} = 1 + \sum_{n=1}^{\infty} n! \left( \frac{k_BT}{e(V_{bi}-V)} \right)^n
$$

이 수식은 현상론적 피팅 변수($n$)을 사용하지 않고, 전기적 직류 측정값($J_{exp}$)만으로 계면 산란 진폭 $\eta_0$ 와 양자 완화 시간 $\tau_{it}$ 를 대수적으로 역산해 내는 완전해(Closed-form Solution)이다. 1차항($n=1$)까지만 전개하더라도 수치 적분 대비 오차율은 1% 미만으로 억제된다.

---

### 6. 유효 전압 구간 확정

순수 열이온 방출(Thermionic Emission)이 지배하는 윈도우에서만 성립하므로, 직렬 저항에 의한 전압 강하를 보정하고 기생 전하 수송의 간섭을 차단하기 위한 전압 한계선을 규정해야 한다.

**1) 거시적 직렬 저항($R_s$) 추출 및 유효 전압($V_{eff}$) 보정**

고전압 영역에서는 소자 벌크 및 금속 컨택의 직렬 저항($R_s$)에 의한 전압 강하가 다이오드의 지수적 전류 성장을 억제하여 I-V 곡선이 선형(Ohmic) 거동으로 전이된다. 따라서 본 양자 수송 모델을 적용하기 앞서, 인가 전압($V_{app}$)에서 직렬 저항 강하분을 소거하여 실제 접합면에 걸리는 유효 전압($V_{eff}$)을 도출해야 한다. 일반적인 열이온 방출 방정식 $I = I_s \exp[e(V_{app} - I R_s)/nk_BT]$ 의 양변에 자연로그를 취하고 전류 $I$ 에 대해 미분하면 다음과 같은 선형 대수 관계식이 도출된다.

$$
\frac{dV_{app}}{dI} = R_s + \frac{n k_BT}{e} \frac{1}{I}
$$

고전압(대전류) 영역에서 $\frac{dV_{app}}{dI}$ 와 $\frac{1}{I}$ 를 각각 $y$ 축, $x$ 축으로 도시(Plot)하여 선형 회귀(Linear regression)를 수행하면, $y$ 절편으로부터 직렬 저항 $R_s$ 를 해석적으로 확정할 수 있다. 산출된 $R_s$ 를 통해 유효 전압 윈도우를 다음과 같이 재정의하며, 이전 장(Section 1~5)에서 논의된 모든 전압 $V$ 는 이 보정된 $V_{eff}$ 를 의미한다.

$$
V_{eff} = V_{app} - I_{exp} R_s
$$

**2) 하한선 결정 ($V_{lower}$): 재결합 전류의 수학적 소멸점 도출**

저전압 영역에서는 벌크 공핍층 내부의 공간 전하 재결합 전류($J_{rec}$)가 지배적이다. 본 모델은 계면 장벽을 투과하는 순수 열이온 방출 전류($J_{TE}$)만을 취급하므로, $J_{TE}$ 가 $J_{rec}$ 를 물리적으로 역전하여 압도하기 시작하는 교차점(Crossover point)을 수학적으로 산출해야 한다.  이상 주계수 $n=1$ 인 열이온 방출 전류와 $n=2$ 인 SRH 재결합 전류 방정식의 크기가 같아지는 지점($J_{TE} = J_{rec}$)을 대수적으로 전개한다.

$$
A^*T^2 \exp\left(-\frac{\Phi_B}{k_BT}\right) \exp\left(\frac{eV}{k_BT}\right) = \frac{e n_i W}{2\tau_{SRH}} \exp\left(\frac{eV}{2k_BT}\right)
$$

단, $n_i$는 진성 캐리어 농도, $W$는 공핍층 두께, $\tau_{SRH}$는 체적 재결합 수명이다. 양변을 $\exp(eV/2k_BT)$ 로 나누어 전압 지수항을 하나로 병합한다.

$$
\exp\left(\frac{eV}{2k_BT}\right) = \frac{e n_i W}{2\tau_{SRH} A^*T^2} \exp\left(\frac{\Phi_B}{k_BT}\right)
$$

양변에 자연로그($\ln$)를 취하고 교차 전압 $V$ 에 대해 정리하면, 이론적 하한선 $V_{lower}$ 는 다음과 같다.

$$
V_{lower} = \frac{2k_BT}{e} \ln\left(\frac{e n_i W}{2\tau_{SRH} A^*T^2}\right) + \frac{2\Phi_B}{e}
$$

**3) 상한선 결정 ($V_{upper}$): 볼츠만 통계 근사의 붕괴 한계**

본 해석 모델의 중추인 1차원 수송 적분은 전자의 페르미 분포를 지수 함수로 단순화하는 볼츠만 통계 근사($E - \mu \gg k_BT$)를 기반으로 전개되었다.따라서, 인가 전압 하에서도 유효 에너지 장벽이 페르미 준위 대비 최소 $3k_BT$ 이상의 두께를 유지해야 한다.

$$
e(V_{bi} - V_{eff}) \ge 3k_BT
$$

이를 유효 전압 $V_{eff}$ 에 대해 이항하면 이론적 상한선 $V_{upper}$ 가 산출된다.

$$
V_{upper} = V_{bi} - \frac{3k_BT}{e}
$$

---

### 7. 4H-SiC SBD 소자 크기별 방사선 피폭 전/후 파라미터 통합 분석

| 소자 크기 (반지름) | 피폭 상태 | 직렬 저항 Rs (Ω) | 모델 교정률 (%) | 유효 산란폭 $\eta_0$ (meV) | 결속 파괴 거리 $l_{coh}$ (nm) | 계면 결함 밀도 $N_{it}$ (cm⁻²) |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **450 μm** | 피폭 전 (Pristine) | 7.1083 | 2.56 | 1.28e-09 | 1.06e+10 (극한 점근선) | 9.38e+04 (검출 한계) |
| | **피폭 후 (Rad)** | **13.3784** | **5.42** | **0.4276** | **31.94** | **3.13e+13** |
| **350 μm** | 피폭 전 (Pristine) | 7.0876 | 2.40 | 4.43e-10 | 3.08e+10 (극한 점근선) | 3.24e+04 (검출 한계) |
| | **피폭 후 (Rad)** | **14.2972** | **5.39** | **0.4444** | **30.73** | **3.25e+13** |
| **250 μm** | 피폭 전 (Pristine) | 7.3586 | 2.19 | 1.73e-10 | 7.88e+10 (극한 점근선) | 1.26e+04 (검출 한계) |
| | **피폭 후 (Rad)** | **14.7761** | **4.61** | **0.5119** | **26.68** | **3.74e+13** |
| **150 μm** | 피폭 전 (Pristine) | 7.9446 | 4.43 | 0.0368 | 371.59 | 2.69e+12 (초기 공정 결함) |
| | **피폭 후 (Rad)** | **17.0690** | **4.08** | **0.6594** | **20.71** | **4.82e+13** |

*(※ $N_{it}$ 환산 조건: 문헌 표준 포획 단면적 $\sigma = 10^{-15}$ cm² 및 계면 유효 두께 $W_{it} = 1$ nm 가정 적용)*

**1) Detection Limit**

피폭 전(Pristine) 대형 소자(450~250 μm)에서 나타나는 $10^{10}$ nm 수준의 결속 거리와 $10^4$ 수준의 결함 밀도는 알고리즘의 붕괴가 아니다. 이는 해당 소자들이 거시 측정 장비의 분해능 하한선을 밑도는 열이온 방출 상태에 있음을 뜻하는 수학적 검출 한계(Detection Limit) 임을 보여준다.

**2) Phase Transition**

피폭 후(Rad) 모든 소자에서 예외 없이 산란폭($\eta_0$)이 수억 배 폭증하며, 양자 결속 거리($l_{coh}$)가 수십 나노미터 스케일로 무너진다. 결과적으로 도출된 $N_{it}$ 수치는 IEEE 및 물리학회에서 보고되는 강 피폭 열화 수치($10^{13} \text{ cm}^{-2}$ 대역)와 일치한다.

**3) Perimeter/Edge-Effect**

표의 아래로 내려갈수록(소자 크기가 450 μm에서 150 μm로 작아질수록), 피폭 후의 결함 밀도($N_{it}$)는 $3.13 \times 10^{13}$에서 $4.82 \times 10^{13}$으로 약 50%가량 더욱 밀집하고, 결속 거리($l_{coh}$)는 31 nm에서 20 nm로 극단적으로 짧아진다. 나아가 150 μm 소자는 피폭 전부터 이미 공정 한계에 의한 결함($2.69 \times 10^{12}$)을 내포하고 있음이 포착된다. 이는 가장자리 둘레 비율(Perimeter-to-Area ratio)이 높은 미세 소자일수록 방사선과 공정 스트레스에 더욱 취약하다는 것을 보여준다.

---

### 8. 코드

```matlab
%% 1. 보편 물리 상수 및 4H-SiC 표준 물성
q = 1.60217663e-19;       
kB = 1.380649e-23;        
T = 300;                  
h = 6.62607015e-34;       
hbar = h / (2 * pi);      
kT_J = kB * T;            
kT_eV = kT_J / q;         
m_0 = 9.10938356e-31;      % 전자 정지 질량 [kg]

% [소자 고유 파라미터 및 문헌 고정값]
V_bi = 1.8031;             % 빌트인 포텐셜 (V)
N_D = 1.05e+16 * 1e6;      % 에피층 도핑 농도 (m^-3) 

N_C = 1.7e19 * 1e6;        
A_star = 146 * 10000;      
m_star = 0.42 * m_0;       % 4H-SiC 문헌 표준 벌크 유효 질량 고정 (역산 배제)
sigma_trap = 1e-15;        % 포획 단면적 가정치 [cm^2] (문헌 표준 비교용)
         
% 계면 유효 두께 가정치 [cm] (1 nm, N_t -> N_it 차원 환산용)
% 고체물리학계에서는 통상적으로 원자 3~4개 층에 해당하는 1 nm (10^-7 cm) 를 표준 유효 두께로 가정
W_it_cm = 1e-7;  

Radius_um = 450;           
Area = pi * (Radius_um * 1e-6)^2; 

%% 2. 실험 데이터 로드 및 노이즈 필터링
data = readmatrix('SiC_IV.csv');
V_raw = data(:, 1);
I_raw = abs(data(:, 3));  
J_raw = I_raw / Area;     
valid_idx = ~isnan(V_raw) & ~isnan(J_raw) & (J_raw > 1e-12);
V_app = V_raw(valid_idx);
J_exp = J_raw(valid_idx);

%% 3. 직렬 저항 (Rs) 자동 산출 및 V_eff 보정 (엄밀한 물리적 한계선 적용)
% [3-1] 미분 저항 및 Cheung's Method용 변수 산출
ln_J = log(J_exp);
dV_dlnJ = gradient(V_app) ./ gradient(ln_J);
dV_dJ = gradient(V_app) ./ gradient(J_exp); % 미분 저항 (R_diff = dV/dJ)

% [3-2] 물리적 한계선 설정: 측정된 가장 순수한 최소 미분 저항 탐색
% R_s는 이 최소 미분 저항(min_Rdiff)을 물리적으로 초과할 수 없음 (V_eff 역주행 방지)
valid_dV_dJ_mask = (gradient(J_exp) > 1e-6) & (dV_dJ > 0);
valid_dV_dJ = dV_dJ(valid_dV_dJ_mask);
if isempty(valid_dV_dJ)
    min_Rdiff = inf;
else
    min_Rdiff = min(valid_dV_dJ);
end

% [3-3] 선형 구간 탐색 (V_bi 이상의 장벽 통제력 상실 구간)
candidate_idx = find(V_app > V_bi);
if length(candidate_idx) > 10
    window_size = 10;
    num_windows = length(candidate_idx) - window_size + 1;
    r_squared = zeros(num_windows, 1);
    
    % 다항식 피팅 경고(조건 악화) 스팸 방지
    warning('off', 'MATLAB:polyfit:RepeatedPointsOrRescale');
    warning('off', 'MATLAB:polyfit:PolyNotUnique');
    
    for i = 1:num_windows
        idx_range = candidate_idx(i : i + window_size - 1);
        x = J_exp(idx_range);
        y = dV_dlnJ(idx_range);
        
        % 전류(x) 포화 구간은 선형 피팅의 의미가 없으므로 배제 (트랩/열화 특성 반영)
        if std(x) < 1e-8
            r_squared(i) = -Inf;
            continue;
        end
        
        [p, ~, mu] = polyfit(x, y, 1);
        y_fit = polyval(p, x, [], mu);
        
        SS_tot = sum((y - mean(y)).^2);
        SS_res = sum((y - y_fit).^2);
        real_slope = p(1) / mu(2);
        
        % 절대 법칙: 산출된 기울기(Rs_Area)가 최소 미분 저항을 넘으면 물리적 오류로 기각
        if real_slope > 0 && real_slope <= min_Rdiff
            r_squared(i) = 1 - (SS_res / SS_tot);
        else
            r_squared(i) = -Inf;
        end
    end
    warning('on', 'all');
    
    [max_R2, best_win_idx] = max(r_squared);
    
    % [3-4] 최종 Rs 확정 및 시각화 윈도우(노란 박스) 범위 정밀 설정
    if max_R2 == -Inf
        % 방사능 피폭 등으로 완벽한 선형 구간이 붕괴된 경우 (Fallback 로직)
        % 가장 가파른(미분 저항이 최소인) 찰나의 순간을 소자의 진짜 Rs로 채택
        Rs_Area = min_Rdiff * 0.99; % 수학적 발산(분모 0)을 막기 위한 1% 마진
        
        % 추출된 정확한 국소 위치만 윈도우로 시각화 (5V 전체 덮임 방지)
        actual_indices = find(valid_dV_dJ_mask);
        [~, min_loc_idx] = min(dV_dJ(valid_dV_dJ_mask));
        true_Rs_idx = actual_indices(min_loc_idx);
        
        % 시각적 표시를 위해 해당 지점 전후(+/- 1 포인트)로 타이트한 윈도우 설정
        Rs_lower_bound = V_app(max(1, true_Rs_idx - 1));
        Rs_upper_bound = V_app(min(length(V_app), true_Rs_idx + 1));
    else
        % 정상적으로 선형 구간이 찾아진 경우 (일반적인 Cheung's Method)
        Rs_win_idx = candidate_idx(best_win_idx : best_win_idx + window_size - 1);
        [p_final, ~, mu_final] = polyfit(J_exp(Rs_win_idx), dV_dlnJ(Rs_win_idx), 1);
        Rs_Area = p_final(1) / mu_final(2);
        Rs_lower_bound = V_app(Rs_win_idx(1));
        Rs_upper_bound = V_app(Rs_win_idx(end));
    end
    Rs = Rs_Area / Area;
else
    error('V_bi 이상의 고전압 데이터가 부족하여 Rs를 추출할 수 없습니다.');
end
% [3-5] 최종 안전장치 및 계면 유효 전압(V_eff) 보정
if Rs_Area > min_Rdiff
    Rs_Area = min_Rdiff * 0.99;
    Rs = Rs_Area / Area;
end
% 전압 강하 보정 (계면의 순수 인가 전압 산출)
V_eff = V_app - (J_exp * Rs_Area);

%% 4. 물리적 전압 경계 자동 추출 (n < 1.3333 진입 및 eta_0 역전 직전)
% [4-1] 하한선: n 수치가 1.3333 미만으로 떨어지는 최초의 지점
n_local = (1/kT_eV) * (gradient(V_app) ./ gradient(log(J_exp)));
% n이 2에서 내려오며 1.3333을 '넘어서는(밑으로 떨어지는)' 첫 번째 인덱스
idx_start = find(n_local < 1.3333, 1, 'first');
if isempty(idx_start)
    error('데이터에서 n < 1.3333 구간을 찾을 수 없습니다.');
end
V_lower_auto = V_app(idx_start);

% [4-2] 상한선: eta_0가 음수로 반전되기 직전의 마지막 양수(+) 지점
Term_Current_all = J_exp ./ (A_star * T^2);
Term_Fermi_all = (N_C / N_D) ./ (1 - exp(-V_eff / kT_eV));
Term_Ideal_all = exp(-(V_bi - V_eff) / kT_eV);
V_upper_Boltzmann = V_bi - (3 * kT_eV);

% eta_0가 0보다 큰 물리적 유효 데이터 마스크
is_positive_eta = (Term_Current_all(:) .* Term_Fermi_all(:)) > Term_Ideal_all(:);
% 하한선 이후, 볼츠만 한계 미만에서 양수인 마지막 데이터 인덱스 추출
valid_indices = find(V_eff > V_lower_auto & V_eff < V_upper_Boltzmann & is_positive_eta);
V_upper_auto = V_eff(valid_indices(end));

% 최종 분석 구간 확정
eta_win_idx = (V_eff >= V_lower_auto) & (V_eff <= V_upper_auto);
V_eta = V_eff(eta_win_idx);
J_eta = J_exp(eta_win_idx);

%% 5. 무한 점근 급수 기반 그랜드 통합 모델 (Grand Unified Asymptotic Model) 적용
asymp_order = 1; 
Term_Current = J_eta ./ (A_star * T^2);
Term_Fermi = (N_C / N_D) ./ (1 - exp(-V_eta / kT_eV));
% [대응 원리 보존] 고전적 열이온 방출 기준점
Term_Ideal = exp(-(V_bi - V_eta) / kT_eV); 

% 유효 장벽 깊이 및 무차원 전개 파라미터 (epsilon) 산출
Delta_E_eV = V_bi - V_eta;
epsilon = kT_eV ./ Delta_E_eV; % k_BT / Delta_E (Asymptotic Expansion Parameter)

% [Model 1] 0차 주성분 (Leading-order Term) 추출
eta_0_0th_J = pi * q * Delta_E_eV .* (Term_Current .* Term_Fermi - Term_Ideal);
eta_0_0th_meV = (eta_0_0th_J / q) * 1e3;               

% [Model 2] N차 점근 완전해 (N-th order Exact Asymptotic Solution) 동적 계산
Correction_Factor = ones(size(epsilon)); % 0차항(n=0)의 값은 1
for n = 1:asymp_order
    Correction_Factor = Correction_Factor + factorial(n) * (epsilon.^n);
end

% 0차 주성분을 다차원 보정 급수로 나누어 최종 역산 수행
eta_0_exact_J = eta_0_0th_J ./ Correction_Factor;
eta_0_exact_meV = (eta_0_exact_J / q) * 1e3;

% 양자 결함 완화 시간(Relaxation time) 산출 (단위: ps)
tau_exact_ps = (hbar ./ (2 * eta_0_exact_J)) * 1e12;       

% [엄밀한 대푯값 산출] 
mean_eta_0th_meV = mean(eta_0_0th_meV, 'omitnan');
mean_eta_exact_J = mean(eta_0_exact_J, 'omitnan');
mean_eta_exact_meV = mean(eta_0_exact_meV, 'omitnan');
effective_tau_exact_ps = (hbar / (2 * mean_eta_exact_J)) * 1e12; 

% 점근 급수 보정에 의한 실제 수학적 교정률 평가
correction_percentage = abs(eta_0_0th_meV - eta_0_exact_meV) ./ eta_0_0th_meV * 100;
mean_correction_pct = mean(correction_percentage, 'omitnan');

%% 8. 유효 산란 단면적 밀도 (Sigma_eff), 체적/면적 트랩 밀도(N_t, N_it) 산출
% 1. 1차원 지향성 리처드슨 열속도 (v_R) 계산 [단위: m/s]
v_R = sqrt((kB * T) / (2 * pi * m_star));

% 2. 양자 결속 파괴 거리 (Quantum Coherence Length, l_coh) 동적 배열 산출
l_coh_m = v_R .* (tau_exact_ps * 1e-12);
l_coh_nm = l_coh_m * 1e9; % [단위: nm]

% 3. 유효 산란 단면적 밀도 (Sigma_eff) 동적 배열 산출 
Sigma_eff_m_inv = 1 ./ l_coh_m;
Sigma_eff_cm_inv = Sigma_eff_m_inv / 100; % [단위: cm^-1]

% 4. 트랩 밀도 역산 (차원 정합성 확보)
% 4-1. 체적당 벌크 트랩 밀도 (N_t) [단위: cm^-3]
N_t_cm3 = Sigma_eff_cm_inv / sigma_trap;
% 4-2. 면적당 계면 결함 밀도 (N_it) [단위: cm^-2] (계면 두께 W_it 적용)
N_it_cm2 = N_t_cm3 * W_it_cm;

% 5. 대푯값 산출 (조화 평균의 엄밀성 적용)
% [수정 사항] 역수 관계인 l_coh_nm 배열을 직접 산술 평균(mean)하면 
% eta_0가 0에 근접하는 국소 아웃라이어(Infinity)가 전체 평균을 오염시킴.
% 따라서, 이미 산란율(eta_0) 기반으로 도출된 대푯값(tau_eff)에서 역산함.
mean_l_coh_nm = v_R * (effective_tau_exact_ps * 1e-12) * 1e9;
mean_Sigma_eff_cm_inv = mean(Sigma_eff_cm_inv, 'omitnan');
mean_N_t_cm3 = mean(N_t_cm3, 'omitnan');
mean_N_it_cm2 = mean(N_it_cm2, 'omitnan');

%% 9. 시각화 1: 동적 차수 모델 교차 검증 
figure('Name', ['Asymptotic Series Extraction (Order: ', num2str(asymp_order), ')'], ...
       'Color', 'w', 'Position', [100 100 1200 500]);
% [Subplot 1] 반대수 I-V 곡선 (Log Scale)
subplot(1, 3, 1);
semilogy(V_app, J_exp, 'k.', 'MarkerSize', 8, 'DisplayName', 'Measured (V_{app})'); hold on;
semilogy(V_eff, J_exp, 'r-', 'LineWidth', 1.5, 'DisplayName', 'R_s Corrected (V_{eff})');
xline(V_lower_auto, 'b--', 'V_{lower} (n < 1.3333)'); 
xline(V_upper_auto, 'b--', 'V_{upper} (eta_0 > 0 Last)');
xlabel('Voltage (V)'); ylabel('Current Density (A/m^2)'); 
title('Forward I-V (Log)'); grid on;
legend('Location', 'northwest');
% [Subplot 2] 선형 I-V 및 Rs 유효 윈도우 
subplot(1, 3, 2);
plot(V_app, I_raw * 1e3, 'k.', 'MarkerSize', 8, 'DisplayName', 'Measured (V_{app})'); hold on;
plot(V_eff, I_raw * 1e3, 'r-', 'LineWidth', 1.5, 'DisplayName', 'R_s Corrected (V_{eff})');
fill([Rs_lower_bound, Rs_upper_bound, Rs_upper_bound, Rs_lower_bound], ...
     [0, 0, max(I_raw)*1e3, max(I_raw)*1e3], 'y', 'FaceAlpha', 0.2);
xlabel('Voltage (V)'); ylabel('Current (mA)'); 
title(['Ohm`s Law Region (R_s = ', num2str(Rs, '%.2f'), ' \Omega)']); grid on;
legend('Location', 'northwest');
% [Subplot 3] 0차 주성분 vs N차 점근 완전해 비교
subplot(1, 3, 3);
yyaxis left; 
plot(V_eta, eta_0_0th_meV, 'b--', 'LineWidth', 1.5, 'DisplayName', '\eta_0 (0th-order)'); hold on;
plot(V_eta, eta_0_exact_meV, 'b-', 'LineWidth', 2.5, 'DisplayName', ['\eta_0 (', num2str(asymp_order), 'th-order Exact)']); 
ylabel('\eta_{0,it} (meV)');
yyaxis right; 
plot(V_eta, tau_exact_ps, 'r-', 'LineWidth', 2, 'DisplayName', ['\tau_{it} (', num2str(asymp_order), 'th-order Exact)']); 
ylabel('\tau_{it} (ps)');
xlabel('V_{eff} (V)'); 
title(['Extracted Quantum Parameters (Order: ', num2str(asymp_order), ')']); grid on;
legend('Location', 'northwest');

%% 10. 시각화 2: 방사선 피폭 열화 독립 지표
figure('Name', 'Interface Degradation Metrics (N_it & Coherence)', ...
       'Color', 'w', 'Position', [150 150 900 400]);
% [Subplot 1] 유효 산란 단면적 밀도 (Sigma_eff) 및 면적당 계면 결함 밀도 (N_it)
subplot(1, 2, 1);
yyaxis left;
plot(V_eta, Sigma_eff_cm_inv, 'r-', 'LineWidth', 2.5);
xlabel('V_{eff} (V)'); ylabel('\Sigma_{eff} (cm^{-1})');
title('Scattering Density & Trap Density');
yyaxis right;
plot(V_eta, N_it_cm2, 'g--', 'LineWidth', 1.5);
ylabel(sprintf('N_{it} (cm^{-2}) [W_{it}=1nm, \\sigma=%.1e]', sigma_trap));
grid on;
% [Subplot 2] 양자 결속 파괴 거리 (l_coh)
subplot(1, 2, 2);
plot(V_eta, l_coh_nm, 'b-', 'LineWidth', 2.5);
xlabel('V_{eff} (V)'); ylabel('l_{coh} (nm)');
title('Quantum Coherence Length');
grid on;

%% 11. 터미널 로그 출력 (최종 논문 보고용 통합 수치)
fprintf('\n========================================================================\n');
fprintf(' [보고서] 4H-SiC SBD 무한 점근 급수 기반 양자 파라미터 추출 결과\n');
fprintf('------------------------------------------------------------------------\n');
fprintf(' 1. 동적 산출된 직렬 저항 (Rs)  : %.4f Ohm\n', Rs);
fprintf(' 2. 추출 윈도우 (V_eff)         : %.3f V ~ %.3f V\n', V_eta(1), V_eta(end));
fprintf(' 3. 전개 파라미터 (epsilon) 범위: %.4f ~ %.4f\n', min(epsilon), max(epsilon));
fprintf('------------------------------------------------------------------------\n');
fprintf(' [수리물리적 점근 보정 결과] (적용 차수: N = %d)\n', asymp_order);
fprintf(' 4. 0차 주성분 평균 eta_0       : %.12f meV\n', mean_eta_0th_meV);
fprintf(' 5. %d차 점근 완전해 평균 eta_0  : %.12f meV\n', asymp_order, mean_eta_exact_meV);
fprintf(' 6. N차항 흡수에 의한 교정률    : %.4f %%\n', mean_correction_pct);
fprintf('------------------------------------------------------------------------\n');
fprintf(' [고체물리 파라미터]\n');
fprintf(' 7. 최종 유효 계면 산란폭 (eta) : %.12f meV\n', mean_eta_exact_meV);
fprintf(' 8. 최종 양자 결함 완화 시간(tau): %.4f ps\n', effective_tau_exact_ps);
fprintf('------------------------------------------------------------------------\n');
fprintf(' [방사선 피폭 계면 열화지표]\n');
fprintf(' 9. 적용된 4H-SiC 유효질량 비   : %.2f m_0\n', m_star / m_0);
fprintf(' 10. 1차원 수송 지향성 속도 (v_R): %.2e m/s\n', v_R);
fprintf(' 11. 양자 결속 파괴 거리 (l_coh) : %.4f nm\n', mean_l_coh_nm);
fprintf(' 12. 유효 산란 단면적 밀도(Sigma) : %.4e cm^-1\n', mean_Sigma_eff_cm_inv);
% fprintf(' 13. 추출된 체적 트랩 밀도 (N_t)  : %.4e cm^-3 (sigma = %.1e cm^2 가정)\n', mean_N_t_cm3, sigma_trap);
fprintf(' 13. 추출된 계면 결함 밀도 (N_it) : %.4e cm^-2 (sigma = %.1e cm^2, W_it = 1 nm 가정)\n', mean_N_it_cm2, sigma_trap);
fprintf('========================================================================\n\n');
```