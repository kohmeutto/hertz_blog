+++
title = "(a) Derivative"
weight = 5
+++

---

- **동일** 매개변수 공간에서의 변환을 다룬다.
- 매개변수 공간은 데카르트 좌표계로 표현한다.
- **변환은 다른 단위 직교 기저로의 변환**이다.

---

### 1. Gradient

$$
\nabla\varphi\to\nabla'\varphi'
$$

변환된 기저와 변환 이전의 기저에서 gradient를 비교해 보자. 스칼라는 0차 텐서이므로, 기저에 상관없이 동일하다.

$$
\nabla'\varphi'
=\nabla'\varphi
=\frac{\partial\varphi}{\partial u_i'}\hat{u}_i'
=\frac{\partial\varphi}{\partial u_j}\frac{\partial u_j}{\partial u_i'}\hat{u}_i'
$$

여기에서, $u_j=C_{ji}' u_i'=C_{ij}u_i'$ 이다.

$$
\frac{\partial u_j}{\partial u_i'}
=C_{ij}
$$

따라서,

$$
\nabla'\varphi'
=C_{ij}\frac{\partial\varphi}{\partial u_j}\hat{u}_i'
$$

---

**example1)** $x_3=z$ 에 대하여 90도 회전 변환된 좌표계에서의 $\partial \varphi'/\partial x_i'$를 구하시오. 단, 스칼라장은 $\varphi=x_1^2+x_2^2+x_3^2$ 로 주어진다.

sol)

$$
\left[\frac{\partial \varphi'}{\partial x_i'}\right]
=\left[C_{ij}\frac{\partial \varphi'}{\partial x_j'}\right]
=\begin{bmatrix}
   \cos90^\circ  & \sin90^\circ & 0 \\
   -\sin90^\circ & \cos90^\circ & 0 \\
   0             & 0            & 1
\end{bmatrix}
\begin{bmatrix}
   \cfrac{\partial \varphi}{\partial x_1} \\
   \cfrac{\partial \varphi}{\partial x_2} \\
   \cfrac{\partial \varphi}{\partial x_3}
\end{bmatrix}
=\begin{bmatrix}
   2x_2  \\
   -2x_1 \\
   2x_3
\end{bmatrix}
$$

**example2)** 임의의 2차 tensor $\bar{\bar{A}}$ 의 변환된 좌표 $x'$에 대한 미분을 구하시오.

sol)

$$
\left[\frac{\partial \bar{\bar{A}}}{\partial x'}\right]_{ijk}
=\frac{\partial A_{jk}'}{\partial x'_i}
=C_{il}C_{jm}C_{kn}\frac{\partial A_{mn}}{\partial x_l}
$$

---

### 2. Divergence

$$
\nabla\cdot\vec{f}\to\nabla'\cdot\vec{f}'
$$

변환된 기저와 변환 이전의 기저에서 curl을 비교해 보자.

$$
\nabla'\cdot\vec{f}'
=\partial_i' f_i'
=C_{ki}C_{ki}\partial_i f_i
=\delta_{kk}\partial_i f_i
=\partial_i f_i
$$

divergence는 좌표계에 관계없이 불변량임을 알 수 있다.

---

### 3. Curl

$$
\nabla\times\vec{f}\to\nabla'\times\vec{f}'
$$

변환된 기저와 변환 이전의 기저에서 curl을 비교해 보자.

$$
[\nabla'\times\vec{f}']_k
=\varepsilon_{ijk}\frac{\partial f_j'}{\partial u_i'}
=\varepsilon_{ijk}C_{il}C_{km}\frac{\partial f_m}{\partial u_l}
$$

$$
\implies
\varepsilon_{ijk}C_{il}C_{jm}\frac{\partial f_m}{\partial u_l}\hat{u}_k'
$$

---

### 4. 시간 미분

다양한 운동방정식은 모두 시간미분을 포함하고 있다. 예를 들어 속도 $\vec{v}$를 생각해 보면, 위치벡터 $\vec{r}$ 의 시간에 대한 미분으로 주어진다. 변화된 기저에서 속도는 아래와 같이 표현된다.

$$
\vec{v}'=\frac{d\vec{r}'}{dt}
$$

윗 식을 지수로 표현하면 다음과 같다.

$$
v_i'
=\frac{dr_i'}{dt}
=C_{ij}\frac{dr_j}{dt}
=C_{ij}v_j
$$

여기에서 **속도는 벡터에 대한 변환법칙을 만족**한다.


