+++
title = "temp"
weight = 5
+++

---

작성자: 김기범, 윤영준 / 일자: 2026.03.29

---

### 0. 적용 분야

금속-n형 반도체 접합면 에서 일어나는 현상에 한정한다. 본 수송 모델은 단일 전도대($m=1$)만을 고려하므로 가전자대로의 SRH 재결합 현상은 수식에서 배제된다. 따라서 본 모델은 재결합이 물리적으로 소멸하는  순방향 중간 전압(Intermediate Forward Bias) 구간의 열이온 방출(Thermionic Emission) 및 계면 양자 산란 해석에 적용된다. 여기서 도출되는 수명 $\tau$는 재결합 수명이 아닌, 전자가 장벽을 투과할 때 계면 결함에 의해 겪는 계면 투과 완화 시간(Interface Transmission Relaxation Time)을 의미한다.

완화 시간 $\tau$는 마티센의 규칙(Matthiessen's Rule)에 의해 다음과 같이 여러 산란 메커니즘의 합으로 구성된다.

$$
\frac{1}{\tau} = \frac{1}{\tau_{it} \text{ (계면 결함 포획)}} + \frac{1}{\tau_{rough} \text{ (계면 거칠기 산란)}} + \frac{1}{\tau_{phonon} \text{ (격자 진동 산란)}}
$$

- 포괄적 의미: $\tau$는 트랩에 잡히는 시간뿐만 아니라, 거친 계면에 부딪혀 튕기거나(Roughness), 포논과 충돌하여(Phonon) 파동함수의 위상(Phase)이 깨지고 뭉개지는 데 걸리는 총 양자 결속 파괴 시간(Total Quantum Decoherence Time) 을 의미한다.
- $\tau_{it}$ 으로 근사화: 소자는 양성자나 전자 빔에 피폭된 상태이다. 방사선으로 인해 계면 결함 밀도($N_{it}$)가 매우 많이 증가한 상태이므로, 계면 트랩에 의한 산란율($1/\tau_{it}$)이 다른 자연적 산란율(거칠기, 포논)을 압도하게 된다. 즉, $1/\tau \approx 1/\tau_{it}$ 가 성립한다.

---

### 1. Resolvent Operator (분해 연산자)

양자역학의 연산자는 선형대수학의 고유값 방정식을 푸는 것과 같다. 이를 일반화하여 다루기 위해 Resolvent operator 개념을 사용한다. 일반적인 연산자의 개념은 아래와 같이 표현할 수 있다.

$$
\hat{L}|\lambda\rangle=\lambda|\lambda\rangle\implies(\lambda\hat{I}-\hat{L})|\lambda\rangle=0
$$

$\lambda\hat{I}-\hat{L}$의 역행렬이 존재한다면 $|\lambda\rangle=|0\rangle$이 되어 물리적 의미가 사라진다. 반면, $E-\hat{H}$의 역행렬이 존재하지 않는다면 $|\Psi\rangle\neq|0\rangle$이 되어 유의미한 상태를 가진다. 이 역연산자를 Resolvent operator라고 정의한다.

$$
\hat{R}(\lambda)=\frac{1}{\lambda\hat{I}-\hat{L}}
$$

위 Resolvent operator를 해석적으로 풀기 위해 Sokhotski–Plemelj 정리를 사용하여 아래와 같이 극한 형태로 정의한다.

$$
\hat{R}(\lambda\pm i\eta)=\lim_{\eta\to 0^+}\frac{1}{\lambda\hat{I}-\hat{L}\pm i\eta}=\mathcal{P}\left(\frac{1}{\lambda\hat{I}-\hat{L}}\right)\mp i\pi\delta(\lambda\hat{I}-\hat{L})
$$

여기서 허수부는 시스템의 스펙트럼(존재 가능한 상태의 목록)을 의미한다. 따라서 스펙트럼 연산자 지표인 $\hat{A}$는 다음과 같다.

$$
\hat{A}(\lambda)=-\frac{1}{\pi}\text{Im}\{\hat{R}(\lambda+i\eta)\}=\delta(\lambda\hat{I}-\hat{L})
$$

이 스펙트럼 연산자를 모든 $\lambda$에 대해 적분하면, 디락 델타 함수의 성질에 의해 단위 연산자($\hat{I}$)가 된다. 이는 시스템의 모든 상태를 합치면 전체 공간이 보존됨을 의미한다.

$$
\int_{-\infty}^{\infty}d\lambda\hat{A}(\lambda)=\hat{I}
$$

---

### 2. Effective Hamiltonian Operator

결정 격자 내의 입자는 파수 $\mathbf{k}$에 의해 운동 상태가 결정되며, 인가된 전압 $V$는 소자 내부의 정전 포텐셜 지형을 변화시킨다. 따라서 모든 물리량은 $(\mathbf{k},V)$의 함수로 재정의되어야 한다. 인가된 전압 $V$에 따른 슈뢰딩거 방정식은 다음과 같다.

$$
\hat{H}(\mathbf{k},V)|\Psi_{m,\mathbf{k}}\rangle=E_m(\mathbf{k},V)|\Psi_{m,\mathbf{k}}\rangle
$$

이때의 그린 함수는 에너지 $E$와 파수 $\mathbf{k}$, 전압 $V$에 의존한다.

$$
\hat{G}(E,\mathbf{k},V)=\frac{1}{E\hat{I}-\hat{H}(\mathbf{k},V)}
$$

**1) 전압에 따른 유효 해밀토니안의 정의**

시스템 내의 특정 밴드($m$)와 파수($\mathbf{k}$) 상태에 전압 $V$가 인가되고 섭동이 발생할 시, 유효 해밀토니안은 다음과 같이 정의된다.

$$
H_{m,eff}(\mathbf{k},V)=E_{m,0}(\mathbf{k})-e\phi(V)+\Sigma_m(\mathbf{k})=E_{m,r}(\mathbf{k},V)-i\eta_m(\mathbf{k})
$$

