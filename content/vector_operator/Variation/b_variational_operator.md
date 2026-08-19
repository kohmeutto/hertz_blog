+++
title = "(b) Variational Operator"
weight = 20
+++

---

### 0. 도입 및 동기 (Motivation)

**1) 출발점: 1차원 실함수의 전미분**

실수 집합 상의 함수 $f: \mathbb{R} \to \mathbb{R}$에 대하여, 점 $x$에서의 임의의 미소 증분 $dx$에 대한 1차 선형 근사(전미분)는 다음과 같이 정의된다.

$$
df(x; dx) \;=\; f'(x)\,dx \;=\; \left.\frac{d}{d\epsilon} f(x + \epsilon\,dx)\right\vert_{\epsilon=0}
$$

* 구조: $f'(x)$는 기준점 $x$에서의 도함수(1차 사상)이며, $dx$는 독립적으로 주어지는 방향 증분이다.
* 의미: 비선형 함수의 거동을 기준점 근방에서 1차 선형화($f(x+dx) \approx f(x) + df$)하는 기본 연산이다.

**2) 무한차원 함수 공간으로의 확장 및 보편화**

미분의 대상을 스칼라 변수에서 **무한차원 상태 벡터 $|u\rangle \in V$** 및 **상태 의존 대상 $X(u)$(연산자 $\hat{A}(u)$, 계수 $D(u)$ 등)**로 확장할 때, 방향도함수 $D[\,\cdot : \cdot\,]$의 대수적 구조는 다음과 같이 일관되게 확장된다.

$$
\begin{aligned}
\text{[1차원 실함수]} \quad & Df[x : dx] &&= f'(x)\,dx \\[6pt]
\text{[다차원 스칼라장]} \quad & Df[\mathbf{x} : \mathbf{h}] &&= \nabla f(\mathbf{x}) \cdot \mathbf{h} \\[6pt]
\text{[무한차원 범함수]} \quad & DJ[u : |\eta\rangle] &&= \langle \nabla J(u) \mid \eta \rangle \\[6pt]
\text{[상태 의존 대상]} \quad & DX[u : |\eta\rangle] &&\equiv \delta X
\end{aligned}
$$

* 구조적 통일성: 모든 차원에서 $D[\text{동작점} : \text{방향}]$은 동작점에서 1차 도함수(선형 사상)를 취하고, 뒤의 방향 인자를 선형으로 전달받는 동일한 구조를 갖는다.
* 변분 기호 $\delta$의 위치: $DX[u : |\eta\rangle]$에서 동작점 $u$와 임의의 변분 방향 $|\eta\rangle$를 매번 병기하는 대신, 축약된 대수 연산 기호로서 $\delta X$를 정의하여 사용한다.

**3) 변분 연산자 $\delta$ 체계의 필요성**

연속체 역학, 비선형 편미분방정식, 양자역학 등에서 변분 연산자 $\delta$를 사용하는 이유는 다음과 같다.

* **비선형계의 체계적 선형화:** 상태 종속 항이 결합된 연산자 방정식 $\hat{A}(u)|u\rangle = |b\rangle$에 대해 평형점 근방의 섭동 전개($|u\rangle \to |u\rangle + \epsilon|\eta\rangle$)를 일관된 대수 형식으로 수행한다.
* **미분 대수 법칙의 상속:** 엡실론 극한($\left.\frac{d}{d\epsilon}\right\vert_{\epsilon=0}$)을 매번 계산하지 않고, 선형성, 곱의 법칙(Leibniz rule), 연쇄 법칙을 켓과 연산자 대수식에 직접 적용한다.
* **선형 항과 비선형 항의 구조 분리:** 공간 미분 연산자($\partial_x, \nabla$)와 같은 상태 독립 선형 연산자와 상태 의존 계수($D(u), \hat{A}(u)$)가 혼재될 때, 교환 잔여항을 통해 미분의 적용 범위를 엄밀하게 구분한다.

---

### 1. 변분 연산자의 기본 성질

**1) 선형성**

상수 $c_1, c_2$와 상태 의존 대상 $X_1(u), X_2(u)$에 대하여 $\delta$는 선형 중첩을 만족한다.

$$
\delta\big\{c_1 X_1 + c_2 X_2\big\} \;=\; c_1\,\delta X_1 \;+\; c_2\,\delta X_2
$$

