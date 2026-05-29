+++
title = "(b) Partial derivative"
weight = 4
+++

---

### 1. 행렬 편미분 (성분별)

매개변수 $\tau^1, \ldots, \tau^n$에 의존하는 행렬 $\hat A(\tau^1, \ldots, \tau^n)$의 변화를 한 변수씩 따로 추적할 필요가 있다. 한 변수 $\tau^a$만 변화시키고 나머지 변수는 고정한 상태에서 미분한 것을 편미분이라 부른다. 매개변수가 $n$개이므로 편미분 행렬도 $n$개 존재한다.

성분별로 적으면 ($2 \times 2$ 예시이며 일반 크기로 그대로 일반화된다)

$$
\frac{\partial \hat A}{\partial \tau^a} = \begin{pmatrix} \dfrac{\partial a_{11}}{\partial \tau^a} & \dfrac{\partial a_{12}}{\partial \tau^a} \\ \dfrac{\partial a_{21}}{\partial \tau^a} & \dfrac{\partial a_{22}}{\partial \tau^a} \end{pmatrix}
$$

각 성분은 통상의 다변수 스칼라 편미분이며, 행렬 편미분은 성분별 스칼라 편미분의 모음일 뿐이다.

---

### 2. 기본 규칙

스칼라 미분에서 통용되는 규칙들이 행렬 편미분에서도 그대로 성립한다. 다만 행렬 곱셈이 비교환이므로 곱셈 규칙에서 인자 순서를 보존해야 한다.

**1) 선형성**

$$
\frac{\partial}{\partial \tau^a}(\alpha \hat A + \beta \hat B) = \alpha\,\frac{\partial \hat A}{\partial \tau^a} + \beta\,\frac{\partial \hat B}{\partial \tau^a}
$$

**2) 곱셈 규칙**

$$
\frac{\partial(\hat A\hat B)}{\partial \tau^a} = \frac{\partial \hat A}{\partial \tau^a}\,\hat B + \hat A\,\frac{\partial \hat B}{\partial \tau^a}
$$

두 인자 $\hat A$, $\hat B$의 좌우 배치가 우변에서도 그대로 유지된다.

**3) 역행렬 편미분**

$\hat A \hat A^{-1} = I$의 양변을 $\tau^a$로 미분하면

$$
\frac{\partial \hat A}{\partial \tau^a}\hat A^{-1} + \hat A\frac{\partial \hat A^{-1}}{\partial \tau^a} = 0
$$

이며, 좌측에 $\hat A^{-1}$를 곱해 정리하면

$$
\frac{\partial \hat A^{-1}}{\partial \tau^a} = -\hat A^{-1}\,\frac{\partial \hat A}{\partial \tau^a}\,\hat A^{-1}
$$

이 식도 좌우 순서가 고정되어 있다.

---

### 3. 혼합 편미분과 클레로 정리

두 변수에 대한 편미분을 차례로 수행한 것이 혼합 편미분이다.

$$
\frac{\partial^2 \hat A}{\partial \tau^a \partial \tau^b} = \frac{\partial}{\partial \tau^a}\!\left(\frac{\partial \hat A}{\partial \tau^b}\right)
$$

$\hat A$가 충분히 매끄러우면 ($C^2$ 이상) *클레로 (Clairaut/Schwarz)* 정리에 의해 미분 순서를 교환할 수 있다.

$$
\frac{\partial^2 \hat A}{\partial \tau^a \partial \tau^b} = \frac{\partial^2 \hat A}{\partial \tau^b \partial \tau^a}
$$

이는 각 성분 $a_{ij}(\tau)$에 표준 스칼라 클레로를 적용한 결과를 행렬 형태로 묶은 것이다. 이것은 미분 작용의 순서에 관한 것이며 **연산자 곱** 의 순서와 혼동하면 안 된다. $\hat A\hat B = \hat B\hat A$를 전혀 보장하지 않는다.

