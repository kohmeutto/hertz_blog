+++
title = "(a) Triple scalar product"
weight = 6
+++

---

### 1. 삼중 내적

$$
(\vec{a}\times\vec{b})\cdot\vec{c}
=\varepsilon_{ijk}a^ib^jc^k
=\varepsilon^{ijk}a_ib_jc_k
$$

proof)

$$
(\vec{a}\times\vec{b})\cdot\vec{c}
=\varepsilon_{ijk}a^ib^j\vec{g}^k\cdot c^l\vec{g}_l
$$

$$
=\varepsilon_{ijk}a^ib^jc^l\vec{g}^k\cdot\vec{g}_l
=\varepsilon_{ijk}a^ib^jc^l\delta^k_l
$$

$$
=\varepsilon_{ijk}a^ib^jc^k
=\varepsilon^{ijk}a_ib_jc_k
$$

---

### 2. 순환기호의 정의

$$
\varepsilon_{ijk}
=V_ge_{ijk}
=\sqrt{g}e_{ijk}
=\begin{cases}
    \,\,\,\,\,V_g  & (123,231,312) \\
    -V_g           & (321,132,213) \\
    \,\,\,\,\,\,0    & (111,223,331) \text{ 등} 
\end{cases}
$$

$$
g
=\begin{vmatrix}
    g_{11} & g_{12} & g_{13} \\
    g_{21} & g_{22} & g_{23} \\
    g_{31} & g_{32} & g_{33}
\end{vmatrix}
$$

proof1)

$$
(\vec{g}_i\times\vec{g}_j)\cdot\vec{g}_k
=\varepsilon_{ijk}
$$

여기에서, $\varepsilon_{ijk}$는 3차 tensor $\stackrel{3}{E}=\varepsilon_{ijk}\vec{g}^i\vec{g}^j\vec{g}^k$의 covariant 성분이다. 한편, 기하학적으로는 세개의 기저 벡터가 이루는 평향 사변체의 체적 $V_g$ 를 의미하게 된다.

$$
\varepsilon_{123}
=(\vec{g}_1\times\vec{g}_2)\cdot\vec{g}_3
=V_g
$$

$$
\varepsilon_{231}
=(\vec{g}_2\times\vec{g}_3)\cdot\vec{g}_1
=V_g
$$

$$
\varepsilon_{312}
=(\vec{g}_3\times\vec{g}_1)\cdot\vec{g}_2
=V_g
$$

역방향으로 지수를 배열하면,

$$
\varepsilon_{132}
=(\vec{g}_1\times\vec{g}_3)\cdot\vec{g}_2
=-V_g
$$

$$
\varepsilon_{213}
=(\vec{g}_2\times\vec{g}_1)\cdot\vec{g}_3
=-V_g
$$

$$
\varepsilon_{321}
=(\vec{g}_3\times\vec{g}_2)\cdot\vec{g}_1
=-V_g
$$

proof2)

$$
(\vec{g}_i\times\vec{g}_j\cdot\vec{g}_k)(\vec{g}_p\times\vec{g}_q\cdot\vec{g}_r)
=\varepsilon_{ijk}\varepsilon_{pqr}
$$

$$
\varepsilon_{ijk}\varepsilon_{pqr}
=\begin{vmatrix}
    g_{ip} & g_{iq} & g_{ir} \\
    g_{jp} & g_{jq} & g_{kr} \\
    g_{kp} & g_{kq} & g_{kr}
\end{vmatrix}
$$

다음과 같이 정의할 수 있다.

$$
g
=\begin{vmatrix}
    g_{11} & g_{12} & g_{13} \\
    g_{21} & g_{22} & g_{23} \\
    g_{31} & g_{32} & g_{33}
\end{vmatrix}
$$

$\varepsilon_{123}$의 값은 다음과 같다.

$$
\varepsilon_{123}
=\sqrt{g}=V_g
$$

---

**example1)**