$$
\delta\big\{\hat{A}\vert{}u\rangle - \vert{}b\rangle\big\} \;=\; \delta\big\{\hat{A}\vert{}u\rangle\big\} \;-\; \delta\vert{}b\rangle
$$

* 성립 근거: 실수 일변수 미분의 선형성이 그대로 상속되기 때문이다.
* 적용 대상: $X$의 종류에 무관하게 성립한다.

{{< details summary="proof" >}}

정의 1에서 $X$ 자리에 $c_1X_1 + c_2X_2$를 대입한다.

$$
\delta\big\{c_1 X_1 + c_2 X_2\big\} \;=\; \left.\frac{d}{d\epsilon}\Big[c_1 X_1(u+\epsilon\eta) + c_2 X_2(u+\epsilon\eta)\Big]\right\vert_{\epsilon=0}
$$

실수 일변수 미분 $d/d\epsilon$의 선형성에 따라 각 항을 분리한다.

$$
= \; c_1\left.\frac{d}{d\epsilon} X_1(u+\epsilon\eta)\right\vert_{\epsilon=0} \;+\; c_2\left.\frac{d}{d\epsilon} X_2(u+\epsilon\eta)\right\vert_{\epsilon=0}
$$

각 항에 정의 1을 적용한다.

$$
= \; c_1\,\delta X_1 \;+\; c_2\,\delta X_2
$$

<hr>

{{< /details >}}

**2) 상수의 변분**

$X_0$가 상태 $u$에 의존하지 않으면 그 변분은 $0$이 된다.

$$
\delta X_0 \;=\; 0
$$

$$
\delta\hat{A}_{a} \;=\; 0 \qquad (\text{상태 자리에 값을 대입한 경우})
$$

* 성립 근거: 상수에 대한 미분값이 $0$이기 때문이다.
* 적용 대상: 아래첨자를 적용한 연산자와 고정된 켓에 적용된다.

{{< details summary="proof" >}}

정의 1에서 $X_0$는 $\epsilon$을 포함하지 않으므로 $X(u+\epsilon\eta) = X_0$가 성립한다.

$$
\delta X_0 \;=\; \left.\frac{d}{d\epsilon} X_0\right\vert_{\epsilon=0}
$$

상수를 미분하면 $0$이 된다.

$$
= \; 0
$$

{{< /details >}}

---

### 2. 곱의 법칙

**1) 연산자와 켓의 곱**

$\hat{G}(\epsilon) \in \mathcal{L}(V, V^{*})$와 $\vert{}g(\epsilon)\rangle \in V$가 $\epsilon$에 대하여 미분가능할 때, 곱의 미분은 인자의 순서를 유지한 채 두 항으로 분리된다.

$$
\frac{d}{d\epsilon}\Big[\hat{G}(\epsilon)\,\vert{}g(\epsilon)\rangle\Big] \;=\; \hat{G}'(\epsilon)\,\vert{}g(\epsilon)\rangle \;+\; \hat{G}(\epsilon)\,\vert{}g'(\epsilon)\rangle
$$

$$
\delta\big\{\hat{A}\,\vert{}u\rangle\big\} \;=\; \big(\delta\hat{A}\big)\,\vert{}u\rangle \;+\; \hat{A}\,\vert{}\delta u\rangle
$$

* 첫째 항: 연산자를 미분하고 켓은 그대로 둔다.
* 둘째 항: 켓을 미분하고 연산자는 그대로 둔다.
* 인자 순서: 연산자는 왼쪽에, 켓은 오른쪽에 배치된다.

{{< details summary="proof" >}}

차분몫을 정의하고 분자에 $\hat{G}(\epsilon)\vert{}g(\epsilon+h)\rangle$를 더한 뒤 동일한 항을 뺀다.

$$
\frac{\hat{G}(\epsilon+h)\vert{}g(\epsilon+h)\rangle - \hat{G}(\epsilon)\vert{}g(\epsilon)\rangle}{h}
$$

$$
= \frac{\hat{G}(\epsilon+h)\vert{}g(\epsilon+h)\rangle - \hat{G}(\epsilon)\vert{}g(\epsilon+h)\rangle}{h} \;+\; \frac{\hat{G}(\epsilon)\vert{}g(\epsilon+h)\rangle - \hat{G}(\epsilon)\vert{}g(\epsilon)\rangle}{h}
$$

첫째 항에서 공통인자 $\vert{}g(\epsilon+h)\rangle$를 묶는다.

