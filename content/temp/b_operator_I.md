+++
title = "(b) Operator I"
weight = 2.5
+++

---

### 1. 항등 연산자

**(1) 이산기저  (Discrete Basis)**

$$
\hat{I} = \sum_i |u_i\rangle \langle u^i|
 = \sum_{i,j} (G^{-1})^{ij}|u_i\rangle \langle u_j|
,\quad
\hat{I} = \sum_i |u_i\rangle \langle u_i|
$$

proof)

$$
|\psi\rangle = \sum_i u_i|u_i\rangle
$$

여기에서, $|u_i\rangle$ 는 단위 기저 벡터이다. 듀얼 기저 벡터와 내적을 하면,

$$
u_i=\langle u^i|\psi\rangle
$$

$$
|\psi\rangle = \sum_i \langle u^i|\psi\rangle|u_i\rangle
= \sum_i |u_i\rangle \langle u^i|\psi\rangle
$$

따라서,

$$
\hat{I} = \sum_i |u_i\rangle \langle u^i|
$$

$$
=\sum_i|u_i\rangle\sum_j(G^{-1})^{ij}\langle u_j|
=\sum_{i,j}(G^{-1})^{ij}|u_i\rangle\langle u_j|
$$

**(2) 연속 기저 (Continuous Basis)**

$$
\hat{I} = \int du |u\rangle \langle u^d|=\int du  \frac{1}{\gamma(u)}|u\rangle\langle u|,\quad
\hat{I} = \int dx |x\rangle \langle x|
$$

proof)

$$
|\psi(u)\rangle = \int du \langle u^d|\psi\rangle |u\rangle 
= \int du |u\rangle \langle u^d|\psi\rangle 
$$

따라서,

$$
\hat{I} = \int du |u\rangle \langle u^d|
= \int du  \frac{1}{\gamma(u)}|u\rangle\langle u|
$$

---

### 2. 내적과 가중함수

힐버트 공간에서, $|f\rangle$와 $|g\rangle$의 내적을 표현할 때,

**(1) 이산기저**

$$
\langle f|g\rangle = \sum_{i,j} \gamma_u f_i g_j
$$

여기에서, $\gamma_u$는 실수값이어야 한다. 이것은 내적의 값이 실수여야하 하지 때문이다. 

proof)

$$
\langle f|g\rangle
= \langle f| \left(\sum_{i,j} |u_i\rangle\langle u^j| \right) |g\rangle
= \langle f| \left(\sum_{i,j} \gamma_u^\ast|u^i\rangle\langle u^j| \right) |g\rangle
=\sum_{i,j} \gamma_u f_i^\ast g_j
$$

**(2) 연속기저**

$$
\langle f|g\rangle = \int du \gamma_u f^\ast(u) g(u),
$$

proof)

$$
\langle f|g\rangle
=\langle f|\left(\int du |u\rangle\langle u^d| \right)|g\rangle
=\int du \gamma_u^\ast\langle f|u^d\rangle\langle u^d|g\rangle
=\int du \gamma_u f^\ast(u) g(u)
$$

---

### 3. 내적 연산의 특성

힐버트 공간 상태 벡터를 $|\psi_n\rangle$ 라 하고, $a_n$ 를 임의의 복소수 스칼라($a_n \in \mathbb{C}$)라고 하자. 아래와 같이 표현할 수 있다.

**(1) Ket의 스칼라 곱**

$$
\langle a\psi| = a^\ast \langle\psi|
$$

**(2) 내적 연산1**

$$
\operatorname{In}\{|\psi_1\rangle,|a_2\psi_2\rangle+|a_3\psi_3\rangle\}
=a_2\langle \psi_1|\psi_2\rangle+a_3\langle \psi_1|\psi_3\rangle
$$

**(3) 내적 연산2**

$$
\operatorname{In}\{|a_1\psi_1\rangle,|\psi_2\rangle+|\psi_3\rangle\}
=a_1^\ast\langle \psi_1|\psi_2\rangle+a_1^\ast\langle \psi_1|\psi_3\rangle
$$

**(4) Dagger (complex conjugate)**

$$
\langle \psi_1|\psi_2\rangle^\dagger
=\langle \psi_1|\psi_2\rangle^\ast
=\langle \psi_2|\psi_1\rangle
$$