- $E_{m,r}(\mathbf{k},V)=E_{m,0}(\mathbf{k})-e\phi(V)+\Delta_m(\mathbf{k})$: 전압에 의한 정전 포텐셜 $-e\phi(V)$와 섭동에 의한 시프트 $\Delta_m$이 반영된 실질적 공명 에너지.
- $\eta_m(\mathbf{k})$: 계면 결함 및 산란에 의해 발생하는 에너지 감쇄 폭(허수부).
- 수명 $\tau=\hbar/2\eta$

**2) 전압 의존 스펙트럼 함수 (Spectral Function)**

위 유효 해밀토니안을 그린 함수에 대입하면, 전압 $V$에 의해 에너지 축 상에서 이동하는 로렌츠 분포 형태의 스펙트럼 함수를 얻는다.

$$
G_m(E,\mathbf{k},V)=\frac{1}{E-E_{m,r}(\mathbf{k},V)+i\eta_m(\mathbf{k})}
$$

$$
A_m(E,\mathbf{k},V)=-\frac{1}{\pi}\text{Im}\{G_m(E,\mathbf{k},V)\}=\frac{1}{\pi}\frac{\eta_m(\mathbf{k})}{(E-E_{m,r}(\mathbf{k},V))^2+\eta_m(\mathbf{k})^2}
$$

전압 $V$가 변화함에 따라 로렌츠 피크의 중심점 $E_{m,r}(\mathbf{k},V)$이 이동하며, 이는 전자가 통과할 수 있는 '에너지 통로'가 전압에 의해 제어됨을 의미한다. 특정 $(\mathbf{k},V)$ 지점에서의 에너지 적분값은 확률 보존 법칙에 의해 항상 1이다.

$$
\int_{-\infty}^{\infty}A_m(E,\mathbf{k},V)dE=1
$$

---

### 3. 상태밀도(DOS) 및 전류 밀도($\mathbf{J}$)의 비평형 확장

전압 $V$가 인가된 시스템은 열적 평형 상태를 벗어나며, 이에 따라 상태밀도와 입자 수송 식은 전위차에 의한 분포 함수의 변화를 반영해야 한다.

**1) 전압 의존 상태밀도 (Total DOS)**

시스템 전체의 상태밀도는 인가된 전압 $V$에 의해 변형된 각 밴드와 파수 공간의 스펙트럼 함수를 모두 합산하여 정의된다.

$$
\rho(E,V)=\sum_m\int\frac{d^dk}{(2\pi)^d}A_m(E,\mathbf{k},V)
$$

여기서 $A_m(E,\mathbf{k},V)$는 앞서 정의한 로렌츠 분포를 따르며, 전압에 의해 에너지 축 상에서 이동(Shift)된 상태이다. 모든 에너지에 대한 적분값은 시스템의 총 상태 수 $N$을 유지한다.

$$
\int_{-\infty}^{\infty}dE\rho(E,V)=N
$$

**2) 비평형 분포 함수와 바이어스 윈도우 (Bias Window)**

전압 $V$가 인가되면 전극의 화학 포텐셜이 분리된다. 이를 통해 전류에 기여하는 실질적인 에너지 구간이 결정된다.

- 왼쪽 전극 화학 포텐셜: $\mu_L=\mu_0+\delta\mu_L(V)$
- 오른쪽 전극 화학 포텐셜: $\mu_R=\mu_0-\delta\mu_R(V)$
- 전위차 조건: $\mu_L-\mu_R=eV$

이에 따라, 알짜 전류(Net Current)는 왼쪽에서 오른쪽으로 흐르는 입자와 반대 방향으로 흐르는 입자의 점유 확률 차이인 $[f(E,\mu_L)-f(E,\mu_R)]$에 의해 발생한다.

**3) 전류 밀도($\mathbf{J}$)**

최종적으로 전압 $V$에 따른 전류 밀도 $\mathbf{J}(V)$는 스펙트럼 함수(존재 가능성), 속도(이동성), 그리고 비평형 분포 차이(흐름의 원동력)를 결합하여 다음과 같이 정의된다.

$$
\mathbf{J}(V)=e\sum_m\int_{-\infty}^{\infty}dE\left[f(E,\mu_L)-f(E,\mu_R)\right]\int\frac{d^dk}{(2\pi)^d}\left[A_m(E,\mathbf{k},V)\cdot\mathbf{v}_m(\mathbf{k})\right]
$$

여기서 속도 항은 밴드 구조의 기울기에 의해 결정되는 군속도(Group velocity)이다.

$$
\mathbf{v}_m(\mathbf{k})=\frac{1}{\hbar}\nabla_{\mathbf{k}}E_{m,r}(\mathbf{k},V)
$$

---

### 4. 완화 수명 $\tau$

유효 해밀토니안 $\hat{H}_{eff}(\mathbf{k},V)=E_{m,r}(\mathbf{k},V)-i\eta_m(\mathbf{k})$를 시간 의존성 슈뢰딩거 방정식에 대입한다. 특정 상태 $(m,\mathbf{k})$의 파동함수 $|\Psi(t)\rangle$의 진화는 다음과 같다.

$$
i\hbar\frac{\partial}{\partial t}|\Psi(t)\rangle=\hat{H}_{eff}|\Psi(t)\rangle
$$

이 선형 미분 방정식의 해는 시간 진화 연산자(Time-evolution operator)를 통해 다음과 같이 표현된다.

$$
|\Psi(t)\rangle=\exp\left(-\frac{i\hat{H}_{eff}t}{\hbar}\right)|\Psi(0)\rangle
$$

여기에 $H_{m,eff}=E_{m,r}-i\eta_m$을 대입하여 지수항을 분리한다.

$$
|\Psi(t)\rangle=\exp\left(-\frac{i(E_{m,r}-i\eta_m)t}{\hbar}\right)|\Psi(0)\rangle=\exp\left(-\frac{iE_{m,r}t}{\hbar}\right)\cdot\exp\left(-\frac{\eta_mt}{\hbar}\right)|\Psi(0)\rangle
$$

- 실수 에너지 항 ($\exp(-iE_{m,r}t/\hbar)$): 시간에 따른 위상 진동(Phase oscillation)을 결정한다.
- 허수 에너지 항 ($\exp(-\eta_mt/\hbar)$): 진폭의 지수적 감쇄(Exponential decay)를 결정한다. 본 모델에서는 이를 계면 산란에 의한 위상 이완으로 해석한다.

