+++
title = "(b) Convolution I"
weight = 2
+++

---

**LSI 연산자 정리**

(1) $\hat{H}|x'\rangle=|h(x-x')\rangle$

(2) $\hat{H}=|h\rangle\ast=\int dx' |h(x-x')\rangle\langle x'|$

(3) $\hat{H}=|h\rangle\ast=\int ds H(s)|s\rangle\langle s|$

---


### 1. 대표적인 LSI operators

LSI(선형 이동 불변) 연산자의 대표적인 (일부)예시들은 다음과 같다. **예외 없이 모든 LSI 연산자들은 합성곱(Convolution)으로 표현** 될 수 있다는 공통점을 가진다.

- 미분 (Differentiation)

$$
|\psi'\rangle=\hat{D}|\psi\rangle
$$

$$
\psi'(x)=\langle x|\psi'\rangle=\langle x|\hat{D}|\psi\rangle=\frac{d}{dx}\psi(x)
$$


- 적분 (Integration)

$$
|g\rangle=\hat{D}^{-1}|f\rangle
$$

$$
g(x)=\langle x|g\rangle=\langle x|\hat{D}^{-1}|f\rangle=\int dx f(x)
$$

- 이동 (Shift / Delay)

$$
|\psi(t-\tau)\rangle=\hat{S}_{\tau}|\psi(t)\rangle
$$

- 스케일링 (Scaling)

$$
|a\psi\rangle=a|\psi\rangle
$$

---

### 2. 모든 LSI 연산자는 합성곱 귀결된다.

어떤 신호 $|\psi\rangle$든, 그 신호는 모든 순간의 임펄스(impulse) 기저 $|\tau\rangle$들의 연속적인 합(적분)으로 표현할 수 있다. 이는 디랙 델타 함수의 기본 성질이다.

$$
|\psi\rangle=\int_{-\infty}^{\infty}d\tau \psi(\tau)|\tau\rangle
$$

임의의 LSI 연산자 $\hat{H}$를 적용한다.

$$
|\varphi\rangle
=\hat{H}|\psi\rangle
=\hat{H}\left(\int_{-\infty}^{\infty}d\tau \psi(\tau)|\tau\rangle\right)
$$

연산자 $\hat{H}$의 선형성을 사용한다.

$$
|\varphi\rangle
=\int_{-\infty}^{\infty}d\tau \psi(\tau) \hat{H}|\tau\rangle
$$

연산자 $\hat{H}$의 시불변을 사용한다. 

$$
|\tau\rangle=\hat{S}_\tau|0\rangle 
$$

$$
|\varphi\rangle
=\int_{-\infty}^{\infty}d\tau \psi(\tau) \hat{H}\hat{S}_\tau|0\rangle
$$

이동연산자와 교환가능하므로,

$$
|\varphi\rangle
=\int_{-\infty}^{\infty}d\tau \psi(\tau) \hat{S}_\tau\hat{H}|0\rangle
$$

$\hat{S}_\tau\hat{H}|0\rangle$은 임펄스 응답 $\hat{H}|0\rangle=|h(t)\rangle$에 대한 $\tau$만큼의 이동변환을 의미한다. 따라서,

$$
|\varphi\rangle
=\int_{-\infty}^{\infty}d\tau \psi(\tau) |h(t-\tau)\rangle
=|\psi\rangle\ast|h\rangle
=|\psi\ast h\rangle
$$

이로써, 모든 LSI 연산자의 입출력 관계는 입력과 임펄스 응답의 합성곱이라는 단 하나의 형태로 귀결됨이 증명되었다.

---

**example)** $|f\rangle+$ 연산자는 선형인가.