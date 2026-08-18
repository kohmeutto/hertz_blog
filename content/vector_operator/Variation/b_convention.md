+++
title = "(b) Convention"
weight = 10
+++

---

### 1. 표기 규약

**1) 헷: 유계 선형 연산자**

기호 위에 헷($\hat{\cdot}$)이 붙은 표기는 $V \to V^*$의 유계 선형 연산자를 뜻한다. 켓과 나란히 붙여 쓰면 해당 연산자의 작용을 나타낸다. 헷이 붙지 않은 기호는 비선형 사상을 의미한다.

$$
\hat{A}|u\rangle \in V^*, \qquad \hat{A}\big(c_1|u_1\rangle + c_2|u_2\rangle\big) = c_1\hat{A}|u_1\rangle + c_2\hat{A}|u_2\rangle
$$

$$
N(u) \in V^* \quad (\text{허용})
$$

$$
N|u\rangle \quad (\text{금지})
$$

* 의미: 헷은 선형성을 표시하고, 켓과의 병치(juxtaposition)는 작용을 표시한다.
* 금지 이유: 병치 표현 자체가 이미 선형 작용의 의미를 담고 있으므로, 비선형 사상을 병치로 쓰면 선형성 여부를 판별할 수 없다.

**2) 소괄호: 상태 의존성**

대상이 상태에 의존할 때 그 사실을 소괄호로 표기한다. 괄호 내부에는 켓 기호($|u\rangle$)가 아닌 상태의 명칭($u$)만을 쓴다.

$$
\hat{A}(u) \quad (\text{의존성 명시})
$$

$$
\hat{A}(u)|v\rangle \quad (\text{의존하는 연산자가 켓에 작용})
$$

$$
\hat{A}\big(|u\rangle\big) \quad (\text{금지})
$$

* 의미: 괄호 안이 이름이면 의존성을 뜻하고, 병치된 것이 켓이면 작용을 뜻한다.
* 금지 이유: 소괄호가 의존성을 나타내는 상황에서 내부에 켓이 들어있으면, 의존성 표시인지 연산의 작용인지 결정할 수 없다.

**3) 중괄호: 변분의 작용 범위**

변분 연산자 $\delta$는 직후에 위치한 단일 기호 하나에만 작용한다. 둘 이상의 기호를 한 덩어리로 묶어 변분하려면 중괄호로 범위를 지정한다.

$$
\delta\hat{A}, \quad \delta|u\rangle, \quad \delta S \qquad (\text{단일 기호})
$$

$$
\delta\big\{\hat{A}(u)|u\rangle\big\} \quad (\text{복합식})
$$

$$
\delta\hat{A}|u\rangle \quad (\text{금지})
$$

* 의미: 중괄호가 없으면 작용 범위는 뒤에 오는 단일 기호 하나로 한정된다.
* 금지 이유: 범위를 명시하지 않으면 $(\delta\hat{A})|u\rangle$인지 $\delta\{\hat{A}|u\rangle\}$인지 해석을 결정할 수 없다.

**4) 대괄호와 콜론: 동작점과 방향**

도함수 $D$에는 동작점과 방향 정보를 함께 전달한다. 대괄호를 사용하고 콜론($:$)의 왼쪽에 동작점을, 오른쪽에 방향 인자를 적는다.

$$
DX[a : |\eta\rangle] \quad (\text{변분값})
$$

$$
DX[a : \cdot] \quad (\text{사상 자체})
$$

$$
DX[|\eta\rangle] \quad (\text{동작점 생략})
$$

$$
D^2X[a : |\eta_1\rangle, |\eta_2\rangle] \quad (\text{다중 방향})
$$

$$
DX\big|_a[|\eta\rangle] \quad (\text{금지})
$$

* 의미: 콜론 오른쪽을 비워두면 방향 인자를 아직 받지 않은 국소 선형 사상 자체를 가리킨다.
* 금지 이유: 세로줄($|$)은 디랙 표기의 켓과 브라 구획선으로 쓰이므로, 어느 세로줄이 동작점을 지정하는 것인지 구문상 결정할 수 없다.

**5) 아래첨자와 인자 생략: 동결과 감춤**

두 표기 모두 식을 간소화하지만 대수적 결과는 반대이다. 아래첨자를 붙이면 상태 자리에 값이 고정되어 더 이상 변수로 작동하지 않으며, 인자를 생략하면 표기상에서만 숨겨질 뿐 활성화된 변수 상태를 유지한다.

