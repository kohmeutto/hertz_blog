+++
title = "행렬 미분"
weight = 5
+++

### 1. 동기

리 군의 매끄러움을 살리려면, 매개변수로 라벨링된 행렬 $A(\tau)$를 미분할 수 있어야 한다. 이 장에서는 행렬 미분의 정의(성분별)와 기본 규칙, 그리고 회전 행렬 예제를 다룬다. 매개변수에서 *한 점*만 골랐을 때 얻는 미분값이 무엇을 가리키는지도 짚는다.

### 2. 성분별 정의

**1)** 행렬 $A(\tau)$의 각 성분 $a_{ij}(\tau)$가 $\tau$의 함수일 때, $A$의 미분은 *각 성분을 따로 미분*해서 만든 행렬이다.

$$\frac{dA}{d\tau} = \begin{pmatrix} \dfrac{da_{11}}{d\tau} & \dfrac{da_{12}}{d\tau} \\ \dfrac{da_{21}}{d\tau} & \dfrac{da_{22}}{d\tau} \end{pmatrix}$$

(여기선 $2 \times 2$로 적었지만 일반 $n \times m$에 그대로 일반화된다.)

**2)** 결과는 같은 크기의 행렬이다.

**3)** *행렬 미분은 새로운 개념이 아니라, 성분 하나하나에 보통의 스칼라 미분을 적용한 것에 불과하다.*

### 3. 기본 규칙

**1)** 선형성:

$$\frac{d}{d\tau}(\alpha A + \beta B) = \alpha \frac{dA}{d\tau} + \beta \frac{dB}{d\tau}$$

**2)** 곱셈 규칙 (*순서 조심*):

$$\frac{d}{d\tau}(AB) = \frac{dA}{d\tau}\, B + A\, \frac{dB}{d\tau}$$

행렬 곱셈은 교환적이지 않으므로 $\dfrac{dA}{d\tau} B$ 와 $B\, \dfrac{dA}{d\tau}$ 는 일반적으로 다르다. 곱셈 순서를 임의로 바꾸면 안 된다.

**3)** 역행렬 미분 (참고):

$AA^{-1} = I$ 양변을 미분하면 $\dfrac{dA}{d\tau} A^{-1} + A \dfrac{d(A^{-1})}{d\tau} = 0$이고, 양변에 $A^{-1}$ 을 왼쪽에서 곱하면

$$\frac{d(A^{-1})}{d\tau} = -A^{-1}\, \frac{dA}{d\tau}\, A^{-1}$$

스칼라의 $\dfrac{d}{d\tau}\dfrac{1}{a} = -\dfrac{1}{a^2}\dfrac{da}{d\tau}$ 와 유사하지만, 행렬 곱셈이 교환적이지 않아 *왼쪽과 오른쪽에 각각* $A^{-1}$ 이 붙는다.

### 4. 회전 행렬 예제

**1)** $SO(2)$의 회전 행렬

$$R(\tau) = \begin{pmatrix} \cos\tau & -\sin\tau \\ \sin\tau & \cos\tau \end{pmatrix}$$

**2)** 성분별 미분:
- $\dfrac{d}{d\tau}\cos\tau = -\sin\tau$
- $\dfrac{d}{d\tau}(-\sin\tau) = -\cos\tau$
- $\dfrac{d}{d\tau}\sin\tau = \cos\tau$
- $\dfrac{d}{d\tau}\cos\tau = -\sin\tau$

**3)** 따라서

$$\frac{dR}{d\tau} = \begin{pmatrix} -\sin\tau & -\cos\tau \\ \cos\tau & -\sin\tau \end{pmatrix}$$

**4)** 특히 $\tau = 0$에서

$$\left.\frac{dR}{d\tau}\right|_{\tau=0} = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} \equiv X$$

이 행렬 $X$ 는 *반대칭*($X^T = -X$)이다. 회전을 "살짝" 일으키는 방향을 가리키는 특정 행렬이라고 볼 수 있다.

**5)** *명명*: 이 X 를 회전 곡선 $R(\tau)$ 의 **생성자(generator)** 라 부른다. §6 에서 보겠지만 X 하나로부터 지수 사상을 통해 곡선 전체 $R(\tau) = \exp(\tau X)$ 가 *생성*되기 때문에 붙은 이름이다. 생성자의 정확한 정의와 일반적 의미는 §9 에서 본격 다룬다.

**6)** *참고*: $X^2 = -I$ 가 성립한다.
$$X^2 = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix}\begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} = \begin{pmatrix} -1 & 0 \\ 0 & -1 \end{pmatrix} = -I$$
이 관계는 뒤에서 $R(\tau)$ 를 $X$ 로부터 "지수 사상"으로 복원할 때 결정적 역할을 한다 (§6).

### 5. 미분 결과의 기하학적 의미

**1)** $A(\tau)$ 가 행렬 공간 안에 그리는 곡선을 떠올린다. $\tau$ 가 변할 때 점이 움직이는데, *어느 방향으로* 움직이는지를 알려주는 행렬이 $\dfrac{dA}{d\tau}$ 다.

**2)** 스칼라 함수의 미분이 "접선의 기울기"인 것과 똑같이, 행렬 함수의 미분도 "곡선의 접선 방향"을 나타내는 행렬이다.

**3)** 곡선 위의 *각 점마다 미분이 정의*되며, 그 점에서 곡선이 어디로 향하는지 알려준다.

<svg viewBox="0 0 300 295" xmlns="http://www.w3.org/2000/svg" style="display:block;margin:auto;max-width:300px">
  <defs>
    <marker id="arr5" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
      <path d="M 0,0 L 10,5 L 0,10 z" fill="#0066cc"/>
    </marker>
  </defs>
  <circle cx="150" cy="140" r="90" fill="none" stroke="black" stroke-width="2"/>
  <circle cx="214" cy="76" r="5" fill="black"/>
  <text x="220" y="73" font-size="12">A(τ)</text>
  <line x1="214" y1="76" x2="186" y2="48" stroke="#0066cc" stroke-width="2.5" marker-end="url(#arr5)"/>
  <text x="138" y="48" font-size="12" fill="#0066cc">dA/dτ</text>
  <text x="150" y="285" text-anchor="middle" font-size="12" font-style="italic">행렬 공간 안의 곡선과 접선 방향</text>
</svg>

**4)** 특히 *단위행렬에서의 미분* (즉 $\tau = 0$ 에서의 미분)은 곡선이 "단위행렬에서 어느 방향으로 출발하는지"를 알려준다. 회전 행렬 예에서 $X = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix}$ 이 바로 그 값이다.

### 6. 정리

**1)** 행렬 미분은 *각 성분을 따로 미분*해서 같은 크기의 행렬을 만드는 것.

**2)** 선형성은 그대로 성립하고, 곱셈 규칙은 *순서를 보존*하며 두 항으로 나타난다. 역행렬 미분에는 양옆에 $A^{-1}$ 이 붙는다.

**3)** 회전 행렬 $R(\tau)$ 를 미분하고 $\tau = 0$ 에서 평가하면 반대칭 행렬 $X = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix}$ 이 나온다. 이를 $R(\tau)$ 의 *생성자*라 부르며 $X^2 = -I$ 가 성립한다.

**4)** 기하학적으로 행렬 미분은 *곡선의 접선 방향*을 가리킨다. 각 점마다 그 점에서의 진행 방향을 알려주는 행렬이 된다.
