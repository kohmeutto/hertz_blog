+++
title = "(a) Dyad & dot products"
weight = 4
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

proof)
    
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

proof)
    
$$
\left(\vec{a}\otimes\vec{b}\right):\left(\vec{c}\otimes\vec{d}\right)=a_{i}\hat{u}_{i}b_{j}\hat{u}_{j}:c_{k}\hat{u}_{k}d_{l}\hat{u}_{l}
$$
    
$$
=a_{i}b_{j}c_{k}d_{l}\left(\hat{u}_{i}\hat{u}_{j}:\hat{u}_{k}\hat{u}_{l}\right)=a_{i}b_{j}c_{k}d_{l}\left(\hat{u}_{i}\cdot\hat{u}_{k}\right)\left(\hat{u}_{j}\cdot\hat{u}_{l}\right)=a_{i}b_{j}c_{k}d_{l}\delta_{ik}\delta_{jl}
$$
    
$$
=a_{i}b_{j}c_{k}d_{l}\delta_{ik}\delta_{jl}=a_{i}c_{i}b_{j}d_{j}=\left(\vec{a}\cdot\vec{c}\right)\left(\vec{b}\cdot\vec{d}\right)
$$

$$
(2)
\bar{\bar{A}}:\bar{\bar{B}}
=A_{11}B_{11}+A_{12}B_{12}+A_{21}B_{21}+\cdots
$$

proof)

$$
\bar{\bar{A}}:\bar{\bar{B}}
=A_{ij}\hat{u}_i\hat{u}_jB_{kl}


B_{11}+A_{12}B_{12}+A_{21}B_{21}+\cdots
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
\bar{\bar{A}}\cdot\cdot\bar{\bar{B}}
=\bar{\bar{A}}:\bar{\bar{B}}^T
=\bar{\bar{A}}^T:\bar{\bar{B}}
$$
