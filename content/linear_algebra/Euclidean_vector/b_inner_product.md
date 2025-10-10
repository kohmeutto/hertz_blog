+++
title = "(b) Inner product"
weight = 8
+++

---

### 1. 벡터의 내적

벡터 $\vec{a}$, 벡터 $\vec{b}$의 내적은 다음과 같다.

$$
\vec{a}\cdot\vec{b}
=[a]^T[b]
=\sum_i a_i b_i
$$

---

### 2. Norm

벡터의 크기는 내적을 사용하여 구할 수 있다.

$$
||\vec{a}||=\sqrt{\sum_i a_{i}^2}
$$

---

### 3. Projection

$$
\vec{a}\cdot\vec{b}=||\vec{a}||\cdot||\vec{b}||\cos\theta
$$

proof)

$\vec{a}$와 $\vec{b}$가 만드는 삼각형에 코사인 법칙을 적용하면 다음과 같다.

$$
||\vec{c}||^2=||\vec{a}||^2+||\vec{b}||^2-2||\vec{a}||\cdot||\vec{b}||\cos\theta
$$

$$
||\vec{c}||^2
=\sum_i (a_i-b_i)^2
=\sum_i (a_i^2+b_i^2-2a_ib_i)
=||\vec{a}||^2+||\vec{b}||^2-2\vec{a}\cdot\vec{b}
$$

따라서,

$$
\vec{a}\cdot\vec{b}=||\vec{a}||\cdot||\vec{b}||\cos\theta
$$