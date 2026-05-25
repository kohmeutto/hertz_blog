+++
title = "Hodge 별표"
weight = 13
+++

### 1. 동기: $k$-form 과 $(n-k)$-form 의 자연스러운 대응

§4 에서 외대수의 차원을 정리할 때 *흥미로운 대칭성* 이 있었다.

$$\dim \Lambda^k V = \binom{n}{k} = \binom{n}{n-k} = \dim \Lambda^{n-k} V$$

이항 계수의 *대칭성* 으로 *$k$-form 공간과 $(n-k)$-form 공간의 차원이 같다*.

차원이 같다는 건 두 공간이 *벡터 공간으로 동형* 임을 뜻한다. 하지만 *자연스러운 (canonical) 대응이 있는가* 는 별개의 문제 — §6 의 *벡터와 1-form* 사이의 관계처럼.

**자연스러운 대응을 만들려면**

§6 에서 본 *음악적 동형사상* 처럼, *추가 구조* 가 필요하다. 이번에는 *메트릭 (metric)* — 즉 *내적 (inner product)* — 이 필요하다.

메트릭이 주어지면, *$k$-form 과 $(n-k)$-form 사이의 자연스러운 대응* 이 정의된다. 이 대응이 **Hodge 별표 (Hodge star) $\star$**.

> $$\star : \Lambda^k V \to \Lambda^{n-k} V$$

이 장에서 Hodge 별표의 정확한 정의, 좌표 표현, 핵심 성질, 그리고 *왜 물리에서 자연스럽게 등장* 하는지를 본다.

### 2. 메트릭과 미분형식의 내적

먼저 메트릭이 *미분형식 사이의 내적* 을 유도하는 방식을 본다.

**벡터의 내적에서 출발**

$V$ 가 $n$ 차원 벡터 공간이고 *내적 $g$* 가 주어져 있다고 하자. 표준 표기로 벡터들의 내적:

$$g(v, w) = v_i\, g^{ij}\, w_j \quad \text{또는 단순히} \quad \langle v, w \rangle$$

$\mathbb{R}^n$ 의 표준 내적이면 $g^{ij} = \delta^{ij}$ (Kronecker delta), 즉 $g(v, w) = \sum_i v_i w_i$.

**1-form 의 내적**

§6 에서 본 음악적 동형사상 (메트릭으로 가능) 을 사용. 두 1-form $\alpha, \beta$ 에 대해

$$\langle \alpha, \beta \rangle := g(\alpha^\sharp, \beta^\sharp)$$

즉 두 1-form 을 *벡터로 바꿔서 내적*. 표준 좌표에서

$$\langle \alpha, \beta \rangle = \sum_i \alpha_i \beta_i$$

**$k$-form 의 내적**

$k$-form 들 사이의 내적은 *기본 단항의 내적을 먼저 정의* 한 다음 *선형성으로 확장*. 두 기본 $k$-form $\alpha_1 \wedge \cdots \wedge \alpha_k$ 와 $\beta_1 \wedge \cdots \wedge \beta_k$ 의 내적:

$$\langle \alpha_1 \wedge \cdots \wedge \alpha_k,\, \beta_1 \wedge \cdots \wedge \beta_k \rangle := \det\big( \langle \alpha_i, \beta_j \rangle \big)_{i, j = 1, \ldots, k}$$

(*$k \times k$ 행렬의 행렬식*. 두 인자의 내적들의 행렬식.)

**표준 기저에서**

표준 좌표 ($\mathbb{R}^n$ 의 유클리드 메트릭) 에서, *서로 다른 기본 $k$-form* 들이 *정규 직교 (orthonormal)*:

$$\langle dx^{i_1} \wedge \cdots \wedge dx^{i_k},\, dx^{j_1} \wedge \cdots \wedge dx^{j_k} \rangle = \begin{cases} 1 & (i_1, \ldots, i_k) = (j_1, \ldots, j_k) \\ 0 & \text{otherwise} \end{cases}$$

(*인덱스가 오름차순으로 정렬된* 표준 기저 가정.) 따라서 $\Lambda^k V$ 의 *표준 기저가 자연스러운 정규 직교 기저*.

