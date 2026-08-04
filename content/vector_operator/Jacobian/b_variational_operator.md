+++
title = "(b) Variational Operator"
weight = 2
+++

## 1. 두 가지 수학적 표현 체계 (Dual Mathematical Frameworks)

변분연산자 $\delta$는 상태 공간 위에서 정의되는 **선형 방향 미분 연산자(Linear Directional Derivative Operator)**이다. 동일한 수학적 본질을 다루는 두 표현 체계의 기호 및 공간 정의는 다음과 같다.

| 구분 | (1) 고전적 함수형 표현 (Functional Form) | (2) 디랙 브라켓 표현 (Dirac Bra-Ket Form) |
| :--- | :--- | :--- |
| **작용 공간** | 무한차원 함수공간 $\mathcal{V}$ | 힐베르트/상태 공간 $\mathcal{H}$ |
| **독립 좌표** | $x \in \Omega \subset \mathbb{R}^d \quad (\delta x = 0)$ | 고정 기저 $\{|x\rangle\}$의 영역 $\Omega \quad (\delta |x\rangle = \mathbf{0})$ |
| **상태 변수** | 상태/장 함수 $u(x) \in \mathcal{V}$ | 상태 켓(State Ket) $|\mathbf{q}\rangle \in \mathcal{H}$ |
| **미소 섭동** | 임의의 시련함수 $\eta(x) = \delta u(x)$ | 가상 변위 켓(Virtual Displacement Ket) $|\delta \mathbf{q}\rangle$ |
| **선형 연산자 작용** | 선형 변분 연산자 $\delta$ | 선형 변분 연산자 $\hat{\delta}$ |
| **비선형 사상/연산자** | 비선형 범함수/사상 $F(u)$ | 비선형 상태 연산자 $\hat{\mathbf{F}}$ |
| **선형화 결과** | 게토 도함수 $F'[u] \delta u$ | 자코비안 연산자 작용 $\hat{J}(\mathbf{q}) |\delta \mathbf{q}\rangle$ |

---

## 2. 변분연산자 $\delta$ 자체의 고유 성질 (Properties of $\delta$ as a Linear Operator)

변분연산자 $\delta$는 그 자체로 **선형 공간 상에서 정의되는 선형 연산자(Linear Operator)**이다. 이 장에서는 $\delta$가 작용하는 대상의 선형성에 기반한 순수 대수적 성질만을 다룬다.

### 2.1. 엄밀한 정의 및 선형성 (Linearity)

변분연산자 $\delta$는 매개변수 $\epsilon$에 대한 선형 방향 미분으로 정의되며, 중첩의 원리(가법성 및 동차성)를 완벽히 만족한다.

#### (1) 함수형 표현
독립변수 $x$가 고정된 상태($\delta x = 0$)에서, 임의의 두 함수 $u_1, u_2 \in \mathcal{V}$와 스칼라 $c_1, c_2$에 대해:

$$
\delta u(x) \equiv \left. \frac{\partial}{\partial \epsilon} \Big( u(x) + \epsilon \eta(x) \Big) \right\vert_{\epsilon = 0} = \eta(x)
$$

$$
\begin{aligned}
\delta (c_1 u_1 + c_2 u_2) &= \left. \frac{\partial}{\partial \epsilon} \Big( [c_1 u_1 + c_2 u_2] + \epsilon [c_1 \eta_1 + c_2 \eta_2] \Big) \right\vert_{\epsilon = 0} \\[8pt]
&= c_1 \eta_1 + c_2 \eta_2 = c_1 \delta u_1 + c_2 \delta u_2
\end{aligned}
$$

#### (2) 브라켓 표현
상태 공간 $\mathcal{H}$ 상의 상태 켓 $|\mathbf{q}\rangle$과 스칼라 $c_1, c_2$에 대해:

$$
|\delta \mathbf{q}\rangle \equiv \hat{\delta} |\mathbf{q}\rangle = \left. \frac{d}{d\epsilon} \Big( |\mathbf{q}\rangle + \epsilon |\eta_{\mathbf{q}}\rangle \Big) \right\vert_{\epsilon = 0} = |\eta_{\mathbf{q}}\rangle
$$

$$
\hat{\delta} (c_1 |\mathbf{q}_1\rangle + c_2 |\mathbf{q}_2\rangle) = c_1 \hat{\delta} |\mathbf{q}_1\rangle + c_2 \hat{\delta} |\mathbf{q}_2\rangle = c_1 |\delta \mathbf{q}_1\rangle + c_2 |\delta \mathbf{q}_2\rangle
$$

---

### 2.2. 선형 연산자와의 가환성 (Commutativity with Linear Operators)

