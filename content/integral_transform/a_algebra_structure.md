+++
title = "(a) Algebra structure"
weight = 7
+++

---

- 푸리에 변환의 대수 구조를 정리한다.
- 푸리에 변환을 사용한 연산자의 관계를 파악한다.
- 양자역학 연산자의 본질을 파악한다.

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
=(-1)^nt^n\left\langle t\middle|f\right\rangle
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
=(-i)^nt^n\left\langle t\middle|f\right\rangle
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
=\frac{1}{i\omega}\left\langle \omega\middle|f\right\rangle
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

### 1. Shifting operator - Time

아래는 시간에 대한 푸리에 역변환과 시간 이동을 나타낸다.

$$
\langle t|e^{-ia\omega}f(\omega)\rangle
=\langle t-i\cdot -ia| f\rangle
=\langle t-a| f\rangle
$$

연산자 형태로 바꿔보자.

$$
\langle t|e^{-ia\omega}f(\omega)\rangle
=\langle t|e^{-ia\hat{\omega}}|f\rangle
=\langle t|\hat{T}(a)|f\rangle
$$

{{< details summary="연산자로의 변환 증명 1" >}}

$$
=\langle t|\int d\omega \left[e^{-ia\omega}f(\omega)|\omega\rangle\right] 
=\langle t|\int d\omega \left[e^{-ia\omega}\langle\omega|f\rangle|\omega\rangle\right]
=\langle t|\int d\omega \left[e^{-ia\omega}\langle\omega||f\rangle|\omega\rangle\right] 
$$ 

$$
=\langle t|\int d\omega \left[\langle\omega|e^{-ia\hat{\omega}}|f\rangle|\omega\rangle\right]
=\langle t|\int d\omega \left[|\omega\rangle\langle\omega|\right]|e^{-ia\hat{\omega}}|f\rangle
$$


$$
=\langle t|\int d\omega \left[|\omega\rangle\langle\omega|\right]|e^{-ia\hat{\omega}}|f\rangle
$$

$$
=\langle t|\hat{I}|e^{-ia\hat{\omega}}|f\rangle
=\langle t|e^{-ia\hat{\omega}}|f\rangle
$$

<hr>

{{< /details >}}

{{< details summary="연산자로의 변환 증명 2" >}}

$$
\langle t|e^{-ia\hat{\omega}}|f\rangle
=\langle t|\hat{I}e^{-ia\hat{\omega}}|f\rangle
$$

$$
=\langle t|\int d\omega |\omega\rangle\langle\omega|e^{-ia\hat{\omega}}|f\rangle
=\langle t|\int d\omega |\omega\rangle e^{-ia\omega}f(\omega)
$$

$$
=\langle t|\int d\omega \left[e^{-ia\omega}f(\omega)|\omega\rangle\right] 
=\langle t|e^{-ia\omega}f(\omega)\rangle
$$

<hr>

{{< /details >}}


위 2개의 식을 비교하자.

$$
\hat{T}(a)=e^{-ia\hat{\omega}}
$$

$$
\langle t|\hat{T}(a)
=\langle t|e^{-ia\hat{\omega}}
=\langle t-a|
$$

$$
\hat{T}^{\dagger}(a)|t\rangle
=e^{ia\hat{\omega}^{\dagger}}|t\rangle
=|t-a\rangle
$$

$$
\hat{T}(a)|t\rangle
=e^{-ia\hat{\omega}}|t\rangle
=|t+a\rangle
$$

주파수는 물리량 이므로, 주파수 연산자는 Hermitian 이다. 따라서,

$$
\hat{T}(a)\hat{T}^{\dagger}(a)
=e^{-ia\hat{\omega}}e^{ia\hat{\omega}^{\dagger}}
=\hat{I}
$$

위 식으로 부터 병진연산자는 Unitary 연산자임을 알 수 있다.

---

### 2. Shifting operator - Position

이 내용은 위와 동일하다. 위치와 파수의 대응관계를 명확하게 이해하고 위와 동일하게 적용해보자.

{{< details summary="위치 병진 이동 연산자" >}}

$$
\langle x|e^{-iak}f(k)\rangle
=\langle x-i\cdot -ia| f\rangle
=\langle x-a| f\rangle
$$

연산자 형태로 바꿔보자.

$$
\langle x|e^{-iak}f(k)\rangle
=\langle x|e^{-ia\hat{k}}|f\rangle
=\langle x|\hat{U}(a)|f\rangle
$$

위 2개의 식을 비교하자.

$$
\hat{U}(a)=e^{-ia\hat{k}}
$$

$$
\langle x|\hat{U}(a)
=\langle x|e^{-ia\hat{k}}
=\langle x-a|
$$

$$
\hat{U}^{\dagger}(a)|t\rangle
=e^{ia\hat{k}^{\dagger}}|x\rangle
=|x-a\rangle
$$

주파수는 물리량 이므로, 파수 연산자는 Hermitian 이다. 따라서,

$$
\hat{U}(a)\hat{U}^{\dagger}(a)
=e^{-ia\hat{k}}e^{ia\hat{k}^{\dagger}}
=\hat{I}
$$

<br>

위 식으로 부터 병진연산자는 Unitary 연산자임을 알 수 있다.

{{< /details >}}

---

### 3. 미분 연산자 - Position & wave number

- **공간에 대한 푸리에 역변환과 미분**

$$
\langle x|kf(k)\rangle
=\langle x|\hat{k}|f\rangle
=-i\frac{d}{dx}\langle x|f\rangle
$$

{{< details summary="연산자로의 변환 증명" >}}

$$
\langle x|kf(k)\rangle
=\langle x|\int dk \left[kf(k)|k\rangle\right] 
=\langle x|\int dk \left[k|k\rangle\langle k|f\rangle\right]
=\langle x|\int dk \left[\hat{k}|k\rangle\langle k|f\rangle\right]
$$ 

$$
=\langle x|\hat{k}|\int dk \left[|k\rangle\langle k\right]|f\rangle
=\langle x|\hat{k}|f\rangle
$$

{{< /details >}}

- **파수에 대한 푸리에 변환과 미분**

$$
\langle k|xf(k)\rangle
=\langle k|\hat{x}|f\rangle
=i\frac{d}{dk}\langle k|f\rangle
$$

---

### 4. 미분 연산자 - Time & frequency

- **시간에 대한 푸리에 역변환과 미분**

$$
\langle t|\omega f(\omega)\rangle
=\langle t|\hat{\omega}|f\rangle
=-i\frac{d}{dt}\langle t|f\rangle
$$

- **주파수에 대한 푸리에 변환과 미분**

$$
\langle \omega|t f(\omega)\rangle
=\langle \omega|\hat{t}|f\rangle
=i\frac{d}{d\omega}\langle \omega|f\rangle
$$