+++
title = "(b) MV continuous spectrum"
weight = 6
+++

### 1. 동기

§8 에서 1매개변수 연속 스펙트럼 미분 — 적분형 스펙트럼 분해, 연속 인덱스의 섭동, 분모 영점에서의 발산을 다루는 주값/$i\varepsilon$ 처방 — 을 다뤘다. §12 에서 이산 다변수로 확장했다.

이 장에서는 두 일반화의 *결합* — 연속 스펙트럼을 가진 다변수 행렬(연산자) $A(\tau^1, \ldots, \tau^n)$ — 을 다룬다. NEGF·산란 이론·물리적 응용에서 가장 일반적인 경우다.

### 2. 다변수 연속 스펙트럼 분해 (가정)

**1)** $A(\tau)$ 가 매개변수 영역에서 연속 스펙트럼을 갖고, 고유값 함수 $\lambda(u, \tau)$ 와 고유벡터 $|u(\tau)\rangle, \langle u^d(\tau)|$ 가 매개변수와 연속 인덱스 모두에 대해 매끄럽다고 가정한다.

**2)** 스펙트럼 분해 (각 점 $\tau$ 에서):

$$A(\tau) = \int du\; \lambda(u, \tau)\, |u(\tau)\rangle \langle u^d(\tau)|$$

**3)** 연속 직교 관계:

$$\langle u^d(\tau) | u'(\tau) \rangle = \delta(u - u')$$

**4)** 자기 쌍대 경우 ($\langle u^d| = \langle u|$, 예: 위치 기저) 는 §8 의 규약에 따른다.

### 3. 편미분의 세 항 분해

**1)** 곱셈 규칙 (§11.3) 을 적분 안의 모든 인자에 적용:

$$\frac{\partial A}{\partial \tau^a} = \int du \left[ \frac{\partial \lambda(u, \tau)}{\partial \tau^a}\, |u\rangle \langle u^d| + \lambda(u, \tau)\, \frac{\partial |u\rangle}{\partial \tau^a} \langle u^d| + \lambda(u, \tau)\, |u\rangle\, \frac{\partial \langle u^d|}{\partial \tau^a} \right]$$

**2)** §12 의 세 항 구조가 연속 인덱스 적분 안에 들어간 형태. 매개변수마다 세 항 분해.

### 4. 다변수 헬만-파인만 (연속)

**1)** 고유값 방정식 $A|u\rangle = \lambda(u) |u\rangle$ 의 양변을 $\tau^a$ 로 편미분 후, $\langle u^d|$ 왼쪽에 곱하고 직교 관계 활용:

$$\boxed{\frac{\partial \lambda(u, \tau)}{\partial \tau^a} = \langle u^d(\tau) | \frac{\partial A}{\partial \tau^a} | u(\tau) \rangle}$$

**2)** 1매개변수·이산 경우의 자연스러운 일반화. *연속 인덱스* $u$ 가 추가됐을 뿐 형태는 같다.

### 5. 다변수 섭동 공식 (연속, 주값/$i\varepsilon$)

**1)** $u' \neq u$ 에 사영:

$$\langle u^{\prime d} | \frac{\partial |u\rangle}{\partial \tau^a} = \frac{\langle u^{\prime d} | \partial A / \partial \tau^a | u \rangle}{\lambda(u) - \lambda(u')}$$

**2)** $|\partial u / \partial \tau^a\rangle$ 를 연속 기저로 전개:

$$\frac{\partial |u\rangle}{\partial \tau^a} = \int du'\; \frac{\langle u^{\prime d} | \partial A / \partial \tau^a | u \rangle}{\lambda(u) - \lambda(u')}\, |u'\rangle$$

**3)** *분모 발산*: $u' = u$ 에서 분모가 0. 또한 일반적으로 $\lambda(u) = \lambda(u')$ 를 만족하는 다른 $u' \neq u$ 가 존재할 수 있다 (스펙트럼이 단사가 아닌 경우). 이 영점들에서 §8 처럼 *주값* 또는 *$i\varepsilon$ 처방* 으로 정칙화:

$$\frac{1}{\lambda(u) - \lambda(u')} \;\to\; \mathcal{P}\frac{1}{\lambda(u) - \lambda(u')} \quad \text{또는} \quad \frac{1}{\lambda(u) - \lambda(u') \pm i\varepsilon}$$

**4)** 부호 ($+i\varepsilon$ vs $-i\varepsilon$) 는 물리적 인과성에 따라 결정 — 지연 그린 함수 ($+$) vs 선행 그린 함수 ($-$).

**5)** *각 방향* $\tau^a$ 마다 독립적인 섭동. §12 와 같은 구조에 연속 인덱스만 추가된 형태.

### 6. 혼합 편미분과 클레로

**1)** $A$ 가 매끄러우면 클레로 정리 그대로 성립:

