+++
title = "고차 미분형식: k-form"
weight = 7
+++

### 1. 동기: 1-form 에서 더 높은 차수로

§6 에서 1-form 을 정의했다. *각 점마다 코벡터를 주는 객체* — 그리고 그게 결국 *각 점에서 1차 미분형식* 이었다.

그런데 자연에는 *2차원 면 위의 양*, *3차원 부피 안의 양* 같은 게 흔히 등장한다. 

- *전기장의 플럭스*: 면을 통과하는 전기장의 양. 면은 *2차원* 객체.
- *전류 밀도*: 단위 면적당 흐르는 전하. 역시 2차원적.
- *질량 밀도*: 단위 부피당 질량. *3차원* 객체.
- *상대성이론의 전자기 텐서*: 시공간 (4차원) 의 *2차원 면 요소* 와 연동.

이런 양들을 *방향이 붙은 면이나 부피에 자연스럽게 작용* 하는 객체로 일반화한 것이 **$k$-form** (고차 미분형식).

§3-§5 의 *쐐기곱과 외대수* 와 §6 의 *1-form* 을 합치면 자연스럽게 $k$-form 이 나온다. 이 장에서 그 정의와 성질, 그리고 *왜 자연스러운 객체인지* 를 본다.

### 2. $k$-form 의 정의

**정의** (k-form): 다양체 $M$ 위의 **$k$-form** 은 *각 점마다 $\Lambda^k T_p^* M$ 의 한 원소를 부여* 하는 객체다.

여기서 $T_p^* M$ 은 §6 에서 본 *점 $p$ 에서의 쌍대 공간* (코벡터 공간). $\Lambda^k T_p^* M$ 은 §3-§4 에서 본 *그 쌍대 공간의 $k$-차 외승* — 즉 $k$ 개의 코벡터들을 쐐기곱한 객체들의 공간.

좀 더 직관적으로 풀어 쓰면: *$k$-form 은 1-form 들의 쐐기곱과 그 일차 결합*. 점마다 그 값이 *코벡터들의 쐐기곱이라는 새 종류의 객체*.

**작용 방식**

1-form 이 *한 벡터를 먹어서 숫자를 내놓았다* 면, $k$-form 은 *$k$ 개의 벡터를 먹어서 숫자를 내놓는다*. 더 정확히는:

> $\omega$ 가 $k$-form 일 때, $k$ 개의 접벡터 $v_1, \ldots, v_k \in T_p M$ 에 대해
> 
> $$\omega_p(v_1, v_2, \ldots, v_k) \in \mathbb{R}$$
> 
> 가 정의되고, 이 결과는 *각 인자에 대해 선형이며 반대칭*.

다중선형성과 반대칭성은 외대수의 본질이라 *자동으로* 따라 나온다 (§3 의 쐐기곱 성질 그대로).

기하학적으로 $\omega_p(v_1, \ldots, v_k)$ 는 *$k$ 개의 벡터로 만든 방향이 붙은 $k$-차원 평행체에 $k$-form 이 작용한 값* — 평행체의 "잘 조절된 부피"라 보면 된다.

### 3. 좌표 기저 $k$-form

1-form 의 기저가 $dx^1, dx^2, \ldots, dx^n$ 이었다 (§6). $k$-form 의 기저는 이들의 *쐐기곱* 으로 얻어진다.

§4 에서 본 $\Lambda^k V^*$ 의 기저 구조를 그대로 가져오면:

> $k$-form 공간의 표준 좌표 기저:
> 
> $$\{\, dx^{i_1} \wedge dx^{i_2} \wedge \cdots \wedge dx^{i_k} \;:\; 1 \le i_1 < i_2 < \cdots < i_k \le n \,\}$$

*인덱스가 엄격히 오름차순*. §4 와 정확히 같은 약속.

차원도 §4 와 같다:

$$\dim \Omega^k(M)_p = \binom{n}{k}$$

