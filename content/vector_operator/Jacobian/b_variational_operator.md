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
| **변분 연산자** | 선형 변분 연산자 $\delta$ | 선형 변분 연산자 $\hat{\delta}$ |
| **상태 독립 선형 연산자** | $\mathcal{L}$ (공간/시간 미분 연산자 등) | $\hat{\mathcal{L}}$ (상태 $\mathbf{q}$에 독립인 에르미트 연산자 등) |
| **연산자 교환 성질** | $\delta \Big[ \mathcal{L}[u] \Big] = \mathcal{L}[\delta u]$ | $\hat{\delta} \Big( \hat{\mathcal{L}} |\mathbf{q}\rangle \Big) = \hat{\mathcal{L}} |\delta \mathbf{q}\rangle$ |

---

## 2. 변분연산자 $\delta$의 정의 및 선형성 (Definition & Linearity)

변분연산자 $\delta$는 그 자체로 **선형 공간 상에서 정의되는 선형 연산자(Linear Operator)**이다. 매개변수 $\epsilon$에 대한 방향 미분으로 정의되며, 중첩의 원리(가법성 및 동차성)를 완벽히 만족한다.

### 2.1. 게토 미분을 통한 엄밀한 정의

#### (1) 함수형 표현
독립변수 $x$가 고정된 상태($\delta x = 0$)에서, 함수 $u(x)$에 임의의 미소 변형 함수 $\eta(x)$를 더한 섭동 $u(x) + \epsilon \eta(x)$를 정의할 때, 변분연산자 $\delta$는 다음과 같이 정의된다.

$$
\delta u(x) \equiv \left. \frac{\partial}{\partial \epsilon} \Big[ u(x) + \epsilon \eta(x) \Big] \right\vert_{\epsilon = 0} = \eta(x)
$$

#### (2) 브라켓 표현
상태 공간 $\mathcal{H}$ 상의 상태 켓 $|\mathbf{q}\rangle$에 가상 변위 켓 $|\eta_{\mathbf{q}}\rangle$의 섭동을 가할 때, 변분 연산자 $\hat{\delta}$의 작용은 다음과 같이 정의된다.

$$
|\delta \mathbf{q}\rangle \equiv \hat{\delta} |\mathbf{q}\rangle \equiv \left. \frac{d}{d\epsilon} \Big( |\mathbf{q}\rangle + \epsilon |\eta_{\mathbf{q}}\rangle \Big) \right\vert_{\epsilon = 0} = |\eta_{\mathbf{q}}\rangle
$$

---

### 2.2. 중첩의 원리 및 선형성 증명 (Proof of Linearity)

#### (1) 함수형 표현
임의의 스칼라 $c_1, c_2$와 함수 $u_1, u_2 \in \mathcal{V}$에 대해:

$$
\begin{aligned}
\delta \Big[ c_1 u_1(x) + c_2 u_2(x) \Big] &= \left. \frac{\partial}{\partial \epsilon} \Big( [c_1 u_1(x) + c_2 u_2(x)] + \epsilon [c_1 \eta_1(x) + c_2 \eta_2(x)] \Big) \right\vert_{\epsilon = 0} \\[8pt]
&= \left. \frac{\partial}{\partial \epsilon} \Big( c_1 [u_1(x) + \epsilon \eta_1(x)] + c_2 [u_2(x) + \epsilon \eta_2(x)] \Big) \right\vert_{\epsilon = 0} \\[8pt]
&= c_1 \eta_1(x) + c_2 \eta_2(x) \\[8pt]
&= c_1 \delta u_1(x) + c_2 \delta u_2(x)
\end{aligned}
$$

#### (2) 브라켓 표현
임의의 스칼라 $c_1, c_2$와 상태 켓 $|\mathbf{q}_1\rangle, |\mathbf{q}_2\rangle \in \mathcal{H}$에 대해:

$$
\begin{aligned}
\hat{\delta} \Big( c_1 |\mathbf{q}_1\rangle + c_2 |\mathbf{q}_2\rangle \Big) &= \left. \frac{d}{d\epsilon} \Big( [c_1 |\mathbf{q}_1\rangle + c_2 |\mathbf{q}_2\rangle] + \epsilon [c_1 |\eta_1\rangle + c_2 |\eta_2\rangle] \Big) \right\vert_{\epsilon = 0} \\[8pt]
&= c_1 |\eta_1\rangle + c_2 |\eta_2\rangle \\[8pt]
&= c_1 \hat{\delta} |\mathbf{q}_1\rangle + c_2 \hat{\delta} |\mathbf{q}_2\rangle = c_1 |\delta \mathbf{q}_1\rangle + c_2 |\delta \mathbf{q}_2\rangle
\end{aligned}
$$

---

## 3. 상태 독립적 선형 연산자와의 가환성 (Commutativity)

