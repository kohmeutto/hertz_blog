+++
title = "(a) Integration"
weight = 5
+++

---

### 1. 발산정리

$$
d^2\vec{s}=d^3V\nabla
$$

적분 기호를 사용하여 표현하면,

$$
\int_{V'}d^3V\nabla\cdot\vec{f}
=\int_{s'}d^2\vec{s}\cdot\vec{f}
$$

적분 표현을 인덱스 표현으로 전개한다.

$$
\int_{V'}d^3V[\partial_i f_i]
=\int_{s'}d^2s[n_if_i],\quad\text{$n_i$ 은 면에 대한 법선벡터이다.
}
$$

---

**example1)** 임의의 표현 s에 대해, 다음의 식이 성립함을 보여라.

$$
\int_{s}d^2\vec{s}'[\vec{u]}=V\bar{\bar{I}}
$$

sol)

$$
\int_{s}d^2\vec{s}'[\vec{u]}
=\int_{V}d^3V'[\nabla \vec{u}]
=\int_{V}d^3V'\bar{\bar{I}}
=V\bar{\bar{I}}
$$

---

### 2. Stokes 정리

$$
d\vec{l}=d^2\vec{s}\times\nabla
$$

적분 기호를 사용하여 표현하면,

$$
\int_{s'}d^2\vec{s}\cdot[\nabla\times\vec{f}]
=\int_{s'}[d^2\vec{s}\times\nabla]\cdot\vec{f}
=\int_{l'}d\vec{l}\cdot\vec{f}
$$

적분 표현을 인덱스 표현으로 전개한다.

$$
\int_{s'}[d^2\vec{s}\times\nabla]\cdot\vec{f}
=\int_{s'}[d^2\vec{s}\times\nabla]_i f_i
=\int_{s'}d^2s[\varepsilon_{ijk}n_j\partial_k f_i],\quad\text{$n_j$ 은 면에 대한 법선벡터이다.
}
$$

$$
\int_{l'}d\vec{l}\cdot\vec{f}
=\int_{l'}dl_if_i
$$

---

**example1)** Stokes 정리를 사용하여, 다음의 식이 성립함을 보여라.


$$
\int_{l'}d\vec{l}\cdot[\phi\nabla\psi]
=\int_{s'}d^2\vec{s}\cdot[\nabla\phi\times\nabla\psi]
$$

sol1)

$$
\int_{s'}d^2\vec{s}\cdot[\nabla\phi\times\nabla\psi]
=\int_{s'}[d^2\vec{s}\times\nabla\phi]\cdot\nabla\psi
=\int_{l'}d\vec{l}\phi\cdot\nabla\psi
=\int_{l'}d\vec{l}\cdot\phi\nabla\psi
$$

sol2)

$$
\int_{l'}d\vec{l}\cdot[\phi\nabla\psi]
=\int_{s'}(d^2\vec{s}\times\nabla)\cdot[\phi\nabla\psi]
=\int_{s'}d^2\vec{s}\cdot[\nabla\times\phi\nabla\psi]
$$

$$
=\int_{s'}d^2\vec{s}\cdot[\nabla\phi\times\nabla\psi+\phi\nabla\times\nabla\psi]
=\int_{s'}d^2\vec{s}\cdot[\nabla\phi\times\nabla\psi]
$$