+++
title = "(b) Normal operators"
weight = 1.5
+++

---

### 1. 정규 연산자의 정의

연산자 $\hat{A}$가 자신의 허미션 켤레($\hat{A}^\dagger$)와 교환 가능할 때, 노름 보존 조건을 만족하는 경우, **정규 연산자(Normal Operator)** 라고 한다.

- [$\hat{A}, \hat{A}^\dagger] = \hat{A}\hat{A}^\dagger - \hat{A}^\dagger\hat{A} = 0$

- 무한 차원을 포괄하는 보편적/해석학적 조건: 정의역 일치 $\mathcal{D}(\hat{A}) = \mathcal{D}(\hat{A}^\dagger)$ 및 노름 보존 $\|\hat{A}\psi\| = \|\hat{A}^\dagger\psi\|$

이 조건을 만족하는 연산자는 **항상 완비적인 정규직교 고유벡터 기저를 가진다는 매우 중요한 특성이 보장** 된다. 고유값이 $\lambda_i$, 고유상태벡터가 $|\lambda_i\rangle$ 라고 할 때,

$$\hat{A} = \sum_i \lambda_i |\lambda_i\rangle \langle \lambda^i| \quad \text{or} \quad \hat{A} = \int d\lambda\, \lambda |\lambda\rangle \langle \lambda^d|$$

$$\hat{A}^\dagger = \sum_i \lambda_i^\ast |\lambda_i\rangle \langle \lambda^i| \quad \text{or} \quad \hat{A}^\dagger = \int d\lambda\, \lambda^\ast |\lambda\rangle \langle \lambda^d|$$

---

### 2. 핵심 특성 및 증명

**1) 특성 1: $\hat{A}$와 $\hat{A}^\dagger$는 고유벡터를 공유한다.**

만약 $|v\rangle$가 정규 행렬 $\hat{A}$의 고유값 $\lambda$에 대한 고유벡터라면, $|v\rangle$는 동시에 $\hat{A}^\dagger$의 고유값 $\lambda^*$에 대한 고유벡터이기도 하다.
 
$$
\hat{A}|v\rangle = \lambda|v\rangle \iff \hat{A}^\dagger|v\rangle = \lambda^*|v\rangle
$$

proof)

앞선 챕터에서, 교환자가 0이면, 고유벡터를 공유한다는 사실을 증명하였다. 이번에는 고유값이 켤레로 나타남을 증명해 보자.

$$
\langle v|\hat{A}|v\rangle = \lambda\langle v|v\rangle
$$

$$
\langle v|\hat{A}^{\dagger}|v\rangle = (\lambda^{\ast}\langle v|)|v\rangle = \lambda^{\ast}\langle v|v\rangle
$$

따라서,

$$
\hat{A}^\dagger|v\rangle = \lambda^*|v\rangle
$$

**2) 특성 2: 서로 다른 고유값의 고유벡터는 직교한다.**

$$
\hat{A}|v_1\rangle = \lambda_1|v_1\rangle \text{ 이고 } \hat{A}|v_2\rangle = \lambda_2|v_2\rangle \text{ 일 때, } \lambda_1 \neq \lambda_2 \text{ 이면 } \langle v_1|v_2\rangle=0 \text{ 이다.}
$$

proof)

$$
\langle v_1|\hat{A}|v_2\rangle = \lambda_2\langle v_1|v_2\rangle
$$

**특성 1**을 이용하면,

$$
\langle v_1|\hat{A}|v_2\rangle
= \langle \hat{A}^\dagger v_1|v_2\rangle
= \langle \lambda_1^*v_1|v_2\rangle = \lambda_1\langle v_1|v_2\rangle
$$

두 결과가 같아야 하므로,

$$
(\lambda_1 - \lambda_2)\langle v_1|v_2\rangle = 0
$$ 
 
$\lambda_1 \neq \lambda_2$ 이므로 반드시 $\langle v_1|v_2\rangle = 0$ 이어야 한다.

**3) 특성 3: 고유값이 중복되더라도 고유벡터는 선형 독립이며 상호 직교하도록 구성할 수 있다.**

고유값이 중복(축퇴)되는 경우, 정규 연산자는 대수적 다중도와 기하적 다중도가 일치하여 결함(Defective) 구조를 갖지 않으므로 대응하는 고유벡터들은 선형 독립을 유지한다. 이 독립적인 기저들을 직교화하여 상호 직교하는 고유벡터군으로 재구성할 수 있다.

