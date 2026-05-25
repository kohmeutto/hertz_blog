+++
title = "(b) MV discrete spectrum"
weight = 5
+++

### 1. 동기

§7에서 1매개변수 행렬 $A(\tau)$ 의 미분이 *세 항* — 고유값 변화 + 켓 고유벡터 변화 + 브라 고유벡터 변화 — 으로 분해됨을 봤다. §11에서 다변수 편미분의 일반 규칙을 다뤘다.

이 장에서는 둘을 결합한다 — 다변수 $A(\tau^1, \ldots, \tau^n)$ 의 각 편미분 $\partial A/\partial \tau^a$ 가 어떻게 스펙트럼 위에서 분해되는지.

### 2. 다변수 스펙트럼 분해 (가정)

**1)** 매개변수 영역에서 $A(\tau)$ 가 *비축퇴 (non-degenerate)* 고유값을 갖고, 고유값 $\lambda_i(\tau)$ 와 고유벡터 $|v_i(\tau)\rangle, \langle v^i(\tau)|$ 가 $\tau$ 에 대해 매끄럽다고 가정한다.

**2)** 이때 각 점 $\tau$ 에서 스펙트럼 분해:

$$A(\tau) = \sum_i \lambda_i(\tau)\, |v_i(\tau)\rangle \langle v^i(\tau)|$$

**3)** 쌍대 기저 직교 관계: $\langle v^i(\tau) | v_j(\tau) \rangle = \delta^i_j$ (각 $\tau$ 에서).

### 3. 편미분의 세 항 분해

**1)** 각 매개변수 $\tau^a$ 에 대한 편미분에 곱셈 규칙 (§11.3) 을 적용:

$$\frac{\partial A}{\partial \tau^a} = \sum_i \left[ \frac{\partial \lambda_i}{\partial \tau^a}\, |v_i\rangle \langle v^i| \;+\; \lambda_i\, \frac{\partial |v_i\rangle}{\partial \tau^a} \langle v^i| \;+\; \lambda_i\, |v_i\rangle\, \frac{\partial \langle v^i|}{\partial \tau^a} \right]$$

**2)** *세 항의 의미*:
- *첫째*: 고유값이 $\tau^a$ 방향으로 변화 (스펙트럼 자체의 이동)
- *둘째*: 켓 고유벡터가 $\tau^a$ 방향으로 변화
- *셋째*: 브라 고유벡터가 $\tau^a$ 방향으로 변화

**3)** §7의 세 항 구조가 *각 매개변수마다* 그대로 적용된다. 매개변수 $n$ 개에 대해 *$n$ 개의 세 항 분해* 가 있다.

### 4. 다변수 헬만-파인만

**1)** $A|v_i\rangle = \lambda_i |v_i\rangle$ 의 양변을 $\tau^a$ 로 편미분:

$$\frac{\partial A}{\partial \tau^a}|v_i\rangle + A\frac{\partial |v_i\rangle}{\partial \tau^a} = \frac{\partial \lambda_i}{\partial \tau^a}|v_i\rangle + \lambda_i \frac{\partial |v_i\rangle}{\partial \tau^a}$$

**2)** 양변에 $\langle v^i|$ 를 왼쪽에서 곱하고 $\langle v^i|A = \lambda_i \langle v^i|$ 활용:

$$\langle v^i|\frac{\partial A}{\partial \tau^a}|v_i\rangle + \lambda_i \langle v^i|\frac{\partial |v_i\rangle}{\partial \tau^a} = \frac{\partial \lambda_i}{\partial \tau^a} + \lambda_i \langle v^i|\frac{\partial |v_i\rangle}{\partial \tau^a}$$

두 둘째 항이 상쇄되어

$$\boxed{\frac{\partial \lambda_i}{\partial \tau^a} = \langle v^i | \frac{\partial A}{\partial \tau^a} | v_i \rangle}$$

**3)** *고유값의 편미분*은 *교란 행렬* $\partial A/\partial \tau^a$ 의 *대각 성분*. §7의 헬만-파인만의 자연스러운 일반화 — 매개변수가 늘어도 형태가 그대로다.

### 5. 다변수 섭동 공식

**1)** 동일한 식에서 양변에 $\langle v^j|$ ($j \neq i$) 을 왼쪽에서 곱:

