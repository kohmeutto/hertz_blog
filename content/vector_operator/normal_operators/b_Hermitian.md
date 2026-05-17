+++
title = "(b) Hermitian"
weight = 2
+++

---

## 1. 허미션 연산자 (Hermitian Operator)

**정의**: 연산자 $\hat{A}$가 자신의 허미션 켤레($\hat{A}^\dagger$)와 같을 때, 즉 $\hat{A} = \hat{A}^\dagger$일 때, 이를 에르미트 연산자라고 한다. 이는 정규 연산자($[\hat{A}, \hat{A}^\dagger]=0$)의 조건을 자명하게 만족한다.

**물리적 의미**: 양자역학에서 **측정 가능한 모든 물리량(Observable)**, 예를 들어 에너지, 위치, 운동량 등은 반드시 에르미트 연산자로 표현된다.

---
### 핵심 특성 및 증명

**1. 고유값은 항상 실수이다.**

> **증명**:
> 1. $\hat{A}|v\rangle = \lambda|v\rangle$ 에서, 양변에 $\langle v|$를 내적하면 $\langle v|\hat{A}|v\rangle = \lambda\langle v|v\rangle$ 이다.
> 2. 위 식의 에르미트 켤레를 취하면 $(\langle v|\hat{A}|v\rangle)^\dagger = (\lambda\langle v|v\rangle)^\dagger$ 이다.
> 3. $(\hat{A}|v\rangle)^\dagger = \langle v|\hat{A}^\dagger$ 이므로, $\langle v|\hat{A}^\dagger|v\rangle = \lambda^*\langle v|v\rangle$ 이다.
> 4. $\hat{A} = \hat{A}^\dagger$ 이므로, $\langle v|\hat{A}|v\rangle = \lambda^*\langle v|v\rangle$ 이다.
> 5. 1번과 4번 결과를 비교하면 $\lambda\langle v|v\rangle = \lambda^*\langle v|v\rangle$ 이고, $\langle v|v\rangle \neq 0$ 이므로 $\lambda=\lambda^*$ 이다. 따라서 고유값 $\lambda$는 실수이다.

**2. 서로 다른 고유값의 고유벡터는 직교한다.**

> **증명**: (1.3절의 보조정리 2에서 증명된 내용) $\hat{A}$가 에르미트 연산자이고 고유값이 실수라는 조건을 사용하면, 서로 다른 고유값에 해당하는 고유벡터들은 항상 서로 수직임이 증명된다.

---
### 예제

#### 1. 파울리 스핀 행렬 $\sigma_y$
$$
\sigma_y = \begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix}
$$
- **에르미트 확인**: $\sigma_y^\dagger = (\sigma_y^*)^T = \begin{pmatrix} 0 & i \\ -i & 0 \end{pmatrix}^T = \begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix} = \sigma_y$.
- **고유값**: $\det(\sigma_y - \lambda I) = \lambda^2 - 1 = 0 \implies \lambda = 1, -1$ (실수).
- **고유벡터**:
    - $\lambda=1$: $|v_1\rangle \rightarrow \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ i \end{pmatrix}$
    - $\lambda=-1$: $|v_2\rangle \rightarrow \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ -i \end{pmatrix}$
- **직교성 확인**: $\langle v_1|v_2\rangle = \frac{1}{2}\begin{pmatrix} 1 & -i \end{pmatrix}\begin{pmatrix} 1 \\ -i \end{pmatrix} = \frac{1}{2}(1 - 1)=0$.

#### 2. 운동량 연산자 (함수 공간)
- **연산자**: $\hat{P} = -i\hbar\frac{d}{dx}$
- **에르미트 확인**: 부분적분을 통해 (함수가 무한대에서 0이 된다는 가정 하에) $\langle f|\hat{P}|g\rangle = \langle \hat{P}f|g\rangle$ 임을 보일 수 있다.
- **고유함수 및 고유값**: $\hat{P}e^{ikx} = (\hbar k)e^{ikx}$.
    - 고유함수는 평면파 $e^{ikx}$이다.
    - 고유값(측정 가능한 운동량)은 $\hbar k$이며, $k$가 실수이므로 항상 실수이다.

---

### 4. Decomposition of Operators

임의의 연산자 $\hat{A}$는 복잡하고 혼란스러워 보일 수 있다. 그러나 수반 연산자($\hat{A}^\dagger$)라는 거울을 이용하면, 모든 연산자는 예외 없이 질서를 상징하는 대칭 성분과 변화를 상징하는 반대칭 성분으로 유일하게 분해된다. 이를 카르테시안 분해(Cartesian Decomposition) 또는 **토플리츠 분해(Toeplitz Decomposition)** 라고 한다.

임의의 연산자 $\hat{A}$를 에르미트 부분($\hat{H}$)과 반-에르미트 부분($\hat{S}$)의 합으로 정의하자.

$$
\hat{A} = \hat{H} + \hat{S}
$$

이때, $\hat{H}$는 에르미트 성질($\hat{H}^\dagger = \hat{H}$)을, $\hat{S}$는 반-에르미트 성질($\hat{S}^\dagger = -\hat{S}$)을 가져야 한다. 수반 연산자의 성질을 이용해 양변에 수반 작용을 가하면,

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