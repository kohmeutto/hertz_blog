+++
title = "외미분 d"
weight = 8
+++

### 1. 동기: 미분의 통합된 언어

미적분에서 우리는 *여러 가지 미분 연산자* 를 배웠다.

- *그라디언트* $\nabla f$: 스칼라 함수 → 벡터장
- *발산* $\nabla \cdot \vec{F}$: 벡터장 → 스칼라 함수
- *회전* $\nabla \times \vec{F}$: 벡터장 → 벡터장 (3D 만)

이 세 연산자들이 *서로 다른 종류* 의 객체들 사이를 오가면서, *어떤 통합된 원리* 가 있는 것처럼 보이긴 한다. 예를 들어 *발산의 회전은 0*, *회전의 그라디언트는 0* 같은 항등식이 있다.

그런데 *4차원 이상* 으로 가면 회전이라는 개념 자체가 잘 정의되지 않는다. 회전이 *3차원에서만 잘 작동* 한다는 사실이 §1 의 *외적이 3D 에서만 벡터로 표현* 되는 우연과 같은 뿌리. 

*외미분 (exterior derivative) $d$* 는 이 모든 것을 *하나의 연산자로 통합* 한다.

> **$d$ 의 역할**: $k$-form 을 받아 $(k+1)$-form 을 내놓는 *유일하고 자연스러운* 미분 연산자.
> 
> $$d: \Omega^k(M) \to \Omega^{k+1}(M)$$

이 연산자가 *모든 차원에서 잘 정의되며*, 그라디언트·발산·회전이 모두 *$d$ 의 특수 경우* 로 표현된다. *부호 항등식* ($\nabla \cdot (\nabla \times \vec{F}) = 0$ 등) 도 모두 *하나의 본질적 성질* $d^2 = 0$ 으로 통합.

이 장에서 $d$ 를 정확히 정의하고 그 성질을 본다. 다음 §9 에서 그라디언트·발산·회전과의 정확한 관계를 본다.

### 2. 0-form 위의 $d$: 함수의 전미분 (복습)

가장 단순한 경우, *0-form* (= 함수) 위의 $d$ 는 이미 §6 에서 봤다.

매끄러운 함수 $f \in \Omega^0(M)$ 에 대해

$$df = \sum_{i=1}^{n} \frac{\partial f}{\partial x^i}\, dx^i$$

이게 *함수의 전미분*. 결과는 *1-form*.

이 연산이 *벡터 작용* 의 측면에서 다음을 만족한다. 접벡터 $v$ 에 대해

$$df(v) = \nabla f \cdot v$$

즉 *$v$ 방향의 방향 미분*. 함수가 *얼마나 변하는지* 를 측정.

이제 이 연산을 *모든 차수의 미분형식으로* 확장하는 게 외미분의 정의.

### 3. 일반 $k$-form 위의 $d$: 정의

일반 $k$-form 의 외미분 정의는 *공리적으로* 주어진다. 즉 $d$ 가 만족해야 할 *핵심 성질들* 을 먼저 정하고, 그것들이 *유일한 연산자를 결정* 한다.

> **외미분 $d$ 의 공리**: $d$ 는 다음 네 성질을 만족하는 *유일한* 연산자 $d: \Omega^k(M) \to \Omega^{k+1}(M)$ 이다.
> 
> 1. *선형성*: $d(\alpha \omega + \beta \eta) = \alpha\, d\omega + \beta\, d\eta$ ($\alpha, \beta$ 상수)
> 2. *0-form 에서의 정의*: 함수 $f$ 에 대해 $df = \sum_i (\partial f / \partial x^i)\, dx^i$ (§6 의 정의)
> 3. *Leibniz 규칙 (등급화)*: $\omega$ 가 $k$-form, $\eta$ 가 $l$-form 일 때
> 
>    $$d(\omega \wedge \eta) = d\omega \wedge \eta + (-1)^k\, \omega \wedge d\eta$$
> 
> 4. *$d^2 = 0$*: $d(d\omega) = 0$ 모든 $\omega$ 에 대해.