$$\langle v^j|\frac{\partial A}{\partial \tau^a}|v_i\rangle + \lambda_j \langle v^j|\frac{\partial |v_i\rangle}{\partial \tau^a} = \lambda_i \langle v^j|\frac{\partial |v_i\rangle}{\partial \tau^a}$$

(왼쪽 둘째 항에 $\langle v^j|A = \lambda_j \langle v^j|$ 적용.)

**2)** 정리하면

$$\langle v^j|\frac{\partial |v_i\rangle}{\partial \tau^a} = \frac{\langle v^j | \partial A / \partial \tau^a | v_i \rangle}{\lambda_i - \lambda_j}, \quad j \neq i$$

**3)** $|\partial v_i / \partial \tau^a\rangle$ 를 기저로 전개 ($j = i$ 항은 게이지 선택, 보통 0 으로 둔다):

$$\boxed{\frac{\partial |v_i\rangle}{\partial \tau^a} = \sum_{j \neq i} \frac{\langle v^j | \partial A / \partial \tau^a | v_i \rangle}{\lambda_i - \lambda_j} |v_j\rangle}$$

**4)** *각 방향* $\tau^a$ 마다 독립적인 섭동 공식. §7의 1매개변수 공식에 매개변수 라벨 $a$ 만 추가된 형태.

**5)** 분모 $\lambda_i - \lambda_j$ 는 *비축퇴* 가정에서 비롯된 안정 조건. 축퇴 영역에서는 발산하며, 이는 베리 위상·고유값 교차 등의 현상과 관련 (이 장 범위 밖).

### 6. 혼합 편미분과 클레로

**1)** 클레로 정리 (§11.4) 에 의해 $A$ 의 혼합 편미분은 순서 교환 가능:

$$\frac{\partial^2 A}{\partial \tau^a \partial \tau^b} = \frac{\partial^2 A}{\partial \tau^b \partial \tau^a}$$

**2)** 스펙트럼 부품 각각도 클레로 만족:

$$\frac{\partial^2 \lambda_i}{\partial \tau^a \partial \tau^b} = \frac{\partial^2 \lambda_i}{\partial \tau^b \partial \tau^a}, \qquad \frac{\partial^2 |v_i\rangle}{\partial \tau^a \partial \tau^b} = \frac{\partial^2 |v_i\rangle}{\partial \tau^b \partial \tau^a}$$

(매끄러운 매개변수화 하에서.)

**3)** *주의*: 이는 *미분 작용 순서*가 교환 가능하다는 뜻이지, 두 *교란 행렬* $\partial A/\partial \tau^a$ 와 $\partial A/\partial \tau^b$ 가 *교환*한다는 것과는 다르다. 일반적으로 

$$\left[\frac{\partial A}{\partial \tau^a},\, \frac{\partial A}{\partial \tau^b}\right] \neq 0$$

이 교환자는 §14의 *리 괄호* 와 직결된다.

### 7. 특별한 경우

**1)** *고유벡터가 모든 $\tau$ 에서 고정*: $\partial |v_i\rangle / \partial \tau^a = 0$ 모든 $a, i$. 그러면 첫째 항만 남고

$$\frac{\partial A}{\partial \tau^a} = \sum_i \frac{\partial \lambda_i}{\partial \tau^a}\, |v_i\rangle \langle v^i|$$

모든 편미분이 *같은 기저에서 대각화* 된다. 예: $A(\tau) = \sum_a \tau^a H_a$ 에서 모든 $H_a$ 가 동시 대각화 가능한 경우 ($[H_a, H_b]=0$ 모든 $a, b$).

**2)** *고유값이 모든 $\tau$ 에서 고정*: $\partial \lambda_i / \partial \tau^a = 0$. 그러면 둘째·셋째 항만 — 고유벡터의 회전만 일어난다. 예: 유니터리 변환 $A(\tau) = U(\tau) A_0 U(\tau)^{-1}$.

### 8. example: 2준위 계의 자기장 매개변수화

**1)** 두 매개변수 $(\tau^1, \tau^2)$ 에 의존하는 2준위 헤르미트 행렬:

$$A(\tau^1, \tau^2) = \tau^1\, \sigma_z + \tau^2\, \sigma_x$$

(파울리 행렬. 자기장의 $z$, $x$ 성분으로 해석 가능.)

