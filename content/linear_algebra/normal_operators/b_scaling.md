+++
title = "(b) Scaling"
weight = 6
+++

---

### 1. 연산자 자체의 표현

'축척'은 본질적으로 **연속적인 공간(continuous space)** 에서만 닫혀있는(closed) 연산이다.

$$
\hat{Z}_a
=\int^{\infty}_{-\infty}du \frac{1}{|a|}|u/a\rangle\langle u^d|
$$

---

### 2. Ket의 작용

$$
\hat{Z}_a|u\rangle
=\frac{1}{|a|}|u/a\rangle
$$

proof)

$$
\hat{Z}_a|u\rangle
=\int^{\infty}_{-\infty}du' \frac{1}{|a|}|u'/a\rangle\langle u'^d|u\rangle
=\int^{\infty}_{-\infty}du' \frac{1}{|a|}|u'/a\rangle\delta(u'-u)
=\frac{1}{|a|}|u/a\rangle
$$

---

### 3. Bra의 작용

$$
\langle u^d|\hat{Z}_a=\langle (au)^d|
$$

proof)

$$
\langle u^d|\hat{Z}_a
=\langle u^d|\int du' \frac{1}{|a|}|u'/a\rangle\langle u'^d|
=\langle u^d|\int du' \frac{1}{|a|}\langle u^d|u'/a\rangle\langle u'^d|
$$

$$
=\int du'\frac{1}{|a|}\delta(u-u'/a)\langle u'^d|
=\int du'\delta(au-u')\langle u'^d|
=\langle (au)^d|
$$

---

### 4. 상태 벡터의 작용

$$
|\varphi\rangle=\hat{Z}_a|\psi\rangle
$$

이 새로운 상태 $|\varphi\rangle$의 파동함수 $\varphi(u)$는 다음과 같다.

$$
\varphi(u)=\langle u^d|\hat{Z}_a|\psi\rangle=\langle (au)^d|\psi\rangle=\psi(au)
$$

---

### 5. 연속적 성분 표현

$$
\langle u^d|\hat{Z}_a|u'\rangle
=\langle (au)^d|u'\rangle
=\delta(au-u')
=\frac{1}{|a|}\delta(u-u'/a)
$$

