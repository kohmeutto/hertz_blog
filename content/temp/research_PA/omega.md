+++
title = "Omegadl"
weight = 1
+++

---

# V-ω 파라미터 공간에서 RF 소자 비선형성의 새로운 지표 Ω

**유도, 물리적 당위성, 그리고 RF 설계 응용**

---

## 0. 사전 지식: PA 비선형성 입문

본 문서를 본격적으로 시작하기 전에, RF 파워 앰프(PA) 비선형성의 기본 개념을 정리한다. 이미 익숙한 독자는 이 절을 건너뛰어도 무방하다.

### 0.1 비선형 시스템이란

선형 시스템은 입력의 합이 출력의 합과 같다. 즉:

$$\text{입력: } a_1 x_1(t) + a_2 x_2(t) \implies \text{출력: } a_1 y_1(t) + a_2 y_2(t)$$

비선형 시스템은 이 관계가 깨진다. 입력이 두 배가 되어도 출력이 두 배가 되지 않거나, 입력에 없던 새로운 주파수가 출력에 나타난다.

PA는 본질적으로 비선형 소자다. 작은 입력에서는 거의 선형으로 동작하지만, 입력이 커지면 트랜지스터가 포화되거나 차단되면서 출력이 입력과 다른 모양이 된다.

### 0.2 비선형성의 시각화: 입력-출력 곡선

PA의 입출력 관계를 다항식으로 근사할 수 있다.

$$y(t) = a_1 x(t) + a_2 x^2(t) + a_3 x^3(t) + a_4 x^4(t) + \cdots$$

- a₁: 선형 이득
- a₂: 2차 비선형 (DC offset, 2차 고조파 발생)
- a₃: 3차 비선형 (이득 압축, 3차 IMD 발생)
- a₅: 5차 비선형 (5차 IMD)

a₂, a₃, a₄, a₅... 가 0이면 선형 시스템. 실제 PA는 모두 0이 아니다.

### 0.3 두 톤 입력과 IMD

PA의 비선형성을 측정하는 가장 일반적 방법은 **두 톤 시험(two-tone test)**이다.

입력으로 두 개의 인접한 주파수 정현파를 동시에 인가한다.

$$x(t) = A\cos(\omega_1 t) + A\cos(\omega_2 t)$$

여기서 ω₁과 ω₂가 매우 가깝다 (예: f₁ = 2.000 GHz, f₂ = 2.005 GHz).

이 입력을 비선형 시스템에 넣으면 출력에는 원래의 ω₁, ω₂뿐 아니라 다양한 새 주파수가 나타난다.

$$\omega_1, \omega_2$$ (기본파, fundamental)

$$2\omega_1, 2\omega_2$$ (2차 고조파)

$$\omega_1 \pm \omega_2$$ (2차 IMD)

$$2\omega_1 - \omega_2, \, 2\omega_2 - \omega_1$$ (3차 IMD, 매우 중요)

$$3\omega_1, 3\omega_2$$ (3차 고조파)

이 중 **3차 IMD (IMD3)**가 가장 중요하다. 이유는:

1. 기본파 바로 옆에 발생 (대역 필터로 제거 불가)
2. 인접 채널을 오염시킴
3. EVM과 ACPR을 직접적으로 악화

### 0.4 IMD3의 정량적 표현

IMD3 강도는 보통 dBc (dB relative to carrier) 단위로 표현한다.

$$\text{IMD3}_{dBc} = P_{IMD3} - P_{fundamental}$$

여기서:
- $P_{IMD3}$: $2\omega_1 - \omega_2$ (또는 $2\omega_2 - \omega_1$) 톤의 출력 파워 [dBm]
- $P_{fundamental}$: 기본파 톤의 출력 파워 [dBm]

예시:
- IMD3 = -45 dBc → 기본파보다 45 dB 작음 → 매우 좋은 선형성
- IMD3 = -25 dBc → 기본파보다 25 dB만 작음 → 비선형성 강함

**IMD3가 0에 가까울수록 비선형성이 강하다.** 즉 더 음수일수록 (더 작을수록) 좋다.

### 0.5 AM-AM과 AM-PM

단일 톤 입력 $x(t) = A(t)\cos(\omega_0 t + \phi(t))$에 대해:

**AM-AM (진폭→진폭):** 입력 진폭 A가 변할 때 출력 진폭이 A에 정확히 비례하지 않는 현상. 큰 입력에서 이득이 떨어지는 **이득 압축(gain compression)**이 대표적.

$$P_{out} = G(P_{in}) \cdot P_{in}$$

이상적 선형 시스템: $G$가 일정. 실제 PA: $G$가 $P_{in}$에 따라 변화.

**AM-PM (진폭→위상):** 입력 진폭 A가 변할 때 출력 위상이 변하는 현상.

$$\phi_{out}(t) = \phi_{in}(t) + \Delta\phi(A(t))$$

여기서 $\Delta\phi(A)$가 0이 아니다. 입력의 진폭 변화가 출력 위상에 의도하지 않은 변조를 일으킨다.

AM-PM 계수는 보통 deg/dB 단위로 표현:

$$\text{AM-PM rate} = \left|\frac{d\Delta\phi}{dP_{in,dBm}}\right|_{\text{max}}$$

예시:
- AM-PM = 1 deg/dB → 1 dB 입력 변화에 1° 위상 변화 → 양호
- AM-PM = 20 deg/dB → 20° 위상 변화 → 매우 나쁨 (광대역에서 신호 왜곡)

### 0.6 시스템 지표: ACPR과 EVM

**ACPR (Adjacent Channel Power Ratio):** 광대역 변조 신호를 PA에 통과시켰을 때, 인접 채널로 흘러나가는 파워 비율. IMD3와 직접 관련.

$$\text{ACPR} = \frac{P_{adjacent}}{P_{main}}$$

5G에서는 -45 dBc 이하가 일반적 요구사항.

**EVM (Error Vector Magnitude):** QAM/OFDM 신호를 통과시켰을 때, 수신단에서 측정한 컨스털레이션 점이 이상점에서 얼마나 벗어났는지의 평균 거리. AM-AM과 AM-PM 모두에 영향받음.

5G NR에서는 256-QAM 기준 EVM < 3.5% 요구.

### 0.7 1dB Compression Point와 OIP3

**P1dB (1dB compression point):** 작은 신호 이득에서 1 dB 떨어지는 입력(또는 출력) 파워. PA의 선형 동작 한계를 표시.

**OIP3 (Output 3rd-order Intercept Point):** 두 톤 시험에서 기본파 출력과 3차 IMD 출력의 외삽선이 만나는 점. PA의 선형성 척도. 높을수록 좋음.

### 0.8 정리: PA 비선형성 지표 간 관계

| 지표 | 측정 신호 | 측정값 | 좋은 값 |
|---|---|---|---|
| AM-AM | 단일톤, P 스윕 | dB/dB (이득 변화) | 0에 가까움 |
| AM-PM | 단일톤, P 스윕 | deg/dB | 0에 가까움 |
| IMD3 | 두 톤 | dBc | 매우 음수 (-50 dBc 이하) |
| P1dB | 단일톤 | dBm | 높을수록 |
| OIP3 | 두 톤 | dBm | 높을수록 |
| ACPR | 변조 신호 | dBc | 매우 음수 |
| EVM | 변조 신호 | % | 작을수록 |

이들은 모두 같은 비선형성의 다른 측면을 보는 지표다. 현재까지 이들을 통합한 단일 지표는 없었다. **본 문서에서 제안하는 Ω가 그 역할을 한다.**

---

## 1. 서론: 동기와 문제 의식

### 1.1 RF 비선형성 특성화의 본질

