+++
title = "(a) Curl"
weight = 3
+++

---

**데카르트 좌표계로 간주하는 매개변수 공간 또는 데카르트 좌표계 실공간**에 대한 curl 이다. 

---

### 1. Curl

$$
\nabla\times\vec{f}
=\frac{\partial}{\partial\vec{u}}\times\vec{f}
=\frac{\partial}{\partial u_i}\hat{u}_i\times f_j\hat{u}_j
=\frac{\partial f_j}{\partial u_i}\hat{u}_i\times\hat{u}_j
=\varepsilon_{ijk}\frac{\partial f_j}{\partial u_i}\hat{u}_k
$$

순환 기호는 인덱스는 하나의 항에 대응된다.

$$
[\nabla\times\vec{f}]_i
=\varepsilon_{ijk}\partial_j f_k
$$

$$
[\nabla\times\vec{f}]_j
=\varepsilon_{jki}\partial_k f_i
=\varepsilon_{ijk}\partial_k f_i
$$

$$
[\nabla\times\vec{f}]_k
=\varepsilon_{kij}\partial_i f_j
=\varepsilon_{ijk}\partial_i f_j
$$

---

### 2. Conjugate curl

$$
\vec{f}\times\nabla
=\hat{u}_if_i\times\frac{\partial}{\partial u_j}\hat{u}_j
=f_i\frac{\partial}{\partial u_j}\hat{u}_i\times\hat{u}_j
=\varepsilon_{ijk}f_i\frac{\partial}{\partial u_j}\hat{u}_k
$$

순환 기호는 인덱스는 하나의 항에 대응된다.

$$
[\vec{f}\times\nabla]_i
=\varepsilon_{ijk}f_j\partial_k
$$

$$
[\vec{f}\times\nabla]_j
=\varepsilon_{jki}f_k\partial_i
=\varepsilon_{ijk}f_k\partial_i
$$

$$
[\vec{f}\times\nabla]_k
=\varepsilon_{ijk}f_i\partial_j
$$

---

### 3. High tensor curl

중복 지수 규칙에 위배하지 않아야 함을 주의한다.

$$
\nabla\times\bar{\bar{A}}
=\frac{\partial}{\partial u_i}\hat{u}_i\times A_{jk}\hat{u}_j\hat{u}_k
=\frac{\partial A_{jk}}{\partial u_i}\hat{u}_i\times\hat{u}_j\hat{u}_k
=\frac{\partial A_{jk}}{\partial u_i}(\hat{u}_i\times\hat{u}_j)\hat{u}_k
=\varepsilon_{ijl}\frac{\partial A_{jk}}{\partial u_i}\hat{u}_l\hat{u}_k
$$

순환 기호는 인덱스는 하나의 항에 대응된다. 그리고 각 항의 인덱스는 순환기호와 인접해야 한다.

$$
[\nabla\times\bar{\bar{A}}]_{lk}
=\varepsilon_{ijl}\partial_i A_{jk}
$$

$$
[\nabla\times\bar{\bar{A}}]_{il}
=\varepsilon_{jki}\partial_j A_{kl}
=\varepsilon_{ijk}\partial_j A_{kl}
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

---

### 4. High tensor conjugate curl

$$
\bar{\bar{A}}\times\nabla
=A_{ij}\hat{u}_i\hat{u}_j\times\frac{\partial}{\partial u_k}\hat{u}_k
=A_{ij}\frac{\partial}{\partial u_k}\hat{u}_i(\hat{u}_j\times\hat{u}_k)
=\varepsilon_{jkl}A_{ij}\frac{\partial}{\partial u_k}\hat{u}_i\hat{u}_l
$$

순환 기호는 인덱스는 하나의 항에 대응된다. 그리고 각 항의 인덱스는 순환기호와 인접해야 한다.

$$
[\bar{\bar{A}}\times\nabla]_{il}
=\varepsilon_{jkl}A_{ij}\partial_k
$$

$$
[\bar{\bar{A}}\times\nabla]_{ij}
=\varepsilon_{kli}A_{jk}\partial_l
=\varepsilon_{ikl}A_{jk}\partial_l
$$