(여기서 $\Omega^k(M)$ 은 $M$ 위의 모든 $k$-form 의 공간, 첨자 $p$ 는 *한 점에서의 차원*. 함수로서의 자유도까지 포함하면 무한 차원이지만, *한 점의 코벡터 공간만 보면* 유한.)

**작은 $n$ 에서 명시적**

3차원 ($n = 3$, 좌표 $x, y, z$):

- 1-form 기저 (3개): $dx, dy, dz$
- 2-form 기저 (3개): $dx \wedge dy,\ dx \wedge dz,\ dy \wedge dz$
- 3-form 기저 (1개): $dx \wedge dy \wedge dz$

4차원 ($n = 4$, 좌표 $x^0, x^1, x^2, x^3$ — 보통 상대성이론에서는 $x^0 = ct$):

- 1-form 기저 (4개): $dx^0, dx^1, dx^2, dx^3$
- 2-form 기저 (6개): $dx^0 \wedge dx^1, dx^0 \wedge dx^2, \ldots, dx^2 \wedge dx^3$
- 3-form 기저 (4개): $dx^0 \wedge dx^1 \wedge dx^2$ 등
- 4-form 기저 (1개): $dx^0 \wedge dx^1 \wedge dx^2 \wedge dx^3$

(4D 2-form 의 *여섯 개* 기저가 *맥스웰 방정식의 전자기 텐서* 와 정확히 같은 구조 — 6개 성분: $E_x, E_y, E_z, B_x, B_y, B_z$. §14 에서 자세히.)

### 4. 일반 $k$-form 의 표현

다양체 위의 *임의의 $k$-form* 은 좌표 기저의 *함수 계수* 일차 결합으로 표현된다.

$$\omega = \sum_{i_1 < i_2 < \cdots < i_k} f_{i_1 i_2 \cdots i_k}(x)\, dx^{i_1} \wedge dx^{i_2} \wedge \cdots \wedge dx^{i_k}$$

여기서 $f_{i_1 \cdots i_k}(x)$ 들은 *매끄러운 함수*. 점에 따라 값이 변하므로 *점마다 다른 $k$-벡터*.

합의 인덱스 범위 $i_1 < i_2 < \cdots < i_k$ 는 *기저가 중복 없이* 표현되도록 제한.

**1-form 의 일반화**

$k = 1$ 일 때 위 표현은

$$\omega = \sum_{i_1} f_{i_1}(x)\, dx^{i_1}$$

— §6 의 1-form 표현. 즉 $k$-form 이 1-form 의 직접적 일반화임이 보인다.

### 5. 2-form 의 예제

가장 친숙한 (1-form 외의) $k$-form 이 2-form 이다. 구체적 예를 본다.

**예 1**: 2차원 평면 ($\mathbb{R}^2$, 좌표 $x, y$) 위의 2-form

$$\omega = f(x, y)\, dx \wedge dy$$

2D 에서 $\dim \Omega^2 = \binom{2}{2} = 1$ 이므로 *2D 의 모든 2-form 은 이 형태*. 함수 $f$ 가 점에 따른 *작용 강도* 를 결정.

**예 2**: 3차원 공간 ($\mathbb{R}^3$, 좌표 $x, y, z$) 위의 일반 2-form

$$\omega = P(x, y, z)\, dy \wedge dz + Q(x, y, z)\, dz \wedge dx + R(x, y, z)\, dx \wedge dy$$

(여기서 표준 기저를 약간 재배열한 것 — $dx \wedge dz = -dz \wedge dx$ 라서 $dz \wedge dx$ 로 표기. *오른손 좌표계의 순환 순서* 에 맞춤.)

이 표현이 *익숙해 보이는 이유*: 3D 벡터장 $\vec{F} = (P, Q, R)$ 과 정확히 같은 정보. 사실:

> 3D 에서 *2-form* ↔ *벡터장* 의 자연스러운 대응이 있다 (Hodge 별표를 통해, §13 에서 정확히).

