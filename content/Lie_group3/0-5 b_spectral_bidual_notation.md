+++
title = "스펙트럼 분해와 바이듀얼 표기"
weight = 5
+++

### 1. 이 절의 동기

이 시리즈 전체에서 연산자를 *스펙트럼 분해(spectral decomposition)* 형태로 표현하고, 기저와 쌍대 기저를 *바이듀얼(bidual) 표기* 로 명시한다. 이 절은 그 표기 약속을 한 자리에서 정리한다.

*왜 이런 표기를 쓰나*.

(1) *비에르미트 연산자가 자주 등장한다*. 반에르미트 행렬 (리 대수의 원소), 비유니타리 연산자 (NEGF 의 자기에너지 $\Sigma$), 비정규 연산자 (G^R, G^A) 등. 이들은 *좌고유벡터와 우고유벡터가 다를 수 있다* — 한 종류만 쓰는 표준 디랙 표기는 부정확해진다.

(2) *비직교 기저가 자연스럽게 등장한다*. 일반 좌표계 (§0-4 의 $\partial_i, dx^i$), 비에르미트 연산자의 고유 기저 등. 이때 *쌍대 기저* 가 일반 기저와 다르고, 명시적으로 추적해야 한다.

(3) *스펙트럼 형태가 모든 함수 계산을 통일* 한다. 한 번 $H = \sum_i \lambda_i |\lambda_i\rangle \langle \lambda^i|$ 으로 분해해 두면 $f(H) = \sum_i f(\lambda_i) |\lambda_i\rangle \langle \lambda^i|$ 로 어떤 함수든 적용 가능. 특히 *지수 사상* $\exp(tH) = \sum_i e^{t\lambda_i} |\lambda_i\rangle \langle \lambda^i|$ 이 리 군 시리즈의 핵심.

이 절은 (i) 벡터 공간과 쌍대, (ii) 기저와 쌍대 기저, (iii) 브라켓 표기 약속, (iv) 정규 연산자에서의 단순화, (v) 연속 기저, (vi) 스펙트럼 분해, (vii) 함수 계산과 지수 사상 — 의 순서로 약속한다.

### 2. 벡터 공간과 쌍대 공간

**1)** *벡터 공간* $V$ — 덧셈과 스칼라 배가 정의된 공간 (체 $\mathbb{F} = \mathbb{R}$ 또는 $\mathbb{C}$ 위).

**2)** *쌍대 공간(dual space)* $V^*$ — *$V$ 위 선형 범함수* 들의 공간

$$V^* = \{ \omega : V \to \mathbb{F} \mid \omega \text{ 선형} \}$$

자체로 벡터 공간이고, *유한 차원* 에서는 $\dim V^* = \dim V$.

**3)** *§0-4 와의 연결*. 다양체의 한 점에서 *접공간* $T_p M$ 이 벡터 공간이고 *코탄젠트 공간* $T_p^* M = (T_p M)^*$ 이 그 쌍대였다. 본 절의 약속은 *벡터 공간 일반* 에 적용되고, 다양체의 접·코탄젠트는 그 *한 점에서의 구현*.

**4)** *이중 쌍대 (double dual)* $V^{**}$ — 유한 차원에서는 $V^{**} \cong V$ (자연 동형). 따라서 *한 번 쌍대를 취한 후 다시 취하면 원래로 돌아온다*. 이것이 "*바이듀얼(bidual) 표기*" 의 어원 — 켓과 브라가 서로 쌍대 관계로 *왔다 갔다* 할 수 있는 구조.

### 3. 기저와 쌍대 기저

**1)** *기저(basis)*. 유한 차원 벡터 공간 $V$ ($\dim V = n$) 의 *기저* 는 *선형 독립이고 공간을 생성* 하는 $n$ 개 벡터 $\{v_1, v_2, \cdots, v_n\}$.

**2)** *임의 벡터의 좌표 전개*. 임의 $v \in V$ 는

$$v = \sum_{i=1}^n v^i \, v_i \quad (\text{또는 아인슈타인 합 규약으로 } v^i v_i)$$

성분 $v^i \in \mathbb{F}$ 가 *좌표 (성분)*. *기저는 아래 첨자, 성분은 위 첨자* — 텐서 분석의 표준 규약.

**3)** *쌍대 기저(dual basis)*. 기저 $\{v_1, \cdots, v_n\}$ 에 대해, *쌍대 기저* 는 $V^*$ 의 기저 $\{v^1, \cdots, v^n\}$ 로, *쌍대 관계*

$$v^i(v_j) = \delta^i_j$$

