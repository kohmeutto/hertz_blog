+++
title = "(b) Nonlinear & Linearization"
weight = 2
+++

---

### 1. 위상 공간의 설정

Let $({V}, \Vert{}\cdot\Vert{}_{{V}})$ and $({W}, \Vert{}\cdot\Vert{}_{{W}})$ be real Banach spaces. Let $U \subseteq {V}$ be a non-empty open subset of ${V}$.

- 평가 상태 (State Vector): $u \in U$
- 방향 섭동 (Perturbation Operand): $\delta u \in {V}$
- 매개변수 (Scalar Parameter): $\epsilon \in \mathbb{R} \setminus \{0\}$ (단, $u + \epsilon \delta u \in U$를 만족하도록 충분히 작음)

입력 상태 공간 ${V}$와 출력 공간 ${W}$는 실수체 $\mathbb{R}$ 상에서 정의된 완결 노름 공간(Complete Normed Vector Space)으로, 공간 내 임의의 코시 수열(Cauchy sequence)이 공간 내부의 원소로 수렴함이 보장된다. 또한 평가 상태 $u$가 속한 영역 $U \subseteq {V}$는 개집합(Open Set)이므로 $u$를 중심점으로 하는 개구(Open Ball)가 $U$ 내부에 존재하여, 임의 방향의 섭동(Perturbation)에 대해 국소 미분 가능성을 보장한다.

---

### 2. 비선형 연산자의 분류 체계

비선형 사상 ${F}: U \to {W}$를 구조적 특성에 따라 다음과 같이 정밀하게 분류한다.

**1) 일반 비선형 연산자 (General Nonlinear Operator)**

임의의 $u_1, u_2 \in U$ 및 $\alpha, \beta \in \mathbb{R}$ ($\alpha u_1 + \beta u_2 \in U$)에 대해 가산성과 제차성을 보장하지 않는 사상.

$$
{F}(c_1 u_1 + c_2 u_2) \neq c_1 {F}(u_1) + c_2 {F}(u_2)
$$

$$
\hat{{F}}\left[c_1 |u_1\rangle + c_2 |u_2\rangle\right] \neq
c_1\hat{{F}}|u_1\rangle + c_2 \hat{{F}}|u_2\rangle
$$

**2) 준선형 연산자 (Quasi-Linear Operator)**

상태 $u \in U$에 의존하는 유계 선형 연산자 사상 ${A}: U \to {L}({V}, {W})$가 존재하여, $u$에 대해 다음과 같이 분해 표현되는 연산자.

$$
{F}(u) \equiv {A}(u)[u]
$$

$$
\hat{{F}}\vert{}u\rangle \equiv \hat{{A}}_u\vert{}u\rangle
$$

**3) 반선형 연산자 (Semi-Linear Operator)**

고정된 선형 연산자 $L \in {L}({V}, {W})$와 상태에 비선형적으로 의존하는 미분가능한 사상 $N: U \to {W}$ 의 합으로 구성되는 연산자.

$$
{F}(u) \equiv L[u] + N(u)
$$

$$
\hat{{F}}\vert{}u\rangle \equiv \hat{L}\vert{}u\rangle + \hat{N}\vert{}u\rangle
$$

---

### 3. 준선형 연산자의 국소 선형화 전개 (Zero-Skip Derivation)

준선형 연산자 $F(u) = {A}(u)[u]$의 상태 $u \in U$에서의 게토 변분 $\delta F(u; \delta u)$ 및 국소 자코비안 연산자 $J_u \in {L}({V}, {W})$는 다음과 같다.

proof)

(1) 게토 변분의 공리적 정의 적용

1차원 매개변수 $\epsilon \to 0$에 대한 미분계수의 정의식에서 출발한다.

$$
\delta F(u; \delta u) \equiv \lim_{\epsilon \to 0} \frac{F(u + \epsilon \delta u) - F(u)}{\epsilon}
$$

$$
\delta \hat{F}(\vert{}u\rangle; \vert{}\delta u\rangle) \equiv \lim_{\epsilon \to 0} \frac{\hat{F}\vert{}u + \epsilon \delta u\rangle - \hat{F}\vert{}u\rangle}{\epsilon}
$$

준선형 연산자의 정의 $F(u) = {A}(u)[u]$ 및 $F(u + \epsilon \delta u) = {A}(u + \epsilon \delta u)[u + \epsilon \delta u]$를 분자에 대입한다.

$$
\delta F(u; \delta u) = \lim_{\epsilon \to 0} \frac{{A}(u + \epsilon \delta u)[u + \epsilon \delta u] - {A}(u)[u]}{\epsilon}
$$

$$
\delta \hat{F}(\vert{}u\rangle; \vert{}\delta u\rangle) \equiv
\lim_{\epsilon \to 0} \frac{\hat{A}_{u+\epsilon\delta u}\vert{}u + \epsilon \delta u\rangle - \hat{A}_{u+\epsilon\delta u}\vert{}u\rangle}{\epsilon}
$$