선형 연산자 $\mathcal{L}$ 및 $\hat{\mathcal{L}}$이 **상태 변수($u$ 또는 $\mathbf{q}$)에 독립적(State-independent)**이라면, 변분 매개변수 $\epsilon$ 관점에서도 상수 연산자로 작용하므로 변분연산자 $\delta$와 자유롭게 순서를 교환(Commute)할 수 있다.

### 3.1. 공간/시간 미분 연산자와의 가환성 ($\delta \mathcal{L} = \mathcal{L} \delta$)

#### (1) 함수형 표현
선형 미분 연산자 $\mathcal{L} \in \left\{ \frac{d}{dx}, \nabla, \frac{\partial}{\partial t} \right\}$와 변분연산자 $\delta$는 클레로-슈바르츠 정리(Clairaut-Schwarz Theorem)에 의해 순서 교환이 가능하다.

$$
\begin{aligned}
\delta \Big[ \mathcal{L}[u](x) \Big] &= \left. \frac{\partial}{\partial \epsilon} \Big( \mathcal{L}\big[ u(x) + \epsilon \eta(x) \big] \Big) \right\vert_{\epsilon = 0} \\[8pt]
&= \left. \frac{\partial}{\partial \epsilon} \Big( \mathcal{L}[u](x) + \epsilon \mathcal{L}[\eta](x) \Big) \right\vert_{\epsilon = 0} \quad (\because \mathcal{L}\text{의 선형성}) \\[8pt]
&= \mathcal{L}[\eta](x) = \mathcal{L}[\delta u](x)
\end{aligned}
$$

* **1차 공간 미분 예시:**
  $$
  \delta \left[ \frac{du}{dx} \right] = \left. \frac{\partial}{\partial \epsilon} \left( \frac{d}{dx} \big[ u(x) + \epsilon \eta(x) \big] \right) \right\vert_{\epsilon = 0} = \frac{d}{dx} \left( \left. \frac{\partial}{\partial \epsilon} \big[ u(x) + \epsilon \eta(x) \big] \right\vert_{\epsilon = 0} \right) = \frac{d}{dx} (\delta u)
  $$

* **구배(Gradient) 연산자 예시:**
  $$
  \delta [\nabla u] = \nabla [\delta u]
  $$

#### (2) 브라켓 표현
상태 변수 $\mathbf{q}$에 독립적인 선형 연산자 $\hat{\mathcal{L}}$에 대해:

$$
\begin{aligned}
\hat{\delta} \Big( \hat{\mathcal{L}} |\mathbf{q}\rangle \Big) &= \left. \frac{d}{d\epsilon} \Big( \hat{\mathcal{L}} \big[ |\mathbf{q}\rangle + \epsilon |\delta \mathbf{q}\rangle \big] \Big) \right\vert_{\epsilon = 0} \\[8pt]
&= \hat{\mathcal{L}} \left( \left. \frac{d}{d\epsilon} \big[ |\mathbf{q}\rangle + \epsilon |\delta \mathbf{q}\rangle \big] \right\vert_{\epsilon = 0} \right) \quad (\because \hat{\mathcal{L}}\text{이 }\mathbf{q} \text{ 및 } \epsilon\text{에 독립}) \\[8pt]
&= \hat{\mathcal{L}} |\delta \mathbf{q}\rangle
\end{aligned}
$$

---

### 3.2. 적분 연산자 및 내적과의 가환성

#### (1) 함수형 표현
적분 영역 $\Omega$가 섭동 매개변수 $\epsilon$에 독립적인 고정 영역일 때, 라이프니츠 적분 규칙(Leibniz Integral Rule)에 의해 변분 기호는 적분 기호 내부로 진입한다.

$$
\delta \left[ \int_\Omega u(x) \, dx \right] = \left. \frac{d}{d\epsilon} \left( \int_\Omega [u(x) + \epsilon \eta(x)] \, dx \right) \right\vert_{\epsilon = 0} = \int_\Omega \left. \frac{\partial}{\partial \epsilon} [u(x) + \epsilon \eta(x)] \right\vert_{\epsilon = 0} dx = \int_\Omega \delta u(x) \, dx
$$

#### (2) 브라켓 표현
상태 변수에 독립인 선형 에르미트 연산자 $\hat{\mathbf{H}}$ ($\hat{\mathbf{H}}^\dagger = \hat{\mathbf{H}}$)에 대해, 내적 연산과의 가환성은 다음과 같다.