로 정의된다. 여기 $\delta^i_j$ 는 *크로네커 델타* ($i = j$ 이면 $1$, 아니면 $0$).

**4)** *주의 — 쌍대 기저는 기저에 의존*. 같은 공간에 다른 기저를 잡으면 그 쌍대 기저도 다르다. *쌍대 기저는 기저 자체와 일반적으로 다른 객체*.

**5)** *첨자 위치 규약*.
- *아래 첨자* — 기저 (벡터)
- *위 첨자* — 쌍대 기저 (선형 범함수) 또는 벡터의 성분
- 아인슈타인 합 규약 — 같은 첨자가 *한 번은 위, 한 번은 아래* 로 나타나면 자동 합산. $v^i v_i = \sum_i v^i v_i$.

### 4. 브라켓 표기 — 켓과 브라

**1)** *디랙의 브라켓 표기(Dirac bracket notation)* 를 본 시리즈 전반에서 사용한다.
- *켓(ket)* $|v\rangle$ — 벡터 공간 $V$ 의 원소
- *브라(bra)* $\langle \omega |$ — 쌍대 공간 $V^*$ 의 원소
- *내적/짝짓기(pairing)* $\langle \omega | v \rangle$ — 브라가 켓에 작용한 결과 ($\in \mathbb{F}$)

**2)** *기저와 쌍대 기저의 브라켓 표기*. 기저 벡터를 $|v_i\rangle$, 쌍대 기저를 $\langle v^i|$ 로 적는다. 쌍대 관계는

$$\langle v^i | v_j \rangle = \delta^i_j$$

**3)** *임의 켓·브라의 전개*.
$$|v\rangle = \sum_i v^i |v_i\rangle, \qquad \langle \omega | = \sum_i \omega_i \langle v^i |$$

켓 성분은 위 첨자 ($v^i$), 브라 성분은 아래 첨자 ($\omega_i$). 짝짓기는

$$\langle \omega | v \rangle = \sum_{i, j} \omega_i v^j \langle v^i | v_j \rangle = \sum_{i, j} \omega_i v^j \delta^i_j = \sum_i \omega_i v^i$$

— 위·아래 첨자의 자연스러운 축약.

**4)** *§0-4 와의 일치*. 다양체의 접·코탄젠트 구조에서

$$|v_i\rangle \leftrightarrow \frac{\partial}{\partial x^i}, \qquad \langle v^i| \leftrightarrow dx^i, \qquad \langle v^i | v_j \rangle \leftrightarrow dx^i(\partial_j) = \delta^i_j$$

*완전히 같은 구조*. 다양체의 코탄젠트는 본 절 약속의 *기하학적 구현*.

**5)** *항등 사상의 분해(resolution of identity)*. 기저-쌍대 기저로 항등 연산자가 분해된다.

$$I = \sum_i |v_i\rangle \langle v^i|$$

(증명 — 임의 $|v\rangle = \sum_j v^j |v_j\rangle$ 에 양변 작용. 좌변은 $|v\rangle$. 우변은 $\sum_i |v_i\rangle \langle v^i| \cdot \sum_j v^j |v_j\rangle = \sum_{i,j} v^j |v_i\rangle \delta^i_j = \sum_i v^i |v_i\rangle = |v\rangle$.)

이 *항등 분해* 가 시리즈 전체의 핵심 도구. 어떤 연산자도 그 사이에 $I$ 를 끼워 넣어 스펙트럼 형태로 전개할 수 있다.

### 5. 단일 (비기저) 벡터의 표기 — 첨자 없음

**1)** *기저 원소가 아닌 단일 벡터* 는 첨자 없이 그냥 $|v\rangle$, $\langle v|$ 로 적는다. *첨자가 있으면 (어떤) 기저의 한 원소* 라는 약속.

**2)** *쌍대 표기*. 단일 켓 $|v\rangle$ 의 쌍대 브라는 *복소켤레 전치* 로 정의되는 표준 디랙 약속을 따른다 — 내적이 정의된 (힐베르트) 공간에서

$$\langle v | := |v\rangle^\dagger$$

내적은 $\langle u | v \rangle$. 이 경우 *기저 첨자 없이 단순 표기*.

**3)** *주의 — 기저인지 단일 벡터인지가 첨자 유무로 구분*. $|v\rangle$ 는 단일 벡터, $|v_i\rangle$ 는 기저의 $i$ 번째 원소. 같은 문자라도 첨자 유무로 의미가 다르다.

### 6. 정규 연산자에서의 단순화

