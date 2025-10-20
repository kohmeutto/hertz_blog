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
=\sum_{m}\gamma_m^{-1}|m+l\rangle\langle m|n\rangle
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
=\int^{\infty}_{-\infty}du' \gamma_{u'}^{-1}|u'+\tau\rangle\langle u'|u\rangle
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

$$
\langle n^d|\hat{S}_l
=\gamma_{n-l}^{-1}\langle n-l|
$$

$$
\langle n|\hat{S}_l
=\gamma_{n-l}^{-1}\gamma_{n}\langle n-l|
$$

proof)

$$
\langle n|\hat{S}_l
=\langle n|\sum_m \gamma_{m}^{-1}|m+l\rangle\langle m|
=\sum_m \gamma_{m}^{-1}\langle n|m+l\rangle\langle m|
=\sum_m \gamma_{m}^{-1}\gamma_{n}\delta_{n,m+l}\langle m|
$$

크로네커 델타의 성질에 의해, $n=m+l$ 이외에는 모두 사라진다. 따라서,

$$
=\gamma_{n-l}^{-1}\gamma_{n}\langle n-l|
$$

**(2) 연속기저**

$$
\langle u^d|\hat{S}_\tau=\langle (u-\tau)^d|
$$

$$
\langle u^d|\hat{S}_\tau=\gamma_{u-\tau}^{-1}\langle u-\tau|
$$

$$
\langle u|\hat{S}_\tau=\gamma_{u-\tau}^{-1}\gamma_{u}\langle u-\tau|
$$

proof)

$$
\langle u|\hat{S}_\tau
=\langle u|\int du' \gamma^{-1}_{u'}|u'+\tau\rangle\langle u'|
=\int du' \gamma^{-1}_{u'}\langle u|u'+\tau\rangle\langle u'|
=\int du' \gamma^{-1}_{u'}\gamma_{u}\delta(u-u'-\tau)\langle u'|
$$

$$
=\gamma_{u-\tau}^{-1}\gamma_{u}\langle u-\tau|
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
\langle m|\hat{S}_l|n\rangle
=\langle m|n+l\rangle
=\gamma_m\langle m^d|n+l\rangle
=\gamma_m\delta_{m,n+l}
$$

**(2) 연속기저**

$$
\langle u|\hat{S}_\tau|u'\rangle
=\langle u|u'+\tau\rangle
=\gamma_u\langle u^d|u'+\tau\rangle
=\gamma_u\delta(u-u'-\tau)
$$

---

### 6. 주의 사항

$$
|\psi(t+\tau)\rangle\ne\hat{S}_\tau|\psi(t)\rangle
$$

- $|\psi(t)\rangle$을 현재 찍은 사진이라고 생각하자.
- $\hat{S}_\tau$는 이 사진을 복사한 다음 $\tau$ 후에 전송하는 것이다.
- $|\psi(t+\tau)\rangle$는 $\tau$초 후에 찍은 사진이다.

따라서 같을 수 없다.
