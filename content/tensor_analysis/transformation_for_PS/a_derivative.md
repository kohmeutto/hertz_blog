+++
title = "(a) Derivative"
weight = 5
+++

---

- **동일** 매개변수 공간에서의 변화를 다룬다.
- 매개변수 공간은 데카르트 좌표계로 표현한다.

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

여기에서, $u_i'=C_{ij}u_j$ 라고 하면, $u_j=C_{ji}^{-1}u_i'$ 이다.

$$
\frac{\partial u_j}{\partial u_i'}
=C_{ji}^{-1}
$$

따라서,

$$
\nabla'\varphi'
=C_{ji}^{-1}\frac{\partial\varphi}{\partial u_j}\hat{u}_i'
$$

직교 기저로의 변환이라면,

$$
\nabla'\varphi'
=C_{ij}\frac{\partial\varphi}{\partial u_j}\hat{u}_i'
=B_{ji}\frac{\partial\varphi}{\partial u_j}\hat{u}_i'
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

---

**example2)** 임의의 2차 tensor $\bar{\bar{A}}$ 의 변환된 좌표 $x'$에 대한 미분을 구하시오.

sol)

$$
\left[\frac{\partial \bar{\bar{A}}}{\partial x'}\right]_{ijk}
=\frac{\partial A_{jk}'}{\partial x'_i}
=C_{il}C_{jm}C_{kn}\frac{\partial A_{mn}}{\partial x_l}
$$

---

### 2. Divergence




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