**1)** *정규 연산자(normal operator)* — 자신과 에르미트 켤레가 *교환하는* 연산자.

$$H \text{ 정규} \iff H H^\dagger = H^\dagger H$$

**2)** *정규 연산자의 분류*.
- *에르미트 (Hermitian)* — $H = H^\dagger$. 고유값 실수.
- *반에르미트 (anti-Hermitian / skew-Hermitian)* — $X^\dagger = -X$. 고유값 *순허수* (실부 $0$).
- *유니타리 (unitary)* — $U^\dagger U = U U^\dagger = I$. 고유값 *모듈러스 $1$* (단위원 위).

세 종류 모두 정규. 일반 정규 연산자는 *복소 고유값* 을 가질 수 있다.

**3)** *정규 연산자의 핵심 성질 (스펙트럼 정리)*. 정규 연산자의 고유벡터들이 *서로 직교* 하고 (적절히 정규화하면) *정규 직교 기저* 를 이룬다. 즉

$$\langle \lambda_i | \lambda_j \rangle = \delta_{ij}$$

— 통상적인 내적 하에서.

**4)** *바이듀얼 표기의 단순화*. 정규 연산자의 고유 기저 $\{|\lambda_i\rangle\}$ 에 대해, *쌍대 기저가 기저 자체와 (내적적으로) 일치* 한다 —

$$\langle \lambda^i | = \langle \lambda_i |$$

즉 *위 첨자와 아래 첨자가 (이 경우에) 같은 객체* 를 가리킨다. 표기상 헷갈리지 않게 *이 단순화를 사용할 때마다 명시*.

> *약속*. 본 시리즈는 *기본적으로 바이듀얼 표기를 유지* 한다 (위 첨자 ↔ 아래 첨자 구분). 정규 연산자에서 단순화 ($\langle \lambda^i | = \langle \lambda_i |$) 를 사용할 때는 *그 시점에서 명시*. 비정규 연산자가 등장하는 NEGF, 비에르미트 양자역학 등에서는 단순화 *사용 안 함*.

**5)** *비정규 연산자의 스펙트럼*. 비정규지만 *대각화 가능* 한 연산자는 *좌고유벡터와 우고유벡터가 다른* 두 기저로 분해된다.

$$H |R_i\rangle = \lambda_i |R_i\rangle, \qquad \langle L_i | H = \lambda_i \langle L_i |$$

두 기저가 *바이오쏘고날 (biorthogonal)*

$$\langle L_i | R_j \rangle = \delta_{ij}$$

이 경우 쌍대 기저가 *왼쪽 고유벡터*. 본 시리즈의 일반 표기 $\langle v^i |$ 가 이 *왼쪽 고유벡터* 와 자연 대응 — 정규 연산자의 경우 좌·우가 일치해서 단순화될 뿐.

### 7. 연속 기저

연속 스펙트럼을 가지는 연산자 (위치 연산자, 운동량 연산자 등) 에는 *연속 기저* 가 필요하다.

**1)** *연속 기저 표기*. 연속 매개변수 $u$ 로 라벨링된 기저 $\{|u\rangle : u \in \mathbb{R}\}$ 와 쌍대 $\{\langle u^d | : u \in \mathbb{R}\}$. *$d$ 첨자(marker)* 가 쌍대임을 표시.

**2)** *직교성 (델타 함수)*. 이산 델타 $\delta^i_j$ 가 *디랙 델타 함수* 로 일반화.

$$\langle u^d | u' \rangle = \delta(u - u')$$

**3)** *항등 분해 (적분)*. 이산 합이 적분으로 일반화.

$$I = \int du \, |u\rangle \langle u^d|$$

**4)** *변수 표기 — 일반 매개변수 $u$*. 본 시리즈에서 일반 연속 매개변수는 $u$, $u'$ 등으로 표기한다. *위치 변수 $x$ 와 구분* — $x$ 는 위치 기저에 한정한 표기.

**5)** *위치 기저는 자체 쌍대*. 위치 기저 $|x\rangle$ 는 표준적으로 *자체 쌍대 관계* —

$$\langle x^d | = \langle x |$$

이 경우 $d$ 첨자 생략. 직교성은 $\langle x | x' \rangle = \delta(x - x')$ 그대로.

위치 기저가 자체 쌍대인 이유 — 표준 $L^2$ 내적과 위치 연산자가 *에르미트* 이고, 그 (이상화된) 고유 기저 $|x\rangle$ 가 정규 연산자의 고유 기저에 해당해서. 정규 연산자 단순화 (§6 (4)) 의 연속판.

### 8. 스펙트럼 분해

