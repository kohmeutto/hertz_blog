+++
title = "(a) Bra"
weight = 3
+++

---

### 1. 유한차원의 내적

**(1) 유클리드 공간**

"$\vec{a}\cdot$" 은 연산자이다. 피 연산자를 요구한다. 이것은 행벡터로 표현된다. 따라서, 행벡터를 의미에 따라, 연산자로 간주할 수 있다.

$$
\vec{a}\cdot:=[a]^T
$$

$$
\vec{a}\cdot\vec{b}=[a]^T[b]
$$

**(2) 힐버트 공간**

$$
\langle a| \text{ 는 } \vec{a}\cdot \text{에 대응한다.}
$$

$$
\langle a|b\rangle \text{ 는 } \vec{a}\cdot\vec{b} \text{ 에 대응한다.}
$$

---

### 2. 유한차원의 항등 연산자

$$
\hat{I} = \sum_i |u_i\rangle \langle u_i|
$$

proof)

$$
|\psi\rangle = \sum_i u_i|u_i\rangle
$$

여기에서, $|u_i\rangle$ 는 단위 기저 벡터이다. 단위 기저 벡터와 내적을 하면,

$$
u_i=\langle u_i|\psi\rangle
$$

$$
|\psi\rangle = \sum_i \langle u_i|\psi\rangle|u_i\rangle
= \sum_i |u_i\rangle \langle u_i|\psi\rangle
$$

따라서,

$$
\hat{I} = \sum_i |u_i\rangle \langle u_i|
$$

---

### 3. 무한차원의 항등 연산자

$$
\hat{I} = \int dx |x\rangle \langle x|
$$

proof)

$$
|\psi\rangle = \int dx \langle x|\psi\rangle |x\rangle 
= \int dx |x\rangle \langle x|\psi\rangle 
$$

따라서,

$$
\hat{I} = \int dx |x\rangle \langle x|
$$

---

### 4. 무한차원의 내적

힐버트 공간에서, 함수 f(x)와 함수 g(x)의 내적을 표현할 때,

$$
\langle f|g\rangle = \int dx  f^{*}(x) g(x)
$$

proof)

$$
\langle f|g\rangle = \langle f|\hat{I}|g\rangle
= \langle f| \left( \int dx |x\rangle \langle x| \right) |g\rangle
= \int dx f^{*}(x) g(x)
$$