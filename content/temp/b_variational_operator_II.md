+++
title = "(b) Variational Operator II"
weight = 3
+++

---

### 1. 세미콜론 ";" 과 콤마 "," 구분

변분 기호 내부에서의 표기 규칙변분 기호 $\delta F$ (또는 $\delta \hat{F}$) 내에서는 고정된 동작점 $u$와 입력되는 변분 방향 $\delta u$의 지위가 완전히 다르므로 반드시 세미콜론 ";" 을 사용한다.

(1) 1계 변분:

$$
\delta F(\vert{}u\rangle \,;\, \vert{}\delta u\rangle)
$$

- 좌측 $\vert{}u\rangle$: 미분이 수행되는 기준 동작점 (Evaluation Point)
- 우측 $\vert{}\delta u\rangle$: 입력되는 변분 방향 (Perturbation Direction)

(2) 2계 변분:

$$
\delta^2 F(\vert{}u\rangle \,;\, \vert{}\delta u_1\rangle ,\, \vert{}\delta u_2\rangle)
$$

- 좌측: 기준 동작점 $\vert{}u\rangle$
- 우측: 2개의 독립된 변분 방향 인자를 콤마 "," 로 나열

---

### 2. 표기

| 수학적 개념 | 함수해석학<br>(Functional Analysis) | 미분학 / 다변수해석<br>(Differential Calculus) | 공학 / 수치해석 / 최적화<br>(Engineering / Optimization) | 디랙 표기법<br>(Dirac Notation) |
| :--- | :--- | :--- | :--- | :--- |
| **기준 상태 (Point)** | $u \in \mathcal{V}$ | $u \in \mathcal{V}$ | $u \in \mathcal{V}$ | $\vert{}u\rangle \in \mathcal{V}$ |
| **변분/섭동 방향** | $\delta u \in \mathcal{V}$ | $h \text{ 또는 } \Delta u$ | $\delta u \text{ 또는 } du$ | $\vert{}\delta u\rangle \in \mathcal{V}$ |
| **1계 미분 연산자** | **$dF(u)$**<br>(게토/프레셰 미분) | **$DF(u)$**<br>(프레셰 도함수) | **$J_u$**<br>(자코비안 연산자) | **$\hat{\mathcal{J}}_u$**<br>(자코비안 헷 연산자) |
| **1계 변분 작용식** | $dF(u)[\delta u]$ | $DF(u)[h]$ | $J_u [\delta u]$ | $\hat{\mathcal{J}}_u \vert{} \delta u\rangle$ |
| **스칼라 범함수 <br> 1계 변분** | $dF(u)[\delta u]$ | $DF(u)[h]$ | $\nabla F(u) \cdot \delta u$ | $\langle \delta F_u \mid \delta u \rangle$ |
| **2계 미분 연산자** | **$d^2 F(u)$**<br>(2계 게토/프레셰 미분) | **$D^2 F(u)$**<br>(2차 프레셰 도함수) | **$H_u$**<br>(헤시안 연산자) | **$\hat{\mathcal{H}}_u$**<br>(헤시안 헷 연산자) |
| **2계 변분 작용식** | $d^2 F(u)[\delta u_1, \delta u_2]$ | $D^2 F(u)[h_1, h_2]$ | $H_u [\delta u_1, \delta u_2]$ | $\hat{\mathcal{H}}_u \vert{} \delta u_1, \delta u_2\rangle$ |
| **스칼라 범함수 <br> 2계 변분** | $d^2 F(u)[\delta u_1, \delta u_2]$ | $D^2 F(u)[h_1, h_2]$ | $\delta u_1^T H_u \delta u_2$ | $\langle \delta u_1 \mid \hat{\mathcal{H}}_u \mid \delta u_2 \rangle$ |

---









### 2. 1계 변분 (1st Variation) $\to$ 선형 연산자 (Linear Operator)

동작점 상태를 Ket $\vert{}u\rangle \in \mathcal{V}$로 두고, 단일 방향 섭동을 $\vert{}\delta u\rangle \in \mathcal{V}$라 한다.


**1) 연산자 사상인 경우 ($\hat{F}: \mathcal{V} \to \mathcal{W}$)**

1계 게토 변분은 국소 자코비안 연산자 $\hat{\mathcal{J}}_u \in \mathcal{L}(\mathcal{V}, \mathcal{W})$가 섭동 Ket $\vert{}\delta u\rangle$에 선형으로 작용하는 형태가 된다.

$$
\delta \hat{F}(\vert{}u\rangle; \vert{}\delta u\rangle) = \hat{\mathcal{J}}_u \vert{}\delta u\rangle
$$


1차 선형성 (Linearity):

$$\hat{\mathcal{J}}_u \big( c_1 \vert{}\delta u_1\rangle + c_2 \vert{}\delta u_2\rangle \big) = c_1 \hat{\mathcal{J}}_u \vert{}\delta u_1\rangle + c_2 \hat{\mathcal{J}}_u \vert{}\delta u_2\rangle$$



