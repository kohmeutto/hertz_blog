+++
title = "(b) Kronecker & Levi-Civit`a Symbols"
weight = 2
+++

---

### 1. The Kronecker delta, $\delta_{ij}$

$$
\delta_{ij}
=\left\lbrace\begin{aligned}
    & 1,\,\, i=j \\  
    & 0,\,\, i\ne j
\end{aligned}\right.
$$

$$
\delta_{ij}
=\left\lbrack I\right\rbrack_{ij}
=\left[\begin{matrix}
    1 & 0 & 0 \\
    0 & 1 & 0 \\
    0 & 0 & 1
\end{matrix}\right]
$$

---

### 2. Substitution tensor, $\delta_{ij}$

$$
\delta_{ij}a_{j}
=\delta_{i1}a_1+\delta_{i2}a_2+\delta_{i3}a_3=a_{i}
$$

From the symmetry of $δ_{ij}$ it follows that $δ_{ij}$ $a_{i} = a_{j}$. Because of this property of $δ_{ij}$, it is sometimes referred to as the 'substitution tensor', since its effect when multiplied by $a_{j}$ is to replace the j with i.

$$
\delta_{ij}a_{i}b_{j}=a_{j}b_{j}=\vec{a}\cdot\vec{b}
$$

---

**example1)** Evaluate $\delta_{jj}$

sol)

$$
\delta_{jj}=\delta_{11}+\delta_{22}+\delta_{33}=3
$$

**example2)** Simplify $\delta_{ij}\delta_{jk}$

sol)

$$
\delta_{ij}\delta_{jk}=\delta_{ik}
$$

---

### 3. Levi-Civita' tenser, $\varepsilon_{ijk}$

$$
\varepsilon_{ijk}
=\left\lbrace\begin{aligned}
    & +1,\,\,\left(1,2,3\,\right),\left(2,3,1\right),\left(3,1,2\right) \\
    & -1,\,\,\left(1,3,2\right),\left(2,1,3\right),\left(3,2,1\right) \\
    & \quad\,0,\,\,\text{otherwise}\end{aligned}\right.
$$

**(1) unit vector expression**

$$
\vec{a}\times\vec{b}
=a_i\hat{u}_i\times b_{j}\hat{u}_j
=a_ib_{j}\hat{u}_i\times\hat{u}_j
$$

$$
=a_ib_{j}\varepsilon_{ijk}\hat{u}_k
=\varepsilon_{ijk}a_ib_{j}\hat{u}_k,\quad
\text{since, }\hat{u}_{i}\times\hat{u}_{j}=\epsilon_{ijk}\hat{u}_{k}
$$

**(2) index expression**

The relationship between  and the cross product is as follows:

$$
\left\lbrack\vec{a}\times\vec{b}\right\rbrack_{i}
=\varepsilon_{ijk}a_{j}b_{k}
\to
\left|\begin{matrix}
\hat{u}_1 & \hat{u}_2 & \hat{u}_3 \\
a_1 & a_2 & a_3 \\
b_1 & b_2 & b_3
\end{matrix}\right|
=\hat{u}_1(a_2b_3-a_3b_2)
+\hat{u}_2(a_3b_1-a_3b_1)
+\hat{u}_3(a_1b_2-a_2b_1)
$$

**(3) Determinent**

There is also a relation between  and the determinant of a 3 x 3 matrix. This can be written

$$
\left|M\right|
=\varepsilon_{ijk}M_{1i}M_{2j}M_{3k}
=\left|\begin{matrix}
M_{11} & M_{12} & M_{13} \\
M_{21} & M_{22} & M_{23} \\
M_{31} & M_{32} & M_{33} \\
\end{matrix}\right|
$$

$$
=M_{11}(M_{22}M_{33}-M_{23}M_{32})
+M_{12}(M_{23}M_{31}-M_{21}M_{33})
+M_{13}(M_{21}M_{32}-M_{22}M_{31})
$$

---

**example1)** Simplify $\varepsilon_{ijk}\varepsilon_{ijk}$

sol)

$$
\varepsilon_{ijk}\varepsilon_{ijk}=1^2+\left(-1\right)^2+1^2+\left(-1\right)^2+1^2+\left(-1\right)^2=6
$$

---

### 4. Scalar triple product

**(1) vectors**

An expression for the scalar triple product $\vec{a}\cdot\vec{b}\times\vec{c}$ can be deduced in suffix notation as follows:

