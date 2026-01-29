+++
title = "(a) Basis & Components"
weight = 1
+++

---

아래를 살펴보면, 성분과 기저변환은 **서로 역변환 관계**임을 알 수 있다.

---

### 1. 공변성분 & 반변기저 ↔ 공변성분 & 반변기저

$$
|\bar{g}^i\rangle
=\langle\bar{g}^i|g_{j}\rangle|g^j\rangle
=\frac{\partial\bar{q}^i}{\partial q^j}|g^j\rangle,\quad
\bar{q}_i
=\langle\bar{g}_i|g^{j}\rangle q_j
=\frac{\partial q^j}{\partial \bar{q}^i}q_j
$$

$$
|g^i\rangle
=\langle g^i|\bar{g}_{j}\rangle|\bar{g}^j\rangle
=\frac{\partial q^i}{\partial \bar{q}^j}|\bar{g}^j\rangle,\quad
q_i
=\langle g_i|\bar{g}^{j}\rangle\bar{q}_j
=\frac{\partial \bar{q}^j}{\partial q^i}\bar{q}_j
$$

proof) 기저

$$
|\bar{g}^i\rangle
=\frac{\partial\bar{q}^i}{\partial\vec{x}}
=\frac{\partial\bar{q}^i}{\partial x_j}\hat{e}_j
=\frac{\partial\bar{q}^i}{\partial q^j}\frac{\partial q^j}{\partial x_j}\hat{e}_j
=\frac{\partial\bar{q}^i}{\partial q^j}|g^j\rangle
$$

$$
=\frac{\partial\bar{q}^i}{\partial x^k}\frac{\partial x^k}{\partial q^j}|g^j\rangle
=\langle\bar{g}^i|g_{j}\rangle|g^j\rangle
$$

proof) 성분

$$
q^j|g_j\rangle
=\bar{q}^i|\bar{g}_{i}\rangle
$$

$$
\implies
\langle\bar{g}^i|q^j|g_j\rangle
=\langle\bar{g}^i|\bar{q}^i|\bar{g}_{i}\rangle
$$

$$
\implies
\bar{q}^i
=\langle\bar{g}^i|g_j\rangle q^j
$$

$$
\langle\bar{g}^i|g_{j}\rangle
=\frac{\partial\bar{q}^i}{\partial\vec{x}}\cdot\frac{\partial\vec{x}}{\partial q^j}
=\frac{\partial\bar{q}^i}{\partial x_k}\frac{\partial x_k}{\partial q^j}
=\frac{\partial\bar{q}^i}{\partial q^j}
$$

---

### 2. 반변성분 & 공변기저 ↔ 반변성분 & 공변기저

$$
|\bar{g}_i\rangle
=\langle\bar{g}_i|g^{j}\rangle|g_j\rangle
=\frac{\partial q^j}{\partial \bar{q}^i}|g_j\rangle,\quad
\bar{q}^i
=\langle\bar{g}^i|g_{j}\rangle q^j
=\frac{\partial \bar{q}^i}{\partial q^j}q^j
$$

$$
|g_i\rangle
=\langle g_i|\bar{g}^{j}\rangle|\bar{g}_j\rangle
=\frac{\partial\bar{q}^j}{\partial q^i}|\bar{g}_j\rangle,\quad
q^i
=\langle g^i|\bar{g}_{j}\rangle\bar{q}^j
=\frac{\partial q^i}{\partial \bar{q}^j}\bar{q}^j
$$

---

### 3. 반변성분 & 공변기저 ↔ 공변성분 & 반변기저

$$
|\bar{g}_i\rangle
=\langle\bar{g}_i|g_{j}\rangle|g^j\rangle
=\frac{\partial q^k}{\partial\bar{q}^i}g_{kj}|g^j\rangle
=\bar{g}_{ij}\frac{\partial \bar{q}^k}{\partial q^j}|g^j\rangle
,\quad
\bar{q}^i
=\langle\bar{g}^i|g^{j}\rangle q_j
=\frac{\partial \bar{q}^i}{\partial q^k}g^{kj}q_j
=\bar{g}^{ik}\frac{\partial q^j}{\partial q^k}q_j
$$