이게 §1 §6 에서 본 "*3D 에서만 외적이 벡터 같은 행동*" 의 미분형식 버전.

**2-form 의 작용**

$\omega = P\, dy \wedge dz + Q\, dz \wedge dx + R\, dx \wedge dy$ 가 두 벡터 $\vec{u}, \vec{v}$ 에 작용하면

$$\omega(\vec{u}, \vec{v}) = P(u_2 v_3 - u_3 v_2) + Q(u_3 v_1 - u_1 v_3) + R(u_1 v_2 - u_2 v_1) = \vec{F} \cdot (\vec{u} \times \vec{v})$$

오른쪽이 *플럭스의 기본 공식*: 벡터장 $\vec{F}$ 가 평행사변형 $\vec{u} \times \vec{v}$ 를 통과하는 양.

> 3D 의 2-form 은 *벡터장의 플럭스를 측정하는 객체*.

이게 *왜 전기장의 플럭스* 등이 자연스럽게 2-form 으로 표현되는지의 이유.

### 6. 3-form 의 예제

**예**: 3차원 공간 위의 일반 3-form

$$\omega = f(x, y, z)\, dx \wedge dy \wedge dz$$

3D 에서 $\dim \Omega^3 = 1$ 이므로 모든 3-form 은 이 형태. 함수 $f$ 가 *위치에 따른 밀도*.

**3-form 의 작용**

이 3-form 이 세 벡터 $\vec{u}, \vec{v}, \vec{w}$ 에 작용하면

$$\omega(\vec{u}, \vec{v}, \vec{w}) = f(x, y, z) \cdot \det(\vec{u}, \vec{v}, \vec{w})$$

§5 에서 본 *행렬식과 쐐기곱의 관계* 에 의해, 결과가 *$f$ × 평행육면체의 방향 부피*.

이게 *부피 적분의 자연스러운 객체*. 영역 $\Omega$ 위에서 *$f$ 의 부피 적분*

$$\iiint_\Omega f\, dV$$

는 사실 *3-form $\omega = f\, dx \wedge dy \wedge dz$ 의 적분*. 여기서 $dV$ 가 우리 외대수의 $dx \wedge dy \wedge dz$ 임을 인식하면, 미적분의 익숙한 공식이 외대수 언어로 *자연스럽게 정리* 된다.

### 7. 미분형식의 쐐기곱

미분형식들끼리 쐐기곱이 정의된다 — $k$-form 과 $l$-form 을 쐐기곱하면 $(k+l)$-form.

> $$\wedge: \Omega^k(M) \times \Omega^l(M) \to \Omega^{k+l}(M)$$

**기본 규칙**: 점마다의 쐐기곱을 *함수 계수와 함께* 한다. 즉 두 미분형식

$$\omega = f\, dx^{i_1} \wedge \cdots \wedge dx^{i_k}, \quad \eta = g\, dx^{j_1} \wedge \cdots \wedge dx^{j_l}$$

의 쐐기곱은

$$\omega \wedge \eta = (f \cdot g)\, dx^{i_1} \wedge \cdots \wedge dx^{i_k} \wedge dx^{j_1} \wedge \cdots \wedge dx^{j_l}$$

(함수 계수는 그냥 곱셈, 1-form 들이 차례대로 쐐기곱.)

일반 미분형식은 이런 단항 형식의 합이므로 *각 단항 쌍에 대해 위 규칙을 적용* 하고 *분배* 한다.

**예제**: 3D 에서 $\omega = x\, dx$ 와 $\eta = y\, dy + z\, dz$ 의 쐐기곱.

$$\omega \wedge \eta = (x\, dx) \wedge (y\, dy + z\, dz) = xy\, (dx \wedge dy) + xz\, (dx \wedge dz)$$

결과는 2-form. *함수 계수는 곱해지고, 1-form 들은 쐐기곱 규칙으로 결합*.

