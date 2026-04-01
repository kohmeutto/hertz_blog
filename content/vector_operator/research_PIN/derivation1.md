+++
title = "Derivation1"
weight = 2
+++

---

### 다크 상태 (Dark State): 결함 포획 모델 및 SRH 재결합 분석

작성자: 김기범 / 일자: 2026.03.27

외부 빔이 없는 다크 상태의 역방향 및 저전압 순방향 전류는 i-layer 내부에 방사선 피폭으로 생성된 깊은 준위 결함(Deep-level trap)에 의한 공간 전하 재결합(Space-Charge Recombination)에 의해 지배된다.

---

### 1. SRH 재결합 수명 (Lifetime) 도출

외부 방사선(Proton irradiation)에 의해 반도체 벌크 내부에 격자 결함(Si 및 C Vacancies)이 생성되면, 연속적인 밴드갭 내부에 불연속적인 깊은 준위의 결함 상태(Deep-level trap states)가 형성된다. 자유 캐리어가 결함 준위 $E_t$ 근처에 접근하여 섭동(포획)이 발생할 시, 유효 해밀토니안은 다음과 같이 정의된다.

$$
H_{eff}(V) = E_{t,0} - e\phi(V) + \Sigma_t = E_{t,r}(V) - i\eta_0
$$

유효 해밀토니안을 시간 의존성 슈뢰딩거 방정식에 대입한다. 자유 캐리어가 결함 상태 $|\Psi(t)\rangle$ 에 노출되었을 때의 진화는 다음과 같다.

$$
i\hbar \frac{\partial}{\partial t} |\Psi(t)\rangle = \hat{H}_{eff} |\Psi(t)\rangle
$$

$$|\Psi(t)\rangle = \exp\left( -\frac{i E_{t,r} t}{\hbar} \right) \cdot \exp\left( -\frac{\eta_0 t}{\hbar} \right) |\Psi(0)\rangle
$$

입자가 결함에 포획되지 않고 생존해 있을 확률 $P(t)$는 절대값 제곱으로 정의되며, 결함의 포획률($\eta_0$)에 의해 지수함수적으로 감쇄(Decay)한.

$$
P(t) = |\langle \Psi(t) | \Psi(t) \rangle| = P(0) \exp\left( -\frac{2\eta_0 t}{\hbar} \right)
$$

거시적 SRH 재결합 수명 감쇄 법칙 $P(t) = P(0) e^{-t/\tau_{SRH}}$ 와 위 식을 직접 비교하면, 양자역학적 포획률 $\eta_0$와 거시적 SRH 재결합 수명 $\tau_{SRH}$ 사이의 관계가 증명된다.

$$
\tau_{SRH} = \frac{\hbar}{2\eta_0}
$$

---

### 2. 순방향 바이어스의 SRH 재결합

Sah-Noyce-Shockley 모델(ref: 10.1109/JRPROC.1957.278528) 에 수학적 원리가 잘 적용되어 있다.

**1) 일반적인 SRH 재결합률 방정식 (General SRH Rate)**

공핍층(Space Charge Region, $W$) 내부에서 발생하는 전자와 정공의 재결합은 밴드갭 내부에 존재하는 결함(Trap)을 매개로 일어난다. 이를 기술하는 원초적인 SRH 재결합률 $U$ (단위 시간, 단위 체적당 재결합하는 EHP의 수)는 다음과 같이 정의된다.

$$
U = \frac{p n - n_i^2}{\tau_p (n + n_1) + \tau_n (p + p_1)}
$$

- $n, p$: 비평형 상태에서의 국소적 전자 및 정공 농도
- $n_i$: 진성 캐리어 농도
- $\tau_n, \tau_p$: 전자와 정공의 포획 수명 (본 유도에서는 단순화를 위해 $\tau_n = \tau_p = \tau_{SRH}$ 로 둔다.)
- $n_1, p_1$: 결함 에너지 준위 $E_t$가 페르미 준위일 때의 캐리어 농도. (가장 재결합이 활발한 '깊은 준위(Deep level)' 결함, 즉 $E_t = E_i$ 인 상황을 가정하면 $n_1 = p_1 = n_i$ 가 된다.)

위 물리적 조건($\tau_n = \tau_p = \tau_{SRH}$, $n_1 = p_1 = n_i$)을 대입하여 지배 방정식을 정리한다.

