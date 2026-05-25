+++
title = "리 대수 ↔ 1-매개변수 부분군 1:1 대응"
weight = 14
+++

### 1. 이 절의 동기

§6, §7, §8 에서 *예고만* 했던 1:1 대응

$$\{ \text{매끄러운 1-매개변수 부분군 } \gamma : \mathbb{R} \to G \} \overset{1:1}{\longleftrightarrow} \mathfrak{g} = T_e G$$

을 *본격 증명* 한다. 시리즈의 가장 중요한 구조적 결과 — *리 군의 모든 1-매개변수 부분군 정보가 리 대수의 한 원소로 정확히 인코딩*.

증명의 핵심 구조 —
- *정방향* $\Phi : \mathfrak{g} \to \{\text{1-매개변수 부분군}\}$, $X \mapsto \gamma_X(t) := \exp(tX)$
- *역방향* $\Psi : \{\text{1-매개변수 부분군}\} \to \mathfrak{g}$, $\gamma \mapsto \gamma'(0)$

두 사상이 *서로의 역* 임을 보이면 1:1 대응 완성. 이를 *ODE 의 존재·유일성* (Picard–Lindelöf 정리) 이 보장.

이 절은 (i) 두 사상의 정의, (ii) $\Phi$ 가 잘 정의됨 (이미지가 1-매개변수 부분군), (iii) $\Psi \circ \Phi = \text{id}$, (iv) $\Phi \circ \Psi = \text{id}$ — ODE 유일성, (v) 결과의 의미와 활용 — 의 순서.

### 2. 두 사상의 정의

**1)** *정방향 사상 $\Phi$*. 리 대수 원소 $X \in \mathfrak{g}$ 에 대해

$$\Phi(X) := \gamma_X, \qquad \gamma_X(t) := \exp(tX) \in G$$

— *$X$ 의 지수로 정의한 곡선*.

**2)** *역방향 사상 $\Psi$*. 1-매개변수 부분군 $\gamma : \mathbb{R} \to G$ 에 대해

$$\Psi(\gamma) := \gamma'(0) = \left. \frac{d \gamma}{dt} \right|_{t=0} \in T_e G = \mathfrak{g}$$

— *항등원에서의 1차 미분* = *생성자*.

**3)** *증명 목표*. 다음 두 등식.

$$\Psi \circ \Phi = \text{id}_{\mathfrak{g}} \quad \text{(원소 → 곡선 → 원소)}$$
$$\Phi \circ \Psi = \text{id}_{\{\text{1-매개변수}\}} \quad \text{(곡선 → 원소 → 곡선)}$$

전자는 *지수의 미분이 원래 원소* — 직접 계산. 후자는 *생성자로부터 원래 곡선이 복원* — *ODE 유일성*.

### 3. $\Phi$ 가 잘 정의됨 — 이미지가 1-매개변수 부분군

$\Phi(X) = \gamma_X$ 가 *진짜 1-매개변수 부분군* 임을 §5 §2 의 세 조건으로 확인.

**1)** *조건 (i) 매끄러움*. $\gamma_X(t) = \exp(tX) = \sum_{n=0}^\infty (tX)^n / n!$ 가 *멱급수*. 절대 수렴 (§7 §2) 이고 항별 미분 가능 → 매끄러움. ✓

**2)** *조건 (ii) 항등 시작점*.

$$\gamma_X(0) = \exp(0 \cdot X) = \exp(0) = I = e \quad \text{(§7 §3 (1))}$$

✓

**3)** *조건 (iii) 합성 법칙*. $\gamma_X(s) \gamma_X(t) = \exp(sX) \exp(tX)$.

$X$ 가 *자기 자신과 가환* ($[sX, tX] = 0$ — 같은 행렬의 스칼라 배는 가환). 가환 지수 법칙 (§7 §4 (1))

$$\exp(sX) \exp(tX) = \exp(sX + tX) = \exp((s+t) X) = \gamma_X(s+t)$$

✓

**4)** *이미지가 $G$ 안에 머묾*. $X \in \mathfrak{g}$ 이므로 정의에 의해 $\exp(tX) \in G$ for all $t$ (§8 §3 (3)).

→ $\Phi(X) = \gamma_X$ 가 *$G$ 안의 매끄러운 1-매개변수 부분군*. $\Phi$ 가 잘 정의됨.

