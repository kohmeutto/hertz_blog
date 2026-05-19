+++
title = "(b) Normal operators"
weight = 1.5
+++

---

### 1. 정규 연산자의 정의

아래의 세가지 조건을 모두 만족할 때, **정규 연산자(Normal Operator)** 라고 한다.

- [$\hat{A}, \hat{A}^\dagger] = \hat{A}\hat{A}^\dagger - \hat{A}^\dagger\hat{A} = 0$
- 정의역 일치 $\mathcal{D}(\hat{A}) = \mathcal{D}(\hat{A}^\dagger)$
- $\mathcal{R}\hat{A}=0$ 이것은 노름 보존 $\|\hat{A}\psi\| = \|\hat{A}^\dagger\psi\|$ 과 동치이다.

이 조건을 만족하는 연산자는 **항상 완비적인 정규직교 고유벡터 기저를 가진다는 매우 중요한 특성이 보장** 된다. 고유값이 $\lambda_i$, 고유상태벡터가 $|\lambda_i\rangle$ 라고 할 때,

$$\hat{A} = \sum_i \lambda_i |\lambda_i\rangle \langle \lambda^i| \quad \text{or} \quad \hat{A} = \int d\lambda\, \lambda |\lambda\rangle \langle \lambda^d|$$

$$\hat{A}^\dagger = \sum_i \lambda_i^\ast |\lambda_i\rangle \langle \lambda^i| \quad \text{or} \quad \hat{A}^\dagger = \int d\lambda\, \lambda^\ast |\lambda\rangle \langle \lambda^d|$$

---

### 2. 특성 1: 우/좌 고유벡터의 켤레 대응

$|v\rangle$ 가 $\hat{A}$ 의 고유벡터 (eigenvalue $\lambda$) 이면, **같은 $|v\rangle$ 가 $\hat{A}^\dagger$ 의 고유벡터** (eigenvalue $\lambda^*$) 이다.

$$
\hat{A}|v\rangle = \lambda|v\rangle \iff \hat{A}^\dagger|v\rangle = \lambda^*|v\rangle
$$

(단일 벡터에 대한 진술이므로 듀얼 마커 없이 $\langle v|$ 사용.)

proof)

$|w\rangle := (\hat{A}^\dagger - \lambda^*)|v\rangle$ 로 정의하고, $\|w\|^2 = 0$ 을 보여 $|w\rangle = 0$, 즉 $\hat{A}^\dagger|v\rangle = \lambda^*|v\rangle$ 을 도출한다.

$$
\|w\|^2 = \langle v|(\hat{A} - \lambda)(\hat{A}^\dagger - \lambda^*)|v\rangle
$$

전개:

$$
= \langle v|\hat{A}\hat{A}^\dagger|v\rangle - \lambda^*\langle v|\hat{A}|v\rangle - \lambda\langle v|\hat{A}^\dagger|v\rangle + |\lambda|^2\|v\|^2
$$

고유값 방정식 $\hat{A}|v\rangle = \lambda|v\rangle$ 으로부터 $\langle v|\hat{A}|v\rangle = \lambda\|v\|^2$. 내적의 sesquilinear 성에서 $\langle v|\hat{A}^\dagger|v\rangle = \overline{\langle v|\hat{A}|v\rangle} = \lambda^*\|v\|^2$. 대입:

$$
= \langle v|\hat{A}\hat{A}^\dagger|v\rangle - 2|\lambda|^2\|v\|^2 + |\lambda|^2\|v\|^2 = \langle v|\hat{A}\hat{A}^\dagger|v\rangle - |\lambda|^2\|v\|^2
$$

여기서 **strict normal 조건** $\hat{A}\hat{A}^\dagger = \hat{A}^\dagger\hat{A}$ 을 적용:

$$
= \langle v|\hat{A}^\dagger\hat{A}|v\rangle - |\lambda|^2\|v\|^2 = \|\hat{A}|v\rangle\|^2 - |\lambda|^2\|v\|^2 = |\lambda|^2\|v\|^2 - |\lambda|^2\|v\|^2 = 0
$$