### 8. 등급화 가환성 (재확인)

§4 에서 본 *등급화 가환성* 이 미분형식에도 그대로 적용된다.

> $\omega$ 가 $k$-form, $\eta$ 가 $l$-form 이면
> 
> $$\omega \wedge \eta = (-1)^{kl}\, \eta \wedge \omega$$

차수의 곱에 따라 부호가 결정. 

**주의할 점**: *함수 계수* (즉 0-form) 는 $k = 0$ 인 미분형식. $(-1)^{0 \cdot l} = 1$ 이므로 함수는 항상 *어느 미분형식과도 자유롭게 곱셈 순서를 바꿀 수 있다*:

$$f \wedge \omega = \omega \wedge f = f \omega$$

(함수와 미분형식의 쐐기곱은 그냥 *함수 배*.)

반면 두 *홀수 차수* 형식의 곱은 *반대칭*: 1-form 끼리는 $-$, 1-form 과 3-form 도 $-$, 3-form 끼리도 $-$.

두 *짝수 차수* 형식은 *교환적*: 2-form 끼리, 4-form 끼리 등.

### 9. $n$-form: 부피 형식

특별한 차수의 미분형식 — *$n$ 차원 다양체 위의 $n$-form* — 에는 따로 이름이 붙는다.

> $n$ 차원 다양체 위의 $n$-form 을 **최고차 형식 (top form)** 또는 *부피 형식의 후보* 라 부른다.

§4 에서 본 *최고차 외승 $\Lambda^n V^*$ 가 1차원* 이라는 사실의 미분형식 버전. 즉 *$n$ 차원 다양체 위의 모든 $n$-form 은*

$$\omega = f(x)\, dx^1 \wedge dx^2 \wedge \cdots \wedge dx^n$$

의 형태로 *유일하게* 표현됨. 함수 $f$ 가 점마다의 *부피 밀도*.

**부피 형식과 적분의 자연스러운 연결**

$n$-form 의 적분이 *$n$-차원 다양체 위의 적분*. 익숙한 다중적분

$$\int_M f\, dV$$

가 사실은 *$n$-form $\omega = f\, dx^1 \wedge \cdots \wedge dx^n$ 의 적분*. 자세한 정의는 §10.

**Lebesgue 측도와의 관계**

표준 좌표에서 $dx^1 \wedge \cdots \wedge dx^n$ 이 *Lebesgue 측도의 무한소* 와 일치. 차이는 *외대수의 부호 (방향) 정보* 를 갖는다는 점. 

미분형식의 적분은 자동으로 *방향이 붙은 적분* — 이게 §11 의 Stokes 정리의 자연스러운 부호 처리를 가능하게 한다.

### 10. 물리적 예: 미분형식의 자연스러운 등장

미분형식이 *자연스러운 언어* 가 되는 물리 예를 정리해 본다.

**플럭스 (flux)**: 자기장 / 전기장이 면을 통과하는 양은 *2-form* 의 면 적분.

$$\Phi_B = \int_S \vec{B} \cdot d\vec{A} = \int_S \omega_B \qquad \text{(2-form 적분)}$$

여기서 $\omega_B = B_x\, dy \wedge dz + B_y\, dz \wedge dx + B_z\, dx \wedge dy$.

**일과 순환 (circulation)**: 힘이 경로를 따라 한 일은 *1-form* 의 곡선 적분.

$$W = \int_C \vec{F} \cdot d\vec{r} = \int_C \omega_F \qquad \text{(1-form 적분)}$$

여기서 $\omega_F = F_x\, dx + F_y\, dy + F_z\, dz$.

**부피 적분**: 질량 / 전하 등의 부피 적분은 *3-form* (3D) 또는 *4-form* (4D) 의 적분.

$$M = \int_\Omega \rho\, dV = \int_\Omega \omega_\rho$$

여기서 $\omega_\rho = \rho\, dx \wedge dy \wedge dz$.

