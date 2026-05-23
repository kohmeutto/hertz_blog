+++
title = "리 군과 예제"
weight = 4
+++

### 1. 동기

지금까지 군(§2)과 다양체(§3)를 따로 봤다. 이 두 구조가 *동시에* 얹힌 것이 리 군(Lie group)이다. 이 장에서는 리 군의 정의를 짚고, 회전 행렬 $SO(2)$를 표준 예제로 다룬다. 이어서 시각화에 유용한 행렬 다양체들(2-구면, 1매개변수 곡선들)도 함께 본다.

### 2. 리 군의 정의

**1)** *리 군(Lie group)* 은 다음 두 구조가 양립하는 집합 $G$다.
- 매끄러운 다양체(§3) 의 구조
- 군(§2) 의 구조

**2)** *양립*이란 군 연산이 다양체 구조와 *매끄럽게* 어울린다는 뜻이다. 구체적으로 다음 두 사상이 매끄러워야 한다.
- 곱셈 사상 $\mu: G \times G \to G,\ (a, b) \mapsto a \cdot b$
- 역원 사상 $\iota: G \to G,\ a \mapsto a^{-1}$

**3)** 즉 군 연산이 매개변수에 대해 $C^\infty$로 변한다는 것이다.

**4)** 리 군은 *군 연산 하나*만 가진다. "매끄러움"은 이 연산의 *성질*이지 별도의 이항 연산이 아니다 (§2.6 참조). 따라서 리 군은 환이 아닌 군이다.

### 3. 표준 예제: SO(2)

**1)** $SO(2)$는 2차원 회전 행렬의 집합이다.

$$R(\tau) = \begin{pmatrix} \cos\tau & -\sin\tau \\ \sin\tau & \cos\tau \end{pmatrix}, \qquad \tau \in [0, 2\pi)$$

**2)** 군 구조:
- 곱셈: $R(\tau_1) \cdot R(\tau_2) = R(\tau_1 + \tau_2)$
- 항등원: $R(0) = I$
- 역원: $R(\tau)^{-1} = R(-\tau)$

**3)** 다양체 구조:
- 매개변수 1개 ($\tau$) → 내재적 차원 1
- $\tau = 0$과 $\tau = 2\pi$가 같은 점이라 *원*의 위상을 가진다
- 외재적으로는 4차원 행렬 공간 안에 심어진 곡선

**4)** 매끄러움: $R(\tau)$의 성분이 $\tau$에 대해 매끄럽고, $R(\tau_1)\cdot R(\tau_2) = R(\tau_1 + \tau_2)$로 곱셈도 매개변수 차원에서 매끄럽다.

**5)** *시각화*: 회전각 $\tau$가 원을 한 바퀴 도는 그림.

<svg viewBox="0 0 300 290" xmlns="http://www.w3.org/2000/svg" style="display:block;margin:auto;max-width:300px">
  <circle cx="150" cy="140" r="90" fill="none" stroke="black" stroke-width="2"/>
  <circle cx="240" cy="140" r="4" fill="black"/>
  <text x="248" y="145" font-size="12">τ = 0 (I)</text>
  <circle cx="150" cy="50" r="4" fill="black"/>
  <text x="115" y="40" font-size="12">τ = π/2</text>
  <circle cx="60" cy="140" r="4" fill="black"/>
  <text x="15" y="145" font-size="12">τ = π</text>
  <circle cx="150" cy="230" r="4" fill="black"/>
  <text x="115" y="252" font-size="12">τ = 3π/2</text>
  <path d="M 232,160 L 226,170 L 238,168 Z" fill="#0066cc"/>
  <text x="245" y="175" font-size="11" fill="#0066cc">τ 증가</text>
  <text x="150" y="280" text-anchor="middle" font-size="13" font-style="italic">SO(2) ≅ S¹</text>
</svg>

### 4. 시각화용 행렬 다양체: 2-구면

**1)** 다음 형식의 $2 \times 2$ 에르미트 무대각합 행렬을 본다.

$$M(x, y, z) = x\sigma_x + y\sigma_y + z\sigma_z = \begin{pmatrix} z & x - iy \\ x + iy & -z \end{pmatrix}$$

여기서 $\sigma_x, \sigma_y, \sigma_z$는 파울리 행렬이다.

$$\sigma_x = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}, \quad \sigma_y = \begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix}, \quad \sigma_z = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}$$

**2)** 파울리 행렬의 대수에서 $\sigma_i \sigma_j + \sigma_j \sigma_i = 2\delta_{ij}I$가 성립하므로

$$M^2 = (x^2 + y^2 + z^2)\, I$$

따라서 $M^2 = I$ 조건은 $x^2 + y^2 + z^2 = 1$, 즉 단위 *2-구면*과 일치한다.

**3)** 매개변수 공간 $(x, y, z) \in \mathbb{R}^3$ 위에서 단위 구면이 다양체이고, 그 위의 각 점이 하나의 행렬에 대응된다.

**4)** 차원: 매개변수가 형식적으로 3개지만 $x^2 + y^2 + z^2 = 1$ 구속이 있어 *자유도*는 2. 즉 내재적 차원이 2인 다양체다.

**5)** 시각화: 에르미트 무대각합 행렬 공간 자체가 3차원($\mathbb{R}^3$)이라, 우리가 사는 공간에 그대로 단위 구를 그리면 된다.