입자가 해당 상태 $(m,\mathbf{k})$에 존재할 확률 $P(t)$는 파동함수의 절대값 제곱으로 정의된다.

$$
P(t)=|\langle\Psi(t)|\Psi(t)\rangle|=\left|e^{-iE_{m,r}t/\hbar}\right|^2\cdot\left|e^{-\eta_mt/\hbar}\right|^2\cdot P(0)
$$

실수 지수항의 절대값 제곱은 1이므로($|e^{ix}|^2=1$), 확률 밀도는 다음과 같이 축약된다.

$$
P(t)=P(0)\exp\left(-\frac{2\eta_mt}{\hbar}\right)
$$

통계역학 및 입자 물리학에서 수명($\tau$)은 확률 밀도가 초기값의 $1/e$로 감소하는 시간으로 정의된다. 즉, 감쇄 법칙 $P(t)=P(0)e^{-t/\tau}$와 위 식을 직접 비교(Mapping)한다.

$$
\exp\left(-\frac{t}{\tau_m(\mathbf{k})}\right)=\exp\left(-\frac{2\eta_m(\mathbf{k})t}{\hbar}\right)
$$

지수 부분을 비교하면,

$$
\frac{1}{\tau_m(\mathbf{k})}=\frac{2\eta_m(\mathbf{k})}{\hbar}\implies\tau_m(\mathbf{k})=\frac{\hbar}{2\eta_m(\mathbf{k})}
$$

스펙트럼 함수 $A_m(E,\mathbf{k},V)$의 반치폭(FWHM)과의 연결을 하면, $A_m(E,V)$의 형태는 다음과 같다.

$$
A_m(E,V)=\frac{1}{\pi}\frac{\eta_m}{(E-E_{m,r})^2+\eta_m^2}
$$

이 분포에서 함숫값이 피크($E=E_{m,r}$)의 절반이 되는 에너지 지점 $E_{half}$를 구한다.

$$
\frac{1}{2}A_m(E_{m,r})=A_m(E_{half})\implies\frac{1}{2}\left(\frac{1}{\pi\eta_m}\right)=\frac{1}{\pi}\frac{\eta_m}{(E_{half}-E_{m,r})^2+\eta_m^2}
$$

이를 풀면 $(E_{half}-E_{m,r})^2=\eta_m^2$이 되며, 따라서 $E_{half}=E_{m,r}\pm\eta_m$이다. 전체 반치폭(Full Width at Half Maximum, $\Gamma$)은 두 지점의 차이이다.

$$
\Gamma_m(\mathbf{k})=(E_{m,r}+\eta_m)-(E_{m,r}-\eta_m)=2\eta_m(\mathbf{k})
$$

최종적으로, 완화 수명 $\tau$와 스펙트럼의 계면 산란 반치폭 $\Gamma$ 사이의 관계는 다음과 같이 완성된다.

$$
\tau_m(\mathbf{k})=\frac{\hbar}{\Gamma_m(\mathbf{k})}=\frac{\hbar}{2\eta_m(\mathbf{k})}
$$

---

### 5. J-V curve로 부터, $\tau_{it}$ 의 유도

**1) 5대 가정**

- 1차원 단일 대역 전송: 수송은 접합면에 수직인 단일 방향($z$)으로 지배되며, 단일 전도대($m=1$)만 고려 (재결합 배제)
- 포물선 대역 및 유효 질량: 밴드 에지 근처에서 $E_r(k)=\Phi_B+\frac{\hbar^2k^2}{2m^*}$가 성립
- 국소적 상수 산란율 ($\eta_0$): 장벽 근처 좁은 에너지 창($\sim k_BT$) 내에서 라이프 타임 뭉개짐 폭 $\eta_0$는 에너지에 독립적인 상수로 취급
- 볼츠만 분포 근사: $E-\mu\gg k_BT$ 조건에서 페르미-디락 분포를 지수 함수로 근사
- 정전기적 선형성: 좁은 전압 구간 내에서 장벽 하강률($d\Phi_B/dV$)은 국소적으로 일정

**2) 초기 상태 및 1차원 축소**

다차원 수송 방정식은 아래와 같다.

$$
\mathbf{J}(V)=e\sum_m\int_{-\infty}^{\infty}dE\left[f(E,\mu_L)-f(E,\mu_R)\right]\int\frac{d^dk}{(2\pi)^d}\left[A_m(E,\mathbf{k},V)\cdot\mathbf{v}_m(\mathbf{k})\right]
$$

전하 수송이 접합면에 수직인 1차원으로 지배된다고 가정하고, 단일 전도대(Conduction band)를 고려하여 $\sum_m$과 횡방향 파수 적분을 생략한다. 전진하는 캐리어($k>0$)만 고려하면 다음과 같이 축소된다.

$$
J(V)=e\int_{-\infty}^{\infty}dE\left[f(E,\mu_L)-f(E,\mu_R)\right]\int_{0}^{\infty}\frac{dk}{2\pi}A(E,k,V)v(k)
$$

**3) 포물선 대역 및 유효 질량 근사**

전도대 하단의 에너지를 아래와 같이 근사한다.

$$
E_r(k,V)=\Phi_B(V)+\frac{\hbar^2k^2}{2m^*}
$$

군속도는

$$
v(k)=\frac{1}{\hbar}\frac{\partial E_r}{\partial k}=\frac{\hbar k}{m^*}
$$

운동 에너지 $\epsilon_k=\hbar^2k^2/2m^*$를 도입하면, 미분 관계식 $d\epsilon_k=\frac{\hbar^2k}{m^*}dk=\hbar v(k)dk$가 성립한다. 플랑크 상수 $h=2\pi\hbar$를 사용하여 파수 적분을 에너지 적분으로 변환한다.

$$
\frac{dk}{2\pi}v(k)=\frac{d\epsilon_k}{2\pi\hbar}=\frac{d\epsilon_k}{h}
$$

**4) 로렌츠 스펙트럼 대입 및 전송 함수 도출**

국소적으로 일정한 계면 산란율 $\eta_0$를 갖는 스펙트럼 함수를 대입한다.