(2) 보정항 삽입을 통한 분자 항등 변형

분자에 보정항 $-{A}(u + \epsilon \delta u)[u] + {A}(u + \epsilon \delta u)[u] = 0$을 항등적으로 삽입한다.

$$
\delta F(u; \delta u) = \lim_{\epsilon \to 0} \frac{{A}(u + \epsilon \delta u)[u + \epsilon \delta u] - {A}(u + \epsilon \delta u)[u] + {A}(u + \epsilon \delta u)[u] - {A}(u)[u]}{\epsilon}
$$

$$
\delta \hat{F} (\vert{}u\rangle; \vert{}\delta u\rangle) = \lim_{\epsilon \to 0} \frac{\hat{A}_{u + \epsilon \delta u}\vert{}u + \epsilon \delta u\rangle - \hat{A}_{u + \epsilon \delta u}\vert{}u\rangle + \hat{A}_{u + \epsilon\delta u}\vert{}u\rangle - \hat{A}_u\vert{}u\rangle}{\epsilon}
$$

(3) 벡터 공간의 가산성 및 연산자 선형성에 따른 항 분리

분자의 첫 번째 묶음 ${A}(u + \epsilon \delta u)[u + \epsilon \delta u] - {A}(u + \epsilon \delta u)[u]$에 연산자 ${A}(u + \epsilon \delta u) \in {L}({V}, {W})$의 우선형성(Right Linearity)을 적용한다.

$$
{A}(u + \epsilon \delta u)[u + \epsilon \delta u] - {A}(u + \epsilon \delta u)[u] = {A}(u + \epsilon \delta u)\big[(u + \epsilon \delta u) - u\big] = {A}(u + \epsilon \delta u)[\epsilon \delta u]
$$

$$
\hat{A}_{u + \epsilon \delta u}\vert{} u + \epsilon \delta u\rangle - \hat{A}_{u + \epsilon \delta u}\vert{}u\rangle = \hat{A}_{u + \epsilon \delta u}\big[\vert{}u + \epsilon \delta u\rangle - \vert{}u\rangle\big] = \hat{A}
_{u + \epsilon \delta u}\vert{}\epsilon \delta u\rangle
$$

이 결과를 분자에 다시 대입한다.

$$
\delta F(u; \delta u) = \lim_{\epsilon \to 0} \frac{{A}(u + \epsilon \delta u)[\epsilon \delta u] + {A}(u + \epsilon \delta u)[u] - {A}(u)[u]}{\epsilon}
$$

$$
\delta \hat{F} (\vert{}u\rangle; \vert{}\delta u\rangle) = \lim_{\epsilon \to 0} \frac{\hat{A}_{u + \epsilon \delta u}\vert{}\epsilon \delta u\rangle + \hat{A}_{u + \epsilon \delta u}\vert{}u\rangle - \hat{A}_u\vert{}u\rangle}{\epsilon}
$$

바나흐 공간 ${W}$의 덧셈 연산에 관한 선형성 및 극한의 가산 공리(Limit Linearity)에 의해 두 분수로 분리한다.

$$
\delta F(u; \delta u) = \lim_{\epsilon \to 0} \left( \frac{{A}(u + \epsilon \delta u)[\epsilon \delta u]}{\epsilon} \right) + \lim_{\epsilon \to 0} \left( \frac{{A}(u + \epsilon \delta u)[u] - {A}(u)[u]}{\epsilon} \right)
$$

$$
\delta \hat{F} (\vert{}u\rangle; \vert{}\delta u\rangle) = \lim_{\epsilon \to 0} \left( \frac{ \hat{A}_{u + \epsilon \delta u}\vert{}\epsilon \delta u\rangle}{\epsilon} \right) + \lim_{\epsilon \to 0} \left( \frac{\hat{A}_{u + \epsilon \delta u}\vert{}u\rangle - \hat{A}_u\vert{}u\rangle}{\epsilon} \right)
$$

(4) 첫번쨰 항의 극한 계산

$$
\delta F(u; \delta u) = {A}(u)[\delta u] + \lim_{\epsilon \to 0} \left( \frac{{A}(u + \epsilon \delta u)[u] - {A}(u)[u]}{\epsilon} \right)
$$

$$
\delta \hat{F} (\vert{}u\rangle; \vert{}\delta u\rangle) = \hat{A}_u\vert{}\delta u\rangle + \lim_{\epsilon \to 0} \left( \frac{\hat{A}_{u + \epsilon \delta u}\vert{}u\rangle - \hat{A}_u\vert{}u\rangle}{\epsilon} \right)
$$

(5) 두번쨰 항의 극한 계산

