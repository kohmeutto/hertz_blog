+++
title = "(b) Copy-shift"
weight = 5
+++

---

### 1. 연산자 자체의 표현

**(1) 이산기저**

$$
\hat{S}_l
=\sum_{n}|n+l\rangle\langle n^d|
=\sum_{n}\gamma_n^{-1}|n+l\rangle\langle n|
$$

**(2) 연속기저**

$$
\hat{S}_\tau
=\int^{\infty}_{-\infty}du |u+\tau\rangle\langle u^d|
=\int^{\infty}_{-\infty}du \gamma_u^{-1}|u+\tau\rangle\langle u|
$$

---

### 2. Ket의 작용

**(1) 이산기저**

$$
\hat{S}_l|n\rangle
=|n+l\rangle
$$

proof)

$$
\hat{S}_l|n\rangle
=\sum_{m}|m+l\rangle\langle m^d|n\rangle
=\sum_{m}|m+l\rangle\delta_{mn}
=|n+l\rangle
$$

**(2) 연속기저**

$$
\hat{S}_\tau|u\rangle
=|u+\tau\rangle
$$


proof)

$$
\hat{S}_\tau|u\rangle
=\int^{\infty}_{-\infty}du' |u'+\tau\rangle\langle u'^d|u\rangle
=\int^{\infty}_{-\infty}du' |u'+\tau\rangle\delta(u'-u)
=|u+\tau\rangle
$$

---

### 3. Bra의 작용

**(1) 이산기저**

$$
\langle n^d|\hat{S}_l
=\langle (n-l)^d|
$$

proof)

$$
\langle n^d|\hat{S}_l
=\langle n|\sum_m |m+l\rangle\langle m^d|
=\sum_m \langle n^d|m+l\rangle\langle m^d|
=\sum_m \delta_{n,m+l}\langle m^d|
$$

크로네커 델타의 성질에 의해, $n=m+l$ 이외에는 모두 사라진다. 따라서,

$$
=\langle (n-l)^d|
$$

**(2) 연속기저**

$$
\langle u^d|\hat{S}_\tau=\langle (u-\tau)^d|
$$

proof)

$$
\langle u^d|\hat{S}_\tau
=\langle u^d|\int du' |u'+\tau\rangle\langle u'^d|
=\int du'\langle u^d|u'+\tau\rangle\langle u'^d|
$$

$$
=\int du'\delta(u-u'-\tau)\langle u'^d|
=\langle (u-\tau)^d|
$$

---

### 4. 상태 벡터의 작용

**(1) 이산기저**

$$
|\varphi\rangle=\hat{S}_l|\psi\rangle
$$

이 새로운 상태 $|\varphi\rangle$의 파동함수 $\varphi_n$는 다음과 같다.

$$
\varphi_n
=\langle n^d|\psi\rangle
=\langle n^d|\hat{S}_l|\psi\rangle
=\langle (n-l)^d|\psi\rangle
=\psi_{n-l}
$$

**(2) 연속기저**

$$
|\varphi\rangle=\hat{S}_\tau|\psi\rangle
$$

이 새로운 상태 $|\varphi\rangle$의 파동함수 $\varphi(u)$는 다음과 같다.

$$
\varphi(u)=\langle u^d|\hat{S}_\tau|\varphi\rangle=\langle (u-\tau)^d|\psi\rangle=\psi(u-\tau)
$$

---

### 5. 연속적 성분 표현

**(1) 이산기저**

$$
\langle m^d|\hat{S}_l|n\rangle
=\langle m|n+l\rangle
=\langle m^d|n+l\rangle
=\delta_{m,n+l}
$$

**(2) 연속기저**

$$
\langle u^d|\hat{S}_\tau|u'\rangle
=\langle u^d|u'+\tau\rangle
=\langle u^d|u'+\tau\rangle
=\delta(u-u'-\tau)
$$