$$
\left[\frac{\partial A}{\partial \tau^a},\, \frac{\partial A}{\partial \tau^b}\right] \neq 0
$$

example)

이 대수적 특성을 증명하기 위해 파울리 행렬로 구성된 2준위 매개변수 연산자를 예시로 든다.

$$
\sigma_x = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}, \quad \sigma_y = \begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix}, \quad \sigma_z = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}
$$

$$
A(\tau^1, \tau^2) = \tau^1 \sigma_z + \tau^2 \sigma_x = \begin{pmatrix} \tau^1 & \tau^2 \\ \tau^2 & -\tau^1 \end{pmatrix}
$$

기준점 $(\tau^1, \tau^2) = (1, 0)$에서 연산자를 평가하면 $A(1, 0) = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}$이 된다. 특성 방정식 $\det(A - \lambda I) = \lambda^2 - 1 = 0$을 풀면 두 개의 비축퇴 고유값 $\lambda_+ = 1$과 $\lambda_- = -1$을 얻는다. 이에 대응하는 정규화된 고유벡터는 대수적 연산을 통해 다음과 같이 유일하게 결정된다.

$$
|v_+\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix}, \quad |v_-\rangle = \begin{pmatrix} 0 \\ 1 \end{pmatrix}
$$

각 매개변수 방향에 대한 연산자의 1계 편미분 작용소는 다음과 같다.

$$
\frac{\partial A}{\partial \tau^1} = \sigma_z = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}, \qquad \frac{\partial A}{\partial \tau^2} = \sigma_x = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}
$$

헬만-파인만 정리를 적용하여 $\tau^1$ 방향의 고유값 편미분을 계산하면 다음과 같다.

$$
\frac{\partial \lambda_+}{\partial \tau^1} = \langle v_+ | \frac{\partial A}{\partial \tau^1} | v_+ \rangle = \begin{pmatrix} 1 & 0 \end{pmatrix} \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix} \begin{pmatrix} 1 \\ 0 \end{pmatrix} = 1
$$

반면 $\tau^2$ 방향의 교란은 비대각 성분으로만 작용하므로 고유값의 1차 변화율은 소거된다.

$$
\frac{\partial \lambda_+}{\partial \tau^2} = \langle v_+ | \frac{\partial A}{\partial \tau^2} | v_+ \rangle = \begin{pmatrix} 1 & 0 \end{pmatrix} \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 1 \\ 0 \end{pmatrix} = 0
$$

섭동 공식을 통해 $\tau^2$ 방향에 의한 켓 고유벡터의 1차 회전 보정항을 계산한다. 자기 자신으로의 투영 성분을 제외한 비대각 합산에 의해 다음 행렬 연산이 도출된다.

$$
\frac{\partial |v_+\rangle}{\partial \tau^2} = \frac{\langle v_- | \sigma_x | v_+ \rangle}{\lambda_+ - \lambda_-} |v_-\rangle = \frac{\begin{pmatrix} 0 & 1 \end{pmatrix} \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 1 \\ 0 \end{pmatrix}}{1 - (-1)} \begin{pmatrix} 0 \\ 1 \end{pmatrix} = \frac{1}{2} \begin{pmatrix} 0 \\ 1 \end{pmatrix}
$$

이는 $\tau^2$ 방향의 미소 변화가 고유상태를 $|v_-\rangle$ 기저 방향으로 회전시킴을 정량적으로 증명한다.

마지막으로 두 교란 연산자의 교환자를 행렬 곱셈을 통해 계산한다.

$$
\left[\frac{\partial A}{\partial \tau^1},\, \frac{\partial A}{\partial \tau^2}\right] = \sigma_z \sigma_x - \sigma_x \sigma_z = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}\begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix} - \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}\begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}
$$

$$
= \begin{pmatrix} 0 & 1 \\ -1 & 0 \end{pmatrix} - \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} = \begin{pmatrix} 0 & 2 \\ -2 & 0 \end{pmatrix} = 2i\begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix} = 2i\sigma_y
$$