$$
\hat{A}_a \equiv \hat{A}(u)\big|_{u=a}, \qquad \delta\hat{A}_a = 0 \qquad (\text{아래첨자: 동결})
$$

$$
\hat{A} \equiv \hat{A}(u), \qquad \delta\hat{A} \neq 0 \qquad (\text{인자 생략: 감춤})
$$

$$
\hat{A}_u \quad (\text{금지})
$$

* 의미: 표기의 축약이 필요할 때는 인자 생략을 사용하고, 특정 동작점을 지정하여 고정할 때만 아래첨자를 붙인다.
* 금지 이유: $u$는 변분의 대상이므로 $\hat{A}_u$로 표기하면 값인지 활성 변수인지 판별할 수 없다.

**6) 내적의 아래첨자: 동일시의 명시**

공간 삼중항에는 둘 이상의 내적이 존재한다. 따라서 대상을 내적을 통해 켓으로 환산할 때는 어떤 내적을 사용했는지 첨자로 명시한다.

$$
\langle \nabla_{\!\mathcal{H}} S | \eta \rangle_{\mathcal{H}}, \qquad \langle \nabla_{\!V} S | \eta \rangle_V \qquad (\text{두 켓은 서로 다르다})
$$

$$
\frac{\delta S}{\delta u} \quad (\text{내적 미명시. } \mathcal{H}\text{-동일시로 읽되 존재성을 별도 확인해야 한다})
$$

* 의미: 아래첨자에 환산에 사용한 내적을 적는다.
* 금지 이유: 첨자를 생략하면 어떤 내적으로 환산했는지 결정할 수 없으며, §5의 정리 2에 따라 선택한 내적에 의해 환산된 켓이 달라지기 때문이다.

---

### 2. 정의

**1) 정의 1 (변분 연산자 $\delta$)**

변분 방향 켓 $|\eta\rangle \in V$를 고정된 인자로 설정한다. 상태 $u$에 의존하는 임의의 대상 $X(u)$에 대하여 변분 연산자 $\delta$를 다음과 같이 정의한다.

$$
\delta X \equiv \left. \frac{d}{d\epsilon} X(u + \epsilon\eta) \right|_{\epsilon = 0}, \qquad \epsilon \in \mathbb{R}
$$

* 적용 대상: 스칼라, 켓, 연산자 등 대상의 종류에 상관없이 동등하게 적용된다.
* $d/d\epsilon$의 성질: 실수 한 변수에 대한 보통의 미분이다. 곱의 법칙, 연쇄 법칙, 선형성 및 상수의 미분이 $0$이 되는 성질이 그대로 상속된다.

**2) 정의 2 (도함수 $D$)**

$\delta X$는 동작점과 방향이 모두 고정된 후 얻어지는 결과값이다. 두 정보를 슬롯으로 전달받는 사상 자체를 $DX$로 표기하며, $DX$가 존재한다는 것은 다음 두 조건을 동시에 만족한다는 뜻이다.

* 방향에 대한 유계 선형성:

$$
DX[a : c_1|\eta_1\rangle + c_2|\eta_2\rangle] = c_1 DX[a : |\eta_1\rangle] + c_2 DX[a : |\eta_2\rangle]
$$

* 잔차의 균등 소멸 (프레셰 미분가능성):

$$
\lim_{\| \eta \|_V \to 0} \frac{\| X(a+\eta) - X(a) - DX[a : |\eta\rangle] \|}{\| \eta \|_V} = 0
$$

**3) 두 정의의 관계**

정의 2의 조건이 성립할 때 $\delta$와 $D$가 연결된다. 동작점이 현재 상태 $u$일 경우 §3-5의 규약에 따라 표기를 생략할 수 있다.

$$
\delta X = DX[u : |\eta\rangle] = DX[|\eta\rangle]
$$

$$
D \text{ 존재} \implies \delta \text{ 존재}, \qquad \delta \text{ 존재} \not\implies D \text{ 존재}
$$

* $\delta X$: 슬롯이 없는 단일 결과값이다.
* $DX[\cdot]$: 두 정보를 슬롯으로 받으며, 오른쪽 슬롯을 비워두면 사상 자체를 나타낸다.
* 정상성 조건: $\delta$는 방향마다 개별적으로 존재하는 값이며, 그 값들의 모임이 당연히 하나의 선형 사상을 형성하는 것은 아니기 때문이다.

