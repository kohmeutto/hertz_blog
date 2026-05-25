+++
title = "(b) Generator"
weight = 4
+++

---

### 1. 생성자(Generator): 변화의 씨앗

리 군 $\hat{S}(\tau)$이 거대한 나무라면, 생성자 $\hat{G}$는 그 나무의 DNA다. 나무가 아무리 크고 복잡하게 자라나도, 그 근본적인 생장 규칙은 DNA 안에 모두 담겨 있다. 거창한 리 군 전체를 들고 다니는 대신, 가장 미세한 성질(생성자) 하나만 파악하면 모든 미래를 예측할 수 있다.

이 생성자는 **모든 리군에 대해 항등원에서 연산자의 미분으로 정의** 된다.

직관적 이해를 위해, "조이스틱은 항상 중앙에 있다"를 리 군의 움직임을 비디오 게임의 캐릭터 조작에 비유해 보자.

- 항등원($\hat{I}$): 조이스틱의 중앙(중립) 위치.
- 생성자($\hat{G}$): 조이스틱을 특정 방향으로 '탁' 튕기는 입력.
- 현재 상태($\hat{S}(\tau)$): 캐릭터가 맵의 저 멀리($\tau=100$) 가 있는 상태.캐릭터가 맵의 어디에 있든(비가환의 복잡한 위치), 

우리가 조작하는 **조이스틱은 항상 내 손안의 중앙(항등원)** 에 있다."캐릭터가 늪지대(비가환 영역)에 있다고 해서, 내가 늪지대에 가서 조종하는 게 아니다. 나는 여전히 안전한 방(항등원)에서 조이스틱을 움직이면, 그 명령이 복사되어(Translation) 캐릭터에게 전달되는 것이다."

---

### 2. 왜 하필 항등원($\tau=0$)인가

많은 사람들이 궁금해한다. $\tau=10$이나 $\tau=100$ 지점에서의 기울기를 구하면 안 되는가. 결론부터 말하면 안 된다. 수학적으로 생성자는 반드시 항등원($\hat{I}$)의 접공간(Tangent Space) 에서 정의되어야 한다.

**(1) 군의 정의: "모든 점은 원점의 복제본이다"**

리 군의 가장 강력한 성질은 **균질성(Homogeneity)** 이다. 우주 어디를 가나 물리 법칙이 똑같은 것처럼, 리 군 위의 어떤 점 $\hat{S}(\tau)$도 결국은 원점의 성질을 평행 이동시킨 것에 불과하다.

$$
\hat{S}(0) = \hat{I}
$$

$$
\hat{S}(\tau + \Delta \tau) = \hat{S}(\tau) \cdot \hat{S}(\Delta \tau)
$$

즉, 현재 위치 $\hat{S}(\tau)$에서의 변화는 **"원점 근처의 아주 작은 변화 $\hat{S}(\Delta \tau)$"** 를 현재 값에 곱해서 만들어진다. 따라서 우리는 원본 규칙이 있는 항등원만 연구하면 된다.

**(2) 수학적 증명: 미분방정식의 유도**

임의의 점 $\tau$에서의 변화율을 구해보면, 필연적으로 $\tau=0$ 항이 튀어나온다.

$$
\frac{d}{d\tau}\hat{S}(\tau)
=\lim_{\Delta \tau \to 0} \frac{\hat{S}(\tau+\Delta\tau) -\hat{S}(\tau)}{\Delta \tau}
=\underbrace{\lim_{\Delta \tau \to 0} \frac{\hat{S}(\Delta\tau)-\hat{I}}{\Delta\tau}}_{\text{Generator } \hat{G}}\cdot\hat{S}(\tau)
$$

$$
=\underbrace{\lim_{\Delta \tau \to 0} \frac{\hat{S}(\Delta\tau)-\hat{S}(0)}{\Delta\tau}}_{\text{Generator } \hat{G}}\cdot\hat{S}(\tau)
=\underbrace{\frac{d}{d\tau}\hat{S}(\tau) \bigg|_{\tau=0}}_{\text{Generator } \hat{G}}\cdot\hat{S}(\tau)
$$

$$
=\hat{G}\cdot \hat{S}(\tau)
$$

이 극한값은 정확히 $\tau=0$(항등원)에서의 미분계수다. 즉, 원점에서의 기울기($\hat{G}$)를 모르면, 리 군 위의 그 어떤 점에서의 변화도 설명할 수 없다.