$$
\frac{\hat{G}(\epsilon+h)\vert{}g(\epsilon+h)\rangle - \hat{G}(\epsilon)\vert{}g(\epsilon+h)\rangle}{h} \;=\; \left[\frac{\hat{G}(\epsilon+h) - \hat{G}(\epsilon)}{h}\right]\vert{}g(\epsilon+h)\rangle
$$

둘째 항에서 선형 연산자 $\hat{G}(\epsilon)$를 밖으로 뺀다.

$$
\frac{\hat{G}(\epsilon)\vert{}g(\epsilon+h)\rangle - \hat{G}(\epsilon)\vert{}g(\epsilon)\rangle}{h} \;=\; \hat{G}(\epsilon)\left[\frac{\vert{}g(\epsilon+h)\rangle - \vert{}g(\epsilon)\rangle}{h}\right]
$$

$h \to 0$의 극한을 적용한다. 첫째 항의 차분몫은 $\hat{G}'(\epsilon)$가 되고 $\vert{}g(\epsilon+h)\rangle$는 연속성에 의해 $\vert{}g(\epsilon)\rangle$가 된다. 둘째 항의 차분몫은 $\vert{}g'(\epsilon)\rangle$가 되고 $\hat{G}(\epsilon)$의 유계성에 의해 극한이 적용된다.

$$
\frac{d}{d\epsilon}\Big[\hat{G}(\epsilon)\,\vert{}g(\epsilon)\rangle\Big] \;=\; \hat{G}'(\epsilon)\,\vert{}g(\epsilon)\rangle \;+\; \hat{G}(\epsilon)\,\vert{}g'(\epsilon)\rangle
$$

$\hat{G}(\epsilon) = \hat{A}(u+\epsilon\eta)$, $\vert{}g(\epsilon)\rangle = \vert{}u\rangle + \epsilon\vert{}\eta\rangle$를 대입하고 $\epsilon = 0$을 적용한다.

$$
\delta\big\{\hat{A}\,\vert{}u\rangle\big\} \;=\; \big(\delta\hat{A}\big)\,\vert{}u\rangle \;+\; \hat{A}\,\vert{}\delta u\rangle
$$

<hr>

{{< /details >}}

**2) 브라와 켓의 곱**

상태에 의존하는 두 켓 $\vert{}p(u)\rangle$, $\vert{}q(u)\rangle$에 대하여 두 슬롯이 각각 미분된다.

$$
\delta\big\{\langle p \vert{} q\rangle\big\} \;=\; \langle \delta p \vert{} q\rangle \;+\; \langle p \vert{} \delta q\rangle
$$

$$
\delta\big\{\langle \psi \vert{} \psi\rangle\big\} \;=\; 2\,\mathrm{Re}\,\langle\psi\vert{}\delta\psi\rangle
$$

* 첫째 항: 브라 슬롯을 미분하고 켓 슬롯은 그대로 둔다.
* 둘째 항: 켓 슬롯을 미분하고 브라 슬롯은 그대로 둔다.
* $\epsilon$의 실수 제한: 브라 슬롯이 반선형이므로 스칼라 인자에 켤레가 적용되기 때문이다.

{{< details summary="proof" >}}

차분몫을 정의하고 분자에 $\langle p(\epsilon)\vert{}q(\epsilon+h)\rangle$를 더한 뒤 동일한 항을 뺀다.

$$
\frac{\langle p(\epsilon+h)\vert{}q(\epsilon+h)\rangle - \langle p(\epsilon)\vert{}q(\epsilon)\rangle}{h}
$$

$$
= \frac{\langle p(\epsilon+h)\vert{}q(\epsilon+h)\rangle - \langle p(\epsilon)\vert{}q(\epsilon+h)\rangle}{h} \;+\; \frac{\langle p(\epsilon)\vert{}q(\epsilon+h)\rangle - \langle p(\epsilon)\vert{}q(\epsilon)\rangle}{h}
$$

첫째 항에서 브라 슬롯의 덧셈성을 적용한다.

$$
\langle p(\epsilon+h)\vert{}q(\epsilon+h)\rangle - \langle p(\epsilon)\vert{}q(\epsilon+h)\rangle \;=\; \big\langle\, p(\epsilon+h) - p(\epsilon) \,\big\vert{}\, q(\epsilon+h)\,\big\rangle
$$

$1/h$를 브라 내부로 대입한다. $h$가 실수이므로 반선형 슬롯에 대입할 때 켤레의 영향을 받지 않는다.