### 3. Hodge 별표의 정의

이제 Hodge 별표를 정확히 정의할 준비가 됐다.

**정의 (Hodge 별표)**

$V$ 가 $n$ 차원 *정향 (oriented) 내적 공간*, $\omega_0 = e^1 \wedge \cdots \wedge e^n$ 이 *방향이 주어진 부피 형식* 일 때, *Hodge 별표* $\star: \Lambda^k V \to \Lambda^{n-k} V$ 는 다음 식으로 정의:

> $$\alpha \wedge \star \beta = \langle \alpha, \beta \rangle\, \omega_0 \quad \forall \alpha \in \Lambda^k V$$

이 식이 *모든 $\alpha$* 에 대해 성립하도록 *$\star \beta$ 가 유일하게* 결정.

**의미를 풀어 보면**

$\beta$ 가 $k$-form 이고 $\star \beta$ 가 $(n-k)$-form 이면, 그 쐐기곱 $\alpha \wedge \star \beta$ 가 *최고차 $n$-form*. 1차원 공간 $\Lambda^n V$ 의 원소는 *부피 형식의 스칼라 배*.

그 스칼라가 *$\alpha$ 와 $\beta$ 의 내적* 이 되도록 $\star\beta$ 를 잡는 것.

**Hodge 별표의 직관**

기하학적으로 $\star \beta$ 는 *$\beta$ 의 직교 보완 (orthogonal complement)*. $\beta$ 가 *$k$-차원 부분공간* 을 나타낸다면, $\star \beta$ 는 *그 부분공간에 수직인 $(n-k)$-차원 부분공간* 을 나타낸다.

이게 *왜 Hodge 별표가 "별표"인지* 의 직관 — *원래 객체에 대응되는 "여공간" (complementary space)* 을 가리킴.

### 4. 명시적 좌표 표현 (3D)

3차원 유클리드 공간에서 Hodge 별표를 *명시적으로* 계산해 본다.

**기본 형식들의 별표**

표준 좌표 $x, y, z$ 와 표준 메트릭 (유클리드).

*0-form 의 별표*: $\Lambda^0 \to \Lambda^3$.

$$\star 1 = dx \wedge dy \wedge dz$$

(*상수 1 의 별표는 부피 형식*.)

*1-form 의 별표*: $\Lambda^1 \to \Lambda^2$.

$$\star\, dx = dy \wedge dz, \quad \star\, dy = dz \wedge dx, \quad \star\, dz = dx \wedge dy$$

(*1-form 의 별표가 그것에 수직인 2-form*. 순환 순서 주의.)

*2-form 의 별표*: $\Lambda^2 \to \Lambda^1$.

$$\star (dy \wedge dz) = dx, \quad \star (dz \wedge dx) = dy, \quad \star (dx \wedge dy) = dz$$

(1-form ↔ 2-form 이 대칭적으로 매핑.)

*3-form 의 별표*: $\Lambda^3 \to \Lambda^0$.

$$\star (dx \wedge dy \wedge dz) = 1$$

(*부피 형식의 별표는 1*.)

**일반 1-form 의 별표**

벡터장 $\vec{F} = (P, Q, R)$ 에 대응하는 1-form $\omega_F = P\, dx + Q\, dy + R\, dz$ 의 별표:

$$\star \omega_F = P\, dy \wedge dz + Q\, dz \wedge dx + R\, dx \wedge dy$$

이게 *§7 §5 에서 본 "벡터장의 플럭스 형식"* — 정확히 같은 객체. *Hodge 별표가 1-form 을 그에 대응하는 플럭스 2-form 으로 보낸다*.

### 5. Hodge 별표의 핵심 성질

**1) $\star^2 = \pm 1$ (이중 별표)**

Hodge 별표를 두 번 적용하면 *원래 형식의 $\pm$ 배*:

$$\star (\star \alpha) = (-1)^{k(n-k)}\, \alpha \quad (\alpha \in \Lambda^k V \text{ in Euclidean signature})$$