선형 연산자인 $\delta$는 공간/시간 미분 연산자 $\mathcal{L} \in \left\{ \frac{d}{dx}, \nabla, \frac{\partial}{\partial t} \right\}$ 및 적분 연산자 $\int_\Omega$ 등 **다른 선형 연산자와 자유롭게 순서를 교환(Commute)**할 수 있다.

#### (1) 공간/시간 미분 연산자와의 가환성 ($\delta \mathcal{L} = \mathcal{L} \delta$)

* **함수형 표현:** 편미분 순서 교환 가능성(Clairaut-Schwarz 정리)에 의해 성립한다.
  $$
  \delta \left( \frac{du}{dx} \right) = \left. \frac{\partial}{\partial \epsilon} \left( \frac{d}{dx} [u(x) + \epsilon \eta(x)] \right) \right\vert_{\epsilon = 0} = \frac{d}{dx} \left( \left. \frac{\partial}{\partial \epsilon} [u(x) + \epsilon \eta(x)] \right\vert_{\epsilon = 0} \right) = \frac{d}{dx} (\delta u)
  $$

* **브라켓 표현:** 상태 변수 $\mathbf{q}$에 독립적인 선형 미분 연산자 $\hat{\mathcal{L}}$은 섭동 매개변수 $\epsilon$과 가환이다.
  $$
  \hat{\delta} (\hat{\mathcal{L}} |\mathbf{q}\rangle) = \left. \frac{d}{d\epsilon} \hat{\mathcal{L}} \big( |\mathbf{q}\rangle + \epsilon |\delta \mathbf{q}\rangle \big) \right\vert_{\epsilon = 0} = \hat{\mathcal{L}} \left( \left. \frac{d}{d\epsilon} \big( |\mathbf{q}\rangle + \epsilon |\delta \mathbf{q}\rangle \big) \right\vert_{\epsilon = 0} \right) = \hat{\mathcal{L}} |\delta \mathbf{q}\rangle
  $$

#### (2) 적분 연산자 및 내적과의 가환성

* **함수형 표현:** 적분 영역 $\Omega$가 $\epsilon$에 독립적일 때, 라이프니츠 적분 규칙(Leibniz Integral Rule)에 의해 적분 기호 내부로 진입한다.
  $$
  \delta \left( \int_\Omega u(x) \, dx \right) = \int_\Omega \delta u(x) \, dx
  $$

* **브라켓 표현:** 힐베르트 공간 상의 선형 내적 연산과 가환이다. (단, $\hat{\mathbf{H}}$는 상태에 독립인 선형 에르미트 연산자)
  $$
  \delta \langle \mathbf{q}_1 | \hat{\mathbf{H}} | \mathbf{q}_2 \rangle = \langle \delta \mathbf{q}_1 | \hat{\mathbf{H}} | \mathbf{q}_2 \rangle + \langle \mathbf{q}_1 | \hat{\mathbf{H}} | \delta \mathbf{q}_2 \rangle
  $$

---

## 3. 비선형 대상의 국소 선형화 (Linearization of Nonlinear Mappings)

선형 연산자인 $\delta$를 **비선형 대상 $F(u)$ 또는 비선형 연산자 $\hat{\mathbf{F}}$에 적용**하면, 해당 비선형 시스템을 국소적으로 1차 선형화(Linearization)하는 **게토 미분(Gâteaux Derivative)** 과정이 수행된다.

### 3.1. 게토 미분과 자코비안 연산자 (Gâteaux Derivative & Jacobian)

비선형 사상에 변분연산자 $\delta$를 적용한 결과는 섭동량 $\delta u$ 또는 $|\delta \mathbf{q}\rangle$에 대해 **선형(Linear)**인 형태를 띤다.

#### (1) 함수형 표현
비선형 사상 $F(u)$에 대한 변분 $\delta F(u)$는 1차 선형 미분형식으로 도출된다.

$$
\delta F(u) \equiv \left. \frac{d}{d\epsilon} F(u + \epsilon \delta u) \right\vert_{\epsilon = 0} = \lim_{\epsilon \to 0} \frac{F(u + \epsilon \delta u) - F(u)}{\epsilon} = F'[u] \delta u = \frac{\partial F}{\partial u} \delta u
$$

#### (2) 브라켓 표현
상태 공간 $\mathcal{H}$ 상의 비선형 연산자 $\hat{\mathbf{F}}$에 대한 변분은 **국소 자코비안 연산자 $\hat{J}(\mathbf{q})$가 입력 켓 $|\delta \mathbf{q}\rangle$에 작용하는 선형 사상**으로 직접 도출된다.

$$
|\delta \mathbf{F}\rangle = \delta \Big( \hat{\mathbf{F}}|\mathbf{q}\rangle \Big) \equiv \left. \frac{d}{d\epsilon} \hat{\mathbf{F}} \Big( |\mathbf{q}\rangle + \epsilon |\delta \mathbf{q}\rangle \Big) \right\vert_{\epsilon = 0}
$$

