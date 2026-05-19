+++
title = "(b) Unitary"
weight = 4
+++

---

### 1. Unitary 연산자

**1) 정의**

연산자 $\hat{U}$ 가 자신의 에르미트 켤레 $\hat{U}^\dagger$ 와 다음 관계를 만족할 때, 이를 **유니타리 (Unitary) 연산자** 라 한다.

$$
\hat{U}^\dagger\hat{U} = \hat{U}\hat{U}^\dagger = \hat{I}
$$

즉 $\hat{U}^\dagger = \hat{U}^{-1}$, 에르미트 켤레가 역원과 같다. 이 조건이 정규 연산자의 조건 $[\hat{U}, \hat{U}^\dagger] = 0$ 을 자동으로 만족한다.

**2) 노름 보존**

임의의 두 벡터 $|v\rangle, |w\rangle$ 에 대해

$$
\langle\hat{U}v|\hat{U}w\rangle = \langle v|\hat{U}^\dagger\hat{U}|w\rangle = \langle v|\hat{I}|w\rangle = \langle v|w\rangle
$$

내적이 보존되며, 특히 노름 $\|\hat{U}v\| = \|v\|$ 가 보존된다.

---

### 2. 고유값은 단위 원 위에 있다

유니타리 연산자의 고유값은 모두 절댓값이 1 인 복소수이다.

$$
\sigma(\hat{U}) \subset \{e^{i\theta} : \theta \in \mathbb{R}\} = S^1
$$

복소 평면에서 단위 원 위에 위치한다.

proof)

$\hat{U}|v\rangle = \lambda|v\rangle$ 가정. 양변에 $\langle v|\hat{U}^\dagger$ 를 내적:

$$
\langle v|\hat{U}^\dagger\hat{U}|v\rangle = \lambda^*\lambda\,\langle v|v\rangle
$$

정의 $\hat{U}^\dagger\hat{U} = \hat{I}$ 에서 좌변이 $\langle v|v\rangle$. 따라서

$$
|\lambda|^2\,\langle v|v\rangle = \langle v|v\rangle
$$

$\langle v|v\rangle \neq 0$ 이므로 $|\lambda|^2 = 1$. 이를 만족하는 복소수는 $\lambda = e^{i\theta}$ ($\theta \in \mathbb{R}$) 의 형태.

---

### 3. 세 가지 정규 연산자의 통합

Hermitian, anti-Hermitian, unitary 의 고유값 위치:

| 연산자 | 정의 | 고유값 위치 | 복소 평면 |
|---|---|---|---|
| Hermitian | $\hat{H}^\dagger = \hat{H}$ | $\lambda \in \mathbb{R}$ | 실수 직선 |
| Anti-Hermitian | $\hat{A}^\dagger = -\hat{A}$ | $\lambda \in i\mathbb{R}$ | 허수 축 |
| Unitary | $\hat{U}^\dagger\hat{U} = \hat{I}$ | $\vert\lambda\vert = 1$ | 단위 원 |

복소 평면의 세 가지 특별한 부분 집합 — 실수 직선, 허수 축, 단위 원 — 이 세 가지 정규 연산자에 대응한다.

---

### 4. 기본 성질

**1) 서로 다른 고유값의 고유벡터 직교성**

$\hat{U}|v_i\rangle = \lambda_i|v_i\rangle, \hat{U}|v_j\rangle = \lambda_j|v_j\rangle, \lambda_i \neq \lambda_j$ 이면

$$
\langle v_i|v_j\rangle = 0
$$

b_normal_operators.md §3 의 특성 2 의 직접 적용. (Unitary 가 정규 연산자이고, 표준 내적에서 듀얼 기저가 자연 켤레와 일치하므로 $\langle v^i| = \langle v_i|$.)

**2) 정수 거듭제곱**

$\hat{U}^n$ 도 유니타리이다 ($n$ 정수).

$$
(\hat{U}^n)^\dagger\,\hat{U}^n = (\hat{U}^\dagger)^n\,\hat{U}^n = \hat{I}^n = \hat{I}
$$

---

### 5. Spectral 분해에서 Hermitian 의 등장 — $\hat{U} = e^{i\hat{H}}$ 의 도출

§2 에서 유니타리의 고유값이 단위 원 위에 있음을 도출했다. 따라서 spectral 분해의 각 고유값이 $e^{i\lambda_n}$ 형태로 표현된다.

$$
\hat{U} = \sum_n e^{i\lambda_n} |v_n\rangle\langle v_n|, \quad \lambda_n \in \mathbb{R}
$$

각 고유값 $e^{i\lambda_n}$ 이 스칼라 지수 함수. 그 정의 — Taylor 급수의 무한 합:

$$
e^{i\lambda_n} = \sum_{k=0}^{\infty} \frac{(i\lambda_n)^k}{k!}
$$

이를 spectral 분해에 대입:

$$
\hat{U} = \sum_n \left(\sum_{k=0}^{\infty} \frac{(i\lambda_n)^k}{k!}\right) |v_n\rangle\langle v_n|
$$

수렴 조건 하에서 합의 순서를 바꿈:

$$
\hat{U} = \sum_{k=0}^{\infty} \frac{i^k}{k!} \sum_n \lambda_n^k |v_n\rangle\langle v_n|
$$

