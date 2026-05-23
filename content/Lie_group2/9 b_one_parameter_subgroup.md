+++
title = "1매개변수 부분군과 준동형 사상"
weight = 9
+++

### 1. 동기

§4~§8까지 1매개변수로 라벨링된 곡선 $R(\tau), \exp(\tau X)$ 를 다뤘다. 이 곡선들은 단순한 매끄러운 경로가 아니라 *대수적 구조*를 가진다.

$$R(\tau_1) R(\tau_2) = R(\tau_1 + \tau_2), \qquad \exp((\tau_1 + \tau_2) X) = \exp(\tau_1 X) \exp(\tau_2 X)$$

이 식은 사상 $\tau \mapsto R(\tau)$ 가 *덧셈군 $(\mathbb{R}, +)$* 의 구조를 *리 군 $G$* 의 구조로 *보존*한다는 뜻이다. 이게 **군 준동형 사상(group homomorphism)** 의 정의 그 자체다.

이 장에서는 지금까지 본 1매개변수 곡선들을 *준동형 사상* 이라는 추상 위에서 다시 정리한다.

### 2. 군 준동형 사상

**1)** 두 군 $(G_1, \cdot_1)$ 과 $(G_2, \cdot_2)$ 사이의 사상 $\phi: G_1 \to G_2$ 가 *군 준동형 사상* 이려면 모든 $a, b \in G_1$ 에 대해 다음이 성립해야 한다.

$$\phi(a \cdot_1 b) = \phi(a) \cdot_2 \phi(b)$$

즉 $\phi$ 는 *연산을 보존*한다.

**2)** 이 조건 하나만으로 다음이 자동으로 따라온다.
- $\phi(e_1) = e_2$ — 항등원이 항등원으로
- $\phi(a^{-1}) = \phi(a)^{-1}$ — 역원이 역원으로

**3)** 따라서 준동형 사상은 군의 *대수적 구조 전체*(연산, 항등원, 역원)를 보존한다.

**4)** *리 군 준동형 사상*은 추가로 *매끄러운* 사상이어야 한다 (양쪽 군이 리 군일 때).

### 3. 1매개변수 부분군의 정의

**1)** *1매개변수 부분군 (1-parameter subgroup)* 은 덧셈군 $(\mathbb{R}, +)$ 에서 리 군 $G$ 로 가는 *매끄러운 군 준동형 사상* 이다.

$$\phi: \mathbb{R} \to G, \quad \phi(\tau_1 + \tau_2) = \phi(\tau_1) \cdot \phi(\tau_2)$$

**2)** 자동으로 따라오는 성질:
- $\phi(0) = e$ (단위원)
- $\phi(-\tau) = \phi(\tau)^{-1}$

**3)** 사상의 *상(image)* $\phi(\mathbb{R}) \subset G$ 가 $G$ 의 *부분군*이 된다. 이게 "1매개변수 *부분군*"이라는 이름의 유래.

### 4. $SO(2)$의 예

**1)** 회전 행렬 함수

$$\phi(\tau) = R(\tau) = \begin{pmatrix} \cos\tau & -\sin\tau \\ \sin\tau & \cos\tau \end{pmatrix}$$

**2)** 준동형 조건 확인:
- $R(\tau_1 + \tau_2) = R(\tau_1) R(\tau_2)$ — 코사인·사인 덧셈정리에서 곧장
- $R(0) = I$
- $R(-\tau) = R(\tau)^{-1}$

**3)** 따라서 $\phi: \mathbb{R} \to SO(2)$ 는 매끄러운 군 준동형 사상.

**4)** 시각화: $\mathbb{R}$ 직선 위의 각 점이 $SO(2)$ 원 위의 한 점에 대응. 직선의 *덧셈*이 원의 *행렬 곱셈*으로 보존된다.

