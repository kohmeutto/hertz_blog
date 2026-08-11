+++
title = "(b) Variational Operator"
weight = 1
+++

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

