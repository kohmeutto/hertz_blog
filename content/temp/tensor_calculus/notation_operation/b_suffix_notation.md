+++
title = "(b) Suffix notation"
weight = 1
+++

---

### 0. Rule

(1) 각 항에서, 1번 사용한 index를 free index 라고 한다.

(2) 각 항에서, 2번 사용한 index를 dummy index라고 하며, dot product 이다.

(3) 각 항에서, dummy index는 최대 2번만 중복해서 쓸 수 있다. (3번 이상 불가)

(4) 하나의 방정식에서, free index는 같아야 한다.

(5) 대칭 행렬이 아니라면, $a_{ij}\ne a_{ji}$ 이다.

---

### 1. free suffix

$$
\vec{c}=\vec{a}+\vec{b}
\rightarrow
c_i=a_i+b_i
$$

The suffix i is called a 'free suffix'. The choice of this free suffix is arbitrary, so the equation could equally well be written $c_j=a_j+b_j$ or $c_k=a_k+b_k$.

---

### 2. single vector expression

$$
\vec{a}=\hat{u}_{i}a_{i}
$$

---

### 3. dot product expression 1

Now consider the dot product of two vectors, $a\cdot b = a_1 b_1 + a_2 b_2 + a_3 b_3$. This can be written more compactly as

$$
\vec{a}\cdot\vec{b}=\sum_{i=1}^3a_{i}b_{i}\rightarrow a_{i}b_{i}
$$

---

### 4. dot product expression 2

$$
\vec{a}\cdot\vec{b}
=a_{i}\hat{u}_{i}\cdot b_{j}\hat{u}_{j}=a_{i}b_{j}\left(\hat{u}_{i}\cdot\hat{u}_{j}\right)
=a_{i}b_{j}\delta_{ij}=a_{i}b_{i}
$$

$$
\hat{u}_{i}\cdot\hat{u}_{j}
=\delta_{ij}
$$

---

### 5. Matrix expression

$$
M_{ij}\ne M_{ji}
$$

$$
M_{ij}=a_{i}b_{j}
$$

$$
M_{ij}x_{i}=a_{i}b_{j}x_{i}=\left(\vec{a\cdot\vec{x}}\right)b_{j}
$$

---

**example 1)** 

Suppose that an expression involves two dot products multiplied together, (a·b)(c·d). In order to indicate which vector is dotted with which, a different dummy suffix must be used for each of the dot products:

$$
\left(\vec{a}\cdot\vec{b}\right)\left(\vec{c}\cdot\vec{d}\right)=a_{j}b_{j}c_{k}d_{k}
$$

**example 2)**

Write the suffix notation expression  in ordinary vector notation.

$$
a_{j}b_{i}c_{j}
\rightarrow
\left(\vec{a\cdot\vec{c}}\right)\vec{b}
$$

**example 3)**

Write the vector equation in suffix notation.

$$
\vec{u}+\left(\vec{a}\cdot\vec{b}\right)\vec{v}
=\left|\vec{a}\right|^2\left(\vec{b}\cdot\vec{v}\right)\vec{a}
$$

sol)

$$
u_{i}+\left\lbrack\left(\vec{a}\cdot\vec{b}\right)\vec{v}\right\rbrack_{i}
=a_{j}a_{j}b_{k}v_{k}a_{i}
$$

$$
u_{i}+a_{j}b_{j}v_{i}=a_{j}a_{j}b_{k}v_{k}a_{i}
$$

**example 4)**

Show that the product of two N x N matrices A and B, G = AB can be written in suffix notation as $C_{ij}=A_{ik}B_{kj}$.

$$
\vec{C}=\vec{AB}\rightarrow C_{ij}
=\left\lbrack\vec{AB}\right\rbrack_{ij}
=A_{ik}B_{kj}
$$

**example 5)**

Show that the trace of the matrix AB (defined as the sum of the elements on the diagonal) is the same as the trace of BA.

proof)

$$
\operatorname{Tr}\left(\vec{A}\vec{B}\right)
=A_{ik}B_{ki}
=B_{ki}A_{ik}
=\operatorname{Tr}\left(\vec{B}\vec{A}\right)
$$

---

### 5. Non-identities

**example1)** 

$$
a_{ij}\left(x_{i}+y_{j}\right)\ne a_{ij}x_{i}+a_{ij}y_{j}
$$

proof)

하나의 방정식에서, free index는 같아야 한다. 를 만족하지 않으므로 문제가 성립 불가능

**example2)** 

$$
M_{ij}x_{i}y_{j}\ne M_{ij}y_{i}x_{j}
$$

proof)

대칭 행렬이 아닌 경우에는,

$$
M_{ij}\ne M_{ji}
$$

따라서,

$$
M_{ij}x_{i}y_{j}
=a_{i}b_{j}x_{i}y_{j}
=\left(\vec{a}\cdot\vec{x}\right)\left(\vec{b}\cdot \vec{y}\right)
$$

$$
M_{ij}y_{i}x_{j}
=a_{i}b_{j}y_{i}x_{j}
=\left(\vec{a}\cdot\vec{y}\right)\left(\vec{b}\cdot\vec{x}\right)
$$

**example3)** 

$$
\left(a_{ij}+a_{ji}\right)x_{i}y_{j}\ne2a_{ij}x_{i}y_{j}
$$

proof)

대칭 행렬이 아닌 경우에는,

$$
a_{ij}\ne a_{ji}
$$

---

### 6. Identities

$$
a_{ij}\left(x_{i}+y_{i}\right)
=a_{ij}x_{i}+a_{ij}y_{i}
$$

$$
a_{ij}x_{i}x_{j}
=a_{ji}x_{i}x_{j}
$$

$$
\left(a_{ij}+a_{ji}\right)x_{i}x_{j}
=2a_{ij}x_{i}x_{j}
$$

---

[Einstein Summation Convention: an Introduction](https://youtu.be/CLrTj7D2fLM?list=PLdgVBOaXkb9D6zw47gsrtE5XqLeRPh27_)