+++
title = "비교환성과 리 괄호"
weight = 14
+++

### 1. 동기

§10.6 에서 다변수 리 군의 두 1매개변수 부분군의 곱이 *순서에 의존* — $\exp(\tau X_a)\exp(\sigma X_b) \neq \exp(\sigma X_b)\exp(\tau X_a)$ — 함을 봤다. §11.4 에서 *미분 작용 순서* 와 *군 곱셈 순서* 가 다름을 강조했고, §12.6·§13.6 에서 두 교란 작용소의 *교환자* 가 일반적으로 0이 아님도 보았다.

이 장에서는 *비교환성 자체를 정량화하는 도구* — **리 괄호 (Lie bracket)** — 를 정의하고 그 의미·성질·물리적 의의를 다룬다.

### 2. 리 괄호의 정의

**1)** 두 행렬 $X, Y$ 에 대해 **리 괄호** (또는 *교환자, commutator*) 는

$$[X, Y] = XY - YX$$

**2)** *기하학적 의미*: $X$ 와 $Y$ 가 *얼마나 교환되지 않는지*를 측정. $[X, Y] = 0$ 이면 두 행렬은 교환한다.

**3)** *대수적 의미*: 두 작용을 *다른 순서로* 적용했을 때의 차이 — $XY$ 와 $YX$ 의 차이가 곧 $[X, Y]$.

### 3. 군 곱셈의 비교환성과 리 괄호

**1)** 두 생성자 $X, Y$ 에 대해 작은 $\tau, \sigma$ 까지 테일러 전개:

$$\exp(\tau X) \exp(\sigma Y) = \left(I + \tau X + \frac{\tau^2}{2}X^2 + \cdots\right)\left(I + \sigma Y + \frac{\sigma^2}{2}Y^2 + \cdots\right)$$

$$= I + \tau X + \sigma Y + \tau\sigma\, XY + \frac{\tau^2}{2}X^2 + \frac{\sigma^2}{2}Y^2 + O(3)$$

**2)** 순서를 바꾸면:

$$\exp(\sigma Y) \exp(\tau X) = I + \sigma Y + \tau X + \tau\sigma\, YX + \frac{\tau^2}{2}X^2 + \frac{\sigma^2}{2}Y^2 + O(3)$$

**3)** 두 식의 차이:

$$\exp(\tau X) \exp(\sigma Y) - \exp(\sigma Y) \exp(\tau X) = \tau\sigma\, (XY - YX) + O(3) = \tau\sigma\, [X, Y] + O(3)$$

**4)** 따라서 *리 괄호는 군 곱셈의 비교환성을 측정하는 선행 항*. 두 1매개변수 부분군이 작은 매개변수에서 얼마나 다르게 결합하는지가 $[X, Y]$ 로 정량화된다.

<svg viewBox="0 0 400 280" xmlns="http://www.w3.org/2000/svg" style="display:block;margin:auto;max-width:400px">
  <defs>
    <marker id="arrXbk" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
      <path d="M 0,0 L 10,5 L 0,10 z" fill="#0066cc"/>
    </marker>
    <marker id="arrYbk" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
      <path d="M 0,0 L 10,5 L 0,10 z" fill="#cc0066"/>
    </marker>
    <marker id="arrGap" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
      <path d="M 0,0 L 10,5 L 0,10 z" fill="#009955"/>
    </marker>
  </defs>
  <circle cx="80" cy="220" r="5" fill="black"/>
  <text x="65" y="240" font-size="13">I</text>
  <line x1="80" y1="220" x2="220" y2="220" stroke="#0066cc" stroke-width="2.5" marker-end="url(#arrXbk)"/>
  <text x="125" y="240" font-size="11" fill="#0066cc">exp(τX)</text>
  <line x1="220" y1="220" x2="220" y2="80" stroke="#cc0066" stroke-width="2.5" marker-end="url(#arrYbk)"/>
  <text x="228" y="155" font-size="11" fill="#cc0066">exp(σY)</text>
  <circle cx="220" cy="80" r="5" fill="#aa00aa"/>
  <text x="232" y="78" font-size="11" fill="#aa00aa">exp(σY)exp(τX)</text>
  <line x1="80" y1="220" x2="80" y2="100" stroke="#cc0066" stroke-width="2" stroke-dasharray="4,3" marker-end="url(#arrYbk)"/>
  <text x="42" y="165" font-size="11" fill="#cc0066">exp(σY)</text>
  <line x1="80" y1="100" x2="195" y2="100" stroke="#0066cc" stroke-width="2" stroke-dasharray="4,3" marker-end="url(#arrXbk)"/>
  <text x="105" y="92" font-size="11" fill="#0066cc">exp(τX)</text>
  <circle cx="195" cy="100" r="5" fill="#0066aa"/>
  <text x="100" y="125" font-size="11" fill="#0066aa">exp(τX)exp(σY)</text>
  <line x1="195" y1="100" x2="218" y2="83" stroke="#009955" stroke-width="3" marker-end="url(#arrGap)"/>
  <text x="280" y="60" font-size="12" fill="#009955">≈ τσ [X, Y]</text>
  <line x1="280" y1="63" x2="215" y2="90" stroke="#009955" stroke-width="0.8" stroke-dasharray="2,2"/>
  <text x="200" y="265" text-anchor="middle" font-size="12" font-style="italic">두 경로의 종점 차이 = 리 괄호</text>