부호 인자가 *차수에 의존*.

**3D 유클리드의 경우**: $n = 3$, 모든 $k$ 에 대해 $k(n-k) = k(3-k)$ 가 *짝수* (직접 확인). 따라서

$$\star^2 = +1 \text{ (3D 에서)}$$

*이중 별표가 항등사상*. 

**4D Minkowski의 경우**: 부호가 더 복잡 (Lorentzian metric 때문). 다음 절에서 자세히.

**2) 내적 보존**

$$\langle \alpha, \beta \rangle = \langle \star \alpha, \star \beta \rangle$$

Hodge 별표는 *내적을 보존하는 등거리 사상 (isometry)*. 정의로부터 직접 증명 가능.

**3) 양의 정부호 메트릭에서의 정의의 일관성**

위의 정의 $\alpha \wedge \star \beta = \langle \alpha, \beta \rangle\, \omega_0$ 에서 $\alpha = \beta$ 로 두면

$$\beta \wedge \star \beta = \langle \beta, \beta \rangle\, \omega_0 = |\beta|^2 \omega_0 \ge 0$$

(*양의 정부호 메트릭에서*.) 이게 *형식의 크기* 가 자연스럽게 등장하는 자리.

### 6. 4차원 Minkowski 공간의 별표

상대성이론과 Maxwell 방정식에서 가장 중요한 *4차원 Minkowski 공간* 의 별표는 약간 다르다.

**메트릭의 차이**

Minkowski 메트릭은 *Lorentzian* — 즉 *유클리드와 부호가 다른* 메트릭. 좌표 $x^0 = ct, x^1, x^2, x^3$ 에 대해

$$g = \text{diag}(-1, +1, +1, +1) \quad \text{(또는 } \text{diag}(+1, -1, -1, -1)\text{)}$$

(*signature* 의 선택에 따라 부호 약속이 다르지만, 핵심은 *시간 좌표가 다른 부호*.)

**이중 별표 부호**

Minkowski 4D 에서:

$$\star^2 = (-1)^{k(4-k)} \cdot (-1)^1 = (-1)^{k(4-k) + 1}$$

(여기서 마지막 $-1$ 은 *signature 의 negative eigenvalue 의 수가 1* 이라는 점에서 옴.)

$k = 1$ 의 경우: $\star^2 = (-1)^{3+1} = +1$.

$k = 2$ 의 경우: $\star^2 = (-1)^{4+1} = -1$. *마이너스*. 

이게 *4D Minkowski 2-form 에 대해 $\star^2 = -1$* — Maxwell 방정식에서 *전기·자기 이중성 (electric-magnetic duality)* 의 자연스러운 표현.

### 7. 코미분 $\delta$ (codifferential)

Hodge 별표가 정의되면, 외미분 $d$ 의 *짝 (adjoint)* 인 *코미분 $\delta$* 가 자연스럽게 정의된다.

**정의**

> $$\delta := (-1)^{\cdots} \star d \star : \Omega^k \to \Omega^{k-1}$$

부호 인자는 차원과 차수에 의존. *결과: $k$-form 을 $(k-1)$-form 으로 보냄*. $d$ 의 반대 방향.

**3D 유클리드 표현**

3차원 유클리드에서 코미분이 *익숙한 벡터 미적분 연산자* 와 대응한다.

*1-form 의 코미분*: $\delta \omega = -\star d \star \omega$. 벡터장 $\vec{F}$ 의 1-form $\omega_F$ 에 대해

$$\delta \omega_F = -\nabla \cdot \vec{F}$$

(*발산의 음수*.) 1-form 에 대한 코미분이 *발산의 자연스러운 표현*.

*2-form 의 코미분*: 비슷한 계산으로 *회전 (curl) 의 음수* 와 관련.

### 8. Laplace-de Rham 연산자

외미분과 코미분을 합치면 *라플라스 연산자의 일반화* 가 나온다.

**정의 (Laplace-de Rham)**

> $$\Delta := d\delta + \delta d : \Omega^k \to \Omega^k$$