$$
\frac{1}{h}\big\langle\, p(\epsilon+h) - p(\epsilon) \,\big\vert{}\, q(\epsilon+h)\,\big\rangle \;=\; \left\langle\, \frac{p(\epsilon+h) - p(\epsilon)}{h} \,\middle\vert{}\, q(\epsilon+h)\,\right\rangle
$$

둘째 항에서 선형 슬롯인 켓 내부로 $1/h$를 대입한다.

$$
\frac{\langle p(\epsilon)\vert{}q(\epsilon+h)\rangle - \langle p(\epsilon)\vert{}q(\epsilon)\rangle}{h} \;=\; \left\langle\, p(\epsilon) \,\middle\vert{}\, \frac{q(\epsilon+h) - q(\epsilon)}{h}\,\right\rangle
$$

$h \to 0$의 극한을 적용하고 $\epsilon = 0$을 대입한다.

$$
\delta\big\{\langle p \vert{} q\rangle\big\} \;=\; \langle \delta p \vert{} q\rangle \;+\; \langle p \vert{} \delta q\rangle
$$

{{< /details >}}

---

### 3. 연쇄 법칙

사상 $Z$와 $Y$의 합성에 대하여, 바깥 사상의 도함수를 $Z(u)$에서 계산하고 방향 인자로 안쪽 사상의 변분을 대입한다.

$$
\delta\big\{Y(Z(u))\big\} \;=\; DY\big[\,Z(u) : \vert{}\delta Z\rangle\,\big], \qquad \vert{}\delta Z\rangle \equiv \delta\big\{Z(u)\big\}
$$

$$
\delta\big\{D(u)\big\} \;=\; D'(u)\,\eta \qquad (\text{스칼라 함수 } D \text{를 상태에 합성한 경우})
$$

* 동작점: $u$가 아니라 $Z(u)$가 된다.
* 방향 인자: 안쪽 사상의 변분이 바깥 사상의 방향 인자가 된다.
* 필요 조건: $Y$에 대하여 정의 2의 미분가능성이 필요하다.

{{< details summary="proof" >}}

정의 1에서 $X(u) = Y(Z(u))$로 둔다.

$$
\delta\big\{Y(Z(u))\big\} \;=\; \left.\frac{d}{d\epsilon}\, Y\Big(Z(u+\epsilon\eta)\Big)\right\vert_{\epsilon=0}
$$

안쪽 사상의 값을 $\vert{}w(\epsilon)\rangle \equiv Z(u + \epsilon\eta)$로 정의한다.

$$
\delta\big\{Y(Z(u))\big\} \;=\; \left.\frac{d}{d\epsilon}\, Y\big(w(\epsilon)\big)\right\vert_{\epsilon=0}
$$

$Y$가 동작점 $\vert{}w(0)\rangle$에서 정의 2의 조건을 만족하므로 연쇄 법칙을 적용한다.

$$
= \; DY\Big[\,w(0) : \vert{}w'(0)\rangle\,\Big]
$$

동작점과 방향 인자를 각각 계산한다. 동작점은 $\epsilon = 0$에서의 값이 된다.

$$
\vert{}w(0)\rangle \;=\; Z(u + 0\cdot\eta) \;=\; Z(u)
$$

방향 인자는 정의 1에 $X = Z$를 대입한 형태가 된다.

$$
\vert{}w'(0)\rangle \;=\; \left.\frac{d}{d\epsilon} Z(u+\epsilon\eta)\right\vert_{\epsilon=0} \;=\; \delta\big\{Z(u)\big\} \;=\; \vert{}\delta Z\rangle
$$

두 결과를 대입한다.

$$
\delta\big\{Y(Z(u))\big\} \;=\; DY\big[\,Z(u) : \vert{}\delta Z\rangle\,\big]
$$

{{< /details >}}

---

### 4. 교환 관계

상태에 의존하는 선형 연산자 $\hat{L}(u)$에 대하여, $\delta$를 연산자 전체에 적용했을 때와 내부 켓에만 적용했을 때의 차이를 **교환 잔여항**으로 정의한다.

$$
\big[\delta,\, \hat{L}\big]\,\vert{}u\rangle \;\equiv\; \delta\big\{\hat{L}\,\vert{}u\rangle\big\} \;-\; \hat{L}\,\big(\delta\vert{}u\rangle\big)
$$

$$
\big[\hat{A},\hat{B}\big] \;=\; \hat{A}\hat{B} - \hat{B}\hat{A} \qquad (\text{양자역학의 교환자})
$$

대괄호 표기는 우변의 차이를 나타내는 축약 표현이다. $\delta\vert{}u\rangle = \vert{}\eta\rangle$이므로 $\delta$는 $V$ 위의 선형 연산자가 아니며, 합성 순서의 차이를 나타내는 연산자가 아니다. 따라서 대괄호를 단독 연산자로 쓰지 않고 $\vert{}u\rangle$에 작용하는 형태로만 쓴다.

**1) 교환 잔여항의 값**