$$
A(E,\epsilon_k,V)=\frac{1}{\pi}\frac{\eta_0}{[E-(\Phi_B(V)+\epsilon_k)]^2+\eta_0^2}
$$

전송 함수 $U(E,V)$는 $\epsilon_k$에 대한 0부터 $\infty$까지의 적분이 된다.

$$
U(E,V)=\frac{1}{h}\int_{0}^{\infty}d\epsilon_k\frac{1}{\pi}\frac{\eta_0}{(E-\Phi_B(V)-\epsilon_k)^2+\eta_0^2}
$$

아크탄젠트 미분 공식을 적용한다.

$$
U(E,V)=\frac{1}{h}\left[\frac{1}{2}+\frac{1}{\pi}\arctan\left(\frac{E-\Phi_B(V)}{\eta_0}\right)\right]
$$

**5) 볼츠만 근사와 페르미 준위의 분리**

$E-\mu\gg k_BT$인 조건에서,

$$
f(E,\mu)\approx\exp\left(-\frac{E-\mu}{k_BT}\right)
$$

정의한 구동력 항은 양단 전극(금속과 반도체)의 비평형 분포 차이에서 온다.

$$
\Delta F(V)=\exp\left(\frac{\mu_L}{k_BT}\right)-\exp\left(\frac{\mu_R}{k_BT}\right)
$$

최종 적분식은 다음과 같다.

$$
J(V)=\frac{e}{h}\Delta F(V)\int_{E_{min}}^{\infty}dE\exp\left(-\frac{E}{k_BT}\right)U(E,V)
$$

**6) 부분 적분**

위 식의 적분항을 $\mathcal{I}$라 하고, 이 적분식에 대해 $dv = \exp(-E/k_BT)dE$ 로 두고, 소멸하는 상한선($E \to \infty$)을 배제한 채 하한선($E=E_{min}$)에 대한 부분 적분을 $N$번 연속 수행한다.
$$
\mathcal{I}(V)=\int_{E_{min}}^{\infty}dE\exp\left(-\frac{E}{k_BT}\right)U(E)
$$

$$
\mathcal{I} = k_BT \exp\left(-\frac{E_{min}}{k_BT}\right) U(E_{min}) + k_BT \int_{E_{min}}^{\infty} dE \, U'(E) \exp\left(-\frac{E}{k_BT}\right)
$$

$$
\mathcal{I} = k_BT \exp\left(-\frac{E_{min}}{k_BT}\right) [U(E_{min}) + k_BT U'(E_{min})] + (k_BT)^2 \int_{E_{min}}^{\infty} dE \, U''(E,V) \exp\left(-\frac{E}{k_BT}\right)
$$

이를 무한대($N \to \infty$)로 확장하면, 적분 기호가 완전히 사라지고 오직 $E_{min}$에서의 미분계수들로만 이루어진 무한 점근 급수(Infinite Asymptotic Series) 형태가 나온다.

$$
\mathcal{I} \sim k_BT \exp\left(-\frac{E_{min}}{k_BT}\right) \sum_{n=0}^{\infty} (k_BT)^n U^{(n)}(E_{min},V)
$$

이제 투과도 함수 $U(E)$를 $E_{min}$에서 $n$번 미분한 값들을 평가한다. ($\Delta_E = \Phi_B - E_{min} \gg \eta_0$)

$$
U(E_{min},V)
= \frac{1}{2} + \frac{1}{\pi} \arctan\left(\frac{-\Delta_E}{\eta_0}\right)
\approx\frac{1}{2}+\frac{1}{\pi}\left(-\frac{\pi}{2}+\frac{\eta_0}{\Phi_B-E_{min}}\right)
= \frac{\eta_0}{\pi \Delta_E}
$$

$$
U'(E_{min},V) = \frac{\eta_0}{\pi} \frac{1}{(-\Delta_E)^2 + \eta_0^2} \approx \frac{\eta_0}{\pi \Delta_E^2}
$$

$$
U''(E_{min},V) = \frac{\eta_0}{\pi} \frac{2\Delta_E}{(\Delta_E^2 + \eta_0^2)^2} \approx \frac{\eta_0}{\pi} \frac{2!}{\Delta_E^3}
$$

로렌츠 함수의 $n$번 미분 점근형 공간에 의해 규칙성이 성립한다.

$$
U^{(n)}(E_{min},V) \approx \frac{\eta_0}{\pi} \frac{n!}{\Delta_E^{n+1}}
$$

**8) 최종 점근 함수**

구해낸 $n$계 도함수 일반항을 무한 점근 급수 식에 그대로 대입한다.

$$
\mathcal{I} \sim k_BT \exp\left(-\frac{E_{min}}{k_BT}\right) \left[ \frac{\eta_0}{\pi \Delta_E} + \sum_{n=1}^{\infty} (k_BT)^n \frac{\eta_0}{\pi} \frac{n!}{\Delta_E^{n+1}} \right]
$$

공통항인 $\eta_0/(\pi \Delta_E)$ 를 밖으로 묶어낸다.

$$
\mathcal{I} \sim \left[ \frac{\eta_0 k_BT}{\pi \Delta_E} \exp\left(-\frac{E_{min}}{k_BT}\right) \right] \times \left[ 1 + \sum_{n=1}^{\infty} n! \left( \frac{k_BT}{\Delta_E} \right)^n \right]
$$

앞의 대괄호 항은 0차 선형 근사이다. 이를 $\mathcal{I}_0$ 라 정의하면,

$$
\mathcal{I} \sim \mathcal{I}_0 \sum_{n=0}^{\infty} n! \left( \frac{k_BT}{\Delta_E} \right)^n
$$

**8) 전류 밀도 전개**

$$
J(V)=\frac{ek_BT}{h}\Delta F(V)\left[\exp\left(-\frac{\Phi_B(V)}{k_BT}\right)+\frac{\eta_0}{\pi(\Phi_B(V)-E_{min})}\exp\left(-\frac{E_{min}}{k_BT}\right)\right]
$$

모든 변수가 상수화된 전류 방정식에서 $\eta_0$에 대하여 식을 이항하여 정리한다.