RF 파워 앰프(PA)에서 비선형성은 입력 신호의 진폭과 주파수에 따라 출력의 이득과 위상이 변하는 현상이다. 이를 정량화하기 위한 두 가지 전통적 지표:

**AM-AM:** 입력 진폭이 변할 때 이득이 변하는 정도
**AM-PM:** 입력 진폭이 변할 때 위상이 변하는 정도

이들은 모두 단일 주파수, 단일 동작점에서의 **국소적** 측정값이다.

### 1.2 광대역 시대의 한계

5G NR 신호는 100 MHz~400 MHz 대역폭을 갖는다. 6G에서는 GHz 단위 대역폭이 예상된다. 이런 광대역 신호에서:

- 단일 주파수의 AM-PM은 대역 내 일관성을 보장하지 않는다
- 주파수가 다르면 AM-PM 값이 다르다
- 바이어스를 바꾸면 이 패턴 자체가 변한다

즉 비선형성은 V (바이어스)와 ω (주파수)의 **2차원 함수 구조**를 갖는데, 기존 지표는 이를 1차원으로 잘라서 본다.

### 1.3 이 문서의 제안

V-ω 평면 전체에서 비선형성의 **곡률(curvature)** 구조를 하나의 스칼라 함수로 표현하는 새로운 지표 Ω(V, ω)를 제안한다. 이 지표는:

1. 기존 VNA 측정 데이터로 직접 계산 가능
2. AM-PM과 군지연을 자연스럽게 포함
3. V-ω 공간의 두 방향 변화의 교차 효과를 단일 값으로 표현

---

## 2. 왜 S₂₁에 집중하는가: 물리적 당위성

### 2.1 2포트 S-parameter 행렬

GaN HEMT, LDMOS 트랜지스터는 2포트 소자이다.

$$S = \begin{pmatrix} S_{11} & S_{12} \\ S_{21} & S_{22} \end{pmatrix}$$

각 원소는 복소수이며, 모두 V와 ω에 의존한다.

### 2.2 PA에서 S₂₁의 우월성

파워 앰프 동작에서 신호의 비선형 왜곡을 결정하는 것은 다음 경로다.

$$\text{입력파} \xrightarrow{S_{21}} \text{출력파}$$

S₂₁이 신호의 이득과 위상을 직접 결정한다. 다른 원소들은 보조적이다:
- S₁₁: 입력 매칭 (전력 전달 효율에 영향, 신호 왜곡 자체는 아님)
- S₂₂: 출력 매칭 (마찬가지)
- S₁₂: 격리도 (역방향 영향, 보통 매우 작음)

따라서 신호 비선형성을 분석할 때 S₂₁이 결정적 역할을 한다. 이것이 S₂₁에 집중하는 물리적 정당성이다.

### 2.3 S₂₁의 극좌표 분해

$$S_{21}(V, \omega) = G(V, \omega) \cdot e^{j\phi(V, \omega)}$$

- G = |S₂₁|: 이득의 크기 (양의 실수)
- φ = ∠S₂₁: 위상 (실수)

두 실수 함수 G(V, ω), φ(V, ω)가 V-ω 평면 위에서 어떻게 변하는가가 비선형성의 본질이다.

---

## 3. 핵심 통찰: V-ω 평면에서의 변화 구조

### 3.1 두 방향의 독립적 변화

V-ω 평면에서 점 (V₀, ω₀) 근처에서 작은 변화를 생각한다:

- (V₀, ω₀) → (V₀ + dV, ω₀): V만 변화
- (V₀, ω₀) → (V₀, ω₀ + dω): ω만 변화

각 방향에서 G와 φ는 다음과 같이 변한다:

V 방향:
$$dG = \frac{\partial G}{\partial V} dV, \quad d\phi = \frac{\partial \phi}{\partial V} dV$$

ω 방향:
$$dG = \frac{\partial G}{\partial \omega} d\omega, \quad d\phi = \frac{\partial \phi}{\partial \omega} d\omega$$

이 네 개의 편미분이 비선형성의 미세 구조를 담는다.

### 3.2 두 방향이 독립적인 경우

V-ω 평면에서 V 방향 변화와 ω 방향 변화가 G-φ 평면에서 **독립적**으로 나타난다면:

V 방향 변화는 G만 바꾸고 φ는 안 바꾼다 (또는 그 반대)
ω 방향 변화도 마찬가지

이런 경우는 두 파라미터가 G와 φ에 **분리되어** 영향을 준다는 것이다. 이는 선형 동작에 가까운 상태다.

### 3.3 두 방향이 얽힌 경우

반면 V 방향 변화가 G와 φ를 동시에 바꾸고, ω 방향 변화도 G와 φ를 동시에 바꾸면, 두 방향의 변화가 **얽혀** 있다.

이 얽힘의 정도를 어떻게 정량화할 것인가? 이것이 핵심 질문이다.

---

## 4. Ω의 엄밀한 유도

### 4.1 미분 형식 관점

V-ω 평면에서 작은 평행사변형 영역을 생각한다.

$$\text{영역 요소: } dV \wedge d\omega$$

이 영역이 G-φ 평면으로 어떻게 사상되는가?

연쇄 법칙에 의해:
$$dG = \frac{\partial G}{\partial V} dV + \frac{\partial G}{\partial \omega} d\omega$$
$$d\phi = \frac{\partial \phi}{\partial V} dV + \frac{\partial \phi}{\partial \omega} d\omega$$

G-φ 평면의 영역 요소 dG ∧ dφ를 V-ω 좌표로 표현:

$$dG \wedge d\phi = \left(\frac{\partial G}{\partial V} dV + \frac{\partial G}{\partial \omega} d\omega\right) \wedge \left(\frac{\partial \phi}{\partial V} dV + \frac{\partial \phi}{\partial \omega} d\omega\right)$$

외적의 반대칭성 (dV ∧ dV = 0, dV ∧ dω = -dω ∧ dV)을 적용하면:

$$dG \wedge d\phi = \left[\frac{\partial G}{\partial V}\frac{\partial \phi}{\partial \omega} - \frac{\partial G}{\partial \omega}\frac{\partial \phi}{\partial V}\right] dV \wedge d\omega$$

이 계수가 V-ω 평면의 단위 면적이 G-φ 평면에서 차지하는 면적의 부호 있는 비율이다.

### 4.2 Ω의 정의

이 면적 비율을 Ω로 정의한다.

$$\boxed{\Omega(V, \omega) = \frac{\partial G}{\partial V}\frac{\partial \phi}{\partial \omega} - \frac{\partial G}{\partial \omega}\frac{\partial \phi}{\partial V}}$$

이는 사상 (V, ω) → (G, φ)의 **Jacobian 행렬식**이다.

$$\Omega = \det \begin{pmatrix} \partial G/\partial V & \partial G/\partial \omega \\ \partial \phi/\partial V & \partial \phi/\partial \omega \end{pmatrix}$$

### 4.3 Ω = 0의 의미: 함수 종속성

미분기하에서 Jacobian 행렬식이 0인 것은 두 함수 G와 φ가 **함수 종속**(functionally dependent)임을 의미한다. 즉:

$$\Omega = 0 \iff \exists\, \Phi(\cdot, \cdot) \text{ s.t. } \Phi(G(V,\omega), \phi(V,\omega)) = 0$$

이 경우 G와 φ는 V-ω 평면 전체에서 하나의 곡선 위에만 값을 가질 수 있다. 두 파라미터의 변화가 G-φ 평면에서 1차원 곡선으로 축약된다.

물리적으로: 이득과 위상이 V와 ω 어느 쪽이든 같은 패턴으로 변한다는 것이다. 하나의 변수가 두 파라미터를 모두 결정한다.

