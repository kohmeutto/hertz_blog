+++
title = "(a) Dot products"
weight = 2
+++

---

### 1. Dyad와 벡터의 내적

$$
\left(\vec{a}\otimes\vec{b}\right)\cdot\vec{c}=\vec{a}\left(\vec{b}\cdot\vec{c}\right)
$$

proof)
    
$$
\left(\vec{a}\otimes\vec{b}\right)\cdot\vec{c}=a_{i}\hat{u}_{i}\otimes b_{j}\hat{u}_{j}\cdot c_{k}\hat{u}_{k}=a_{i}b_{j}c_{k}\left(\hat{u}_{i}\otimes\hat{u}_{j}\cdot\hat{u}_{k}\right)
$$
    
$$
=a_{i}b_{j}c_{k}\left(\hat{u}_{i}\delta_{jk}\right)=a_{i}b_{j}c_{j}\hat{u}_{i}=\vec{a}\left(\vec{b}\cdot\vec{c}\right)
$$

---

### 2. Dyad와 dyad의 내적

Dyad와 dyad의 내적은 **일반적인 행렬 곱**을 의미한다. 이중 bar, $\bar{\bar{A}}$는 2차텐서를 의미한다.

$$
(1)
\bar{\bar{A}}\cdot\bar{\bar{B}}
=\left[\begin{matrix}
    A_{11} & A_{12} & \cdots \\
    A_{21} & A_{22} & \cdots \\
    \vdots & \vdots & \ddots
\end{matrix}\right]
\left[\begin{matrix}
    B_{11} & B_{12} & \cdots \\
    B_{21} & B_{22} & \cdots \\
    \vdots & \vdots & \ddots
\end{matrix}\right]
$$

$$
(2)
\left(\vec{a}\otimes\vec{b}\right)\cdot\left(\vec{c}\otimes\vec{d}\right)=\left(\vec{b}\cdot\vec{c}\right)\vec{a}\vec{d}
$$

proof2)
    
$$
\left(\vec{a}\otimes\vec{b}\right)\cdot\left(\vec{c}\otimes\vec{d}\right)=a_{i}\hat{u}_{i}b_{j}\hat{u}_{j}\cdot c_{k}\hat{u}_{k}d_{l}\hat{u}_{l}
$$
    
$$
=a_{i}b_{j}c_{k}d_{l}\hat{u}_{i}\delta_{jk}\hat{u}_{l}=a_{i}b_{j}c_{j}d_{l}\hat{u}_{i}\hat{u}_{l}=\left(\vec{b}\cdot\vec{c}\right)\vec{a}\vec{d}
$$

---

### 3. Dyad의 이중 점 곱 1 (double dot product 1)

Dyad와 dyad의 이중 점 곱은, **동일 위치 원소 곱에 대한 합**이다. 

$$
(1)
\left(\vec{a}\otimes\vec{b}\right):\left(\vec{c}\otimes\vec{d}\right)=\left(\vec{a}\cdot\vec{c}\right)\left(\vec{b}\cdot\vec{d}\right)
$$

$$
(2)
\bar{\bar{A}}:\bar{\bar{B}}
=A_{11}B_{11}+A_{12}B_{12}+A_{21}B_{21}+\cdots
$$

proof1)
    
$$
\left(\vec{a}\otimes\vec{b}\right):\left(\vec{c}\otimes\vec{d}\right)=a_{i}\hat{u}_{i}b_{j}\hat{u}_{j}:c_{k}\hat{u}_{k}d_{l}\hat{u}_{l}
$$
    
$$
=a_{i}b_{j}c_{k}d_{l}\left(\hat{u}_{i}\hat{u}_{j}:\hat{u}_{k}\hat{u}_{l}\right)=a_{i}b_{j}c_{k}d_{l}\left(\hat{u}_{i}\cdot\hat{u}_{k}\right)\left(\hat{u}_{j}\cdot\hat{u}_{l}\right)=a_{i}b_{j}c_{k}d_{l}\delta_{ik}\delta_{jl}
$$
    
$$
=a_{i}b_{j}c_{k}d_{l}\delta_{ik}\delta_{jl}=a_{i}c_{i}b_{j}d_{j}=\left(\vec{a}\cdot\vec{c}\right)\left(\vec{b}\cdot\vec{d}\right)
$$

proof2)

$$
\bar{\bar{A}}:\bar{\bar{B}}
=A_{ij}\hat{u}_i\hat{u}_j:B_{kl}\hat{u}_{kl}\hat{u}_{kl}
=A_{ij}B_{kl}\left(\hat{u}_i\cdot\hat{u}_k\right)\left(\hat{u}_j\cdot\hat{u}_l\right)
$$

$$
=A_{ij}B_{kl}\delta_{ik}\delta_{jl}
=A_{ij}B_{ij}
$$

---

### 4. Dyad의 이중 점 곱 2 (double dot product 2)

$$
\bar{\bar{A}}\cdot\cdot\bar{\bar{B}}
=\bar{\bar{A}}:\bar{\bar{B}}^T
=\bar{\bar{A}}^T:\bar{\bar{B}}
$$

---

### 5. 양쪽 점 곱

$$
\vec{a}\cdot\bar{\bar{A}}\cdot\vec{b}
=\vec{a}\vec{b}:\bar{\bar{A}}
=\bar{\bar{A}}:\vec{a}\vec{b}
$$

proof)

$$
a_i\hat{u}_i\cdot A_{jk}\hat{u}_j\hat{u}_k\cdot b_l\hat{u}_l
=a_ib_lA_{jk}(\hat{u}_i\cdot \hat{u}_j)(\hat{u}_k\cdot \hat{u}_l)
=a_ib_lA_{jk}\delta_{ij}\delta_{kl}
=a_iA_{ik}b_k
$$

$$
a_ib_l\hat{u}_i\hat{u}_l:A_{jk}\hat{u}_j\hat{u}_k
=a_ib_lA_{jk}(\hat{u}_i\cdot \hat{u}_j)(\hat{u}_k\cdot \hat{u}_l)
=a_iA_{ik}b_k
$$