$$
\vec{a}\cdot\vec{b}\times\vec{c}
=a_{i}\left\lbrack\vec{b}\times\vec{c}\right\rbrack_{i}
=a_{i}\varepsilon_{ijk}b_{j}c_{k}
=\varepsilon_{ijk}a_{i}b_{j}c_{k}
$$

$$
\varepsilon_{ijk}a_{i}b_{j}c_{k}
=a_1\left(b_2c_3-b_3c_2\right)+a_2\left(b_3c_1-b_1c_3\right)+a_3\left(b_1c_2-b_2c_1\right)
$$

For unit vector expression,

$$
\vec{a}\cdot\vec{b}\times\vec{c}
=a_{i}\hat{u}_{i}\cdot\left(b_{j}\hat{u}_{j}\times c_{k}\hat{u}_{k}\right)
=a_{i}\hat{u}_{i}\cdot b_{j}c_{k}\left(\hat{u}_{j}\times\hat{u}_{k}\right)
$$

$$
=a_{i}b_{j}c_{k}\left(\hat{u}_{i}\cdot\hat{u}_{j}\times\hat{u}_{k}\right)
=a_{i}b_{j}c_{k}\left(\hat{u}_{i}\cdot\epsilon_{ijk}\hat{u}_{i}\right)
=\epsilon_{ijk}a_{i}b_{j}c_{k}
$$

이 삼중곱의 크기는 3개의 벡터가 만드는 평행육면체의 부피를 의미한다.

**(2) Levi-Civita' tenser**

The dot product and the cross product are interchangeable.

$$
\varepsilon_{ijk}
=\hat{u}_{i}\cdot\left(\hat{u}_{j}\times\hat{u}_{k}\right)
=\left(\hat{u}_{i}\times\hat{u}_{j}\right)\cdot\hat{u}_{k}
$$

---

### 5. Relation betweenand $\varepsilon_{ijk}$ & $\delta_{ij}$

증명과정은 매우 복잡(노가다)하다. 암기한다.

$$
\varepsilon_{ijk}\varepsilon_{lmn}
=\left|\begin{matrix}
    \delta_{il} & \delta_{jl} & \delta_{kl} \\
    \delta_{im} & \delta_{jm} & \delta_{km} \\
    \delta_{in} & \delta_{jn} & \delta_{kn}
\end{matrix}\right|
=\left|\begin{matrix}
    \delta_{il} & \delta_{im} & \delta_{in} \\
    \delta_{jl} & \delta_{jm} & \delta_{jn} \\
    \delta_{kl} & \delta_{km} & \delta_{kn}
\end{matrix}\right|
$$

$$
\varepsilon_{ijk}\varepsilon_{klm}
=\left|\begin{matrix}
    \delta_{il} & \delta_{jl} \\
    \delta_{im} & \delta_{jm}
\end{matrix}\right|
=\delta_{il}\delta_{jm}-\delta_{jl}\delta_{im}
$$

---

**example1)** Simplify $\delta_{ij}\varepsilon_{ijk}$

sol)

$$
\delta_{ij}\varepsilon_{ijk}=\varepsilon_{jjk}=0
$$

**example2)** Show $\vec{a}\times\left(\vec{b}\times\vec{c}\right)=\vec{b}\left(\vec{a}\cdot\vec{c}\right)-\vec{c}\left(\vec{a}\cdot\vec{b}\right)$

sol)

$$
\left\lbrack\vec{a}\times\left(\vec{b}\times\vec{c}\right)\right\rbrack_{i}
=\varepsilon_{ijk}a_{j}\left\lbrack\vec{b}\times\vec{c}\right\rbrack_{k}
=\varepsilon_{ijk}a_{j}\varepsilon_{klm}b_{l}c_{m}
=\left(\delta_{il}\delta_{jm}-\delta_{jl}\delta_{im}\right)a_{j}b_{l}c_{m}
$$

$$
\left(\delta_{il}\delta_{jm}-\delta_{jl}\delta_{im}\right)a_{j}b_{l}c_{m}
=\delta_{il}\delta_{jm}a_{j}b_{l}c_{m}-\delta_{jl}\delta_{im}a_{j}b_{l}c_{m}
$$

$$
\delta_{il}\delta_{jm}a_{j}b_{l}c_{m}-\delta_{jl}\delta_{im}a_{j}b_{l}c_{m}
=a_{m}b_{i}c_{m}-a_{l}b_{l}c_{i}
$$

$$
a_{m}b_{i}c_{m}-a_{l}b_{l}c_{i}
\rightarrow
\vec{b}\left(\vec{a}\cdot\vec{c}\right)-\vec{c}\left(\vec{a}\cdot\vec{b}\right)
$$