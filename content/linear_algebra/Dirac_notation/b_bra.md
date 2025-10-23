+++
title = "(b) Bra"
weight = 2
+++

---

### 1. Bra

**(1) 유클리드 공간**

"$\vec{a}\cdot$" 은 연산자이다. 피 연산자를 요구한다. 이것은 행벡터로 표현된다. 따라서, 행벡터를 의미에 따라, 연산자로 간주할 수 있다.

$$
\vec{a}\cdot:=\vec{a}^T:=[a]^T
$$

$$
\vec{a}\cdot\vec{b}=\vec{a}^T\vec{b}
=[a]^T[b]
$$

**(2) 힐버트 공간**

$$
\langle a| \text{ 는 } \vec{a}\cdot \text{에 대응한다.}
$$

$$
\langle a|b\rangle \text{ 는 } \vec{a}\cdot\vec{b} \text{ 에 대응한다.}
$$

유클리드 공간의 $\vec{a}\cdot:=\vec{a}^T$ 인 것처럼 복소수 까지 확장된 힐버트 공간에서는,

$$
\langle a|:=|a\rangle^{\ast T}:=|a \rangle^\dagger 
$$

위와 같은 것을 아래와 같이 부른다.

- ket a의 bra 벡터
- ket a의 허미션 켤레
- ket a의 쌍대 벡터

---

### 2. 모든 Bra 벡터는 선형연산자 이다. 이것은 반드시 만족한다.

$$
\langle f| (a_1|\psi_1\rangle+a_2|\psi_2\rangle)
=a_1\langle f| \psi_1\rangle+a_2\langle f| \psi_2\rangle
$$

---

### 3. 쌍대 기저

어떤 벡터 $|v\rangle$의 특정 성분, 예를 들어 $v_3$ 를 어떻게 알아낼 수 있을까. 바로 이 질문에 답하기 위해 쌍대공간과 Bra가 그 진가를 발휘한다. Ket 공간의 기저 {$|u\rangle$}가 주어지면, 그에 완벽하게 짝을 이루는 특별한 Bra들의 집합이 쌍대공간 안에 존재한다. 이를 **쌍대 기저(Dual Basis)** 부른다.

**(1) 이산기저  (Discrete Basis)**

$$
\langle u^i|u_j\rangle
=\delta^i_j
$$

$$
|v\rangle
=\sum_i v_i|u_i\rangle
=v_1|u_1\rangle+v_2|u_2\rangle+v_3|u_3\rangle+\cdots
$$

$$
v_2
=\langle u^2|v\rangle
$$

**(2) 연속 기저 (Continuous Basis)**

$$
\langle u^d|u'\rangle
=\delta(u-u')
$$

$$
|f\rangle = \int du f(u)|u\rangle
$$

$$
\langle u^d|f\rangle
= \langle u^d|\left(\int du' f(u')|u'\rangle\right)
= \int du' f(u')\langle u^d|u'\rangle
= \int du f(u)\delta(u-u')
= f(u)
$$


---

### 4. 쌍대 벡터 vs. 쌍대 기저, 정규직교기저

$|u\rangle$ 기저가 있다. **엄연히 쌍대 벡터와 쌍대 기저는 서로 다른 정의**이다. 혼동되지 않도록 학습한다.

- 쌍대 벡터: 리츠의 표현정리는 만족하는 $\langle u|=|u\rangle^\dagger$
- 쌍대 기저(Dual basis): $\langle u^d|u\rangle=\delta$ 를 만족하는 $\langle u^d|$

$$
\langle u'|u\rangle = 2\pi\delta(u-u') \ne \delta(u-u')
$$

$$
\langle u^d|u\rangle = \delta(u^d-u) = \delta(u-u^d)
$$

**쌍대벡터=쌍대기저**가 같은 경우가 있으며, 아래를 만족할 경우, $|u\rangle$는 **정규직교기저**라고 한다.

$$
\langle u^d|=\langle u|=|u\rangle^\dagger:\text{정규직교기저}
$$

$|u\rangle$가 **정규직교기저** 라면,

$$
\langle u_i|u_j\rangle
=\langle u^i|u_j\rangle
=\delta_{ij}:\text{이산정규직교기저}
$$

$$
\langle u'|u\rangle
=\langle u^d|u\rangle
=\delta(u'-u)
=\delta(u-u'):\text{연속정규직교기저}
$$

---

### 5. 직교기저와 정규화 상수

**직교기저의 경우**(비 직교 기저는 안됨), 쌍대 벡터와 쌍대 기저는 서로 정규화 상수의 변환 관계가 있다.

**(1) 이산기저**

$$
\langle u^i|=\sum_j (G^{-1})^{ij} \langle u_j|
$$

**(2) 연속기저**

$$
\langle u^d|=\frac{1}{\gamma(u)} \langle u|
$$
