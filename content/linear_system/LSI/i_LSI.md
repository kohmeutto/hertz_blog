+++
title = "(i) LSI"
weight = 1
+++

---

### 1. LSI

Linear + Shift Invariance

---

### 2. Linearity(선형성)=Superpostion

Superposition은 Linearity 와 동치이다. 따라서, 두가지 용어를 system 에서 혼용해서 사용해도 같은 의미임을 상기하라.

$$
\text{Superposition}=\text{Addictivity}+\text{Scaling}
$$

$$
\hat{H}(a|\psi_1\rangle+b|\psi_2\rangle)
=a\hat{H}|\psi_1\rangle+b\hat{H}|\psi_2\rangle
$$

---

### 3. Copy-shift invariance

- 이동 불변 시스템이란 시스템을 작동시키는 근본적인 규칙(rule)이 이동(시간,공간) 등에 따라 변하지 않는다는 의미한다. 
- 따라서 동일한 모양의 입력을 언제 넣든지 상관없이, 출력은 항상 **똑같은 모양으로 나온다.**
- LSI 연산자는 copy-shift 연산자와 **교환가능함** 을 의미한다.

$$
[\hat{H},\hat{S}_{\tau}]
\implies
\hat{S}_\tau\hat{H}=\hat{H}\hat{S}_\tau
$$

- '똑같은 모양으로 나온다.'의 의미는 단지 출력이 **평행 이동**할 뿐이다.

$$
h(u-\tau,u)=h(u,u+\tau)\implies h(u,\tau)=h(u-\tau)
$$

proof)

임펄스 응답으로 전개해 본다.

$$
\langle u^d|\hat{S}_\tau\hat{H}|u'\rangle
=\langle (u-\tau)^d|\hat{H}|u'\rangle
=h(u-\tau, u')
$$

$$
\langle u^d|\hat{H}\hat{S}_\tau|u'\rangle
=\langle u^d|\hat{H}|u'+\tau\rangle
=h(u,u'+\tau)
$$

따라서,

$$
h(u-\tau,u')=h(u,u'+\tau)\implies
h(x,y)=h(x+s,y+s)
$$

여기에서 어떤 $s$를 선택해도, 위 식은 반드시 만족해야 한다. $s$에 $-y$를 대입하면,


$$
h(x,y)=h(x-y,0)
$$

함수 $h$ 의 값은, 첫 번째 인자가 $x-y$ 이고 두 번째 인자가 $0$일 때의 값과 항상 같다. 즉, 함수 $h$ 의 값은 오직 $x-y$ 라는 **차이 값에만 의존한다** 는 것이 증명되었다.

---

### 3.모든 LSI 연산자는 합성곱 귀결된다.

LSI(선형 이동 불변) 연산자의 대표적인 (일부)예시들은 다음과 같다. **"예외 없이 모든" LSI 연산자들은 합성곱(Convolution)으로 표현** 될 수 있다는 공통점을 가진다.

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
\hat{S}_{\tau}|\psi(t)\rangle
$$

- 진폭 스케일링 (Amplitude scaling)

$$
|a\psi\rangle=a|\psi\rangle
$$

---

### 4. Convolution의 유도

아래 형태는 선형이기만 하면 어떤 변환이든 표현할 수 있다. 하지만 아직 이동 불변(Shift-Invariance) 조건은 포함하지 않았다.

$$
\hat{H}=\iint du du' h(u,u')|u\rangle\langle u'^d|
$$

이 일반적인 형태에 **"LSI 시스템"** 이라는 강력한 제약 조건을 걸어본다. 이동 불변은 위에서 보다 싶이, 평행이동을 의미한다.

$$
\hat{H}
=\iint du'' du' h(u''-u')|u''\rangle\langle u'^d|
$$

임의의 벡터와 연산을 수행해보자.

$$
\langle u^d|\hat{H}|f\rangle
=\iint du'' du' h(u''-u')\delta(u-u'')f(u')
=\int du' h(u-u') f(u')
$$

$$
=:h(u)\ast f(u)
=\langle u^d|(|h\rangle\ast|f\rangle)
=\langle u^d|(|h\rangle\ast)|f\rangle
$$

따라서,

$$
\hat{H} = |h\rangle\ast
$$

---

### 5. 연산자의 합성

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

**example1)** $|f\rangle+$ 연산자는 선형인가.

**example2)** 미분 연산자를 컨볼루션으로 표현하라.

**example3)** 적분 연산자를 컨볼루션으로 표현하라.