$$
U = \frac{p n - n_i^2}{\tau_{SRH} (n + p + 2n_i)}
$$

결함이 밴드갭 정중앙 $E_i$에 위치하고 전자와 정공의 포획 단면적이 같다는 가정 적용되어 있다. 1957년 Sah, Noyce, Shockley가 비대칭성까지 모두 고려하여 적분을 수행해 본 결과, 최대 피크의 위치만 살짝 이동할 뿐 공핍층 전체를 적분한 총 전류량($J_{rec}$)의 스케일은 $\tau_{SRH} = \sqrt{\tau_n \tau_p}$ 라는 '유효 평균 수명'을 대입한 결과와 수학적으로 동일함을 증명해 냈다.즉, $\tau_n = \tau_p = \tau_{SRH}$ 로 두는 것은 식을 불필요하게 꼬지 않고 거시적 전류 스케일을 정확히 뽑아내기 위한 대수적 테크닉(Effective Parameterization)이다. 4H-SiC에 양성자(Proton)나 전자 빔(Electron beam)을 강하게 때리면, 격자가 깨지면서 특유의 방사선 유도 결함들이 생깁니다. 그중 가장 재결합을 지배하는 결함이 바로 탄소 빈자리(Carbon Vacancy, $V_C$)에 의해 형성되는 $\text{Z}_{1/2}$ 센터와 $\text{EH}_{6/7}$ 센터이다.4H-SiC의 밴드갭 $E_g \approx 3.26 \text{ eV}$. 따라서 정중앙 $E_i$는 약 $1.63 \text{ eV}$ 깊이에 있다.수많은 논문(DLTS 분석 등)에 따르면, 4H-SiC 방사선 조사 시 발생하는 가장 강력한 결함인 $\text{EH}_{6/7}$ 센터의 실제 에너지 위치는 전도대 아래 약 $1.5 \sim 1.6 \text{ eV}$ 이다. 4H-SiC가 방사선을 맞고 만들어내는 핵심 결함($\text{EH}_{6/7}$)의 위치가, 밴드갭 정중앙($1.63 \text{ eV}$)'의 위치와 거의 정확하게 일치한다.

**2) 열역학적 구동력: 준페르미 준위의 분리 (Quasi-Fermi Levels)**

순방향 전압 $V$가 인가되면, 시스템은 열평형을 잃고 전자의 준페르미 준위($F_n$)와 정공의 준페르미 준위($F_p$)로 쪼개진다. 공핍층 내부에서 두 준위의 에너지 차이는 외부에서 인가된 전압 $V$와 일치한다.

$$
F_n - F_p = qV
$$

볼츠만 통계에 의해 비평형 상태의 전자와 정공 농도는 각각 다음과 같이 정의된다.

$$
n = n_i \exp\left(\frac{F_n - E_i}{k_B T}\right), \quad p = n_i \exp\left(\frac{E_i - F_p}{k_B T}\right)
$$

이 두 농도를 곱($pn$)하면, 내부에 얽혀 있던 $E_i$ 항이 소거되면서 오직 인가전압 $V$에만 종속되는 보존 법칙이 나온다.

$$
p n = n_i^2 \exp\left(\frac{F_n - F_p}{k_B T}\right) = n_i^2 \exp\left(\frac{qV}{k_B T}\right)
$$

이제 이 $pn$의 곱을 앞서 정리한 SRH 방정식의 분자에 대입한다.

$$
U = \frac{n_i^2 \exp\left(\frac{qV}{k_B T}\right) - n_i^2}{\tau_{SRH} (n + p + 2n_i)}
$$

순방향 바이어스($V \gg k_B T/q$) 조건에서는 $\exp(qV/k_B T) \gg 1$ 이 성립하므로, 분자의 $-n_i^2$ 항은 무시할 수 있다.

$$
U \approx \frac{n_i^2 \exp\left(\frac{qV}{k_B T}\right)}{\tau_{SRH} (n + p + 2n_i)}
$$

**3) 산술-기하 평균에 의한 최대 재결합률 ($U_{max}$)의 증명**

