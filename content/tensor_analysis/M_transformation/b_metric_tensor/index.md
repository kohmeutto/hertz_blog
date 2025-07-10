+++
title = "(a) Metric tensor"
weiggt = 2
+++

---

매트릭 텐서는 실공간[v]에서 두 기저 시스템, 즉 공변기저벡터($g_i$)와 반변기저벡터($g^i$) 사이의 관계를 정의하는 핵심적인 텐서이다. 이는 마치 두 언어 사이의 '사전' 역할을 하며, **한 종류의 기저를 다른 종류의 기저로, 또는 한 종류의 성분을 다른 종류의 성분으로 변환하는 다리 역할**을 한다.

---

### 1. 공변 기저 벡터의 매트릭 텐서

$$
g_{ij}=\vec{g}_i\cdot\vec{g}_j
$$

매트릭 텐서를 행렬로 표시하면 다음과 같다.

$$
\left[g_{ij}\right]
=\begin{bmatrix}
    g_{11} & g_{12} & g_{13} \\
    g_{21} & g_{22} & g_{23} \\
    g_{31} & g_{32} & g_{33} \
\end{bmatrix}
$$

만약, 공변기저벡터들이 서로 ortgorhonal 하다면, 대각 성분을 제외한 모든 성분은 0이 된다. 공변기저벡터를 사용한 두 벡터의 내적은 매트릭 텐서를 사용하여 표현할 수 있다.

$$
\vec{a}\cdot\vec{b}=a^i\vec{g}_i\cdot b^j\vec{g}_j=a^ib^jg_{ij}
$$

---

### 2. 반변기저벡터의 역 매트릭 텐서

$$
g^{ij}=\vec{g}^i\cdot\vec{g}^j
$$

역 매트릭 텐서를 행렬로 표시하면 다음과 같다.

$$
\left[g^{ij}\right]
=\begin{bmatrix}
    g^{11} & g^{12} & g^{13} \\
    g^{21} & g^{22} & g^{23} \\
    g^{31} & g^{32} & g^{33} \
\end{bmatrix}
$$

만약, 반변기저벡터들이 서로 ortgorhonal 하다면, 대각 성분을 제외한 모든 성분은 0이 된다. 반변기저벡터를 사용한 두 벡터의 내적은 역 매트릭 텐서를 사용하여 표현할 수 있다.

$$
\vec{a}\cdot\vec{b}
=a_i\vec{g}^i\cdot b_j\vec{g}^j=a_ib_jg^{ij}
$$

----

### 3. 기저의 변환

$$
\vec{g}_i=g_{ij}\vec{g}^j
$$

$$
\vec{g}^i=g^{ij}\vec{g}_j
$$

{{< details summary="proof" >}}

$$
\vec{g}_i=C_{ij}\vec{g}^j
$$

$$
\vec{g}_i\cdot\vec{g}_j
=C_{ij}\vec{g}^j\cdot\vec{g}_j
=C_{ij}
$$

따라서, 

$$
C_{ij}=g_{ij}
$$

<hr>

{{< /details >}}

위의 관계식으로 부터, 아래의 관계식을 얻을 수 있다.

$$
\left[g^{ij}\right]=\left[g_{ij}\right]^{-1}
$$

{{< details summary="proof" >}}

$$
\vec{g}_i\cdot\vec{g}^j
=g_{ik}\vec{g}^k\cdot g^{jl}\vec{g}_l
=g_{ik}g^{jl}\delta^k_l
=g_{ik}g^{jk}
$$

$$
\delta^j_i=g_{ik}g^{jk}
$$

$$
\left[g^{jk}\right]^{-1}\delta^j_i=g_{ik}
$$

따라서,

$$
\left[g^{ij}\right]=\left[g_{ij}\right]^{-1}
$$

{{< /details >}}

---

### 4. 성분의 변환

$$
a_i
=g_{ij}a^j
$$


$$
a^i
=g^{ij}a_j
$$

proof)

동일 실공간에서 $\vec{a}$는 텐서이므로 다음과 같이 쓸 수 있다.

$$
\vec{a}
=a^i\vec{g}_i
=a_i\vec{g}^i
$$

벡터의 공변 성분을 얻기 위해, 공변기저벡터 $\vec{g}_k$와 내적한다.

$$
\vec{a}\cdot\vec{g}_k
=a^i\vec{g}_i\cdot\vec{g}_k
$$

따라서,

$$
a_k
=a^ig_{ik}
$$

---

**example1)** 데카르트 실공간 기준 원통좌표계의 (1) 매트릭, (2) 역매트릭 텐서, (3) 공변기저벡터 & (4) 반변기저벡터를 구하여라.

{{< details summary="sol" >}}

$$
\vec{g}_1=\left[\cos\phi, \sin\phi, 0\right]^T
$$

$$
\vec{g}_2=\rho\left[-\sin\phi, \cos\phi, 0\right]^T
$$

$$
\vec{g}_3=\left[0, 0, 1\right]^T
$$

매트릭 텐서(각 성분에 대한 내적)은 아래와 같다.

$$
g_{12}=g_{21}=0
$$

$$
g_{13}=g_{31}=0
$$

$$
g_{23}=g_{32}=0
$$

$$
g_{11}=1
$$

$$
g_{22}=\rho^2
$$

$$
g_{33}=1
$$

역 매트릭 텐서는 $[g^{ij}]=[g_{ij}]^{-1}$ 관계를 사용하여 구할 수 있다.

$$
g^{12}=g^{21}=0
$$

$$
g^{13}=g^{31}=0
$$

$$
g^{23}=g^{32}=0
$$

$$
g^{11}=1
$$

$$
g^{22}=1/\rho^2
$$

$$
g^{33}=1
$$

반변 기저 벡터는 $\vec{g}^{i}=g^{ij}\vec{g}_j$ 관계를 사용하여 구할 수 있다.

$$
\vec{g}^1
=g^{11}\vec{g}_{1}+g^{12}\vec{g}_{2}+g^{13}\vec{g}_{3}
=\vec{g}_1
=\left[\cos\phi, \sin\phi, 0\right]^T
$$

$$
\vec{g}^2
=g^{21}\vec{g}_{1}+g^{22}\vec{g}_{2}+g^{23}\vec{g}_{3}
=\frac{1}{\rho^2}\vec{g}_2
=\frac{1}{\rho}\left[-\sin\phi, \cos\phi, 0\right]^T
$$

$$
\vec{g}^3
=g^{31}\vec{g}_{1}+g^{32}\vec{g}_{2}+g^{33}\vec{g}_{3}
=\left[0, 0, 1\right]^T
$$

{{< /details >}}