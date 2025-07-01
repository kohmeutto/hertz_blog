+++
title = "(a) Divergence"
weight = 2
+++

---

- 매개변수공간에 대한 divergence 이다. 
- 매개변수 공간을 데카르트 좌표계로 표현하고 다룬다.

---

### 1. Divergence

$$
\nabla\cdot\vec{f}
=\frac{\partial}{\partial\vec{u}}\cdot\vec{f}
=\frac{\partial}{\partial u_i}\hat{u}_i\cdot f_j\hat{u}_j
=\frac{\partial f_j}{\partial u_i}\hat{u}_i\cdot \hat{u}_j
=\frac{\partial f_j}{\partial u_j}
=\frac{\partial f_1}{\partial u_1}+\frac{\partial f_2}{\partial u_2}+\frac{\partial f_3}{\partial u_3}
$$

$$
\nabla\cdot\vec{f}
=[\nabla]_j[\vec{f}]_j
=\frac{\partial f_j}{\partial u_j}
$$

---

**example1)** 벡터 $\vec{u}=u_1\hat{u}_1+u_2\hat{u}_2+u_3\hat{u}_3$ 에 대한 발산을 구하여라.

sol)

$$
\nabla\cdot\vec{u}
=\frac{\partial u_j}{\partial u_j}
=3
$$

---

### 2. 2차 텐서의 divergence

$$
\nabla\cdot\bar{\bar{A}}
=\frac{\partial}{\partial u_i}\hat{u}_i\cdot A_{jk}\hat{u}_j\hat{u}_k
=\frac{\partial A_{jk}}{\partial u_i}(\hat{u}_i\cdot\hat{u}_j)\hat{u}_k
=\frac{\partial A_{jk}}{\partial u_i}\delta_{ij}\hat{u}_k
=\frac{\partial A_{ik}}{\partial u_i}\hat{u}_k
$$

$$
[\nabla\cdot\bar{\bar{A}}]_j
=[\nabla]_i\bar{\bar{A}}_{ij}
=\frac{\partial A_{ij}}{\partial u_i}
$$


---

### 3. Laplacian operator

$$
\nabla^2
=\nabla\cdot\nabla
=\frac{\partial}{\partial u_i}\hat{u}_i\cdot\frac{\partial}{\partial u_j}\hat{u}_j
=\frac{\partial^2}{\partial u_i \partial u_j}(\hat{u}_i\cdot\hat{u}_j)
=\frac{\partial^2}{\partial u_i \partial u_j}\delta_{ij}
=\frac{\partial^2}{\partial u_i \partial u_i}
=\frac{\partial^2}{\partial u_i^2}
$$

$$
\nabla^2
=[\nabla]_i[\nabla]_i
=\frac{\partial^2}{\partial u_i^2}
$$

---