<svg viewBox="0 0 500 280" xmlns="http://www.w3.org/2000/svg" style="display:block;margin:auto;max-width:500px">
  <defs>
    <marker id="arr9" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
      <path d="M 0,0 L 10,5 L 0,10 z" fill="#0066cc"/>
    </marker>
  </defs>
  <line x1="40" y1="70" x2="340" y2="70" stroke="black" stroke-width="2"/>
  <text x="355" y="75" font-size="14">ℝ (덧셈)</text>
  <circle cx="100" cy="70" r="3" fill="black"/>
  <text x="100" y="55" text-anchor="middle" font-size="11">0</text>
  <circle cx="160" cy="70" r="3" fill="black"/>
  <text x="160" y="55" text-anchor="middle" font-size="11">π/2</text>
  <circle cx="220" cy="70" r="3" fill="black"/>
  <text x="220" y="55" text-anchor="middle" font-size="11">π</text>
  <circle cx="280" cy="70" r="3" fill="black"/>
  <text x="280" y="55" text-anchor="middle" font-size="11">3π/2</text>
  <circle cx="180" cy="200" r="50" fill="none" stroke="black" stroke-width="2"/>
  <text x="245" y="205" font-size="14">SO(2) (곱셈)</text>
  <circle cx="230" cy="200" r="3" fill="black"/>
  <text x="240" y="205" font-size="11">I</text>
  <circle cx="180" cy="150" r="3" fill="black"/>
  <text x="180" y="142" text-anchor="middle" font-size="11">R(π/2)</text>
  <circle cx="130" cy="200" r="3" fill="black"/>
  <text x="100" y="205" font-size="11">R(π)</text>
  <circle cx="180" cy="250" r="3" fill="black"/>
  <text x="180" y="268" text-anchor="middle" font-size="11">R(3π/2)</text>
  <line x1="100" y1="80" x2="228" y2="197" stroke="#0066cc" stroke-width="1.2" marker-end="url(#arr9)" stroke-dasharray="3,2"/>
  <line x1="160" y1="80" x2="180" y2="150" stroke="#0066cc" stroke-width="1.2" marker-end="url(#arr9)" stroke-dasharray="3,2"/>
  <line x1="220" y1="80" x2="135" y2="198" stroke="#0066cc" stroke-width="1.2" marker-end="url(#arr9)" stroke-dasharray="3,2"/>
  <line x1="280" y1="80" x2="180" y2="247" stroke="#0066cc" stroke-width="1.2" marker-end="url(#arr9)" stroke-dasharray="3,2"/>
  <text x="380" y="155" font-size="14" fill="#0066cc">φ: τ ↦ R(τ)</text>
  <text x="380" y="175" font-size="11" fill="#0066cc">준동형 사상</text>
</svg>

### 5. $\exp(\tau X)$ 는 항상 1매개변수 부분군

**1)** 임의의 정사각 행렬 $X$ 에 대해 다음을 정의한다.

$$\phi_X(\tau) = \exp(\tau X)$$

**2)** 준동형 조건 확인:

$$\phi_X(\tau_1 + \tau_2) = \exp((\tau_1 + \tau_2) X) = \exp(\tau_1 X) \exp(\tau_2 X) = \phi_X(\tau_1) \phi_X(\tau_2)$$

(가운데 등호는 $X$ 와 자기 자신이 교환하므로 §6.5(3)이 성립한다.)

**3)** 자동 성질:
- $\phi_X(0) = \exp(0) = I$
- $\phi_X(-\tau) = \exp(-\tau X) = \exp(\tau X)^{-1} = \phi_X(\tau)^{-1}$

**4)** $\phi_X$ 는 $\tau$ 에 대해 매끄럽다 (테일러 급수가 $\tau$ 의 멱급수).

**5)** 따라서 *모든 행렬 $X$ 마다 $\phi_X(\tau) = \exp(\tau X)$ 가 1매개변수 부분군을 정의*한다.

### 6. 역방향: 모든 1매개변수 부분군은 $\exp$ 형태

**1)** 위의 역도 성립한다.

> 행렬 리 군 $G$ 의 매끄러운 1매개변수 부분군 $\phi: \mathbb{R} \to G$ 는 *반드시* 어떤 행렬 $X$ 에 대해 $\phi(\tau) = \exp(\tau X)$ 형태다.

**2)** 이 $X$ 는 $\phi$ 의 $\tau = 0$ 에서의 미분으로 결정된다.

$$X = \left.\frac{d\phi}{d\tau}\right|_{\tau=0}$$

**3)** proof) $\phi$ 가 준동형이라는 조건에서 미분방정식을 유도한다. 임의의 $\tau$ 에 대해

$$\frac{d\phi(\tau)}{d\tau} = \left.\frac{d}{d\sigma}\phi(\tau + \sigma)\right|_{\sigma=0} = \left.\frac{d}{d\sigma}\big[\phi(\tau)\phi(\sigma)\big]\right|_{\sigma=0} = \phi(\tau)\, X$$

여기서 $X = \dfrac{d\phi}{d\sigma}\big|_{\sigma=0}$.

이 미분방정식 $\dfrac{d\phi}{d\tau} = \phi(\tau)\, X$ 의 초기조건 $\phi(0) = I$ 인 해는 유일하게 $\phi(\tau) = \exp(\tau X)$ 다 (§6.5).

### 7. 생성자: 정의와 의미

