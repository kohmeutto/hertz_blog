+++
title = "(b) Variational Operator I"
weight = 3
+++

---

### 1. 정의: 게토 미분 (Gâteaux Derivative)

변분연산자 $\delta$는 "함수 공간(Function Space) 위에서 작동하는 무한차원 미분연산자"이다. 변분연산자 $\delta$는 매개변수 $\epsilon$에 대한 방향 미분(Directional Derivative)으로 정의된다.

$$
u(x) \to u(x) + \epsilon \eta(x) \quad (\eta(x) \text{는 임의의 미소 변형 함수})
$$

$$
\delta u(x) \equiv \left. \frac{\partial}{\partial \epsilon} (u(x) + \epsilon \eta(x)) \right\vert{}_{\epsilon = 0} = \eta(x)
$$

- 미분 연산자 $d$: 숫자 $3$은 미분 대상(변수)이 아니므로 $\frac{d}{dx}(3) = 0$
- 변분 연산자 $\delta$: 독립변수 $x$는 변분의 대상(함수)이 아니므로 $\delta x = 0$

---

### 2. 선형성 (Linearity)

변분연산자 $\delta$는 선형 연산자(Linear Operator)이다. 임의의 상수 $c_1, c_2$와 함수 $u_1, u_2$에 대해 다음이 성립한다.

$$
\delta (c_1 u_1 + c_2 u_2) = c_1 \delta u_1 + c_2 \delta u_2
$$

---

### 3. 미분연산자와의 가환성 (Commutativity with Differential Operators)

공간/시간 미분 연산자 $\frac{d}{dx}, \nabla, \frac{\partial}{\partial t}$ 등과 변분연산자 $\delta$는 서로 순서를 바꾸어도 결과가 같다. $\delta$는 $\epsilon$에 대한 편미분이고, $\frac{d}{dx}$는 $x$에 대한 편미분이므로 Clairaut-Schwarz 정리(편미분 순서 교환 가능성)에 의해 가환성이 성립한다.


$$
\delta \left( \frac{du}{dx} \right) = \frac{d}{dx} (\delta u)$$$$\delta (\nabla u) = \nabla (\delta u)
$$

---

### 4. 라이프니츠 법칙 / 곱의 미분법 (Leibniz Rule / Product Rule)

두 함수 $u(x)$와 $v(x)$의 곱에 변분연산자를 적용할 때, 일반 미분과 동일하게 곱의 법칙이 성립한다.

$$
\delta (u \cdot v) = (\delta u) v + u (\delta v)
$$

proof) 게토 미분 정의 적용

$$
\delta(u \cdot v) = \left. \frac{\partial}{\partial \epsilon} \Big( [u + \epsilon \eta_u][v + \epsilon \eta_v] \Big) \right\vert{}_{\epsilon = 0}
= \left. \frac{\partial}{\partial \epsilon} \Big( uv + \epsilon(\eta_u v + u \eta_v) + \epsilon^2 \eta_u \eta_v \Big) \right\vert{}_{\epsilon = 0}
$$

$$
= \eta_u v + u \eta_v = (\delta u) v + u (\delta v)
$$

---

### 5. 연쇄 법칙 / 합성함수의 변분 (Chain Rule)

함수 $u(x)$를 인수로 갖는 일반적인 비선형 함수 $F(u)$에 변분연산자 $\delta$를 적용하면 다음과 같이 일반 미분의 연쇄 법칙 형태를 나타낸다.

$$
\delta F(u) = \frac{\partial F}{\partial u} \delta u
$$

마찬가지로 $u$와 $u' = \frac{du}{dx}$를 모두 인수로 갖는 $F(x, u, u')$에 대해서는,

$$
\delta F(x, u(x), u'(x)) = \frac{\partial F}{\partial u} \delta u + \frac{\partial F}{\partial u'} \delta u' = \frac{\partial F}{\partial u} \delta u + \frac{\partial F}{\partial u'} \frac{d}{dx}(\delta u)
$$

$x$는 변하지 않으므로($\delta x = 0$), $x$에 대한 편미분 항 ($\partial F/\partial) x(\delta x)$는 $0$이 되어 나타나지 않는다.

---

### 6. 적분 기호와의 가환성 (Commutativity with Integrals)

변분연산자 $\delta$는 공간 영역 $\Omega$에 대한 적분 기호 $\int_\Omega$와도 순서를 바꿀 수 있다.

$$
\delta \left( \int_\Omega F(u) \, dx \right) = \int_\Omega \delta F(u) \, dx
$$

이 성질 역시 적분 영역 $\Omega$가 $\epsilon$에 독립적(고정)일 때, 적분 기호 내부로 미분을 밀어 넣는 라이프니츠 적분 규칙(Leibniz Integral Rule)에 의해 성립한다.

