+++
title = "(a) Symplectic matrix"
weight = 10
+++

---

수반 연산자를 구하는 과정은 시스템이 정의된 **공간의 성격(내적의 정의)** 에 따라 달라진다. 하지만 그 모든 과정은 단 하나의 목표 즉 연산자를 브라(Bra) 쪽으로 넘겼을 때 결과값(스칼라)의 불변성을 유지하는 것에 집중한다.

---

### 1. 유한 차원: 행렬 성분의 자리 바꾸기

$$
(A^\dagger)_{ij} = (A_{ji})^{\ast}
$$

proof) 

행렬 $A$의 수반 행렬 $A^\dagger$가 왜 '켤레 전치'가 되는지는 성분 단위의 비교를 통해 자명해진다.

- 좌변 (대상에 작용): $\langle v | Aw \rangle = \sum_i \sum_j v_i^* A_{ij} w_j$
- 우변 (관찰자에 작용): $\langle A^\dagger v | w \rangle = \sum_j \sum_i (A^\dagger_{ji})^* v_i^* w_j$


---

### 2. 미분 연산자, 수반연산자 도출의 부품

**1) 미분의 부품, 형식적 수반(formal adjoint) & 경계항**

$$
\hat{D}=\frac{d}{dx} \implies \hat{D}^{\dagger}=-\frac{d}{dx} \quad\text{with boundary term: } [\phi^{\ast}\psi]_a^b
$$

proof)

$$
\langle \phi|\hat{D}\psi\rangle
=\int_a^b dx\left\lbrack\phi^{\ast}\frac{d}{dx}\psi\right\rbrack
=\int_a^b dx\left\lbrack\frac{d}{dx}\phi^{\ast}\psi-\psi\frac{d}{dx}\phi^{\ast}\right\rbrack
=\left\lbrack \phi^{\ast}\psi\right\rbrack^b_a-\int_a^b dx\left\lbrack\psi\frac{d}{dx}\phi^{\ast}\right\rbrack
$$

$$
=\left\lbrack \phi^{\ast}\psi\right\rbrack^b_a+\langle\hat{D}^{\dagger}\phi|\psi\rangle
$$

위를 라그랑주 항등식(Lagrange Identity) 이라고 하며, 아래와 같이 구분한다.

$$\langle \phi | \hat{D} \psi \rangle = \underbrace{\langle-\hat{D}\phi|\psi\rangle}_{\text{formal adjoint}}+\underbrace{\left\lbrack\phi^{\ast}\psi\right\rbrack^b_a}_{\text{boundary term}}
$$

**2) 복소수 함수의 부품**

$$
q(x)^{\dagger}=q(x)^{\ast}
$$

proof)

$$
\langle \phi | p \psi \rangle = \int dx \phi^* p \psi = \int dx (p^* \phi)^* \psi = \langle p^* \phi | \psi \rangle
$$

**3) $\dagger$의 역순법칙과 선형성**

- 역순 법칙: $(\hat{A}\hat{B})^\dagger = \hat{B}^\dagger \hat{A}^\dagger$
- 선형성: $(\hat{A} + \hat{B})^\dagger = \hat{A}^\dagger + \hat{B}^\dagger$

---

### 3. 미분연산자의 경계항: 심플레틱 행렬

이전 챕터에서 수반 연산자는 측정의 관점을 바꾸는 도구라고 하였다. 이 관점의 전환 과정에서 발생하는 부산물들을 어떻게 체계적으로 관리할 것인가가 본 장의 핵심이다. 앞서 정의한 **'미분 부품'** 을 확장하면, 임의의 차수에 대한 경계항 $J$를 다음과 같이 일반화할 수 있다.

$$
\langle \phi | L \psi \rangle - \langle L^\dagger \phi | \psi \rangle = [ \langle \Phi | \Omega | \Psi \rangle ]_a^b
$$

$k$차 미분 연산자에서 시스템의 상태를 완벽히 규정하기 위해서는 0차(함숫값)부터 $k-1$차 미분치까지의 모든 정보가 필요하다. 따라서 상태 벡터 $\vec{\Psi}$는 다음과 같은 $k \times 1$ 열벡터로 정의된다. 이는 시스템의 현재 위치뿐만 아니라, 모든 고차 미분 정보를 포함하는 **고차원 위상 공간(High-dimensional Phase Space)** 의 좌표이다.