이 네 조건이 $d$ 를 *유일하게 결정* 한다.

**왜 이 네 조건이 정당한가**

- 조건 1 (선형성) 은 자연스러운 요구. 미분 연산자는 보통 선형.
- 조건 2 는 외미분이 *익숙한 미분과 일치* 함을 보장.
- 조건 3 (Leibniz 규칙) 은 *곱의 미분 법칙* 의 일반화. 부호 $(-1)^k$ 는 등급화 가환성과 일관성을 위함.
- 조건 4 ($d^2 = 0$) 는 *가장 중요한 성질* — *이중 미분이 사라진다*. §6 §7 에서 본 mixed partial 의 대칭성에서 따라 나오는 자연스러운 결과.

### 4. 좌표 표현으로의 명시적 공식

위 공리에서 *좌표 표현으로의 명시적 계산법* 이 따라 나온다.

일반 $k$-form 

$$\omega = \sum_{i_1 < \cdots < i_k} f_{i_1 \cdots i_k}(x)\, dx^{i_1} \wedge \cdots \wedge dx^{i_k}$$

의 외미분은

> $$d\omega = \sum_{i_1 < \cdots < i_k} df_{i_1 \cdots i_k} \wedge dx^{i_1} \wedge \cdots \wedge dx^{i_k}$$

여기서 $df_{i_1 \cdots i_k}$ 는 조건 2 의 전미분.

**왜 이 공식이 옳은가**

조건 3 (Leibniz 규칙) 을 단항 $f_{i_1 \cdots i_k}\, dx^{i_1} \wedge \cdots \wedge dx^{i_k}$ 에 적용해 보자. $f_{i_1 \cdots i_k}$ 는 0-form 이므로

$$d(f \cdot dx^{i_1} \wedge \cdots \wedge dx^{i_k}) = df \wedge (dx^{i_1} \wedge \cdots \wedge dx^{i_k}) + (-1)^0\, f \cdot d(dx^{i_1} \wedge \cdots \wedge dx^{i_k})$$

두 번째 항에서 *$dx^{i_j}$ 가 $d$ 의 결과*  ($d(x^{i_j}) = dx^{i_j}$) 이고, $d^2 = 0$ 으로 $d(dx^{i_j}) = 0$. Leibniz 규칙을 반복 적용하면 두 번째 항이 *모두 0*. 따라서

$$d(f \cdot dx^{i_1} \wedge \cdots \wedge dx^{i_k}) = df \wedge dx^{i_1} \wedge \cdots \wedge dx^{i_k}$$

이 결과를 일반 $k$-form 에 *선형성* 으로 확장하면 위 공식이 따라 나온다.

**계산 절차**

실용적으로 외미분을 계산할 때:

(1) 각 단항의 *함수 계수* $f_I$ 만 *$d$ 하기* (= 전미분).

(2) 그 결과 (1-form) 를 단항의 *맨 앞* 에 쐐기곱.

(3) 분배. 그게 끝.

### 5. 구체적 예제 (2D)

2차원 ($n = 2$, 좌표 $x, y$) 에서 외미분을 손으로 계산해 보자.

**예제 1**: 0-form $f(x, y) = x^2 + xy$ 의 외미분.

전미분 공식으로:

$$df = \frac{\partial f}{\partial x}\, dx + \frac{\partial f}{\partial y}\, dy = (2x + y)\, dx + x\, dy$$

결과는 1-form.

**예제 2**: 1-form $\omega = P(x, y)\, dx + Q(x, y)\, dy$ 의 외미분.

위 공식 적용. 각 단항에 대해 $df_I \wedge dx^I$ 형태로:

먼저 $P\, dx$ 의 외미분:

$$d(P\, dx) = dP \wedge dx = \left(\frac{\partial P}{\partial x}\, dx + \frac{\partial P}{\partial y}\, dy\right) \wedge dx$$

분배하면

$$= \frac{\partial P}{\partial x}\, (dx \wedge dx) + \frac{\partial P}{\partial y}\, (dy \wedge dx)$$

$dx \wedge dx = 0$ 이고 $dy \wedge dx = -dx \wedge dy$ 이므로

$$d(P\, dx) = -\frac{\partial P}{\partial y}\, dx \wedge dy$$

비슷하게 $Q\, dy$ 에 대해

$$d(Q\, dy) = dQ \wedge dy = \frac{\partial Q}{\partial x}\, (dx \wedge dy) + \frac{\partial Q}{\partial y}\, (dy \wedge dy) = \frac{\partial Q}{\partial x}\, dx \wedge dy$$

(여기서 $dy \wedge dy = 0$ 이용.)

합치면

$$\boxed{\;\; d\omega = \left(\frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y}\right) dx \wedge dy \;\;}$$

이 결과가 *2D 회전 (curl)* — Green 정리의 적분량과 정확히 같음. §9 에서 자세히.

**예제 3**: 2-form $\omega = f(x, y)\, dx \wedge dy$ 의 외미분.

$$d\omega = df \wedge dx \wedge dy = \left(\frac{\partial f}{\partial x}\, dx + \frac{\partial f}{\partial y}\, dy\right) \wedge dx \wedge dy$$

전개하면

$$= \frac{\partial f}{\partial x}\, (dx \wedge dx \wedge dy) + \frac{\partial f}{\partial y}\, (dy \wedge dx \wedge dy)$$

첫째 항은 $dx \wedge dx = 0$ 으로 사라지고, 두 번째 항은 $dy$ 가 두 번 등장하므로 (다중선형 반대칭의 $f(v, v) = 0$ 성질) 0. 따라서

$$d(f\, dx \wedge dy) = 0$$

*2D 에서 2-form 의 외미분은 항상 0*. 이유는 *결과가 3-form 인데 2차원 공간에는 3-form 이 없음* ($\dim \Omega^3(\mathbb{R}^2) = 0$). 차원에 의한 자동 소멸.

### 6. 구체적 예제 (3D)

3차원 ($n = 3$, 좌표 $x, y, z$) 에서 더 풍부한 외미분 계산.

**예제 1**: 0-form $f$ 의 외미분 (그라디언트의 1-form 버전).

$$df = \frac{\partial f}{\partial x}\, dx + \frac{\partial f}{\partial y}\, dy + \frac{\partial f}{\partial z}\, dz$$

3D 그라디언트 $\nabla f = (\partial f / \partial x, \partial f / \partial y, \partial f / \partial z)$ 의 정보를 *1-form 으로 인코딩*. (벡터장과의 차이는 §6 에서.)

**예제 2**: 1-form $\omega = P\, dx + Q\, dy + R\, dz$ 의 외미분.

2D 예제처럼 각 단항에 대해 계산.

$$d(P\, dx) = \frac{\partial P}{\partial y}\, dy \wedge dx + \frac{\partial P}{\partial z}\, dz \wedge dx$$

(나머지는 $dx \wedge dx = 0$.) $dy \wedge dx = -dx \wedge dy$, $dz \wedge dx = -dx \wedge dz$ 로 정렬하면

$$d(P\, dx) = -\frac{\partial P}{\partial y}\, dx \wedge dy - \frac{\partial P}{\partial z}\, dx \wedge dz$$

$d(Q\, dy)$ 와 $d(R\, dz)$ 도 비슷하게 계산. 표준 정리하면

$$d\omega = \left(\frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y}\right) dx \wedge dy + \left(\frac{\partial R}{\partial x} - \frac{\partial P}{\partial z}\right) dx \wedge dz + \left(\frac{\partial R}{\partial y} - \frac{\partial Q}{\partial z}\right) dy \wedge dz$$