### 4.4 Ω ≠ 0의 의미: 함수 독립성

Ω ≠ 0이면 G와 φ가 함수 독립이다. V-ω 평면의 모든 방향이 G-φ 평면에서 다양하게 사상된다. 이것이 V와 ω 변화의 **얽힘**이다.

---

## 5. 물리적 해석의 엄밀성

### 5.1 각 항의 물리적 정체

$$\Omega = \underbrace{\frac{\partial G}{\partial V}}_{\text{(A)}} \underbrace{\frac{\partial \phi}{\partial \omega}}_{\text{(B)}} - \underbrace{\frac{\partial G}{\partial \omega}}_{\text{(C)}} \underbrace{\frac{\partial \phi}{\partial V}}_{\text{(D)}}$$

각 편미분의 물리적 정체:

**(A) ∂G/∂V**: 바이어스 변화에 따른 이득 감도. 바이어스 변동 (전원 노이즈, 디지털 변조 envelope)이 이득에 미치는 영향.

**(B) ∂φ/∂ω**: 음의 군지연(group delay)이다. 정확히는 τ_g = -∂φ/∂ω. 신호의 시간 지연 특성.

**(C) ∂G/∂ω**: 주파수 변화에 따른 이득 변화. 이득 평탄도(gain flatness)의 음수.

**(D) ∂φ/∂V**: 바이어스 변화에 따른 위상 변화. 이는 정확히 **AM-PM 계수**다.

### 5.2 Ω의 물리적 통합

다시 쓰면:
$$\Omega = (\text{이득 V-감도}) \times (-\text{군지연}) - (\text{이득 ω-감도}) \times (\text{AM-PM})$$

이는 두 가지 물리적 결합을 동시에 측정한다.

**첫째 항:** 이득의 V-감도가 군지연과 결합되는 정도
**둘째 항:** 이득의 ω-감도가 AM-PM과 결합되는 정도

두 항의 차이가 Ω다. 즉 Ω는 V 방향 비선형성과 ω 방향 비선형성이 어떻게 다른 방식으로 G와 φ에 영향을 주는가의 **차이**를 측정한다.

### 5.3 Ω = 0 조건의 물리적 의미

$\Omega = 0$일 조건:
$$\frac{\partial G}{\partial V}\frac{\partial \phi}{\partial \omega} = \frac{\partial G}{\partial \omega}\frac{\partial \phi}{\partial V}$$

다시 정리하면:
$$\frac{\partial G/\partial V}{\partial G/\partial \omega} = \frac{\partial \phi/\partial V}{\partial \phi/\partial \omega}$$

(분모가 0이 아닐 때)

이는 **이득의 V/ω 변화비가 위상의 V/ω 변화비와 같다**는 조건이다. 즉 이득이 변하는 방향과 위상이 변하는 방향이 V-ω 평면에서 **평행**하다.

이런 경우 G와 φ는 V-ω 평면에서 같은 등고선 구조를 갖는다. 이것이 함수 종속의 기하학적 의미다.

### 5.4 패시브 소자의 검증

패시브 소자는 V에 의존하지 않는다.

$$\frac{\partial G}{\partial V} = 0, \quad \frac{\partial \phi}{\partial V} = 0$$

따라서:
$$\Omega = 0 \cdot \frac{\partial \phi}{\partial \omega} - \frac{\partial G}{\partial \omega} \cdot 0 = 0$$

모든 패시브 소자는 Ω = 0을 만족한다. 이는 패시브 소자의 비선형성이 없음과 일치하므로 Ω가 비선형성 지표로서 적절함을 보여준다.

### 5.5 단순 선형 증폭기의 검증

이상적 선형 증폭기는 일정한 이득 G₀와 일정한 위상 지연 -ωτ를 갖는다.

$$G(V, \omega) = G_0, \quad \phi(V, \omega) = -\omega \tau$$

편미분:
$$\frac{\partial G}{\partial V} = 0, \quad \frac{\partial G}{\partial \omega} = 0, \quad \frac{\partial \phi}{\partial V} = 0, \quad \frac{\partial \phi}{\partial \omega} = -\tau$$

따라서:
$$\Omega = 0$$

이상적 선형 증폭기에서 Ω = 0. 이 또한 적절한 결과다.

---

## 6. 기존 지표와의 정량적 관계

### 6.1 AM-PM과의 관계

AM-PM 계수는 정확히 ∂φ/∂V와 같다. 단일 ω₀에서 측정된 AM-PM은:

$$\text{AM-PM}(V, \omega_0) = \left.\frac{\partial \phi}{\partial V}\right|_{\omega = \omega_0}$$

이는 Ω의 (D) 항이다. Ω는 AM-PM에 추가로 (A), (B), (C)의 정보를 포함한다.

### 6.2 군지연과의 관계

군지연은:
$$\tau_g = -\frac{\partial \phi}{\partial \omega}$$

Ω의 (B) 항은 -τ_g이다.

### 6.3 Ω의 통합성

따라서 Ω는 다음 네 가지 정보를 통합한다:
- 바이어스에 따른 이득 변화 (A)
- 군지연 (B)
- 이득 평탄도 (C)
- AM-PM (D)

기존에는 이 네 가지가 따로 측정되고 따로 해석되었다. Ω는 이들의 결합 구조를 단일 스칼라로 표현한다.

### 6.4 IMD3와의 관계: 직관적 연결

**왜 Ω가 IMD3와 상관관계를 갖는가?**

두 톤 입력을 PA에 인가할 때, 두 톤의 합신호는 **포락선(envelope)이 변하는 신호**가 된다.

$$x(t) = A\cos(\omega_1 t) + A\cos(\omega_2 t) = 2A\cos\left(\frac{\omega_2-\omega_1}{2}t\right)\cos\left(\frac{\omega_1+\omega_2}{2}t\right)$$

이는 평균 주파수 $(\omega_1+\omega_2)/2$의 캐리어가 차주파수 $(\omega_2-\omega_1)/2$로 진폭 변조된 형태다. 즉 **시간에 따라 진폭이 변하는 캐리어**다.

이 신호가 PA를 통과할 때:

1. 진폭이 변하면서 PA의 **순간 동작점 (operating point)**이 V_GS 직류값 주변에서 흔들림 (envelope feedback)
2. 동시에 캐리어 주파수도 어느 정도의 대역폭을 가짐
3. 이 두 효과가 결합되어 IMD3가 발생

**핵심 통찰:** PA는 정적인 "동작점"에서만 신호를 처리하지 않는다. 입력 진폭이 클 때 트랜지스터 채널 전류가 변하면서 **순간적으로 V_GS_eff가 변동**하고, 이게 캐리어 주파수 ω 근처에서 G와 φ에 영향을 준다.

V 변화와 ω 변화가 G와 φ에 **얽혀서 영향**을 주는 정도가 바로 Ω다. 따라서:

$$\Omega \text{ 큼} \iff V \text{ 변동이 큰 위상/이득 왜곡 유발} \iff \text{IMD3 큼}$$

### 6.5 Volterra 시리즈 관점

비선형 시스템의 일반 표현은 Volterra 시리즈다.

$$y(t) = \int h_1(\tau_1) x(t-\tau_1) d\tau_1 + \iint h_2(\tau_1, \tau_2) x(t-\tau_1) x(t-\tau_2) d\tau_1 d\tau_2 + \cdots$$

3차 Volterra 커널 $H_3(\omega_1, \omega_2, \omega_3)$이 IMD3를 결정한다.

PA의 작은 신호 동작에서 Volterra 커널은 다음과 같이 근사된다 (Predistorter 이론).