연산자의 *스펙트럼 분해(spectral decomposition)* 가 본 시리즈의 핵심 도구.

**1)** *이산 스펙트럼*. 대각화 가능한 연산자 $H$ (정규 또는 비정규) 에 대해

$$H = \sum_i \lambda_i \, |\lambda_i\rangle \langle \lambda^i|$$

여기 $\{\lambda_i\}$ 는 고유값, $\{|\lambda_i\rangle\}$ 는 우고유벡터, $\{\langle \lambda^i|\}$ 는 좌고유벡터 (= 쌍대 기저).

*확인* — 임의 $|v\rangle = \sum_j v^j |\lambda_j\rangle$ 에 $H$ 작용

$$H |v\rangle = \sum_{i, j} \lambda_i v^j |\lambda_i\rangle \langle \lambda^i | \lambda_j \rangle = \sum_{i, j} \lambda_i v^j \delta^i_j |\lambda_i\rangle = \sum_i \lambda_i v^i |\lambda_i\rangle$$

각 고유 성분이 그 고유값으로 곱해진다.

**2)** *연속 스펙트럼*. 연속 고유값 $\lambda$ 에 대해

$$H = \int d\lambda \, \lambda \, |\lambda\rangle \langle \lambda^d|$$

(혼합 스펙트럼 — 이산 + 연속 — 도 가능하나 본 시리즈에서 자주 등장하지는 않음.)

**3)** *항등 분해 (분광 측도)* — 스펙트럼 분해의 특수경우. $H = I$ 로 잡으면

$$I = \sum_i |v_i\rangle \langle v^i| \quad \text{또는} \quad I = \int du \, |u\rangle \langle u^d|$$

§4 (5) 와 §7 (3) 에서 본 식. 어떤 기저에서든 성립.

**4)** *정규 연산자의 특수경우*. 정규 연산자에서는 $\langle \lambda^i | = \langle \lambda_i |$ 단순화가 가능 (§6 (4)). 이때 스펙트럼 분해는

$$H = \sum_i \lambda_i \, |\lambda_i\rangle \langle \lambda_i| \quad (\text{정규일 때만})$$

이것이 표준 양자역학 교과서의 형태. 본 시리즈는 *비정규 가능성* 을 항상 의식해 *기본 표기는 $\langle \lambda^i|$* 유지.

### 9. 함수 계산과 지수 사상

스펙트럼 분해의 가장 강력한 응용 — *함수의 작용* 을 *고유값에만 적용* 으로 환원.

**1)** *함수 계산(functional calculus)*. 연산자 $H$ 가 스펙트럼 분해 $H = \sum_i \lambda_i |\lambda_i\rangle \langle \lambda^i|$ 를 가지면, 적절한 함수 $f$ 에 대해

$$f(H) = \sum_i f(\lambda_i) \, |\lambda_i\rangle \langle \lambda^i|$$

*고유값에 함수를 적용하고 나머지 (고유벡터 구조) 는 그대로 유지*.

(증명 — 다항식 $f(z) = z^n$ 에 대해 $H^n$ 을 직접 계산하면 $H^n = \sum_i \lambda_i^n |\lambda_i\rangle \langle \lambda^i|$ (귀납). 일반 함수는 다항식 또는 거듭제곱 급수의 극한.)

**2)** *지수 사상*. $f(z) = e^{tz}$ ($t \in \mathbb{R}$ 또는 $\mathbb{C}$) 의 경우

$$\exp(tH) = \sum_i e^{t \lambda_i} \, |\lambda_i\rangle \langle \lambda^i|$$

— 이것이 리 군 시리즈에서 *가장 자주 사용할* 형태.

**3)** *해석 — 모든 고유 모드에 독립 진화*. 각 고유벡터 방향이 *$e^{t\lambda_i}$ 배율* 로 변한다.
- $\lambda_i$ 실수 — *지수적 증가/감소*
- $\lambda_i$ 순허수 ($\lambda_i = i\omega_i$) — *조화 진동* $e^{it\omega_i}$ (반에르미트 행렬, 즉 리 대수 원소)
- $\lambda_i$ 복소 — 증가/감소 + 진동 (NEGF 의 자기에너지 등)

**4)** *리 군과의 연결*. 리 군의 원소를 *지수 사상* 으로 $g = \exp(tX)$ 로 표현하면 ($X$ 는 리 대수 원소), $X$ 의 스펙트럼 분해

$$X = \sum_i \lambda_i |\lambda_i\rangle \langle \lambda^i|$$

가 그대로 군 원소의 스펙트럼 형태

