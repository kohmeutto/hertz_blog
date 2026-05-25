+++
title = "(b) SV discrete spectrum"
weight = 2
+++

---

### 1. 일반 형태: 세 항 분해

**1)** 매개변수 $\tau$에 의존하는 행렬 $A(\tau)$의 스펙트럼 분해를 다음과 같이 쓴다.

$$A(\tau) = \sum_i \lambda_i(\tau)\, \vert v_i(\tau)\rangle\langle v^i(\tau)\vert$$

고유값 $\lambda_i(\tau)$와 고유벡터 $\vert v_i(\tau)\rangle$ 둘 다 $\tau$에 따라 변할 수 있다 (쌍대 기저 $\langle v^i(\tau)\vert$ 도 함께 변한다).

**2)** 곱셈 규칙(§5)을 세 인자에 모두 적용하면:

$$\frac{dA}{d\tau} = \sum_i \Big[\dot\lambda_i\, \vert v_i\rangle\langle v^i\vert + \lambda_i\, \vert\dot v_i\rangle\langle v^i\vert + \lambda_i\, \vert v_i\rangle\langle \dot v^i\vert\Big]$$

여기서 점은 $\tau$에 대한 미분이다 ($\dot\lambda_i = d\lambda_i/d\tau$ 등). 세 항의 의미:
- *고유값 변화* 항
- *켓 고유벡터 회전* 항
- *브라 고유벡터 회전* 항

**3)** 핵심: 미분이 *고유값*과 *고유벡터* 양쪽에 모두 작용한다.

---

### 2. 깔끔한 경우: 고유벡터가 고정

**1)** $\vert v_i\rangle$ 와 $\langle v^i\vert$ 가 $\tau$ 와 무관하면 ($\vert\dot v_i\rangle = 0$, $\langle\dot v^i\vert = 0$), 뒤의 두 항이 사라진다.

$$\frac{dA}{d\tau} = \sum_i \dot\lambda_i\, \vert v_i\rangle\langle v^i\vert$$

**2)** 이 식은 *함수 미적분의 미분에 해당하는* 구조다. §6에서 본 $f(A) = \sum_i f(\lambda_i)\vert v_i\rangle\langle v^i\vert$ 에서 스칼라 함수에 미분을 적용한 결과로 자연스럽게 해석된다.

**3)** 즉 고유벡터가 고정되면 행렬 미분은 *고유값에만* 미분을 적용하는 것과 동치다. 함수 미적분과 미분이 *같은 스펙트럼 분해 위에서* 깨끗하게 어울린다.

---

### 3. example: $\exp(\tau X)$의 미분

**1)** $X$ 가 $\tau$ 에 무관하고 대각화 가능할 때, $A(\tau) = \exp(\tau X)$ 를 스펙트럼 분해로 본다.

$X$의 스펙트럼 분해를 $X = \sum_i \mu_i\, \vert v_i\rangle\langle v^i\vert$ 로 쓰면, 함수 미적분 정의(§6)로:

$$A(\tau) = \exp(\tau X) = \sum_i e^{\tau \mu_i}\, \vert v_i\rangle\langle v^i\vert$$

**2)** 즉 $A(\tau)$ 의 고유값은 $e^{\tau \mu_i}$ ($\tau$-의존), 고유벡터는 $\vert v_i\rangle$ ($\tau$-무관, $X$ 와 동일).

**3)** §3의 깔끔한 경우에 해당하므로:

$$\frac{dA}{d\tau} = \sum_i \frac{d}{d\tau}\big(e^{\tau\mu_i}\big)\, \vert v_i\rangle\langle v^i\vert = \sum_i \mu_i\, e^{\tau\mu_i}\, \vert v_i\rangle\langle v^i\vert$$

**4)** 이 결과는 $X \cdot A(\tau)$ 와 같다. 직접 계산:

$$X \cdot A(\tau) = \left(\sum_j \mu_j\, \vert v_j\rangle\langle v^j\vert\right) \left(\sum_i e^{\tau\mu_i}\, \vert v_i\rangle\langle v^i\vert\right)$$