$$\frac{\partial^2 A}{\partial \tau^a \partial \tau^b} = \frac{\partial^2 A}{\partial \tau^b \partial \tau^a}$$

스펙트럼 부품 $\lambda(u, \tau)$, $|u(\tau)\rangle$ 각각도 매끄러운 경우 클레로 만족.

**2)** *주의 반복*: 클레로는 *미분 작용 순서* 의 교환 가능성을 말하고, 두 *교란 작용소* $\partial A/\partial \tau^a$, $\partial A/\partial \tau^b$ 의 *교환자* 와는 다르다. 일반적으로

$$\left[\frac{\partial A}{\partial \tau^a},\, \frac{\partial A}{\partial \tau^b}\right] \neq 0$$

이게 §14 의 리 괄호로 직결된다.

### 7. 특별한 경우

**1)** *고유함수가 모든 $\tau$ 에서 고정*: $\partial |u\rangle / \partial \tau^a = 0$. 첫째 항만 남음:

$$\frac{\partial A}{\partial \tau^a} = \int du\; \frac{\partial \lambda(u, \tau)}{\partial \tau^a}\, |u\rangle \langle u^d|$$

예: $A(\tau) = T + \tau^a V_a$ 에서 모든 $V_a$ 가 $T$ 와 동시 대각화 가능한 경우 ($[T, V_a] = 0$, $[V_a, V_b] = 0$).

**2)** *고유값이 모든 $\tau$ 에서 고정*: 둘째·셋째 항만 — 고유함수의 회전만. 예: 유니터리 변환 $A(\tau) = U(\tau) A_0 U(\tau)^{-1}$.

### 8. example: 자유 입자 + 두 위치 의존 섭동

**1)** 1차원 슈뢰딩거형 작용소:

$$A(\tau^1, \tau^2) = -\frac{d^2}{dx^2} + \tau^1 V_1(x) + \tau^2 V_2(x)$$

$\tau = 0$ 에서 자유 입자. 평면파 고유함수 $|u\rangle \sim e^{iux}$, 고유값 $\lambda(u) = u^2$.

**2)** 편미분:

$$\frac{\partial A}{\partial \tau^1} = V_1, \qquad \frac{\partial A}{\partial \tau^2} = V_2$$

**3)** 헬만-파인만 (1차 고유값 이동):

$$\frac{\partial \lambda(u)}{\partial \tau^1}\bigg|_{\tau=0} = \langle u^d | V_1 | u \rangle$$

평면파 기저에서는 $V_1$ 의 공간 평균 형태에 해당.

**4)** 섭동 공식 (1차 고유함수 보정):

$$\frac{\partial |u\rangle}{\partial \tau^a}\bigg|_{\tau=0} = \int du'\; \frac{\langle u^{\prime d}|V_a|u\rangle}{u^2 - u^{\prime 2} + i\varepsilon}\, |u'\rangle$$

**5)** 분모 $u^2 - u^{\prime 2} = (u - u')(u + u')$ 는 *두 곳에서 0* — $u' = u$ (자기 자신) 와 $u' = -u$ (반대 운동량). $i\varepsilon$ 처방으로 처리.

**6)** 이 형태는 *자유 입자의 지연 그린 함수*

$$G^R_0(u, u') = \frac{\delta(u - u')}{u^2 - u^{\prime 2} + i\varepsilon}$$

와 직결된다. 다변수 섭동의 1차 응답 = 자유 그린 함수에 교란을 작용한 결과. NEGF 의 출발점.

### 9. 정리

**1)** 다변수 연속 스펙트럼 행렬의 편미분이 *세 항으로 분해*된다 — 각 매개변수마다, 연속 인덱스 적분 안에서.

**2)** *다변수 헬만-파인만*:

$$\frac{\partial \lambda(u, \tau)}{\partial \tau^a} = \langle u^d | \frac{\partial A}{\partial \tau^a} | u \rangle$$

**3)** *다변수 섭동 공식*:

$$\frac{\partial |u\rangle}{\partial \tau^a} = \int du'\; \frac{\langle u^{\prime d}|\partial A / \partial \tau^a|u\rangle}{\lambda(u) - \lambda(u') \pm i\varepsilon}\, |u'\rangle$$

(또는 주값.) $i\varepsilon$ 부호는 인과성 (지연/선행) 으로 결정.

**4)** *클레로 정리*는 매끄러운 경우 그대로 성립. 단, 교란 작용소의 *교환자*는 일반적으로 0 이 아니며, 이게 §14 리 괄호의 기반.

**5)** *자유 입자 예제*는 1차 섭동이 *지연 그린 함수* 와 직접 연결됨을 보여준다 — NEGF 의 출발점.

**6)** 이로써 §5~§13 의 *미분 도구* 가 완성됐다. 다음 §14 에서 *비교환성 자체*를 리 괄호로 정량화한다.
