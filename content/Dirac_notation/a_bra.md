+++
title = "(a) Bra"
weight = 3
+++

---

### 1. Bra

**(1) 유클리드 공간**

"$\vec{a}\cdot$" 은 연산자이다. 피 연산자를 요구한다. 이것은 행벡터로 표현된다. 따라서, 행벡터를 의미에 따라, 연산자로 간주할 수 있다.

$$
\vec{a}\cdot:=\vec{a}^T:=[a]^T
$$

$$
\vec{a}\cdot\vec{b}=\vec{a}^T\vec{b}
=[a]^T[b]
$$

**(2) 힐버트 공간**

$$
\langle a| \text{ 는 } \vec{a}\cdot \text{에 대응한다.}
$$

$$
\langle a|b\rangle \text{ 는 } \vec{a}\cdot\vec{b} \text{ 에 대응한다.}
$$

유클리드 공간의 $\vec{a}\cdot:=\vec{a}^T$ 인 것처럼 복수수 까지 확장된 힐버트 공간에서는,

$$
\langle a|:=|a\rangle^{\ast T}:=|a \rangle^\dagger 
$$

---

### 2. 항등 연산자

**(1) 유한차원**

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

**(2) 무한차원**

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

### 3. 함수의 내적

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

---

### 4. 내적 연산의 특성

힐버트 공간 상태 벡터를 $|\psi_n\rangle$ 라 하고, $a_n$ 를 임의의 복소수 스칼라($a_n \in \mathbf{C}$)라고 하자. 아래와 같이 표현할 수 있다.

**(1) Ket의 스칼라 곱**

$$
\langle a\psi| = a^\ast \langle\psi|
$$

**(2) 내적 연산1**

$$
\operatorname{In}\{|\psi_1\rangle,|a_2\psi_2\rangle+|a_3\psi_3\rangle\}
=a_2\langle \psi_1|\psi_2\rangle+a_3\langle \psi_1|\psi_3\rangle
$$

주의사항 (잘못된 표기)

$$
a_2|\psi_2\rangle+a_3|\psi_3\rangle\ne|a_2\psi_2+a_3\psi_3\rangle
$$

**(3) 내적 연산2**

$$
\operatorname{In}\{|a_1\psi_1\rangle,|\psi_2\rangle+|\psi_3\rangle\}
=a_1^\ast\langle \psi_1|\psi_2\rangle+a_1^\ast\langle \psi_1|\psi_3\rangle
$$

**(4) Dagger (complex conjugate)**

$$
\langle \psi_1|\psi_2\rangle^\dagger
=\langle \psi_2|\psi_1\rangle
$$