$\delta$가 연산자를 통과할 때 발생하는 잔여항은 해당 연산자의 변분이다.

$$
\big[\delta,\, \hat{L}\big]\,\vert{}u\rangle \;=\; \big(\delta\hat{L}\big)\,\vert{}u\rangle
$$

$$
\big[\delta,\, \hat{A}(u)\big]\,\vert{}u\rangle \;=\; \big(\delta\hat{A}\big)\vert{}u\rangle \;\ne\; 0
$$

* 적용 도구: §3-1의 곱의 법칙을 적용한다.
* 잔여항의 구조: 연산자의 변분이 동작점 켓에 작용한 형태이다.
* 방향 켓의 위치: 방향 켓은 $\delta\hat{L}$ 내부에 포함된다.

{{< details summary="proof" >}}

§3-1의 곱의 법칙에 $\hat{A} = \hat{L}$을 대입한다.

$$
\delta\big\{\hat{L}\,\vert{}u\rangle\big\} \;=\; \big(\delta\hat{L}\big)\,\vert{}u\rangle \;+\; \hat{L}\,\vert{}\delta u\rangle
$$

$\vert{}\delta u\rangle = \delta\vert{}u\rangle$를 대입한다.

$$
\delta\big\{\hat{L}\,\vert{}u\rangle\big\} \;=\; \big(\delta\hat{L}\big)\,\vert{}u\rangle \;+\; \hat{L}\,\big(\delta\vert{}u\rangle\big)
$$

양변에서 $\hat{L}\big(\delta\vert{}u\rangle\big)$를 뺀다.

$$
\delta\big\{\hat{L}\,\vert{}u\rangle\big\} \;-\; \hat{L}\,\big(\delta\vert{}u\rangle\big) \;=\; \big(\delta\hat{L}\big)\,\vert{}u\rangle
$$

교환 잔여항의 정의를 적용한다.

$$
\big[\delta,\, \hat{L}\big]\,\vert{}u\rangle \;=\; \big(\delta\hat{L}\big)\,\vert{}u\rangle
$$

<hr>

{{< /details >}}


**2) 가환의 조건**

연산자가 선형이고 상태에 의존하지 않으면 잔여항이 $0$이 된다.

$$
\big[\delta,\, \hat{L}_0\big]\,\vert{}u\rangle \;=\; 0
$$

$$
\delta\big\{\hat{L}_0\,\vert{}u\rangle\big\} \;=\; \hat{L}_0\,\vert{}\delta u\rangle
$$

* 적용 도구: §5-1의 결과와 §2-2의 상수 변분 성질을 적용한다.
* 필요 조건: 연산자의 선형성과 상태 독립성이 동시에 성립해야 한다.
* 불필요한 가정: 혼합 편미분의 교환 정리는 증명에 쓰이지 않는다.

{{< details summary="proof" >}}

$\hat{L}_0$가 $u$에 의존하지 않으므로 §2-2에 의해 변분은 $0$이다.

$$
\delta\hat{L}_0 \;=\; 0
$$

이를 §5-1의 결과에 대입한다.

$$
\big[\delta,\, \hat{L}_0\big]\,\vert{}u\rangle \;=\; \big(\delta\hat{L}_0\big)\,\vert{}u\rangle \;=\; 0\cdot\vert{}u\rangle \;=\; 0
$$

교환 잔여항의 정의를 전개한다.

$$
\delta\big\{\hat{L}_0\,\vert{}u\rangle\big\} \;-\; \hat{L}_0\,\big(\delta\vert{}u\rangle\big) \;=\; 0
$$

$$
\delta\big\{\hat{L}_0\,\vert{}u\rangle\big\} \;=\; \hat{L}_0\,\vert{}\delta u\rangle
$$

{{< /details >}}

---

### 5. 적용

**1) 공간 미분 연산자**

$\partial_x$는 선형이고 상태에 의존하지 않으므로 §5-2가 적용된다.

