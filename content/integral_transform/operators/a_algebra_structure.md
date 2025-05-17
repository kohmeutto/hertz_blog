+++
title = "(a) Algebra structure"
weight = 1
+++

---

- 라플라스 변환의 대수 구조를 정리한다.
- 푸리에 변환의 대수 구조를 정리한다.

---

### 1. 양방향 라플라스 변환의 대수 구조

- 이동 연산 1

$$
\langle s|e^{at}f(t)\rangle
=\langle s|e^{a\hat{t}}|f\rangle
=\langle s-a|f\rangle
$$

$$
\langle t|e^{as}f(s)\rangle
=\langle t|e^{a\hat{s}}|f\rangle
=\langle t+a|f\rangle
$$

- 이동 연산 2

$$
\langle s|f(t+a)\rangle
=\langle s|e^{a\hat{s}}|f\rangle
=e^{as}\langle s|f\rangle
$$

$$
\langle t|f(s+a)\rangle
=\langle t|e^{-a\hat{t}}|f\rangle
=e^{-at}\langle t|f\rangle
$$

- scaling 1

$$
\langle s|f(at)\rangle
=\frac{1}{|a|}\left\langle\frac{s}{a}\middle|f(t)\right\rangle
$$

$$
\langle t|f(as)\rangle
=\frac{1}{|a|}\left\langle\frac{t}{a}\middle|f(s)\right\rangle
$$

- scaling 2

$$
\langle s|f(at+b)\rangle
=\left\langle s\middle|e^{\frac{b}{a}\hat{s}}\middle|f(at)\right\rangle
=e^{\frac{b}{a}s}\left\langle s\middle|f(at)\right\rangle
=\frac{1}{|a|}e^{\frac{b}{a}s}\left\langle\frac{s}{a}\middle|f(t)\right\rangle
$$

$$
\langle t|f(as+b)\rangle
=\left\langle t\middle|e^{-\frac{b}{a}\hat{t}}\middle|f(as)\right\rangle
=e^{-\frac{b}{a}t}\left\langle t\middle|f(as)\right\rangle
=\frac{1}{|a|}e^{-\frac{b}{a}t}\left\langle\frac{t}{a}\middle|f(s)\right\rangle
$$

- 미분 1

$$
\left\langle s\middle|\frac{d^n}{dt^n}f(t)\right\rangle
=\left\langle s\middle|(\hat{D}_t)^n\middle|f\right\rangle
=s^n\left\langle s\middle|f\right\rangle
$$

$$
\left\langle t\middle|\frac{d^n}{ds^n}f(s)\right\rangle
=\left\langle t\middle|(\hat{D}_s)^n\middle|f\right\rangle
=(-t)^n\left\langle t\middle|f\right\rangle
$$

- 미분 2

$$
\left\langle s\middle|t^nf(t)\right\rangle
=\left\langle s\middle|(\hat{t})^n\middle|f\right\rangle
=(-1)^n\frac{d^n}{ds^n}\left\langle s\middle|f\right\rangle
$$

$$
\left\langle t\middle|s^nf(s)\right\rangle
=\left\langle t\middle|(\hat{s})^n\middle|f\right\rangle
=\frac{d^n}{dt^n}\left\langle t\middle|f\right\rangle
$$

- 적분 1

$$
\left\langle s\middle|(\hat{D}_t)^{-1}\middle|f\right\rangle
=\frac{1}{s}\left\langle s\middle|f\right\rangle
$$

$$
\left\langle t\middle|(\hat{D}_s)^{-1}\middle|f\right\rangle
=\frac{1}{t}\left\langle t\middle|f\right\rangle
$$

- 적분 2

$$
\left\langle s\middle|\frac{1}{t}f(t)\right\rangle
=\left\langle s\middle|(\hat{t})^{-1}\middle|f\right\rangle
=\int_{s}^{\infty}ds'\left\langle s'\middle|f\right\rangle
$$

$$
\left\langle t\middle|\frac{1}{s}f(s)\right\rangle
=\left\langle t\middle|(\hat{s})^{-1}\middle|f\right\rangle
=\int_{-\infty}^{t}dt'\left\langle t'\middle|f\right\rangle
$$

---

### 2. 푸리에 변환의 대수 구조