</svg>

### 4. 리 괄호의 성질

**1)** *반대칭성*:

$$[X, Y] = -[Y, X]$$

(정의에서 직접.) 특히 $[X, X] = 0$.

**2)** *선형성* (각 인자에 대해):

$$[\alpha X + \beta Y, Z] = \alpha [X, Z] + \beta [Y, Z], \qquad [X, \alpha Y + \beta Z] = \alpha [X, Y] + \beta [X, Z]$$

**3)** *야코비 항등식*:

$$[X, [Y, Z]] + [Y, [Z, X]] + [Z, [X, Y]] = 0$$

proof) 각 항을 전개:

(1) $[X, [Y, Z]] = X(YZ - ZY) - (YZ - ZY)X = XYZ - XZY - YZX + ZYX$

(2) $[Y, [Z, X]] = Y(ZX - XZ) - (ZX - XZ)Y = YZX - YXZ - ZXY + XZY$

(3) $[Z, [X, Y]] = Z(XY - YX) - (XY - YX)Z = ZXY - ZYX - XYZ + YXZ$

세 식을 더하면 *모든 항이 쌍으로 상쇄* — 합이 0.

**4)** 야코비 항등식이 *결합법칙의 대체물*. 일반적으로 $[X, [Y, Z]] \neq [[X, Y], Z]$ (리 괄호는 *결합법칙 만족 안 함*), 하지만 야코비 항등식을 만족한다.

**5)** *주의*: 리 괄호가 결합법칙을 만족하지 않으므로 리 대수는 *환 (ring)* 이 아니다 — §2 에서 본 환의 정의 ($\cdot$ 의 결합법칙) 가 불성립.

### 5. 폐쇄성: 생성자의 리 괄호는 다시 생성자

**1)** *핵심 주장*: $X, Y$ 가 리 군 $G$ 의 생성자라면, $[X, Y]$ 도 *같은 리 군 $G$* 의 생성자다.

**2)** *왜 그런가*: 다음 곡선이 매끄러운 1매개변수 부분군의 미분이 된다.

$$\phi(t) = \exp(\sqrt{t}\, X) \exp(\sqrt{t}\, Y) \exp(-\sqrt{t}\, X) \exp(-\sqrt{t}\, Y)$$

테일러 전개 ($s = \sqrt{t}$ 로 놓고 4차까지 전개) 하면

$$\phi(t) = I + t [X, Y] + O(t^{3/2})$$

따라서 $\left.\dfrac{d\phi}{dt}\right|_{t=0} = [X, Y]$ — 즉 $[X, Y]$ 가 $\phi$ 의 생성자.

**3)** 이 *폐쇄성* 이 생성자 집합에 *대수적 구조* 를 부여한다.

> 벡터 공간 (§11.6) + 닫힌 리 괄호 = **리 대수 (Lie algebra)**

**4)** 1매개변수 경우는 폐쇄성이 자명. $X$ 와 그 스칼라 배만 있으니 $[X, \alpha X] = 0$ 으로 자동 닫힌다. *다변수에서 비로소 폐쇄성이 비자명한 정보* 가 된다.

### 6. 구조 상수

**1)** 리 군 $G$ 의 생성자들을 기저 $\{X_1, \ldots, X_n\}$ 으로 잡으면, 임의의 리 괄호 $[X_a, X_b]$ 도 같은 리 대수에 속하므로 이 기저로 전개할 수 있다.

$$[X_a, X_b] = \sum_c f^c_{ab}\, X_c$$

**2)** 계수 $f^c_{ab}$ 를 *구조 상수 (structure constants)* 라 부른다. 리 대수의 *완전한 정보* 를 담고 있다.

**3)** 반대칭성에서 $f^c_{ab} = -f^c_{ba}$. 야코비 항등식은 구조 상수에 대한 이차 조건이 된다.

