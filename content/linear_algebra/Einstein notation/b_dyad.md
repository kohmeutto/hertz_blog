+++
title = "(b) Dyad"
weight = 3
+++

---

### 1. Dyad 개념

Dyad란 두 벡터의 곱으로 이루어진 2차 tensor를 의미한다. 이때의 곱을 tensor 곱 또는 dyad 라고 한다. 표기법은 아래와 같다.

$$
\vec{a}\otimes\vec{b}
=\vec{a}\vec{b}
=\left[\begin{matrix}
    a_1 \\ a_2 \\ a_3 \\ \vdots
\end{matrix}\right]
\left[\begin{matrix}
    b_1 & b_2 & b_3 & \cdots
\end{matrix}\right]
$$

$$
[\vec{a}\vec{b}]_{ij}
=a_ib_j
$$

---

### 2. 표기법 & 교환법칙이 성립하지 않음

Dyad는 2차 tensor로서 성분과 기저 dyad로 구성된다.

$$
\vec{a}\otimes\vec{b}=a_{i}\hat{u}_{i}\otimes b_{j}\hat{u}_{j}=a_{i}b_{j}\left(\hat{u}_{i}\otimes\hat{u}_{j}\right)=\text{성분}\cdot\text{(기저 dyad)}
$$

$$
[\vec{a}\vec{b}]_{ij}
=a_ib_j
$$

일반적으로 dyad는 교환 법칙이 성립되지 않는다.

$$
\vec{a}\otimes\vec{b}\ne\vec{b}\otimes\vec{a}
$$

---

### 3. 분배법칙과 결합법칙

- 분배법칙

$$
\vec{a}\otimes\left(\vec{b}+\vec{c}\right)=\vec{a}\otimes\vec{b}+\vec{a}\otimes\vec{c}
$$

- 결합법칙

$$
\lambda\vec{a}\otimes\vec{b}=\vec{a}\otimes\left(\lambda\vec{b}\right)=\lambda\left(\vec{a}\otimes\vec{b}\right)
$$

