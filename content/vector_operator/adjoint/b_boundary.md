+++
title = "(b) Boundary"
weight = 2
+++

---

### 1. 경계항의 성질

**1) 선형성**

연산자의 선형 결합에 대해 $\mathcal{R}$ 도 같은 선형 결합 형태:

$$
\mathcal{R}(\alpha\hat{A} + \beta\hat{B})[\phi, \psi] = \alpha\,\mathcal{R}\hat{A}[\phi, \psi] + \beta\,\mathcal{R}\hat{B}[\phi, \psi]
$$

proof)

$\mathcal{R}$ 의 정의에 직접 대입.

$$
\langle\phi|(\alpha\hat{A} + \beta\hat{B})\psi\rangle = \alpha\langle\phi|\hat{A}\psi\rangle + \beta\langle\phi|\hat{B}\psi\rangle
$$

각 항을 레지듀 형태로 변환.

$$
= \alpha\bigl(\langle\hat{A}^\dagger\phi|\psi\rangle + \mathcal{R}\hat{A}[\phi, \psi]\bigr) + \beta\bigl(\langle\hat{B}^\dagger\phi|\psi\rangle + \mathcal{R}\hat{B}[\phi, \psi]\bigr)
$$

내적의 sesquilinear 성으로 $(\alpha\hat{A} + \beta\hat{B})^\dagger\phi = \alpha^*\hat{A}^\dagger\phi + \beta^*\hat{B}^\dagger\phi$ 를 고려하면 첫 항들이 $\langle(\alpha\hat{A} + \beta\hat{B})^\dagger\phi|\psi\rangle$ 로 통합. 따라서 남은 부분이

$$
\mathcal{R}(\alpha\hat{A} + \beta\hat{B})[\phi, \psi] = \alpha\,\mathcal{R}\hat{A}[\phi, \psi] + \beta\,\mathcal{R}\hat{B}[\phi, \psi]
$$

**2) 곱셈규칙**

$$
\langle\phi|\hat{A}\hat{B}|\psi\rangle
=\langle\hat{B}^\dagger\hat{A}^\dagger\phi||\psi\rangle+\mathcal{R}(\hat{A}\hat{B})[\phi,\psi]
$$

핵심

$$
\mathcal{R}(\hat{A}\hat{B})[\phi,\psi]
=\mathcal{R}\hat{A}[\phi,\hat{B}\psi]+\mathcal{R}\hat{B}[\hat{A}^\dagger\phi,\psi]
$$

proof)

$\hat{A}$ 를 먼저 브라 쪽으로 옮긴다 ($\hat{B}\psi$ 를 새 켓으로 봄):

$$
\langle\phi|\hat{A}(\hat{B}\psi)\rangle = \langle\hat{A}^\dagger\phi|\hat{B}\psi\rangle + \mathcal{R}\hat{A}[\phi, \hat{B}\psi]
$$

그 후 $\hat{B}$ 를 브라 쪽으로 옮긴다 ($\hat{A}^\dagger\phi$ 를 새 브라로 봄):

$$
\langle\hat{A}^\dagger\phi|\hat{B}\psi\rangle = \langle\hat{B}^\dagger\hat{A}^\dagger\phi|\psi\rangle + \mathcal{R}\hat{B}[\hat{A}^\dagger\phi, \psi]
$$

결합:

$$
\langle\phi|\hat{A}\hat{B}\psi\rangle = \langle\hat{B}^\dagger\hat{A}^\dagger\phi|\psi\rangle + \mathcal{R}\hat{A}[\phi, \hat{B}\psi] + \mathcal{R}\hat{B}[\hat{A}^\dagger\phi, \psi]
$$

마지막 두 항이 $\mathcal{R}(\hat{A}\hat{B})$ 의 정의. 부분 적분을 두 번 수행한 결과, 각 단계의 중첩된 변형이 인자로 들어옴.

---

### 2. 적용

**1) 곱셈 작용소**