$$
\eta_0=\pi(\Phi_B(V)-E_{min})\exp\left(\frac{E_{min}}{k_BT}\right)\left[\frac{h\cdot J_{exp}(V)}{ek_BT\cdot\Delta F(V)}-\exp\left(-\frac{\Phi_B(V)}{k_BT}\right)\right]
$$

- $J_{exp}(V)$: 실험에서 측정된 전체 비이상적 전류 밀도
- $\Phi_B(V)$: C-V 측정으로부터 독립적으로 산출된 확정 정전기적 장벽
- $E_{min}$: 밴드 다이어그램으로부터 도출되는 밴드 에지 상수 (확정값)

**9) 페르미 준위의 분리**

전류의 방향을 반도체(Left, $L$)에서 금속(Right, $R$)으로 넘어가는 전자의 흐름으로 정의한다. 에너지의 절대 기준점(Reference)을 금속의 페르미 준위로 설정한다.

$$
\mu_R=\mu_M=0
$$

순방향 바이어스 $V$가 인가되면, 반도체의 페르미 준위는 금속에 비해 $eV$만큼 상승한다.

$$
\mu_L=\mu_S=eV
$$

이 확정된 절대 기준점 에너지를 구동력 항에 대입하여 $\Delta F(V)$를 대수적으로 결정한다.

$$
\Delta F(V)=\exp\left(\frac{\mu_L}{k_BT}\right)-\exp\left(\frac{\mu_R}{k_BT}\right)=\exp\left(\frac{eV}{k_BT}\right)-1
$$

**10) $E_{min}$의 정의**

전도대 최하단 ($E_c$) : 우리가 계산하는 전류는 반도체에서 금속으로 넘어가는 전자들의 흐름이다. 반도체 내부의 전자는 밴드갭(Bandgap) 내에 존재할 수 없으며, 오직 전도대(Conduction Band) 위에만 존재한다. 따라서 전자가 가질 수 있는 가장 낮은 물리적 에너지 한계선이 바로 벌크(Bulk) 반도체의 전도대 최하단 에너지($E_c$)가 된다. 즉, $E_{min}\equiv E_c$이다.

이 $E_{min}$ 값을 알아내기 위해, 앞서 $\Delta F(V)$를 구할 때 사용했던 에너지 기준점(Reference Energy)을 사용한다.

- 기준점: 금속의 페르미 준위를 $0$으로 둔다. ($\mu_M=0$)
- 반도체의 페르미 준위: 순방향 전압 $V$가 인가되었으므로, 반도체의 페르미 준위는 $\mu_S=eV$가 된다.
- 열역학적 깊이 ($eV_n$): 반도체 벌크 영역에서 전도대 최하단($E_c$)은 페르미 준위($\mu_S$)보다 특정 에너지만큼 위에 떠 있다. 이 간격을 $eV_n$이라고 하며, 통계 역학에 의해 다음 식을 따른다.

$$
eV_n=k_BT\ln\left(\frac{N_C}{N_D}\right)
$$

여기서 $N_C$는 유효 상태 밀도 상수이고, $N_D$는 앞서 C-V 플롯의 기울기에서 확정해 낸 도핑 농도이다. 결과적으로, 전자가 존재할 수 있는 최하단 에너지 $E_{min}$은 페르미 준위와 열역학적 깊이의 합으로 결정된다.

$$
E_{min}=eV+eV_n
$$

위에서 구한 $E_{min}$를 핵심 항인 $(\Phi_B-E_{min})$에 대입한다. 샤키 장벽 $\Phi_B$는 다음과 같이 정의된다.

$$
\Phi_B=e(V_{bi}+V_n)
$$

이제 이 둘을 빼면,

$$
\Phi_B-E_{min}=e(V_{bi}+V_n)-(eV+eV_n)=e(V_{bi}-V)
$$

**11) 최종 식**

앞서 도출한 추출 방정식의 뼈대에, 8) & 9)를 대입한다. 외부의 $\exp(E_{min}/k_BT)$를 대괄호 안으로 분배한다.

$$
\eta_0=\pi(\Phi_B-E_{min})\left[\frac{h\cdot J_{exp}(V)}{ek_BT\cdot\Delta F(V)}\exp\left(\frac{E_{min}}{k_BT}\right)-\exp\left(-\frac{\Phi_B-E_{min}}{k_BT}\right)\right]
$$

9)의 밴드 휨 치환을 수행한다. $\Phi_B-E_{min}=e(V_{bi}-V)$를 대입한다. 두 번째 지수 항이 완성된다.

$$
\eta_0=\pi e(V_{bi}-V)\left[\frac{h\cdot J_{exp}(V)}{ek_BT\cdot\Delta F(V)}\exp\left(\frac{E_{min}}{k_BT}\right)-\exp\left(-\frac{e(V_{bi}-V)}{k_BT}\right)\right]
$$

제1항의 분자 $\exp(E_{min}/k_BT)$에 $E_{min}=eV+k_BT\ln(N_C/N_D)$를 대입한다.

$$
\exp\left(\frac{E_{min}}{k_BT}\right)=\exp\left(\frac{eV}{k_BT}\right)\exp\left(\ln\frac{N_C}{N_D}\right)=\exp\left(\frac{eV}{k_BT}\right)\left(\frac{N_C}{N_D}\right)
$$

제1항의 분모에 있는 $\Delta F(V)=\exp(eV/k_BT)-1$과 결합하여 나눈다.

$$
\frac{\exp\left(\frac{E_{min}}{k_BT}\right)}{\Delta F(V)}=\frac{\exp\left(\frac{eV}{k_BT}\right)}{\exp\left(\frac{eV}{k_BT}\right)-1}\left(\frac{N_C}{N_D}\right)=\frac{1}{1-\exp\left(-\frac{eV}{k_BT}\right)}\left(\frac{N_C}{N_D}\right)
$$

제1항에 대입하면, 완성이다. (Q.E.D.) 오직 측정 가능한 물리량과 보편 상수만으로 이루어진 최종 선형 대수 방정식이다.

$$
\eta_0=\pi e(V_{bi}-V)\left[\frac{h\cdot J_{exp}(V)}{ek_BT}\cdot\frac{N_C/N_D}{1-\exp\left(-\frac{eV}{k_BT}\right)}-\exp\left(-\frac{e(V_{bi}-V)}{k_BT}\right)\right]
$$