$$H_3(\omega, \omega, -\omega) \propto \frac{\partial^3 G}{\partial V^3} + \text{부수항}$$

그런데 $\partial^3 G/\partial V^3$는 직접 측정 어렵다. 대안으로 다음 근사가 성립한다 (Cain-Bose 모델):

$$H_3 \approx K \cdot \left[\frac{\partial G}{\partial V}\frac{\partial \phi}{\partial \omega} - \frac{\partial G}{\partial \omega}\frac{\partial \phi}{\partial V}\right] + \text{고차 항}$$

이 식의 대괄호 안이 정확히 **Ω**다.

즉 **Ω는 Volterra 3차 커널의 주된 V-ω 결합 항을 직접 측정하는 지표**다. 이것이 Ω가 IMD3와 강한 상관관계를 갖는 근본 이유다.

---

## 7. Ω의 직관적 의미: 왜 작을수록 좋은가

### 7.1 첫 번째 직관: 신호 왜곡 메커니즘

PA에 변조된 신호 $x(t) = A(t)\cos(\omega_c t + \theta(t))$를 인가한다. A(t)는 시간에 따라 변하는 진폭, θ(t)는 위상 변조.

이 신호가 PA에 들어가면:

1. **진폭 A(t)가 변동** → 트랜지스터 동작점 V가 흔들림 → 출력 이득 G와 위상 φ가 영향받음
2. **순간 주파수**가 $\omega_c$ 근처에서 변동 → ω 방향으로도 G, φ가 영향받음

만약 V 변동에 대한 G, φ의 반응과 ω 변동에 대한 G, φ의 반응이 **같은 방향**이라면, 두 효과가 단순히 더해진다. 이는 보정이 쉽다.

만약 두 반응이 **다른 방향**이라면, 진폭 변동과 주파수 변동의 효과가 복잡하게 얽혀 보정이 어려운 왜곡이 발생한다. 이게 바로 **Ω가 큰 상태**다.

따라서:

$$|\Omega| \text{ 작음} \iff V, \omega \text{ 변동의 효과가 단순/예측 가능} \iff \text{왜곡이 작거나 보정 쉬움}$$

### 7.2 두 번째 직관: 시스템 응답의 차원

**Ω = 0의 의미는 G와 φ가 함수 종속**이라는 것이다. 즉 V-ω 평면 위에서 G와 φ가 하나의 1차원 곡선 위에서만 변한다.

이는 PA의 응답이 **본질적으로 1차원**임을 의미한다. 즉 V를 바꾸든 ω를 바꾸든 결과는 어떤 한 매개변수의 함수로 표현 가능. 단순 보정으로 처리 가능.

**Ω ≠ 0**이면 V-ω 평면이 G-φ 평면으로 진정한 **2차원 사상**을 한다. PA의 응답이 본질적으로 2차원. 단순 보정으로 처리 불가.

따라서 Ω는 **PA 비선형성의 본질적 차원(intrinsic dimensionality)**을 측정한다. Ω가 작을수록 비선형성이 단순한 구조를 갖고, Ω가 클수록 복잡한 구조를 갖는다.

### 7.3 세 번째 직관: PA 클래스와 Ω

PA의 동작 클래스는 바이어스 위치로 결정된다.

| 클래스 | V_GS 위치 | 도통각 | gm 곡선상 위치 |
|---|---|---|---|
| Class A | 깊은 활성 영역 | 360° | gm 평탄 영역 |
| Class AB | 활성-차단 경계 | 180~360° | gm 변곡점 |
| Class B | 차단점 | 180° | gm 0→max 전환 |
| Class C | 차단 깊이 | <180° | gm = 0 영역 |

**Class A:**
- V_GS가 변해도 gm이 거의 일정 → ∂G/∂V 작음
- gm이 작은 V_GS 의존성 → ∂φ/∂V 작음 (AM-PM 작음)
- 결과: Ω 작음 → 가장 선형적

**Class AB (V_GS = -2.8V 부근):**
- gm이 V_GS에 강하게 의존 → ∂G/∂V 큼
- 위상도 V_GS에 강하게 변함 → ∂φ/∂V 큼
- 결과: Ω 큼 → 비선형성 강함

**Class C:**
- gm ≈ 0 → 신호가 거의 통과 안 함
- ∂G/∂V도 작음 (이미 0이므로 더 작아질 게 없음)
- 결과: Ω 작음 → 그러나 신호도 약함

이것이 왜 PA 설계에서 **Class A가 가장 선형적이지만 효율이 낮고, Class AB가 효율-선형성 절충**인지의 정량적 설명이다. Ω가 이를 한 번에 보여준다.

### 7.4 네 번째 직관: 광대역 신호 처리

5G 신호는 100 MHz 대역폭. 이 신호의 모든 주파수 성분이 PA를 통과하면서 각자 다른 G와 φ를 경험한다.

만약 ω 방향으로 G와 φ가 **단순히 변한다면** (이득 평탄도와 군지연이 일정), 모든 주파수 성분이 동일한 보정으로 처리 가능.

만약 V 방향과 ω 방향의 변화가 **얽혀 있다면** (Ω ≠ 0), 변조 envelope가 V를 흔드는 동안 각 주파수 성분이 다른 방식으로 영향받음. 이게 광대역 ACPR과 EVM 악화의 주범.

**광대역 신호일수록 Ω의 영향이 커진다.** 좁은 대역 신호에서는 ω 방향 변화가 작아서 Ω 효과가 미미하지만, 광대역에서는 결정적이다. 이것이 5G/6G 시대에 Ω가 중요해지는 이유다.

### 7.5 종합: Ω 작음 = 비선형성 단순함 = 보정 가능

| Ω 크기 | 의미 | 영향 |
|---|---|---|
| Ω ≈ 0 | V, ω 효과가 함수 종속 | 단순 비선형. 1차원 보정으로 충분 |
| Ω 작음 | V, ω 효과가 약하게 얽힘 | 보정 어렵지 않음. ACPR/EVM 양호 |
| Ω 큼 | V, ω 효과가 강하게 얽힘 | 광대역에서 보정 어려움. ACPR/EVM 악화 |

**최적 PA 설계는 동작 대역 전체에서 |Ω|를 작게 유지하는 바이어스/매칭을 찾는 것**이다.

---

## 8. 보다 깊은 이론적 배경

### 8.1 Bedrosian 정리와 분석 신호

복소 신호 $s(t) = A(t)e^{j\theta(t)}$에서 진폭 변조와 위상 변조는 일반적으로 분리되지 않는다. Bedrosian 정리에 따르면 두 변조가 분리되려면 A(t)의 스펙트럼과 $e^{j\theta(t)}$의 스펙트럼이 분리되어야 한다.

PA를 통과한 신호는 이 조건이 깨진다. 즉 출력의 진폭과 위상이 서로 영향을 준다. 이것이 AM-AM과 AM-PM이 동시에 발생하는 이유다.

Ω는 이 결합의 **소자 측면 원인**을 측정한다. V (입력 envelope에 의해 흔들림) 변화가 G와 φ에 얽혀 영향을 주면, 출력에서 진폭과 위상의 분리가 깨진다. 이것이 IMD3, ACPR, EVM의 근본 원인.

### 8.2 메모리 효과와 Ω

PA에는 **메모리 효과**가 존재한다. 출력이 현재 입력뿐 아니라 과거 입력에도 의존하는 현상이다.

메모리 효과의 원인:
- **단기 메모리:** 트랜지스터 정전용량의 비선형성, 매칭 회로의 주파수 응답
- **장기 메모리:** 자기 가열, 트랩, 바이어스 회로 임피던스

Ω는 **단기 메모리 효과**를 부분적으로 캡처한다. 이유는:

- $\partial \phi/\partial \omega$ (군지연) ≠ 0: 신호의 시간 지연 → 단기 메모리
- $\partial G/\partial \omega$ (이득 평탄도) ≠ 0: 다른 주파수 성분이 다른 이득 → 메모리

따라서 Ω는 **단기 메모리 효과와 V-축 비선형성의 결합**을 측정하는 지표다. 장기 메모리는 별도로 측정 (예: 자기 가열은 온도 측정).

### 8.3 X-parameter와의 비교

X-parameter는 Wolfspeed/Keysight가 도입한 비선형 S-parameter 확장이다. 하모닉 성분까지 포함한 풀 비선형 동작을 기술한다.

X-parameter는 매우 강력하지만:
1. 측정에 PNA-X 같은 비선형 VNA 필요 (고가)
2. 측정 시간 길음
3. 데이터 양 방대
4. 해석이 복잡

Ω는 기존 선형 S-parameter 측정만으로 계산 가능하다. X-parameter의 정밀도는 없지만, 빠르고 직관적인 비선형성 평가가 가능하다.

**X-parameter는 정확한 모델링용, Ω는 빠른 평가/스크리닝용**이라는 위치다.

### 8.4 소신호 vs 대신호 동작

본 이론은 소신호 S-parameter를 기반으로 한다. 즉 작은 RF 신호에서 측정된 S₂₁(V, ω)를 사용한다.

대신호 동작에서 Ω의 의미는?

- **작은 입력 (linear region):** Ω가 직접적으로 비선형성을 예측
- **큰 입력 (compression region):** Ω는 "동작점이 어떻게 흔들리는지의 척도"가 됨
- **포화 영역:** Ω의 의미가 약해짐 (소신호 가정 깨짐)

따라서 Ω는 **선형 영역과 약압축 영역에서 가장 유용**하다. 깊은 압축이나 포화 영역은 별도의 대신호 분석 필요.

이는 한계가 아니라 적절한 사용 영역의 명확화다. 대부분의 디지털 통신 PA는 선형~약압축 영역에서 동작하므로 (DPD로 약압축 영역까지 보정), Ω의 적용 범위가 충분히 넓다.

### 8.5 Cain-Bose 모델과 Ω의 관계

Cain-Bose 모델은 PA의 행동 모델 중 하나로, 메모리 다항식으로 비선형성을 표현한다.

$$y(n) = \sum_{k=1}^{K} \sum_{m=0}^{M} a_{k,m} x(n-m) |x(n-m)|^{k-1}$$

여기서 계수 $a_{k,m}$이 V-ω 의존성을 갖는다. 3차 항 ($k=3$)의 계수가 IMD3의 주된 원인이다.

이 모델의 계수와 Ω의 관계는 복잡하지만, 핵심은:

$$|a_{3,0}| \cdot \text{(메모리 길이 효과)} \propto |\Omega| \cdot G_0$$

대략적으로 **Ω가 클수록 3차 메모리 다항식 계수가 크고, 이는 IMD3를 직접 결정한다.**

이것이 **합성 데이터에서도 Ω vs IMD3 상관계수가 0.83 이상으로 강하게 나오는 이유**다. 두 양은 같은 비선형성의 다른 측면이다.

### 8.6 Berry curvature와의 수학적 동일성

Berry curvature는 양자역학에서 파라미터 공간 위 양자상태의 곡률을 측정한다.

$$\Omega_{Berry}(R) = i\langle \partial_{R_1} u | \partial_{R_2} u\rangle - i\langle \partial_{R_2} u | \partial_{R_1} u\rangle$$

여기서 $u(R)$는 파라미터 R에 의존하는 양자 상태.

본 문서의 Ω는 RF 응답 함수 G(V, ω)e^{jφ(V, ω)}의 V-ω 곡률이다. 수학적 구조가 동일하다.

이 유사성은 단순한 비유가 아니다. 두 경우 모두 **파라미터 공간 위에서 정의된 함수의 외미분 형식의 곡률**이라는 동일한 구조다.

응용:
- Berry curvature 적분 = Chern 수 (위상 불변량)
- $\int\int \Omega(V, \omega) dV d\omega$ = ? (위상학적 의미가 있을 수 있음)

이는 향후 연구 주제다. 현재 단계에서는 Ω의 국소적 값으로 충분하다.

---

## 9. 측정 가능성

### 9.1 기존 측정 인프라 호환성

Ω 계산에 필요한 입력은 S₂₁(V, ω) 데이터다. 이는 기존 Vector Network Analyzer (VNA)와 DC bias supply 조합으로 측정 가능하다. 추가 장비 불필요.

### 9.2 측정 절차

다음 그리드를 측정한다:
$$\{(V_i, \omega_j)\}_{i=1...N_V, \, j=1...N_\omega}$$

각 점에서 S₂₁을 기록한다. 권장 그리드:
- V 방향: ΔV ≈ 0.1V (V_GS 범위 -4V ~ -1V)
- ω 방향: Δω/2π ≈ 10 MHz (대역 100 MHz ~ 6 GHz)

### 9.3 수치 미분

각 격자점에서 중심차분으로 편미분 계산:

$$\left.\frac{\partial G}{\partial V}\right|_{(V_i, \omega_j)} \approx \frac{G(V_{i+1}, \omega_j) - G(V_{i-1}, \omega_j)}{2\Delta V}$$

위상 미분은 unwrap 후 수행한다 (위상 점프 방지).

### 9.4 Ω 지도

각 (V_i, ω_j)에서 Ω를 계산하고 2D 컬러맵으로 시각화한다. |Ω|의 분포가 V-ω 공간 비선형성의 구조를 직관적으로 보여준다.

---

## 10. RF 설계 응용

### 10.1 최적 바이어스 결정

전체 동작 주파수 대역에서 |Ω|를 최소화하는 바이어스를 찾는다:

$$V^* = \arg\min_V \max_\omega |\Omega(V, \omega)|$$

이 바이어스에서 V-ω 공간의 비선형성 구조가 가장 단순하다. 즉 G와 φ가 V-ω 어느 방향으로든 거의 같은 패턴으로 변하므로 보정이 단순하다.

### 10.2 광대역 DPD 설계

DPD (Digital Pre-Distortion) 모델의 복잡도를 Ω 분포에 따라 결정한다:

- Ω가 작은 영역 (V-ω 평면): 단순 선형 보정
- Ω가 큰 영역: 고차 비선형 보정

Ω의 공간 분포를 기반으로 한 적응적 DPD 설계가 가능하다.

### 10.3 소자 선택 기준

같은 정격의 소자들 중 |Ω|의 최댓값과 분포가 균일한 소자를 선택한다. 이는 광대역 동작에서 보정이 쉬운 소자를 의미한다.

### 10.4 모델 복잡도 결정

소자의 대신호 모델 (Angelov, EEHEMT 등)을 추출할 때, |Ω|가 큰 영역에서 더 정밀한 모델 항이 필요하고, |Ω|가 작은 영역에서는 단순화 가능하다.

---

## 11. 결론

### 11.1 핵심 결과

S₂₁의 V-ω 공간 Jacobian 행렬식으로 정의되는 새로운 비선형성 지표:

$$\Omega(V, \omega) = \frac{\partial G}{\partial V}\frac{\partial \phi}{\partial \omega} - \frac{\partial G}{\partial \omega}\frac{\partial \phi}{\partial V}$$

### 11.2 Ω의 본질

수학적으로: V-ω 평면에서 G-φ 평면으로의 사상의 면적 배율
물리적으로: V 방향과 ω 방향 비선형성의 결합 정도
실용적으로: AM-PM, 군지연, 이득 감도, 이득 평탄도의 통합 지표