계산 결과가 0행렬이 아니므로 두 미분 작용소는 교환되지 않는다. 미분 작용의 교환성(클레로 정리)과 연산자 곱의 비교환성이 공존하는 이 대수적 비동치성은 후속 장의 리 괄호 표상 체계를 구성하는 근본적인 수학적 토대가 된다.

---

### 4. 다변수 테일러 전개

매끄러운 행렬값 함수 $\hat g(\tau^1, \ldots, \tau^n)$이 원점에서 $\hat g(0) = I$를 만족한다고 하자. 단위원 근방의 임의의 $\hat g(\tau)$를 1차/2차 항까지 분석하려면 테일러 전개가 필요하다.

성분별 스칼라 테일러를 행렬 전체에 적용하면

$$
\hat g(\tau) = I + \sum_a \tau^a\, \hat X_a + \frac{1}{2}\sum_{a,b}\tau^a\tau^b\, \hat X_{ab} + \frac{1}{3!}\sum_{a,b,c}\tau^a\tau^b\tau^c\, \hat X_{abc} + O(\tau^4)
$$

여기서 1차 계수와 2차 계수는

$$
\hat X_a \equiv \left.\frac{\partial \hat g}{\partial \tau^a}\right|_{\tau=0}, \qquad \hat X_{ab} \equiv \left.\frac{\partial^2 \hat g}{\partial \tau^a \partial \tau^b}\right|_{\tau=0}
$$

으로 정의되는 행렬들이다. $\hat X_a$를 *생성자* (generator), $\hat X_{ab}$를 *2차 미분 계수*라 부른다. 클레로 정리에 의해 $\hat X_{ab} = \hat X_{ba}$이며, 지표 교환에 대해 대칭이다.

**주의**: 일반적으로 $\hat X_{ab} \neq \hat X_a \hat X_b$이다. $\hat X_{ab}$는 함수 $\hat g$의 2차 편미분으로부터 정의되는 행렬이고 $\hat X_a \hat X_b$는 두 생성자의 행렬 곱이며, 둘 사이의 관계는 매개변수화 $\hat g(\tau)$의 구체적 형태에 의존한다. 특수 경우 ($\hat g = \exp$)에서 이 관계를 아래에서 다룬다.

---

### 5. exponential 의 2차 미분 항

$$\hat g(\tau) = \exp\bigl(\sum_a \tau^a \hat X_a\bigr)$$

지수 사상으로 매개변수화한 특수 경우에서 $\hat X_{ab}$가 생성자들 $\hat X_a, \hat X_b$로 어떻게 표현되는지 계산할 수 있다.

$$
\hat g(\tau) = \exp\left(\sum_a \tau^a \hat X_a\right)
$$

$\hat Y \equiv \sum_a \tau^a \hat X_a$로 두고 지수 함수의 테일러 급수 $\exp(\hat Y) = I + \hat Y + \tfrac{1}{2}\hat Y^2 + O(\hat Y^3)$를 적용한다. $\hat Y^2$를 전개하면

$$
\hat Y^2 = \left(\sum_a \tau^a \hat X_a\right)\!\left(\sum_b \tau^b \hat X_b\right) = \sum_{a,b}\tau^a\tau^b\, \hat X_a \hat X_b
$$

스칼라 $\tau^a$는 자유롭게 위치를 옮길 수 있으나, 행렬 $\hat X_a$는 비교환이므로 곱 $\hat X_a \hat X_b$의 순서를 보존해야 한다. 따라서 지수 사상의 2차까지의 전개는

$$
\hat g(\tau) = I + \sum_a \tau^a \hat X_a + \frac{1}{2}\sum_{a,b}\tau^a\tau^b\, \hat X_a \hat X_b + O(\tau^3)
$$

이를 §4의 일반 형식과 비교한다.