---

### 3. 생성자의 해석 1: "순간 변화율과 미소 성분"

생성자의 첫 번째 정체는 **"아무것도 안 한 상태에서의 튀어 나가려는 속도"** 다.

**(1) 미분의 정의: 찰나의 움직임**

$$
\hat{G} := \frac{d}{d\tau}\hat{S}(\tau) \bigg|_{\tau=0}
$$

물리적 예시로 회전 운동에서 $\hat{S}(\tau)$가 회전 행렬(위치)이라면, $\hat{G}$는 각속도(Angular Velocity) 행렬이다.

**(2) 미소 성분 (Infinitesimal Element)**

이를 테일러 급수로 아주 짧은 시간($\Delta \tau$)에 대해 전개하면, 리 군의 가장 기본적인 미소 조각이 드러난다.

$$
\hat{S}(\Delta \tau) \approx \hat{I} + \Delta \tau \cdot \hat{G}
$$

즉, 거대한 리 군 변환은 **"제자리($I$) + 아주 작은 변화($G$)"** 를 무한히 누적시킨 결과다.

---

### 4. 생성자의 해석 2: "미분 연산자의 고유값"

생성자의 두 번째 정체는 "변하지 않는 규칙(Invariant)", 즉 **고유값(Eigenvalue)** 으로서의 성질이다. 앞서 유도한 미분방정식을 다시 보자.

$$
\underbrace{\frac{d}{d\tau}}_{\text{Operator}} \hat{S}(\tau) = \underbrace{\hat{G}}_{\text{Eigenvalue}} \cdot \underbrace{\hat{S}(\tau)}_{\text{Eigenfunction}}
$$

- 함수 $\hat{S}(\tau)$: 시간이 지남에 따라 계속 변한다. (현상, Phenomenon)
- 생성자 $\hat{G}$: 시간 $\tau$에 상관없이 영원히 변하지 않는 상수다. (본질, Essence) 이것은 생성자가 단순한 기울기가 아니라, **시스템 전체를 관통하며 변하지 않는 고유한 성질(DNA)** 임을 의미한다.

---

### 5. 생성자의 해석 3: "접공간의 기저 (Basis)"
   
생성자의 세 번째 정체는 다변수(Multivariable) 상황에서 비로소 드러난다. 우리가 3차원 공간에서 $x, y, z$축을 따로 움직일 수 있듯이, 리 군의 움직임도 여러 개의 독립적인 파라미터들로 구성된다.

**(1) 다변수 함수로서의 리 군**

리 군 연산자 $\hat{S}$가 $N$개의 변수 $\boldsymbol{\tau} = (\tau_1, \tau_2, \dots, \tau_N)$에 의해 움직인다고 가정해 보자. (예: 3차원 회전이라면 $\tau_1, \tau_2, \tau_3$는 롤, 피치, 요 각도일 수 있다.)

$$
\hat{S}(\tau_1, \tau_2, \dots, \tau_N)
$$

**(2) 수학적 증명: 연쇄 법칙과 전미분 (Chain Rule)**

이 복잡한 다변수 함수가 원점($\boldsymbol{\tau}=0$)에서 움직이기 시작할 때의 **"총 변화율(Total Generator)"** 을 알고 싶다. 이를 위해 가상의 시간 $t$를 도입하여, 파라미터들이 $\boldsymbol{\tau}(t)$ 궤적을 그리며 움직인다고 가정하자.

원점($t=0$)에서의 변화율은 **다변수 연쇄 법칙(Multivariable Chain Rule)** 에 의해 다음과 같이 분해된다.

$$
\hat{S}(\{\tau_i(t)\})
:=\hat{S}(\tau_1(t), \tau_2(t), \dots, \tau_N(t))
$$

$$
\frac{d}{dt}\hat{S}(\{\tau_i(t)\})
=\hat{G}_{total}\cdot\hat{S}(\{\tau_i(t)\})
$$

$$
\hat{G}_{total}
=\frac{d}{dt} \hat{S}(\{\tau_i(t)\}) \bigg|_{\tau_i=0} 
=\sum_{i=1}^{N} \left( \frac{\partial \hat{S}}{\partial \tau_i} \bigg|_{\tau_i=0} \right) \cdot \frac{d\tau_i}{dt}
$$

이 식을 뜯어보면 놀라운 구조가 보인다.