$$g = \exp(tX) = \sum_i e^{t \lambda_i} |\lambda_i\rangle \langle \lambda^i|$$

를 준다. *리 대수 원소의 스펙트럼 = 리 군 원소의 스펙트럼*. 다른 점은 *고유값에 지수가 씌워진 것뿐*.

**5)** *구체적 예 — $SU(2)$* (§16 본격). $\mathfrak{su}(2)$ 원소 $X = i (a \sigma_x + b \sigma_y + c \sigma_z)$ 의 스펙트럼 분해를 사용해 $\exp(X) \in SU(2)$ 를 명시 형태로 계산. 본 시리즈의 핵심 계산 도구.

### 10. 표기 요약표

본 시리즈 전체에서 사용할 표기를 한 표에 정리한다.

| 객체 | 표기 | 비고 |
|---|---|---|
| 이산 기저 (켓) | $\vert v_i \rangle$ | 아래 첨자 |
| 이산 쌍대 기저 (브라) | $\langle v^i \vert$ | 위 첨자 |
| 이산 쌍대 관계 | $\langle v^i \vert v_j \rangle = \delta^i_j$ | 크로네커 델타 |
| 단일 (비기저) 켓 | $\vert v \rangle$ | 첨자 없음 |
| 단일 브라 | $\langle v \vert$ | 첨자 없음 |
| 연속 기저 (켓) | $\vert u \rangle$ | $u \in \mathbb{R}$ |
| 연속 쌍대 기저 (브라) | $\langle u^d \vert$ | $d$ marker |
| 연속 쌍대 관계 | $\langle u^d \vert u' \rangle = \delta(u - u')$ | 디랙 델타 |
| 위치 기저 (자체 쌍대) | $\vert x \rangle, \langle x \vert$ | $d$ 생략 |
| 항등 분해 (이산) | $I = \sum_i \vert v_i \rangle \langle v^i \vert$ | 분광 분해 특수 |
| 항등 분해 (연속) | $I = \int du \, \vert u \rangle \langle u^d \vert$ | |
| 연산자 스펙트럼 분해 | $H = \sum_i \lambda_i \vert \lambda_i \rangle \langle \lambda^i \vert$ | 좌·우 고유벡터 |
| 정규 연산자 단순화 | $\langle \lambda^i \vert = \langle \lambda_i \vert$ | 명시 사용 시 |
| 함수 계산 | $f(H) = \sum_i f(\lambda_i) \vert \lambda_i \rangle \langle \lambda^i \vert$ | |
| 지수 사상 | $\exp(tH) = \sum_i e^{t\lambda_i} \vert \lambda_i \rangle \langle \lambda^i \vert$ | |

### 11. 이 절을 닫으며

이 절에서 약속한 것.

(1) *벡터 공간과 쌍대* — 다양체 접·코탄젠트 (§0-4) 의 일반화. *바이듀얼* 표기는 켓 ↔ 브라의 쌍대 관계를 명시.

(2) *이산 기저 $|v_i\rangle$ 와 쌍대 $\langle v^i|$* — 위·아래 첨자로 구분. 쌍대 관계 $\langle v^i | v_j \rangle = \delta^i_j$.

(3) *연속 기저 $|u\rangle$ 와 쌍대 $\langle u^d|$* — $d$ marker 로 쌍대 표시. 위치 기저는 자체 쌍대.

(4) *정규 연산자* 에서는 좌·우 고유기저가 일치해 $\langle \lambda^i| = \langle \lambda_i|$ 단순화 가능. *비정규* 일 때는 좌·우 분리 유지.

(5) *스펙트럼 분해* $H = \sum_i \lambda_i |\lambda_i\rangle \langle \lambda^i|$ 이 시리즈 전체의 표준 형태. 함수 계산은 $f(H) = \sum_i f(\lambda_i) |\lambda_i\rangle \langle \lambda^i|$, 지수 사상은 $\exp(tH) = \sum_i e^{t\lambda_i} |\lambda_i\rangle \langle \lambda^i|$.

(6) 리 군의 원소가 *리 대수 원소의 지수* 라는 시각 (§7 이후) 이, 스펙트럼 분해를 통해 *고유값에 지수를 씌운 형태* 로 명시화된다.

이로써 §0 부 사전 준비 (약자 §0-1, 군 §0-2, 다양체 §0-3, 접공간 §0-4, 표기 §0-5) 가 끝났다. 다음 §1 (리 군의 정의) 부터 *리 군 = 매끄러운 다양체 + 매끄러운 군 연산* 의 본격 정의로 진입한다.