**1)** *정의*: 1매개변수 부분군 $\phi: \mathbb{R} \to G$ 의 **생성자(generator)** 는 단위원에서의 그 미분이다.

$$X = \left.\frac{d\phi}{d\tau}\right|_{\tau=0}$$

§5–§6에서 등장한 행렬 X 가 정확히 이 생성자다. §5에서는 "단위행렬에서의 미분 결과" 라고 비공식적으로 부르고 §5.5 에서 명명만 했는데, 그 정확한 정의가 위 식이다.

**2)** *역방향*: 행렬 X 가 주어지면, 그것이 생성하는 1매개변수 부분군은

$$\phi_X(\tau) = \exp(\tau X)$$

이다 (§5와 §6의 결과).

**3)** 두 방향이 *서로의 역*이고, 따라서 다음의 *일대일 대응*이 성립한다.

$$\big\{ \text{생성자 } X \big\} \;\longleftrightarrow\; \big\{ \text{매끄러운 1매개변수 부분군 } \phi_X: \mathbb{R} \to G \big\}$$

**4)** *왜 "생성자"인가*: X 하나가 부분군 *전체*를 결정한다. 부분군의 모든 원소가 X 의 거듭제곱으로 (지수 사상의 테일러 급수를 통해) 만들어진다.

$$\phi_X(\tau) = \exp(\tau X) = I + \tau X + \frac{\tau^2}{2!} X^2 + \frac{\tau^3}{3!} X^3 + \cdots$$

X 가 *씨앗* 이고, 지수 사상이 *씨앗에서 곡선 전체를 자라게* 한다.

**5)** 생성자의 두 가지 동등한 정체:
- *기하학적*: 단위원에서의 곡선의 출발 방향 (속도 벡터)
- *대수적*: 부분군의 모든 원소를 거듭제곱과 지수로 만들어내는 씨앗

§6.7 의 미분-지수 역대응이 이 두 시각을 정확히 매개한다.

**6)** *생성자가 사는 공간*: 1매개변수 경우엔 X 와 그 스칼라 배 ($2X, -X, 0.5X, \ldots$) 만 가능하다. 즉 *생성자의 공간이 1차원*이다. 이는 부분군의 차원과 같다 (§3 의 매개변수-차원 원리).

**7)** *주의*: 모든 행렬이 임의의 리 군의 생성자가 되는 것은 아니다. 예를 들어 $SO(2)$ 의 생성자는 *반대칭* 행렬에 한정된다 (§5.4 의 X 가 반대칭인 것을 확인). 어떤 행렬이 주어진 리 군 $G$ 의 생성자가 되는지의 정확한 조건은 *접공간/리 대수* 논의 (마지막 장) 에서 명확해진다.

### 8. example: $SO(2)$ 정리

**1)** $X = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix}$ — 단위행렬에서의 방향.

**2)** 대응되는 1매개변수 부분군: $\phi_X(\tau) = \exp(\tau X) = R(\tau)$ — 회전 행렬의 원.

**3)** $X$ 의 스칼라 배 (예: $2X$, $-X$) 도 1매개변수 부분군을 정의한다.
- $\phi_{2X}(\tau) = \exp(2\tau X) = R(2\tau)$ — 두 배 속도로 도는 원
- $\phi_{-X}(\tau) = R(-\tau)$ — 반대 방향으로 도는 원

상은 모두 같은 원 $SO(2)$ 지만, *어떻게 거기를 매개변수화하느냐*가 다르다.

### 9. 정리

**1)** *군 준동형 사상*은 군의 연산 구조를 보존하는 사상. $\phi(ab) = \phi(a)\phi(b)$ 만 요구하면 항등원·역원 보존은 자동으로 따라온다.

**2)** *1매개변수 부분군*은 $(\mathbb{R}, +) \to G$ 의 매끄러운 군 준동형 사상.

**3)** 행렬 리 군에서 *모든* 1매개변수 부분군은 $\phi_X(\tau) = \exp(\tau X)$ 형태이며, $X$ 는 사상의 $\tau = 0$ 미분으로 결정된다.

**4)** 1매개변수 부분군 $\phi_X$ 의 *생성자*는 단위원에서의 미분 $X = \dfrac{d\phi}{d\tau}\big|_{\tau=0}$. 생성자와 부분군 사이에 일대일 대응이 있다.

**5)** 이 관점에서 §4~§8 의 1매개변수 이야기 *전체*가 한 줄로 요약된다.

> 각 *생성자* $X$ 마다 1매개변수 부분군 $\phi_X(\tau) = \exp(\tau X)$ 가 하나씩 정해진다.