이 *세 계수* 가 정확히 3D 회전 $\nabla \times \vec{F}$ 의 *세 성분*! 자세히 보면

$$\nabla \times \vec{F} = \left(\frac{\partial R}{\partial y} - \frac{\partial Q}{\partial z},\; \frac{\partial P}{\partial z} - \frac{\partial R}{\partial x},\; \frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y}\right)$$

부호 정렬 후 정확히 위 외미분 결과와 일치. 따라서:

> *3D 에서 1-form 의 외미분 = 회전 (curl)*. 미분형식 언어로 정확한 대응.

**예제 3**: 2-form $\omega = P\, dy \wedge dz + Q\, dz \wedge dx + R\, dx \wedge dy$ 의 외미분.

각 단항 외미분 후 합치면 (계산 생략)

$$d\omega = \left(\frac{\partial P}{\partial x} + \frac{\partial Q}{\partial y} + \frac{\partial R}{\partial z}\right) dx \wedge dy \wedge dz$$

세 *편미분의 합* — 정확히 *발산 (divergence) $\nabla \cdot \vec{F}$* 의 식. 따라서:

> *3D 에서 2-form 의 외미분 = 발산 (divergence) × 부피 형식*.

### 7. $d^2 = 0$ 의 정확한 의미와 증명

외미분의 *가장 중요한 성질* 이 $d^2 = 0$. 이중 외미분은 항상 0.

> **정리**: 모든 매끄러운 미분형식 $\omega$ 에 대해
> 
> $$d(d\omega) = 0$$

**0-form 에서의 증명**

먼저 0-form (= 함수) 에 대해서 본다. 함수 $f$ 에 대해 $df = \sum_i (\partial f / \partial x^i)\, dx^i$.

이걸 다시 $d$ 하면

$$d(df) = \sum_i d\left(\frac{\partial f}{\partial x^i}\right) \wedge dx^i = \sum_i \sum_j \frac{\partial^2 f}{\partial x^j \partial x^i}\, dx^j \wedge dx^i$$

이중 합을 풀어 보자. 각 $(i, j)$ 쌍에서 *대각 항* ($i = j$) 은 $dx^i \wedge dx^i = 0$ 이므로 사라짐.

*비대각 항* 은 *교차 쌍* 으로 묶어 본다. $i < j$ 와 $i > j$ 의 두 항을 합쳐서

$$\frac{\partial^2 f}{\partial x^i \partial x^j}\, dx^i \wedge dx^j + \frac{\partial^2 f}{\partial x^j \partial x^i}\, dx^j \wedge dx^i$$

$dx^j \wedge dx^i = -dx^i \wedge dx^j$ 이므로

$$= \left( \frac{\partial^2 f}{\partial x^i \partial x^j} - \frac{\partial^2 f}{\partial x^j \partial x^i} \right) dx^i \wedge dx^j$$

매끄러운 함수의 *혼합 편미분의 대칭성* (클레로 정리, Schwarz 정리) 에 의해

$$\frac{\partial^2 f}{\partial x^i \partial x^j} = \frac{\partial^2 f}{\partial x^j \partial x^i}$$

따라서 각 쌍의 차이가 0. 모든 비대각 항도 0. 결과적으로 $d(df) = 0$. ∎

**일반 $k$-form 에 대한 일반화**

일반 $k$-form $\omega = f_I\, dx^I$ (단항으로 표기) 에 대해

$$d\omega = df_I \wedge dx^I$$

다시 $d$ 하면 (Leibniz 규칙 적용)

$$d(d\omega) = d(df_I) \wedge dx^I + (-1)^1\, df_I \wedge d(dx^I)$$

위 결과로 $d(df_I) = 0$. 또 $dx^I$ 가 *상수 좌표 미분들의 쐐기곱* 이므로 $d(dx^I) = 0$ (역시 Leibniz 규칙과 $d(dx^i) = 0$ 적용).