위 수식에서 분자(전압에 의한 열역학적 구동력)는 공핍층 내부 어디서나 일정한 상수이다. 따라서 전체 재결합률 $U$가 최대값을 가지기 위해서는 분모인 $(n + p + 2n_i)$ 가 최소값을 가져야만 합한. 여기서 산술-기하 평균 부등식 (AM-GM Inequality)을 적용한다. $n$과 $p$는 모두 양수이므로 다음이 항상 성립한다.

$$
n + p \ge 2\sqrt{np}
$$

등호(최소값)가 성립할 조건은 오직 $n = p$ 일 때이다. 즉, 공핍층 내부에서 전자 농도와 정공 농도가 완벽하게 교차하여 같아지는 바로 그 지점($n=p$)에서 재결합이 가장 격렬하게(최대치로) 발생한다. 이 교차점($n=p$)에서의 농도를 하면, 앞서 $pn = n_i^2 \exp(qV/k_B T)$ 임을 증명했다. $n=p$ 이므로 $n^2 = p^2 = n_i^2 \exp(qV/k_B T)$ 가 된다. 양변에 루트를 씌운다.

$$
n = p = n_i \exp\left(\frac{qV}{2 k_B T}\right)
$$

여기서 처음으로 지수함수 분모에 숫자 2 가 나온다. 곱해서 전압 $V$를 만들어야 하는 두 농도가 완벽히 똑같아지려면, 각각이 전압의 절반($V/2$)씩을 나눠 가져야 하기 때문이다. 이제 이 조건($n=p$)을 분모에 대입하여 최대 재결합률 $U_{max}$를 얻는다.

$$
U_{max}
= \frac{n_i^2 \exp\left(\frac{qV}{k_B T}\right)}{\tau_{SRH} \left[ n_i \exp\left(\frac{qV}{2k_B T}\right) + n_i \exp\left(\frac{qV}{2k_B T}\right) + 2n_i \right]}
=\frac{n_i^2 \exp\left(\frac{qV}{k_B T}\right)}{\tau_{SRH} \left[ 2n_i \exp\left(\frac{qV}{2k_B T}\right) + 2n_i \right]}
$$

순방향 인가 상태이므로 $2n_i \exp(qV/2k_B T) \gg 2n_i$ 가 성립하여, 분모의 $+2n_i$ 상수항은 소거된다.

$$
U_{max}
\approx \frac{n_i^2 \exp\left(\frac{qV}{k_B T}\right)}{2\tau_{SRH} n_i \exp\left(\frac{qV}{2k_B T}\right)}
= \frac{n_i}{2\tau_{SRH}} \exp\left(\frac{qV}{2k_B T}\right)
$$

---

### 3. 역방향 바이어스의 SRH 재결합

역방향 바이어스($V < 0$)가 강하게 인가되어 $|V| \gg k_B T/q$ 인 상황을 가정한다.앞서 순방향에서 사용했던 열역학적 보존 법칙 $pn = n_i^2 \exp\left(\frac{qV}{k_B T}\right)$ 에 음수인 전압을 대입하면, 지수 함수 항은 수학적으로 $0$으로 수렴한다.

$$
\exp\left(-\frac{q|V|}{k_B T}\right) \approx 0 \implies pn \approx 0
$$

원래의 SRH 기본 방정식 분자에 이를 대입한다.

$$
\text{Numerator} = pn - n_i^2 \approx 0 - n_i^2 = -n_i^2
$$

분자의 지수항이 사라지고, $-n_i^2$ 이라는 물리 상수만 남게 된다.

역방향 바이어스의 물리적 의미는 "공핍층 내부의 캐리어(전자와 정공)를 양쪽 전극으로 완전히 이동시킨다는 것이다. 따라서 공핍층 내부의 국소적 캐리어 농도 $n$과 $p$는 진성 캐리어 농도 $n_i$보다도 훨씬 작아진다 ($n \ll n_i$, $p \ll n_i$). 이를 SRH 방정식의 분모에 대입한다.

$$
\text{Denominator} = \tau_{SRH} (n + p + 2n_i) \approx \tau_{SRH} (0 + 0 + 2n_i) = 2 \tau_{SRH} n_i
$$

분모 역시 복잡한 농도 변수($n, p$)가 모두 소거되고 상수로 변한다. 정리된 분자와 분모를 결합하여 역방향에서의 재결합률 $U$를 계산한다.