연산자 사상 ${A}: U \to {L}({V}, {W})$가 $u$에서 프레셰 미분가능하다고 전제한다. 이때 도함수 $D{A}(u)$는 다음 공간의 원소이다.$$D{A}(u) \in {L}\big({V}, {L}({V}, {W})\big)$$따라서 방향 $\delta u \in {V}$에 대한 연산자 사상의 극한은 다음과 같이 유일한 선형 연산자 $D{A}(u)[\delta u] \in {L}({V}, {W})$로 수렴한다.$$\lim_{\epsilon \to 0} \frac{{A}(u + \epsilon \delta u) - {A}(u)}{\epsilon} = D{A}(u)[\delta u]$$이 연산자를 상태 벡터 $u \in {V}$에 작용시킨다.$$\text{Term 2} = \Big( D{A}(u)[\delta u] \Big) [u]$$스타일 B 표기 규칙(3-Tier Notation Standard)에 따라, $D{A}(u)$가 방향 섭동 $\delta u$와 평가 상태 $u$에 2중 선형으로 작용함을 명시하는 텐서 표기로 환원한다.$$\text{Term 2} = D{A}(u)[\delta u, u]$$2.5. 최종 연산자 도출 및 국소 자코비안 확립$\text{Term 1}$과 $\text{Term 2}$를 합성한다.$$\delta F(u; \delta u) = {A}(u)[\delta u] + D{A}(u)[\delta u, u]$$우변의 사상 $\delta u \mapsto {A}(u)[\delta u] + D{A}(u)[\delta u, u]$는 $\delta u$에 대해 대수적 선형성을 만족하며, 위상적으로 유계이다. 따라서 게토 도함수 $dF(u) \in {L}({V}, {W})$가 존재하고 다음이 성립한다.$$dF(u)[\delta u] = {A}(u)[\delta u] + D{A}(u)[\delta u, u]$$이로부터 상태 $u \in U$에서의 국소 접연산자 / 자코비안 연산자 (Tangent / Jacobian Operator) $J_u \in {L}({V}, {W})$를 다음과 같이 완전히 확립한다.$$J_u = {A}(u) + D{A}(u)[\,\cdot\,, u]$$3. 구체적 예시: 비선형 2차 미분 연산자의 완전 선형화이론의 명확성을 위해 다음의 비선형 미분 연산자 $F: C^2(\Omega) \to C^0(\Omega)$에 준선형 연산자 선형화를 적용한다.$$F(u)(x) \equiv u(x) \frac{d^2 u(x)}{dx^2}$$3.1. 준선형 구조 분해상태 $u(x)$에 의존하는 선형 미분 연산자 ${A}(u)$를 다음과 같이 정의한다.$${A}(u)[v](x) \equiv u(x) \frac{d^2 v(x)}{dx^2}$$그러면 원래 연산자는 $F(u)(x) = {A}(u)u$로 완벽하게 표현된다.3.2. 연산자 미분 $D{A}(u)[\delta u]$의 유도상태 $u$의 섭동 $\delta u$에 대한 연산자 ${A}$의 게토 미분을 구한다.$$\begin{aligned} D{A}(u)[\delta u][v](x) &= \lim_{\epsilon \to 0} \frac{{A}(u + \epsilon \delta u)[v](x) - {A}(u)[v](x)}{\epsilon} \\ &= \lim_{\epsilon \to 0} \frac{\big(u(x) + \epsilon \delta u(x)\big) \frac{d^2 v(x)}{dx^2} - u(x) \frac{d^2 v(x)}{dx^2}}{\epsilon} \\ &= \lim_{\epsilon \to 0} \frac{\epsilon \delta u(x) \frac{d^2 v(x)}{dx^2}}{\epsilon} \\ &= \delta u(x) \frac{d^2 v(x)}{dx^2} \end{aligned}$$3.3. 자코비안 연산자 $J_u[\delta u]$의 완전 합성유도된 정리에 따라 $J_u[\delta u] = {A}(u)[\delta u] + D{A}(u)[\delta u, u]$를 계산한다.첫 번째 항 ${A}(u)[\delta u](x)$:$${A}(u)[\delta u](x) = u(x) \frac{d^2 \delta u(x)}{dx^2}$$두 번째 항 $D{A}(u)[\delta u, u](x)$ (즉, $v = u$ 대입):$$D{A}(u)[\delta u, u](x) = D{A}(u)[\delta u][u](x) = \delta u(x) \frac{d^2 u(x)}{dx^2}$$두 항을 합산하여 최종 선형화 연산자 $J_u\delta u$를 얻는다.$$J_u[\delta u](x) = u(x) \frac{d^2 \delta u(x)}{dx^2} + \left( \frac{d^2 u(x)}{dx^2} \right) \delta u(x)$$이는 미적분학의 곱의 미분법 공식과 완전히 일치함을 보여주며, 본 체계가 무한차원 연산자 공간에서 완벽한 논리적 정합성을 가짐을 증명한다.







