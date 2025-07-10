+++
title = "(a) Gradient"
weight = 1
+++

---

### 1. Scalar gradient 

$$
\nabla\varphi
=\frac{\partial \varphi}{\partial\vec{u}}
=\frac{\partial \varphi}{\partial u_i}\hat{u}_i
=\frac{\partial \varphi}{\partial u_1}\hat{u}_1+\frac{\partial \varphi}{\partial u_2}\hat{u}_+\frac{\partial \varphi}{\partial u_3}\hat{u}_3
$$

$$
[\nabla\varphi]_i
=[\nabla]_i\varphi
=\frac{\partial \varphi}{\partial u_i}
$$

---

### 2. Vector Gradient  

$$
\nabla\vec{f}
=\frac{\partial \vec{f}}{\partial\vec{u}}
=\frac{\partial f_j}{\partial u_i}\hat{u}_i\hat{u}_j
$$

$$
[\nabla\vec{f}]_{ij}
=[\nabla]_i\vec{f}_j
=\frac{\partial f_j}{\partial u_i}
$$

전개하면, 다음과 같으며, 2차 텐서임을 알 수 있다.

$$
\begin{align}
\nabla\vec{f}
= & \frac{\partial f_1}{\partial u_1}\hat{u}_1\hat{u}_1 + \frac{\partial f_1}{\partial u_2}\hat{u}_2\hat{u}_1 + \frac{\partial f_1}{\partial u_3}\hat{u}_3\hat{u}_1 \\
  & \frac{\partial f_2}{\partial u_1}\hat{u}_1\hat{u}_2 + \frac{\partial f_2}{\partial u_2}\hat{u}_2\hat{u}_2 + \frac{\partial f_2}{\partial u_3}\hat{u}_3\hat{u}_2 \\
  & \frac{\partial f_3}{\partial u_1}\hat{u}_1\hat{u}_3 + \frac{\partial f_3}{\partial u_2}\hat{u}_2\hat{u}_3 + \frac{\partial f_3}{\partial u_3}\hat{u}_3\hat{u}_3
\end{align}
$$

---

### 3. Conjugate vector gradient

$$
\vec{f}\nabla
= f_i\frac{\partial}{\partial u_j}\hat{u}_i\hat{u}_j
$$

---

### 4. Vector gradient & Kronecker delta

$$
\nabla\vec{u}
=\frac{\partial \vec{u}}{\partial \vec{u}}
=\frac{\partial u_i}{\partial u_j}\hat{u}_i\hat{u}_j
=[\delta_{ij}]
=\bar{\bar{I}}
$$

$$
[\nabla\vec{u}]_{ij}
=\partial_i u_j
=\bar{\bar{I}}
$$

---

### 5. High tensor gradient

2차 텐서에서,

$$
\nabla\bar{\bar{A}}
=\frac{\partial \bar{\bar{A}}}{\partial \vec{u}}
=\frac{\partial A_{jk}}{\partial u_i}\hat{u}_i\hat{u}_j\hat{u}_k
$$

$$
[\nabla\bar{\bar{A}}]_{ijk}
=[\nabla]_i[\bar{\bar{A}}]_{jk}
=\frac{\partial A_{jk}}{\partial u_i}
$$

4차 텐서에서,

$$
\nabla\stackrel{4}{A}
=\frac{\partial A_{jklm}}{\partial u_i}\hat{u}_i\hat{u}_j\hat{u}_k\hat{u}_l\hat{u}_m
$$

$$
[\nabla\stackrel{4}{A}]_{ijklm}
[\nabla]_i[\stackrel{4}{A}]_{jklm}
=\frac{\partial A_{jklm}}{\partial u_i}\hat{u}_i\hat{u}_j\hat{u}_k\hat{u}_l\hat{u}_m
$$