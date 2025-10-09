+++
title = "(b) Matrix & Kernel"
weight = 4
+++

---

- '행렬'이라는 용어는 이산적인 시스템을 다루기 위한 수학적 도구이다.
- '커널'이라는 용어는 연속적인 시스템을 다루기 위한 수학적 도구이다.

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

'적분 커널'은 연속 기저에서 연산자를 나타내는, 행렬의 일반화된 개념이다. 행렬이 이산적인 인덱스 i, j에 의해 정의되는 숫자들의 집합($A_{ij}$)이라면, 커널은 연속적인 인덱스 $x'$, $x$에 의해 정의되는 함수 $K(x', x)$ 이다.

**(1) 커널의 정의**

연산자 Â의 적분 커널 $K(x', x)$는 다음과 같이 정의된다. 이는 이산 기저의 행렬 성분 $A_{ij}=\langle u_i| \hat{A} |u_j\rangle$에 정확히 대응된다.

$$
\hat{A}=\iint dx' dx K(x',x) |x'\rangle\langle x| \quad
\text{where }
K(x',x)=\langle x'|\hat{A}|x\rangle
$$

proof)

$$
\hat{A}
=\hat{I}\hat{A}\hat{I}
=\left(\int dx'|x'\rangle\langle x'|\right)\hat{A}\left(\int dx|x\rangle\langle x|\right)
=\iint dx' dx |x'\rangle\langle x'|\hat{A}|x\rangle \langle x|
$$

$$
=\iint dx' dx K(x',x) |x'\rangle\langle x|
$$

**(2) 커널을 이용한 연산**

연산자 Â가 벡터 |ψ⟩에 작용하여 새로운 벡터 |φ⟩를 만드는 과정($|\phi\rangle = \hat{A}|\psi\rangle$)은, 적분 커널을 이용하여 다음과 같이 표현된다.

$$
\phi(x')=\int dx K(x',x) \psi(x)
$$

proof)

$$
|\phi\rangle = \hat{A}|\psi\rangle
$$


의 양변에 $⟨x'|$를 내적하면,

$$
\phi(x') = \langle x'|\hat{A}|\psi\rangle
$$

여기에 항등 연산자 $\hat{I} = \int dx |x\rangle \langle x|$를 삽입하면,

$$
\phi(x')
=\langle x'|\hat{A}\hat{I}|\psi\rangle
=\langle x'|\hat{A}\left(\int dx |x\rangle \langle x|\right) |\psi\rangle
=\int dx \langle x'|\hat{A}|x\rangle \langle x|\psi\rangle
$$

$$
=\int dx K(x',x) \psi(x)
$$

---

### 3. 연산자의 직관적 의미

위에서 행렬과 적분커널을 잘 살펴보면, 사영연산자를 적용하여, 상수값을 곱하여, 이 모든것을 합치는 과정이라는 알았다. 따라서, 아래와 같은 직관적인 의미로 해석할 수 있다.

- 사영연산자: 특정기저로 사영시킨다.
- 상수값: 특정기저로 사영한 결과에 어떠한 상수를 곱해 변환한다.