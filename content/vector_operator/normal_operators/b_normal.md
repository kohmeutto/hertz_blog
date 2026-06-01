+++
title = "(b) Normal"
weight = 1
+++

---

### 1. 정규 연산자의 정의

아래의 세가지 조건을 모두 만족할 때, **정규 연산자(Normal Operator)** 라고 한다.

- [$\hat{A}, \hat{A}^\dagger] = \hat{A}\hat{A}^\dagger - \hat{A}^\dagger\hat{A} = 0$
- 정의역 일치 $\mathcal{D}(\hat{A}) = \mathcal{D}(\hat{A}^\dagger)$
- $\mathcal{R}\hat{A}=0$ 이것은 노름 보존 $\|\hat{A}\psi\| = \|\hat{A}^\dagger\psi\|$ 과 동치이다.

위 조건을 만족하는 연산자는 스펙트럼 정리(Spectral Theorem)에 의하여 **공간 전체를 전개(Span)하는 완비적 정규직교 고유기저(Complete Orthonormal Eigenbasis)** 를 가진다. 고유값이 $\lambda_i$, 대응하는 고유벡터가 $|\lambda_i\rangle$일 때, 스펙트럼 분해 공식은 다음과 같이 확정된다.

$$
\hat{A} = \sum_i \lambda_i |\lambda_i\rangle \langle \lambda_i| \quad \text{or} \quad \hat{A} = \int d\lambda \, \lambda |\lambda\rangle \langle \lambda|
$$

$$
\hat{A}^\dagger = \sum_i \lambda_i^\ast |\lambda_i\rangle \langle \lambda_i| \quad \text{or} \quad \hat{A}^\dagger = \int d\lambda \, \lambda^\ast |\lambda\rangle \langle \lambda|
$$

---

### 2. 특성 1: 쌍대 기저와 브라 기저의 일치성

$$
\langle \lambda^i | = \langle \lambda_i |, \quad \langle \lambda^d | = \langle \lambda |,
$$

proof)

일반적인 쌍대 기저(bi-dual basis)를 이용한 스펙트럼 표현에서 출발하여, 교환자 조건 $[\hat{A}, \hat{A}^\dagger] = 0$이 쌍대 기저와 브라 기저의 일치를 강제함을 증명한다.

*(1) 쌍대 기저를 이용한 연산자 표현*

$$
\hat{A} = \sum_i \lambda_i |\lambda_i\rangle \langle \lambda^i|
$$

여기서 쌍대 기저는 원 켓 기저 $|\lambda_j\rangle$에 대하여 크로네커 델타 성질인 $\langle \lambda^i|\lambda_j\rangle = \delta^i_j$를 만족합니다. 이 쌍대직교성에 의해 항등 연산자 $\hat{I}$에 대한 완비성 관계식(completeness relation)은 양방향으로 성립한다.

$$
\hat{I} = \sum_i |\lambda_i\rangle \langle \lambda^i| = \sum_i |\lambda^i\rangle \langle \lambda_i|
$$

*(2) 수반 연산자의 스펙트럼 표현*


연산자 $\hat{A}$에 허미션 켤레(Hermitian conjugate)를 취하여 수반 연산자 $\hat{A}^\dagger$를 도출합니다. 합의 각 항에서 고유값은 복소 공액이 되며, 켓 벡터와 브라 벡터의 위치가 역전된다.

$$
\hat{A}^\dagger = \sum_i \lambda_i^\ast |\lambda^i\rangle \langle \lambda_i|
$$

이때 $|\lambda^i\rangle$는 쌍대 기저 브라 벡터 $\langle \lambda^i|$의 켓 형태이며, $\langle \lambda_i|$는 원 켓 벡터 $|\lambda_i\rangle$의 브라 형태이다.

*(3) 정규성 조건의 적용*