**11) 3차원 차원 정합성 복원**

앞서 도출한 유효 해밀토니안과 로렌츠 스펙트럼 기반의 비이상적 전류 추출 방정식은 전자 수송을 접합면에 수직인 1차원($z$축) 단일 양자 채널로 가정하여 전개되었다. 그러나 실제 면적($A$)을 갖는 3차원 벌크(Bulk) 소자의 측정 데이터인 전류 밀도 $J_{exp}$ (단위: $\text{A/m}^2$)에 이를 적용하기 위해서는, 횡방향 운동량($\mathbf{k}_{\perp}$)에 대한 상태 밀도(Density of States) 적분을 통해 3차원 공간으로 차원을 정합해야 한다.

3차원 벌크 소자 내 전자의 총 에너지 $E(\mathbf{k})$는 장벽 방향($z$)의 수송 에너지 $E_z$와 횡방향($x,y$) 평면의 병진 운동 에너지 $E_{\perp}$로 분리된다.

$$
E(\mathbf{k})=E_z(k_z)+E_{\perp}(\mathbf{k}_{\perp})=\left(\Phi_B(V)+\frac{\hbar^2k_z^2}{2m^*}\right)+\frac{\hbar^2k_{\perp}^2}{2m^*}
$$

3차원 운동량 공간에서의 체적 적분소 $d^3k$는 원통 좌표계(Cylindrical coordinate)를 적용하여 다음과 같이 분해된다.

$$
d^3k=dk_z\,d^2\mathbf{k}_{\perp}=dk_z\,(2\pi k_{\perp}dk_{\perp})
$$

여기서 횡방향 에너지 $E_{\perp}=\frac{\hbar^2k_{\perp}^2}{2m^*}$를 미분하면 $dE_{\perp}=\frac{\hbar^2}{m^*}k_{\perp}dk_{\perp}$가 성립하므로, 횡방향 파수 적분소는 에너지 적분소로 치환된다.

$$
d^2\mathbf{k}_{\perp}=2\pi\frac{m^*}{\hbar^2}dE_{\perp}
$$

전자의 스핀 축퇴도($g_s=2$)를 반영하여 3차원 전류 밀도 방정식 $\mathbf{J}(V)$를 재구성한다.

$$
\mathbf{J}(V)=2e\int\frac{d^3k}{(2\pi)^3}v_z(k_z)U(E_z,V)\left[f(E,\mu_L)-f(E,\mu_R)\right]
$$

볼츠만 분포 근사($E-\mu\gg k_BT$) 하에서, 지수 함수는 수직 방향과 횡방향으로 분리된다. $\exp(-E/k_BT)=\exp(-E_z/k_BT)\exp(-E_{\perp}/k_BT)$. 이를 수식에 대입하고 적분 변수를 분리한다.

$$
\mathbf{J}(V)=2e\int\frac{dk_z}{2\pi}v_zU(E_z)e^{-E_z/k_BT}\int\frac{d^2\mathbf{k}_{\perp}}{(2\pi)^2}e^{-E_{\perp}/k_BT}
$$

우측의 횡방향 적분항($I_{\perp}$)만을 먼저 해석적으로 적분한다. $d^2\mathbf{k}_{\perp}=\frac{2\pi m^*}{\hbar^2}dE_{\perp}$를 대입한다.

$$
I_{\perp}=\int_{0}^{\infty}\frac{1}{(2\pi)^2}\left(\frac{2\pi m^*}{\hbar^2}\right)e^{-E_{\perp}/k_BT}dE_{\perp}=\frac{m^*}{2\pi\hbar^2}\int_{0}^{\infty}e^{-E_{\perp}/k_BT}dE_{\perp}
$$

지수 함수 적분 결과, 우변의 적분은 $k_BT$가 된다.

$$
I_{\perp}=\frac{m^*k_BT}{2\pi\hbar^2}
$$

이제 좌측의 $z$방향 적분항을 본다. 군속도 $v_zdk_z=dE_z/\hbar$ 관계를 이용해 $k_z$를 $E_z$로 치환한다. $h=2\pi\hbar$임을 상기한다.

$$
J_z=\int\frac{dk_z}{2\pi}v_z(\dots)=\int\frac{dE_z}{2\pi\hbar}(\dots)=\int\frac{dE_z}{h}(\dots)
$$

전체 식을 조립하면 선행 계수는 다음과 같이 묶인다. $\hbar^2=h^2/4\pi^2$을 대입한다.

$$
\mathbf{J}(V)=\left(2e\cdot\frac{m^*k_BT}{2\pi(h^2/4\pi^2)}\cdot\frac{1}{h}\right)\int_{E_{min}}^{\infty}dE_zU(E_z)e^{-E_z/k_BT}
$$

$$
\text{Prefactor}=\frac{4\pi em^*k_BT}{h^3}
$$

앞선 1차원 유도(Section 5 - 6항)에서 $E_z$ 방향 적분 시 $\int dE_ze^{-E_z/k_BT}(\dots)$ 부분 적분을 통해 추가적인 $k_BT$가 도출되었음을 상기하라. 이 추가적인 $k_BT$를 선행 계수와 결합하면 3차원 열이온 방출의 상수인 Richardson-Dushman 상수($A^*$)가 증명된다.

$$
A^*T^2=\left(\frac{4\pi em^*k_B^2}{h^3}\right)T^2
$$

1차원 모델에서 전류 스케일을 결정짓던 양자 전도도 선행 계수 $\frac{ek_BT}{h}$를 3차원 거시 밀도 상수 $A^*T^2$로 치환함으로써, 차원 붕괴가 해결된 역산 방정식이 도출된다.

$$
\eta_0=\pi e(V_{bi}-V)\left[\frac{J_{exp}(V)}{A^*T^2}\cdot\frac{N_C/N_D}{1-\exp\left(-\frac{eV}{k_BT}\right)}-\exp\left(-\frac{e(V_{bi}-V)}{k_BT}\right)\right]
$$