$$
\hat{M}:=p\cdot
\implies \mathcal{R}\hat{M}=0
$$

proof)

$$
\langle\phi|\hat{M}\psi\rangle=\langle\hat{M}^\dagger\phi|\psi\rangle
$$

경계항이 발생 안 함. 따라서,

$$
\mathcal{R}\hat{M}=0
$$

**2) 2차 미분**

$$
\mathcal{R}\hat{D}^2[\phi,\psi] = [\phi^*\psi' -(\phi^*)'\psi]^a_b
=\begin{vmatrix} \phi^\ast & \psi \\ (\phi^*)' & \psi'\end{vmatrix}^a_b
$$

proof)

$$
\mathcal{R}\hat{D}^2[\phi,\psi]
=\mathcal{R}\hat{D}[\phi,\hat{D}\psi]+\mathcal{R}\hat{D}[\hat{D}^\dagger\phi,\psi]
$$

여기에서,

$$
\mathcal{R}\hat{D}[\phi,\hat{D}\psi] = [\phi^*\psi']^a_b,\quad \mathcal{R}\hat{D}[\hat{D}^\dagger\phi,\psi] = [-(\phi^*)'\psi]^a_b
$$

따라서,

$$
\mathcal{R}\hat{D}^2[\phi,\psi] = [\phi^*\psi' -(\phi^*)'\psi]^a_b
$$

**3) Strum-Lioville** 

$$
\hat{L}=\hat{D}p\hat{D}+q,\quad\text{단, $p,q$ 는 모두 실수이다.}
$$

$$
\mathcal{R}\hat{L} = [p(\phi^*\psi' -(\phi^*)'\psi)]^a_b
=\left(p\begin{vmatrix} \phi^\ast & \psi \\ (\phi^*)' & \psi'\end{vmatrix}\right)^a_b
$$

proof)

선형성을 적용한다.

$$
\mathcal{R}\hat{L}=\mathcal{R}(\hat{D}p\hat{D})+\mathcal{R}({q\hat{I}})
$$

(1) 첫번째 항

$$
\mathcal{R}(\hat{D}p\hat{D})
=\mathcal{R}\hat{D}[\phi,p\hat{D}\psi]+\mathcal{R}(p\hat{D})[\hat{D}^\dagger\phi,\psi]
$$

$$
=\mathcal{R}\hat{D}[\phi,p\hat{D}\psi]
+\mathcal{R}(p\cdot)[\hat{D}^\dagger\phi,\hat{D}\psi]
+\mathcal{R}\hat{D}[p^\dagger\hat{D}^\dagger\phi,\psi]
$$

$$
=\mathcal{R}\hat{D}[\phi,p\hat{D}\psi]
+\mathcal{R}\hat{D}[p^\dagger\hat{D}^\dagger\phi,\psi]
$$

$$
=[p(\phi^*\psi' -(\phi^*)'\psi)]^a_b
$$

(2) 두번째 항

$$
\mathcal{R}({q\hat{I}})=0
$$

---

### 3. 심플레틱 행렬

2차 미분과 §2-(3) 의 SL 연산자에서 $\mathcal{R}$ 이 phase space 벡터의 결정식 형태로 나타났다. 이를 일반화하면 **심플렉틱 행렬 (symplectic matrix)** 이 등장한다.

**1) 2차의 경우 — 자연 등장**

2차 미분의 결과:

$$
\mathcal{R}\hat{D}^2[\phi, \psi] = \phi^*\psi' - (\phi^*)'\psi\bigg|_a^b
$$

phase space 벡터 $\Phi = (\phi, \phi')^T$, $\Psi = (\psi, \psi')^T$ 로 표기하면

$$
\mathcal{R}\hat{D}^2[\phi, \psi] = \begin{bmatrix}\phi^* & (\phi^*)'\end{bmatrix}\begin{bmatrix}0 & 1\\-1 & 0\end{bmatrix}\begin{bmatrix}\psi\\\psi'\end{bmatrix}\bigg|_a^b = \bigl[\Phi^*\Omega_2\Psi\bigr]_a^b
$$