- 이동 연산 1

$$
\langle \omega|e^{at}f(t)\rangle
=\langle \omega|e^{a\hat{t}}|f\rangle
=\langle \omega+ia|f\rangle
$$

$$
\langle t|e^{a\omega}f(\omega)\rangle
=\langle t|e^{a\hat{\omega}}|f\rangle
=\langle t-ia|f\rangle
$$

- 이동 연산 2

$$
\langle \omega|f(t+a)\rangle
=\langle \omega|e^{ia\hat{\omega}}|f\rangle
=e^{ia\omega}\langle \omega|f\rangle
$$

$$
\langle t|f(\omega+a)\rangle
=\langle t|e^{-ia\hat{t}}|f\rangle
=e^{-iat}\langle t|f\rangle
$$

- scaling 1

$$
\langle \omega|f(at)\rangle
=\frac{1}{|a|}\left\langle\frac{\omega}{a}\middle|f(t)\right\rangle
$$

$$
\langle t|f(a\omega)\rangle
=\frac{1}{|a|}\left\langle\frac{t}{a}\middle|f(\omega)\right\rangle
$$

- scaling 2

$$
\langle \omega|f(at+b)\rangle
=\left\langle \omega\middle|e^{\frac{b}{a}\hat{\omega}}\middle|f(at)\right\rangle
=e^{\frac{b}{a}\omega}\left\langle \omega\middle|f(at)\right\rangle
=\frac{1}{|a|}e^{\frac{b}{a}\omega}\left\langle\frac{\omega}{a}\middle|f(t)\right\rangle
$$

$$
\langle t|f(a\omega+b)\rangle
=\left\langle t\middle|e^{-\frac{b}{a}\hat{t}}\middle|f(a\omega)\right\rangle
=e^{-\frac{b}{a}t}\left\langle t\middle|f(a\omega)\right\rangle
=\frac{1}{|a|}e^{-\frac{b}{a}t}\left\langle\frac{t}{a}\middle|f(\omega)\right\rangle
$$

- 미분 1

$$
\left\langle \omega\middle|\frac{d^n}{dt^n}f(t)\right\rangle
=\left\langle \omega\middle|(\hat{D}_t)^n\middle|f\right\rangle
=(i\omega)^n\left\langle \omega\middle|f\right\rangle
$$

$$
\left\langle t\middle|\frac{d^n}{d\omega^n}f(\omega)\right\rangle
=\left\langle t\middle|(\hat{D}_\omega)^n\middle|f\right\rangle
=(-it)^n\left\langle t\middle|f\right\rangle
$$

- 미분 2

$$
\left\langle \omega\middle|t^nf(t)\right\rangle
=\left\langle \omega\middle|(\hat{t})^n\middle|f\right\rangle
=i^n\frac{d^n}{d\omega^n}\left\langle \omega\middle|f\right\rangle
$$

$$
\left\langle t\middle|\omega^nf(\omega)\right\rangle
=\left\langle t\middle|(\hat{\omega})^n\middle|f\right\rangle
=(-i)^n\frac{d^n}{dt^n}\left\langle t\middle|f\right\rangle
$$

- 적분 1

$$
\left\langle \omega\middle|(\hat{D}_t)^{-1}\middle|f\right\rangle
=\langle\omega|u\ast f\rangle
= \frac{1}{i\omega} \langle \omega|f\rangle + \pi \langle 0|f\rangle \delta(\omega)
$$

$$
\left\langle t\middle|(\hat{D}_\omega)^{-1}\middle|f\right\rangle
=\frac{1}{it}\left\langle t\middle|f\right\rangle
$$

- 적분 2

$$
\left\langle \omega\middle|\frac{1}{t}f(t)\right\rangle
=\left\langle \omega\middle|(\hat{t})^{-1}\middle|f\right\rangle
=i\int_{\omega}^{\infty}d\omega'\left\langle \omega'\middle|f\right\rangle
$$

$$
\left\langle t\middle|\frac{1}{\omega}f(\omega)\right\rangle
=\left\langle t\middle|(\hat{\omega})^{-1}\middle|f\right\rangle
=i\int_{-\infty}^{t}dt'\left\langle t'\middle|f\right\rangle
$$

---