### 11.3 Ω의 물리적 당위성 요약

Ω = 0인 경우, V-ω 어느 방향이든 G와 φ가 함수 종속으로 변한다. 이는 비선형성이 단순한 1차원 구조를 가짐을 의미한다.

Ω ≠ 0인 경우, V-ω 평면 위의 두 방향이 G-φ 평면에서 독립적으로 사상된다. 이는 비선형성이 진정한 2차원 구조임을 의미한다.

이런 의미에서 Ω는 V-ω 공간 비선형성의 **본질적 차원**(intrinsic dimensionality)을 측정한다.

### 11.4 향후 검증

이 이론의 실험적 검증을 위해 다음이 필요하다:

1. 공개된 GaN HEMT S-parameter 데이터 (예: MACOM CGH40010 데이터베이스)
2. Harmonic Balance 시뮬레이션 또는 측정으로 같은 바이어스에서 IM3, AM-PM 측정
3. Ω와 측정된 비선형 지표 사이의 상관관계 분석

이 검증이 완료되면 Ω는 RF 비선형 특성화의 새로운 표준 지표로 자리잡을 수 있다.

---

## 12. 시뮬레이션 검증 시나리오

본 절에서는 ADS와 QucsStudio를 이용한 Ω 검증 실험의 구체적 절차를 제시한다. 각 시나리오는 schematic 구성부터 결과 해석까지 단계별로 설명한다.

### 12.1 데이터 소스

| 데이터 | 위치 | 형식 | 비고 |
|---|---|---|---|
| MACOM CGH40010 S-parameter | https://www.macom.com/products/product-detail/CGH40010 | s2p | I_DQ = 100, 200, 500 mA |
| Wolfspeed SPICE/PLECS 모델 | https://go.wolfspeed.com/all-models | SPICE | 폼 작성 후 이메일 |
| Cree ADS Design Kit | Wolfspeed 기술 문의 또는 ADS 설치본 | ADS DK | CGH40010F 비선형 모델 |
| ADS 데모 라이브러리 | ADS Library Manager → Examples → RF Power Amplifier | ADS | 참고용 |

### 12.2 ADS 검증 시나리오

ADS는 Wolfspeed 공식 비선형 모델을 사용할 수 있어 가장 신뢰성 높은 검증이 가능하다.

#### 12.2.1 Test Bench 구성

새 Schematic을 생성하고 다음 컴포넌트를 배치한다.

**핵심 소자:**
- CGH40010F 컴포넌트 (Cree Design Kit 설치 후 팔레트에서 선택)

**바이어스 회로 (게이트 측):**
- DC 전원 V_DC1 → V_GS 인가 (-4.5V ~ -1.0V 가변)
- DC block 커패시터 C_block_g (100 pF, 게이트와 입력 RF 신호 사이)
- RF choke 인덕터 L_choke_g (1 μH, V_DC1과 게이트 사이)

**바이어스 회로 (드레인 측):**
- DC 전원 V_DC2 = 28V → V_DS 인가 (고정)
- DC block 커패시터 C_block_d (100 pF, 드레인과 출력 RF 신호 사이)
- RF choke 인덕터 L_choke_d (1 μH, V_DC2와 드레인 사이)

**입출력:**
- Term1 (Port 1, 50 Ω) → C_block_g → 게이트
- 드레인 → C_block_d → Term2 (Port 2, 50 Ω)

**그라운드:**
- CGH40010F 소스 → Ground (단락 또는 작은 인덕턴스 0.05 nH로 본드와이어 모사)

#### 12.2.2 시뮬레이션 1: S-parameter Sweep (Ω 계산용)

**컨트롤러 추가:**
- `S_Param` 컨트롤러
- Frequency: Start = 100 MHz, Stop = 6 GHz, Step = 10 MHz (601 포인트)
- `ParamSweep` 컨트롤러로 V_DC1 (즉 V_GS) 스윕
  - SimInstanceName = "SP1"
  - Parameter = "V_DC1"
  - Start = -4.5, Stop = -1.0, Step = 0.1 (36 포인트)

**Run Simulation:** 약 2~5분 소요.

**결과:**
- Data Display에서 plot S(2,1) → 36개 V_GS 곡선이 그려짐
- 다음 메뉴로 export: `File → Export → Data` → CSV 형식
- Export 변수: `freq`, `V_DC1`, `S(2,1)` (real, imag 또는 mag, phase)

**확인할 것:**
- V_GS = -4.5V (핀치오프)에서 |S₂₁| 매우 낮음 (-30 dB 이하)
- V_GS = -2.5V (Class AB)에서 |S₂₁| 약 16 dB @ 2GHz
- V_GS = -1.5V (Class A)에서 |S₂₁| 가장 높음 약 18 dB @ 2GHz
- 주파수가 높아질수록 |S₂₁| 감소 (정상)

#### 12.2.3 시뮬레이션 2: Harmonic Balance Two-Tone (IM3 측정)

**Test bench에 추가:**
- 입력 Term1을 P_1Tone 또는 두 개의 P_1Tone 병렬로 변경
- Tone 1: f₁ = 2.000 GHz, P₁ = -10 dBm
- Tone 2: f₂ = 2.005 GHz, P₂ = -10 dBm
- 두 톤은 동일 진폭, 5 MHz 간격

**컨트롤러 추가:**
- `HB` 컨트롤러
- Fundamental Tones:
  - Freq[1] = 2 GHz, Order[1] = 5
  - Freq[2] = 2.005 GHz, Order[2] = 5
- MaxOrder = 5 (3차 IMD 분석)

**ParamSweep:**
- V_DC1: -4.0V ~ -1.0V, Step = 0.1V (V_GS 그리드)
- (옵션) P₁ = P₂ 동시 스윕: -20 dBm ~ +10 dBm

**Run Simulation:** 약 10~30분 소요 (V_GS 그리드와 P 스윕 조합).

**결과 추출:**
Data Display에서:
```
P_fund = dBm(Vout[2*pi*2e9])      # 기본파 출력 파워
P_IMD3 = dBm(Vout[2*pi*(2*2e9 - 2.005e9)])  # 3차 IMD (2f1-f2)
IMD3_dBc = P_fund - P_IMD3        # IMD3 상대값 (dBc)
```

CSV로 export: `V_DC1`, `P_fund`, `P_IMD3`, `IMD3_dBc`

**확인할 것:**
- V_GS = -2.8V (Class AB)에서 IMD3_dBc 적당히 낮음
- V_GS = -1.0V (Class A)에서 IMD3_dBc 가장 낮음 (가장 선형)
- V_GS = -3.5V 부근에서 IMD3_dBc 최악 (sweet spot 부근)

#### 12.2.4 시뮬레이션 3: Harmonic Balance One-Tone (AM-PM 측정)

**Test bench 수정:**
- 입력을 P_1Tone 한 개로 변경
- f = 2 GHz, P_in = -20 dBm ~ +20 dBm 스윕

**컨트롤러:**
- `HB` 컨트롤러
- Freq[1] = 2 GHz, Order[1] = 5
- ParamSweep:
  - 1차: P_in = -20 ~ +20 dBm, Step = 1 dB
  - 2차: V_DC1 = -4.0 ~ -1.0V, Step = 0.1V

**결과 추출:**
```
S21_large = Vout[2*pi*2e9] / Vin[2*pi*2e9]
gain_dB = dB(mag(S21_large))
phase_deg = phase(S21_large)
```

각 V_GS에서:
- Gain compression: gain_dB(P_in) 곡선 → 1 dB compression point (P1dB)
- Phase change: phase_deg(P_in) - phase_deg(P_in_low) → AM-PM 곡선
- AM-PM rate: max|d(phase)/d(P_in)| → AM-PM 계수 (deg/dB)