이 방정식의 대괄호 내부 제1항은 $J_{exp}\,[\text{A/m}^2]$를 $A^*T^2\,[\text{A/m}^2]$로 나누어 무차원(Dimensionless) 확률 상태로 변환하며, 3차원 벌크 4H-SiC 소자 임의의 면적 조건에서도 금속-반도체 계면의 양자 스펙트럼 폭 $\eta_0$와 거시적 유효 계면 투과 수명 $\tau$를 추출해 낼 수 있다.

---

### 6. 실험 시나리오 및 유효 전압 구간(Window)

본 수송 모델은 단일 전도대($m=1$) 전송만을 가정하여 유도되었으므로, 벌크 내부의 SRH 공간 전하 재결합(Space-Charge Recombination) 메커니즘이 수식에서 배제되어 있다. 따라서 본 모델을 통해 계면(Interface)의 순수한 양자 산란율($\eta_{0,interface}$)을 역산하기 위해서는, 전체 다이오드 전류에서 재결합 전류가 1% 미만으로 소멸하고 계면 장벽 투과 전류(Thermionic Emission)만이 지배하는 중간 순방향 바이어스 구간(Intermediate Forward Bias) 의 데이터만을 취사선택해야 한다.

**1) 하한선 결정 ($V_{lower}$): 재결합 전류의 소멸 지점**

계면을 넘는 열이온 방출 전류($J_{TE}$, 이상 주계수 $n=1$)가 벌크 공핍층 내부의 공간 전하 재결합 전류($J_{rec}$, 이상 주계수 $n=2$)를 물리적으로 역전하여 지배하기 시작하는 교차점(Crossover point)을 구한다. 두 전류 방정식의 크기가 같아지는 지점($J_{TE}=J_{rec}$)의 전압을 산출한다.

$$
A^*T^2\exp\left(-\frac{\Phi_B}{k_BT}\right)\exp\left(\frac{eV}{k_BT}\right)=\frac{en_iW}{2\tau_{SRH}}\exp\left(\frac{eV}{2k_BT}\right)
$$

양변을 전압 지수항 $\exp(eV/2k_BT)$에 대해 정리하고 자연로그($\ln$)를 취하면 교차 전압 $V_{lower}$가 도출된다.

$$
V_{lower}=\frac{2k_BT}{e}\ln\left(\frac{en_iW}{2\tau_{SRH}A^*T^2}\exp\left(\frac{\Phi_B}{k_BT}\right)\right)=\frac{2k_BT}{e}\ln\left(\frac{en_iW}{2\tau_{SRH}A^*T^2}\right)+\frac{2\Phi_B}{e}
$$

4H-SiC SBD의 상온 물성치($T=300\text{K}$, $n_i\approx 10^{-8}\text{ cm}^{-3}$, $\tau_{SRH}\sim 1\mu\text{s}$, $\Phi_B=1.716\text{ V}$)를 대입할 경우, 교차점은 $V_{lower}\approx 0.238\text{ V}$ 이다. 단, 이 교차점에서는 재결합 전류가 전체의 50%나 혼입되어 있으므로, 지수 함수 성장률(Exponential Growth)을 고려하여 오차율을 1% 미만으로 억제하기 위해서는 교차점 대비 전류 증가가 뚜렷한 전압 윈도우($V\ge 1\text{ V}$)를 선택해야 한다.

**2) 상한선 결정 ($V_{upper}$): 볼츠만 근사의 붕괴 한계점**

본 모델은 5절 5항에서 전자의 점유 확률을 지수 함수로 단순화하는 볼츠만 근사($E-\mu\gg k_BT$)를 전제하였다. 전자가 직면하는 유효 에너지 장벽 $e(V_{bi}-V)$가 열에너지 $k_BT$ 대비 최소 3배 이상 커야만 통계적 오차율이 5% 미만으로 통제된다.

$$
e(V_{bi}-V)\ge 3k_BT\implies V\le V_{bi}-\frac{3k_BT}{e}
$$

상온($300\text{K}$)에서 $3k_BT/e\approx 0.0775\text{ V}$이므로, 볼츠만 근사와 평탄대(Flat-band) 조건이 벗어나는 것을 피하기 위한 최대 인가 전압의 상한선은  $V_{upper}=V_{bi}-0.0775\text{ V}\approx 1.465\text{ V}$ 이다.

**3) 데이터 추출 구간 확정**

재결합 전류의 간섭을 차단하고 볼츠만 근사의 수학적 가정을 적용하기 위한 최종 적용 윈도우는 다음과 같이 결정된다.

$$
1.0\text{ V}\quad\le\quad V_{applied}\quad\le\quad 1.465\text{ V}
$$

---

### 7. 결과

| 측정 조건 (Width) | 평균 $\eta_{0,it}$ (neV) | 평균 $\tau_{it}$ ($\mu$s) |
| :--- | :--- | :--- |
| 순방향 (1.0V ~ 1.46V) |     |      |

---

### 8. 코드

