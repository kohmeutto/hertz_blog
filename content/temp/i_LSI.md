+++
title = "(i) LSI"
weight = 1
+++

---

**LSI 연산자 정리**

(1) $\hat{H}|x'\rangle=|h(x-x')\rangle$

(2) $\hat{H}=|h\rangle\ast=\int dx' |h(x-x')\rangle\langle x'|$

(3) $\hat{H}=|h\rangle\ast=\int ds H(s)|s\rangle\langle s|$

---

### 1. LSI

LSI operator(system) 이 가지는 특성은 아래와 같다.

**(1) Linearity(선형성)=Superpostion**

Superposition은 Linearity 와 동치이다. 따라서, 두가지 용어를 system 에서 혼용해서 사용해도 같은 의미임을 상기하라.

$$
\text{Superposition}=\text{Addictivity}+\text{Scaling}
$$

$$
\hat{H}(a|\psi_1\rangle+b|\psi_2\rangle)
=a\hat{H}|\psi_1\rangle+b\hat{H}|\psi_2\rangle
$$

**(2) Shift invarient**

- 이동 불변 시스템이란 시스템을 작동시키는 근본적인 규칙(rule)이 이동(시간,공간) 등에 따라 변하지 않는다는 의미한다. 
- 따라서 동일한 모양의 입력을 언제 넣든지 상관없이, 출력은 항상 **똑같은 모양으로 나온다.**
- '똑같은 모양으로 나온다.'의 의미는 단지 출력이 나오는 시간만 입력이 들어간 시간에 맞춰 **평행 이동**할 뿐이다.

$$
|\varphi(t-\tau)\rangle=\hat{H}|\psi(t-\tau)\rangle
$$

proof)

$|\varphi(t)\rangle=\hat{H}|\psi(t)\rangle$라고 하자.

$$
\hat{H}|\psi(t-\tau)\rangle
=\hat{H}\hat{S}_\tau|\psi(t)\rangle
$$

이동 불변은 시스템(연산자)과 이동 연산자와 교환 가능을 의미하므로,

$$
\hat{S}_\tau\hat{H}|\psi(t)\rangle
=\hat{S}_\tau\hat{H}|\psi(t)\rangle
=\hat{S}_\tau|\varphi(t)\rangle
=|\varphi(t-\tau)\rangle
$$

만약, $t_0\ne t_1$ 라고 하자.

$$
|\varphi(t-t_1\rangle=\hat{H}|\psi(t-t_0)\rangle
$$

이것은 이동 불변성을 만족하지 않는다.

---

### 2. LSI 연산자

아래 형태는 선형이기만 하면 어떤 변환이든 표현할 수 있다. 하지만 아직 이동 불변(Shift-Invariance) 조건은 포함하지 않았다.

$$
\hat{H}=\int dx' |h(x,x')\rangle \langle x'|
$$

이 일반적인 형태에 **"LSI 시스템"** 이라는 강력한 제약 조건을 걸어본다. 이동 불변은 위에서 보다 싶이, 평행이동을 의미한다.

$$
\hat{H}=\int dx' |h(x-x')\rangle \langle x'|
$$

임펄스 기저와의 연산을 수행해보자.

$$
\hat{H}|\tau\rangle
=\int dx' |h(x-x') \rangle\langle x' |\tau\rangle
=\int dx' |h(x-x') \rangle\delta(x'-\tau)
=|h(x-\tau) \rangle
$$

---

### 3.모든 LSI 연산자는 합성곱 귀결된다.

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

### 4. 연산자의 합성

이 내용은 선형 부품(작은 선형 시스템)이 모였을 때 만들어지는 회로 전체(큰 시스템)을 왜 선형시스템으로 볼 수 있는지에 대한 설명이 가능하다.

**(1) 선형연산자 + 선형연산자 = 선형연산자**

- 직렬합성(Series Combination)

$$
\hat{T}=\hat{L}_2\hat{L}_1
$$

$$
\hat{T}(a_1|\psi_1\rangle+a_2|\psi_2\rangle)=\hat{L}_2\hat{L}_1(a_1|\psi_1\rangle+a_2|\psi_2\rangle)
$$

$$
=\hat{L}_2(a_1\hat{L}_1|\psi_1\rangle+a_2\hat{L}_1|\psi_2\rangle)
$$

$$
=a_1\hat{L}_2\hat{L}_1|\psi_1\rangle+a_2\hat{L}_2\hat{L}_1|\psi_2\rangle
$$

$$
=a_1\hat{T}_1|\psi_1\rangle+a_2\hat{T}_1|\psi_2\rangle
$$

- 병렬합성(Parallel Combination)

$$
\hat{T}=\hat{L}_1+\hat{L}_2
$$

$$
\hat{T}(a_1|\psi_1\rangle+a_2|\psi_2\rangle)=(\hat{L}_1+\hat{L}_2)(a_1|\psi_1\rangle+a_2|\psi_2\rangle)
$$

$$
=(a_1\hat{L}_1|\psi_1\rangle+a_2\hat{L}_1|\psi_2\rangle)+(a_1\hat{L}_2|\psi_1\rangle+a_2\hat{L}_2|\psi_2\rangle)
$$

$$
=a_1(\hat{L}_1+\hat{L}_2)|\psi_1\rangle+a_2(\hat{L}_1+\hat{L}_2)|\psi_2\rangle
$$

$$
=a_1\hat{T}_1|\psi_1\rangle+a_2\hat{T}_1|\psi_2\rangle
$$

**(2) 선형연산자 + 비선형연산자 = 비선형연산자**

- 직렬합성(Series Combination)

$$
\hat{T}=\hat{L}\hat{N}
$$

$$
\hat{T}(a_1|\psi_1\rangle+a_2|\psi_2\rangle)=\hat{L}\hat{N}(a_1|\psi_1\rangle+a_2|\psi_2\rangle)
$$

$$
\ne a_1\hat{T}_1|\psi_1\rangle+a_2\hat{T}_1|\psi_2\rangle
$$

- 병렬합성(Parallel Combination)

$$
\hat{T}=\hat{L}+\hat{N}
$$

$$
\hat{T}(a_1|\psi_1\rangle+a_2|\psi_2\rangle)=(\hat{L}+\hat{N})(a_1|\psi_1\rangle+a_2|\psi_2\rangle)
$$

$$
=(a_1\hat{L}|\psi_1\rangle+a_2\hat{L}|\psi_2\rangle)+\hat{N}(a_1|\psi_1\rangle+a_2|\psi_2\rangle)
$$

$$
\ne a_1\hat{T}_1|\psi_1\rangle+a_2\hat{T}_1|\psi_2\rangle
$$

---

**example)** $|f\rangle+$ 연산자는 선형인가.