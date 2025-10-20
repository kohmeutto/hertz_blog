+++
title = "(b) Syntax"
weight = 5
+++

---

### 1. 규칙과 관습

**(1) 기호의 병치는 '결과'에 대한 별명으로 허용된다.**

- OK: $\hat{A}|\psi\rangle=|A\psi\rangle$
- OK: $\hat{U}|\psi\rangle=|U\psi\rangle$

**(2) 함수 인자(매개변수)는 허용된다.**

일반적으로

- OK: $|\psi(t)\rangle$
- OK: $|\psi(x)\rangle$

**(3) bar 안의 매개변수와 ket안의 매개변수가 중복되면 안된다.**

- NG: $\langle t|\psi(t)\rangle$
- OK: $\langle x'|\psi(x)\rangle$

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


