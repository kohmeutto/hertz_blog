+++
title = "System"
weight = 10
+++

---

### 1. 닫힌계, 고립계, 열린계

| 계의 분류 | 질량 교환 | 에너지 교환 | 대표 예시 및 특징 |
| :--- | :---: | :---: | :--- |
| **고립계**<br>(Isolated System) | 불가<br>($\Delta m = 0$) | 불가<br>($Q=0, W=0$) | [물체 + 장 + 외력원] 전체, 외부와 완전히 단절된 우주 |
| **닫힌계**<br>(Closed System) | 불가<br>($\Delta m = 0$) | 가능<br>($Q \neq 0, W \neq 0$) | [물체 + 장] (외력이 일을 가함), 밀폐 용기 내 반응계 |
| **열린계**<br>(Open System) | 가능<br>($\Delta m \neq 0$) | 가능<br>($Q \neq 0, W \neq 0$) | 공간 검사 체적(포인팅 벡터 $\oint \mathbf{S} \cdot d\mathbf{a}$ 유출입), 파이프 유동 |

---

### 2. Field, Potential, 일과 에너지 정리

**1) 장(Field)**

- 공간상에 분포하여 입자와 국소적으로 상호작용하며 에너지, 운동량을 직접 저장하고 운반하는 **독립된 물리적 주체(Physical Agent)** 이다. 
- **국소 작용** 이란 입자는 멀리 떨어진 원격 입자와 직접 상호작용하는 것이 아니라, 자신이 위치한 지점의 장과 국소적으로 에너지를 교환하는 것이다.

**2) Potential**

- 장을 계에 포함시켰을 때, 장의 에너지를 potential 이라 한다. 입자가 없는 진공이라 하더라도 장이 존재하면 공간 체적당 에너지가 실재한다.

$$u_e = \frac{1}{2}\epsilon_0 \vert{}\mathbf{E}\vert{}^2, \quad u_g = -\frac{1}{8\pi G} \vert{}\mathbf{g}\vert{}^2$$

- 장을 계 외부의 객체로 취급(일을 하는 대상)할 때와, 장을 계 내부의 객체로 취급(계 에너지의 대상)할 때의 관계는 아래와 같다.

$$\Delta U \equiv -W_{\text{field}} = -\int_{a}^{b} \mathbf{F}_{\text{field}} \cdot d\mathbf{l}$$

$$\mathbf{F}_{\text{field}} = -\nabla U$$

**3) 일과 에너지 정리**

$$
\text{계(system)의 에너지 변화량} = \text{계 외부에서 한 일}
$$

---

### 3. Example 1: 중력장과 질량 물체 (낙하 및 들어올리기)

질량 $m$인 물체가 중력장 $\mathbf{g} = -g \hat{\mathbf{j}}$ 하에서 높이 $h$만큼 이동할 때, 계의 경계 설정에 따라 물리량이 어떻게 기술되는지 비교한다.

**1) 물체를 높이 $h$에서 가만히 떨어뜨리는 경우 (자연 낙하: $y = h \to 0$)**

(1) 경계 설정 A: 계 = [물체 단독]

- 중력장은 계 외부에 존재하므로, 중력은 외력($W_{\text{ext}}$)으로 작용한다.
- 중력의 작용 방향($-y$)과 이동 방향($-y$)이 같으므로 외력이 한 일은 양수이다.

$$
W_{\text{ext}} = W_{\text{field}} = \int_{h}^{0} (-mg \hat{\mathbf{j}}) \cdot (dy \hat{\mathbf{j}}) = +mgh > 0
$$

- 일-에너지 정리:

$$
\Delta K = W_{\text{ext}} = +mgh \quad \Longrightarrow \quad K_f - 0 = mgh
$$

(2) 경계 설정 B: 계 = [물체 + 지구 중력장]