$$
\begin{aligned}
\delta \langle \mathbf{q}_1 | \hat{\mathbf{H}} | \mathbf{q}_2 \rangle &= \left. \frac{d}{d\epsilon} \left( \langle \mathbf{q}_1 + \epsilon \delta \mathbf{q}_1 | \hat{\mathbf{H}} | \mathbf{q}_2 + \epsilon \delta \mathbf{q}_2 \rangle \right) \right\vert_{\epsilon = 0} \\[8pt]
&= \langle \delta \mathbf{q}_1 | \hat{\mathbf{H}} | \mathbf{q}_2 \rangle + \langle \mathbf{q}_1 | \hat{\mathbf{H}} | \delta \mathbf{q}_2 \rangle
\end{aligned}
$$

---

## 4. 대수적 변분 규칙 (Algebraic Rules of Variational Operation)

### 4.1. 곱의 미분법 (Leibniz Rule for Product of States)

#### (1) 함수형 표현
두 상태 함수 $u(x), v(x)$의 곱 $u \cdot v$에 대한 변분 전개:

$$
\begin{aligned}
\delta \Big[ u(x) \cdot v(x) \Big] &= \left. \frac{\partial}{\partial \epsilon} \Big( [u(x) + \epsilon \eta_u(x)][v(x) + \epsilon \eta_v(x)] \Big) \right\vert_{\epsilon = 0} \\[8pt]
&= \left. \frac{\partial}{\partial \epsilon} \Big( u(x)v(x) + \epsilon [\eta_u(x) v(x) + u(x) \eta_v(x)] + \epsilon^2 \eta_u(x) \eta_v(x) \Big) \right\vert_{\epsilon = 0} \\[8pt]
&= \eta_u(x) v(x) + u(x) \eta_v(x) = \big(\delta u(x)\big) v(x) + u(x) \big(\delta v(x)\big)
\end{aligned}
$$

#### (2) 브라켓 표현
두 상태 켓의 스칼라 내적 $\langle \mathbf{u} | \mathbf{v}\rangle$에 대한 변분 전개:

$$
\begin{aligned}
\hat{\delta} \langle \mathbf{u} | \mathbf{v}\rangle &= \left. \frac{d}{d\epsilon} \left( \langle \mathbf{u} + \epsilon \delta \mathbf{u} | \mathbf{v} + \epsilon \delta \mathbf{v} \rangle \right) \right\vert_{\epsilon = 0} \\[8pt]
&= \langle \delta \mathbf{u} | \mathbf{v}\rangle + \langle \mathbf{u} | \delta \mathbf{v}\rangle
\end{aligned}
$$

---

### 4.2. 범함수의 변분 및 연쇄 법칙 (Variation of Functionals & Chain Rule)

#### (1) 함수형 표현
독립변수 $x$와 상태 $u(x)$, 및 그 구배 $u'(x) = \frac{du}{dx}$를 인수로 받는 범함수 $F[x, u, u']$에 변분 연산자를 작용할 때, 독립변수는 변하지 않으므로($\delta x = 0$) 다음이 성립한다.

$$
\begin{aligned}
\delta F[x, u, u'] &= \frac{\partial F}{\partial x} \underbrace{\delta x}_{=0} + \frac{\partial F}{\partial u} \delta u + \frac{\partial F}{\partial u'} \delta u' \\[8pt]
&= \frac{\partial F}{\partial u} \delta u + \frac{\partial F}{\partial u'} \frac{d}{dx}(\delta u)
\end{aligned}
$$

#### (2) 브라켓 표현
상태 켓 $|\mathbf{q}\rangle$의 2차 스칼라 범함수 $F[\mathbf{q}] \equiv \langle \mathbf{q} | \hat{\mathbf{H}} | \mathbf{q}\rangle$에 변분 연산자를 작용하면:

$$
\hat{\delta} F[\mathbf{q}] = \langle \delta \mathbf{q} | \hat{\mathbf{H}} | \mathbf{q}\rangle + \langle \mathbf{q} | \hat{\mathbf{H}} | \delta \mathbf{q}\rangle
$$

---

## 5. 최종 정립: 표기법 변환 요약

선형 변분 연산자 $\delta$ 및 $\hat{\delta}$의 고유 대수적 성질은 두 표현 체계에서 다음과 같이 1:1로 정확하게 대응된다.

$$
\begin{array}{rcccl}
\text{선형 미분 가환성} & \quad & \delta \Big[ \mathcal{L}[u] \Big] = \mathcal{L}[\delta u] & \quad \Longleftrightarrow \quad & \hat{\delta} \Big( \hat{\mathcal{L}} |\mathbf{q}\rangle \Big) = \hat{\mathcal{L}} |\delta \mathbf{q}\rangle \\[12pt]
\text{곱의 변분 법칙} & \quad & \delta [u \cdot v] = (\delta u)v + u(\delta v) & \quad \Longleftrightarrow \quad & \hat{\delta} \langle \mathbf{u} | \mathbf{v}\rangle = \langle \delta \mathbf{u} | \mathbf{v}\rangle + \langle \mathbf{u} | \delta \mathbf{v}\rangle
\end{array}
$$