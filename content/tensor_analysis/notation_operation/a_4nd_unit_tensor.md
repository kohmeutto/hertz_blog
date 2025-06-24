+++
title = "(a) 4nd unit tensor"
weight = 5
+++

---

### 1. 4차 단위 텐서

$$
\stackrel{4}{I}=\delta_{ik}\delta_{jl}\hat{u}_i\hat{u}_j\hat{u}_k\hat{u}_l
$$

$$
\bar{\bar{A}}=\stackrel{4}{I}:\bar{\bar{A}}
$$

각 성분과 값을 나열해 보자. $(i,j,k,l;\text{값})$

$$
(1,1,1,1;1), (2,2,2,2;1), (3,3,3,3;1)
$$

$$
(1,1,1,2;0), (1,1,1,3;0), (1,1,1,4;0)
$$

$$
(1,2,1,2;1), (1,3,1,3;1), (1,4,1,4;1) 
$$

$$
(1,1,2,2;0), (1,1,3,3;0), (1,1,4,4;0) 
$$

$$
(1,2,2,1;0), (1,3,3,1;0), (2,1,1,2;0) 
$$

**proof)**

$$
\bar{\bar{A}}=\stackrel{4}{I}:\bar{\bar{A}}
$$

$$
A_{mn}\hat{u}_m\hat{u}_n
=C_{ijkl}\hat{u}_i\hat{u}_j\hat{u}_k\hat{u}_l:A_{mn}\hat{u}_m\hat{u}_n
$$

아래와 같이 정리할 수 있다.

$$
\hat{u}_m\hat{u}_n
=C_{ijkl}\hat{u}_i\hat{u}_j\hat{u}_k\hat{u}_l:\hat{u}_m\hat{u}_n
=C_{ijkl}\hat{u}_i\hat{u}_j(\hat{u}_k\hat{u}_l:\hat{u}_m\hat{u}_n)
=C_{ijkl}\hat{u}_i\hat{u}_j(\hat{u}_k\cdot\hat{u}_m)(\hat{u}_l\cdot\hat{u}_n)
$$

$$
=C_{ijkl}\hat{u}_i\hat{u}_j\delta_{km}\delta_{ln}
=C_{ijmn}\hat{u}_i\hat{u}_j
$$

따라서,

$$
C_{ijmn}
=\delta_{im}\delta_{jn}
$$

m를 k로 바꾸고, n을 l로 바꾸면,

$$
C_{ijkl}
=\delta_{ik}\delta_{jl}
$$

---

### 2. 전치 변환 (4차)텐서

$\stackrel{4T}{I}$ 텐서는 '4차 단위 텐서'의 전치가 아님을 주의한다. 2차 텐서가 주어졌을 때, 이 2차 텐서를 전치 텐서로 변환시키는 연산자이다.

$$
\stackrel{4T}{I}
=\delta_{il}\delta_{jk}\hat{u}_i\hat{u}_j\hat{u}_k\hat{u}_l
$$

$$
\bar{\bar{A}}^T
=\stackrel{4T}{I}:\bar{\bar{A}}
$$

각 성분과 값을 나열해 보자. $(i,j,k,l;\text{값})$

$$
(1,1,1,1;1), (2,2,2,2;1), (3,3,3,3;1)
$$

$$
(1,1,1,2;0), (1,1,1,3;0), (1,1,1,4;0)
$$

$$
(1,2,1,2;0), (1,3,1,3;0), (1,4,1,4;0) 
$$

$$
(1,1,2,2;1), (1,1,3,3;1), (1,1,4,4;1) 
$$

$$
(1,2,2,1;1), (1,3,3,1;1), (2,1,1,2;1) 
$$

---

### 3. 대칭 & 비대칭 변환 (4차)텐서

**(1) 대칭 텐서**

$$
\operatorname{sym}\bar{\bar{A}}
=\stackrel{4s}{I}:\bar{\bar{A}}
=\frac12\left(\bar{\bar{A}}+\bar{\bar{A}}^T\right)
$$

$$
\stackrel{4s}{I}
=\operatorname{sym}\stackrel{4}{I}
=\frac12\left(\stackrel{4}{I}+\stackrel{4T}{I}\right),\quad
\left(I_{ikjl}\right)_s
=\frac12\left(\delta_{ik}\delta_{jl}+\delta_{il}\delta_{jk}\right)
$$

proof)

$$
\operatorname{sym}\bar{\bar{A}}
=\stackrel{4s}{I}:\bar{\bar{A}}
=\frac12\left(\bar{\bar{A}}+\bar{\bar{A}}^T\right)
=\frac12\stackrel{4}{I}:\left(\bar{\bar{A}}+\bar{\bar{A}}^T\right)
$$

$$
=\frac12\left(\stackrel{4}{I}:\bar{\bar{A}}+\stackrel{4}{I}:\bar{\bar{A}}^T\right)
=\frac12\left(\stackrel{4}{I}:\bar{\bar{A}}+\stackrel{4T}{I}:\bar{\bar{A}}\right)
=\frac12\left(\stackrel{4}{I}+\stackrel{4T}{I}\right):\bar{\bar{A}}
$$

따라서,

$$
\stackrel{4s}{I}
=\frac12\left(\bar{\bar{A}}+\bar{\bar{A}}^T\right)
$$

**(2) 비대칭 텐서**

$$
\operatorname{skew}\bar{\bar{A}}
=\stackrel{4a}{I}:\bar{\bar{A}}
=\frac12\left(\bar{\bar{A}}-\bar{\bar{A}}^T\right)
$$

$$
\stackrel{4a}{I}
=\operatorname{skew}\stackrel{4}{I}
=\frac12\left(\stackrel{4}{I}-\stackrel{4T}{I}\right),\quad
\left(I_{ikjl}\right)_a
=\frac12\left(\delta_{ik}\delta_{jl}-\delta_{il}\delta_{jk}\right)
$$

proof)

$$
\operatorname{skew}\bar{\bar{A}}
=\stackrel{4a}{I}:\bar{\bar{A}}
=\frac12\left(\bar{\bar{A}}-\bar{\bar{A}}^T\right)
=\frac12\stackrel{4}{I}:\left(\bar{\bar{A}}-\bar{\bar{A}}^T\right)
$$

$$
=\frac12\left(\stackrel{4}{I}:\bar{\bar{A}}-\stackrel{4}{I}:\bar{\bar{A}}^T\right)
=\frac12\left(\stackrel{4}{I}:\bar{\bar{A}}-\stackrel{4T}{I}:\bar{\bar{A}}\right)
=\frac12\left(\stackrel{4}{I}-\stackrel{4T}{I}\right):\bar{\bar{A}}
$$

따라서,

$$
\stackrel{4a}{I}
=\frac12\left(\bar{\bar{A}}-\bar{\bar{A}}^T\right)
$$