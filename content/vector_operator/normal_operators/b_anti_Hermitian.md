+++
title = "(b) anti-Hermitian"
weight = 30
+++

---

## 1. 반-허미션 연산자 (Anti-Hermitian Operator)

**1) 정의**

연산자 $\hat{A}$가 자신의 허미션 켤레($\hat{A}^\dagger$)에 음의 부호를 붙인 것과 같을 때, 즉 $\hat{A}^\dagger = -\hat{A}$일 때, 이를 **반-허미션(또는 스큐-허미션, Skew-Hermitian) 연산자**라고 한다. 이 연산자 역시 정규 연산자($[\hat{A}, \hat{A}^\dagger]=0$)의 조건을 만족한다.

**2) 물리적 의미**

반-허미션 연산자는 직접적으로 물리량을 나타내지는 않지만, 유니타리 변환을 만들어내는 **생성자(Generator)** 로서, 시스템의 동적인 변화를 기술하는 데 핵심적인 역할을 한다.

---

### 2. 고유값은 항상 순수 허수이거나 0이다.

반-허미션 연산자의 모든 고유값 $\lambda$는 실수부가 0인 순수 허수(Pure imaginary number)이거나 0이다.

$$
\lambda = -\lambda^\ast
$$

proof)

임의의 고유값 $\lambda$와 영벡터가 아닌 고유벡터 $|\lambda\rangle$에 대하여, 다음의 우측 고유방정식이 성립한다.

$$
\hat{A}|\lambda\rangle = \lambda|\lambda\rangle
$$

위 식의 양변 좌측에 $\langle \lambda|$를 내적하여 스칼라 방정식을 도출한다.

$$
\langle \lambda|\hat{A}|\lambda\rangle = \lambda\langle \lambda|\lambda\rangle
$$

이 스칼라 방정식 전체에 허미션 켤레(복소 공액)를 취한다. 내적의 공리인 $\langle \psi | \phi \rangle^\ast = \langle \phi | \psi \rangle$ 및 연산자의 켤레 법칙을 적용한다.

$$
(\langle \lambda|\hat{A}|\lambda\rangle)^\ast = (\lambda\langle \lambda|\lambda\rangle)^\ast
$$

$$
\langle \lambda|\hat{A}^\dagger|\lambda\rangle = \lambda^\ast\langle \lambda|\lambda\rangle
$$

정의에 의해 $\hat{A}^\dagger = -\hat{A}$이므로, 좌변의 연산자를 치환한다.

$$
\langle \lambda|(-\hat{A})|\lambda\rangle = \lambda^\ast\langle \lambda|\lambda\rangle
$$

$$
-\langle \lambda|\hat{A}|\lambda\rangle = \lambda^\ast\langle \lambda|\lambda\rangle
$$

최초에 도출한 스칼라 내적 방정식($\langle \lambda|\hat{A}|\lambda\rangle = \lambda\langle \lambda|\lambda\rangle$)을 좌변에 대입한다.

$$
-\lambda\langle \lambda|\lambda\rangle = \lambda^\ast\langle \lambda|\lambda\rangle
$$

$$
(\lambda + \lambda^\ast)\langle \lambda|\lambda\rangle = 0
$$

고유벡터는 영벡터가 아니므로, 그 노름의 제곱인 $\langle \lambda|\lambda\rangle$는 0이 될 수 없다. 따라서 이 방정식이 항등적으로 성립하기 위한 유일한 조건은 다음과 같다.

$$
\lambda + \lambda^\ast = 0 \implies \lambda = -\lambda^\ast
$$

어떤 복소수가 자신의 복소 공액에 마이너스를 붙인 것과 같다는 것은, 그 수의 실수부가 0임을 의미한다.

---

### 3. 허미션 연산자와의 관계

어떤 허미션 연산자 $\hat{H}$에 허수 단위 $i$를 곱한 $i\hat{H}$는 반-허미션 연산자이다.

proof)

$$
(i\hat{H})^\dagger = i^*\hat{H}^\dagger = (-i)(\hat{H}) = -(i\hat{H})
$$

---

### 4. 예

**1) 행렬**

$$
\hat{A} = \begin{pmatrix} 0 & 1 \\ -1 & 0 \end{pmatrix}
$$

(1) 반-허미션 확인

$$
\hat{A}^\dagger = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} = -\hat{A}
$$

(2) 고유값

$$
\det(\hat{A} - \lambda I) = \lambda^2 + 1 = 0 \implies \lambda = i, -i
\quad\text{(순수 허수)}
$$

(3) 고유벡터

$$
\lambda=i \text{:}\quad |v_1\rangle \rightarrow \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ i \end{pmatrix}
$$

$$
\lambda=-i \text{:}\quad |v_2\rangle \rightarrow \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ -i \end{pmatrix}
$$

(4) 직교성 확인

$$
\langle v_1|v_2\rangle = 0
$$

**2) 미분 연산자 (함수 공간)**

$$
\hat{D} = \frac{d}{dx}
$$

(1) 반-허미션 확인

부분적분을 통해,

$$
\hat{D}^\dagger = -\hat{D}
$$

(2) 고유함수 및 고유값

$$
\hat{D}e^{ikx} = (ik)e^{ikx}
$$

- 고유함수는 평면파 $e^{ikx}$이다.
- 고유값은 $ik$이며, $k$가 실수이므로 항상 순수 허수이다.

---

### 4. Decomposition of Operators

임의의 연산자 $\hat{A}$는 복잡하고 혼란스러워 보일 수 있다. 그러나 수반 연산자($\hat{A}^\dagger$)라는 거울을 이용하면, **모든 연산자(비정규 포함)는 예외 없이** 질서를 상징하는 대칭 성분과 변화를 상징하는 반대칭 성분으로 유일하게 분해된다. 이를 카르테시안 분해(Cartesian Decomposition) 또는 **토플리츠 분해(Toeplitz Decomposition)** 라고 한다.

임의의 연산자 $\hat{A}$를 허미션 부분($\hat{H}$)과 반-허미션 부분($\hat{S}$)의 합으로 정의하자.

$$
\hat{A} = \hat{H} + \hat{S}
$$

이때, $\hat{H}$는 허미션 성질($\hat{H}^\dagger = \hat{H}$)을, $\hat{S}$는 반-허미션 성질($\hat{S}^\dagger = -\hat{S}$)을 가져야 한다. 수반 연산자의 성질을 이용해 양변에 수반 작용을 가하면,

$$
\hat{A}^\dagger = (\hat{H} + \hat{S})^\dagger = \hat{H}^\dagger + \hat{S}^\dagger = \hat{H} - \hat{S}
$$

위 두 식을 더하고 빼서 정리하면, 우리는 $\hat{A}$를 구성하는 두 조각의 **유일한 해(Unique Solution)** 를 도출하게 된다.

$$
\text{Hermitian Part: } \hat{H} = \frac{1}{2}(\hat{A} + \hat{A}^\dagger)
$$

$$
\text{Anti-Hermitian Part: } \hat{S} = \frac{1}{2}(\hat{A} - \hat{A}^\dagger)
$$