+++
title = "(b) Normal operators"
weight = 1
+++

---

### 1. 정규 연산자의 정의

연산자 $\hat{A}$가 자신의 에르미트 켤레($\hat{A}^\dagger$)와 교환 가능할 때, 즉 교환자가 0일 때 **정규 연산자(Normal Operator)** 라고 한다.
$$
[\hat{A}, \hat{A}^\dagger] = \hat{A}\hat{A}^\dagger - \hat{A}^\dagger\hat{A} = 0
$$

이 조건을 만족하는 연산자는 **항상 완비적인 정규직교 고유벡터 기저를 가진다는 매우 중요한 특성이 보장** 된다.

---

### 2. 핵심 특성 및 증명

**(1) 특성 1: $\hat{A}$와 $\hat{A}^\dagger$는 고유벡터를 공유한다.**

만약 $|v\rangle$가 정규 행렬 $\hat{A}$의 고유값 $\lambda$에 대한 고유벡터라면, $|v\rangle$는 동시에 $\hat{A}^\dagger$의 고유값 $\lambda^*$에 대한 고유벡터이기도 하다.
 
$$
\hat{A}|v\rangle = \lambda|v\rangle \iff \hat{A}^\dagger|v\rangle = \lambda^*|v\rangle
$$

proof)

$(\hat{A}-\lambda\hat{I})$ 연산자의 노름 제곱 $||(\hat{A}-\lambda\hat{I})|v\rangle||^2$를 계산하면, $\hat{A}$가 정규 행렬이라는 조건 때문에 이 값이 $||(\hat{A}^\dagger-\lambda^*\hat{I})|v\rangle||^2$와 같아짐을 보일 수 있다. 한쪽이 0이면 다른 쪽도 반드시 0이어야 하므로 위 관계가 증명된다.

**(2) 특성 2: 서로 다른 고유값의 고유벡터는 직교한다.**

$$
\hat{A}|v_1\rangle = \lambda_1|v_1\rangle \text{ 이고 } \hat{A}|v_2\rangle = \lambda_2|v_2\rangle \text{ 일 때, } \lambda_1 \neq \lambda_2 \text{ 이면 } \langle v_1|v_2\rangle=0 \text{ 이다.}
$$

proof)

$\langle v_1|\hat{A}|v_2\rangle = \lambda_2\langle v_1|v_2\rangle$ 이다. 또한, **특성 1**을 이용하면 $\langle v_1|\hat{A}|v_2\rangle = \langle \hat{A}^\dagger v_1|v_2\rangle = \langle \lambda_1^*v_1|v_2\rangle = \lambda_1\langle v_1|v_2\rangle$ 이다. 두 결과가 같아야 하므로, $(\lambda_1 - \lambda_2)\langle v_1|v_2\rangle = 0$ 이고, $\lambda_1 \neq \lambda_2$ 이므로 반드시 $\langle v_1|v_2\rangle = 0$ 이어야 한다.

#### **특성 3: 에르미트/반-에르미트 부분의 교환 가능성**

> **정리**: 연산자 $\hat{A}$가 정규 연산자인 것은, 그 에르미트 부분 $\hat{H} = \frac{1}{2}(\hat{A}+\hat{A}^\dagger)$와 반-에르미트 부분 $\hat{S} = \frac{1}{2}(\hat{A}-\hat{A}^\dagger)$가 서로 교환 가능한 것($[\hat{H}, \hat{S}]=0$)과 동치이다.

> **증명**:
> 1. $\hat{A}=\hat{H}+\hat{S}$ 이고 $\hat{A}^\dagger=\hat{H}-\hat{S}$ 이다.
> 2. 교환자 $[\hat{A}, \hat{A}^\dagger]$를 계산한다.
>
$$
\begin{align*}
[\hat{A}, \hat{A}^\dagger] &= (\hat{H} + \hat{S})(\hat{H} - \hat{S}) - (\hat{H} - \hat{S})(\hat{H} + \hat{S}) \\
&= (\hat{H}^2 - \hat{H}\hat{S} + \hat{S}\hat{H} - \hat{S}^2) - (\hat{H}^2 + \hat{H}\hat{S} - \hat{S}\hat{H} - \hat{S}^2) \\
&= -\hat{H}\hat{S} + \hat{S}\hat{H} - \hat{H}\hat{S} + \hat{S}\hat{H} \\
&= 2(\hat{S}\hat{H} - \hat{H}\hat{S}) = 2[\hat{S}, \hat{H}]
\end{align*}
$$
> 3. 따라서 $[\hat{A}, \hat{A}^\dagger]=0$인 것은 $[\hat{S}, \hat{H}]=0$, 즉 $[\hat{H}, \hat{S}]=0$인 것과 동치이다.

#### **특성 4: 연산자와 수반의 동일한 '크기'**

