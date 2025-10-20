+++
title = "(b) Matrix & Kernel"
weight = 4
+++

---

### 1. 이산기저와 행렬

**(1) 단위기저(orthonormal basis) 벡터**

연산자 $\hat{A}$의 행렬성분 $A_{ij}$는 다음과 같이 정의된다.

$$
\hat{A}=\sum_{i,j}A_{ij}|u_i\rangle\langle u_j|, \quad
\text{where }
A_{ij}=\langle u_i| \hat{A} |u_j\rangle
$$

proof)

$$
\hat{A}
=\hat{I}\hat{A}\hat{I}
=\left(\sum_i|u_i\rangle\langle u_i|\right)\hat{A}\left(\sum_j|u_j\rangle\langle u_j|\right)
=\sum_{i,j}|u_i\rangle\langle u_i|\hat{A}|u_j\rangle\langle u_j|
$$

$$
=\sum_{i,j}A_{ij}|u_i\rangle\langle u_j|
$$

**(2) 듀얼기저(dual basis) 벡터**

$$
\hat{A}=\sum_{i,j}A^i_{.j}|u_i\rangle\langle u^j|, \quad
\text{where }
A^i_{.j}=\langle u^i| \hat{A} |u_j\rangle
$$

proof)

$$
\hat{A}
=\hat{I}\hat{A}\hat{I}
=\left(\sum_i|u_i\rangle\langle u^i|\right)\hat{A}\left(\sum_j|u_j\rangle\langle u^j|\right)
=\sum_{i,j}|u_i\rangle\langle u^i|\hat{A}|u_j\rangle\langle u^j|
$$

$$
=\sum_{i,j}A^i_{.j}|u_i\rangle\langle u^j|
$$

**(3) 행렬을 이용한 연산**

연산자 Â가 벡터 |ψ⟩에 작용하여 새로운 벡터 |φ⟩를 만드는 과정($|\phi\rangle = \hat{A}|\psi\rangle$)은, 행렬을 이용하여 다음과 같이 표현된다.

$$
\phi_i=\sum_j A_{ij}\psi_j
$$

proof)

$$
|\phi\rangle = \hat{A}|\psi\rangle
$$


의 양변에 $\langle u_i|$를 내적하면,

$$
\phi_i = \langle u_i|\hat{A}|\psi\rangle
$$

여기에 항등 연산자 $\hat{I} = \sum_j |u_j\rangle \langle u_j|$를 삽입하면,

$$
\phi_i
=\langle u_i|\hat{A}\hat{I}|\psi\rangle
=\langle u_i|\hat{A}\left(\sum_j |u_j\rangle \langle u_j|\right) |\psi\rangle
=\sum_j \langle u_i|\hat{A}|u_j\rangle \psi_j
$$

$$
=\sum_j A_{ij}\psi_j
$$

---

### 2. 연속 기저와 적분 커널 (Integral Kernel)

연산자 $\hat{A}$의 적분 커널 $K(u, u)$는 다음과 같이 정의된다.

$$
\hat{A}
=\iint du du' (\gamma_u\gamma_{u'})^{-1} K(u,u') |u\rangle\langle u'| \quad
\text{where }
K(u,u')=\langle u|\hat{A}|u'\rangle
$$

proof)

$$
\hat{A}
=\hat{I}\hat{A}\hat{I}
=\left(\int du \gamma_u^{-1}|u\rangle\langle u|\right)\hat{A}\left(\int du'\gamma_{u'}^{-1}|u'\rangle\langle u'|\right)
=\iint du du' (\gamma_u\gamma_{u'})^{-1}|u\rangle\langle u|\hat{A}|u'\rangle \langle u'|
$$

$$
=\iint du du' (\gamma_u\gamma_{u'})^{-1} K(u,u') |u\rangle\langle u'|
$$

**(2) 커널을 이용한 연산**

$$
\varphi(u)=\int du' K(u,u') \psi(u')
$$

proof)

$$
\langle u|\varphi\rangle = \langle u|\hat{A}|\psi\rangle
=\iint du'' du' (\gamma_{u''}\gamma_{u'})^{-1} K(u'',u') \langle u|u''\rangle\langle u'|\psi\rangle
$$

$$
=\iint du'' du' (\gamma_{u''}\gamma_{u'})^{-1}\gamma_u\gamma_{u'} K(u'',u') \delta(u-u'')\psi(u')
$$

$$
=\int du' (\gamma_{u}\gamma_{u'})^{-1}\gamma_u\gamma_{u'} K(u,u') \psi(u')
$$

$$
=\int du' K(u,u') \psi(u')
$$

---

### 3. 연산자의 직관적 의미

위에서 행렬과 적분커널을 잘 살펴보면, 사영연산자를 적용하여, 상수값을 곱하여, 이 모든것을 합치는 과정이라는 알았다. 따라서, 아래와 같은 직관적인 의미로 해석할 수 있다.

- 사영연산자: 특정기저로 사영시킨다.
- 상수값: 특정기저로 사영한 결과에 어떠한 상수를 곱해 변환한다.