두 항 모두 0 이므로 $d^2 \omega = 0$. ∎

**$d^2 = 0$ 의 본질**

이 성질의 *본질* 은 *혼합 편미분의 대칭성* — 즉 미적분의 가장 기본적인 사실 중 하나. $d$ 가 이 대칭성을 *쐐기곱의 반대칭성과 만나게 해서* 자연스럽게 항등식 $d^2 = 0$ 으로 인코딩.

이게 *왜 $d^2 = 0$ 이 자연스러운지* 의 답: *대칭 + 반대칭 = 0*.

### 8. $d^2 = 0$ 의 결과: 익숙한 항등식들

$d^2 = 0$ 의 *익숙한 미적분 항등식들* 이 모두 따라 나온다.

**그라디언트의 회전 = 0**

함수 $f$ 의 그라디언트를 *1-form 으로 본 외미분* 이 $df$. 이걸 다시 $d$ 하면 (3D 회전):

$$d(df) = 0$$

좌변은 *$df$ (1-form) 의 외미분* — §9 의 결과로 *회전과 동치*. 따라서

$$\nabla \times (\nabla f) = 0$$

익숙한 항등식.

**회전의 발산 = 0**

벡터장 $\vec{F}$ 를 *2-form 으로 본 외미분* 이 발산 (위에서 봄). 

$\vec{F}$ 가 어떤 1-form $\omega_F$ 의 *외미분 결과* (즉 회전) 라면, 그걸 다시 $d$ 하면 0:

$$d(d\omega_F) = 0$$

이걸 발산-회전 언어로 옮기면

$$\nabla \cdot (\nabla \times \vec{G}) = 0$$

(어떤 $\vec{G}$ 에 대해 $\vec{F} = \nabla \times \vec{G}$ 일 때.) 또 익숙한 항등식.

**모든 부호 항등식의 통일**

벡터 미적분의 *복잡한 부호 항등식들* 이 모두 *$d^2 = 0$ 하나로 통합*. 이게 외미분의 *우아함*. 

### 9. 좌표 독립성

위에서 $d$ 를 *좌표 표현* 으로 정의했다. 그런데 다양체에는 *여러 좌표계* 가 가능. *다른 좌표에서 같은 결과* 가 나올까?

답: *그렇다*. $d$ 는 *좌표에 독립적인 자연스러운 연산자*.

증명 아이디어: 두 좌표계 $\{x^i\}$ 와 $\{y^j\}$ 사이의 좌표 변환을 $y^j = y^j(x)$ 라 하자. 함수의 전미분이 

$$df = \sum_i \frac{\partial f}{\partial x^i}\, dx^i = \sum_j \frac{\partial f}{\partial y^j}\, dy^j$$

(체인 룰로 자동 일치.) 이 일치가 일반 $k$-form 의 외미분에도 자연스럽게 확장됨 (Leibniz 규칙과 $d^2 = 0$ 보존).

이게 외미분이 *진짜로 자연스러운 객체* 라는 증거. 좌표를 어떻게 잡든 같은 결과 — *미분형식 언어의 좌표 독립성* 의 한 측면.

### 10. 폐형식과 완전형식

외미분 관련 *두 가지 중요한 개념*.

**폐형식 (closed form)**: 외미분이 0 인 미분형식.

$$d\omega = 0$$

위의 $d^2 = 0$ 에 의해, *어떤 형식의 외미분은 항상 폐형식*. 

**완전형식 (exact form)**: 다른 형식의 외미분으로 표현되는 미분형식.

$$\omega = d\eta \quad \text{어떤 } \eta \text{ 에 대해}$$

$d^2 = 0$ 으로 *완전형식은 항상 폐형식*:

$$\omega = d\eta \;\Rightarrow\; d\omega = d(d\eta) = 0$$

**역은?**