$$
\vec{\Phi} = \begin{bmatrix} \phi \\ \phi' \\ \phi'' \\ \vdots \\ \phi^{(k-1)} \end{bmatrix}, \quad
\vec{\Psi} = \begin{bmatrix} \psi \\ \psi' \\ \psi'' \\ \vdots \\ \psi^{(k-1)} \end{bmatrix}
$$

상태 벡터들 사이에서 '배턴 터치'를 수행하는 $\mathbf{\Omega}$는 $k \times k$ 행렬이며, $+1$, $-1$이 번갈아 나타난다. (계수 $p$가 있다면 여기에 $p$가 곱해진다.) 모양은 주대각선이 아니라 '부대각선(Anti-diagonal)' 방향으로 성분들이 배치되는 반대칭(Skew-symmetric) 행렬이 된다. $k=4$ (4차 미분 연산자)일 때 $J$를 조립해 보면, 상태 벡터는 $4 \times 1$이 되고 $\mathbf{\Omega}$는 다음과 같은 $4 \times 4$ 행렬이 강제된다.

$$
J = \begin{bmatrix} \phi^\ast & \phi^{\ast'} & \phi^{\ast''} & \phi^{\ast'''} \end{bmatrix} 
\underbrace{\begin{bmatrix} 
0 & 0 & 0 & 1 \\
0 & 0 & -1 & 0 \\
0 & 1 & 0 & 0 \\
-1 & 0 & 0 & 0 
\end{bmatrix}}_{\mathbf{\Omega}}
\begin{bmatrix} \psi \\ \psi' \\ \psi'' \\ \psi''' \end{bmatrix}
$$


proof)

**(1) 적분에서 연산자 대수로: 미분 취하기**

$$
\langle \phi|\hat{D}^k\psi\rangle-\langle (-\hat{D})^k\phi|\psi\rangle
=J(\phi,\psi)
$$

여기서 적분 기호를 제거하고 연산자 자체의 구조를 직접 들여다보기 위해, 양변에 미분 연산($D$)을 취한다.

$$
\phi^{\ast}\hat{D}^k\psi-\psi(-\hat{D})^k\phi^{\ast}=DJ(\phi,\psi)
$$

**(2) 망원 급수를 통한 유도**

$$
D^k - \bar{D}^k = (D - \bar{D}) \sum_{j=0}^{k-1} D^{k-1-j} \bar{D}^j
$$

위의 연산자 구조를 입히면, $J$의 정체가 나오게 된다.

$$
\phi^{\ast}\hat{D}^k\psi-\psi(-\hat{D})^k\phi^{\ast} = D \left[ \sum_{j=0}^{k-1} ((-D)^j \phi^{\ast}) \cdot (D^{k-1-j} \psi) \right]
$$

J에 대해 정리하면,

$$
J = \sum_{j=0}^{k-1} (-1)^j \phi^{\ast(j)} \psi^{(k-1-j)}
$$
 
**(3) 상태 벡터 확장**

미분 차수가 1일 때($k=1$), 스칼라 이다.

$$
J=[\phi^\ast]1[\psi]
$$

미분 차수가 2 이상일 때 ($k=2~$), 심플레틱 행렬이 탄생하게 된다. 이것은 이전 챕터에서 다룬 **'미분 내제(론스키안)'** 와 완전히 일치한다. 이를 상태 벡터로 사영하면 다음과 같은 행렬 구조가 강제된다.

$$
J = \phi^\ast \psi' - \phi^{\ast'} \psi
= \begin{bmatrix}
\phi^\ast & \phi^{\ast'}
\end{bmatrix} \begin{bmatrix}
0 & 1 \\ -1 & 0
\end{bmatrix} \begin{bmatrix}
\psi \\ \psi'
\end{bmatrix}
$$

여기서 나타나는 **$\mathbf{\Omega} = \begin{bmatrix} 0 & 1 ; -1 & 0 \end{bmatrix}$** 이 바로 심플레틱 행렬이다.

---
