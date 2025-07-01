+++
title = "(a) 2nd tensor"
weight = 3
+++

---

- **동일** 매개변수 공간에서의 변환을 다룬다.
- 매개변수 공간은 데카르트 좌표계로 표현한다.
- **변환은 다른 단위 직교 기저로의 변환**이다.

---

### 1. 2차 tensor의 성분 변환: 텐서 표기법 사용

$$
A_{ij}'=C_{ik}C_{jl}A_{kl},\quad \text{$C_{ik}$, $C_{jl}$는 성분 변환 텐서의 성분이다.}
$$

$$
C_{ik}C_{jl}=B_{ki}B_{lj}
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

따라서,

$$
A_{ij}'=B_{ik}B_{jl}A_{kl}
$$


새로운 기저 벡터 $\hat{u}_i'$를 원래 기저 벡터 $\hat{u}_k$의 선형 결합으로 표현하면 다음과 같다.
(이때 $B_{ik}$는 1. 기저 벡터의 변환에서 정의된 $B_{ij}$의 성분이다.)

$$
\hat{u}_i' = B_{ik}\hat{u}_k
$$

텐서의 불변성 $\bar{\bar{A}} = A_{ij}'\hat{u}_i'\hat{u}_j' = A_{kl}\hat{u}_k\hat{u}_l$을 이용하여, $A_{ij}'$를 $A_{kl}$로 표현해 보자.
우리는 $A_{ij}'\hat{u}_i'\hat{u}_j'$ 항에서 새로운 기저 $\hat{u}_i', \hat{u}_j'$를 원래 기저 $\hat{u}_k, \hat{u}_l$로 변환하여 비교할 것이다.

$$
A_{ij}'\hat{u}_i'\hat{u}_j' = A_{ij}'(B_{ik}\hat{u}_k)(B_{jl}\hat{u}_l)
$$

괄호를 풀고 정리하면:

$$
= A_{ij}'B_{ik}B_{jl}\hat{u}_k\hat{u}_l
$$

이 식은 $A_{kl}\hat{u}_k\hat{u}_l$과 같아야 하므로, 성분들을 비교한다:

$$
A_{kl} = A_{ij}'B_{ik}B_{jl}
$$

이제 $A_{ij}'$에 대해 정리하기 위해, 위 식의 양변에 직교 변환 행렬의 역변환(전치 행렬)을 적용한다. 즉, $B_{pk}$와 $B_{ql}$을 곱하고 합한다. (직교 행렬의 특성 $B_{ik}B_{jk} = \delta_{ij}$ 활용)

$$
A_{kl}B_{pk}B_{ql} = A_{ij}'B_{ik}B_{jl}B_{pk}B_{ql}
$$

우변을 정리하면:

$$
A_{ij}'(B_{ik}B_{pk})(B_{jl}B_{ql}) = A_{ij}'\delta_{ip}\delta_{jq} = A_{pq}'
$$

따라서,

$$
A_{pq}' = B_{pk}B_{ql}A_{kl}
$$

인덱스를 일반적으로 $i, j$로 조정하면, 2차 텐서의 성분 변환 공식은 다음과 같다:

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