우변의 비선형 항을 Taylor 전개하여 1차 선형화하면:

$$
\hat{\mathbf{F}} \Big( |\mathbf{q}\rangle + \epsilon |\delta \mathbf{q}\rangle \Big) = \hat{\mathbf{F}}|\mathbf{q}\rangle + \epsilon \hat{J}(\mathbf{q}) |\delta \mathbf{q}\rangle + \mathcal{O}(\epsilon^2)
$$

따라서,
$$
|\delta \mathbf{F}\rangle = \hat{J}(\mathbf{q}) |\delta \mathbf{q}\rangle \quad \left( \text{단, } \hat{J}(\mathbf{q}) \equiv \frac{\delta \mathbf{F}}{\delta \mathbf{q}} \right)
$$

---

### 3.2. 비선형 합성 및 연쇄 법칙 (Chain Rule & Product Rule)

비선형 대상의 곱이나 합성 구조에 선형 연산자 $\delta$를 작용시킬 때 적용되는 미분법칙들이다.

#### (1) 곱의 미분법 (Leibniz Rule for Products)
* **함수형 표현:** $u(x) \cdot v(x)$ 곱 연산에 대한 선형화:
  $$
  \delta(u \cdot v) = \left. \frac{\partial}{\partial \epsilon} \Big( [u + \epsilon \eta_u][v + \epsilon \eta_v] \Big) \right\vert_{\epsilon = 0} = (\delta u) v + u (\delta v)
  $$

* **브라켓 표현:** 두 연산자 작용의 내적/결합에 대한 선형화:
  $$
  \begin{aligned}
  |\delta (\hat{\mathbf{A}} \hat{\mathbf{B}} \mathbf{q})\rangle &= \left. \frac{d}{d\epsilon} \left[ \hat{\mathbf{A}}(\mathbf{q} + \epsilon \delta \mathbf{q}) \cdot \hat{\mathbf{B}}(\mathbf{q} + \epsilon \delta \mathbf{q}) \right] \right\vert_{\epsilon = 0} \\[8pt]
  &= \Big( \hat{J}_A(\mathbf{q}) |\delta \mathbf{q}\rangle \Big) \hat{\mathbf{B}}|\mathbf{q}\rangle + \hat{\mathbf{A}}|\mathbf{q}\rangle \Big( \hat{J}_B(\mathbf{q}) |\delta \mathbf{q}\rangle \Big) \\[8pt]
  &= |\delta \mathbf{A}\rangle \hat{\mathbf{B}}|\mathbf{q}\rangle + \hat{\mathbf{A}}|\mathbf{q}\rangle |\delta \mathbf{B}\rangle
  \end{aligned}
  $$

#### (2) 연쇄 법칙 (Chain Rule)
* **함수형 표현:** $u(x)$와 구배 $u'(x)$를 포함하는 비선형 라그랑지안 $F(x, u, u')$에 대해 ($\delta x = 0$):
  $$
  \delta F(x, u, u') = \frac{\partial F}{\partial u} \delta u + \frac{\partial F}{\partial u'} \delta u' = \frac{\partial F}{\partial u} \delta u + \frac{\partial F}{\partial u'} \frac{d}{dx}(\delta u)
  $$

* **브라켓 표현:** 비선형 연산자 $\hat{\mathbf{F}}(\mathbf{q})$를 기저 벡터 $\{|e_i\rangle\}$로 성분 전개한 연쇄 법칙:
  $$
  |\delta \mathbf{F}\rangle = \hat{J}(\mathbf{q}) |\delta \mathbf{q}\rangle = \sum_{i=1}^{m} \left( \sum_{j=1}^{n} \frac{\partial F_i}{\partial q_j} \delta q_j \right) |e_i\rangle
  $$

---

## 4. 최종 정립: 표기법 변환 요약

선형 연산자 $\delta$가 비선형 대상에 작용하여 국소 선형화를 수행할 때, 두 표현 체계 사이의 대응 관계는 다음과 같이 명확히 일치한다.

$$
\begin{array}{rcccl}
\text{함수형 게토 미분} & \quad & \delta F(u) = \dfrac{\partial F}{\partial u} \delta u & \quad & \\[10pt]
& \quad & \Updownarrow & \quad & \text{동일 수학적 본질 (국소 선형화)} \\[10pt]
\text{브라켓 자코비안 작용} & \quad & |\delta \mathbf{F}\rangle = \hat{J}(\mathbf{q}) |\delta \mathbf{q}\rangle & \quad & (\text{단, } \hat{J}(\mathbf{q}) \equiv \dfrac{\delta \mathbf{F}}{\delta \mathbf{q}})
\end{array}
$$