이전 증명 단계에서 확립된 대수학적 불변량에 따라, 교환자 조건 $[\hat{A}, \hat{A}^\dagger] = 0$을 만족하는 정규 연산자의 경우 켓 기저에 대한 $\hat{A}|\lambda_k\rangle = \lambda_k|\lambda_k\rangle$가 성립하면 수반 연산자에 대해서도 다음의 고유값 방정식이  성립한다.

$$
\hat{A}^\dagger|\lambda_k\rangle = \lambda_k^\ast|\lambda_k\rangle
$$

*(4) 행렬 요소 비교를 통한 직교성 도출*

정의된 $\hat{A}^\dagger$의 스펙트럼 표현을 임의의 켓 기저 $|\lambda_k\rangle$에 작용한다.

$$
\hat{A}^\dagger|\lambda_k\rangle = \left( \sum_j \lambda_j^\ast |\lambda^j\rangle \langle \lambda_j| \right) |\lambda_k\rangle = \sum_j \lambda_j^\ast \langle \lambda_j|\lambda_k\rangle |\lambda^j\rangle
$$

이 결과를 정규성에 의해 도출된 $\hat{A}^\dagger|\lambda_k\rangle = \lambda_k^\ast|\lambda_k\rangle$와 등치시킨다.

$$
\sum_j \lambda_j^\ast \langle \lambda_j|\lambda_k\rangle |\lambda^j\rangle = \lambda_k^\ast |\lambda_k\rangle
$$

우변의 $|\lambda_k\rangle$를 앞서 언급한 완비성 관계식 $\hat{I} = \sum_j |\lambda^j\rangle \langle \lambda_j|$를 이용하여 전개한다.

$$
\sum_j \lambda_j^\ast \langle \lambda_j|\lambda_k\rangle |\lambda^j\rangle = \lambda_k^\ast \sum_j \langle \lambda_j|\lambda_k\rangle |\lambda^j\rangle
$$

좌변으로 항을 이항하여 묶어내면,

$$
\sum_j (\lambda_j^\ast - \lambda_k^\ast) \langle \lambda_j|\lambda_k\rangle |\lambda^j\rangle = 0
$$

*(5) 쌍대 기저와 브라 기저의 일치 증명*

기저 벡터 $|\lambda^j\rangle$들은 선형 독립(linearly independent)이므로, 이들의 선형 결합이 0이 되기 위해서는 각 계수가 모두 0이어야 한다.

$$
(\lambda_j^\ast - \lambda_k^\ast) \langle \lambda_j|\lambda_k\rangle = 0
$$

고유값이 서로 다른 경우($\lambda_j \neq \lambda_k$), 위 식을 만족하기 위한 유일한 해는 $\langle \lambda_j|\lambda_k\rangle = 0$이다. 이는 원 켓 기저 벡터들이 자연 내적 공간에서 상호 직교함을 의미합니다.각 벡터를 자기 자신과 내적하여 정규화($\langle \lambda_k|\lambda_k\rangle = 1$)하면, 원 기저 간의 내적은 크로네커 델타로 환원된다.

$$
\langle \lambda_j|\lambda_k\rangle = \delta_{jk}
$$

초기 스펙트럼 표현에서 쌍대 기저는 $\langle \lambda^j|\lambda_k\rangle = \delta^j_k$로 정의되었다. 주어진 완비 기저 공간에서 특정 직교성을 만족하는 쌍대 기저는 대수학적으로 유일하게 결정된다. 브라 기저 $\langle \lambda_j|$가 쌍대 기저 $\langle \lambda^j|$와 완전히 동일한 크로네커 델타 조건을 충족하므로, 선형대수학의 유일성 정리에 의해 $\langle \lambda^j| = \langle \lambda_j|$임이 증명된다.

---

### 2. 특성 1: 우측 및 좌측 고유벡터의 켤레 대응

