+++
title = "(b) Fourier series"
weight = 9
+++

---

### 1. 푸리에 급수

**주기 함수** 의 상태 벡터 $|f\rangle$를 $|1\rangle$, $|\cos_n\rangle=|\cos n\omega_0 t\rangle$, $|\sin_n\rangle=|\sin n\omega_0 t\rangle$을 사용한 이산기저로도 표현할 수 있으며, $\langle t|f\rangle=f(t)$ 푸리에 급수라고 한다.

$$
f(t)
=a_0+\sum_{n=1}^{\infty} \{a_n\cos n\omega_0 t + b_n\sin n\omega_0 t\}
=\sum_{n=-\infty}^{\infty} c_n e^{jn\omega_0 t}
=d_0+\sum_{n=1}^{\infty}d_n\cos (n\omega_0 t + \varphi_n)
$$

where,

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

$$
c_n
=\langle \exp_n^d|f\rangle
=\frac{1}{T}\exp_n|f\rangle
$$

$$
d_0=c_0,\quad
d_n=2|c_n|,\quad
\varphi_n=\operatorname{ang}\{c_n\}
$$

proof)

$$
|f\rangle
=a_0|1\rangle + \sum_{n=1}^{\infty} \left\{ a_n |\cos_ n\rangle + b_n |\sin_n\rangle \right\}
$$

각 계수를 구하기 위해서, 각 기저를 정규직교기저로 만들기 위한 쌍대 기저를 알아야 한다. 우선 각 기저 $|\cos_n\rangle$, $|\sin_n\rangle$가 서로 독립임을 확인한다. Wronskian 방법을 사용하면,

$$
W
=\begin{bmatrix}
\cos n\omega_0 t & \sin n\omega_0  t \\
-\omega_0n\sin n\omega_0t & \omega_0 n\cos n\omega_0 t
\end{bmatrix}\implies
|W|\ne0
$$

따라서, 서로 독립이다. 이번에는 각 기저의 쌍대기저를 구해야 한다.

(1) $a_0$, $\langle 1^d|$

$$
\langle 1^d|1\rangle
=\frac{1}{\gamma}\int_T dt 1^\ast \cdot 1=1\implies
\gamma=\frac{1}{T}
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

(2) $a_n$, $\langle \cos_n^d|$

$$
\langle \cos_n^d|\cos_n\rangle
=\frac{1}{\gamma}\int_T dt \cos^2 n\omega_0 t=1\implies
\gamma=\frac{2}{T}
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

(3) $b_n$, $\langle \sin n^d|$

$$
\langle \sin_n^d|\sin_n\rangle
=\frac{1}{\gamma}\int_T dt \sin^2 n\omega_0 t=1\implies
\gamma=\frac{2}{T}
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

(4) $c_n$, $\langle \exp_n^d|$

$$
\langle \exp_n^d|\exp_n\rangle
=\frac{1}{\gamma}\int_T dt e^{-jn\omega_0 t}e^{jn\omega_0 t}=1\implies
\gamma=\frac{1}{T}
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

{{< /details >}}

---

### 3. 푸리에 급수는 로랑 급수의 "특별한 경우" 이다.

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