안쪽의 합 $\sum_n \lambda_n^k |v_n\rangle\langle v_n|$ 이 어떤 작용소의 $k$ 거듭제곱의 형태. 작용소 $\hat{H}$ 를

$$
\hat{H} := \sum_n \lambda_n |v_n\rangle\langle v_n|
$$

으로 둔다. $\lambda_n$ 이 실수이므로 $\hat{H}$ 가 Hermitian:

$$
\hat{H}^\dagger = \sum_n \overline{\lambda_n} |v_n\rangle\langle v_n| = \sum_n \lambda_n |v_n\rangle\langle v_n| = \hat{H}
$$

(자연 내적의 정규 작용소에서 dual basis 와 켤레가 일치 — b_normal_operators.md §3.)

Spectral 분해의 직교성 $\langle v_n|v_m\rangle = \delta_{nm}$ 에서

$$
\hat{H}^k = \sum_n \lambda_n^k |v_n\rangle\langle v_n|
$$

이를 위 식에 대입하면

$$
\hat{U} = \sum_{k=0}^{\infty} \frac{i^k}{k!} \hat{H}^k = \sum_{k=0}^{\infty} \frac{(i\hat{H})^k}{k!}
$$

스칼라 케이스 $e^{ix} = \sum_k (ix)^k/k!$ 와 형식적으로 같으므로 같은 표기를 사용한다.

$$
\hat{U} = e^{i\hat{H}}
$$

---

### 6. 회전의 양과 측정 가능한 양의 동일성

§5 의 두 spectral 분해를 나란히 놓는다.

$$
\hat{H} = \sum_n \lambda_n |v_n\rangle\langle v_n|, \quad \hat{U} = \sum_n e^{i\lambda_n} |v_n\rangle\langle v_n|
$$

두 작용소가 같은 사영 $|v_n\rangle\langle v_n|$ 위에 자리잡혀 있다. 사영 부분이 동일하고, 사영에 곱해지는 스칼라가 한쪽에서 $\lambda_n$, 다른 쪽에서 $e^{i\lambda_n}$. 같은 실수 $\lambda_n$ 이 두 표현에 등장한다 — 한 표현에서는 그대로, 다른 표현에서는 지수 안의 phase 각도로.

$\hat{U}$ 의 작용을 본다. 사영 $|v_n\rangle\langle v_n|$ 에 스칼라 $e^{i\lambda_n}$ 가 곱해진다. $|e^{i\lambda_n}| = 1$ 이므로 사영의 크기가 유지되고 위상만 $\lambda_n$ 각도로 회전. $\hat{U}$ 가 부분 공간 $|v_n\rangle$ 방향을 $\lambda_n$ 만큼 위상 회전시키는 작용소.

$\hat{H}$ 의 작용을 본다. 사영 $|v_n\rangle\langle v_n|$ 에 스칼라 $\lambda_n$ 이 곱해진다. 실수 배율. $\hat{H}$ 가 부분 공간 $|v_n\rangle$ 방향에서 $\lambda_n$ 의 값을 측정하는 작용소.

같은 $\lambda_n$ 이 두 작용소에서 서로 다른 역할을 한다. $\hat{U}$ 에서는 회전의 양, $\hat{H}$ 에서는 측정값. 회전의 양 자체가 측정 가능한 양.

$\hat{H}$ 가 $\hat{U}$ 와 무관하게 외부에서 정의된 작용소가 아니다. §5 의 도출에서 $\hat{H}$ 가 $\hat{U}$ 의 spectral 분해에 들어있는 phase 각도들 $\{\lambda_n\}$ 을 모아 작용소 형태로 정리한 결과. $\hat{U}$ 와 $\hat{H}$ 가 별개의 두 작용소가 아니라 같은 spectral 정보의 두 표현 — 한 표현이 위상 곱셈 (회전), 다른 표현이 스칼라 곱셈 (측정).

**Noether 와의 연결**

대칭 변환을 유니타리 $\hat{U}$ 로 기술한다. §5 의 결과에 의해 모든 유니타리가 어떤 Hermitian $\hat{H}$ 로부터 자연 등장한다. $\hat{H}$ 가 변환 $\hat{U}$ 의 generator.

$\hat{H}$ 가 Hermitian 이므로 그 고유값 $\lambda_n$ 이 실수 — 측정 가능한 양. 대칭 변환을 일으키는 양이 측정 가능한 양이다.

$\hat{H}$ 가 자기 자신과 commute 한다 (자명). $\hat{U} = e^{i\hat{H}}$ 의 spectral 분해가 $\hat{H}$ 의 spectral 분해와 같은 기저를 사용하므로 $\hat{H}$ 와 $\hat{U}$ 도 commute. 변환 $\hat{U}$ 가 generator $\hat{H}$ 를 변화시키지 않는다.

대칭 변환의 generator 가 측정 가능한 양이며 그 변환 하에서 보존되는 양이다. 시간 진화 unitary $\hat{U}(t)$ 의 1-parameter 군 구조와 Heisenberg 운동 방정식을 추가하면 시간 불변 보존량의 statement (Noether 의 양자 버전) 가 도출되며, 시간 진화의 1-parameter 군 framework 이 후속 Lie 군 chapter 에서 다뤄진다.
