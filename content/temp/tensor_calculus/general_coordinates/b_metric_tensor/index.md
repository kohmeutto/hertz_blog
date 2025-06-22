+++
title = "(a) Metric tensor"
weight = 2
+++

---

### 0. 매트릭 텐서

**동일 실공간[v]의 텐서에 대한 기저 변환 & 성분 변환의 설명**이다.

매트릭 텐서는 실공간[v]에서 두 기저 시스템, 즉 공변기저벡터($h_i$)와 반변기저벡터($h^i$) 사이의 관계를 정의하는 핵심적인 텐서이다. 이는 마치 두 언어 사이의 '사전' 역할을 하며, **한 종류의 기저를 다른 종류의 기저로, 또는 한 종류의 성분을 다른 종류의 성분으로 변환하는 다리 역할**을 한다.

---

### 1. 공변 기저 벡터의 매트릭 텐서

$$
h_{ij}=\vec{h}_i\cdot\vec{h}_j
$$

매트릭 텐서를 행렬로 표시하면 다음과 같다.

$$
\left[h_{ij}\right]
=\begin{bmatrix}
    h_{11} & h_{12} & h_{13} \\
    h_{21} & h_{22} & h_{23} \\
    h_{31} & h_{32} & h_{33} \
\end{bmatrix}
$$

만약, 공변기저벡터들이 서로 orthorgonal 하다면, 대각 성분을 제외한 모든 성분은 0이 된다. 공변기저벡터를 사용한 두 벡터의 내적은 매트릭 텐서를 사용하여 표현할 수 있다.

$$
\vec{a}\cdot\vec{b}=a^i\vec{h}_i\cdot b^j\vec{h}_j=a^ib^jh_{ij}
$$

---

### 2. 반변기저벡터의 역 매트릭 텐서

$$
h^{ij}=\vec{h}^i\cdot\vec{h}^j
$$

역 매트릭 텐서를 행렬로 표시하면 다음과 같다.

$$
\left[h^{ij}\right]
=\begin{bmatrix}
    h^{11} & h^{12} & h^{13} \\
    h^{21} & h^{22} & h^{23} \\
    h^{31} & h^{32} & h^{33} \
\end{bmatrix}
$$

만약, 반변기저벡터들이 서로 orthorgonal 하다면, 대각 성분을 제외한 모든 성분은 0이 된다. 반변기저벡터를 사용한 두 벡터의 내적은 역 매트릭 텐서를 사용하여 표현할 수 있다.

$$
\vec{a}\cdot\vec{b}
=a_i\vec{h}^i\cdot b_j\vec{h}^j=a_ib_jh^{ij}
$$

----

### 3. 기저의 변환

$$
\vec{h}_i=h_{ij}\vec{h}^j
$$

$$
\vec{h}^i=h^{ij}\vec{h}_j
$$

{{< details summary="proof" >}}

$\vec{A}=C_j\vec{h}^j$ 라고 하고, $\vec{A}=\vec{h}_i$로 놓자. 

$$
\vec{h}_i=C_{ij}\vec{h}^j
$$

$$
\vec{h}_i\cdot\vec{h}_j
=C_{ij}\vec{h}^j\cdot\vec{h}_j
=C_{ij}
$$

따라서, $C_{ij}=h_{ij}$ 이므로 이를 대입하면,

$$
\vec{h}_i=h_{ij}\vec{h}^j
$$

<hr>

{{< /details >}}

위의 관계식으로 부터, 아래의 관계식을 얻을 수 있다.

$$
\left[h^{ij}\right]=\left[h_{ij}\right]^{-1}
$$

{{< details summary="proof" >}}

$$
\vec{h}_i\cdot\vec{h}^j
=h_{ik}\vec{h}^k\cdot h^{jl}\vec{h}_l
=h_{ik}h^{jl}\delta^k_l
=h_{ik}h^{jk}
$$

$$
\delta^j_i=h_{ik}h^{jk}
$$

$$
\left[h^{jk}\right]^{-1}\delta^j_i=h_{ik}
$$

따라서,

$$
\left[h^{ij}\right]=\left[h_{ij}\right]^{-1}
$$

{{< /details >}}

---

### 4. 성분의 변환

$$
a_i
=h_{ij}a^j
$$


$$
a^i
=h^{ij}a_j
$$

proof)

동일 실공간에서 $\vec{a}$는 텐서이므로 다음과 같이 쓸 수 있다.

$$
\vec{a}
=a^i\vec{h}_i
=a_i\vec{h}^i
$$

벡터의 공변 성분을 얻기 위해, 공변기저벡터 $\vec{h}_k$와 내적한다.

$$
\vec{a}\cdot\vec{h}_k
=a^i\vec{h}_i\cdot\vec{h}_k
$$

따라서,

$$
a_k
=a^ih_{ik}
$$

---

**example1)** 데카르트 실공간 기준 원통좌표계의 (1) 매트릭, (2) 역매트릭 텐서, (3) 공변기저벡터 & (4) 반변기저벡터를 구하여라.

{{< details summary="sol" >}}

$$
\vec{h}_1=\left[\cos\phi, \sin\phi, 0\right]^T
$$

$$
\vec{h}_2=\rho\left[-\sin\phi, \cos\phi, 0\right]^T
$$

$$
\vec{h}_3=\left[0, 0, 1\right]^T
$$

매트릭 텐서(각 성분에 대한 내적)은 아래와 같다.

$$
h_{12}=h_{21}=0
$$

$$
h_{13}=h_{31}=0
$$

$$
h_{23}=h_{32}=0
$$

$$
h_{11}=1
$$

$$
h_{22}=\rho^2
$$

$$
h_{33}=1
$$

역 매트릭 텐서는 $[h^{ij}]=[h_{ij}]^{-1}$ 관계를 사용하여 구할 수 있다.

$$
h^{12}=h^{21}=0
$$

$$
h^{13}=h^{31}=0
$$

$$
h^{23}=h^{32}=0
$$

$$
h^{11}=1
$$

$$
h^{22}=1/\rho^2
$$

$$
h^{33}=1
$$

반변 기저 벡터는 $\vec{h}^{i}=h^{ij}\vec{h}_j$ 관계를 사용하여 구할 수 있다.

$$
\vec{h}^1
=h^{11}\vec{h}_{1}+h^{12}\vec{h}_{2}+h^{13}\vec{h}_{3}
=\vec{h}_1
=\left[\cos\phi, \sin\phi, 0\right]^T
$$

$$
\vec{h}^2
=h^{21}\vec{h}_{1}+h^{22}\vec{h}_{2}+h^{23}\vec{h}_{3}
=\frac{1}{\rho^2}\vec{h}_2
=\frac{1}{\rho}\left[-\sin\phi, \cos\phi, 0\right]^T
$$

$$
\vec{h}^3
=h^{31}\vec{h}_{1}+h^{32}\vec{h}_{2}+h^{33}\vec{h}_{3}
=\left[0, 0, 1\right]^T
$$

{{< /details >}}