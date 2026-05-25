+++
title = "(b) MV matrix"
weight = 4
+++

### 1. 동기

§5에서 1매개변수 행렬 $A(\tau)$의 미분을 다뤘다. §10에서 다변수 매개변수화 $g(\tau^1, \ldots, \tau^n)$을 소개했고, 각 방향의 편미분이 생성자 $X_a$를 준다는 것까지 봤다.

이 장에서는 §5의 *다변수 판* 을 정리한다 — 편미분의 정의, 기본 규칙, 혼합 편미분 (클레로 정리), 다변수 테일러 전개, 방향 미분. 이 도구들이 §12, §13, 그리고 §14의 리 괄호 정의에 직접 필요하다.

### 2. 편미분 (성분별)

**1)** 행렬 $A(\tau^1, \ldots, \tau^n)$ 의 *편미분*은 한 변수만 변화시키면서 미분한 것이다.

$$\frac{\partial A}{\partial \tau^a} = \begin{pmatrix} \dfrac{\partial a_{11}}{\partial \tau^a} & \dfrac{\partial a_{12}}{\partial \tau^a} \\ \dfrac{\partial a_{21}}{\partial \tau^a} & \dfrac{\partial a_{22}}{\partial \tau^a} \end{pmatrix}$$

($2 \times 2$의 예지만 일반 크기에 그대로 일반화된다.)

**2)** §5와 정확히 같은 정의 — *각 성분을 편미분*. 결과도 같은 크기의 행렬.

**3)** 매개변수 $n$ 개에 대응되는 $n$ 개의 편미분 행렬이 있다.

### 3. 기본 규칙

§5의 모든 규칙이 편미분으로 그대로 옮겨진다 (각 매개변수 $\tau^a$ 에 독립적으로 적용).

**1)** *선형성*:

$$\frac{\partial}{\partial \tau^a}(\alpha A + \beta B) = \alpha\, \frac{\partial A}{\partial \tau^a} + \beta\, \frac{\partial B}{\partial \tau^a}$$

**2)** *곱셈 규칙* (순서 조심):

$$\frac{\partial(AB)}{\partial \tau^a} = \frac{\partial A}{\partial \tau^a}\, B + A\, \frac{\partial B}{\partial \tau^a}$$

행렬 곱셈이 교환적이지 않으므로 순서를 보존해야 한다.

**3)** *역행렬 편미분*:

$$\frac{\partial (A^{-1})}{\partial \tau^a} = -A^{-1}\, \frac{\partial A}{\partial \tau^a}\, A^{-1}$$

### 4. 혼합 편미분과 클레로 정리

**1)** 두 번 편미분: $\dfrac{\partial^2 A}{\partial \tau^a \partial \tau^b}$.

**2)** *클레로 (Clairaut/Schwarz) 정리*: $A$ 가 매끄럽다면 ($C^2$ 이상) 미분 순서를 바꿔도 결과가 같다.

$$\frac{\partial^2 A}{\partial \tau^a \partial \tau^b} = \frac{\partial^2 A}{\partial \tau^b \partial \tau^a}$$

**3)** 즉 *미분의 순서는 교환 가능*하다. 보통의 다변수 미적분에서 잘 알려진 사실을 각 성분에 적용한 것에 불과하다.

**4)** *주의 — 미분 순서 ≠ 군 곱셈 순서*: 클레로는 *미분 작용의 순서*에 대한 진술이다. 한편 *군 곱셈*의 순서는 여전히 보존되어야 한다. $\exp(\tau X)\exp(\sigma Y)$ 와 $\exp(\sigma Y)\exp(\tau X)$ 는 일반적으로 다르다 (§10.6). 이 두 가지가 어떻게 양립하는지가 §14 리 괄호의 핵심.

### 5. 다변수 테일러 전개

**1)** 매끄러운 $g(\tau)$ 가 $g(0) = I$ 를 만족할 때, 단위원 근처에서의 전개:

$$g(\tau) = I + \sum_a \tau^a\, X_a + \frac{1}{2}\sum_{a,b} \tau^a \tau^b\, X_{ab} + O(\tau^3)$$

여기서:
- $X_a = \left.\dfrac{\partial g}{\partial \tau^a}\right|_{\tau=0}$ — 생성자 (§10)
- $X_{ab} = \left.\dfrac{\partial^2 g}{\partial \tau^a \partial \tau^b}\right|_{\tau=0}$ — 2차 미분 계수

**2)** 클레로에 의해 $X_{ab} = X_{ba}$ — *대칭* 계수다.

**3)** *주의*: $X_{ab}$ 는 일반적으로 *생성자의 곱* $X_a X_b$ 와 같지 않다. 매개변수화 $g$ 가 어떻게 정의됐는지에 따라 다르다.