$$
|g_i\rangle
=\langle g_i|\bar{g}_j\rangle|\bar{g}^j\rangle
=g_{ik}\frac{\partial q^k}{\partial \bar{q}^j}|\bar{g}^j\rangle
=\frac{\partial\bar{q}^k}{\partial q^i}\bar{g}_{kj}|\bar{g}_j\rangle
,\quad
q^i
=\langle g^i|\bar{g}^j\rangle\bar{q}_j
=g^{ik}\frac{\partial \bar{q}^j}{\partial q^k}\bar{q}_j
=\frac{\partial q^i}{\partial\bar{q}^k}\bar{g}^{kj}\bar{q}_j
$$

$$
|\bar{g}^i\rangle
=\langle\bar{g}^i|g^{j}\rangle|g_j\rangle
=\frac{\partial\bar{q}^i}{\partial q^k}g^{kj}|g_j\rangle
=\bar{g}^{ik}\frac{\partial q^j}{\partial\bar{q}^k}|g_j\rangle
,\quad
\bar{q}_i
=\langle\bar{g}_i|g_{j}\rangle q^j
=\frac{\partial q^k}{\partial\bar{q}^i}g_{kj}q^j
=\bar{g}_{ij}\frac{\partial \bar{q}^k}{\partial q^j}q^j
$$

$$
|g^i\rangle
=\langle g^i|\bar{g}^{j}\rangle|\bar{g}_j\rangle
=g^{ik}\frac{\partial\bar{q}^j}{\partial q^k}|\bar{g}_j\rangle
=\frac{\partial q^i}{\partial \bar{q}^k}\bar{g}^{kj}|\bar{g}_j\rangle
,\quad
q_i
=\langle g_i|\bar{g}_j\rangle\bar{q}^j
=g_{ik}\frac{\partial q^k}{\partial \bar{q}^j}\bar{q}^j
=\frac{\partial \bar{q}^k}{\partial q^i}\bar{g}_{ik}\bar{q}^j
$$

proof1)

$$
\bar{q}_i
=\langle\bar{g}_i|g_{j}\rangle q^j
=\frac{\partial \vec{x}}{\partial \bar{q}^i}\cdot\frac{\partial \vec{x}}{\partial q^j}q^j
=\frac{\partial q^k}{\partial\bar{q}^i}\left(\frac{\partial \vec{x}}{\partial q^k}\cdot\frac{\partial \vec{x}}{\partial q^j}\right)q^j
=\frac{\partial q^k}{\partial\bar{q}^i}g_{kj}q^j
$$

proof2)

$$
\bar{q}_i
=\langle\bar{g}_i|g_{j}\rangle q^j
=\langle\bar{g}_i|g^k\rangle\langle g_k|g_{j}\rangle q^j
=\frac{\partial q^k}{\partial\bar{q}^i}g_{kj}q^j
$$

$$
\bar{q}_i
=\langle\bar{g}_i|g_{j}\rangle q^j
=\langle\bar{g}_i|\bar{g}_k\rangle\langle \bar{g}^k|g_{j}\rangle q^j
=\bar{g}_{ik}\frac{\partial \bar{q}^k}{\partial q^j}q^j
$$

proof3)

$$
\bar{q}_i
=\langle\bar{g}_i | g_{j}\rangle q^j
=\left\langle \frac{\partial g^k}{\partial \bar{q}^i}g_k\middle|g_{j}\right\rangle q^j
=\frac{\partial q^k}{\partial\bar{q}^i}g_{kj}q^j
$$

$$
\bar{q}_i
=\langle\bar{g}_i|g_{j}\rangle q^j
=\left\langle\bar{g}_i\middle|\frac{\partial\bar{q}^k}{\partial q^j}\bar{g}_{k}\right\rangle q^j
=\frac{\partial\bar{q}^k}{\partial q^j}\bar{g}_{ik}q^j
$$

---