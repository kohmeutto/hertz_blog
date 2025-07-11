+++
title = "(a) 2nd tensor"
weight = 2
+++

---

### 1. 텐서 성분의 표기

**(1) 변환**

$$
A_{ij}'=C_{ik}'C_{jl}'A_{kl},\quad \text{$C_{ik}'$, $C_{jl}'$는 성분 변환 텐서의 성분이다.}
$$

**(2) 역변환**

$$
A_{ij}=C_{ik}C_{jl}A_{kl}',\quad \text{$C_{ik}$, $C_{jl}$는 성분 변환 텐서의 성분이다.}
$$

---

### 2. 다른 단위 직교 기저로의 변환: Dirac notation 사용

기저의 성분은 모두 실수이다.

$$
A_{ij}'=C_{ik}'C_{jl}'A_{kl}
$$

$$
C_{ik}'C_{jl}'
=\langle u'_i|u_k\rangle\langle u'_j|u_l\rangle
$$

이번에는 역변환을 생각해 보자.

$$
A_{ij}=C_{ik}C_{jl}A_{kl}'
$$

$$
C_{ik}C_{jl}
=\langle u_i|u'_k\rangle\langle u_j|u'_l\rangle
$$

proof)

디렉 표기법을 사용하면 보다 우아하게 성분 변환을 표현할 수 있다. **힐베르트 공간** 에서, 텐서 A를 아래와 같이 표현할 수 있다.

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
\hat{C}_{ik}'\hat{C}_{lj}
=\langle u'_i|u_k\rangle\langle u_l|u'_j\rangle
=\langle u'_i|u_k\rangle\langle u'_j|u_l\rangle^\ast
=\langle u'_i|u_k\rangle\langle u'_j|u_l\rangle
=\hat{C}_{ik}'\hat{C}_{jl}'
$$

---

### 3. 성분 추출

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
\end{bmatrix}
$$

sol)

$$
A_{ij}'
=\langle u_i'|\bar{\bar{A}}|u_j'\rangle
=\langle u_i'|u_k\rangle \langle u_l |u_j'\rangle A_{kl}
$$

$$
\langle u_i'|u_k\rangle
=\begin{bmatrix}
    0 & 1 & 0 \\
    -1 & 0  & 0 \\
    0 & 0  & 1
\end{bmatrix},\quad
\langle u_l|u'_j\rangle
=\begin{bmatrix}
    0 & -1 & 0 \\
    1 & 0  & 0 \\
    0 & 0  & 1
\end{bmatrix}
$$

$$
[A_{ij}']
=\begin{bmatrix}
    0  & 1 & 0 \\
    -1 & 0 & 0 \\
    0  & 0 & 1
\end{bmatrix}
\begin{bmatrix}
    2  & -1 & 3 \\
    -1 & 1  & 4 \\
    3  & 4  & 1
\end{bmatrix}
\begin{bmatrix}
    0 & -1 & 0 \\
    1 & 0  & 0 \\
    0 & 0  & 1
\end{bmatrix}
=\begin{bmatrix}
    1 & 1  & 4 \\
    1 & 2  & -3 \\
    4 & -3 & 1 
\end{bmatrix}
$$


