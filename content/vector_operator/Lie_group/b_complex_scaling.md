+++
title = "(b) Complex scaling"
weight = 14
+++

---

### 1. 연산자 자체의 표현

'단순 축척' 연산자 $\hat{Z}_a$가 $\int du \frac{1}{|a|}|u/a\rangle\langle u^d|$로 정의되듯이, '복소 축척' 연산자 $\hat{Z}_c$는 복소 평면에서의 야코비안($1/|c|^2$)을 포함하여 다음과 같이 정의된다.

$$
\hat{Z}_c=\iint_C d^2z \frac{1}{|c|^2} |z/c\rangle\langle z^d|
$$

여기에서, $d^2z=dxdy$ 로 복소평면의 면적소를 의미힌다.

---

### 2. Ket의 작용

$$
\hat{Z}_c|z\rangle=\frac{1}{|c|^2} |z/c\rangle
$$

proof)

$$
\hat{Z}_c|z\rangle
=\iint_C d^2z' \frac{1}{|c|^2} |z'/c\rangle\langle z'^d|z\rangle
=\iint_C d^2z' \frac{1}{|c|^2} |z'/c\rangle\delta^2(z'-z)
=\frac{1}{|c|^2} |z/c\rangle
$$

---

### 3. Bra의 작용

$$
\langle z^d|\hat{Z}_c=\langle (cz)^d|
$$

proof)

$$
\langle z^d|\hat{Z}_c
=\langle z^d|\iint d^2z' \frac{1}{|c|^2}|z'/c\rangle\langle z'^d|
=\iint d^2z' \frac{1}{|c|^2}\langle z^d|z'/c\rangle\langle z'^d|
$$

$$
=\iint d^2z'\frac{1}{|c|^2}\delta^2(z-z'/c)\langle z'^d|
=\iint d^2z'\delta^2(cz-z')\langle z'^d|
=\langle (cz)^d|
$$

---

### 4. 상태 벡터의 작용

'단순 축척' 연산이 $\psi(au)$ (실수 축척)를 만들듯이, '복소 축척' 연산은 $\psi(cu)$ (복소수 축척/회전)를 만든다.

$$
|\varphi\rangle=\hat{Z}_c|\psi\rangle
$$

이 새로운 상태 $|\varphi\rangle$의 파동함수 $\varphi(z)$는 다음과 같다.

$$
\varphi(z)=\langle z^d|\hat{Z}_c|\psi\rangle=\langle (cz)^d|\psi\rangle=\psi(cz)
$$

---

### 5. 연속적 성분 표현

$$
\langle z^d|\hat{Z}_c|z'\rangle
=\langle (cz)^d|z'\rangle
=\delta(cz-z')
=\frac{1}{|c|^2}\delta(z-z'/c)
$$

---

### 6. Unitary가 될 조건
