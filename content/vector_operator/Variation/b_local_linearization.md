+++
title = "(b) Local linearization"
weight = 40
+++

---

### 1. 개요 및 목적

본 문서는 비선형 사상 $F : V \to V^{*}$를 동작점에서 하나의 선형 연산자로 근사하는 전개를 다룬다. 그 선형 연산자를 **자코비안**로 정의하고 $\hat{J}_{a}$로 쓴다.

$$
\hat{J}_{a}\,\vert{}\eta\rangle \;\equiv\; DF\big[\,a : \vert{}\eta\rangle\,\big] \;\in\; V^{*}
$$

$\hat{J}_{a}$는 $\mathcal{L}(V,V^{*})$의 원소이므로 규약에 따라 헷을 씌운다. 아래첨자 $a$는 규약 §3-5에 따라 상태 자리에 값을 대입한 것이다.

---

### 2. 비선형 사상의 구조 분류

**1) 일반 비선형 사상**

어떤 상태 $u_1, u_2$와 스칼라 $c_1, c_2$에 대하여 가산성과 제차성이 성립하지 않는 사상이다.

$$
F\big(c_1 u_1 + c_2 u_2\big) \;\ne\; c_1 F(u_1) \;+\; c_2 F(u_2)
\qquad \text{예: 소성 영역의 응력-변형 관계 (이력에 따라 응답이 달라진다)}
$$

* 가정한 구조: 내부 구조를 가정하지 않는다.
* 선형인 부분: 선형인 부분이 존재하지 않는다.
* 표기: 헷을 쓰지 않고 $F(u)$로 적으며 병치 표기 $F\vert{}u\rangle$는 쓰지 않는다.

**2) 반선형 사상**

상태에 무관한 유계 선형 연산자와 미분가능한 비선형 사상의 합으로 정의되는 사상이다.

$$
F(u) \;=\; \hat{L}_0\,\vert{}u\rangle \;+\; N(u)
\qquad \text{예: 반응-확산계. } \;\; F(c) \;=\; -\hat{\Delta}\,\vert{}c\rangle \;+\; R(c)
$$

* 가정한 구조: 선형 사상과 비선형 사상의 합으로 분해된다고 가정한다.
* 선형인 부분: $\hat{L}_0$가 선형 사상이며 상태에 의존하지 않는다.
* 표기: $\hat{L}_0$에는 헷을 씌우고 $N$에는 헷을 씌우지 않는다.

**3) 준선형 사상**

상태에 의존하는 연산자와 상태 자신의 작용 형태로 정의되는 사상이다.

$$
F(u) \;=\; \hat{A}(u)\,\vert{}u\rangle
\qquad \text{예: 유체의 이류항. } \;\; F(\mathbf{u}) \;=\; \big(\mathbf{u}\cdot\nabla\big)\mathbf{u}, \quad \hat{A}(\mathbf{u}) \;=\; \mathbf{u}\cdot\nabla
$$

* 가정한 구조: 상태 의존 연산자와 상태 켓의 곱으로 분해된다고 가정한다.
* 선형인 부분: 상태를 고정했을 때 $\hat{A}(u)$는 선형 사상이 된다.
* 표기: 소괄호 내부의 $u$는 상태 의존성을 뜻하고 병치된 $\vert{}u\rangle$는 작용을 뜻한다.

---

### 3. 구조별 자코비안

**1) 반선형 구조**

$$
F(u) \;=\; \hat{L}_0\,\vert{}u\rangle \;+\; N(u)
$$

$$
\hat{J}_{a}\,\vert{}\eta\rangle \;=\; \hat{L}_0\,\vert{}\eta\rangle \;+\; DN\big[\,a : \vert{}\eta\rangle\,\big]
$$

* 동작점 의존: 둘째 항만 동작점에 의존하며 첫째 항은 동작점에 의존하지 않는다.
* 적용 도구: 변분 연산자의 선형성과 상태 독립 연산자의 가환 조건을 적용한다.
* 방향 켓의 배치: 두 항 모두 방향 켓이 한 번씩 들어간다.

{{< details summary="proof" >}}

변분 연산자의 선형성을 적용하여 두 항을 나눈다.

$$
\delta F \;=\; \delta\big\{\hat{L}_0\vert{}u\rangle\big\} \;+\; \delta\big\{N(u)\big\}
$$