정규 연산자 구조에서는 우고유벡터(Right eigen\lambdaector)를 허미션 켤레화하여 좌측 고유 상태를 취할 때, 상태 공간의 왜곡 없이 고유값의 복소수 부호만이 반전된다.

$$
\hat{A}^\dagger |\lambda_i\rangle = \lambda_i^\ast |\lambda_i\rangle
$$

proof)

임의의 고유값 $\lambda$와 고유벡터 $|\lambda\rangle$에 대하여 $\hat{A}|\lambda\rangle = \lambda|\lambda\rangle$가 성립한다고 가정한다. 새로운 연산자 $\hat{T} = \hat{A} - \lambda\hat{I}$를 정의하면, $\hat{A}$가 정규 연산자이므로 $\hat{T}$ 역시 다음의 교환자 가환성을 유지한다.

$$
[\hat{T}, \hat{T}^\dagger] = [ \hat{A} - \lambda\hat{I}, \hat{A}^\dagger - \lambda^\ast\hat{I} ] = [\hat{A}, \hat{A}^\dagger] = 0
$$

정규 연산자의 3번 조건(노름 보존)에 의하여 $\|\hat{T}\lambda\| = \|\hat{T}^\dagger \lambda\|$가 성립하므로, 다음의 동치 관계가 성립한다.

$$
\|(\hat{A} - \lambda\hat{I})\lambda\| = 0 \iff \|(\hat{A}^\dagger - \lambda^\ast\hat{I})\lambda\| = 0
$$

연산자 노름의 정의상 위 조건은 다음 방정식과 동치이다.

$$
\hat{A}^\dagger |\lambda\rangle = \lambda^\ast |\lambda\rangle
$$

---

### 3. 특성 2: 서로 다른 고유값의 고유벡터는 biorthogonal

$\hat{A}|\lambda_i\rangle = \lambda_i|\lambda_i\rangle$, $\hat{A}|\lambda_j\rangle = \lambda_j|\lambda_j\rangle$, $\lambda_i \neq \lambda_j$ 이면

$$
\langle \lambda_i|\lambda_j\rangle = 0
$$

proof)

$$
\hat{A}|\lambda_i\rangle = \lambda_i|\lambda_i\rangle, \quad \hat{A}|\lambda_j\rangle = \lambda_j|\lambda_j\rangle
$$

특성 1의 결과인 $\hat{A}^\dagger |\lambda_i\rangle = \lambda_i^\ast |\lambda_i\rangle$에 허미션 수반을 취하여 브라 벡터로 변환한다.
$$\langle \lambda_i | \hat{A} = \lambda_i \langle \lambda_i |$$

행렬 요소 $\langle \lambda_i | \hat{A} | \lambda_j \rangle$를 두 가지 방향으로 전개하여 대조한다.

(1) 우측 작용: $\langle \lambda_i | (\hat{A} | \lambda_j \rangle) = \lambda_j \langle \lambda_i | \lambda_j \rangle$  
(2) 좌측 작용: $(\langle \lambda_i | \hat{A}) | \lambda_j \rangle = \lambda_i \langle \lambda_i | \lambda_j \rangle$

두 전개 결과는 일치해야 하므로 다음의 구속 조건이 도출된다.
$$(\lambda_i - \lambda_j) \langle \lambda_i | \lambda_j \rangle = 0$$

$\lambda_i \neq \lambda_j$이므로 스칼라 항은 0이 될 수 없다. 따라서 서로 다른 고유상태 간의 내적은 0이다.
$$\langle \lambda_i | \lambda_j \rangle = 0 \quad (i \neq j)$$

자기 자신에 대해 크기를 1로 정규화($\langle \lambda_i | \lambda_i \rangle = 1$)하면, 최종적으로 크로네커 델타 조건 $\langle \lambda_i | \lambda_j \rangle = \delta_{ij}$가 성립한다.

---

### 4. 특성 3: 중복 고유값에서도 완비 고유 기저

