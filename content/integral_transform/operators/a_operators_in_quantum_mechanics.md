+++
title = "(a) Operators in quantum mechanics"
weight = 3
+++

---

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
=\langle t-a|,\quad
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

위 식으로 부터 병진연산자는 Unitary 연산자임을 알 수 있다. 또한, $\hat{\omega}$는 시간 진화를 일으키는 생성자임을 확인할 수 있다. 생성자 $\hat{\omega}=\hat{H}/\hbar$ 임을 사용하여, 양자역학적인 시간진화연산자를 유도할 수 있다. 아주 작은 시간 변화($\delta t$)에 대해서,

$$
\hat{T}(\delta t)
=e^{-\frac{i}{\hbar}\delta t\hat{H}},\quad
\hat{T}(\delta t)|t\rangle
=|t+\delta t\rangle
$$

---

### 2. Shifting operator - Position

이 내용은 위와 동일하다. 위치와 파수의 대응관계를 명확하게 이해하고 위와 동일하게 적용해보자.

$$
\langle x|e^{-iak}f(k)\rangle
=\langle x-i\cdot -ia| f\rangle
=\langle x-a| f\rangle
$$

연산자 형태로 바꿔보자.

$$
\langle x|e^{-iak}f(k)\rangle
=\langle x|e^{-ia\hat{k}}|f\rangle
=\langle x|\hat{P}(a)|f\rangle
$$

위 2개의 식을 비교하자.

$$
\hat{P}(a)=e^{-ia\hat{k}}
$$

$$
\langle x|\hat{P}(a)
=\langle x|e^{-ia\hat{k}}
=\langle x-a|,\quad
\hat{P}^{\dagger}(a)|t\rangle
=e^{ia\hat{k}^{\dagger}}|x\rangle
=|x-a\rangle
$$

주파수는 물리량 이므로, 파수 연산자는 Hermitian 이다. 따라서,

$$
\hat{P}(a)\hat{P}^{\dagger}(a)
=e^{-ia\hat{k}}e^{ia\hat{k}^{\dagger}}
=\hat{I}
$$

위 식으로 부터 병진연산자는 Unitary 연산자임을 알 수 있다. 운동량 공간으로 확장해보자.

$$
\hat{P}(\epsilon)
=e^{-\frac{i}{\hbar}\epsilon\hat{p}},\quad
\hat{P}(\epsilon)|x\rangle
=|x+\epsilon\rangle
$$

---

### 3. Momentum & Position operators

**(1) 위치 공간에 대한 운동량 연산자**

$$
\langle x|kf(k)\rangle
=\langle x|\hat{k}|f\rangle
=-i\frac{d}{dx}\langle x|f\rangle
$$

파수 연산자는 hermitian 이다. 위치공간에서 파수 연산자는 

$$
-i\frac{d}{dx}\langle x|=\langle x|\hat{k},\quad
i\frac{d}{dx}|x\rangle=\hat{k}|x\rangle
$$

따라서, 위치 공간에서 운동량 연산자는 다음과 같이 대응된다.

$$
-i\hbar\frac{d}{dx}\langle x|=\langle x|\hat{p},\quad
i\hbar\frac{d}{dx}|x\rangle=\hat{p}|x\rangle
$$

ℹ️ 주의사항

$$
\left(\frac{d}{dx}\langle x|\right)^\dagger
=\frac{d}{dx}|x\rangle,\quad
\left(\frac{d}{dx}\right)^\dagger
=-\frac{d}{dx}
$$

**(2) 운동량 공간에 대한 위치 연산자**

$$
\langle k|xf(x)\rangle
=\langle k|\hat{x}|f\rangle
=i\frac{d}{dk}\langle k|f\rangle
$$

위치 연산자는 hermitian 이다. 파수 공간에서 위치 연산자는 

$$
i\frac{d}{dk}\langle k|=\langle k|\hat{x},\quad
-i\frac{d}{dk}|k\rangle=\hat{x}|k\rangle
$$

따라서, 운동량 공간에서 위치 연산자는 다음과 같이 대응된다.

$$
i\hbar\frac{d}{dp}\langle p|=\langle p|\hat{x},\quad
-i\hbar\frac{d}{dp}|p\rangle=\hat{x}|p\rangle
$$

---

### 4. 슈뢰딩거 파동 방정식의 유도

시간 진화 연산자로 부터 시작해보자.

$$
\hat{T}(t+\delta t,t)
=e^{-\frac{i}{\hbar}\delta t\hat{H}}=\hat{I}-\frac{i}{\hbar}\hat{H}\delta t,
$$

$$
\hat{T}(t+\delta t,t)|\Psi(t)\rangle
=|\Psi(t+\delta t)\rangle\implies|\Psi(t)\rangle-\frac{i}{\hbar}\hat{H}\delta t|\Psi(t)\rangle=|\Psi(t+\delta t)\rangle
$$

$$
-\frac{i}{\hbar}\hat{H}\delta t|\Psi(t)\rangle=|\Psi(t+\delta t)\rangle-|\Psi(t)\rangle
$$

$$
\hat{H}|\Psi(t)\rangle=i\hbar \frac{|\Psi(t+\delta t)\rangle-|\Psi(t)\rangle}{\delta t}
=i\hbar \frac{d}{dt}|\Psi(t)\rangle
$$

