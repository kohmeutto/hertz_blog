+++
title = "(a) 2nd tensor"
weight = 3
+++

---

### 1. 2차 tensor의 성분 변환: 텐서 표기법 사용

여기에서의 설명은 **직교좌표계의 기저**로 한정한다. **직교가 아닌 일반 좌표계에서는 적용할 수 없다.**

$$
A_{ij}'=C_{ijkl}A_{kl},\quad \text{$C_{ijkl}$ 는 성분 변환 텐서의 성분이다.}
$$

$$
C_{ijkl}=B_{ik}B_{jl}
$$

proof)

**동일 공간**에서, 텐서는 좌표계가 달라져도 불변임을 기억하라.

$$
\bar{\bar{A}}
=A_{ij}'\hat{u}_i'\hat{u}_j'
=A_{ij}\hat{u}_i\hat{u}_j
$$

기저 벡터의 변환을 적용해 보자.

$$
A_{ij}\hat{u}_i\hat{u}_j
=A_{ij}(B_{ki}\hat{u}_k')(B_{lj}\hat{u}_l')
=A_{ij}B_{ki}B_{lj}\hat{u}_k'\hat{u}_l'
$$

$k$↔$i$, $l$↔$j$ 로 조정하면,

$$
A_{kl}B_{ik}B_{jl}\hat{u}_i'\hat{u}_j'
=A_{ij}'\hat{u}_i'\hat{u}_j'
$$

따라서,

$$
A_{ij}'=B_{ik}B_{jl}A_{kl}
$$

---

### 2. 2차 tensor의 성분 변환: Dirac notation 사용

직교좌표계 뿐만아니라, **일반좌표계에서도 적용**할 수 있다. 디렉 표기법을 사용하면 보다 우아하게 성분 변환을 표현할 수 있다.

**힐베르트 공간** 에서, 텐서 A를 아래와 같이 표현할 수 있다.

$$
|\bar{\bar{A}}\rangle=A_{ij}|u_i\rangle\langle u_j|
=A_{ij}'|u_i'\rangle\langle u_j'|
$$

**텐서의 성분 변환**을 파악하기 위해, **기저 벡터 변환** 을 수행하자. 항등 연산자를 사용하면,

$$
|\bar{\bar{A}}\rangle=A_{kl}\left(|u'_i\rangle\langle u'_i|\right)|u_k\rangle\langle u_l|\left(|u'_j\rangle\langle u'_j|\right)
=\left\lbrace\langle u'_i|u_k\rangle\langle u_l|u'_j\rangle\right\rbrace A_{kl}|u'_i\rangle\langle u'_j|
$$

따라서, 성분변환은 아래와 같다.

$$
A_{ij}'
=\langle u'_i|u_k\rangle\langle u_l|u'_j\rangle A_{kl}
$$

정리하면, **2차 텐서의 성분 변환 연산자**를 아래와 같이 표현할 수 있다.

$$
\hat{C}_{ijkl}
=\langle u'_i|u_k\rangle\langle u_l|u'_j\rangle
$$

**일반적으로 2차 텐서의 성분 변환은 내적의 관점**으로 아래와 같이 쓸 수 있다.

$$
A_{ij}'
=\langle u_i'|\bar{\bar{A}}|u_j'\rangle
$$

---

**example1)** 2차 텐서 $[A_{ij}]$ 가 아래와 같이 주어졌을 때, z축을 중심으로 +90도 회전변환을 하였다. 이 때, A에 대한 변환 텐서를 구하여라.

$$
\bar{\bar{A}}
=\begin{bmatrix}
    2  & -1 & 3 \\
    -1 & 1  & 4 \\
    3  & 4  & 1
\end{bmatrix},\quad
\bar{\bar{B}}
=\begin{bmatrix}
    0 & -1 & 0 \\
    1 & 0  & 0 \\
    0 & 0  & 1
\end{bmatrix}
$$

sol)

$$
A_{ij}'
=\langle u_i'|\bar{\bar{A}}|\ u_j'\rangle
$$

$$
[A_{ij}']
=\begin{bmatrix}
    0 & -1 & 0 \\
    1 & 0  & 0 \\
    0 & 0  & 1
\end{bmatrix}
\begin{bmatrix}
    2  & -1 & 3 \\
    -1 & 1  & 4 \\
    3  & 4  & 1
\end{bmatrix}
\begin{bmatrix}
    0  & 1 & 0 \\
    -1 & 0  & 0 \\
    0  & 0  & 1
\end{bmatrix}
=\begin{bmatrix}
    1  & 1  & -4 \\
    1  & 2  & 3 \\
    -4 & -3 & 1
\end{bmatrix}
$$