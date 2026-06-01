+++
title = "(b) Pesudo-adjoint"
weight = 2
+++

---

### 1.  M-계량 공간에서 내적의 정의

양의 정부호 허미션 계량 연산자 $\hat{M}$ ($\hat{M} = \hat{M}^\dagger, \hat{M} > 0$)이 부여된 선형 공간에서, 임의의 두 상태 벡터 $|\phi\rangle, |\psi\rangle$에 대한 $\hat{M}$-내적 구조는 다음과 같이 정의된다.
$$
\langle \phi | \psi \rangle_M \equiv \langle \phi | \hat{M} | \psi \rangle
$$

---

### 2. 유사 수반성 정의

**1) 유한 차원**

공간적 영역의 경계가 존재하지 않아 부분 적분에 의한 경계 평가항이 소거되는 유한 차원 행렬 대수 공간에서, 선형 연산자 $\hat{A}$에 대응하는 유사 수반 연산자(Pseudo-adjoint operator) $\hat{A}^\sharp$는 $\hat{M}$-내적의 불변성을 매개하는 다음의 연산자 수반 법칙을 충족하는 고유한 작용소로 정의된다.
$$
\langle \phi | \hat{A} \psi \rangle_{M} = \langle \hat{A}^\sharp \phi | \psi \rangle_{M}
$$

**2) 무한 차원**


무한 차원 함수 공간에서 미분 작용소를 포함하는 연산자를 다룰 경우, 내적 적분 연산 과정에서 부분 적분이 수반되므로 영역 경계에서의 평가항이 필연적으로 발생한다. 계량 연산자 $\hat{M}$이 미분 작용소를 내포하는 소볼레프 계량 기전으로 확장되더라도, 형식적 자기 수반성($\hat{M}^\dagger = \hat{M}$)에 의하여 도메인 내부(Bulk)에서의 대수적 결합 법칙은 불변이다.

$\hat{M}$-내적 공간에서의 전역적 유사 수반 관계식은 $\hat{M}$과 $\hat{A}$의 미분 작용에 의해 생성되는 전체 경계 선형 형식 $\mathcal{R}(\hat{M}\hat{A})[\phi, \psi]$를 동반하여 다음과 같이 정식화된다.

$$
\langle \phi | \hat{A} \psi \rangle_{M} = \langle \hat{A}^\sharp \phi | \psi \rangle_{M} + \mathcal{R}(\hat{M}\hat{A})[\phi, \psi]
$$

---

### 3. 유사 수반 연산자와 수반 연산자의 관계

$$
\hat{A}^\dagger\hat{M} = \hat{M}\hat{A}^\sharp \implies \hat{A}^\sharp = \hat{M}^{-1}\hat{A}^\dagger\hat{M}
$$

proof)

$$
\langle \phi | \hat{M}\hat{A} \psi \rangle = \langle (\hat{M}\hat{A})^\dagger \phi | \psi \rangle + \mathcal{R}(\hat{M}\hat{A})[\phi, \psi]
$$

M-공간에서의 표기는 아래와 같으며, 이를 비교해 본다.

$$
\langle \phi | \hat{A} \psi \rangle_{M} = \langle \hat{A}^\sharp \phi | \psi \rangle_{M} + \mathcal{R}(\hat{M}\hat{A})[\phi, \psi]
$$

비교하면 아래와 같다.

$$
\hat{M}^\dagger\hat{A}^\sharp=(\hat{M}\hat{A})^\dagger=\hat{A}^\dagger\hat{M}^\dagger
$$

계량 연산자의 자기 수반성($\hat{M} = \hat{M}^\dagger$)을 적용한다. 따라서, 

$$
\hat{A}^\dagger\hat{M} = \hat{M}\hat{A}^\sharp \implies \hat{A}^\sharp = \hat{M}^{-1}\hat{A}^\dagger\hat{M}
$$

---