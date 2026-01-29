+++
title = "(a) Derivative"
weight = 4
+++

---

### 1. Gradient

$$
\nabla\varphi
=\frac{\partial\varphi}{\partial u_j}\hat{u}_j,\quad
\nabla'\varphi'
=\frac{\partial\varphi'}{\partial u_j'}\hat{u}_j'
$$

$$
\nabla\varphi
=\nabla'\varphi'
$$

proof)

변환된 기저와 변환 이전의 기저에서 gradient를 비교해 보자. 스칼라는 0차 텐서이므로, 기저에 상관없이 동일하다.

$$
\nabla'\varphi'
=\nabla'\varphi
=\frac{\partial\varphi}{\partial u_i'}\hat{u}_i'
=\frac{\partial\varphi}{\partial u_j}\frac{\partial u_j}{\partial u_i'}\hat{u}_i'
$$

여기에서, $u_j=\langle u_j|u_i'\rangle u_i'$ 이다. 국소적 변화를 선형으로 볼 수 있으므로

$$
\frac{\partial u_j}{\partial u_i'}
=\langle u_j|u_i'\rangle
=\langle u_i'|u_j\rangle^{\dagger}
=\langle u_i'|u_j\rangle
$$

따라서,

$$
\nabla'\varphi'
=\langle u_i'|u_j\rangle\frac{\partial\varphi}{\partial u_j}|u_i'\rangle
=\frac{\partial\varphi}{\partial u_j}|u_i'\rangle\langle u_i'|u_j\rangle
=\frac{\partial\varphi}{\partial u_j}|u_j\rangle
$$

---

**example1)**
$x_3=z$ 에 대하여 +90도 회전 변환된 좌표계에서의 $\partial \varphi'/\partial x_i'$를 구하시오. 단, 스칼라장은 $\varphi=x_1^2+x_2^2+x_3^2$ 로 주어진다.

sol)

$$
\left[\frac{\partial \varphi'}{\partial x_i'}\right]
=\left[\langle x_i'|x_j\rangle \frac{\partial \varphi}{\partial x_j}\right]
=\begin{bmatrix}
   \cos90^\circ & \sin90^\circ & 0 \\
   -\sin90^\circ & \cos90^\circ  & 0 \\
   0            & 0            & 1
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
=\langle x'_i| x_l\rangle\langle x'_j| x_m\rangle\langle x'_k| x_n\rangle\frac{\partial A_{mn}}{\partial x_l}
$$

---

### 2. Divergence

$$
\nabla\cdot\vec{f}
=\partial_i f_i,\quad
\nabla'\cdot\vec{f}'
=\partial_i' f_i'
$$

$$
\nabla\cdot\vec{f}=\nabla'\cdot\vec{f}'
$$

proof)

$$
\nabla'\cdot\vec{f}'
=\partial_i' f_i'
=\langle x'_i| x_m\rangle\langle x'_i| x_n\rangle \partial_m f_n
=\langle x_m| x_i'\rangle\langle x'_i| x_n\rangle \partial_m f_n
$$

$$
=\langle x_m|x_n\rangle \partial_m f_n
=\delta_{mn}\partial_m f_n
=\partial_n f_n
$$

---

### 3. Curl

$$
\nabla\times\vec{f}
=\varepsilon_{ijk}\partial_i f_j\hat{e}_k,\quad
\nabla'\times\vec{f}'
=\varepsilon_{ijk}\partial_i' f_j'\hat{e}_k'
$$

$$
\nabla\times\vec{f}=\nabla'\times\vec{f}'
$$

proof)

$$
[\nabla'\times\vec{f}']_k
=\varepsilon_{ijk}'\partial_i'f_j'
=\langle u_i'|u_m\rangle\langle u_j'|u_n\rangle\langle u_k'|u_p\rangle\varepsilon_{mnp}\langle u_i'|u_m\rangle\langle u_j'|u_n\rangle\partial_mf_n
$$

$$
=\langle u_k'|u_p\rangle\varepsilon_{mnp}\partial_mf_n
=\langle u_k'|u_p\rangle[\nabla\times\vec{f}]_p
$$

curl 연산 결과는 일정한 변환규칙을 만족하므로 텐서이다.
 
---

### 4. 시간 미분

다양한 운동방정식은 모두 시간미분을 포함하고 있다. 예를 들어 속도 $\vec{v}$를 생각해 보면, 위치벡터 $\vec{r}$ 의 시간에 대한 미분으로 주어진다. 변화된 기저에서 속도는 아래와 같이 표현된다.

$$
\vec{v}=\vec{v}'
$$

proof)

$$
\vec{v}'=\frac{d\vec{r}'}{dt}
$$

윗 식을 지수로 표현하면 다음과 같다.

$$
v_i'
=\frac{dr_i'}{dt}
=\langle u_i'|u_j\rangle\frac{dr_j}{dt}
=\langle u_i'|u_j\rangle v_j
$$

여기에서 **속도는 변환법칙을 만족하므로 텐서**이다.