$$
\delta\big\{\partial_x u\big\} \;=\; \partial_x\big(\delta u\big)
$$

* 잔여항: $0$이다.
* 성립 근거: 연산자가 선형이고 상태에 의존하지 않기 때문이다.

**2) 고정된 브라와의 내적**

$\vert{}v\rangle$가 $u$에 의존하지 않으면 내적은 선형이고 상태에 의존하지 않는다.

$$
\delta\big\{\langle v \vert{} u\rangle\big\} \;=\; \langle v \vert{} \delta u\rangle
$$

* 잔여항: $0$이다.
* 성립 근거: 켓 슬롯에 대하여 선형이고 $\epsilon$을 포함하지 않기 때문이다.

**3) 상태에 의존하는 연산자**

$\hat{A}(u)$는 선형이지만 상태에 의존하므로 잔여항이 발생한다.

$$
\delta\big\{\hat{A}(u)\,\vert{}u\rangle\big\} \;=\; \hat{A}(u)\,\vert{}\delta u\rangle \;+\; \big(\delta\hat{A}\big)\vert{}u\rangle
$$

* 잔여항: $\big(\delta\hat{A}\big)\vert{}u\rangle$가 된다.
* 성립 근거: 연산자가 선형이지만 상태에 의존하기 때문이다.

**4) 브라와 켓이 모두 상태에 의존하는 경우**

두 슬롯이 모두 상태에 의존하므로 §3-2의 곱의 법칙을 적용한다.

$$
\delta\big\{\langle p \vert{} q\rangle\big\} \;=\; \langle \delta p \vert{} q\rangle \;+\; \langle p \vert{} \delta q\rangle
$$

* 잔여항: 발생하지 않는다.
* 성립 근거: 두 슬롯 각각에 §3-2를 적용하기 때문이다.

example)

상태 의존 계수를 갖는 2계 연산자 $\hat{A}(u) = -\partial_x\big(D(u)\,\partial_x\,\cdot\,\big)$를 다룬다. 이 연산자는 $\partial_x$와 $D(u)$의 합성이므로 §6-1과 §6-3을 순서대로 적용한다. $\partial_x$는 통과하고 $D(u)$에서 잔여항이 발생한다.

$$
\delta\hat{A} \;=\; -\partial_x\Big(\big(\delta D\big)\,\partial_x\,\cdot\,\Big), \qquad \delta D \;=\; D'(u)\,\eta
$$

---

### 7. 요약표

**1) 연산별 $\delta$의 적용 결과**

| 만나는 연산 | 조건 | 결과 |
| :--- | :--- | :--- |
| 합 $c_1X_1 + c_2X_2$ | 없음 | $c_1\delta X_1 + c_2\delta X_2$ |
| 상수 $X_0$ | $u$에 무관 | $0$ |
| 연산자와 켓의 곱 $\hat{A}\vert{}u\rangle$ | 없음 | $\big(\delta\hat{A}\big)\vert{}u\rangle + \hat{A}\vert{}\delta u\rangle$ |
| 브라와 켓의 곱 $\langle p\vert{}q\rangle$ | $\epsilon \in \mathbb{R}$ | $\langle \delta p\vert{}q\rangle + \langle p\vert{}\delta q\rangle$ |
| 연산자 사이의 곱 $\hat{A}\hat{B}$ | 합성이 정의됨 | $\big(\delta\hat{A}\big)\hat{B} + \hat{A}\big(\delta\hat{B}\big)$ |
| 합성 $Y(Z(u))$ | $Y$에 정의 2 성립 | $DY\big[\,Z(u) : \vert{}\delta Z\rangle\,\big]$ |

**2) 교환 잔여항**

| 대상 | 선형 여부 | 상태 의존 여부 | $\big[\delta,\,\hat{L}\big]\vert{}u\rangle$ |
| :--- | :--- | :--- | :--- |
| $\partial_x$, $\nabla$ | 선형 | 무관 | $0$ |
| 고정된 브라 $\langle v\vert{}$ | 선형 | 무관 | $0$ |
| 아래첨자를 적용한 $\hat{A}_{a}$ | 선형 | 무관 | $0$ |
| 상태 의존 연산자 $\hat{A}(u)$ | 선형 | 의존 | $\big(\delta\hat{A}\big)\vert{}u\rangle$ |
| 비선형 사상 $N$ | 비선형 | — | 정의되지 않는다 |