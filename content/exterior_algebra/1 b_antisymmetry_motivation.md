+++
title = "동기: 왜 반대칭이 중요한가"
weight = 1
+++

### 1. 시작: 평행사변형의 넓이

두 벡터 $\vec{v}, \vec{w}$ 가 만드는 평행사변형의 넓이를 어떻게 계산하나?

2차원에서 $\vec{v} = (a, b)$, $\vec{w} = (c, d)$ 일 때:

$$\text{넓이} = \det\begin{pmatrix} a & c \\ b & d \end{pmatrix} = ad - bc$$

예: $\vec{v} = (3, 1)$, $\vec{w} = (1, 2)$ 면 넓이 $= 3 \cdot 2 - 1 \cdot 1 = 5$.

이건 익숙한 *2D 행렬식*. 그런데 여기에 *깊은 의미가 숨어 있다*.

### 2. 흥미로운 점: 순서를 바꾸면 부호가 바뀐다

$\vec{v}$ 와 $\vec{w}$ 의 *순서를 바꿔서* 계산해 보자.

$$\det\begin{pmatrix} c & a \\ d & b \end{pmatrix} = cb - da = -(ad - bc)$$

위의 예에서: $\vec{w} = (1, 2)$, $\vec{v} = (3, 1)$ 순서로 두면 $1 \cdot 1 - 2 \cdot 3 = -5$.

부호가 *반대* 가 됐다. 그런데 *같은 평행사변형*을 그렸을 뿐인데?

<svg viewBox="0 0 500 280" xmlns="http://www.w3.org/2000/svg" style="display:block;margin:auto;max-width:500px">
  <defs>
    <marker id="vArr" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
      <path d="M 0,0 L 10,5 L 0,10 z" fill="#0066cc"/>
    </marker>
    <marker id="wArr" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
      <path d="M 0,0 L 10,5 L 0,10 z" fill="#cc0066"/>
    </marker>
    <marker id="rotArr" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
      <path d="M 0,0 L 10,5 L 0,10 z" fill="#009955"/>
    </marker>
  </defs>
  <g transform="translate(0,0)">
    <polygon points="50,200 170,200 230,80 110,80" fill="#cce5ff" fill-opacity="0.5" stroke="black" stroke-width="1.5"/>
    <line x1="50" y1="200" x2="170" y2="200" stroke="#0066cc" stroke-width="2.5" marker-end="url(#vArr)"/>
    <text x="105" y="222" font-size="14" fill="#0066cc" font-weight="bold">v</text>
    <line x1="50" y1="200" x2="110" y2="80" stroke="#cc0066" stroke-width="2.5" marker-end="url(#wArr)"/>
    <text x="65" y="138" font-size="14" fill="#cc0066" font-weight="bold">w</text>
    <text x="135" y="155" text-anchor="middle" font-size="16" font-weight="bold">+ A</text>
    <path d="M 130 175 A 28 28 0 0 1 100 145" stroke="#009955" stroke-width="2" fill="none" marker-end="url(#rotArr)"/>
    <text x="125" y="255" text-anchor="middle" font-size="12" font-style="italic">v 다음 w (반시계)</text>
  </g>
  <g transform="translate(250,0)">
    <polygon points="50,200 170,200 230,80 110,80" fill="#ffcccc" fill-opacity="0.5" stroke="black" stroke-width="1.5"/>
    <line x1="50" y1="200" x2="110" y2="80" stroke="#cc0066" stroke-width="2.5" marker-end="url(#wArr)"/>
    <text x="65" y="138" font-size="14" fill="#cc0066" font-weight="bold">w</text>
    <line x1="50" y1="200" x2="170" y2="200" stroke="#0066cc" stroke-width="2.5" marker-end="url(#vArr)"/>
    <text x="105" y="222" font-size="14" fill="#0066cc" font-weight="bold">v</text>
    <text x="135" y="155" text-anchor="middle" font-size="16" font-weight="bold">− A</text>
    <path d="M 100 145 A 28 28 0 0 0 130 175" stroke="#009955" stroke-width="2" fill="none" marker-end="url(#rotArr)"/>
    <text x="125" y="255" text-anchor="middle" font-size="12" font-style="italic">w 다음 v (시계)</text>
  </g>
</svg>

### 3. 왜 부호가 바뀔까: 방향이 붙은 넓이

행렬식이 단순한 "넓이" 가 아니라 *방향이 붙은 넓이 (oriented area)* 를 측정하기 때문이다.

**직관**: $\vec{v}$ 에서 $\vec{w}$ 로 *회전하는 방향*을 본다.

- *반시계 방향* (수학에서 양의 방향) → *양의* 넓이
- *시계 방향* → *음의* 넓이

평행사변형은 *모양만* 보면 두 순서가 같지만, *어느 방향으로 도는가* 까지 보면 다르다. 행렬식은 *이 방향 정보까지 포함한 넓이*.