**4)** *구조 상수가 같은 두 리 대수는 (국소적으로) 동등*. 즉 리 군의 무한소 구조 전체가 $f^c_{ab}$ 에 담긴다.

### 7. example: $SO(3)$ 의 리 괄호

**1)** §10.5 의 생성자:

$$L_x = \begin{pmatrix} 0 & 0 & 0 \\ 0 & 0 & -1 \\ 0 & 1 & 0 \end{pmatrix}, \; L_y = \begin{pmatrix} 0 & 0 & 1 \\ 0 & 0 & 0 \\ -1 & 0 & 0 \end{pmatrix}, \; L_z = \begin{pmatrix} 0 & -1 & 0 \\ 1 & 0 & 0 \\ 0 & 0 & 0 \end{pmatrix}$$

**2)** 직접 계산:

$$L_x L_y = \begin{pmatrix} 0 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 1 & 0 \end{pmatrix}\begin{pmatrix} 0 & 0 & 1 \\ 0 & 0 & 0 \\ -1 & 0 & 0 \end{pmatrix} \cdots$$

(성분별 계산으로) $L_x L_y - L_y L_x$ 를 구하면

$$[L_x, L_y] = \begin{pmatrix} 0 & -1 & 0 \\ 1 & 0 & 0 \\ 0 & 0 & 0 \end{pmatrix} = L_z$$

**3)** 마찬가지로 (순환 대칭으로) 다음이 성립한다.

$$[L_x, L_y] = L_z, \qquad [L_y, L_z] = L_x, \qquad [L_z, L_x] = L_y$$

**4)** 구조 상수: $f^c_{ab} = \varepsilon_{abc}$ (레비-치비타 기호, $\varepsilon_{xyz} = 1$ 등).

$$[L_a, L_b] = \sum_c \varepsilon_{abc}\, L_c$$

이게 $SO(3)$ 리 대수의 *완전한 표현*. 양자역학 각운동량의 교환관계 $[J_a, J_b] = i\hbar\, \varepsilon_{abc}\, J_c$ 가 정확히 같은 구조 — $i\hbar$ 배만 다르다 (자기수반성과 단위를 위한 관습).

### 8. BCH 공식 (간단히)

**1)** §3 에서 본 1차 비교환성은 더 일반적인 *베이커-캠벨-하우스도르프 (BCH) 공식*의 첫 항:

$$\exp(X) \exp(Y) = \exp\left(X + Y + \frac{1}{2}[X, Y] + \frac{1}{12}\big[X, [X, Y]\big] - \frac{1}{12}\big[Y, [X, Y]\big] + \cdots\right)$$

**2)** *모든 항이 $X, Y$ 와 그들의 리 괄호의 중첩으로만 표현된다* — 즉 리 대수 안에 *닫혀* 있다.

**3)** *교환하는 경우* ($[X, Y] = 0$): BCH 가 $\exp(X) \exp(Y) = \exp(X + Y)$ 로 축약 — §6 의 1매개변수 결과와 일치.

**4)** *해석*: 두 1매개변수 부분군의 곱이 *하나의 지수* 로 표현될 때, 지수 안의 인자가 리 괄호만 사용해 만들어진다. 리 대수의 *생성력 (generative power)* 을 보여주는 깊은 결과.

### 9. 정리

**1)** *리 괄호*: $[X, Y] = XY - YX$ — 두 작용소의 비교환성을 측정.

**2)** *군 곱셈 비교환성과의 관계*:

$$\exp(\tau X)\exp(\sigma Y) - \exp(\sigma Y)\exp(\tau X) = \tau\sigma\, [X, Y] + O(3)$$

리 괄호 = 비교환성의 선행 항.

**3)** *성질*: 반대칭성, 선형성, 야코비 항등식. *결합법칙 만족 안 함* — 따라서 리 대수는 환이 아니다.

**4)** *폐쇄성*: 생성자의 리 괄호는 다시 생성자. 이게 생성자 집합에 *리 대수* 라는 대수 구조를 부여.

**5)** *구조 상수* $f^c_{ab}$ 가 리 대수를 완전히 결정. $SO(3)$ 의 경우 $\varepsilon_{abc}$ — 각운동량 교환관계의 기원.

**6)** *BCH 공식*: 두 지수의 곱이 리 괄호들로 만든 단일 지수로 표현된다 — 리 대수의 생성력.

**7)** 마지막 장에서 리 대수의 정확한 *추상적 정의* 와 *접공간* 으로서의 의미를 다룬다.