따라서 $\|w\|^2 = 0 \implies |w\rangle = 0 \implies \hat{A}^\dagger|v\rangle = \lambda^*|v\rangle$.

---

### 3. 특성 2: 서로 다른 고유값의 고유벡터는 biorthogonal

$\hat{A}|v_i\rangle = \lambda_i|v_i\rangle$, $\hat{A}|v_j\rangle = \lambda_j|v_j\rangle$, $\lambda_i \neq \lambda_j$ 이면

$$
\langle v^i|v_j\rangle = 0
$$

여기서 $\langle v^i|$ 는 $|v_i\rangle$ 의 듀얼 기저 (위첨자 = 반변 인덱스).

strict normal in 표준 L² (Hermitian 등) 의 경우 $\langle v^i| = \langle v_i|$ 이므로, 위 결과는 표준 교재의 $\langle v_i|v_j\rangle = 0$ 으로 자동 환원.

proof)

$\langle v^i|\hat{A}|v_j\rangle$ 을 두 방향으로 평가한다.

**(우측 작용)** $\hat{A}|v_j\rangle = \lambda_j|v_j\rangle$ 사용:

$$
\langle v^i|\hat{A}|v_j\rangle = \lambda_j\,\langle v^i|v_j\rangle
$$

**(좌측 작용)** 특성 1 에 의해 $|v_i\rangle$ 가 $\hat{A}^\dagger$ 의 고유벡터 (eigenvalue $\lambda_i^*$). 자연 내적에서 $\langle v^i| = \langle v_i|$ 이므로 $\langle v^i|$ 가 $\hat{A}$ 의 좌고유벡터 (eigenvalue $\lambda_i$):

$$
\langle v^i|\hat{A} = \lambda_i\,\langle v^i|
$$

이를 사용:

$$
\langle v^i|\hat{A}|v_j\rangle = \lambda_i\,\langle v^i|v_j\rangle
$$

두 결과를 같게 놓으면:

$$
(\lambda_i - \lambda_j)\,\langle v^i|v_j\rangle = 0
$$

$\lambda_i \neq \lambda_j$ 이므로 $\langle v^i|v_j\rangle = 0$.

---

### 4. 특성 3: 비결함성 — 중복 고유값에서도 완비 고유 기저

strict normal 연산자는 **Jordan block 을 가지지 않는다**. 즉, 중복 고유값 $\lambda$ 에 대해 대수적 다중도와 기하적 다중도가 일치하여, 고유 공간 $V_\lambda$ 의 차원이 다중도와 같다.

proof) **일반화 고유공간이 고유공간과 일치함**.

핵심: $(\hat{A} - \lambda)^2 |v\rangle = 0$ 인 임의의 $|v\rangle$ 에 대해 $(\hat{A} - \lambda)|v\rangle = 0$ 임을 보이면, 일반화 고유공간 (높은 차수의 nilpotent 작용으로 0 이 되는 벡터들) 이 고유공간 (1차 작용으로 0) 과 일치함이 따라온다.

$|w\rangle := (\hat{A} - \lambda)|v\rangle$ 로 놓으면 $(\hat{A} - \lambda)|w\rangle = (\hat{A} - \lambda)^2|v\rangle = 0$, 즉 $|w\rangle$ 가 고유값 $\lambda$ 의 고유벡터. **특성 1** 에 의해

$$
\hat{A}^\dagger|w\rangle = \lambda^*|w\rangle \implies (\hat{A}^\dagger - \lambda^*)|w\rangle = 0
$$

이제 $\|w\|^2$ 를 계산:

$$
\|w\|^2 = \langle w|w\rangle = \langle w|(\hat{A} - \lambda)|v\rangle
$$

b_adjoint.md §2 의 수반 관계로 $\hat{A} - \lambda$ 를 bra 쪽으로 옮기면:

$$
= \langle (\hat{A}^\dagger - \lambda^*)w|v\rangle = \langle 0|v\rangle = 0
$$

따라서 $|w\rangle = 0$, 즉 $(\hat{A} - \lambda)|v\rangle = 0$. **Jordan block 부재 증명 완료**.

**다중도 = 고유공간 차원**: 위 결과로 고유값 $\lambda$ 의 대수적 다중도 ($k$) 만큼의 선형 독립 고유벡터가 $V_\lambda$ 에 존재.

**Biorthogonalization**: $V_\lambda$ 의 $k$ 개의 선형 독립 고유벡터 $\{|u_1\rangle, \ldots, |u_k\rangle\}$ 에 Gram-Schmidt 직교화 (자연 내적에서) 를 적용하면 biorthogonal 기저 $\{|e_1\rangle, \ldots, |e_k\rangle\}$ 가 얻어진다.

$$
|e_1\rangle = |u_1\rangle, \quad |e_j\rangle = |u_j\rangle - \sum_{i=1}^{j-1}\frac{\langle e^i|u_j\rangle}{\langle e^i|e_i\rangle}|e_i\rangle
$$

(여기서 $\langle e^i|$ 는 듀얼 기저, 위첨자 인덱스.) 특성 2 에 의해 다른 고유값과의 biorthogonality 가 자동 보장. 결과적으로 전체 공간의 biorthogonal 완비 기저가 완성된다.

---

### 5. 특성 4: 영공간과 열공간의 직교성

strict normal 연산자에서 **영공간(null space)** 과 **열공간(range)** 은 직교한다.

$$
\ker(\hat{A}) \perp \text{ran}(\hat{A})
$$

즉, $|u\rangle \in \ker(\hat{A})$, $|w\rangle \in \text{ran}(\hat{A})$ 이면 $\langle u|w\rangle = 0$. 여기서 $|u\rangle, |w\rangle$ 는 부분공간의 단일 원소이므로 듀얼 마커 없이 $\langle u|, \langle w|$ 사용.

proof)

**(단계 1)** $\ker(\hat{A}) = \ker(\hat{A}^\dagger)$.

노름 보존 조건 $\|\hat{A}|v\rangle\| = \|\hat{A}^\dagger|v\rangle\|$ 으로부터:

$$
|v\rangle \in \ker(\hat{A}) \iff \|\hat{A}|v\rangle\| = 0 \iff \|\hat{A}^\dagger|v\rangle\| = 0 \iff |v\rangle \in \ker(\hat{A}^\dagger)
$$

이는 strict normal 의 직접 결과 (특성 1 의 특수 사례: $\lambda = 0$).

**(단계 2)** 임의의 연산자에서 $\text{ran}(\hat{A}) \perp \ker(\hat{A}^\dagger)$.

$|w\rangle = \hat{A}|v\rangle \in \text{ran}(\hat{A})$, $|u\rangle \in \ker(\hat{A}^\dagger)$ 이면 b_adjoint.md §2 의 수반 관계로:

$$
\langle u|w\rangle = \langle u|\hat{A}|v\rangle = \langle \hat{A}^\dagger u|v\rangle = \langle 0|v\rangle = 0
$$

이 부분은 **strict normal 조건을 사용하지 않으며**, 모든 연산자에 대해 성립.

**결합**: 단계 1 의 $\ker(\hat{A}) = \ker(\hat{A}^\dagger)$ 와 단계 2 의 $\text{ran}(\hat{A}) \perp \ker(\hat{A}^\dagger)$ 를 합치면

$$
\text{ran}(\hat{A}) \perp \ker(\hat{A})
$$

가 성립.

**의미**: 영공간 위의 사영과 열공간 위의 사영이 직합 분해를 이루며, $\mathcal{H} = \ker(\hat{A}) \oplus \text{ran}(\hat{A})$. 이 분해가 일반화된 그린함수 (영공간 사영 제거 후 역연산자 구성) 의 정확한 수학적 기반이다.