**왜 방향을 신경 쓰는가?**

표면에는 *앞면과 뒷면*이 있다. 어느 면을 "위" 로 보는지에 따라 적분의 부호가 결정된다. 예를 들어 *플럭스 (전기장이 어떤 면을 통과하는 양)* 를 계산할 때 면의 *방향* 이 중요. 한 쪽으로 흐르는 전기장은 양의 플럭스, 반대 방향은 음의 플럭스.

이 *방향의 중요성*이 결국 모두 *반대칭성*에서 비롯된다.

### 4. 3차원으로 확장: 외적

3차원에서는 두 벡터의 *외적 (cross product)* $\vec{v} \times \vec{w}$ 가 평행사변형의 넓이를 *벡터로* 표현한다.

핵심 성질:

$$\vec{v} \times \vec{w} = -\vec{w} \times \vec{v}$$

*순서를 바꾸면 부호가 반대*. 2D 행렬식과 정확히 같은 성질.

- $|\vec{v} \times \vec{w}|$ = 평행사변형의 넓이 (양수)
- $\vec{v} \times \vec{w}$ 의 *방향* = 평행사변형의 *법선 방향* (면에 수직)

법선 방향이 두 개 있는데 (앞면, 뒷면) — 오른손 법칙으로 결정. *이게 방향의 기원*. 손을 뒤집으면 (= 순서를 바꾸면) 부호가 반대.

### 5. 4차원 이상에서는?

3D 에서는 외적이 *벡터로* 표현됐다. 그런데 4차원 이상에서는 *외적이 벡터로 표현되지 않는다*.

**왜?** 3D 에서 두 벡터로 만든 평행사변형의 법선은 *1차원* (다른 2차원에 수직인 방향이 단 하나). 그래서 벡터로 표현된다. 

하지만 4D 에서 두 벡터로 만든 평면에 수직인 방향은 *2차원* — 더 이상 단일 벡터로 표현 불가. 5D 에서는 3차원이 수직. 등등.

**해결책**: 벡터를 일반화한 *새로운 객체* 가 필요. 이게 **쐐기곱 (wedge product)** $\vec{v} \wedge \vec{w}$ 이다.

쐐기곱은 *모든 차원에서* 작동하며, 항상 같은 핵심 성질을 갖는다:

$$\vec{v} \wedge \vec{w} = -\vec{w} \wedge \vec{v}$$

### 6. 반대칭이 핵심인 이유

위 세 가지 (2D 행렬식, 3D 외적, 일반 쐐기곱) 의 공통점:

> *벡터의 순서를 바꾸면 부호가 반대*

이걸 **반대칭성 (antisymmetry)** 이라 부른다.

이게 우연이 아니라 *방향이 붙은 넓이·부피를 표현하는 모든 자연스러운 방법*의 공통 성질이다. 

뒤집어서: *반대칭성을 만족하는 자연스러운 함수*들은 모두 본질적으로 같은 종류의 객체다. 이게 **외대수 (exterior algebra)** 의 출발점.

(*다중선형* 은 "여러 벡터에 의존하며 각 벡터에 대해 선형" 이라는 뜻. 자세한 정의는 §2 에서 다룬다.)

### 7. 이 시리즈에서 다룰 내용 (예정)

(1) 다중선형성과 반대칭성의 정확한 정의 (§2)

(2) 쐐기곱 $v \wedge w$ 의 정의와 성질 (§3)

(3) 외대수의 기저와 차원 (§4)

(4) 행렬식의 진정한 의미 (§5)

(5) 미분형식 — 함수처럼 다루는 쐐기곱 (§6-§7)

(6) 외미분 $d$ — 모든 벡터 미적분을 통합 (§8-§9)

(7) 적분과 Stokes 정리 (§10-§11)

(8) de Rham 코호몰로지 (§12)

(9) Hodge 별표 (§13)

(10) 응용: Maxwell, 심플렉틱, Berry, Noether (§14)

### 8. 왜 외대수를 배우는가

- *Maxwell 방정식* 이 두 줄로 줄어든다: $dF = 0$, $d\star F = J$
- *Noether 정리* 의 보존 흐름이 자연스럽게 미분형식으로 표현됨
- *해밀턴 역학* 의 위상 공간 구조 (심플렉틱 형식)
- *위상 절연체·Berry 위상* — 응집계 물리의 위상 분석
- *Stokes 정리* — 다변수 미적분의 진짜 일반화

요약: *부피·넓이·방향이 관련된 모든 수학·물리는 결국 외대수의 언어로 통일된다*.

리 군 시리즈가 *연속 대칭의 언어* 였다면, 외대수 시리즈는 *부피·방향의 언어* 다. 둘이 만나서 물리의 통일 그림이 완성된다.