첫째 항에서 $\hat{L}_0$는 선형이고 상태에 의존하지 않으므로 가환 조건이 성립한다.

$$
\delta\big\{\hat{L}_0\vert{}u\rangle\big\} \;=\; \hat{L}_0\,\vert{}\delta u\rangle \;=\; \hat{L}_0\,\vert{}\eta\rangle
$$

둘째 항은 정의 2의 도함수 표기로 쓴다.

$$
\delta\big\{N(u)\big\} \;=\; DN\big[\,a : \vert{}\eta\rangle\,\big]
$$

두 항을 더한다.

$$
\hat{J}_{a}\,\vert{}\eta\rangle \;=\; \hat{L}_0\,\vert{}\eta\rangle \;+\; DN\big[\,a : \vert{}\eta\rangle\,\big] \qquad \blacksquare
$$

<hr>

{{< /details >}}

**2) 준선형 구조**

$$
F(u) \;=\; \hat{A}(u)\,\vert{}u\rangle
$$

$$
\hat{J}_{a}\,\vert{}\eta\rangle \;=\; \Big(D\hat{A}\big[\,a : \vert{}\eta\rangle\,\big]\Big)\vert{}a\rangle \;+\; \hat{A}_{a}\,\vert{}\eta\rangle
$$

* 동작점 의존: 두 항 모두 동작점에 의존한다.
* 적용 도구: 연산자와 켓 사이의 곱의 법칙을 적용한다.
* 방향 켓의 배치: 1항에서는 도함수의 방향 슬롯에 들어가고 2항에서는 연산자의 병치 자리에 들어간다.

{{< details summary="proof" >}}

곱의 법칙을 $\hat{A}(u)$와 $\vert{}u\rangle$의 곱에 적용한다.

$$
\delta F \;=\; \big(\delta\hat{A}\big)\,\vert{}u\rangle \;+\; \hat{A}(u)\,\vert{}\delta u\rangle
$$

네 인자를 동작점 $a$에서 각각 계산한다. 연산자의 변분을 도함수로 쓴다.

$$
\delta\hat{A} \;=\; D\hat{A}\big[\,a : \vert{}\eta\rangle\,\big]
$$

1항의 나머지 인자는 동작점의 상태 켓이다.

$$
\vert{}u\rangle \;=\; \vert{}a\rangle
$$

2항의 계수 연산자는 상태 자리에 값 $a$가 대입된 형태이다.

$$
\hat{A}(u) \;=\; \hat{A}(a) \;=\; \hat{A}_{a}
$$

2항의 나머지 인자는 방향 켓이다.

$$
\vert{}\delta u\rangle \;=\; \vert{}\eta\rangle
$$

네 식을 대입한다.

$$
\hat{J}_{a}\,\vert{}\eta\rangle \;=\; \Big(D\hat{A}\big[\,a : \vert{}\eta\rangle\,\big]\Big)\vert{}a\rangle \;+\; \hat{A}_{a}\,\vert{}\eta\rangle \qquad \blacksquare
$$

{{< /details >}}

---

### 5. 요약표

**1) 구조와 자코비안**

| 구조 | 형태 | 자코비안 $\hat{J}_{a}$ | 동작점 의존 |
| :--- | :--- | :--- | :--- |
| 일반 비선형 | 가정 없음 | 정의 2로 계산 | 전체 |
| 반선형 | $\hat{L}_0\vert{}u\rangle + N(u)$ | $\hat{L}_0 + DN\big[\,a:\,\cdot\,\big]$ | 둘째 항만 |
| 준선형 | $\hat{A}(u)\vert{}u\rangle$ | $\Big(D\hat{A}\big[\,a:\,\cdot\,\big]\Big)\vert{}a\rangle + \hat{A}_{a}$ | 두 항 모두 |
| 선형 | $\hat{L}_0\vert{}u\rangle$ | $\hat{L}_0$ | 없음 |

**2) 준선형 전개에서 두 켓이 들어가는 자리**

| 항 | 방향 켓 $\vert{}\eta\rangle$ | 동작점 켓 $\vert{}a\rangle$ |
| :--- | :--- | :--- |
| $\Big(D\hat{A}\big[\,a : \vert{}\eta\rangle\,\big]\Big)\vert{}a\rangle$ | 대괄호 내부의 방향 슬롯 | 병치 자리 |
| $\hat{A}_{a}\,\vert{}\eta\rangle$ | 병치 자리 | 연산자의 아래첨자 |