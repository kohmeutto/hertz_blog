+++
title = "(a) Dot products"
weight = 2
+++

---

### 1. Dyad와 벡터의 내적

$$
\left(\vec{a}\otimes\vec{b}\right)\cdot\vec{c}=\vec{a}\left(\vec{b}\cdot\vec{c}\right)
$$

proof) 벡터 표기법

$$
\left(\vec{a}\otimes\vec{b}\right)\cdot\vec{c}=a_{i}\hat{u}_{i}\otimes b_{j}\hat{u}_{j}\cdot c_{k}\hat{u}_{k}=a_{i}b_{j}c_{k}\left(\hat{u}_{i}\otimes\hat{u}_{j}\cdot\hat{u}_{k}\right)
$$
    
$$
=a_{i}b_{j}c_{k}\left(\hat{u}_{i}\delta_{jk}\right)
=a_{i}b_{j}c_{j}\hat{u}_{i}
=\vec{a}\left(\vec{b}\cdot\vec{c}\right)
$$

proof) 성분 표기법

$$
[\vec{a}\vec{b}]_{ij}\vec{c}_j=a_{i}b_{j}c_{j}\implies
\vec{a}\left(\vec{b}\cdot\vec{c}\right)
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

proof2) 벡터 표기법
    
$$
\left(\vec{a}\otimes\vec{b}\right)\cdot\left(\vec{c}\otimes\vec{d}\right)=a_{i}\hat{u}_{i}b_{j}\hat{u}_{j}\cdot c_{k}\hat{u}_{k}d_{l}\hat{u}_{l}
$$
    
$$
=a_{i}b_{j}c_{k}d_{l}\hat{u}_{i}\delta_{jk}\hat{u}_{l}=a_{i}b_{j}c_{j}d_{l}\hat{u}_{i}\hat{u}_{l}=\left(\vec{b}\cdot\vec{c}\right)\vec{a}\vec{d}
$$

proof2) 성분 표기법
    
$$
[\vec{a}\vec{b}]_{ij}[\vec{c}\vec{d}]_{jk}
=a_{i}b_{j}c_{j}d_{k}
=\left(\vec{b}\cdot\vec{c}\right)\vec{a}\vec{d}
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

proof1) 벡터 표기법
    
$$
\left(\vec{a}\otimes\vec{b}\right):\left(\vec{c}\otimes\vec{d}\right)=a_{i}\hat{u}_{i}b_{j}\hat{u}_{j}:c_{k}\hat{u}_{k}d_{l}\hat{u}_{l}
$$
    
$$
=a_{i}b_{j}c_{k}d_{l}\left(\hat{u}_{i}\hat{u}_{j}:\hat{u}_{k}\hat{u}_{l}\right)=a_{i}b_{j}c_{k}d_{l}\left(\hat{u}_{i}\cdot\hat{u}_{k}\right)\left(\hat{u}_{j}\cdot\hat{u}_{l}\right)=a_{i}b_{j}c_{k}d_{l}\delta_{ik}\delta_{jl}
$$
    
$$
=a_{i}b_{j}c_{k}d_{l}\delta_{ik}\delta_{jl}=a_{i}c_{i}b_{j}d_{j}=\left(\vec{a}\cdot\vec{c}\right)\left(\vec{b}\cdot\vec{d}\right)
$$

proof1) 성분 표기법
    
$$
[\vec{a}\vec{b}]_{ij}[\vec{c}\vec{d}]_{ij}
=a_{i}b_{j}c_{i}d_{j}
=\left(\vec{a}\cdot\vec{c}\right)\left(\vec{b}\cdot\vec{d}\right)
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

proof) 벡터 표기법

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

proof) 성분 표기법

$$
[\vec{a}]_i[\bar{\bar{A}}]_{ij}][\vec{b}]_{j}
=a_ib_jA_{ij}\implies
a_iA_{ik}b_k=\vec{a}\vec{b}:\bar{\bar{A}}
$$

---

### 6.  점곱(Dot Product)의 교환 가능성

점곱(dot product)의 **교환 가능성(commutative property)** 은 연산되는 대상의 종류(스칼라, 벡터, 텐서)에 따라 달라진다.

| 연산 대상 | 기호 | 결과 타입 | 교환 가능성 | 비고 |
| :------------------------- | :--------------- | :---------- | :------------------- | :------------------------------------------------------- |
| 스칼라 $\cdot$ 스칼라 | $a \cdot b$ | 스칼라 | **가능** | $a \cdot b = b \cdot a$ |
| 스칼라 $\cdot$ 벡터 | $c\vec{a}$ | 벡터 | **가능** | $c\vec{a} = \vec{a}c$ (점은 주로 생략) |
| 벡터 $\cdot$ 벡터 | $\vec{a} \cdot \vec{b}$ | 스칼라 | **가능** | $\vec{a} \cdot \vec{b} = \vec{b} \cdot \vec{a}$ (가장 흔한 점곱) |
| 텐서 $\cdot$ 벡터 | $\bar{\bar{T}} \cdot \vec{v}$ | 벡터 | **일반적으로 불가능** | $\bar{\bar{T}} \cdot \vec{v} \neq \vec{v} \cdot \bar{\bar{T}}$ (텐서가 대칭일 때만 같음) |
| 벡터 $\cdot$ 텐서 | $\vec{v} \cdot \bar{\bar{T}}$ | 벡터 | **일반적으로 불가능** | $\vec{v} \cdot \bar{\bar{T}} \neq \bar{\bar{T}} \cdot \vec{v}$ (텐서가 대칭일 때만 같음) |
| 텐서 $\cdot$ 텐서 | $\bar{\bar{S}} \cdot \bar{\bar{T}}$ | 2차 텐서 | **일반적으로 불가능** | 일반적인 행렬 곱셈과 동일 |
| 텐서 이중 점곱 (Frobenius) | $\bar{\bar{S}} : \bar{\bar{T}}$ | 스칼라 | **가능** | $S_{ij}T_{ij}$ (모든 성분 곱의 합) |
| 텐서 이중 점곱 (Trace) | $\bar{\bar{S}} \cdot \cdot \bar{\bar{T}}$ | 스칼라 | **가능** | $S_{ij}T_{ji}$ (행렬 곱의 대각합, $\operatorname{tr}\bar{\bar{S}}\bar{\bar{T}}$) |
