+++
title = "(b) Laurent's series I"
weight = 9
+++

---

### 1. Kernel forcing

$$
h(z, z')
= \frac{1}{|z'|^2}h_M(z/z')
$$

proof)

$$
\langle z^d|\hat{Z}_c\hat{M}|z'\rangle
= \langle (cz)^d|\hat{M}|z'\rangle
= h(cz, z')
$$

$$
\langle z^d|\hat{M}\hat{Z}_c|z'\rangle
= \frac{1}{|c|^2}\langle z^d|\hat{M}|z'/c\rangle
= \frac{1}{|c|^2}h(z, z'/c)
$$

$c$는 임의의 스케일 상수이므로 $z'$ 값을 대입할 수 있다. 

$$
h(z'z, z')
= \frac{1}{|z'|^2}h(z, 1)
$$

$z$에 대한 함수 $h_M(z)$ 를 $h_M(z):=h(z, 1)$ 이라고 새롭게 정의한다. (즉, 입력 $z'$ 이 1일 때의 시스템 응답을 $h_M$으로 정의)

$$
h(z, z')
= \frac{1}{|z'|^2}h_M(z/z')
$$

---

### 2. Mellin convolution for complex

일반적인 선형연산자의 short cut 형태를 사용한다.

$$
\hat{M}=\int d^2z' |h_z(z,z')\rangle\langle z'^d|
$$

이 일반적인 형태에 **"LScI 시스템"** 이라는 강력한 제약 조건을 걸어본다.

$$
\hat{M}=\int_C d^2z' \frac{1}{|z'|^2}|h_M(z/z')\rangle\langle z'^d|
$$

임의의 벡터와 연산을 수행해보자.

$$
\langle z^d|\hat{M}|f\rangle
=\int_C d^2z' \frac{1}{|z'|^2}\langle z^d|h_M(z/z')\rangle\langle z'^d|f\rangle
$$

$$
=\int_C d^2z' \frac{1}{|z'|^2}\langle z^d|h_M(z/z')\rangle\langle z'^d|f\rangle
$$

$$
=\int_C \frac{d^2z'}{|z'|^2}h_M(z/z')f(z')
$$

---

### 3. Eigenvalue & Eigenvector

$$
\text{eigenvector: } \langle z^d|s\rangle=z^{-s}
$$

$$
\text{eigenvalue: } \langle s^M|f\rangle = \int_C \frac{d^2z}{|z|^2} z^{s} \langle z^d|f\rangle
$$

proof)

$f(z)=z^{-s}$라고 하자.

$$
\langle z^d|\hat{M}|f\rangle
=\int_C \frac{d^2z'}{|z'|^2}h_M(z/z')f(z')
=\int_C \frac{d^2z'}{|z'|^2}h_M(z/z')z'^{-s}
$$

$z/z'=u$ 라고 하면,

$$
\frac{dz'}{du}=\frac{d}{du}\left(\frac{z}{u}\right)=-\frac{z}{u^2}\implies dz'=-\frac{z}{u^2}du
$$

$d^2z$ 는 $z$의 위상차이에 의한 면적을 의미한다. 웻지 곱(Wedge Product)을 사용할 수 있다. 

$$
d^2z'
=\frac{1}{2}\left|dz'\land (dz')^\ast\right|
=\frac{1}{2}\left|-\frac{z}{u^2}du\land -\left(\frac{z}{u^2}\right)^\ast du^\ast\right|
=\frac{|z|^2}{|u|^4}d^2u 
$$

$$
\frac{d^2z'}{|z'|^2}
=\frac{1}{|z'|^2}\cdot\frac{|z|^2}{|u|^4}d^2u 
=\frac{1}{|z'|^2}\cdot\frac{|uz'|^2}{|u|^4}d^2u
=\frac{1}{|u|^2}d^2u 
$$

따라서,

$$
\langle z^d|\hat{M}|f\rangle
=z^{-s}\int_C \frac{d^2u}{|u|^2}u^sh_M(u)
$$

---

### 4. 멜린 역변환

$$
m(z)
=\langle z^d|m\rangle=\langle z^d|\int ds \langle s^{M,d}|m\rangle|s\rangle
=\frac{1}{2\pi i}\int ds \langle s^M|m\rangle\langle z^d|s\rangle
=\frac{1}{2\pi i}\int ds \langle s^M|m\rangle z^{-s}
$$

---

### 5. 로랑 급수 = Z-transform

- 수학에서는 **로랑급수** 로 불린다. 공학에서는 **Z-transform**  으로 불린다. 사실상 완전히 동일하다.
- 푸리에 급수와 마찬가지로, 로랑급수는 멜린 역변환의 이산기저로 부터 유도된다.