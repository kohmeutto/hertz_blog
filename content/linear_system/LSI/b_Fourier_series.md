+++
title = "(b) Fourier series"
weight = 9
+++

---

### 1. 푸리에 급수의 본질

$|f\rangle$이 이산 무한 기저 $|\omega_{n,A}\rangle$로 표현가능하다면,

$$
|f\rangle
=\sum_{n=-\infty}^{\infty} c_n |\omega_{n,A}\rangle
$$

여기에서,

$$
\langle t^A|\omega_{n,A}\rangle
=e^{in\omega_0t},\quad
\langle \omega_{n}^{A}|t_A\rangle
=e^{-in\omega_0t}
$$

쌍대기저를 구하면,

$$
\int_T dt\{\langle \omega_{n}^{A}|t_A\rangle\langle t^A|\omega_{n,A}\rangle\}
=\int_T dt\{e^{-in\omega_0t}e^{+in\omega_0t}\}
=T
$$

$$
\int_T dt\{\langle \omega_{n}^{A}|t_A\rangle\langle t^A|\omega_{m,A}\rangle\}
=\int_T dt\{e^{-in\omega_0t}e^{+im\omega_0t}\}
=0
$$

$$
\langle\omega_n^{A}|\omega_{m,A}\rangle=T\delta_{nm}
$$

따라서,  $|\omega_{n,A}\rangle$는 비정규 직교 기저임을 알 수 있다. 듀얼기저는 아래와 같다.

$$
\langle\omega_n^{A,d}|=\frac{1}{T}\langle\omega_n^{A}|
$$

위 식을 사용하여, $|f\rangle$을 $|t^A\rangle$로 사영하였을 때, 좌표를 구해보자.

$$
f(t)
=\langle t^A|f\rangle
=\sum_n c_n \langle t^A|\omega_{n,A}\rangle
=\sum_n c_n e^{in\omega_0t}
$$

$$
c_n
=\langle\omega_n^{A,d}|f\rangle
=\frac{1}{T}\int_T dt \{e^{-in\omega_0t}f(t)\}
$$

---

### 2. 푸리에 급수의 형태와 직관적 이해

위에서는 푸리에 변환으로 부터, 푸리에 급수의 본질을 이해하였다. 그러나, 푸리에 급수는 직관적으로 테일러 급수 같이 이해할 수 있다. 주기함수일 경우, 주파수의 정수배인 정현파 함수의 합으로 표현할 수 있다.

$$
f(t)
=\sum_{n=-\infty}^{\infty} c_n e^{in\omega_0 t}
$$

$$
=d_0+\sum_{n=1}^{\infty}d_n\cos (n\omega_0 t + \varphi_n)
$$

$$
=a_0+\sum_{n=1}^{\infty} \{a_n\cos n\omega_0 t + b_n\sin n\omega_0 t\}
$$

where,

$$
c_n
=\langle \exp_n^d|f\rangle
=\frac{1}{T}\langle\exp_n|f\rangle
$$

$$
d_0=c_0,\quad
d_n=2|c_n|,\quad
\varphi_n=\operatorname{ang}\{c_n\}
$$

$$
a_0
=\langle 1^d|f\rangle
=\frac{1}{T}\langle1|f\rangle,\quad
a_n
=\langle \cos_n^d|f\rangle
=\frac{2}{T}\langle \cos_n|f\rangle,\quad
b_n
=\langle \sin_n^d|f\rangle
=\frac{2}{T}\langle \sin_n|f\rangle
$$

proof)

(1) $c_n$, $\langle \exp_n^d|$

$$
\langle \exp_n^d|\exp_n\rangle
=\frac{1}{\gamma}\int_T dt e^{-in\omega_0 t}e^{in\omega_0 t}=1\implies
\gamma=T
$$

$$
\langle \exp_n^d|
=\frac{1}{T}\langle \exp_n|
$$

$$
c_n
=\langle \exp_n^d|f\rangle
=\frac{1}{T}\langle \exp_n|f\rangle
$$

(2) $d_0$, $d_n$, $\varphi_n$

$$
f(t)
=d_0+\sum_{n=1}^{\infty}d_n\cos (n\omega_0 t + \varphi_n)
=d_0+\sum_{n=1}^{\infty}d_n\frac{e^{+i(n\omega_0t+\varphi_n)}+e^{-i(n\omega_0t+\varphi_n)}}{2}
$$

$$
f(t)
=\sum_{n=-\infty}^{\infty}c_ne^{in\omega_0t}
=c_0+\sum_{n=1}^{\infty}\left\{c_ne^{in\omega_0t}+c_{-n}e^{-in\omega_0t}\right\}
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

(3) $a_0$, $\langle 1^d|$

$$
\langle 1^d|1\rangle
=\gamma^{-1}|\langle 1|1\rangle
=\frac{1}{\gamma}\langle1|\int_T dt |t\rangle\langle t|1\rangle
=\frac{1}{\gamma}\int_T dt
=1\implies
\gamma=T
$$

$$
\langle 1^d|
=\frac{1}{T}\langle 1|
$$

$$
a_0
=\langle 1^d|f\rangle
=\frac{1}{T}\langle1|f\rangle
$$

(4) $a_n$, $\langle \cos_n^d|$

$$
\langle \cos_n^d|\cos_n\rangle
=\frac{1}{\gamma}\int_T dt \cos^2 n\omega_0 t=1\implies
\gamma=\frac{T}{2}
$$

$$
\langle \cos_n^d|
=\frac{2}{T}\langle \cos_n|
$$

$$
a_n
=\langle \cos_n^d|f\rangle
=\frac{2}{T}\langle \cos_n|f\rangle
$$

(5) $b_n$, $\langle \sin_n^d|$

$$
\langle \sin_n^d|\sin_n\rangle
=\frac{1}{\gamma}\int_T dt \sin^2 n\omega_0 t=1\implies
\gamma=\frac{T}{2}
$$

$$
\langle \sin_n^d|
=\frac{2}{T}\langle \sin_n|
$$

$$
b_n
=\langle \sin_n^d|f\rangle
=\frac{2}{T}\langle \sin_n|f\rangle
$$

---

### 3. 주기함수

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

{{< /details >}}

---

### 4. 푸리에 급수는 로랑 급수의 "특별한 경우" 이다.

원점에서의 로랑 급수는 아래와 같이 표현한다.

$$
f(z)=\sum_{n=-\infty}^{\infty} b_n z^n,
\quad\text{where, }
b_n
=\frac{1}{2\pi i}\oint \frac{dz}{z}z^{-n}f(z)
$$

크기가 1인 단위원 이다.

$$
z=e^{i\omega_0 t}=e^{i\theta}
$$

$$
f(z)=\sum_{n=-\infty}^{\infty} b_n z^n
=\sum_{n=-\infty}^{\infty} b_n e^{i\omega_0 nt}
$$

$$
b_n
=\frac{1}{2\pi i}\oint \frac{dz}{z}z^{-n}f(z)
=\frac{1}{2\pi i}\int_0^{2\pi} \frac{ie^{i\theta}d\theta}{e^{i\theta}}e^{-in\theta}f(z)
=\frac{1}{T}\int_T dt e^{-i\omega_0 n t}f(z)
$$