*$k$-form 을 $k$-form 으로* 보내는 *2차 미분 연산자*.

**0-form 의 라플라시안**

함수 $f$ 에 대해

$$\Delta f = \delta(df) + d(\delta f) = \delta(df) + 0 = -\nabla \cdot (\nabla f) = -\nabla^2 f$$

(*$\delta f = 0$* 은 $f$ 가 *0-form 이므로 더 낮은 차수가 없음*.) 

부호 약속에 따라 *익숙한 라플라시안 $\nabla^2 f$* 과 같은 값 (부호 약속만 다름).

**일반 $k$-form 의 라플라시안**

$\Delta = d\delta + \delta d$ 가 *모든 차수에서* 잘 정의된 라플라시안. 

이게 *물리에서 자주 등장하는 연산자*. 예: *맥스웰 방정식의 빈 공간 해* 가 *$\Delta A = 0$* 의 해.

### 9. Hodge 정리

de Rham 코호몰로지의 *놀라운 정리* 가 Hodge 정리.

> **Hodge 정리**: 컴팩트 정향 리만 다양체 $M$ 의 각 de Rham 코호몰로지 류에서 *조화적 (harmonic) 대표원* 이 유일하게 존재.

여기서 *조화적 $k$-form* 은 $\Delta \omega = 0$ 인 $k$-form.

**의미**

$H^k(M)$ 의 한 원소는 *동치류 (폐형식들 모듈로 완전형식들)*. Hodge 정리에 의해 *각 동치류에서 라플라시안 = 0 인 특별한 대표원 (조화형식)* 이 *유일하게* 존재.

이게 *위상학적 정보 ($H^k$) 와 해석학적 정보 (조화형식) 의 완벽한 대응*. 

**응용**

- *Hodge 분해*: 모든 $k$-form 이 *조화형식 + 완전형식 + 코완전형식* 으로 *유일하게 분해*.
- *지표 정리 (index theorem)*: 조화형식의 차원 = 코호몰로지의 Betti 수 = 위상학적 불변량. 이게 *Atiyah-Singer 지표 정리* 의 출발점.

이 깊은 결과들이 *Hodge 별표가 단순한 도구 이상* 임을 보여준다.

### 10. Maxwell 방정식의 준비

§14 에서 자세히 다룰 *Maxwell 방정식의 미분형식 표현* 을 위한 준비.

**전자기 텐서**

4차원 Minkowski 시공간 위의 *전자기 2-form*:

$$F = \frac{1}{2}\, F_{\mu\nu}\, dx^\mu \wedge dx^\nu$$

여기서 $F_{\mu\nu}$ 가 *전자기 텐서* — 6 개의 독립 성분이 *전기장의 3 성분 + 자기장의 3 성분*. 

**Maxwell 방정식 (미리보기)**

자기장의 발산 없음 + Faraday 법칙:

$$dF = 0$$

(*$F$ 가 폐 2-form*.) 이게 *§9 §8 에서 본 "비회전 + 자기 모노폴 없음"* 의 4D 통일된 표현.

Gauss 법칙 + Ampère-Maxwell 법칙:

$$d \star F = J$$

(*외미분과 Hodge 별표 합성이 전류 3-form*.) 

> *맥스웰의 네 방정식이 두 줄로* — $dF = 0$ 과 $d \star F = J$.

이 표현이 가능하려면 *Hodge 별표가 필수*. Lorentzian 메트릭의 $\star$ 가 *전기장과 자기장을 자연스럽게 섞어줌* — 전기·자기 이중성.

§14 에서 자세히 다룬다.

### 11. NEGF·응집계와의 연결

Hodge 별표가 *응집계 물리에서 자주 등장*.

**Brillouin 영역의 Hodge 이론**

토러스 위에서 정의된 *Bloch 파동함수* 들의 *Berry 곡률* 은 *2-form*. Brillouin 영역의 *볼륨* 에 대한 적분이 *Chern 수* 인데, 이 적분에서 *Hodge 별표가 자연스럽게 등장*.

**TKNN 공식**