**전자기 텐서 (4D)**: 상대성이론의 전자기 텐서 $F_{\mu\nu}$ 가 *4차원 시공간 위의 2-form*. 

$$F = \frac{1}{2} F_{\mu\nu}\, dx^\mu \wedge dx^\nu$$

이게 *Maxwell 방정식을 두 줄로 압축* 하는 자연스러운 표현. §14 에서 자세히.

**핵심**: 위 모든 양들이 *미분형식의 적분* 형태로 정리되며, 그 *차수가 적분 영역의 차원과 일치*. 1차원 적분 → 1-form, 2차원 적분 → 2-form, $n$ 차원 적분 → $n$-form. 이게 *왜 미분형식이 적분의 자연스러운 언어인지* 의 답.

### 11. 형식 합의 가능성

여러 차수의 미분형식을 *합쳐서* 하나의 객체로 다룰 수도 있다. *형식 합* (formal sum):

$$\Omega = \alpha_0 + \alpha_1 + \alpha_2 + \cdots + \alpha_n$$

(각 $\alpha_k$ 가 $k$-form.) 이건 §4 의 *전체 외대수 $\Lambda V$* 의 미분형식 버전.

전체 외대수 미분형식의 공간:

$$\Omega^*(M) = \bigoplus_{k=0}^{n} \Omega^k(M)$$

이 공간에서 *쐐기곱이 자유롭게 작동* 한다 (다른 차수 끼리도). 결과는 *합 안에서 자동으로 적절한 차수에 들어간다*.

이런 통합된 시각이 *Stokes 정리, de Rham cohomology, Hodge 이론* 의 자연스러운 무대.

### 12. 정리

이 장에서 다룬 내용을 정리한다.

**1)** *$k$-form* 은 *각 점마다 $\Lambda^k T_p^* M$ 의 원소* 를 주는 객체. 1-form 의 자연스러운 일반화.

**2)** $k$-form 은 *$k$ 개의 벡터를 먹어서 숫자를 내놓는* 다중선형 반대칭 함수. 점마다 작용.

**3)** *좌표 기저*: $dx^{i_1} \wedge \cdots \wedge dx^{i_k}$ ($i_1 < \cdots < i_k$). 한 점에서의 차원이 $\binom{n}{k}$.

**4)** *일반 표현*: $\omega = \sum_{i_1 < \cdots < i_k} f_{i_1 \cdots i_k}(x)\, dx^{i_1} \wedge \cdots \wedge dx^{i_k}$. 함수 계수가 점마다 다름.

**5)** *2-form*: 3D 에서 *벡터장의 플럭스* 와 자연스러운 대응. $\omega(\vec{u}, \vec{v}) = \vec{F} \cdot (\vec{u} \times \vec{v})$.

**6)** *3-form (3D)*: 부피 적분의 자연스러운 객체. $\omega = f\, dx \wedge dy \wedge dz$.

**7)** *미분형식의 쐐기곱*: $\wedge: \Omega^k \times \Omega^l \to \Omega^{k+l}$. 함수 계수는 곱셈, 1-form 들은 외대수 규칙.

**8)** *등급화 가환성*: $\omega \wedge \eta = (-1)^{kl}\, \eta \wedge \omega$. 함수는 항상 교환적.

**9)** *$n$-form (top form)*: $n$ 차원 다양체에서 1차원 공간. *부피 적분의 자연스러운 객체* — 자동으로 방향 정보 포함.

**10)** *물리적 자연스러움*: 1-form ↔ 곡선 적분, 2-form ↔ 면 플럭스, $n$-form ↔ 부피 적분. *적분 영역의 차원과 미분형식의 차수가 일치*.

다음 §8 에서 *외미분 $d$* — 미분형식들 사이의 *통합된 미분 연산자* — 를 정의한다. $d$ 가 *그라디언트, 발산, 회전* 등을 *하나의 연산자로 통합* 한다.
