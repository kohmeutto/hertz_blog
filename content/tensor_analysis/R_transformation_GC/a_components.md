+++
title = "(a) Components"
weight = 1
+++

---

### 1. 다른 기저로의 변환: Dirac notation 사용

**(1) 반변성분 ↔ 반변성분**

$$
\bar{u}^i
=\langle\bar{g}^i|g_{j}\rangle u^j
=\frac{\partial\bar{q}^i}{\partial q^j}u^j
$$

$$
u^i
=\langle g^i|\bar{g}_{j}\rangle \bar{u}^j
=\frac{\partial q^i}{\partial \bar{q}^j}\bar{u}^j
$$

proof)

$$
u^j|g_j\rangle
=\bar{u}^i|\bar{g}_{i}\rangle
$$

$$
\implies
\langle\bar{g}^i|u^j|g_j\rangle
=\langle\bar{g}^i|\bar{u}^i|\bar{g}_{i}\rangle
$$

$$
\implies
\bar{u}^i
=\langle\bar{g}^i|g_j\rangle u^j
$$

$$
\langle\bar{g}^i|g_{j}\rangle
=\frac{\partial\bar{q}^i}{\partial\vec{x}}\cdot\frac{\partial\vec{x}}{\partial q^j}
=\frac{\partial\bar{q}^i}{\partial x_k}\frac{\partial x_k}{\partial q^j}
=\frac{\partial\bar{q}^i}{\partial q^j}
$$

**(2) 공변성분 ↔ 공변성분**

$$
\bar{u}_i
=\langle\bar{g}_i|g^{j}\rangle u_j
=\frac{\partial q^j}{\partial \bar{q}^i}u_j
$$

$$
u_i
=\langle g_i|\bar{g}^j\rangle \bar{u}_j
=\frac{\partial \bar{q}^j}{\partial q^i}\bar{u}_j
$$

**(3) 반변성분 ↔ 공변성분**

$$
\bar{u}_i
=\langle\bar{g}_i|g_{j}\rangle u^j
=\frac{\partial q^k}{\partial\bar{q}^i}g_{kj}u^j
=\bar{g}_{ij}\frac{\partial \bar{q}^k}{\partial q^j}u^j
$$

$$
u^i
=\langle g^i|\bar{g}^j\rangle\bar{u}_j
=g^{ik}\frac{\partial \bar{q}^j}{\partial q^k}\bar{u}_j
=\frac{\partial q^i}{\partial\bar{q}^k}\bar{g}^{kj}\bar{u}_j
$$

$$
\bar{u}^i
=\langle\bar{g}^i|g^{j}\rangle u_j
=\frac{\partial \bar{q}^i}{\partial q^k}g^{kj}u_j
$$

$$
u_i
=\langle g_i|\bar{g}_j\rangle\bar{u}^j
=g_{ik}\frac{\partial q^k}{\partial \bar{q}^j}\bar{u}_j
$$

proof1)

$$
\bar{u}_i
=\langle\bar{g}_i|g_{j}\rangle u^j
=\frac{\partial \vec{x}}{\partial \bar{q}^i}\cdot\frac{\partial \vec{x}}{\partial q^j}u^j
=\frac{\partial q^k}{\partial\bar{q}^i}\left(\frac{\partial \vec{x}}{\partial q^k}\cdot\frac{\partial \vec{x}}{\partial q^j}\right)u^j
=\frac{\partial q^k}{\partial\bar{q}^i}g_{kj}u^j
$$

proof2)

$$
\bar{u}_i
=\langle\bar{g}_i|g_{j}\rangle u^j
=\langle\bar{g}_i|g^k\rangle\langle g_k|g_{j}\rangle u^j
=\frac{\partial q^k}{\partial\bar{q}^i}g_{kj}u^j
$$

$$
\bar{u}_i
=\langle\bar{g}_i|g_{j}\rangle u^j
=\langle\bar{g}_i|\bar{g}_k\rangle\langle \bar{g}^k|g_{j}\rangle u^j
=\bar{g}_{ik}\frac{\partial \bar{q}^k}{\partial q^j}u^j
$$

proof3)

$$
\bar{u}_i
=\langle\bar{g}_i | g_{j}\rangle u^j
=\left\langle \frac{\partial g^k}{\partial \bar{q}^i}g_k\middle|g_{j}\right\rangle u^j
=\frac{\partial q^k}{\partial\bar{q}^i}g_{kj}u^j
$$

$$
\bar{u}_i
=\langle\bar{g}_i|g_{j}\rangle u^j
=\left\langle \bar{g}_i\middle|g_{j}\right\rangle u^j
=\bar{g}_{ik}\frac{\partial \bar{q}^k}{\partial q^j}u^j
$$

---