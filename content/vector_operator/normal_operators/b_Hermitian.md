+++
title = "(b) Hermitian"
weight = 20
+++

---

## 1. 허미션 연산자 (Hermitian Operator)

**1) 정의**

연산자 $\hat{A}$가 자신의 허미션 켤레($\hat{A}^\dagger$)와 같을 때, 즉 $\hat{A} = \hat{A}^\dagger$일 때, 이를 허미션 연산자라고 한다. 이는 정규 연산자($[\hat{A}, \hat{A}^\dagger]=0$)의 조건을 자명하게 만족한다.

**2) 물리적 의미**

양자역학에서 **측정 가능한 모든 물리량(Observable)**, 예를 들어 에너지, 위치, 운동량 등은 반드시 허미션 연산자로 표현된다.

---

### 2. 고유값은 항상 실수이다

허미션 연산자의 모든 고유값 $\lambda$는 허수부가 0인 실수(Real number)이다.

$$
\lambda = \lambda^\ast
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

정의에 의해 $\hat{A} = \hat{A}^\dagger$이므로, 좌변의 연산자를 원래대로 치환할 수 있다.

$$
\langle \lambda|\hat{A}|\lambda\rangle = \lambda^\ast\langle \lambda|\lambda\rangle
$$

최초에 도출한 스칼라 내적 방정식과 위 방정식을 상호 대조하여 차감한다.

$$
\lambda\langle \lambda|\lambda\rangle = \lambda^\ast\langle \lambda|\lambda\rangle
$$

$$
(\lambda - \lambda^\ast)\langle \lambda|\lambda\rangle = 0
$$

고유벡터는 영벡터가 아니므로, 그 노름의 제곱인 $\langle \lambda|\lambda\rangle$는 0이 될 수 없다. 따라서 이 방정식이 항등적으로 성립하기 위한 유일한 조건은 다음과 같다.

$$
\lambda - \lambda^\ast = 0 \implies \lambda = \lambda^\ast
$$

결론적으로, 대수적 연역에 의하여 허미션 연산자의 모든 고유값은 실수 영역에만 존재함이 증명된다.

---

### 3. 예

**1) 파울리 스핀 행렬 $\sigma_y$**

$$
\sigma_y = \begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix}
$$

(1) 허미션 확인

$$
\sigma_y^\dagger = (\sigma_y^*)^T = \begin{pmatrix} 0 & i \\ -i & 0 \end{pmatrix}^T = \begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix} = \sigma_y
$$

(2) 고유값

$$
\det(\sigma_y - \lambda I) = \lambda^2 - 1 = 0 \implies \lambda = 1, -1
$$

(3) 고유벡터

$$
\lambda=1 \text{:} \quad |v_1\rangle \rightarrow \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ i \end{pmatrix}
$$

$$
\lambda=-1 \text{:} \quad |v_2\rangle \rightarrow \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ -i \end{pmatrix}
$$

(4) 직교성 확인

$$
\langle v_1|v_2\rangle = \frac{1}{2}\begin{pmatrix} 1 & -i \end{pmatrix}\begin{pmatrix} 1 \\ -i \end{pmatrix} = \frac{1}{2}(1 - 1)=0
$$

**2) 운동량 연산자 (함수 공간)**

$$
\hat{P} = -i\hbar\frac{d}{dx}
$$

(1) 허미션 확인

부분적분을 통해 (함수가 무한대에서 0이 된다는 가정 하에, $\mathcal{R}\hat{P}=0$), 아래임을 보일 수 있다.

$$
\langle f|\hat{P}|g\rangle = \langle \hat{P}f|g\rangle
$$


(2) 고유함수 및 고유값

$$
\hat{P}e^{ikx} = (\hbar k)e^{ikx}
$$

- 고유함수: $e^{ikx}$
- 고유값(측정 가능한 운동량): $\hbar k$이며, $k$가 실수이므로 항상 실수이다.