---

### 3. 해석 예시

**1) 스칼라 변분: 해석역학의 정상성 조건**

작용량 $S(q)$는 상태를 받아 스칼라를 출력한다. $\delta S$ 역시 스칼라이다.

$$
\delta S = \left. \frac{d}{d\epsilon} S(q + \epsilon\eta) \right|_{\epsilon=0} = DS[q : |\eta\rangle]
$$

$$
DS[q : |\eta\rangle] = 0 \qquad \forall |\eta\rangle \in V \qquad (\text{정상성 조건})
$$

* 해석: 모든 방향에 대해 변분값이 $0$이면 되며, 그 값들이 하나의 선형 사상을 이룰 필요는 없다.
* 적용 정의: 정의 1만으로 충분하며 정의 2는 필요하지 않다.

**2) 연산자 변분: 연속체역학의 접선 강성**

변형 상태 $|\varepsilon\rangle$에 의존하는 강성 $\hat{C}(\varepsilon)$에 대해 응력이 $\hat{C}(\varepsilon)|\varepsilon\rangle$로 주어질 때 응력의 변분을 구한다.

$$
\delta\big\{\hat{C}(\varepsilon)|\varepsilon\rangle\big\} = \left. \frac{d}{d\epsilon} \Big[ \hat{C}(\varepsilon + \epsilon\eta) \big(|\varepsilon\rangle + \epsilon|\eta\rangle\big) \Big] \right|_{\epsilon=0}
$$

$$
\delta\big\{\hat{C}(\varepsilon)|\varepsilon\rangle\big\} = (\delta\hat{C}) |\varepsilon\rangle + \hat{C}(\varepsilon)|\delta\varepsilon\rangle
$$

* 해석: 강성 연산자를 고정된 연산자로 간주하면 첫 번째 항이 사라진다.
* 1항의 당위성: $\hat{C}(\varepsilon)$로 표기하여 $\varepsilon$ 의존성을 명시했으므로, 곱의 법칙에 따라 첫 번째 항이 반드시 도출된다.

proof)

대괄호 안은 $\epsilon$에 대한 두 함수의 곱이므로 곱의 법칙을 적용한다.

$$
\left. \left[ \frac{d}{d\epsilon} \hat{C}(\varepsilon+\epsilon\eta) \right] \big(|\varepsilon\rangle + \epsilon|\eta\rangle\big) \right|_{\epsilon=0} + \left. \hat{C}(\varepsilon+\epsilon\eta) \left[ \frac{d}{d\epsilon} \big(|\varepsilon\rangle+\epsilon|\eta\rangle\big) \right] \right|_{\epsilon=0}
$$

네 부분을 각각 $\epsilon = 0$에서 계산한다.

$$
\left. \frac{d}{d\epsilon} \hat{C}(\varepsilon+\epsilon\eta) \right|_{\epsilon=0} = \delta\hat{C}, \qquad (|\varepsilon\rangle + \epsilon|\eta\rangle)\big|_{\epsilon=0} = |\varepsilon\rangle
$$

$$
\hat{C}(\varepsilon+\epsilon\eta)\big|_{\epsilon=0} = \hat{C}(\varepsilon), \qquad \left. \frac{d}{d\epsilon} \big(|\varepsilon\rangle+\epsilon|\eta\rangle\big) \right|_{\epsilon=0} = |\eta\rangle = |\delta\varepsilon\rangle
$$

**3) 내적의 변분: 양자역학의 규격화 조건**

규격화 조건 $\langle\psi|\psi\rangle = 1$이 변분 방향에 부과하는 제약 조건을 구한다. 정의 1에서 $\epsilon \in \mathbb{R}$이므로 곱의 법칙이 내적의 두 슬롯에 적용된다.

$$
\delta\big\{\langle\psi|\psi\rangle\big\} = \langle \delta\psi | \psi\rangle + \langle \psi | \delta\psi\rangle
$$

$$
\mathrm{Re}\langle\psi|\eta\rangle = 0 \qquad (\text{허용되는 변분 방향})
$$

* 해석: 규격화를 유지하는 변분 방향은 $|\psi\rangle$에 실수 의미에서 직교하는 것들이다.
* $\epsilon$의 실숫값 조건: $\epsilon$이 복소수라면 내적의 첫 슬롯 변분에 곱의 법칙이 성립하지 않는다.

proof)

우변의 두 항은 켤레 관계이므로 실수부의 두 배로 정리된다.