정규 연산자 $\hat{A}$의 임의의 고유값 $\lambda$에 대한 대수적 중복도와 기하학적 중복도는 항상 동일하게 일치하며, 고유 공간 $\mathcal{V}_\lambda$ 내의 선형 독립인 고유벡터들은 표준 그람-슈미트(Gram-Schmidt) 직교화 절차를 거쳐 완벽한 정규직교 완비 기저를 형성한다.

$$
(\hat{A} - \lambda\hat{I})^2 |\psi\rangle = 0 \implies (\hat{A} - \lambda\hat{I}) |\psi\rangle = 0$$$$|e_j\rangle = |u_j\rangle - \sum_{i=1}^{j-1} \frac{\langle e_i | u_j \rangle}{\langle e_i | e_i \rangle} |e_i\rangle
$$

proof)

수가 2인 선형 연산자의 작용에 의해 0으로 수축하는 힐베르트 공간 내의 임의의 상태 벡터 $|\psi\rangle$를 상정한다.

$$
(\hat{A} - \lambda\hat{I})^2 |\psi\rangle = 0
$$

위 조건 하에서 중간 상태 벡터 $|w\rangle$를 다음과 같이 정의하여 도출한다.

$$
|w\rangle = (\hat{A} - \lambda\hat{I})|\psi\rangle
$$

정의된 중간 상태 벡터 $|w\rangle$에 선형 연산자 $(\hat{A} - \lambda\hat{I})$를 전방 작용시키면, 초기 전제 조건에 의하여 다음과 같이 영벡터로 귀결된다.$$(\hat{A} - \lambda\hat{I})|w\rangle = (\hat{A} - \lambda\hat{I})^2|\psi\rangle = 0$$위 식을 분배 법칙에 따라 전개하면 $\hat{A}|w\rangle = \lambda|w\rangle$가 되므로, 상태 벡터 $|w\rangle$는 연산자 $\hat{A}$의 고유값 $\lambda$에 대응하는 우고유벡터임을 알 수 있다. 이때 정규 연산자의 근본 성질을 규명한 특성 1(우측 및 좌측 고유벡터의 켤레 대응)을 적용하면, 수반 연산자 $\hat{A}^\dagger$에 대해서도 동일한 기하학적 구조를 공유하며 고유값만이 복소 공액으로 반전되는 다음 항등식이 유도된다.

$$
\hat{A}^\dagger|w\rangle = \lambda^*|w\rangle
$$

위 식의 우변 항을 좌변으로 이항하여 공통 상태 벡터 $|w\rangle$로 묶어 정리하면 다음과 같다.

$$
(\hat{A}^\dagger - \lambda^*\hat{I})|w\rangle = 0
$$

이제 상태 벡터 $|w\rangle$의 표준 노름의 제곱 $\|w\|^2$을 힐베르트 공간의 내적 정의에 입각하여 낱낱이 전개한다.

$$
\|w\|^2 = \langle w | w \rangle = \langle w | (\hat{A} - \lambda\hat{I}) | \psi \rangle
$$

정규 연산자의 제3 조건에 의하여 경계 잔여물 $\mathcal{R}_{\hat{A}}$은 존재하지 않으므로, 수반 연산자의 근본 정의에 따라 우측 켓 벡터 공간에 작용하는 선형 작용소 $(\hat{A} - \lambda\hat{I})$를 좌측 브라 벡터 공간의 연산 영역으로 사상할 수 있다.

$$
\langle w | (\hat{A} - \lambda\hat{I}) | \psi \rangle
= \langle (\hat{A} - \lambda\hat{I})^\dagger w | \psi \rangle
= \langle (\hat{A}^\dagger - \lambda^*\hat{I}) w | \psi \rangle
= \langle 0 | \psi \rangle = 0
$$