$$
\frac{1}{2}\sum_{a,b}\tau^a\tau^b\, \hat X_{ab} = \frac{1}{2}\sum_{a,b}\tau^a\tau^b\, \hat X_a \hat X_b
$$

좌변의 $\hat X_{ab}$는 $a, b$에 대해 대칭이지만 우변의 $\hat X_a \hat X_b$는 일반적으로 비대칭이다. 인덱스에 대해 비교해 본다.

$$
\hat{X}_{ab}+\hat{X}_{ba}=\hat{X}_{a}\hat{X}_{b}+\hat{X}_{b}\hat{X}_{a}\implies 2\hat{X}_{ab}=\hat{X}_{a}\hat{X}_{b}+\hat{X}_{b}\hat{X}_{a}
$$

따라서.

$$
\hat X_{ab} = \frac{1}{2}\bigl(\hat X_a \hat X_b + \hat X_b \hat X_a\bigr)=\frac{1}{2}\{\hat X_a, \hat X_b\}
$$

이며, *반교환자* $\{\hat X_a, \hat X_b\} \equiv \hat X_a \hat X_b + \hat X_b \hat X_a$의 절반과 같다.

---

### 6. 방향 미분

**1) 동기**

다변수 함수 $\hat{g}(\tau^1, \ldots, \tau^n)$을 그대로 미분하려면 다변수 도구가 필요하다. 방향 미분을 쉽게 이해하기 위해, 다음의 예를 생각할 수 있다. $f(x, y) = x^2 + y^2$의 점 $(1, 1)$에서 "북동쪽 ($x, y$ 둘 다 증가) 으로 움직일 때 $f$가 얼마나 빨리 변하나" 라는 질문. 편미분 $\partial f/\partial x = 2$, $\partial f/\partial y = 2$ 각각만으로는 직접 답이 안 나오고, 둘을 합치는 방법(방향 미분) 이 필요하다.

**2) 정의**

출발점 $\tau_0 \in \mathbb{R}^n$과 방향 벡터 $v = (v^1, \ldots, v^n) \in \mathbb{R}^n$이 주어졌을 때, 방향 벡터가 만드는 직선 위로 $\hat{g}$를 제한하면 $t$의 단일변수 행렬 함수 $\hat{g}(\tau_0 + tv)$가 나온다. 이 단일변수 함수의 $t = 0$에서의 미분이 **$\tau_0$에서 방향 $v$의 방향 미분** 이다.

$$
D_v \hat{g}\bigg|_{\tau_0} = \sum_a v^a \, \frac{\partial \hat{g}}{\partial \tau^a}\bigg|_{\tau_0}
$$

$\tau_0$는 매개변수 공간의 **임의의 점**이다. 한 점에 고정된 개념이 아니라 모든 점에서 정의되는 양이며, 점이 바뀌면 값도 바뀐다. ($t=0$은 "출발 순간"을 의미할 뿐, 출발점 자체와 다른 개념이다. 단일변수 미분에서 한 점의 기울기를 측정할 때 그 점을 매개변수 0으로 잡는 관습일 뿐이며 출발점은 자유롭게 선택할 수 있다.

proof)

$v$ 방향으로 움직일 때, 각 매개변수의 변화는 아래와 같이 쓸 수 있다.

$$
\tau^a(t) = \tau_0^a + tv^a,\implies\frac{d\tau^a}{dt} = v^a
$$

미소 $t$의 변화에 대해, 연쇄법칙의 일반 형태는 다음과 같다.

$$
\frac{d}{dt}\hat{g}(\tau^1(t),\cdots,\tau^n(t))
=\sum_a\frac{\partial\hat{g}}{\partial\tau^a}\cdot\frac{d\tau^a}{dt}
=\sum_a\frac{\partial\hat{g}}{\partial\tau^a}\cdot v^a
$$

**3) 항등원 ($\tau_0 = 0$) 에서의 특별한 의미**