- 중력장은 계 내부에 포함되므로, 외부에서 가해진 일은 없다 ($W_{\text{ext}} = 0$).- 장이 물체에 한 양의 일($W_{\text{field}} = +mgh$)은 장의 잔고를 소모시키므로 퍼텐셜 에너지 감소로 기록된다.

$$
\Delta U \equiv -W_{\text{field}} = -(+mgh) = -mgh < 0
$$

- 에너지 보존:

$$
\Delta E_{\text{sys}} = \Delta K + \Delta U = 0 \quad \Longrightarrow \quad \Delta K = -\Delta U = +mgh
$$

**2) 외력(손)이 물체를 일정한 속도로 들어 올리는 경우 ($y = 0 \to h$)계 = [물체 + 지구 중력장]**

- 중력은 이동 방향과 반대이므로 장이 한 일은 음수이다. ($W_{\text{field}} = -mgh < 0$)
- 따라서 퍼텐셜 에너지는 증가한다. ($\Delta U = -W_{\text{field}} = +mgh > 0$)
- 손이 가한 외력의 일($W_{\text{손}} = +mgh$)은 계의 퍼텐셜 에너지를 충전하는 데 사용된다. ($\Delta K = 0$)

$$\Delta E_{\text{sys}} = \Delta U = W_{\text{손}} = +mgh$$

---

### 4. Example2: 수소 원자계 (양성자-전자 결합과 질량 결손)

**1) 전자기장(Field)이 수행한 일과 퍼텐셜 에너지**

- 쿨롱 인력 벡터 (중심 인력 방향):

$$\mathbf{F}_e = -\frac{1}{4\pi\epsilon_0}\frac{e^2}{r^2}\hat{\mathbf{r}}$$

- 이동 변위 벡터 ($r = \infty \to a_0$, $dr < 0$): 

$$d\mathbf{l} = dr \hat{\mathbf{r}}$$

- 전기장이 한 일 ($W_{\text{field}}$): 인력 방향과 접근 방향이 일치하므로 장은 양의 일을 수행한다.

$$W_{\text{field}} = \int_{\infty}^{a_0} \left(-\frac{1}{4\pi\epsilon_0}\frac{e^2}{r^2}\hat{\mathbf{r}}\right) \cdot (dr\hat{\mathbf{r}}) = \left[ \frac{1}{4\pi\epsilon_0}\frac{e^2}{r} \right]_{\infty}^{a_0} = +\frac{e^2}{4\pi\epsilon_0 a_0} > 0$$

- 계 = [양성자 + 전자 + 전자기장]의 퍼텐셜 에너지 변화:

$$\Delta U \equiv -W_{\text{field}} = -\frac{e^2}{4\pi\epsilon_0 a_0} \approx -27.2\text{ eV} < 0$$

**2) 에너지 방출 및 질량 결손 ($E = mc^2$)**

- 에너지 수지: 전자의 운동에너지는 $\Delta K = +13.6\text{ eV}$ 증가하며, 결합 과정에서 계 밖으로 광자(빛) 형태로 방출된 에너지는 $13.6\text{ eV}$이다.

$$\Delta E_{\text{sys}} = \Delta K + \Delta U = +13.6\text{ eV} - 27.2\text{ eV} = -13.6\text{ eV} \quad (\text{에너지 방출})$$

- 공간 장 에너지 밀도 적분과의 일치: 입자들의 상대 배치가 달라짐에 따라 전 공간의 합성 전기장 $\mathbf{E} = \mathbf{E}_p + \mathbf{E}_e$의 에너지 적분값($\frac{1}{2}\int \epsilon_0 \vert{}\mathbf{E}\vert{}^2 dV$)이 정확히 $27.2\text{ eV}$만큼 감소하여 방출 에너지의 원천이 된다.
- 질량 결손 실재성: 형성된 수소 원자 계의 총 질량은 구성 입자들의 고유 질량 합보다 정확히 결손된 결합 에너지에 해당하는 양만큼 가볍다.