+++
title = "(a) Components"
weight = 1
+++

---

### 1. 다른 단위 직교 기저로의 변환: Dirac notation 사용

기저의 성분은 모두 실수이다.

$$
u_i'=\langle u_i'|u_j\rangle u_j
$$

$$
\langle u_i'|u_j\rangle
=\langle u_j|u_i'\rangle^\ast
=\langle u_j|u_i'\rangle
$$

이번에는 역변환을 생각해 보자.

$$
u_i=\langle u_i|u_j'\rangle u_j'
$$

$$
\langle u_i|u_j'\rangle
=\langle u_j'|u_i\rangle^\ast
=\langle u_j'|u_i\rangle
$$

proof)

**힐베르트 공간** 에서, 텐서 r를 아래와 같이 표현할 수 있다.

$$
|r\rangle
=u_i'|u_i'\rangle
=u_j|u_j\rangle
$$

**텐서의 성분 변환**을 파악하기 위해, **기저 벡터 변환** 을 수행하자. 항등 연산자를 사용하면,

$$
|r\rangle
=u_i'|u_i'\rangle
=u_j|u_i'\rangle\langle u_i'|u_j\rangle
=\langle u_i'|u_j\rangle u_j|u_i'\rangle
$$

따라서, 성분변환은 아래와 같다.

$$
u_{i}'
=\langle u_i'|u_j\rangle u_j
$$

정리하면, **벡터의 성분 변환 연산자**를 아래와 같이 표현할 수 있다.

$$
\hat{C}_{ij}'
=\langle u_i'|u_j\rangle
$$

---

### 2. 성분 추출

**일반적으로 벡터의 성분 변환은 내적의 관점**으로 아래와 같이 쓸 수 있다.

$$
u_{i}'
=\langle u_i'|r\rangle
$$

proof)

성분변환은 아래와 같다.

$$
u_{i}'
=\langle u_i'|u_j\rangle u_j
=\langle u_i'| (u_j|u_j\rangle)
=\langle u_i'| r\rangle
$$


---

### 3. 항등 연산

기저의 성분은 모두 실수이다.

$$
\delta_{ij}=\langle u_i | u_j \rangle
= \langle u_i | u_k'\rangle \langle u_k'| u_j \rangle
= \langle u_k' | u_i\rangle \langle u_k'| u_j \rangle
= \langle u_i | u_k'\rangle \langle u_j| u_k' \rangle
$$

proof)

$$
\delta_{ij}=\langle u_i | u_j \rangle
= \langle u_i |\left(| u_k'\rangle \langle u_k'|\right)| u_j \rangle
= \langle u_i | u_k'\rangle \langle u_k'| u_j \rangle
$$

여기에서, 기저의 성분이 실수라면,

$$
\langle u_i | u_k'\rangle
=\langle u_k' | u_i\rangle^\ast
=\langle u_k' | u_i\rangle
$$