방향 미분 자체는 임의의 $\tau_0$에서 정의되지만, 리 군 매개변수화 $\hat{g}(0) = \hat{I}$ 에서는 항등원이 $\tau_0 = 0$에 해당하며 그 점의 편미분에 별도 이름이 붙는다.

$$
\hat{X}_a \;\equiv\; \frac{\partial \hat{g}}{\partial \tau^a}\bigg|_{\tau=0}
$$

이를 **생성자** (generator) 라 부른다. 항등원에서의 방향 미분은

$$
D_v \hat{g}\bigg|_{0} = \sum_a v^a \hat{X}_a
$$

가 되어 **모두 생성자의 일차결합**으로 표현된다. $v$를 임의로 바꿔도 결합 계수만 달라질 뿐 같은 $\{\hat{X}_a\}$ 위에서 움직인다. 따라서 **항등원에서 출발할 수 있는 모든 1차 방향** 의 집합은 정확히 $\operatorname{span}\{\hat{X}_1, \ldots, \hat{X}_n\}$이며, 이 벡터 공간을 **접공간 / 리 대수** 라 부른다. 일반점 $\tau_0 \neq 0$에서는 그 점의 편미분이 생성자가 아니므로 이런 특별한 닫힌 구조가 자동으로 따라오지 않는다. 항등원이 특별한 이유가 여기에 있다. 리 대수 챕터에서 다시 다룬다.

**4) 기하학적 그림**

$\hat{g}(\tau)$는 행렬 공간 안에 곡면을 그린다. 매개변수 공간의 한 점 $\tau_0$가 행렬 공간의 한 점 $\hat{g}(\tau_0)$에 대응하고, 방향 $v$가 그 점에서 출발하는 **접선 벡터** $D_v \hat{g}|_{\tau_0}$에 대응한다. 같은 점 $\hat{g}(\tau_0)$에서 $v$를 바꾸면 서로 다른 접선 벡터가 나오고, 모든 접선 벡터의 집합이 그 점의 **접공간**이다. 항등원의 접공간이 곧 리 대수.

---

### 7. example: SO(3) 다변수 미분

$SO(3)$의 지수 사상 매개변수화

$$
\hat g(\tau^1, \tau^2, \tau^3) = \exp\!\left(\tau^1 \hat L_x + \tau^2 \hat L_y + \tau^3 \hat L_z\right)
$$

를 사용한다. 벡터 $(\tau^1, \tau^2, \tau^3)$는 회전축 $\times$ 회전각도를 나타내며, $\tau = 0$에서 $\hat g(0) = \exp(0) = I$이다. 표준 생성자는

$$
\hat L_x = \begin{pmatrix} 0 & 0 & 0 \\ 0 & 0 & -1 \\ 0 & 1 & 0 \end{pmatrix}, \qquad \hat L_y = \begin{pmatrix} 0 & 0 & 1 \\ 0 & 0 & 0 \\ -1 & 0 & 0 \end{pmatrix}, \qquad \hat L_z = \begin{pmatrix} 0 & -1 & 0 \\ 1 & 0 & 0 \\ 0 & 0 & 0 \end{pmatrix}
$$

이며 모두 반대칭 ($\mathfrak{so}(3)$의 원소).

**1) 1차 편미분**

$$
\left.\frac{\partial \hat g}{\partial \tau^a}\right|_{\tau=0} = \hat L_a \qquad (a = x, y, z)
$$

**2) 방향 미분**

임의의 방향 $v = (v^1, v^2, v^3)$으로의 미분은

$$
\left.\frac{d}{dt}\hat g(tv)\right|_{t=0} = v^1 \hat L_x + v^2 \hat L_y + v^3 \hat L_z
$$

이며 축 $v$ 주위의 무한소 회전 생성자이다. 회전축 방향이 $v/|v|$이고 회전 속도가 $|v|$이다.

**3) 2차 미분 계수의 일반 공식**

§5의 결과를 그대로 적용하면

$$
\hat X_{ab} = \frac{1}{2}\bigl(\hat L_a \hat L_b + \hat L_b \hat L_a\bigr)
$$

