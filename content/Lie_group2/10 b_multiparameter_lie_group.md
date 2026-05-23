+++
title = "다변수 리 군과 생성자"
weight = 10
+++

### 1. 동기

§9에서 1매개변수 부분군과 행렬 $X$ 의 일대일 대응을 봤다. 이 장에서는 매개변수가 *여러 개* 인 일반적인 리 군으로 일반화한다.

$n$ 차원 리 군에서는 단위원 근처를 $n$ 개의 매개변수로 라벨링할 수 있고, 각 매개변수 방향마다 *생성자(generator)* 라 부를 행렬이 하나씩 나온다. 이들이 모여 더 풍부한 구조를 이루는데, 핵심은 *비교환성* 이다 (다음 장에서 본격 다룬다).

### 2. $n$ 차원 리 군의 다변수 매개변수화

**1)** 리 군 $G$ 가 *$n$ 차원 다양체*일 때, 단위원 근처의 점들은 $n$ 개의 매개변수 $(\tau^1, \tau^2, \ldots, \tau^n) \in \mathbb{R}^n$ 으로 라벨링된다.

**2)** 즉 어떤 매끄러운 사상 $g: \mathbb{R}^n \to G$ 가 있어
- $g(0, 0, \ldots, 0) = e$ (단위원)
- $0$ 근처의 $(\tau^1, \ldots, \tau^n)$ 마다 $g(\tau^1, \ldots, \tau^n) \in G$

**3)** 매개변수 개수 $n$ 이 리 군의 *차원* 이다 (§3의 다양체 차원).

**4)** example) $SO(3)$ (3차원 회전군): $n = 3$. 매개변수는 회전축의 세 성분, 또는 오일러 각 $(\phi, \theta, \psi)$ 등.

### 3. 다중 생성자

**1)** 단위원에서 각 매개변수 $\tau^a$ 방향으로 편미분하면 *$n$ 개의 행렬*이 나온다.

$$X_a = \left.\frac{\partial g}{\partial \tau^a}\right|_{\tau=0}, \qquad a = 1, \ldots, n$$

**2)** 이 $X_a$ 들은 각각 *생성자(generator)* 다. §9에서 1매개변수 경우의 단 하나의 생성자 X 를 정의했는데, 이제 같은 개념이 *n 개*로 확장된 것이다. 각 $X_a$ 는 단위원에서 $\tau^a$ 방향의 1매개변수 부분군 $\exp(\tau X_a)$ 를 생성한다.

**3)** $X_a$ 들이 일차독립이라서 단위원에서의 *$n$ 개의 독립적 방향*을 이룬다.

**4)** §5에서 본 1매개변수 경우 ($n=1$) 의 자연스러운 일반화. 하나의 $X$ 대신 $X_1, \ldots, X_n$ 의 모임이다.

**5)** 직관: 각 $X_a$ 는 단위원에서 "$\tau^a$ 방향으로 살짝 움직이면 어디로 가는지" 를 가리킨다.

<svg viewBox="0 0 360 280" xmlns="http://www.w3.org/2000/svg" style="display:block;margin:auto;max-width:360px">
  <defs>
    <marker id="arrA" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
      <path d="M 0,0 L 10,5 L 0,10 z" fill="#0066cc"/>
    </marker>
    <marker id="arrB" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
      <path d="M 0,0 L 10,5 L 0,10 z" fill="#cc0066"/>
    </marker>
    <marker id="arrC" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
      <path d="M 0,0 L 10,5 L 0,10 z" fill="#009955"/>
    </marker>
  </defs>
  <ellipse cx="180" cy="140" rx="150" ry="105" fill="#fafafa" stroke="#aaa" stroke-width="1" stroke-dasharray="4,4"/>
  <text x="60" y="35" font-size="13" fill="#666">리 군 G (n차원 다양체)</text>
  <circle cx="180" cy="140" r="6" fill="black"/>
  <text x="190" y="135" font-size="13">I</text>
  <line x1="180" y1="140" x2="290" y2="140" stroke="#0066cc" stroke-width="2.5" marker-end="url(#arrA)"/>
  <text x="285" y="160" font-size="13" fill="#0066cc">X_1</text>
  <line x1="180" y1="140" x2="245" y2="60" stroke="#cc0066" stroke-width="2.5" marker-end="url(#arrB)"/>
  <text x="255" y="55" font-size="13" fill="#cc0066">X_2</text>
  <line x1="180" y1="140" x2="245" y2="220" stroke="#009955" stroke-width="2.5" marker-end="url(#arrC)"/>
  <text x="255" y="230" font-size="13" fill="#009955">X_3</text>
  <path d="M 180,140 Q 240,150 290,150" fill="none" stroke="#0066cc" stroke-width="1.2" stroke-dasharray="3,3"/>
  <path d="M 180,140 Q 215,90 240,55" fill="none" stroke="#cc0066" stroke-width="1.2" stroke-dasharray="3,3"/>
  <path d="M 180,140 Q 215,190 240,225" fill="none" stroke="#009955" stroke-width="1.2" stroke-dasharray="3,3"/>
  <text x="50" y="265" font-size="11">n개의 생성자가 각각 1매개변수 부분군 exp(τ X_a) 를 정의 (점선 곡선)</text>