> **정리**: 연산자 $\hat{A}$가 정규 연산자인 것은, 모든 벡터 $|v\rangle$에 대해 $||\hat{A}|v\rangle|| = ||\hat{A}^\dagger|v\rangle||$ 인 것과 동치이다.

> **증명**: $ ||\hat{A}|v\rangle||^2 = \langle v|\hat{A}^\dagger\hat{A}|v\rangle$ 이고 $ ||\hat{A}^\dagger|v\rangle||^2 = \langle v|\hat{A}\hat{A}^\dagger|v\rangle$ 이다. 따라서 두 크기가 같은 것은 $\langle v|\hat{A}^\dagger\hat{A}|v\rangle = \langle v|\hat{A}\hat{A}^\dagger|v\rangle$ 와 동치이며, 이는 $\langle v|[\hat{A}^\dagger, \hat{A}]|v\rangle=0$을 의미한다. 모든 벡터에 대해 이 식이 성립하려면 연산자 $[\hat{A}^\dagger, \hat{A}]$가 0이어야 하므로, $\hat{A}$가 정규 연산자임과 동치이다.

#### **특성 5: 영공간과 열공간의 직교성**

> **정리**: 정규 연산자 $\hat{A}$의 영공간($N(A)$)은 그 열공간($C(A)$)과 항상 서로 수직이다.

> **증명**:
> 1. **보편적 원리**: 선형대수학의 기본 정리에 따라, 모든 행렬에 대해 영공간은 **행공간(Row Space, $C(A^T)$)**과 수직이다: $N(A) \perp C(A^T)$.
> 2. **정규 연산자의 특성**: 정규 연산자는 **열공간과 행공간이 같다**: $C(A) = C(A^T)$. (이는 특성 1로부터 유도된다. 영공간의 직교 보공간은 행공간($N(A)^\perp=C(A^T)$)이고, 좌측 영공간의 직교 보공간은 열공간($N(A^\dagger)^\perp=C(A)$)이다. 특성 1에서 $N(A)=N(A^\dagger)$이므로, 그 직교 보공간인 $C(A^T)$와 $C(A)$도 같다.)
> 3. **결론**: 따라서, 1번과 2번을 종합하면, 정규 연산자에 대해서는 $N(A) \perp C(A)$가 성립함이 증명된다. ✅

### 비교: 비정규 연산자


정규 연산자가 아닌 경우, 완비적인 고유벡터 기저를 갖지 못할 수 있다. 이러한 행렬을 '불완전 행렬(defective matrix)'이라고 한다. 이들은 공간을 순수하게 늘리거나 줄이는 것이 아닌, '찌그러뜨리는(shear)' 변환을 포함하여 안정적인 불변 방향이 부족하다.

- **예제 (비정규 행렬)**: $\hat{A} = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}$
    - $\hat{A}^\dagger = \begin{pmatrix} 1 & 0 \\ 1 & 1 \end{pmatrix}$
    - $[\hat{A}, \hat{A}^\dagger] = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix} \neq 0$ 이므로 정규 행렬이 아니다.
    - 이 행렬의 고유벡터는 $\begin{pmatrix} 1 \\ 0 \end{pmatrix}$ 방향 하나뿐이므로, 2차원 공간의 기저를 이룰 수 없다.

---
### 가역성 (Invertibility)

정규 연산자의 가역성은 고유값에 의해 결정된다. "가역적이다"라는 것은 "역변환이 존재한다"는 의미이며, 이는 "0으로 소멸되는 정보(영공간)가 없다"는 것과 같다.

- **가역적 정규 연산자 (Invertible Normal Operator)**
    - **조건**: **모든 고유값이 0이 아닐 때**.
    - **증명**: 행렬식은 고유값의 곱($\det(A) = \prod \lambda_i$)과 같다. 모든 고유값이 0이 아니면, 행렬식은 0이 아니므로 역행렬이 존재한다. 이 경우 영공간은 $\{0\}$ 뿐이다.
    - **물리적 의미**: 변환 과정에서 정보의 손실이 없으며, 0이 아닌 상태를 0 상태로 보내지 않는다.
    - **예제**: $\sigma_x = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}$는 정규(에르미트) 행렬이며, 고유값은 $1, -1$이므로 가역적이다.

- **비가역적 정규 연산자 (Non-invertible Normal Operator)**
    - **조건**: **적어도 하나의 고유값이 0일 때**.
    - **증명**: 고유값 중 0이 하나라도 포함되면, 행렬식($\det(A) = \prod \lambda_i$)은 0이 된다. 따라서 역행렬이 존재하지 않으며, 고유값 0에 해당하는 고유벡터들이 0이 아닌 영공간을 형성한다.
    - **물리적 의미**: 변환 과정에서 특정 상태(영공간)의 정보가 '소멸'된다.
    - **예제**: $\begin{pmatrix} 1 & 1 \\ 1 & 1 \end{pmatrix}$는 정규(에르미트) 행렬이며, 고유값은 $0, 2$이므로 비가역적이다.