<svg viewBox="0 0 320 320" xmlns="http://www.w3.org/2000/svg" style="display:block;margin:auto;max-width:320px">
  <circle cx="160" cy="160" r="100" fill="none" stroke="black" stroke-width="2"/>
  <path d="M 60,160 A 100,25 0 0,0 260,160" fill="none" stroke="black" stroke-width="1"/>
  <path d="M 60,160 A 100,25 0 0,1 260,160" fill="none" stroke="black" stroke-width="1" stroke-dasharray="3,3"/>
  <line x1="160" y1="40" x2="160" y2="280" stroke="#888" stroke-width="1.5"/>
  <line x1="40" y1="160" x2="280" y2="160" stroke="#888" stroke-width="1.5"/>
  <line x1="100" y1="200" x2="220" y2="120" stroke="#888" stroke-width="1.5" stroke-dasharray="2,2"/>
  <circle cx="160" cy="60" r="5" fill="#cc0000"/>
  <text x="170" y="55" font-size="13">(0,0,1): σ_z</text>
  <circle cx="260" cy="160" r="5" fill="#cc0000"/>
  <text x="200" y="178" font-size="13">(1,0,0): σ_x</text>
  <circle cx="220" cy="120" r="5" fill="#cc0000"/>
  <text x="225" y="115" font-size="13">(0,1,0): σ_y</text>
  <text x="160" y="305" text-anchor="middle" font-size="13" font-style="italic">M² = I, M = xσ_x + yσ_y + zσ_z, x²+y²+z²=1</text>
</svg>

**6)** *주의*: 이 2-구면은 *리 군은 아니다*. 군 연산이 자연스럽게 주어지지 않기 때문이다. 다만 "행렬들이 이루는 다양체"의 직관을 잡기 좋은 예다. (양자정보에서 *블로흐 구면(Bloch sphere)*과 유사한 형태로 등장한다.)

### 5. 1매개변수 곡선들

**1)** 매개변수 1개로 만든 행렬은 행렬 공간 안에서 *1차원 곡선*을 그린다. 위의 무대각합 에르미트 행렬 공간 $\mathbb{R}^3$에서 모양만 다른 곡선들을 본다.

**2)** example1) 직선

$$M(\tau) = \tau \sigma_z = \begin{pmatrix} \tau & 0 \\ 0 & -\tau \end{pmatrix}$$

$(x, y, z) = (0, 0, \tau)$. $z$축을 따라가는 직선.

**3)** example2) 원

$$M(\tau) = \cos\tau \, \sigma_x + \sin\tau \, \sigma_y$$

$(x, y, z) = (\cos\tau,\, \sin\tau,\, 0)$. $xy$평면 위의 단위 원.

**4)** example3) 나선

$$M(\tau) = \cos\tau \, \sigma_x + \sin\tau \, \sigma_y + \tau \, \sigma_z$$

$(x, y, z) = (\cos\tau,\, \sin\tau,\, \tau)$. $z$축을 따라 위로 감기는 나선.

<svg viewBox="0 0 280 400" xmlns="http://www.w3.org/2000/svg" style="display:block;margin:auto;max-width:280px">
  <line x1="140" y1="370" x2="140" y2="40" stroke="#666" stroke-width="1.5"/>
  <text x="148" y="45" font-size="13">z</text>
  <line x1="40" y1="350" x2="240" y2="350" stroke="#666" stroke-width="1.5"/>
  <text x="245" y="355" font-size="13">x</text>
  <line x1="110" y1="370" x2="170" y2="320" stroke="#666" stroke-width="1.5" stroke-dasharray="2,2"/>
  <text x="92" y="375" font-size="13">y</text>
  <polyline points="200,350 182,323 140,301 98,284 80,271" fill="none" stroke="#0066cc" stroke-width="2" stroke-dasharray="5,3"/>
  <polyline points="80,271 98,259 140,242 182,220 200,193" fill="none" stroke="#0066cc" stroke-width="2"/>
  <polyline points="200,193 182,166 140,144 98,127 80,114" fill="none" stroke="#0066cc" stroke-width="2" stroke-dasharray="5,3"/>
  <text x="205" y="345" font-size="11" fill="#0066cc">τ = 0</text>
  <text x="205" y="190" font-size="11" fill="#0066cc">τ = 2π</text>
  <text x="65" y="110" font-size="11" fill="#0066cc">τ = 3π</text>
</svg>

**5)** *핵심*: 세 예 모두 매개변수가 1개라 *내재적 차원은 1*인 곡선이다. 모양만 직선/원/나선으로 다를 뿐이다. 외재적으로는 3차원 공간 안에 *심어진* 1차원 곡선이다.

**6)** 이 곡선들은 일반적으로 리 군은 아니다 (군 연산이 곡선 위에서 닫히지 않는다). 다만 "1매개변수 다양체가 3차원 공간 안에서 다양한 모양으로 보일 수 있다"는 직관을 준다.

### 6. 정리

**1)** 리 군 = 매끄러운 다양체 + 군 구조 (양립). 군 연산이 매개변수에 대해 매끄럽다.

**2)** *유일한 이항 연산*은 군 곱셈. 매끄러움은 이 연산의 성질이지 별도의 이항 연산이 아니라서 환이 아니다.

**3)** $SO(2)$는 1차원 리 군의 표준 예. 원의 위상을 가지며 회전각 $\tau$가 매개변수다.

**4)** 파울리 행렬의 2-구면, 1매개변수 곡선들은 리 군은 아니지만 *행렬 다양체*의 시각화 직관을 잡는 데 유용하다. 매개변수 개수와 다양체 차원의 관계를 구체적 행렬 예로 확인할 수 있다.