*폐형식이 항상 완전형식인가?* 즉 $d\omega = 0$ 이면 $\omega = d\eta$ 인 $\eta$ 가 존재하는가?

답은 *공간의 위상에 따라 다르다*. 

- *볼록한 영역* (또는 *수축 가능한 영역*) 에서는 *항상 그렇다* — Poincaré 보조정리.
- *위상적으로 복잡한 영역* (예: 원, 도넛 모양) 에서는 *그렇지 않을 수 있다*.

이 차이를 측정하는 것이 *de Rham cohomology* (§12). 

> 폐형식 / 완전형식의 비율 = $H^k(M)$ (de Rham 코호몰로지 군)

이게 *외미분이 위상 정보를 인코딩* 한다는 놀라운 사실. 자세한 내용은 §12.

**§6 §10 의 예제 다시 보기**

§6 §10 에서 "어떤 함수의 미분도 아닌 1-form" 의 예로 $\omega = y\, dx - x\, dy$ 를 봤다. 이 1-form 의 외미분을 계산해 보면

$$d\omega = -dy \wedge dx - dx \wedge dy = dx \wedge dy - dx \wedge dy + \cdots$$

다시 정렬하면 (잠깐의 부호 정리)

$$d(y\, dx) = dy \wedge dx = -dx \wedge dy$$

$$d(-x\, dy) = -dx \wedge dy$$

합치면 $d\omega = -dx \wedge dy - dx \wedge dy = -2\, dx \wedge dy \neq 0$.

따라서 $\omega$ 가 *폐형식이 아님*. 따라서 어떤 함수의 미분도 아닌 것이 *외미분으로 즉시 확인*.

(만약 *원에서 정의된* 비슷한 1-form $\omega = (x\, dy - y\, dx)/(x^2 + y^2)$ 를 보면, *폐형식이지만 전체 정의역에서 완전형식이 아닌* 1-form 의 유명한 예. §12 에서 다룬다.)

### 11. 정리

이 장에서 다룬 내용을 정리한다.

**1)** *외미분* $d: \Omega^k(M) \to \Omega^{k+1}(M)$ 는 $k$-form 을 $(k+1)$-form 으로 보내는 *통합된 미분 연산자*.

**2)** *네 가지 공리* 로 정의: 선형성, 0-form 에서의 정의 (전미분), Leibniz 규칙, $d^2 = 0$.

**3)** *좌표 명시적 공식*:

$$d\omega = \sum_I df_I \wedge dx^I$$

— 각 단항의 *함수 계수만 외미분* 하고 *맨 앞에 쐐기곱*.

**4)** *2D 1-form 의 외미분*: $d(P\, dx + Q\, dy) = (\partial_x Q - \partial_y P)\, dx \wedge dy$ — *2D 회전*.

**5)** *3D 1-form 의 외미분*: $d\omega_F$ 가 *3D 회전 $\nabla \times \vec{F}$* 와 일치.

**6)** *3D 2-form 의 외미분*: 발산 × 부피 형식.

**7)** *$d^2 = 0$* — 이중 외미분은 항상 0. 본질은 *혼합 편미분의 대칭성*.

**8)** *익숙한 부호 항등식들* ($\nabla \times \nabla f = 0$, $\nabla \cdot (\nabla \times \vec{F}) = 0$) 이 모두 $d^2 = 0$ 의 결과.

**9)** *좌표 독립성*: $d$ 가 좌표 선택에 무관한 자연스러운 연산자.

**10)** *폐형식* $d\omega = 0$ 과 *완전형식* $\omega = d\eta$. 완전 → 폐는 항상 성립. 폐 → 완전은 *공간의 위상에 따라 다름*. 차이가 *de Rham cohomology* (§12).

다음 §9 에서 *외미분과 벡터 미적분의 정확한 대응* — 그라디언트·발산·회전이 모두 *$d$ 의 특수 경우* 로 어떻게 나오는지 — 를 자세히 본다.