기저 벡터가 $\vec{g}_1=\hat{e}_1
+\hat{e}_2$, $\vec{g}_2=-\hat{e}_1+2\hat{e}_2$, $\vec{g}_3=\hat{e}_3$ 와 같이 정의된 일반 좌표계에서, $\vec{a}=3\vec{g}_1-\vec{g}_2+\vec{g}_3$, $\vec{b}=2\vec{g}_1+\vec{g}_3$ 의 외적  $\vec{a}\times\vec{b}$ 를 구하시오.

sol)

$$
[\vec{a}\times\vec{b}]_k
=\epsilon_{ijk}a^ib^j
$$

여기에서,

$$
\varepsilon_{123}=(\vec{g}_1\times\vec{g}_2)\cdot\vec{g}_3
=\begin{vmatrix}
    1  & 1 & 0 \\
    -1 & 2 & 0 \\
    0  & 0 & 1 
\end{vmatrix}
=3
$$

$$
[\vec{a}\times\vec{b}]_1
=3(-1\cdot 1-1\cdot 0)=-3
$$

$$
[\vec{a}\times\vec{b}]_2
=3(1\cdot 2-3\cdot 1)=-3
$$

$$
[\vec{a}\times\vec{b}]_3
=3(3\cdot 2-0\cdot 3)=6
$$

---

### 3. 역(반변) 기저 벡터

$$
\vec{g}^1
=\frac{\vec{g}_2\times\vec{g}_3}{V_g}
=-\frac{\vec{g}_3\times\vec{g}_2}{V_g}
$$

$$
\vec{g}^2
=\frac{\vec{g}_3\times\vec{g}_1}{V_g}
=-\frac{\vec{g}_3\times\vec{g}_1}{V_g}
$$

$$
\vec{g}^3
=\frac{\vec{g}_1\times\vec{g}_2}{V_g}
=-\frac{\vec{g}_2\times\vec{g}_1}{V_g}
$$

proof)

i,j,k는 (123) 같은 순환이라고 가정한다.

$$
\vec{g}_i\times\vec{g}_j
=\lambda\vec{g}^k
$$

$$
\implies
(\vec{g}_i\times\vec{g}_j)\cdot\vec{g}_l
=\lambda\vec{g}^k\cdot\vec{g}_l
$$

$$
\implies
V_g
=\lambda\vec{g}^k\delta_l^k
$$

k=l로 놓으면,

$$
\lambda
=V_g
$$

따라서,

$$
\vec{g}^k=\frac{\vec{g}_i\times\vec{g}_j}{V_g}
$$

---

### 4. 역순환 기호의 정의

$$
\varepsilon^{ijk}
=\frac{1}{V_g}e^{ijk}
=\frac{1}{\sqrt{g}}e^{ijk}
=\begin{cases}
    \,\,\,\,\,\cfrac{1}{V_g} & (123,231,312) \\
    -\cfrac{1}{V_g}          & (321,132,213) \\
    \,\,\,\,\,\,\,0          & (111,223,331) \text{ 등} 
\end{cases}
$$

proof1)

$$
\varepsilon^{123}
=(\vec{g}^1\times\vec{g}^2)\cdot\vec{g}^3
=\frac{(\vec{g}_2\times\vec{g}_3)\times(\vec{g}_3\times\vec{g}_1)\cdot(\vec{g}_1\times\vec{g}_2)}{V^3_g}
$$

여기에서,

$$
(\vec{g}_2\times\vec{g}_3)\times(\vec{g}_3\times\vec{g}_1)\cdot(\vec{g}_1\times\vec{g}_2)
=(\vec{g}_1\times\vec{g}_2\cdot\vec{g}_3)(\vec{g}_1\times\vec{g}_2\cdot\vec{g}_3)
=V_g^2
$$

따라서,

$$
\varepsilon^{123}
=\frac{1}{V_g}
$$

proof2)

$$
\varepsilon^{ijk}
=g^{ip}g^{jq}g^{kr}\varepsilon_{pqr}
=g^{ip}g^{jq}g^{kr}e_{pqr}\sqrt{g}
=\frac{1}{g}e_{ijk}\sqrt{g}
$$

$$
=\frac{1}{\sqrt{g}}e^{ijk}
$$


---


