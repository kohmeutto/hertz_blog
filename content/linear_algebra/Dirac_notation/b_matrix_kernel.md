+++
title = "(b) Matrix & Kernel"
weight = 4
+++

---

### 1. 이산기저와 행렬

**(1) 듀얼기저(dual basis) 벡터**

$$
\hat{A}=\sum_{i,j}A_{ij}|u_i\rangle\langle u^j|, \quad
\text{where }
A_{ij}=\langle u^i| \hat{A} |u_j\rangle
$$

proof)

$$
\hat{A}
=\hat{I}\hat{A}\hat{I}
=\left(\sum_i|u_i\rangle\langle u^i|\right)\hat{A}\left(\sum_j|u_j\rangle\langle u^j|\right)
=\sum_{i,j}|u_i\rangle\langle u^i|\hat{A}|u_j\rangle\langle u^j|
$$

$$
=\sum_{i,j}A_{ij}|u_i\rangle\langle u^j|
$$

**(2) 행렬을 이용한 연산**

연산자 Â가 벡터 |ψ⟩에 작용하여 새로운 벡터 |φ⟩를 만드는 과정($|\phi\rangle = \hat{A}|\psi\rangle$)은, 행렬을 이용하여 다음과 같이 표현된다.

$$
\phi_i=\sum_j A_{ij}\psi_j
$$

proof)

$$
|\phi\rangle = \hat{A}|\psi\rangle
$$


의 양변에 $\langle u^i|$를 내적하면,

$$
\phi_i = \langle u^i|\hat{A}|\psi\rangle
$$

여기에 항등 연산자 $\hat{I} = \sum_j |u_j\rangle \langle u^j|$를 삽입하면,

$$
\phi_i
=\langle u^i|\hat{A}\hat{I}|\psi\rangle
=\langle u^i|\hat{A}\left(\sum_j |u_j\rangle \langle u^j|\right) |\psi\rangle
=\sum_j \langle u^i|\hat{A}|u_j\rangle \psi_j
$$

$$
=\sum_j A_{ij}\psi_j
$$

---

### 2. 연속 기저와 적분 커널 (Integral Kernel)

**(1) 적분 커널**

$$
h(u,u')=\langle u^d|\hat{H}|u'\rangle
$$

proof)

$|f\rangle=\int dx f(x) |x\rangle$과 마찬가지로, $\hat{H}$를 아래와 같이 놓자.

$$
\hat{H}=\iint du du' h(u,u') |u\rangle\langle u'^d| 
$$

또따른 식은 아래와 같다.

$$
\hat{H}
=\hat{I}\hat{H}\hat{I}=\left(\int du |u\rangle\langle u^d|\right)\hat{H}\left(\int du' |u'\rangle\langle u'^d|\right)
=\iint du du' |u\rangle\langle u^d|\hat{H}|u'\rangle\langle u'^d|
$$

따라서, 연산자 $\hat{H}$의 적분 커널 $h(u, u)$는 다음과 같이 정의된다.

$$
h(u,u')
=\langle u^d|\hat{H}|u'\rangle
$$

**(2) 커널을 이용한 연산**

$$
\varphi(u)=\int du' h(u,u') \psi(u')
$$

proof)

$$
\langle u^d|\varphi\rangle
=\langle u^d|\hat{H}|\psi\rangle
=\iint du'' du' h(u'',u') \langle u^d|u''\rangle\langle u'^d|\psi\rangle
$$

$$
=\iint du'' du' h(u'',u') \delta(u-u'') \langle u'^d|\psi\rangle
$$

$$
=\int du' h(u,u') \psi(u')
$$

---

### 3. 연산자의 직관적 의미

위에서 행렬과 적분커널을 잘 살펴보면, 사영연산자를 적용하여, 상수값을 곱하여, 이 모든것을 합치는 과정이라는 알았다. 따라서, 아래와 같은 직관적인 의미로 해석할 수 있다.

- 사영연산자: 특정기저로 사영시킨다.
- 상수값: 특정기저로 사영한 결과에 어떠한 상수를 곱해 변환한다.