*Thouless-Kohmoto-Nightingale-den Nijs 공식* — 양자 홀 전도도가 *Chern 수의 정수 배*. 

$$\sigma_{xy} = \frac{e^2}{h} \cdot C, \quad C = \frac{1}{2\pi} \int_{BZ} F$$

여기서 $F$ 의 적분에서 *Hodge 별표가 메트릭 (Brillouin 영역의 자연 메트릭) 을 통해 등장*.

**Green 함수의 스펙트럼 분해**

NEGF 에서 *그린 함수의 스펙트럼 분해* 가 *Hodge 분해의 무한 차원 일반화* 로 볼 수 있음. 그린 함수의 *조화 부분 (resolvent) 과 비조화 부분* 의 분리가 Hodge 정리의 정신.

### 12. 일반 메트릭과의 일반화

위에서 표준 (유클리드 또는 Minkowski) 메트릭을 가정했는데, *일반 리만 / 의사-리만 다양체* 에서도 Hodge 별표가 잘 정의된다.

**리만 다양체 (양의 정부호)**

리만 다양체에서 메트릭 $g_{ij}$ 가 *양의 정부호*. 부피 형식

$$\omega_g = \sqrt{|\det g|}\, dx^1 \wedge \cdots \wedge dx^n$$

이게 *메트릭의 야코비안* 을 포함하는 *일반 부피 형식*. $\sqrt{|\det g|}$ 가 *기준 좌표에서 메트릭의 정보를 인코딩*.

**의사-리만 다양체 (Minkowski 처럼)**

*signature* 가 $(p, q)$ — 즉 $p$ 개의 양의 고윳값, $q$ 개의 음의 고윳값. 부피 형식은 같은 형태지만 *행렬식의 부호* 가 *signature* 에 의존.

**리 군의 Hodge 별표**

§14 의 Noether 정리 응용에서 사용될 *리 군 위의 Haar 측도* 가 *Hodge 별표의 일반화된 부피 형식*. Lie 군 시리즈의 결과와 자연스럽게 연결.

### 13. 정리

이 장에서 다룬 내용을 정리한다.

**1)** *Hodge 별표* $\star: \Lambda^k V \to \Lambda^{n-k} V$ 는 *$k$-form 을 $(n-k)$-form 으로* 자연스럽게 보내는 변환.

**2)** *정의*: $\alpha \wedge \star \beta = \langle \alpha, \beta \rangle\, \omega_0$. *내적과 부피 형식을 사용*.

**3)** *필요 조건*: 메트릭 (또는 내적) 과 *정향 (orientation)* 이 있어야 함.

**4)** *기본 성질*: 

- $\star^2 = (-1)^{k(n-k)}$ (유클리드).
- 내적 보존 등거리 사상.

**5)** *3D 유클리드 별표*: 1-form ↔ 2-form 의 자연스러운 대응. 벡터장의 *플럭스 형식*이 1-form 의 별표.

**6)** *4D Minkowski 별표*: 2-form 에 대해 $\star^2 = -1$ — *전기·자기 이중성*의 자연스러운 표현.

**7)** *코미분* $\delta := \star d \star$ (부호 인자 포함). 외미분의 짝.

**8)** *Laplace-de Rham 연산자* $\Delta = d\delta + \delta d$. 모든 차수의 미분형식에 작용.

**9)** *Hodge 정리*: 각 코호몰로지 류에 *유일한 조화 대표원* 존재. *위상학과 해석학의 깊은 연결*.

**10)** *Maxwell 방정식* 의 미분형식 표현 ($dF = 0$, $d \star F = J$) 이 Hodge 별표를 *결정적으로 사용*.

**11)** *응집계 물리*: Chern 수, Berry 곡률, NEGF 의 그린 함수 분해 — 모두 Hodge 이론과 연결.

다음 §14 에서 외대수 시리즈의 *마지막 장* 으로 *주요 응용* 들을 자세히 본다. *Maxwell 방정식, 심플렉틱 기하 (Hamilton 역학), Berry 위상, Noether 정리* — 외대수 언어가 *물리의 자연스러운 도구* 임을 보여주는 응용들.