$\langle v^j\vert v_i\rangle = \delta^j_i$ 를 적용하면

$$= \sum_i \mu_i\, e^{\tau\mu_i}\, \vert v_i\rangle\langle v^i\vert$$

**5)** 따라서 §6에서 본 $\dfrac{d}{d\tau}\exp(\tau X) = X\, \exp(\tau X)$ 가 *스펙트럼 분해 위에서 고유값별 스칼라 미분*으로 자연스럽게 재현된다.

---

### 4. 일반 경우: 고유벡터가 변하는 상황

**1)** 일반적으로 $A(\tau)$ 의 고유벡터도 $\tau$ 에 따라 변한다. 이때 $\vert\dot v_i\rangle$ 을 구체적으로 계산하려면 *섭동 이론(perturbation theory)* 이 필요하다.

**2)** 비퇴화 고유값 ($\lambda_i \neq \lambda_j$ for $i \neq j$) 가정 하에서:

$$\vert\dot v_i\rangle = \sum_{j\neq i} \frac{\langle v^j\vert\dot A\vert v_i\rangle}{\lambda_i - \lambda_j}\, \vert v_j\rangle$$

($\vert v_i\rangle$ 자신 방향의 성분은 정규화 게이지 자유도에 해당하며, 표준적 선택에서 0으로 잡는다.)

**3)** proof) 고유값 식 $A\vert v_i\rangle = \lambda_i \vert v_i\rangle$ 양변을 미분한다.

$$\dot A\vert v_i\rangle + A\vert \dot v_i\rangle = \dot\lambda_i\vert v_i\rangle + \lambda_i\vert \dot v_i\rangle$$

좌변에 $\langle v^j\vert$ ($j \neq i$)를 곱한다. $\langle v^j\vert v_i\rangle = 0$ 이고 $\langle v^j\vert A = \lambda_j\langle v^j\vert$ 이므로:

$$\langle v^j\vert \dot A\vert v_i\rangle + \lambda_j\langle v^j\vert \dot v_i\rangle = 0 + \lambda_i\langle v^j\vert \dot v_i\rangle$$

정리하면:

$$\langle v^j\vert \dot v_i\rangle = \frac{\langle v^j\vert\dot A\vert v_i\rangle}{\lambda_i - \lambda_j}$$

이를 $\vert\dot v_i\rangle = \sum_j \langle v^j\vert\dot v_i\rangle\, \vert v_j\rangle$ 에 대입하면 위 공식이 나온다.

**4)** 분모에 $\lambda_i - \lambda_j$ 가 나오는 점이 핵심이다.
- 고유값이 *가까울수록* 분모가 작아져 고유벡터의 변화율이 커진다 (작은 섭동에도 큰 회전)
- 고유값이 *겹치는 경우(퇴화)*는 분모가 0이 돼 위 공식이 직접 적용되지 않는다. 이 경우 퇴화 섭동 이론이 필요하다

---

### 5. 정리

**1)** 스펙트럼 분해된 행렬을 미분하면 *세 항*이 나온다: 고유값 변화 + 켓 고유벡터 회전 + 브라 고유벡터 회전.

**2)** 고유벡터가 고정되면 뒤의 두 항이 사라져, *고유값에만 미분이 작용하는* 깨끗한 구조가 된다. 함수 미적분의 자연스러운 짝.

**3)** $\exp(\tau X)$ 는 이 깨끗한 경우의 대표 예. 고유벡터가 $X$ 의 고유벡터로 고정, 고유값만 $e^{\tau\mu_i}$ 로 변한다.

**4)** 일반 경우엔 고유벡터도 변한다. 비퇴화 고유값에서 $\vert\dot v_i\rangle$ 은 다른 고유벡터들의 합으로 표시되며, 분모 $\lambda_i - \lambda_j$ 가 회전 속도를 결정한다.
