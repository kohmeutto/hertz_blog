+++
title = "(b) Generator II"
weight = 5
+++

---

### 1. 가환군의 생성자들은 항상 교환 가능

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

### 2. 어떤 연산자($\hat{S}$)와 그것을 만들어낸 생성자($\hat{G}$)는 항상 교환 가능"

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