- $\cfrac{\partial \hat{S}}{\partial \tau_i}|_{\tau=0}$ (편미분): 다른 변수들은 다 고정하고, 오직 $i$번째 변수만 건드렸을 때의 변화율이다. 이것이 바로 **$i$번째 기저 생성자 $\hat{G}_i$** 의 정의다. 예로 $x$축으로만 회전하려는 성질 ($\hat{G}_x$)
- $\cfrac{d\tau_i}{dt}$ (가중치): 그 방향으로 얼마나 세게 가속 페달을 밟았는지를 나타내는 스칼라 값($\omega_i$)이다.

**(3) 선형 결합의 필연성**

위의 연쇄 법칙에 의해, 총 생성자 $\hat{G}_{total}$은 필연적으로 **기저 생성자들의 선형 결합(Linear Combination)** 이 된다.

$$
\hat{G}_{total} = \omega_1 \hat{G}_1 + \omega_2 \hat{G}_2 + \cdots + \omega_N \hat{G}_N
$$

- 비 가환 리 군($\hat{S}$): 굽어 있어서 단순 덧셈이 안 된다. ($R_x \cdot R_y \neq R_{x+y}$)
- 리 대수($\hat{G}$): 미분(접평면)의 세계이므로, 전미분 원리에 의해 각 성분들이 벡터처럼 더해진다. ($\vec{\omega} = \omega_x \hat{i} + \omega_y \hat{j}$) 이것이 바로 생성자를 **"리 대수 공간을 구성하는 기저(Basis)"** 라고 부르는 진짜 이유다.

---

### 6. 중요특성1: 가환군의 생성자들은 항상 교환 가능

$\hat{S}$가 가환군(Abelian Group)이라고 가정하에,

$$
[\hat{G}_1, \hat{G}_2] = 0
$$

proof)

$\hat{S}$가 가환군(Abelian Group)이라고 가정해 보자. 그러면 임의의 두 원소 $\hat{S}_1, \hat{S}_2$에 대해 순서를 바꿔도 결과가 같아야 한다.

$$
\hat{S}_1 \hat{S}_2 = \hat{S}_2 \hat{S}_1
$$

이 $\hat{S}$들을 아주 작은 움직임(무한소, Infinitesimal)이라고 생각하고 생성자 $\hat{G}$로 표현해 보자. ($\epsilon$은 아주 작은 실수)

$$
\hat{S}_1 \approx \hat{I} + \epsilon \hat{G}_1,\quad
\hat{S}_2 \approx I + \epsilon \hat{G}_2
$$

이제 그룹의 가환 조건식에 대입해 본다.

좌변 ($\hat{S}_1 \hat{S}_2$): 

$$
(\hat{I} + \epsilon \hat{G}_1)(I + \epsilon \hat{G}_2) = I + \epsilon(\hat{G}_1 + \hat{G}_2) + \epsilon^2 (\hat{G}_1 \hat{G}_2)
$$

우변 ($\hat{S}_2 \hat{S}_1$):

$$
(I + \epsilon \hat{G}_2)(I + \epsilon \hat{G}_1) = I + \epsilon(\hat{G}_2 + \hat{G}_1) + \epsilon^2 (\hat{G}_2 \hat{G}_1)
$$

좌변과 우변이 같아야 하므로, 1차항($\epsilon$)과 상수항($\hat{I}$)을 소거하고 남은 2차항($\epsilon^2$)끼리 비교하면 다음 결론이 나온다.

$$
\hat{G}_1 \hat{G}_2 = \hat{G}_2 \hat{G}_1 \quad \Longleftrightarrow \quad [\hat{G}_1, \hat{G}_2] = 0
$$

---

### 7. 중요특성2: $\hat{S}$와 $\hat{G}$는 항상 교환 가능"

가환/비가환에 관계 없이, 아래는 항상 만족한다.

$$
[\hat{S},\hat{G}]=0
$$

위 식의 물리적 의미는 매우 중요하다.

- 회전해도($\hat{S}$) 회전축($\hat{G}$)은  변하지 않는다 (불변성)
- $\hat{S}$와 $\hat{G}$는 동시 고유벡터를 가진다.

proof)

$$
\hat{S}(\tau) \approx \hat{I} + \tau\hat{G}
$$

$$
\hat{S}\hat{G}\approx\hat{I}\hat{G} + \tau\hat{G}\hat{G}
=\hat{G}+\tau\hat{G}^2
$$

따라서, 교환 가능하다.

---