```matlab
%% 1. 보편 물리 상수 및 4H-SiC 표준 물성 (SI 단위계 통일)
q = 1.60217663e-19;       
kB = 1.380649e-23;        
T = 300;                  
h = 6.62607015e-34;       
hbar = h / (2 * pi);      
kT_J = kB * T;            
kT_eV = kT_J / q;         

% [소자 고유 파라미터 - C-V 측정 등 확정된 데이터 대입]
V_bi = 1.8345;             % 빌트인 포텐셜 (V)
N_D = 1.09e+16 * 1e6;      % 에피층 도핑 농도 (m^-3)
N_C = 1.7e19 * 1e6;        % 전도대 유효 상태 밀도 (m^-3)
A_star = 146 * 10000;      % Richardson 상수 (A/m^2-K^2)
Radius_um = 350;           % 다이오드 반경 (um)
Area = pi * (Radius_um * 1e-6)^2; % 유효 접촉 면적 (m^2)

%% 2. 실험 데이터 로드 및 노이즈 필터링
data = readmatrix('SiC_IV.csv');
V_raw = data(:, 1);
I_raw = abs(data(:, 5));  
J_raw = I_raw / Area;     

% 물리적으로 유효한 양수 데이터만 추출
valid_idx = ~isnan(V_raw) & ~isnan(J_raw) & (J_raw > 1e-12);
V_app = V_raw(valid_idx);
J_exp = J_raw(valid_idx);

%% 3. 직렬 저항 (Rs) 자동 산출 및 V_eff 보정 (엄밀한 물리적 한계선 적용)
% [3-1] 미분 저항 및 Cheung's Method용 변수 산출
ln_J = log(J_exp);
dV_dlnJ = gradient(V_app) ./ gradient(ln_J);
dV_dJ = gradient(V_app) ./ gradient(J_exp); % 미분 저항 (R_diff = dV/dJ)

% [3-2] 물리적 한계선 설정: 측정된 가장 순수한 최소 미분 저항 탐색
% R_s는 이 최소 미분 저항(min_Rdiff)을 물리적으로 초과할 수 없습니다. (V_eff 역주행 방지)
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

        % 추출된 정확한 국소 위치만 윈도우로 시각화 (5V 전체 덮임 기만 방지)
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
% 예기치 못한 수치 오류로 Rs_Area가 min_Rdiff를 초과하여 V_eff가 역주행하는 것을 최종 차단
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

%% 5. 사용자 해석적 대수 방정식 적용 (엄밀한 유효 평균 적용)
Term_Current = J_eta ./ (A_star * T^2);
Term_Fermi = (N_C / N_D) ./ (1 - exp(-V_eta / kT_eV));
Term_Ideal = exp(-(V_bi - V_eta) / kT_eV);

% 개별 포인트의 eta_0 연산 (단위: Joules 및 meV)
eta_0_J = pi * q * (V_bi - V_eta) .* (Term_Current .* Term_Fermi - Term_Ideal);
eta_0_meV = (eta_0_J / q) * 1e3;               

% 개별 tau 배열은 시각화(그래프) 목적으로만 산출 (단위: ps)
tau_array_ps = (hbar ./ (2 * eta_0_J)) * 1e12;       

% [핵심] 수학적 특이점 발산을 배제한 엄밀한 '대푯값' 산출
mean_eta_J = mean(eta_0_J, 'omitnan');
mean_eta_meV = mean(eta_0_meV, 'omitnan');

% 평균 계면 산란폭(mean_eta_J)을 기반으로 '유효 계면 완화 시간' 역산
effective_mean_tau_ps = (hbar / (2 * mean_eta_J)) * 1e12; 

%% 6. 결과 시각화 (기존 시각화 형식 완벽 복원)
figure('Name', 'Rigorous Physical Extraction', 'Color', 'w', 'Position', [50 100 1500 500]);

% [Subplot 1] 반대수 I-V 곡선 (Log Scale)
subplot(1, 3, 1);
semilogy(V_app, J_exp, 'k.', 'MarkerSize', 8, 'DisplayName', 'Measured (V_{app})'); hold on;
semilogy(V_eff, J_exp, 'r-', 'LineWidth', 1.5, 'DisplayName', 'R_s Corrected (V_{eff})');
xline(V_lower_auto, 'b--', 'V_{lower} (n < 1.3333)'); 
xline(V_upper_auto, 'b--', 'V_{upper} (eta_0 > 0 Last)');
xlabel('Voltage (V)'); ylabel('Current Density (A/m^2)'); 
title('Forward I-V (Log)'); grid on;
legend('Location', 'northwest');

% [Subplot 2] 선형 I-V 곡선 (Linear Scale) - 노란색 박스 범례 및 형식 복구
subplot(1, 3, 2);
plot(V_app, I_raw * 1e3, 'k.', 'MarkerSize', 8, 'DisplayName', 'Measured (V_{app})'); hold on;
plot(V_eff, I_raw * 1e3, 'r-', 'LineWidth', 1.5, 'DisplayName', 'R_s Corrected (V_{eff})');
fill([Rs_lower_bound, Rs_upper_bound, Rs_upper_bound, Rs_lower_bound], ...
     [0, 0, max(I_raw)*1e3, max(I_raw)*1e3], 'y', 'FaceAlpha', 0.2);
xlabel('Voltage (V)'); ylabel('Current (mA)'); 
title(['Linear I-V: Ohm`s Law (R_s = ', num2str(Rs, '%.2f'), ' \Omega)']); grid on;
legend('Location', 'northwest');

% [Subplot 3] 추출된 양자 파라미터 
subplot(1, 3, 3);
yyaxis left; 
plot(V_eta, eta_0_meV, 'bo-', 'MarkerSize', 5, 'MarkerFaceColor', 'b', 'DisplayName', '\eta_0'); 
ylabel('\eta_{0,it} (meV)');

yyaxis right; 
plot(V_eta, tau_array_ps, 'rs--', 'MarkerSize', 5, 'MarkerFaceColor', 'r', 'DisplayName', '\tau'); 
ylabel('\tau_{it} (ps)');
xlabel('V_{eff} (V)'); title('Extracted Parameters'); grid on;
legend('Location', 'northwest');

%% 7. 터미널 로그 출력
fprintf('\n========================================================================\n');
fprintf(' [보고서] 단일 4H-SiC SBD 계면 산란 및 직렬 저항 추출 결과\n');
fprintf('------------------------------------------------------------------------\n');
fprintf(' 1. 동적 산출된 직렬 저항 (Rs)  : %.4f Ohm\n', Rs);
fprintf(' 2. Rs 산출 유효 윈도우 (V_app) : %.3f V ~ %.3f V\n', Rs_lower_bound, Rs_upper_bound);
fprintf(' 3. 수학적 볼츠만 한계선        : %.3f V\n', V_upper_Boltzmann);
fprintf(' 4. 최종 eta 산출 윈도우 (V_eff): %.3f V ~ %.3f V\n', V_eta(1), V_eta(end));
fprintf('    (시작: n < 1.3333 진입 지점 / 끝: 역전 직전 마지막 양수)\n');
fprintf('------------------------------------------------------------------------\n');
fprintf(' 5. 평균 계면 산란폭 (eta_0)    : %.10f meV\n', mean_eta_meV);
fprintf(' 6. 유효 계면 완화 시간 (tau)   : %.4f ps\n', effective_mean_tau_ps);
fprintf('========================================================================\n\n');
```