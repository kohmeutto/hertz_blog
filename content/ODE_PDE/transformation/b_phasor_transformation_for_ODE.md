+++
title = "(b) Phasor transform for ODE"
weight = 1
+++

---

**페이저 변환을 수행할 수 있는 조건**

- 입력과 출력이 단일 주기와 단일 파장을 가진다.
- 연산자가 self-adjoint 일 경우, 특수해는 전체해가 된다.

---

### 1. Phasor 변환

$$
A\cos\left(\omega t+\phi\right) \to Ae^{i\phi}
$$

$$
A\sin\left(\omega t+\phi\right)\to-iAe^{i\phi}
$$

$$
A\cos\left(\omega t+\phi\right) \to Ae^{i\phi}
$$

$$
A\sin\left(\omega t+\phi\right)\to-iAe^{i\phi}
$$

$$
A\cos\left(\omega t-kx+\phi\right)\to Ae^{i\left(-kx+\phi\right)}
$$

$$
A\sin\left(\omega t-kx+\phi\right)\to-iAe^{i\left(-kx+\phi\right)}
$$

$$
Ae^{ikx}e^{-i\omega t}\to Ae^{ikx}
$$

$e^{-i\omega t}$를 기준으로,

$$
\frac{\partial}{\partial t}\to-i\omega
$$

$$
\frac{\partial^2}{\partial t^2}\to-\omega^2
$$

$e^{+i\omega t}$를 기준으로,

$$
\frac{\partial}{\partial t}\to i\omega
$$

$$
\frac{\partial^2}{\partial t^2}\to-\omega^2
$$

---

**example1)**

$$
y''-y'-2y=\cos x
$$

{{< details summary="sol" >}}

$$
\left(-1-i-2\right)\underline{y_p}=1
$$

$$
\underline{y_p}=-\frac{1}{3+i}=-\frac{3-i}{10}
$$

$$
y_{p}=\operatorname{Re}\left\lbrack-\frac{3-i}{10}e^{ix}\right\rbrack=\operatorname{Re}\left\lbrack-\frac{3-i}{10}\left(\cos x+i\sin x\right)\right\rbrack=-\frac{3}{10}\cos x-\frac{1}{10}\sin x
$$

<hr>

{{< /details >}}


**example2)**

$$
y''-3y'-4y=\sin 2x
$$

{{< details summary="sol" >}}

$$
(-4-6i-4)\underline{y_p}=-1i
$$

$$
y_p=\operatorname{Re}\left\lbrack\frac{-i}{-4-6i-4}e^{i2x}\right\rbrack=\operatorname{Re}\left\lbrack\frac{-8i+6}{100}\left(\cos x+i\sin x\right)\right\rbrack=\frac{3}{50}\cos x+\frac{2}{25}\sin x
$$

<hr>

{{< /details >}}

**example3)**

$$
y''+y'-2y=4\sin 2x
$$

{{< details summary="sol" >}}

$$
(-4+i-2)\underline{y_p}=-1i
$$

$$
y_p=\operatorname{Re}\left\lbrack\frac{-i}{-4+i-2}e^{i2x}\right\rbrack=\operatorname{Re}\left\lbrack\frac{6i-1}{37}\left(\cos x+i\sin x\right)\right\rbrack=-\frac{1}{37}\cos x-\frac{6}{37}\sin x
$$

<hr>

{{< /details >}}

**example4)**

$$
y''+25y=32\cos 3x
$$

{{< details summary="sol" >}}

$$
(-9+25)\underline{y_p}=1
$$

$$
y_p=\operatorname{Re}\left\lbrack\frac{1}{16}e^{i3x}\right\rbrack=\frac{1}{16}\cos 3x
$$

<hr>

{{< /details >}}

**example5)**

$$
y''+4y=\sin 2x
$$

{{< details summary="sol" >}}

$$
\left(s^2+4\right)\underline{y_p}=-1i,\quad s=2i
$$

$$
\underline{y_p}=\frac{1}{s-2i}\cdot\frac{-i}{\left.\left(s+2i\right)\right|_{s=2i}}=x\cdot\frac{-i}{4i}=-\frac14x
$$

$$
y_{p}=\operatorname{Re}\left\lbrack-\frac{x}{4}e^{i2x}\right\rbrack=-\frac{x}{4}\cos2x
$$

<hr>

{{< /details >}}

**example6)**

$$
x^2y''-2xy'+2y=\cos x
$$

{{< details summary="sol" >}}

$$
\left(s^2-3s+2\right)\underline{y_p}=1
$$

$$
\underline{y_p}=\frac{1}{\left(s^2-3s+2\right)\left|_{s=i}\right.}=\frac{1}{-3i+1}
$$

$$
y_{p}=\operatorname{Re}\left\lbrack\frac{3i+1}{10}\left(\cos x+i\sin x\right)\right\rbrack=\frac{1}{10}\cos x-\frac{3}{10}\sin x
$$

<hr>

{{< /details >}}

**example7)**

$$
x^2y''+11xy'+25y=3\sin3x
$$

{{< details summary="sol" >}}

$$
\left(s^2-10s+25\right)\underline{y_p}=-1i
$$

$$
\underline{y_p}=\frac{1}{\left(s-5\right)^2\left|_{s=3i}\right.}=\frac{1}{34}
$$

$$
y_{p}=\operatorname{Re}\left\lbrack\frac{1}{34}\left(\cos x+i\sin x\right)\right\rbrack=\frac{1}{34}\cos x
$$

{{< /details >}}

---

[Phasor - Wikipedia](https://en.wikipedia.org/wiki/Phasor)

[Analytic signal - Wikipedia](https://en.wikipedia.org/wiki/Analytic_signal)

[9.2 Phasor(페이저) : 네이버 블로그](https://blog.naver.com/songsite123/222893596083)

[signal - Phasors and Fourier Transform - Electrical Engineering Stack Exchange](https://electronics.stackexchange.com/questions/440689/phasors-and-fourier-transform)