여기서 $\Omega_2$ 가 2x2 심플렉틱 행렬:

$$
\Omega_2 = \begin{pmatrix}0 & 1\\-1 & 0\end{pmatrix}
$$

부대각선에서 $+1, -1$ 이 등장하는 반대칭 행렬. 이 행렬을 별도로 정의한 것이 아니라, 곱셈 규칙의 결과에서 자연 추출된 것.

**2) 4차의 경우**

$\hat{D}^4 = \hat{D}\hat{D}\hat{D}\hat{D}$ 에 곱셈 규칙을 세 번 반복하면

$$
\mathcal{R}\hat{D}^4[\phi, \psi] = [\phi^*\psi''' - (\phi^*)'\psi'' + (\phi^*)''\psi' - (\phi^*)'''\psi]_a^b
$$

phase space 벡터 $\Phi = (\phi, \phi', \phi'', \phi''')^T$, $\Psi = (\psi, \psi', \psi'', \psi''')^T$ 로 표기:

$$
\mathcal{R}\hat{D}^4[\phi, \psi] = \bigl[\Phi^*\Omega_4\Psi\bigr]_a^b
$$

with

$$
\Omega_4 = \begin{pmatrix}0 & 0 & 0 & 1\\0 & 0 & -1 & 0\\0 & 1 & 0 & 0\\-1 & 0 & 0 & 0\end{pmatrix}
$$

부대각선 (anti-diagonal) 에서 부호가 교대로 등장하는 반대칭 행렬.

**3) 일반 $k$ 차 미분**

$\hat{D}^k$ 의 곱셈 규칙을 $k-1$ 번 반복하면

$$
\mathcal{R}\hat{D}^k[\phi, \psi] = \sum_{m=0}^{k-1}(-1)^m\bigl[(\phi^*)^{(m)}\psi^{(k-1-m)}\bigr]_a^b
$$

phase space 벡터 $\Phi = (\phi, \phi', \ldots, \phi^{(k-1)})^T$ 로 표기하면

$$
\mathcal{R}\hat{D}^k[\phi, \psi] = \bigl[\Phi^*\Omega_k\Psi\bigr]_a^b
$$

with $\Omega_k$ 가 $k\times k$ 심플렉틱 행렬:

$$
(\Omega_k)_{ij} = \begin{cases}(-1)^{i-1} & \text{if } i + j = k+1\\0 & \text{otherwise}\end{cases}
$$

부대각선 ($i + j = k+1$) 에서 부호 교대, 나머지 0. 반대칭 ($\Omega_k^T = -\Omega_k$, $k$ 짝수일 때).

**4) 심플렉틱 형식의 의미**

$\Omega$ 는 phase space (함수와 모든 도함수의 묶음) 위의 **심플렉틱 형식 (symplectic form)**. 고전 역학의 phase space $(q, p)$ 위의 $dq \wedge dp$ 와 같은 구조이다.

함수가 위치 ($q$) 에, 도함수가 운동량 ($p$) 에 대응하는 자연스러운 대응. 이 대응이 미분 연산자의 boundary 분석에 phase space 의 기하학적 구조를 부여한다.

**5) BC 와 라그랑지안 부분공간**

$\mathcal{R} = 0$ 의 조건이 모든 $\phi, \psi \in \mathcal{D}$ 에 대해 만족되려면, boundary 위의 phase space 벡터들이 심플렉틱 형식이 0 인 부분공간 — **라그랑지안 부분공간 (Lagrangian subspace)** — 에 있어야 한다.

가능한 라그랑지안 부분공간들의 집합이 미분 연산자의 self-adjoint extension 의 집합과 일대일 대응. 표준 BC (Dirichlet, Neumann, periodic, mixed) 들이 모두 라그랑지안 부분공간의 구체적 사례이다.
