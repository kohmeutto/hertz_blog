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

{{< details summary="연산자로의 변환 증명" >}}

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


위 2개의 식을 비교하자. 병진 연산은 내적이 

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



위 2개의 식을 비교하자. 병진 연산은 내적이 

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

<hr>

{{< /details >}}