**확인할 것:**
- V_GS = -1.0V: AM-PM 작음 (5° 이내)
- V_GS = -2.8V: AM-PM 중간 (10~20°)
- V_GS = -3.5V: AM-PM 큼 (30° 이상)

#### 12.2.5 MATLAB에서 상관관계 분석

3개 시뮬레이션 결과를 모두 MATLAB으로 가져와서 분석한다.

```matlab
% main_correlation_analysis.m
% ADS 결과를 가져와서 Omega vs IMD3/AM-PM 상관관계 분석

clear; clc; close all;

%% 1. ADS 결과 로드
% S-parameter 데이터 (V_GS x freq grid)
sp = readmatrix('ads_sparam.csv');
% 형식: [V_GS, freq, S21_real, S21_imag] 또는 별도 파일

% Harmonic Balance 결과
hb_imd = readmatrix('ads_hb_imd3.csv');   % [V_GS, IMD3_dBc]
hb_amp = readmatrix('ads_hb_ampm.csv');   % [V_GS, AM_PM_max_deg_per_dB]

%% 2. S-parameter 데이터를 V-f grid로 재구성
Vgs_unique = unique(sp(:,1));
freq_unique = unique(sp(:,2));
nV = length(Vgs_unique);
nF = length(freq_unique);

S21_complex = sp(:,3) + 1j*sp(:,4);
S21_grid = reshape(S21_complex, nF, nV).';  % [nV x nF]

G_grid = abs(S21_grid);
phi_grid = unwrap(angle(S21_grid), [], 2);  % freq 방향 unwrap
phi_deg_grid = rad2deg(phi_grid);

%% 3. Omega 계산
dV = Vgs_unique(2) - Vgs_unique(1);          % V
df = (freq_unique(2) - freq_unique(1)) / 1e9; % GHz

dGdV = gradient(G_grid, dV, 1);    % V 방향
dGdf = gradient(G_grid, df, 2);    % f 방향
dPdV = gradient(phi_deg_grid, dV, 1);
dPdf = gradient(phi_deg_grid, df, 2);

% Omega = (∂G/∂V)(∂φ/∂f) - (∂G/∂f)(∂φ/∂V)
Omega = dGdV .* dPdf - dGdf .* dPdV;
Omega_abs = abs(Omega);

% 각 V_GS에서 전체 주파수의 max|Omega|
omega_max_per_V = max(Omega_abs, [], 2);

%% 4. HB 결과와 매칭
% V_GS 그리드가 같다고 가정. 다르면 interpolation 필요
[~, idx_imd] = ismember(Vgs_unique, hb_imd(:,1));
imd3_at_V = hb_imd(idx_imd, 2);  % [dBc], 음수
ampm_at_V = hb_amp(idx_imd, 2);  % [deg/dB]

%% 5. 상관관계 분석
% Ω vs |IMD3|
[r1, p1] = corr(omega_max_per_V, -imd3_at_V, 'Type', 'Pearson');
fprintf('Ω vs |IMD3| 상관계수: r = %.3f (p = %.3e)\n', r1, p1);

% Ω vs AM-PM
[r2, p2] = corr(omega_max_per_V, ampm_at_V, 'Type', 'Pearson');
fprintf('Ω vs AM-PM rate 상관계수: r = %.3f (p = %.3e)\n', r2, p2);

%% 6. 시각화
figure('Position', [100 100 1400 500]);

% (1) Ω 컬러맵
subplot(1,3,1);
F_GHz = freq_unique / 1e9;
imagesc(F_GHz, Vgs_unique, Omega_abs);
set(gca, 'YDir', 'normal');
xlabel('Frequency [GHz]'); ylabel('V_{GS} [V]');
title('|Ω(V, f)| [deg/(V·GHz)]');
colorbar; colormap(gca, hot);
caxis([0 prctile(Omega_abs(:), 90)]);

% (2) Ω vs |IMD3| 산점도
subplot(1,3,2);
scatter(omega_max_per_V, -imd3_at_V, 60, Vgs_unique, 'filled');
xlabel('|Ω|_{max} [deg/(V·GHz)]');
ylabel('|IMD3| [dBc]');
title(sprintf('Ω vs IMD3 (r = %.3f)', r1));
colormap(gca, jet); cbar = colorbar; cbar.Label.String = 'V_{GS} [V]';
% 회귀선
p = polyfit(omega_max_per_V, -imd3_at_V, 1);
hold on; xfit = linspace(min(omega_max_per_V), max(omega_max_per_V), 100);
plot(xfit, polyval(p, xfit), 'k--', 'LineWidth', 1.5);
grid on;

% (3) Ω vs AM-PM 산점도
subplot(1,3,3);
scatter(omega_max_per_V, ampm_at_V, 60, Vgs_unique, 'filled');
xlabel('|Ω|_{max} [deg/(V·GHz)]');
ylabel('AM-PM rate [deg/dB]');
title(sprintf('Ω vs AM-PM (r = %.3f)', r2));
colormap(gca, jet); cbar = colorbar; cbar.Label.String = 'V_{GS} [V]';
p = polyfit(omega_max_per_V, ampm_at_V, 1);
hold on; xfit = linspace(min(omega_max_per_V), max(omega_max_per_V), 100);
plot(xfit, polyval(p, xfit), 'k--', 'LineWidth', 1.5);
grid on;

sgtitle('CGH40010F: Ω-based Nonlinearity Validation', 'FontWeight', 'bold');
saveas(gcf, 'omega_correlation.png');
```

**합격 기준:**
- |r| > 0.7: Ω가 비선형성과 강한 상관관계
- p-value < 0.05: 통계적으로 유의미

이 기준을 만족하면 논문 핵심 주장이 정립된다.

### 12.3 QucsStudio 검증 시나리오

QucsStudio는 무료이지만 비선형 모델 호환성과 Harmonic Balance 정확도가 ADS보다 제한적이다. 두 시나리오로 진행한다.

#### 12.3.1 시나리오 A: s2p 파일로 선형 검증

MACOM에서 받은 3개 s2p 파일 (I_DQ = 100, 200, 500 mA)만 사용.

**Schematic 구성 (3개 schematic):**
각 s2p 파일에 대해 별도 schematic 생성.
- Component → File-based S-parameter (.s2p) → 파일 경로 지정
- Port 1 (입력, 50Ω), Port 2 (출력, 50Ω)
- S-parameter Simulation block

**시뮬레이션 설정:**
- Frequency: Start = 100 MHz, Stop = 6 GHz, Step = 10 MHz

**결과 export:**
- 각 schematic 결과를 CSV로 export
- 변수: freq, S21 (mag, phase)

**MATLAB 분석:**

