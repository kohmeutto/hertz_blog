+++
title = "(a) Curl"
weight = 3
+++

---

(1) **데카르트 좌표계로 간주하는 매개변수 공간 또는 데카르트 좌표계 실공간**에 대한 gradient 이다. 

(2) curl 은 텐서의 차수에 변화를

---

### 1. Curl

$$
\nabla\times\vec{f}
=\frac{\partial}{\partial\vec{u}}\times\vec{f}
=\frac{\partial}{\partial u_i}\hat{u}_i\times f_j\hat{u}_j
=\frac{\partial f_j}{\partial u_i}\hat{u}_i\times\hat{u}_j
=\varepsilon_{ijk}\frac{\partial f_j}{\partial u_i}\hat{u}_k
$$

$$
[\nabla\times\vec{f}]_k
=\varepsilon_{ijk}\partial_i f_j
$$

---

### 2. Conjugate curl (잘못되었다고 생각 함)

$$
\vec{f}\times\nabla
=f_i\hat{u}_i\times\frac{\partial}{\partial u_j}\hat{u}_j
=\frac{\partial f_i}{\partial u_j}\hat{u}_i\times\hat{u}_j
=\varepsilon_{ijk}\frac{\partial f_i}{\partial u_j}\hat{u}_k
$$

---

### 3. High tensor curl

중복 지수 법칙에 위배하지 않아야 함을 주의한다.

$$
\nabla\times\bar{\bar{A}}
=\frac{\partial}{\partial u_i}\hat{u}_i\times A_{jk}\hat{u}_j\hat{u}_k
=\frac{\partial A_{jk}}{\partial u_i}\hat{u}_i\times\hat{u}_j\hat{u}_k
=\frac{\partial A_{jk}}{\partial u_i}(\hat{u}_i\times\hat{u}_j)\hat{u}_k
=\varepsilon_{ijl}\frac{\partial A_{jk}}{\partial u_i}\hat{u}_l\hat{u}_k
$$

$$
[\nabla\times\bar{\bar{A}}]_{lk}
=\varepsilon_{ijl}\partial_i A_{jk}
$$

---

**example1)** $\nabla\times\nabla f=0$ 임을 보여라.

sol)

$$
\nabla\times\nabla f\implies
\varepsilon_{ijk}\partial_j[\nabla f]_k
=\varepsilon_{ijk}\partial_j\partial_k f
$$

전개하면, 순환기호의 특성에 따라, 서로 상쇄된다. 따라서 0이다.