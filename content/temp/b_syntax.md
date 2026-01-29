+++
title = "(b) Syntax"
weight = 5
+++

---

### 1. 규칙과 관습

**(1) 기호의 병치는 '결과'에 대한 별명으로 허용된다.**

스칼라나 모자가 없는 연산자 기호를 Ket 이름에 붙여 쓰는 것은, 연산이 끝난 후의 결과 벡터에 대한 별명으로 관용적으로 허용된다.

- OK: $a|\psi\rangle=|a\psi\rangle$
- OK: $U|\psi\rangle=|U\psi\rangle$

**(2) 함수 인자에 대한 연산은 이름표 내부에서 허용된다.**

일반저그로

- OK: $|\psi(t+a)\rangle=\hat{T}(-a)|\psi\rangle$

|f(t+a)⟩와 같은 표현이 허용되는 이유는, + 연산이 벡터 |f⟩에 작용하는 것이 아니라, 이름표로 사용된 함수 f의 **입력 인자(argument) t** 에 작용하기 때문이다. 이것은 이동 연산자 T̂(-a)가 |f⟩에 작용한 결과 벡터에 대한 별명이다.

---

### 2. Bra

**(1) 스칼라 곱**

$$
\langle a\psi|=a^\ast\langle\psi|
$$

proof)

$$
\langle a\psi|=(a|\psi\rangle)^\dagger=a^\ast\langle \psi|
$$

**(2) 연산자**

$$
\langle U\psi|=\langle\psi|U^\dagger
$$

proof)

$$
\langle U\psi|=(U|\psi\rangle)^\dagger=\langle \psi|U^\dagger
$$


---

**(1) 연산은 항상 Ket/Bra의 바깥에서 이루어진다.**

수학적 연산을 나타내는 기호는 이름표 안으로 들어가지 않는다. 그러나 단순히 +와 같은 것을 연산자가 아닌 문자로서만 인식한다면 가능하다.

- OK: $|a\rangle+|b\rangle$
- NG:  $|a+b\rangle$

**(2) '모자(^)' 기호는 공식적인 '연산자' 선언이다.**

연산자 기호 Â는 Ket의 이름표 안으로 들어가지 않는 것이 엄격한 관습이다. 위 (1)에서 보다싶이, 모자(^)는 연산자의 선언이므로 이름표 안으로 들어가지 않는다.

- OK: $\hat{A}|\psi\rangle$
- NG: $|\hat{A}\psi\rangle$