### 4. $\Psi$ 가 잘 정의됨 — 미분이 리 대수 원소

$\Psi(\gamma) = \gamma'(0)$ 가 *진짜 $T_e G = \mathfrak{g}$ 의 원소* 임을 확인.

**1)** *$\gamma : \mathbb{R} \to G$ 가 매끄럽고 $\gamma(0) = e$*. §0-4 §3 의 접공간 정의에서, *항등원을 지나는 매끄러운 곡선의 항등원에서의 속도 벡터* 는 $T_e G$ 의 원소.

$$\gamma'(0) = (d\gamma)_0 (1) \in T_e G$$

✓

**2)** *행렬군에서 더 명시적*. $\gamma : \mathbb{R} \to G \subseteq M_N(\mathbb{F})$ 라 $\gamma(t)$ 가 행렬. $\gamma'(0)$ 가 행렬, $T_e G$ 의 정의식 (예 — 반대칭, 반에르미트 등) 을 만족 — 정의식의 미분 (§8 §4) 이 정확히 그 결과.

→ $\Psi(\gamma) \in \mathfrak{g}$. $\Psi$ 가 잘 정의됨.

### 5. 첫 번째 합성 — $\Psi \circ \Phi = \text{id}_{\mathfrak{g}}$

원소 $X$ 에서 곡선 $\gamma_X = \exp(tX)$ 로 갔다가 다시 원소로 가는 것이 *원래 $X$* 임을 직접 계산.

**1)** *계산*.

$$\Psi(\Phi(X)) = \Psi(\gamma_X) = \gamma_X'(0) = \left. \frac{d}{dt} \exp(tX) \right|_{t=0}$$

**2)** *지수 미분 (§7 §3 (4))*.

$$\frac{d}{dt} \exp(tX) = X \exp(tX) = \exp(tX) X$$

$t = 0$ 대입

$$\left. \frac{d}{dt} \exp(tX) \right|_{t=0} = X \exp(0) = X \cdot I = X$$

**3)** *결과*.

$$\Psi(\Phi(X)) = X \quad \Leftrightarrow \quad \Psi \circ \Phi = \text{id}_{\mathfrak{g}}$$

— *원소 → 곡선 → 원소가 항등*. ✓

**4)** *해석*. $X$ 의 정보가 *$\gamma_X$ 의 항등원에서의 미분으로 정확히 복원*. *지수와 미분이 서로의 역* — 통상 지수 함수의 $\frac{d}{dt} e^{at}|_{t=0} = a$ 의 일반화.

### 6. 두 번째 합성 — $\Phi \circ \Psi = \text{id}_{\{\text{1-매개변수}\}}$

곡선 $\gamma$ 에서 생성자 $X = \gamma'(0)$ 을 잡고, 다시 *$X$ 로부터 곡선* $\gamma_X = \exp(tX)$ 을 만들면 *원래 $\gamma$* 임을 보인다. *ODE 유일성* 이 핵심.

**1)** *목표*. 임의 1-매개변수 부분군 $\gamma : \mathbb{R} \to G$ 와 $X := \gamma'(0)$ 에 대해

$$\gamma(t) = \exp(tX) \quad \text{for all } t \in \mathbb{R}$$

**2)** *$\gamma$ 가 ODE 를 만족함*. §6 §5 의 결과 재확인. 합성 법칙 $\gamma(s+t) = \gamma(s) \gamma(t)$ 의 $t$ 미분 후 $t = 0$ 대입

$$\gamma'(s) = \gamma(s) \cdot \gamma'(0) = \gamma(s) \cdot X$$

또는 $s = 0$ 대입

$$\gamma'(t) = X \cdot \gamma(t)$$

초기 조건 $\gamma(0) = e = I$.

→ $\gamma$ 는 다음 ODE 의 해 —

$$\boxed{y'(t) = X \cdot y(t), \qquad y(0) = I}$$

**3)** *$\exp(tX)$ 도 같은 ODE 의 해*. §7 §3 (4) 에서 $\frac{d}{dt} \exp(tX) = X \exp(tX)$, 초기 조건 $\exp(0) = I$. → $\exp(tX)$ 도 같은 ODE 의 해.

**4)** *ODE 유일성 (Picard–Lindelöf 정리)*.