힐베르트 공간을 규정하는 내적의 양의 정부호성(Positive definiteness) 공리에 의하여, 자기 자신과의 내적치인 노름의 제곱이 스칼라 0으로 수렴하는 벡터는 오직 영벡터($|0\rangle$) 공간의 원소뿐이다.

$$
|w\rangle = 0 \quad \implies \quad (\hat{A} - \lambda\hat{I})|\psi\rangle = 0
$$

이 결과는 차수가 2 이상인 높은 차수의 대수적 멱연산에 의해서만 0으로 전리되던 일반화 고유벡터가 존재할 수 없음을 뜻하며, 대수적 중복도 공간을 형성하는 모든 원소가 예외 없이 1차 고유방정식을 충족함을 증명한다. 조르단 블록의 부재 원리에 의하여, 고유값 $\lambda$의 대수적 중복도가 $k$라면 해당 고유 공간 $\mathcal{V}_\lambda$에는 구조적 결함 없이 정확히 $k$개의 선형 독립인 순수 우고유벡터 기저 집합 ${|u_1\rangle, |u_2\rangle, \dots, |u_k\rangle}$가 확보된다. 이 선형 독립인 기저 집합에 대하여 힐베르트 공간 내부의 자연 내적을 기반으로 하는 표준 그람-슈미트 직교화 절차를 전개한다.첫 번째 정규직교 기저 벡터는 초기 상태 벡터의 노름을 표준화하여 다음과 같이 지정된다.

$$
|e_1\rangle = |u_1\rangle
$$

임의의 $j$번째 정규직교 기저 벡터 $|e_j\rangle$는, 이전에 순차적으로 도출된 상호 직교 기저 벡터들인 $|e_1\rangle$부터 $|e_{j-1}\rangle$까지의 모든 부분 사형 성분들을 대수적으로 차감하는 다음의 투영 공식을 거쳐 생성된다.

$$
|e_j\rangle = |u_j\rangle - \sum_{i=1}^{j-1} \frac{\langle e_i | u_j \rangle}{\langle e_i | e_i \rangle} |e_i\rangle
$$

---

### 5. 특성 4: 영공간과 열공간의 직교성

strict normal 연산자에서 **영공간(null space)** 과 **열공간(range)** 은 직교한다.

$$
\ker(\hat{A}) \perp \text{ran}(\hat{A})
$$

즉, $|u\rangle \in \ker(\hat{A})$, $|w\rangle \in \text{ran}(\hat{A})$ 이면 $\langle u|w\rangle = 0$.

proof)

노름 보존 조건 $\|\hat{A}\lambda\| = \|\hat{A}^\dagger \lambda\|$에 의하여, 영공간에 관한 다음의 동치 관계가 성립한다.

$$
|u\rangle \in \ker(\hat{A}) \iff \hat{A}|u\rangle = 0 \iff \hat{A}^\dagger |u\rangle = 0 \iff |u\rangle \in \ker(\hat{A}^\dagger)
$$

열공간의 임의의 원소 $|w\rangle \in \text{ran}(\hat{A})$를 상정한다. 열공간의 정의에 따라 $|w\rangle = \hat{A}|x\rangle$를 만족하는 임의의 상태 벡터 $|x\rangle$가 존재한다. 영공간의 원소 $|u\rangle$와 열공간의 원소 $|w\rangle$ 사이의 표준 내적을 전개한다.

$$
\langle u | w \rangle = \langle u | \hat{A} | x \rangle = \langle \hat{A}^\dagger u | x \rangle
$$

위 식에서 $|u\rangle \in \ker(\hat{A}^\dagger)$이므로 $\hat{A}^\dagger |u\rangle = 0$이 대입된다.

$$
\langle u | w \rangle = \langle 0 | x \rangle = 0
$$

결과적으로 두 부분공간의 모든 원소 간 내적이 0으로 수렴하므로, 정규 연산자 하에서는 영공간과 열공간의 기하학적 구조가 힐베르트 공간 내에서 직교 분할됨이 증명된다.

---