**2)** 점 $(\tau^1, \tau^2) = (1, 0)$ 에서 평가:
- $A = \sigma_z = \mathrm{diag}(1, -1)$
- 고유값: $\lambda_+ = +1, \lambda_- = -1$
- 고유벡터: $|v_+\rangle = |\uparrow\rangle, |v_-\rangle = |\downarrow\rangle$

**3)** 교란 행렬:

$$\frac{\partial A}{\partial \tau^1} = \sigma_z, \qquad \frac{\partial A}{\partial \tau^2} = \sigma_x$$

**4)** 고유값의 편미분 (헬만-파인만):

(1) $\dfrac{\partial \lambda_+}{\partial \tau^1} = \langle\uparrow| \sigma_z |\uparrow\rangle = +1$

(2) $\dfrac{\partial \lambda_+}{\partial \tau^2} = \langle\uparrow| \sigma_x |\uparrow\rangle = 0$

(3) $\dfrac{\partial \lambda_-}{\partial \tau^1} = \langle\downarrow| \sigma_z |\downarrow\rangle = -1$

해석: $\tau^1$ 방향은 고유값을 *벌리고* ($+\lambda$ 는 더 올리고 $-\lambda$ 는 더 내림), $\tau^2$ 방향은 1차에서 고유값을 *건드리지 않는다*. 2차 효과는 별도 계산 필요.

**5)** 고유벡터의 편미분 (섭동 공식):

(1) $\dfrac{\partial |v_+\rangle}{\partial \tau^1} = \dfrac{\langle\downarrow| \sigma_z |\uparrow\rangle}{1-(-1)} |\downarrow\rangle = \dfrac{0}{2} |\downarrow\rangle = 0$ (대각이라 회전 없음)

(2) $\dfrac{\partial |v_+\rangle}{\partial \tau^2} = \dfrac{\langle\downarrow| \sigma_x |\uparrow\rangle}{1-(-1)} |\downarrow\rangle = \dfrac{1}{2} |\downarrow\rangle$

해석: $\tau^2$ 방향이 *고유벡터를 $|\downarrow\rangle$ 쪽으로 회전* 시킨다 — 비대각 섭동의 효과.

**6)** *교란 행렬의 교환자*:

$$\left[\frac{\partial A}{\partial \tau^1},\, \frac{\partial A}{\partial \tau^2}\right] = [\sigma_z, \sigma_x] = 2i\sigma_y \neq 0$$

미분 순서는 교환 가능하지만 (클레로), 두 교란 행렬은 교환하지 않는다. 이 비교환성이 §14 의 리 괄호로 이어진다.

### 9. 정리

**1)** 다변수 행렬 $A(\tau)$ 의 편미분이 §7의 *세 항*으로 분해된다 — *각 매개변수마다*.

$$\frac{\partial A}{\partial \tau^a} = \sum_i \left[ \frac{\partial \lambda_i}{\partial \tau^a}\, |v_i\rangle \langle v^i| + \lambda_i \frac{\partial |v_i\rangle}{\partial \tau^a} \langle v^i| + \lambda_i |v_i\rangle \frac{\partial \langle v^i|}{\partial \tau^a} \right]$$

**2)** *다변수 헬만-파인만*: 고유값 편미분은 교란 행렬의 대각 성분.

$$\frac{\partial \lambda_i}{\partial \tau^a} = \langle v^i | \frac{\partial A}{\partial \tau^a} | v_i \rangle$$

**3)** *다변수 섭동 공식*: 고유벡터 편미분은 비대각 성분으로 사영.

$$\frac{\partial |v_i\rangle}{\partial \tau^a} = \sum_{j \neq i} \frac{\langle v^j | \partial A / \partial \tau^a | v_i \rangle}{\lambda_i - \lambda_j} |v_j\rangle$$

**4)** *클레로 정리*: 혼합 편미분은 순서 교환 가능 (매끄러운 경우). 단, 두 교란 행렬이 *교환* 한다는 것과는 다르다 — 이 비교환성이 §14 리 괄호의 기반.

**5)** *특수 경우*: 고유벡터 고정 → 첫째 항만 / 고유값 고정 → 둘째·셋째 항만.

**6)** 다음 장 §13 에서 연속 스펙트럼으로 확장한다.