</svg>

### 4. 다중 1매개변수 부분군

**1)** 각 생성자 $X_a$ 마다 §9의 일대일 대응에 의해 *1매개변수 부분군*이 정해진다.

$$\phi_a(\tau) = \exp(\tau X_a)$$

$n$ 개의 생성자 → $n$ 개의 1매개변수 부분군.

**2)** 각 부분군은 단위원에서 $X_a$ 방향으로 출발한 매끄러운 곡선이다.

**3)** *이 $n$ 개의 부분군이 리 군 $G$ 의 구조를 충분히 결정*한다 (단위원 근처에서). 다음 장에서 그 이유를 명확히 한다.

### 5. example: $SO(3)$

**1)** $SO(3)$ = 3차원 회전군. $n = 3$.

**2)** 표준 매개변수화는 좌표축 회전이다.

$$R_x(\tau) = \begin{pmatrix} 1 & 0 & 0 \\ 0 & \cos\tau & -\sin\tau \\ 0 & \sin\tau & \cos\tau \end{pmatrix}$$

$$R_y(\tau) = \begin{pmatrix} \cos\tau & 0 & \sin\tau \\ 0 & 1 & 0 \\ -\sin\tau & 0 & \cos\tau \end{pmatrix}$$

$$R_z(\tau) = \begin{pmatrix} \cos\tau & -\sin\tau & 0 \\ \sin\tau & \cos\tau & 0 \\ 0 & 0 & 1 \end{pmatrix}$$

**3)** 각 경우 단위원 ($\tau=0$) 에서의 미분 = 생성자.

$$L_x = \left.\frac{dR_x}{d\tau}\right|_{\tau=0} = \begin{pmatrix} 0 & 0 & 0 \\ 0 & 0 & -1 \\ 0 & 1 & 0 \end{pmatrix}$$

$$L_y = \begin{pmatrix} 0 & 0 & 1 \\ 0 & 0 & 0 \\ -1 & 0 & 0 \end{pmatrix}, \qquad L_z = \begin{pmatrix} 0 & -1 & 0 \\ 1 & 0 & 0 \\ 0 & 0 & 0 \end{pmatrix}$$

**4)** 세 생성자 $L_x, L_y, L_z$ 가 일차독립. $SO(3)$ 의 3개 독립 방향에 정확히 대응한다.

**5)** 각 생성자가 1매개변수 부분군을 정의: $\exp(\tau L_a) = R_a(\tau)$. (확인은 §6에서의 $SO(2)$ 계산과 같은 방식으로 가능.)

**6)** 세 생성자는 모두 *반대칭*: $L_a^T = -L_a$. 이는 $SO(3)$ 가 회전군 (직교 행렬의 군) 이라는 데서 자연스럽게 나오는 성질이다.

### 6. 결정적 차이: 비교환성 미리보기

**1)** 1매개변수 경우 ($n=1$): 같은 $X$ 에서 나온 두 곡선은 항상 *교환*한다.

$$\exp(\tau X) \exp(\sigma X) = \exp((\tau + \sigma) X) = \exp(\sigma X) \exp(\tau X)$$

**2)** 다변수 경우 ($n \geq 2$): *다른* 생성자에서 나온 두 곡선은 일반적으로 *교환하지 않는다*.

$$\exp(\tau X_a) \exp(\sigma X_b) \neq \exp(\sigma X_b) \exp(\tau X_a) \quad (\text{일반적으로})$$

**3)** example) $SO(3)$ 에서 $x$ 축 회전 후 $y$ 축 회전 ≠ $y$ 축 회전 후 $x$ 축 회전. 책 한 권을 들고 두 가지 순서로 $90°$ 회전을 해 보면 결과가 다른 자세에 도달한다.

**4)** 이 비교환성을 *정량적으로* 잡아내는 양이 다음 장의 *리 괄호* $[X, Y] = XY - YX$ 다.

### 7. 정리

**1)** $n$ 차원 리 군은 $n$ 개의 매개변수로 단위원 근처를 라벨링한다.

**2)** 각 매개변수 방향 편미분 → $n$ 개의 생성자 $X_a$.

**3)** 각 생성자마다 §9의 일대일 대응에 의해 1매개변수 부분군 $\exp(\tau X_a)$ 가 정해진다.

**4)** $SO(3)$ 의 경우 생성자 $L_x, L_y, L_z$ 가 표준 예. 모두 반대칭 행렬이다.

**5)** *핵심 새 현상: 비교환성*. 다른 생성자에서 나온 부분군들은 일반적으로 곱셈 순서가 결과를 바꾼다. 이를 정량적으로 잡는 것이 다음 장의 *리 괄호* 다.