$$
\langle \delta\psi | \psi\rangle + \langle \psi | \delta\psi\rangle = 2\mathrm{Re}\langle\psi|\delta\psi\rangle
$$

좌변은 상수 $1$의 변분이므로 $0$이다.

$$
2\mathrm{Re}\langle\psi|\delta\psi\rangle = 0
$$

$|\delta\psi\rangle = |\eta\rangle$을 대입하고 $2$로 나누면 결과가 도출된다. 

---

### 4. 표기 요약표

**1) 기호의 역할**

| 기호 | 적용 위치 | 대수적 역할 | 작성 예시 |
| :--- | :--- | :--- | :--- |
| **헷 ($\hat{\cdot}$)** | 연산자 기호 위 | 유계 선형 연산자($V \to V^*$)임을 표시 | $\hat{A}$ |
| **병치** | 연산자와 켓 사이 | 선형 연산자의 작용을 표시 | $\hat{A}\vert u\rangle$ |
| **소괄호 `()`** | 대상 직후 | 상태 의존성을 표시 (내부에 상태 명칭 사용) | $\hat{A}(u)$ |
| **중괄호 `{}`** | $\delta$ 직후 | 변분의 작용 범위를 지정 | $\delta\{\hat{A}\vert u\rangle\}$ |
| **대괄호 `[]`** | $D$ 직후 | 동작점과 방향 인자를 전달 | $DX[a : \vert \eta\rangle]$ |
| **콜론 `:`** | 대괄호 내부 | 동작점과 방향 인자를 구별 | $[a : \vert \eta\rangle]$ |
| **쉼표 `,`** | 콜론 오른쪽 | 다중 방향 인자를 나열 | $[a : \vert \eta_1\rangle, \vert \eta_2\rangle]$ |
| **오른쪽 비움** | 대괄호 내부 | 방향을 받지 않은 사상 자체를 지정 | $DX[a : \cdot]$ |
| **아래첨자** | 대상 우하단 | 상태 자리에 특정 값을 고정 | $\hat{A}_a$ |
| **인자 생략** | 소괄호 제거 | 상태 인자를 표기에서 감춤 | $\hat{A} \equiv \hat{A}(u)$ |
| **내적 첨자** | 브라켓 우하단 | 리스 동일시에 사용한 내적을 명시 | $\langle\cdot\vert\cdot\rangle_{\mathcal{H}}$ |

<br>

**2) 금지 표기 및 올바른 표기**

| 금지 표기 | 위반 항목 | 올바른 표기 | 사유 |
| :--- | :--- | :--- | :--- |
| $\hat{A}\big(\vert u\rangle\big)$ | §3-2 | $\hat{A}(u)$ | 소괄호 내부에 켓 표기 사용 금지 |
| $N\vert u\rangle$ ($N$ 비선형) | §3-1 | $N(u)$ | 비선형 사상에 병치 작용 표기 사용 금지 |
| $\delta\hat{A}\vert u\rangle$ | §3-3 | $(\delta\hat{A})\vert u\rangle$ 또는 $\delta\{\hat{A}\vert u\rangle\}$ | 변분 작용 범위의 모호성 |
| $DX\big\vert_a[\vert\eta\rangle]$ | §3-4 | $DX[a : \vert\eta\rangle]$ | 세로줄($\vert$) 사용으로 인한 디랙 표기와의 구문 충돌 |
| $D\{\hat{A}_a\}[\vert\eta\rangle]$ | §3-5 | $DX[a : \vert\eta\rangle]$ | 고정된 상숫값 대상에 대한 미분 수행 모순 |
| $\hat{A}_u$ | §3-5 | $\hat{A}$ 또는 $\hat{A}_a$ | 변분 대상 $u$를 아래첨자로 고정 표현 금지 |
| $\hat{D}$, $\hat{\delta}$ | §3-1 | $D$, $\delta$ | 미분/변분 연산자에 헷 표기 부과 금지 |
| $\hat{A}(u; \delta u)$ | 정의 1 | $\delta\hat{A}$ 또는 $D\hat{A}[\vert\eta\rangle]$ | 세미콜론 사용 및 방향 인자의 중복 전달 금지 |
| $[\cdot] \in \mathcal{L}(\mathcal{H})$ | 정리 1 | 소속은 대상에 따라 정해짐 | 괄호 종류에 따른 출력 공간 소속 고정 오류 |