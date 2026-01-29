+++
title = "(b) Fourier transform I"
weight = 6
+++

---

### 1. 푸리에 변환의 본질

푸리에 변환은 라플라스 변환의 특수한 경우이다. 즉, **s-domain의 실수부가 0으로 고정하고, 허수축에서만의 변환** 을 의미한다.

우선 라플라스 변환 연산자를 살펴보자.

$$
\langle s^L|f\rangle=\int dt \left[ e^{-st} f(t) \right]
$$

실수부가 0으로 고정되면,

$$
\langle s^L|f\rangle|_{\operatorname{Re}[s]=0}
=2\pi i\langle s^d|f\rangle|_{\operatorname{Re}[s]=0}
=\int_{-\infty}^{\infty} dt \left[ e^{-i\omega t} f(t) \right]
$$

**(1) 비정규 직교 기저 푸리에 변환 & 변환 연산자**

- **수학, 공학, 특히 신호 처리에서** 비대칭성 기반 정의가 더 많이 사용된다.
- 비대칭적인 형태가 수학적 이론 전개에 편리하기 때문

$$
\langle \omega^A|f\rangle
=\langle s^L|f\rangle|_{\operatorname{Re}[s]=0}
=\int_{-\infty}^{\infty} dt \left[ e^{-i\omega t} f(t) \right]
$$

**(2) 정규 직교 기저 푸리에 변환 & 변환 연산자**

- **물리학, 특히 양자역학에서 정규 직교성 기반 정의**가 필수적으로 많이 사용된다.
- 에너지 보존과 확률 진폭 해석의 중요성 때문

$$
\langle \omega^S|f\rangle
=\frac{1}{\sqrt{2\pi}}\langle s^L|f\rangle|_{\operatorname{Re}[s]=0}
=\frac{1}{\sqrt{2\pi}}\int_{-\infty}^{\infty} dt \left[ e^{-i\omega t} f(t) \right]
$$

---

### 2. Basis

**(1) 비정규 직교 기저**

$$
\langle t|\omega\rangle_A
=\langle t|s\rangle|_{\operatorname{Re}[s]=0}
=e^{i\omega t},\quad \langle\omega^A|t\rangle=e^{-i\omega t}
$$

$$
\langle\omega^{A,d}|
=\frac{1}{2\pi}\langle\omega^{A}|
$$

이것은 푸리에 변환의 결과가, **$|\omega_A\rangle$의 기저를 사용한 좌표 $\langle \omega^{A,d}|f\rangle$ 에 $2\pi$ 배** 임을 알 수 있다. 

**(2) 정규 직교 기저**

대칭 푸리에 변환을 기준으로 설명한다.

$$
\langle \omega^{S}|f\rangle
=\frac{1}{\sqrt{2\pi}}\int_{-\infty}^{\infty} dt \left[ e^{-i\omega t} f(t) \right]
$$

$$
\langle \omega^S|f\rangle
=\langle \omega^S|\hat{I}|f\rangle
=\int_{-\infty}^{\infty} dt \langle \omega^S|t_S\rangle\langle t^S|f\rangle
$$

위 두개의 식을 비교하면,

$$
\langle \omega^S|t\rangle=\frac{1}{\sqrt{2\pi}}e^{-i\omega t},\quad
\langle t|\omega\rangle_S=\frac{1}{\sqrt{2\pi}}e^{+i\omega t}
$$

$\langle \omega^S|\omega'\rangle$ 이 무엇인지 확인해 보자.

$$
\langle \omega^S|\omega'\rangle
=\langle \omega^S|\hat{I}|\omega'\rangle
=\int_{-\infty}^{\infty} dt \langle \omega^S|t\rangle\langle t|\omega'\rangle
=\frac{1}{2\pi}\int_{-\infty}^{\infty} dt e^{-i(\omega-\omega')t}
=\delta(\omega-\omega')
$$

따라서, 

$$
\langle \omega^{S,d}|=\langle \omega^S|
$$

즉, $|\omega\rangle_S$ 은 **정규직교기저** 이다.

---

### 3. 푸리에 역변환

**(1) 비정규 직교 기저**

$$
f(t)
=\langle t|f\rangle_A
=\frac{1}{2\pi}\int d\omega \langle \omega^A|f\rangle_A e^{i\omega t}
$$

proof)

$$
\langle t|f\rangle_A=\int d\omega \langle \omega^{A,d}|f\rangle \langle t|\omega\rangle
=\frac{1}{2\pi}\int d\omega \langle \omega^{A}|f\rangle e^{i\omega t}
$$

**(2) 정규 직교 기저**

$$
f(t)
=\langle t|f\rangle_S
=\frac{1}{\sqrt{2\pi}}\int d\omega \langle \omega^S|f\rangle_A e^{i\omega t}
$$

proof)

$$
\langle t|f\rangle_S=\int d\omega \langle \omega^{S,d}|f\rangle \langle t|\omega\rangle
=\frac{1}{\sqrt{2\pi}}\int d\omega \langle\omega^{S}|f\rangle e^{i\omega t}
$$

---

### 4. 푸리에 변환의 물리적 의미

**함수는 여러 주파수 성분들이 중첩** 되어 있다고 볼 수 있다. 푸리에 변환은 **감쇄하지 않는 정현파의 각주파수 성분 크기를 구하는 것** 이다. 아래는 cosine과 sine 함수를 나타내며, 빨간색은 주파수 성분의 크기이다.

- cosine 함수
<img src="image1.png" width="60%" height="auto">

- sine 함수
<img src="image2.png" width="60%" height="auto">

---

### 5. 푸리에 변환의 존재 조건

$$
\langle s^L|f\rangle|_{s=i\omega}\to\langle \omega|f\rangle
$$

위 식을 만족하려면, ROC가 허수축을 포함해야 한다.