> *정리* (Picard–Lindelöf). 매끄러운 ODE $y'(t) = F(y(t), t)$ + 초기 조건 $y(0) = y_0$ 의 *해가 유일* (해당 함수 공간에서).

위 ODE $y'(t) = X y(t)$ 에서 $F(y, t) = X y$ 가 $y$ 에 대해 *선형* (특히 매끄러움). 따라서 *해가 유일*.

→ $\gamma(t) = \exp(tX)$ for all $t$.

**5)** *결과*.

$$\Phi(\Psi(\gamma)) = \Phi(\gamma'(0)) = \gamma_{\gamma'(0)}(t) = \exp(t \gamma'(0)) = \gamma(t)$$

$$\Phi \circ \Psi = \text{id}_{\{\text{1-매개변수}\}}$$

— *곡선 → 원소 → 곡선이 항등*. ✓

**6)** *해석*. *합성 법칙* 이 $\gamma$ 가 *ODE 의 해* 임을 강제하고, *지수가 그 ODE 의 유일 해* 라는 두 사실의 결합이 *복원 가능성* 을 보장. 즉 *생성자 $X$ 하나로 부분군 전체가 복원*.

### 7. 1:1 대응의 결과

**1)** *주 정리*.

> *정리*. 리 군 $G$ 의 *매끄러운 1-매개변수 부분군 전체* 와 *리 대수 $\mathfrak{g}$ 의 원소 전체* 사이에 *자연스러운 1:1 대응* 이 존재 —
>
> $$\Phi : \mathfrak{g} \to \{\text{매끄러운 1-매개변수 부분군}\}, \quad X \mapsto \gamma_X(t) = \exp(tX)$$
>
> $$\Psi : \{\text{매끄러운 1-매개변수 부분군}\} \to \mathfrak{g}, \quad \gamma \mapsto \gamma'(0)$$
>
> $\Psi \circ \Phi = \text{id}$, $\Phi \circ \Psi = \text{id}$.

**2)** *시리즈에서의 의의*. *리 군의 모든 1-매개변수 부분군 정보가 리 대수의 한 원소로 정확히 인코딩*. 무한 차원 객체 (매끄러운 곡선) 가 유한 차원 객체 (벡터) 로 *정확히 환원*. 이것이 *리 군 → 리 대수 환원* 의 첫 단계.

**3)** *지수 사상의 위상*. 위 1:1 대응에서 *지수 사상이 두 방향을 잇는 다리*. 한 방향은 명시적 ($\exp$), 다른 방향은 미분 (1차).

**4)** *전역 vs 국소*. *이 1:1 대응이 곡선 전체와 원소 전체 사이* 임. 그러나 *지수 사상 $\exp : \mathfrak{g} \to G$ 자체* (곡선이 아닌 *한 점* $\exp(X) = \gamma_X(1)$) 는 *전역적 1:1 이 아닐 수 있다* — §7 §6 의 단사·전사 문제. 두 가지를 헷갈리지 않도록.

### 8. 예시 — $SO(2)$ 와 $U(1)$

추상 결과를 *가환 1차원 리 군* 에서 확인.

**1)** *$SO(2)$ 에서*. $\mathfrak{so}(2) = \{ \alpha J : \alpha \in \mathbb{R} \} \cong \mathbb{R}$ — 1차원 (§8 §5 (7)).

1-매개변수 부분군 — $\gamma(t) = R(\alpha t)$, 매개변수 $\alpha \in \mathbb{R}$ (§5 §6 (3)). 매개변수도 $\mathbb{R}$.

대응: $\alpha J \leftrightarrow R(\alpha t)$. 1:1.

**2)** *$U(1)$ 에서*. $\mathfrak{u}(1) = \{ i\alpha : \alpha \in \mathbb{R} \} \cong \mathbb{R}$ — 1차원 (§8 §6 (7)).

1-매개변수 부분군 — $\gamma(t) = e^{i \alpha t}$, $\alpha \in \mathbb{R}$.

대응: $i\alpha \leftrightarrow e^{i\alpha t}$. 1:1.

**3)** *가환 1차원의 경우 — 양쪽 모두 $\mathbb{R}$*. 1-매개변수 부분군의 *전체 집합* 과 리 대수의 *원소 전체* 가 *같은 $\mathbb{R}$* 으로 매개변수화 된다.

