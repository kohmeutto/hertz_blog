+++
title = "(b) M-Hermitian"
weight = 4
+++

---

### 1. M-허미션 연산자 (M-Hermitian Operator)

연산자 $\hat{A}$가 자신의 $\hat{M}$-수반 연산자 $\hat{A}^\sharp$와 같을 때, 이를 **M-허미션 연산자**라고 정의한다.

$$
\hat{A} = \hat{A}^\sharp
$$

---

### 2. M-허미션의 고유값은 항상 실수이다

M-허미션 연산자의 모든 고유값 $\lambda$는 허수부가 0인 실수(Real number)이다.

$$
\lambda = \lambda^\ast
$$

proof)

임의의 고유값 $\lambda$와 영벡터가 아닌 고유벡터 $|\lambda\rangle$에 대하여, 다음의 우측 고유방정식이 성립한다.

$$
\hat{A}|\lambda\rangle = \lambda|\lambda\rangle
$$

위 식의 양변 좌측에 브라 벡터 $\langle \lambda | \hat{M}$을 내적하여 $\hat{M}$-내적 스칼라 방정식을 도출한다.

$$
\langle \lambda | \hat{M}\hat{A} | \lambda \rangle = \lambda \langle \lambda | \hat{M} | \lambda \rangle
$$

이 스칼라 방정식 전체에 허미션 켤레(복소 공액)를 취한다. 내적의 공리인 $\langle \psi | \phi \rangle^\ast = \langle \phi | \psi \rangle$ 및 연산자의 켤레 법칙을 적용한다.

$$
(\langle \lambda | \hat{M}\hat{A} | \lambda \rangle)^\ast = (\lambda \langle \lambda | \hat{M} | \lambda \rangle)^\ast
$$

$$
\langle \lambda | \hat{A}^\dagger\hat{M} | \lambda \rangle = \lambda^\ast \langle \lambda | \hat{M} | \lambda \rangle
$$

정의에 의해 $\hat{M}\hat{A} = \hat{A}^\dagger\hat{M}$이므로, 좌변의 연산자를 치환한다.

$$
\langle \lambda | \hat{M}\hat{A} | \lambda \rangle = \lambda^\ast \langle \lambda | \hat{M} | \lambda \rangle
$$

최초에 도출한 스칼라 내적 방정식과 위 방정식을 대조하여 차감한다.

$$
\lambda\langle \lambda | \hat{M} | \lambda \rangle = \lambda^\ast\langle \lambda | \hat{M} | \lambda \rangle
$$

$$
(\lambda - \lambda^\ast)\langle \lambda | \hat{M} | \lambda \rangle = 0
$$

고유벡터는 영벡터가 아니며 계량 연산자 $\hat{M}$은 양의 정부호($\hat{M} > 0$)이므로, $\hat{M}$-노름의 제곱인 $\langle \lambda | \hat{M} | \lambda \rangle$는 0이 될 수 없다. 따라서 방정식이 성립하기 위한 조건은 다음과 같다.

$$
\lambda - \lambda^\ast = 0 \implies \lambda = \lambda^\ast
$$

M-허미션 연산자의 모든 고유값은 실수 영역에 존재한다.

---

### 3. M-반-허미션 연산자 ($\hat{M}$-anti-Hermitian Operator)

연산자 $\hat{A}$가 자신의 $\hat{M}$-수반 연산자 $\hat{A}^\sharp$에 음의 부호를 붙인 것과 같을 때, 즉 다음 조건을 만족할 때 이를 **$\hat{M}$-반-허미션 연산자**라고 정의한다.

$$
\hat{A}^\sharp = -\hat{A}
$$

---

### 4. M-반-허미션 연산자 고유값은 항상 순수 허수이거나 0이다

$\hat{M}$-반-허미션 연산자의 모든 고유값 $\lambda$는 실수부가 0인 순수 허수(Pure imaginary number)이거나 0이다.

$$
\lambda = -\lambda^\ast
$$

proof)

임의의 고유값 $\lambda$와 영벡터가 아닌 고유벡터 $|\lambda\rangle$에 대하여, 다음의 우측 고유방정식이 성립한다.

$$
\hat{A}|\lambda\rangle = \lambda|\lambda\rangle
$$

위 식의 양변 좌측에 브라 벡터 $\langle \lambda | \hat{M}$을 내적하여 $\hat{M}$-내적 스칼라 방정식을 도출한다.

$$
\langle \lambda | \hat{M}\hat{A} | \lambda \rangle = \lambda \langle \lambda | \hat{M} | \lambda \rangle
$$

이 스칼라 방정식 전체에 허미션 켤레(복소 공액)를 취한다. 내적의 공리인 $\langle \psi | \phi \rangle^\ast = \langle \phi | \psi \rangle$ 및 연산자의 켤레 법칙을 적용한다.

$$
(\langle \lambda | \hat{M}\hat{A} | \lambda \rangle)^\ast = (\lambda \langle \lambda | \hat{M} | \lambda \rangle)^\ast
$$

$$
\langle \lambda | \hat{A}^\dagger\hat{M} | \lambda \rangle = \lambda^\ast \langle \lambda | \hat{M} | \lambda \rangle
$$

정의에 의해 $-\hat{M}\hat{A} = \hat{A}^\dagger\hat{M}$이므로, 좌변의 연산자를 치환한다.

$$
\langle \lambda | (-\hat{M}\hat{A}) | \lambda \rangle = \lambda^\ast \langle \lambda | \hat{M} | \lambda \rangle
$$

$$
-\langle \lambda | \hat{M}\hat{A} | \lambda \rangle = \lambda^\ast \langle \lambda | \hat{M} | \lambda \rangle
$$

최초에 도출한 스칼라 내적 방정식($\langle \lambda | \hat{M}\hat{A} | \lambda \rangle = \lambda \langle \lambda | \hat{M} | \lambda \rangle$)을 좌변에 대입한다.

$$
-\lambda\langle \lambda | \hat{M} | \lambda \rangle = \lambda^\ast\langle \lambda | \hat{M} | \lambda \rangle
$$

$$
(\lambda + \lambda^\ast)\langle \lambda | \hat{M} | \lambda \rangle = 0
$$

고유벡터는 영벡터가 아니며 계량 연산자 $\hat{M}$은 양의 정부호($\hat{M} > 0$)이므로, $\hat{M}$-노름의 제곱인 $\langle \lambda | \hat{M} | \lambda \rangle$는 0이 될 수 없다. 따라서 방정식이 성립하기 위한 유일한 조건은 다음과 같다.

$$
\lambda + \lambda^\ast = 0 \implies \lambda = -\lambda^\ast
$$