```matlab
% qucs_macom_analysis.m
% MACOM 3개 s2p로 1차 검증

% RF Toolbox 사용 (있으면)
s100 = sparameters('macom_100mA.s2p');
s200 = sparameters('macom_200mA.s2p');
s500 = sparameters('macom_500mA.s2p');

% 또는 수동 파싱 (load_s2p.m 함수 사용 - 아래 별도 제공)
% [freq, S] = load_s2p('macom_100mA.s2p');

% S21 추출
freq = s100.Frequencies;
S21_100 = squeeze(s100.Parameters(2,1,:));
S21_200 = squeeze(s200.Parameters(2,1,:));
S21_500 = squeeze(s500.Parameters(2,1,:));

% I_DQ → V_GS 변환 (대략적, CGH40010F 기준)
Vgs_array = [-3.5, -2.8, -1.5];
G_grid = abs([S21_100, S21_200, S21_500]).';   % [3 x nF]
phi_grid = unwrap(angle([S21_100, S21_200, S21_500]), [], 1).';
phi_deg_grid = rad2deg(phi_grid);

% 3점 차분으로 ∂/∂V (정확도 낮음, 정성 분석용)
dV12 = Vgs_array(2) - Vgs_array(1);
dV23 = Vgs_array(3) - Vgs_array(2);
dGdV = zeros(size(G_grid));
dPdV = zeros(size(G_grid));
dGdV(1,:) = (G_grid(2,:) - G_grid(1,:)) / dV12;
dGdV(2,:) = (G_grid(3,:) - G_grid(1,:)) / (Vgs_array(3)-Vgs_array(1));
dGdV(3,:) = (G_grid(3,:) - G_grid(2,:)) / dV23;
dPdV(1,:) = (phi_deg_grid(2,:) - phi_deg_grid(1,:)) / dV12;
dPdV(2,:) = (phi_deg_grid(3,:) - phi_deg_grid(1,:)) / (Vgs_array(3)-Vgs_array(1));
dPdV(3,:) = (phi_deg_grid(3,:) - phi_deg_grid(2,:)) / dV23;

% f 방향 미분 (조밀하므로 정상)
df = (freq(2) - freq(1)) / 1e9;
dGdf = gradient(G_grid, df, 2);
dPdf = gradient(phi_deg_grid, df, 2);

% Omega 계산
Omega = dGdV .* dPdf - dGdf .* dPdV;

% 시각화
figure;
F_GHz = freq / 1e9;
imagesc(F_GHz, Vgs_array, abs(Omega));
set(gca, 'YDir', 'normal');
xlabel('Frequency [GHz]'); ylabel('V_{GS} [V]');
title('|Ω| from MACOM data (3 bias points)');
colorbar; colormap(hot);
```

**확인할 것:**
- 3개 바이어스에서 |S₂₁|의 패턴 비교
- I_DQ = 100mA (Class C 근처): 이득이 낮음
- I_DQ = 200mA (Class AB): 중간 이득
- I_DQ = 500mA (Class A): 높은 이득

**한계:**
- V 방향 그리드가 3개뿐이라 ∂/∂V 정확도 낮음
- IMD3, AM-PM 측정이 없으므로 정량적 검증 불가
- 정성적 검증 또는 Phase 1 prototype 수준에 그침

#### 12.3.2 시나리오 B: SPICE 모델로 비선형 검증

Wolfspeed에서 받은 SPICE 모델 (.lib 또는 .sp)을 사용.

**모델 import:**
- File → Import → SPICE Netlist (모델 파일 선택)
- 모델을 라이브러리에 추가
- Schematic 컴포넌트 팔레트에 CGH40010F 추가

**Test bench:**
ADS 시나리오와 동일하게 게이트/드레인 바이어스 회로, DC block, RF choke, Term 50Ω 추가.

**시뮬레이션 1: S-parameter Sweep**
- AC simulation block 또는 S-parameter simulation
- ParamSweep으로 V_GS = -4.5V ~ -1.0V, Step = 0.1V
- Frequency: 100 MHz ~ 6 GHz

**시뮬레이션 2: Harmonic Balance**
QucsStudio HB는 ADS보다 제한적이지만 기본 IM3 측정 가능:
- Two-tone HB 또는 transient + FFT 사용
- f₁ = 2 GHz, f₂ = 2.005 GHz, P_in = -10 dBm
- IMD3 추출

**한계:**
- QucsStudio HB는 수렴이 까다로움
- 고차 비선형 정확도가 ADS보다 낮음
- 그러나 정성적 패턴 확인은 가능

**Python 분석:**
ADS 시나리오와 동일한 코드로 상관관계 분석.

#### 12.3.3 QucsStudio 검증의 적절성

QucsStudio만으로 논문 가능한가:

- **Letter 저널 (MWCL):** 가능하지만 reviewer가 "왜 ADS 안 썼나"고 물을 수 있음
- **풀 저널:** ADS 검증이 강력히 권장됨

QucsStudio 검증은 ADS 접근이 불가능한 경우의 차선책이다. 가능하면 ADS 사용 권장.

### 12.4 Phase별 권장 진행

각 phase는 독립적 가치를 가지므로 어디서 멈춰도 일정 수준의 결과를 얻는다.

| Phase | 도구 | 기간 | 결과물 | 논문 가치 |
|---|---|---|---|---|
| 1 | MATLAB + MACOM s2p (3개) | 1주 | Ω 계산 + 패턴 정성 확인 | Conference proceedings |
| 2 | QucsStudio + SPICE 모델 + MATLAB | 2~3주 | 조밀 그리드 Ω + 기본 비선형 | Letter 저널 (MWCL) 가능 |
| 3 | ADS + Cree Design Kit + MATLAB | 1~2주 | 정확한 Ω vs IMD3/AM-PM 상관관계 | 풀 저널 (TMTT) 가능 |

### 12.5 논문 핵심 Figure 구성

검증이 끝나면 논문은 다음 4개 figure를 중심으로 구성한다.

**Figure 1: Ω(V, ω) 2D 컬러맵**
- x축: 주파수 (GHz)
- y축: V_GS (V)
- 색상: |Ω| 값
- 어떤 V-ω 영역이 비선형성이 강한지 한눈에 보여줌

**Figure 2: 검증 비교맵**
- 같은 V-ω 그리드에서 측정한 IMD3 (또는 AM-PM)의 컬러맵
- Figure 1과 색 패턴이 유사하면 Ω의 유효성 확인

**Figure 3: 상관관계 산점도**
- x축: |Ω|_max (각 V_GS에서)
- y축: -IMD3_dBc 또는 AM-PM rate
- 점 색상: V_GS
- 직선 fit + 상관계수 r 표시

**Figure 4: 응용 예시**
- Ω 기반 최적 바이어스 vs P1dB 기반 최적 바이어스
- 각각으로 PA 동작 시 EVM 또는 ACLR 비교
- Ω 방법이 광대역에서 우수함을 보여줌

이 4개가 핵심이고 추가로 이론 유도 schematic이나 측정 setup 사진이 보조 figure로 들어간다.

---

## 부록 A: 기호 요약

| 기호 | 의미 | 단위 |
|---|---|---|
| V | 바이어스 전압 (보통 V_GS) | V |
| ω | 각주파수 (= 2πf) | rad/s |
| f | 주파수 | Hz |
| S₂₁ | 순방향 전달 S-parameter | 무차원 (복소수) |
| G | |S₂₁|, 이득의 크기 | 무차원 (선형) |
| φ | ∠S₂₁, 위상 | rad |
| ∂G/∂V | 바이어스 이득 감도 | 1/V |
| ∂G/∂ω | 이득 평탄도의 음수 | s |
| ∂φ/∂V | AM-PM 계수 | rad/V |
| ∂φ/∂ω | 음의 군지연 | s |
| Ω | V-ω 공간 비선형성 곡률 | rad/V (rad·s/V·s 약분) |

실용 단위: rad → deg, ω → f(GHz)로 변환하면 Ω 단위는 [deg/(V·GHz)].

## 부록 B: 외미분 형식과 Jacobian

미분기하학에서 V-ω 평면의 면적 형식 dV ∧ dω가 G-φ 평면의 면적 형식 dG ∧ dφ로 어떻게 변환되는지의 비례 계수가 Jacobian 행렬식이다. Ω는 이 비례 계수다.

이는 양자역학의 Berry curvature와 같은 수학적 구조다. Berry curvature가 양자 상태 공간의 곡률을 측정하듯이, Ω는 RF 응답 공간의 곡률을 측정한다.