---

### 1. 변분연산자 $\delta$의 게토 미분 정의

변분연산자 $\delta$는 "함수 공간(Function Space) 위에서 작동하는 무한차원 미분연산자"이다.

- 미분 연산자 $d$: 숫자 $3$은 미분 대상(변수)이 아니므로 $\frac{d}{dx}(3) = 0$
- 변분 연산자 $\delta$: 독립변수 $x$는 변분의 대상(함수)이 아니므로 $\delta x = 0$

**1) 함수형 표현**

독립변수 $x$가 고정된 상태($\delta x = 0$)에서, 함수 $u(x)$에 임의의 미소 변형 함수 $\eta(x)$의 섭동을 가할 때 변분연산자 $\delta$의 작용:

$$
\delta u(x) \equiv \left. \frac{\partial}{\partial \epsilon} \Big[ u(x) + \epsilon \eta(x) \Big] \right\vert_{\epsilon = 0} = \eta(x)
$$

**2) 브라켓 표현**

상태 공간 $\mathcal{H}$ 상의 상태 켓 $|{q}\rangle$에 가상 변위 켓 $|\eta_{{q}}\rangle$의 섭동을 가할 때, 변분 연산자 $\hat{\delta}$의 작용:

$$
|\delta {q}\rangle \equiv \hat{\delta} |{q}\rangle \equiv \left. \frac{d}{d\epsilon} \Big( |{q}\rangle + \epsilon |\eta_{{q}}\rangle \Big) \right\vert_{\epsilon = 0} = |\eta_{{q}}\rangle
$$

---

### 2. 변분 연산자 자체의 선형성 (Derivation Property)

변분 연산자 $\delta$는 상태 공간 상의 섭동에 대해 항상 선형 중첩을 만족한다.

$$
\delta \Big[ c_1 u_1(x) + c_2 u_2(x) \Big] = c_1 \delta u_1(x) + c_2 \delta u_2(x)
$$

$$
\hat{\delta} \Big( c_1 |{q}_1\rangle + c_2 |{q}_2\rangle \Big) = c_1 \hat{\delta} |{q}_1\rangle + c_2 \hat{\delta} |{q}_2\rangle
$$

---

### 3. 라이프니츠 법칙 기반의 보편적 변분 전개 (Leibniz Engine)

모든 변분 연산은 대상의 구조와 무관하게 **라이프니츠 곱의 미분법(Product Rule)과 게토 연쇄 법칙(Chain Rule)** 을 통해 전개된다.

$$
\delta \Big[ f(u) \cdot g(u) \Big] = \big(\delta f(u)\big) g(u) + f(u) \big(\delta g(u)\big)
$$

$$
\hat{\delta} \langle {u} | {v}\rangle = \langle \delta {u} | {v}\rangle + \langle {u} | \delta {v}\rangle
$$

---

### 4. 상태 독립 좌표 연산자와의 가환성 ($\delta \mathcal{L}_0 = \mathcal{L}_0 \delta$)

연산자 $\mathcal{L}_0$가 상태 변수 $u$에 전혀 의존하지 않고 독립 좌표 $x$에만 작용하는 연산자(예: $\frac{d}{dx}, \nabla, \int dx$)일 때, $\delta$와의 가환성이 성립한다.

**1) 클레로-슈바르츠 정리 기반 증명 (함수형)**

$\delta$는 섭동 매개변수 $\epsilon$에 대한 미분이분 공간 좌표 $x$의 미분 연산자 $\mathcal{L}_0$와 독립이다.

$$
\delta \Big[ \mathcal{L}_0[u](x) \Big] = \mathcal{L}_0 [\delta u](x)
$$

proof)

$$
\delta \Big[ \mathcal{L}_0[u](x) \Big] = \left. \frac{\partial}{\partial \epsilon} \Big( \mathcal{L}_0 \big[ u(x) + \epsilon \eta(x) \big] \Big) \right\vert_{\epsilon = 0}
$$

$$
= \mathcal{L}_0 \left( \left. \frac{\partial}{\partial \epsilon} \big[ u(x) + \epsilon \eta(x) \big] \right\vert_{\epsilon = 0} \right) \quad (\because \epsilon\text{과 } x\text{의 독립성에 의한 미분순서 교환})
$$

$$
= \mathcal{L}_0 [\delta u](x)
$$

**2) 브라켓 표현**

상태 변수 ${q}$에 독립인 연산자 $\hat{\mathcal{L}}_0$에 대해:

$$
\hat{\delta} \Big( \hat{\mathcal{L}}_0 |{q}\rangle \Big) = \hat{\mathcal{L}}_0 \Big( \hat{\delta} |{q}\rangle \Big) = \hat{\mathcal{L}}_0 |\delta {q}\rangle
$$

---