**4)** *특수 경우* $g(\tau) = \exp\bigl(\sum_a \tau^a X_a\bigr)$ 라면, 지수 사상의 테일러 급수에서

$$g(\tau) = I + \tau^a X_a + \frac{1}{2}(\tau^a X_a)(\tau^b X_b) + \cdots = I + \tau^a X_a + \frac{1}{2}\tau^a \tau^b X_a X_b + \cdots$$

(아인슈타인 합 규약 사용.) 따라서 $X_{ab} = \dfrac{1}{2}(X_a X_b + X_b X_a)$ — *대칭화* 된 곱. 클레로의 $X_{ab} = X_{ba}$ 와 일치한다.

### 6. 방향 미분

**1)** 방향 벡터 $v = (v^1, \ldots, v^n) \in \mathbb{R}^n$ 이 주어졌을 때, 그 방향으로의 미분은

$$\left.\frac{d}{dt}g(tv)\right|_{t=0} = \sum_a v^a\, X_a$$

**2)** 즉 *모든 방향*의 미분이 *생성자들의 일차 결합*으로 표현된다.

**3)** 이는 *단위원에서의 모든 가능한 출발 방향*이 생성자 $X_1, \ldots, X_n$ 의 일차 결합으로 만들어짐을 의미한다.

**4)** 따라서 생성자들이 *벡터 공간*을 이룬다. 1매개변수 경우의 1차원 생성자 공간 (§9.7.6) 의 다변수 일반화. 이 벡터 공간이 §14 이후의 *접공간/리 대수* 의 토대.

### 7. example: $SO(3)$ 다변수 미분

**1)** $SO(3)$ 의 자연스러운 매개변수화 (지수 사상 이용):

$$g(\tau^1, \tau^2, \tau^3) = \exp(\tau^1 L_x + \tau^2 L_y + \tau^3 L_z)$$

벡터 $(\tau^1, \tau^2, \tau^3)$ 가 (회전축 × 회전각도) 를 나타낸다. $\tau = 0$ 에서 $g(0) = \exp(0) = I$.

**2)** 편미분 (테일러 1차 항):

$$\frac{\partial g}{\partial \tau^a}\bigg|_{\tau=0} = L_a \quad (a = x, y, z)$$

§10.5 의 세 생성자 $L_x, L_y, L_z$ 가 정확히 이 편미분.

**3)** 임의의 방향 $v = (v^1, v^2, v^3)$ 으로의 방향 미분:

$$\left.\frac{d}{dt}g(tv)\right|_{t=0} = v^1 L_x + v^2 L_y + v^3 L_z$$

이는 *축 $v$ 방향*의 무한소 회전 생성자. 회전축 방향이 $v / |v|$, 회전 속도가 $|v|$.

**4)** 2차 미분 계수 (위 매개변수화에서):

$$X_{ab} = \left.\frac{\partial^2 g}{\partial \tau^a \partial \tau^b}\right|_{\tau=0} = \frac{1}{2}(L_a L_b + L_b L_a)$$

(대칭화. §5.4 의 일반론과 일치.) 이 *대칭* 부분이 클레로로 보장된다. 한편 *반대칭* 부분 $\frac{1}{2}(L_a L_b - L_b L_a)$ 는 *리 괄호* $\frac{1}{2}[L_a, L_b]$ — 이는 매개변수화의 2차 미분에는 나타나지 않지만 군 곱셈의 비교환성에서 나타난다 (§14).

### 8. 정리

**1)** *편미분*은 한 매개변수만 미분 — 성분별 정의는 §5와 같다.

**2)** *기본 규칙*(선형성, 곱셈 규칙, 역행렬 미분) 모두 편미분으로 그대로 옮겨진다. 곱셈 규칙은 *순서 조심*.

**3)** *클레로 정리*: 매끄러운 $g$ 의 혼합 편미분은 *순서 교환 가능*. 이는 미분 순서에 대한 진술이지, 군 곱셈 순서에 대한 것이 아니다.

**4)** *다변수 테일러 전개*: 단위원 근처에서

$$g(\tau) = I + \tau^a X_a + \frac{1}{2}\tau^a \tau^b X_{ab} + O(\tau^3)$$

클레로에 의해 $X_{ab} = X_{ba}$.

**5)** *방향 미분*은 생성자들의 일차 결합. 따라서 *생성자 공간이 벡터 공간*이다.

**6)** 이 도구들이 §12 (스펙트럼 미분의 다변수 판), §13 (연속 스펙트럼), §14 (리 괄호) 의 토대가 된다.