이것이 *가환 리 군과 리 대수의 일치* — 가환 연결 리 군에서 *부분군 = 군 자체 (한 원소가 군 전체)*. 비가환에서는 1-매개변수 부분군이 *진정한 부분군*.

### 9. 예시 — $SU(2)$

비가환 리 군에서 확인.

**1)** *$\mathfrak{su}(2)$* — 3차원 실 벡터 공간, 기저 $\{i\sigma_x, i\sigma_y, i\sigma_z\}$. (§8 §7 (6).)

**2)** *세 가지 1-매개변수 부분군 (각 기저 원소로부터)*.

- $X = i\sigma_z$ → $\gamma(t) = \exp(t \cdot i\sigma_z) = \begin{pmatrix} e^{it} & 0 \\ 0 & e^{-it} \end{pmatrix}$ — *$z$-축 (스핀) 회전*
- $X = i\sigma_x$ → $\gamma(t) = \exp(t \cdot i\sigma_x) = \cos(t) I + i \sin(t) \sigma_x = \begin{pmatrix} \cos t & i\sin t \\ i \sin t & \cos t \end{pmatrix}$ — *$x$-축 회전*
- $X = i\sigma_y$ → $\gamma(t) = \exp(t \cdot i\sigma_y) = \begin{pmatrix} \cos t & \sin t \\ -\sin t & \cos t \end{pmatrix}$ — *$y$-축 회전*

(계산 — $\sigma_x^2 = \sigma_y^2 = \sigma_z^2 = I$ 사용한 오일러 공식의 행렬 버전, §7 §4 와 §7 §9.)

**3)** *일반 원소 — 결합*. $X = i(a\sigma_x + b\sigma_y + c\sigma_z) \in \mathfrak{su}(2)$ 에 대해

$$\exp(X) = \cos(\|v\|) I + i \frac{\sin(\|v\|)}{\|v\|} (a\sigma_x + b\sigma_y + c\sigma_z)$$

where $v = (a, b, c)$ 와 $\|v\| = \sqrt{a^2 + b^2 + c^2}$. 

(계산 — $(a\sigma_x + b\sigma_y + c\sigma_z)^2 = (a^2+b^2+c^2)I$ — 파울리 anticommutator $\{\sigma_i, \sigma_j\} = 2\delta_{ij} I$. 따라서 $(iV)^{2k} = (-1)^k \|v\|^{2k} I$ — 오일러 공식.)

**4)** *각 방향마다 다른 1-매개변수 부분군*. $\mathfrak{su}(2)$ 의 $3$차원 원소 공간 → *3-매개변수 가족의 1-매개변수 부분군*. 한 부분군이 *$X$ 의 방향 (벡터 $v$)* 와 *크기 (스칼라 배 $X \to tX$)* 로 매개변수화. 합쳐서 *$\mathbb{R}^3$ 자유도*.

**5)** *비가환의 의미*. 서로 *다른 방향* 의 1-매개변수 부분군은 *서로 가환 안 함*. 예 — $\exp(i\sigma_x)$ 과 $\exp(i\sigma_y)$ 가 가환 안 함 (§7 §4 (3) 의 반례).

각 1-매개변수 부분군 *내부* 는 가환이지만 *서로 다른 부분군 사이* 는 비가환 — 이것이 비가환 리 군의 정확한 모습. *교환자* (§10) 가 이 비가환성을 *무한소* 로 측정.

### 10. 이 1:1 대응이 *준동형* 인가

엄밀히는 $\Phi$ 와 $\Psi$ 가 *집합 사이 1:1* 이지만, 양쪽에 *대수 구조* 가 있어 그 구조도 보존되는가가 의문.

**1)** *$\mathfrak{g}$ 의 구조* — 벡터 공간 (덧셈, 실 스칼라 배).

**2)** *1-매개변수 부분군 집합의 구조* — *재매개화* (시간 늘리기·줄이기) 가 자연스러운 구조. $\gamma(t) \mapsto \gamma(ct)$ 가 다른 1-매개변수 부분군.

**3)** *스칼라 배 보존*. $\Phi(cX)(t) = \exp(tcX) = \exp((ct) X) = \gamma_X(ct)$ — *시간을 $c$ 배로 재매개화한 곡선*. $\Phi$ 가 *스칼라 배를 시간 재매개화로* 보존.