$$
U \approx \frac{-n_i^2}{2 \tau_{SRH} n_i} = -\frac{n_i}{2 \tau_{SRH}}
$$

여기서 도출된 음수($-$) 부호는 물리학적으로 다음의 의미를 지닌다. $U$는 원래 재결합률로 정의되었다. 그런데 값이 음수가 나왔다는 것은, 반대로 결함(Trap)을 매개로 전자-정공 쌍이 끊임없이 생성(Generation) 되고 있음을 의미한다. 이를 열적 생성률(Thermal Generation Rate, $G_{th}$) 이라 부르며, 부호를 반대로 취하여 양수로 정의한다.

$$
G_{th} = -U = \frac{n_i}{2 \tau_{SRH}}
$$

---

### 4. 공간 전하 재결합 전류 ($J_{rec}$)

전류 밀도 $J_{rec}$ 는 공핍층 폭 $W$ 내부에서 발생하는 모든 재결합률 $U(x)$에 전하량 $q$를 곱하여 공간에 대해 적분한 값이다.

$$
J_{rec} = q \int_{0}^{W} dx U(x) 
$$

$U(x)$는 $n=p$ 인 지점에서 가장 뾰족한 피크($U_{max}$)를 가지며, 양옆으로 급격히 감소하는 분포를 보인다. 1957년 Sah, Noyce, Shockley가 발표한 논문(Sah-Noyce-Shockley Approximation)에 따르면, 이 복잡한 적분을 완벽하게 푸는 대신  공핍층 폭 $W$ 전체에 걸쳐 최대 재결합률 $U_{max}$가 균일하게 일어난다고 가정하는 직사각형 근사(Rectangular Approximation) 를 도입해도 물리적 스케일이 매우 정확하게 일치함이 증명되었다. 즉, 적분식은 다음과 같이 컴팩트한 곱셈으로 치환된다.

$$
J_{rec} \approx q \cdot W \cdot U_{max}
$$

여기에 앞서 대수적으로 완벽히 증명한 $U_{max}$ 를 그대로 대입한다.

**1) 순방향 바이어스 ($V > 0$): 공간 전하 재결합 전류 ($J_{fwd}$)**

$$
J_{fwd}(V) = \frac{q n_i W(V)}{2 \tau_{SRH}} \exp\left(\frac{qV}{2k_B T}\right)
$$

**2) 역방향 바이어스 ($V < 0$): 공간 전하 재결합 전류 ($J_{rev}$)**

$$
J_{rev}(V) = \frac{q n_i W(V)}{2 \tau_{SRH}}
$$

---

### 5. 결함 포획률($\eta_0$)의 도출

4H-SiC는 와이드 밴드갭($E_g \approx 3.26\text{ eV}$) 특성상 극도로 낮은 진성 캐리어 농도($n_i \sim 10^{-9}\text{ cm}^{-3}$)를 가지며, 이로 인해 열역학적 확산 전류 성분($J_{diff} \propto n_i^2$)은 사실상 $0$으로 억제된다. 따라서 본 4H-SiC p-i-n 소자의 다크 상태 전류는 방사선 조사 여부와 무관하게 공핍층 내 깊은 준위 결함을 매개로 한 공간 전하 재결합/생성 전류($J_{rec/gen} \propto n_i$)에 의해 전적으로 지배된다. 본 모델은 이 물리 조건을 근거로 $J_{exp} \approx J_{rec/gen}$ 등가식을 사용하여 방사선 피폭에 따른 $\tau_{SRH}$ 붕괴를 정량적으로 계산한다. 방사선 조사 후 다크 전류가 증가했다는 것은, 위 식에 의해 양자역학적 결함 포획률($\eta_0$)이 증가했고 그에 따라 캐리어의 생존 수명($\tau_{SRH}$)이 짧아졌음을 의미한다.

**1) 순방향 닫힌 해 (Forward Closed-form)**

$$
\eta_0 = \left[ \frac{\hbar}{q n_i W(V)} \right] \cdot J_{exp, fwd}(V) \cdot \exp\left(-\frac{qV}{2k_B T}\right)
$$

**2) 역방향 닫힌 해 (Reverse Closed-form)**

$$
\eta_0 = \left[ \frac{\hbar}{q n_i W(V)} \right] \cdot J_{exp, rev}(V)
$$