**4) $\hat X_{xy}$의 계산**

행렬 곱 $\hat L_x \hat L_y$와 $\hat L_y \hat L_x$를 직접 계산하면

$$
\hat L_x \hat L_y = \begin{pmatrix} 0 & 0 & 0 \\ 0 & 0 & -1 \\ 0 & 1 & 0 \end{pmatrix}\!\!\begin{pmatrix} 0 & 0 & 1 \\ 0 & 0 & 0 \\ -1 & 0 & 0 \end{pmatrix} = \begin{pmatrix} 0 & 0 & 0 \\ 1 & 0 & 0 \\ 0 & 0 & 0 \end{pmatrix}
$$

$$
\hat L_y \hat L_x = \begin{pmatrix} 0 & 0 & 1 \\ 0 & 0 & 0 \\ -1 & 0 & 0 \end{pmatrix}\!\!\begin{pmatrix} 0 & 0 & 0 \\ 0 & 0 & -1 \\ 0 & 1 & 0 \end{pmatrix} = \begin{pmatrix} 0 & 1 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 0 \end{pmatrix}
$$

따라서

$$
\hat X_{xy} = \frac{1}{2}\bigl(\hat L_x \hat L_y + \hat L_y \hat L_x\bigr) = \frac{1}{2}\begin{pmatrix} 0 & 1 & 0 \\ 1 & 0 & 0 \\ 0 & 0 & 0 \end{pmatrix}
$$

이 행렬은 *대칭* (클레로의 결과)이며, *반대칭 행렬들의 공간* $\mathfrak{so}(3)$에는 속하지 않는다. 즉 $\hat X_{ab}$는 일반적으로 리 대수의 원소가 아니다. $\hat X_a$와 $\hat X_{ab}$가 서로 다른 공간에 사는 별개의 행렬이라는 것이 이 예에서 명확히 드러난다.

**5) 리 괄호와의 관계**

같은 두 곱의 차를 계산하면

$$
[\hat L_x, \hat L_y] = \hat L_x \hat L_y - \hat L_y \hat L_x = \begin{pmatrix} 0 & 0 & 0 \\ 1 & 0 & 0 \\ 0 & 0 & 0 \end{pmatrix} - \begin{pmatrix} 0 & 1 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 0 \end{pmatrix} = \begin{pmatrix} 0 & -1 & 0 \\ 1 & 0 & 0 \\ 0 & 0 & 0 \end{pmatrix} = \hat L_z
$$

즉 $[\hat L_x, \hat L_y] = \hat L_z$ ($SO(3)$의 정의 관계). 이 부분이 §14에서 다룰 리 대수 구조이다.

따라서 행렬 곱 $\hat L_x \hat L_y$는 대칭 부분과 반대칭 부분으로 분해된다.

$$
\hat L_x \hat L_y = \underbrace{\hat X_{xy}}_{\text{대칭}} + \underbrace{\frac{1}{2}[\hat L_x, \hat L_y]}_{\text{반대칭}} = \frac{1}{2}\begin{pmatrix} 0 & 1 & 0 \\ 1 & 0 & 0 \\ 0 & 0 & 0 \end{pmatrix} + \frac{1}{2}\begin{pmatrix} 0 & -1 & 0 \\ 1 & 0 & 0 \\ 0 & 0 & 0 \end{pmatrix} = \begin{pmatrix} 0 & 0 & 0 \\ 1 & 0 & 0 \\ 0 & 0 & 0 \end{pmatrix}
$$

대칭 부분 $\hat X_{ab}$는 매개변수의 2차 변화 (테일러 2차 항)에 기여하고, 반대칭 부분 $\tfrac{1}{2}[\hat L_a, \hat L_b]$는 군 곱셈의 비교환성 (BCH 2차 보정)에서 살아남는다. 동일한 행렬 곱 $\hat L_a \hat L_b$가 두 역할로 갈라진다는 것이 핵심이다.

---