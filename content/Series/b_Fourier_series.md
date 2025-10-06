+++
title = "(b) Fourier series"
weight = 2
+++

---

### 1. 푸리에 급수

**주기 함수** 의 상태 벡터 $|f\rangle$를 $|1\rangle$, $|\cos n\omega_0 t\rangle$, $|\sin n\omega_0 t\rangle$을 사용한 이산기저로도 표현할 수 있으며, 기저의 좌표값을 푸리에 급수라고 한다.

$$
f(t)
=a_0+\sum_{n=1}^{\infty} \{a_n\cos n\omega_0 t + b_n\sin n\omega_0 t\}
$$

$$
=\sum_{n=-\infty}^{\infty} c_n e^{jn\omega_0 t}
$$

$$
=d_0+\sum_{n=1}^{\infty}d_n\cos (n\omega_0 t + \varphi_n)
$$

where,

$$
a_0
=\langle 1|f\rangle
=\frac{1}{T}\int_T dt f(t)
$$

$$
a_n
=\langle\cos n\omega_0 t|f\rangle
=\frac{2}{T}\int_T dt \cos (n\omega_0t)f(t)
$$

$$
b_n
=\langle\sin n\omega_0 t|f\rangle
=\frac{2}{T}\int_T dt \sin (n\omega_0t)f(t)
$$

$$
c_n
=\langle e^{jn\omega_0t}|f\rangle
=\frac{1}{T}\int_T dt e^{-jn\omega_0t}f(t)
$$

$$
d_0=c_0
$$

$$
d_n=2|c_n|
$$

$$
\varphi_n=\operatorname{ang}\{c_n\}
$$

proof)

$$
|f\rangle
=a_0|1\rangle + \sum_{n=1}^{\infty} \left\{ a_n |\cos n\omega_0 t\rangle + b_n |\sin n\omega_0 t\rangle \right\}
$$

각 계수를 구하기 위해서, 각 기저에 대한 쌍대기저(범함수)를 알아야 한다.

(1) $a_0$, $\langle 1|$

$$
\langle 1|
=\frac{1}{T}\int_T dt \langle t|
$$

$$
a_0
=\langle 1|f\rangle
=\frac{1}{T}\int_T dt f(t)
$$

(2) $a_n$, $\langle \cos n\omega_0 t|$

$$
\langle \cos n\omega_0 t|
=\frac{2}{T}\int_T dt \cos (n\omega_0t) \langle t|
$$

$$
a_n
=\langle \cos n\omega_0 t|f\rangle
=\frac{1}{T}\int_T dt \cos (n\omega_0t) f(t)
$$

(3) $b_n$, $\langle \sin n\omega_0 t|$

$$
\langle \sin n\omega_0 t|
=\frac{2}{T}\int_T dt \sin (n\omega_0t) \langle t|
$$

$$
b_n
=\langle \sin n\omega_0 t|f\rangle
=\frac{2}{T}\int_T dt \sin (n\omega_0t) f(t)
$$

(4) $c_n$, $\langle e^{jn\omega_0t}|$

$$
\langle e^{jn\omega_0t}|
=\frac{1}{T}\int_T dt e^{-jn\omega_0t} \langle t|
$$

$$
c_n
=\langle e^{jn\omega_0t}|f\rangle
=\frac{1}{T}\int_T dt e^{-jn\omega_0t} f(t)
$$


(5) $d_0$, $d_n$, $\varphi_n$

$$
f(t)
=d_0+\sum_{n=1}^{\infty}d_n\cos (n\omega_0 t + \varphi_n)
=d_0+\sum_{n=1}^{\infty}d_n\frac{e^{+j(n\omega_0t+\varphi_n)}+e^{-j(n\omega_0t+\varphi_n)}}{2}
$$

$$
f(t)
=\sum_{n=-\infty}^{\infty}c_ne^{jn\omega_0t}
=c_0+\sum_{n=1}^{\infty}\left\{c_ne^{jn\omega_0t}+c_{-n}e^{-jn\omega_0t}\right\}
$$

$$
d_0=c_0
$$

$$
c_n=\frac{e^{j\varphi_n}}{2}d_n,\quad
c_{-n}=\frac{e^{-j\varphi_n}}{2}d_n=c_n^\ast\implies
d_n=2|c_n|
$$

$$
\varphi_n=\operatorname{ang}\{c_n\}
$$

---

### 2. 주기함수

푸리에 급수는 임의의 주기함수를 정현함수의 합으로 표현할 수 있음을 보여준다. 그렇다면, 주기함수임을 어떻게 판별할 수 있는가이다. 푸리에 급수에서 메인 주파수의 **정수배**에 해당하는 정현파가 합성됨을 주목하라.

**example)** 주기신호인지 비주기신호인지 구별하고, 주기 신호라면 주기를 구하라.

(a) $x_1(t)=\sin\left(\cfrac{2\pi}{3}t\right)$

(b) $x_2(t)=\sin\left(\cfrac{2\pi}{5}t\right)\cos\left(\cfrac{4\pi}{3}t\right)$

(c) $x_3(t)=\sin\left(3t\right)$

(d) $x_4(t)=x_1(t)-2x_3(t)$

{{< details summary="sol(a)" >}}

$$
f=\frac{1}{3}, T=3
$$

<hr>

{{< /details >}}

{{< details summary="sol(b)" >}}

$$
\sin\left(\frac{2\pi}{5}t\right)\cos\left(\frac{4\pi}{3}t\right)
=\frac{1}{2}\sin\left(\frac{2\pi}{5}t+\frac{4\pi}{3}t\right)
+\frac{1}{2}\sin\left(\frac{2\pi}{5}t-\frac{4\pi}{3}t\right)
$$

$$
=\frac{1}{2}\sin\left(\frac{26\pi}{15}t\right)
-\frac{1}{2}\sin\left(\frac{14\pi}{15}t\right)
$$

$$
=\frac{1}{2}\sin\left(2\pi\cdot 13\cdot\frac{1}{15}t\right)
-\frac{1}{2}\sin\left(2\pi\cdot 7\cdot\frac{1}{15}t\right)
$$

따라서,

$$
f=\frac{1}{15}, T=15
$$

<hr>

{{< /details >}}

{{< details summary="sol(c)" >}}

$$
f=\frac{3}{2\pi}, T=\frac{2\pi}{3}
$$

<hr>

{{< /details >}}

{{< details summary="sol(d)" >}}

비주기함수

<hr>

{{< /details >}}