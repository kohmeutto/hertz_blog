+++
title = "(a) Algebra structure"
weight = 7
+++

---

- 푸리에 변환의 대수 구조를 정리한다.
- 푸리에 변환을 사용한 연산자의 관계를 파악한다.
- 양자역학 연산자의 본질을 파악한다.

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
=|x+a\rangle
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