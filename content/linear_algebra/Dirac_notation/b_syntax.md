+++
title = "(b) Syntax"
weight = 5
+++

---

### 1. 규칙과 관습

**(1) 기호의 병치는 '결과'에 대한 별명으로 허용된다.**

- OK: $\hat{A}|\psi\rangle=|A\psi\rangle$
- OK: $\hat{U}|\psi\rangle=|U\psi\rangle$

**(2)  벡터 값 함수라는 별도의 엄격한 정의 하에서만 사용된다.**

- OK: $|\psi\rangle(t)=|\psi(t)\rangle$
- OK: $|\psi\rangle(x)=|\psi(x)\rangle$

시간 또는 공간의 상태를 나타내기 위해 위와 같은 표기를 관용적으로 사용한다. 예로  $|\psi(t=1)\rangle$ 은 $t=1$에서의 벡터 상태를 나타낸다. $|f\rangle\ne|f(t)\rangle$임을 주의한다.

**(3) bar 안의 매개변수와 ket안의 매개변수가 중복되면 안된다.**

Ket 안의 매개변수는 ket 벡터의 인덱스를 나타내므로 bra 벡터안에 중복되서 쓰면 안된다. 

- NG: $\langle t|\psi(t)\rangle$
- OK: $\langle x'|\psi(x)\rangle$

$\langle t|...$ 에서 $t$는 **측정의 기준이 되는 좌표(basis label)** 를 의미한다. 반면 $...|\psi(t)\rangle$ 에서의 $t$는 **상태 벡터를 결정하는 파라미터(parameter)** 이다. 이 두 가지 다른 역할을 하는 변수에 같은 이름을 부여하면, 수식이 적분 등으로 확장될 때 어떤 t가 적분 변수이고 어떤 t가 자유 변수인지 구분할 수 없게 된다.

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