**4)** *덧셈은 보존 안 됨 (일반적으로)*. $\Phi(X+Y)(t) = \exp(t(X+Y))$. 이것이 $\Phi(X)(t) \cdot \Phi(Y)(t) = \exp(tX) \exp(tY)$ 와 같은가? 

— *$X, Y$ 가환일 때만*. 비가환 시 BCH 보정으로 다름 (§7 §4).

**5)** *결과*. $\Phi$ 가 *벡터 공간 구조 일부 (스칼라 배) 만* 보존, *덧셈* 은 가환 시에만. 1-매개변수 부분군의 *덧셈 구조* 는 (가환 시에만) 정의됨.

**6)** *완전한 구조 보존 — 리 괄호 차원*. *덧셈은 보존 안 되지만*, $\mathfrak{g}$ 에 *리 괄호* $[X, Y] = XY - YX$ 를 추가하면 그것이 *군 교환자의 무한소* 로 자연스럽게 보존. *완전한 리 대수 ↔ 리 군 (국소) 대응* 이 §10–§11 의 본격 주제.

### 11. 응용 — 리 군 분석을 리 대수로 환원

1:1 대응의 *실용적 의미*.

**1)** *리 군 원소의 매개변수화*. 항등원 근방의 모든 $g \in G$ 가 $g = \exp(X)$ ($X \in \mathfrak{g}$) 형태. *지수 사상의 국소 일대일성* (§7 §6) 으로 보장. 컴팩트 연결의 경우 *전역적* (§12).

응용 — 군 원소를 *벡터 공간 원소* 로 매개변수화. 적분, 미분, 계산이 *벡터 공간에서* 수행 가능.

**2)** *Haar 측도의 명시적 표현* (예고). 컴팩트 연결 리 군의 Haar 측도가 *리 대수 위 측도 + 야코비*로 표현. 측도 이론을 *벡터 공간 위 측도* (Lebesgue) 로 환원.

**3)** *표현론 도구*. 군 표현 $\rho : G \to GL(V)$ 를 *리 대수 표현* $\rho_* : \mathfrak{g} \to \text{End}(V)$ 로 환원. 무한 차원 매끄러운 함수 공간 위 작용이 *유한 차원 행렬 작용* 으로.

**4)** *물리에서의 활용*. 양자역학의 *대칭 분석* 이 거의 모두 *리 대수* 차원에서 수행 — 각운동량 (생성자), 해밀토니안, 운동량 등 모두 *리 대수 원소*. *생성자의 교환자 관계* 가 양자역학의 핵심 (§10).

### 12. 이 절을 닫으며

이 절에서 점검한 것.

(1) *두 사상의 정의* — $\Phi : X \mapsto \gamma_X = \exp(tX)$, $\Psi : \gamma \mapsto \gamma'(0)$.

(2) *각 사상이 잘 정의됨* — $\Phi$ 의 이미지가 1-매개변수 부분군, $\Psi$ 의 이미지가 $T_e G = \mathfrak{g}$.

(3) *$\Psi \circ \Phi = \text{id}$* — 지수의 미분 $\frac{d}{dt}\exp(tX)|_{t=0} = X$.

(4) *$\Phi \circ \Psi = \text{id}$* — *ODE 유일성* (Picard–Lindelöf). 합성 법칙이 강제하는 ODE $\gamma' = X\gamma$ 의 유일 해가 $\exp(tX)$.

(5) *주 정리* — 매끄러운 1-매개변수 부분군 ↔ 리 대수 원소 1:1 대응. 무한 차원 객체 (곡선) ↔ 유한 차원 객체 (벡터).

(6) *예시 확인* — $SO(2)$, $U(1)$ 가환 1차원, $SU(2)$ 비가환 3차원.

(7) *구조 보존* — 스칼라 배 보존, 덧셈은 가환 시에만. *리 괄호 도입 시 완전한 구조 보존* — §10 본격.

(8) *응용* — 리 군 분석의 리 대수로의 환원. 적분·미분·표현론 모두 벡터 공간 차원으로.

다음 §10 에서 *교환자와 리 괄호* 를 본격 다룬다. *군 교환자 $[g, h] = ghg^{-1}h^{-1}$ 의 무한소 측정 = 리 대수 교환자 $[X, Y] = XY - YX$*. 이로써 §3 §6 의 직관이 *정확한 정의* 가 되고, *리 대수 구조* 가 완성에 한 걸음 다가간다.