proof)

정규 연산자 $\hat{A}$가 $k$번 중복되는 고유값 $\lambda$를 가진다고 가정할 때, 이 고유값에 대응하는 $k$개의 선형 독립인 고유벡터 집합 $\{|u_1\rangle, |u_2\rangle, \dots, |u_k\rangle\}$이 존재하여 고유 공간(Eigenspace) $V_\lambda$를 형성한다.

이 공간 $V_\lambda$ 내의 임의의 선형 결합 또한 $\hat{A}$에 대해 동일한 고유값 $\lambda$를 가지는 고유벡터가 된다.

$$
\hat{A}\sum_{j=1}^k c_j |u_j\rangle = \sum_{j=1}^k c_j \hat{A} |u_j\rangle = \lambda \sum_{j=1}^k c_j |u_j\rangle
$$

따라서 이 부분 공간에 속한 기저 벡터들에 그람-슈미트 직교화(Gram-Schmidt orthogonalization)를 적용하여 새로운 직교 기저 집합 $\{|e_1\rangle, |e_2\rangle, \dots, |e_k\rangle\}$를 구성한다.

$$
|e_1\rangle = |u_1\rangle
$$

$$
|e_j\rangle = |u_j\rangle - \sum_{i=1}^{j-1} \frac{\langle e_i|u_j\rangle}{\langle e_i|e_i\rangle} |e_i\rangle \quad (j = 2, \dots, k)
$$

새로 구성된 직교 기저 $\{|e_j\rangle\}$ 역시 고유 공간 $V_\lambda$에 속하므로 $\hat{A}$의 고유벡터 조건을 만족하며 상호 직교한다. 특성 2에 의해 다른 고유값을 가지는 고유벡터들과는 이미 직교성이 보장되므로, 이를 통해 전체 상태 공간에 대한 정규직교 기저(Orthonormal basis)가 완성된다.

**4) 특성 4: 영공간(Null space)과 열공간(Column space)의 직교성**

정규 연산자의 영공간 $\ker(\hat{A})$과 열공간(치역, $\text{ran}(\hat{A})$)은 서로 직교한다. 

proof)

먼저, 정규 연산자의 영공간은 수반 연산자의 영공간과 완전히 일치함을 증명한다.
정규 연산자의 노름 보존 조건에 의해 임의의 벡터 $|v\rangle$에 대해 다음이 성립한다.

$$
\|\hat{A}v\| = \|\hat{A}^\dagger v\|
$$

만약 $|v\rangle \in \ker(\hat{A})$ 라면 $\hat{A}|v\rangle = 0$ 이므로 $\|\hat{A}v\| = 0$ 이다.
따라서 $\|\hat{A}^\dagger v\| = 0$ 이 되어 $\hat{A}^\dagger|v\rangle = 0$ 을 만족하므로 $|v\rangle \in \ker(\hat{A}^\dagger)$ 이다. 역의 과정도 동일하게 성립하므로 최종적으로 $\ker(\hat{A}) = \ker(\hat{A}^\dagger)$ 이다.

다음으로 일반적인 연산자에서 열공간 $\text{ran}(\hat{A})$의 임의의 벡터 $|w\rangle$와 $\ker(\hat{A}^\dagger)$의 임의의 벡터 $|u\rangle$의 내적을 계산한다.
$|w\rangle \in \text{ran}(\hat{A})$ 이므로 특정 벡터 $|v\rangle$에 대해 $|w\rangle = \hat{A}|v\rangle$ 로 표현된다.

$$
\langle u|w\rangle = \langle u|\hat{A}v\rangle = \langle \hat{A}^\dagger u|v\rangle
$$

$|u\rangle \in \ker(\hat{A}^\dagger)$ 이므로 $\hat{A}^\dagger|u\rangle = 0$ 이다.

$$
\langle \hat{A}^\dagger u|v\rangle = \langle 0|v\rangle = 0
$$

즉, 임의의 연산자에서 열공간 $\text{ran}(\hat{A})$과 수반 연산자의 영공간 $\ker(\hat{A}^\dagger)$은 항상 직교한다.

여기에 앞서 증명한 $\ker(\hat{A}) = \ker(\hat{A}^\dagger)$ 조건을 대입하면, 정규 연산자에 대하여 영공간과 열공간의 직교성이 완벽하게 성립함이 증명된다.

$$
\text{ran}(\hat{A}) \perp \ker(\hat{A})
$$