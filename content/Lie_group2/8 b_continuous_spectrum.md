+++
title = "연속 스펙트럼 확장"
weight = 8
+++

### 1. 동기

§7까지는 이산 스펙트럼(고유값들이 띄엄띄엄 분포된 경우)을 다뤘다. 그러나 위치 연산자, 운동량 연산자, 자유 입자 해밀토니안 같은 많은 연산자는 *연속 스펙트럼*을 가진다. 이 장에서는 §7의 결과들을 연속 스펙트럼으로 확장한다.

핵심 변환:
- 합 → 적분
- 크로네커 델타 → 디랙 델타
- 이산 고유벡터 $\vert v_i\rangle$ → 연속 고유상태 $\vert u\rangle$

세 항 분해의 구조 자체는 그대로 유지된다.

### 2. 연속 스펙트럼 분해

**1)** 연속 매개변수 $u$로 라벨링된 고유상태로 연산자 $A$를 분해하면

$$A = \int du\, \lambda(u)\, \vert u\rangle\langle u^d\vert$$

여기서:
- $\lambda(u)$는 $\vert u\rangle$에 대응되는 고유값 (연속 매개변수의 함수)
- $\langle u^d\vert$는 연속 기저에 대한 쌍대 기저 (§1 참조)

**2)** 직교성:

$$\langle u^d\vert u'\rangle = \delta(u - u')$$

크로네커 $\delta^i_j$ 가 디랙 $\delta(u-u')$로 바뀐다.

**3)** *주의*: 연속 고유상태 $\vert u\rangle$ 는 보통의 힐베르트 공간 원소가 아닌 *일반화된 고유상태*다 (rigged Hilbert space의 원소). 형식적으로 이산 경우와 같은 식이 통하지만, 정확한 수학적 정당화는 별도 이론(분배 이론, rigged Hilbert space)에서 다뤄진다.

**4)** 위치 기저의 경우: $\vert x\rangle$ 는 자체수반이라 $\langle x^d\vert = \langle x\vert$ 로 단순화된다 (§1).

### 3. 연속 함수 미적분

**1)** 이산 경우 $f(A) = \sum_i f(\lambda_i)\, \vert v_i\rangle\langle v^i\vert$ 의 연속판:

$$f(A) = \int du\, f(\lambda(u))\, \vert u\rangle\langle u^d\vert$$

고유상태는 그대로 두고, *고유값에만 $f$ 를 적용*하는 원리는 동일하다.

**2)** example) 지수 사상의 연속판:

$$\exp(A) = \int du\, e^{\lambda(u)}\, \vert u\rangle\langle u^d\vert$$

### 4. 연속 스펙트럼에서의 미분: 세 항

**1)** 매개변수 $\tau$ 에 의존하는 연산자 $A(\tau)$ 의 연속 스펙트럼 분해를 다음으로 쓴다.

$$A(\tau) = \int du\, \lambda(u, \tau)\, \vert u(\tau)\rangle\langle u^d(\tau)\vert$$

고유값과 고유상태 모두 $\tau$ 에 따라 변할 수 있다.

**2)** 곱셈 규칙을 세 인자에 모두 적용:

$$\frac{dA}{d\tau} = \int du\, \Big[\dot\lambda(u, \tau)\, \vert u\rangle\langle u^d\vert + \lambda(u, \tau)\, \vert\dot u\rangle\langle u^d\vert + \lambda(u, \tau)\, \vert u\rangle\langle \dot{u^d}\vert\Big]$$

세 항의 의미는 §7의 이산 경우와 같다. 단지 *합이 적분으로* 바뀌었다.

### 5. 깔끔한 경우: 고유상태 고정

**1)** $\vert u\rangle$ 가 $\tau$ 와 무관하면 뒤의 두 항이 사라지고

$$\frac{dA}{d\tau} = \int du\, \dot\lambda(u, \tau)\, \vert u\rangle\langle u^d\vert$$

**2)** 함수 미적분의 미분 구조(§7.3의 연속판)가 그대로 적용된다.

**3)** example) 위치 연산자가 곱해진 형태

$$A(\tau) = \tau \hat{x}$$

위치 기저는 $\hat{x}\vert x\rangle = x\vert x\rangle$ 로 고유상태가 고정 ($\tau$ 와 무관).

- 고유값: $\lambda(x, \tau) = \tau x$
- 고유상태: $\vert x\rangle$ ($\tau$-무관)

따라서

$$\frac{dA}{d\tau} = \int dx\, x\, \vert x\rangle\langle x\vert = \hat{x}$$

직접 미분 $\dfrac{d}{d\tau}(\tau \hat{x}) = \hat{x}$ 와 일치.

### 6. 일반 경우: 고유상태가 변하는 상황

**1)** 비퇴화 연속 스펙트럼에서 섭동 형식의 공식:

$$\vert\dot u\rangle = \int du'\, \frac{\langle u'^d\vert\dot A\vert u\rangle}{\lambda(u) - \lambda(u')}\, \vert u'\rangle$$

(적분에서 $u' = u$ 점은 분모가 0이 되므로 제외; *주값(principal value)* 으로 처리)

**2)** 이산 공식(§7.5)과 같은 구조. 분모 $\lambda(u) - \lambda(u')$ 가 고유상태 변화 속도를 결정한다.

**3)** $u' = u$ 점의 처리:

분모 영점 ($u' = u$) 근처에서 적분이 발산할 수 있다. 표준 처방은 두 가지다.
- *주값*: $\int_{\vert u'-u\vert > \epsilon} du'\, \cdots$ 의 극한 $\epsilon \to 0$ 으로 취함
- *$i\epsilon$ 처방*: 분모를 $\lambda(u) - \lambda(u') + i\epsilon$ 으로 약간 이동시켜 영점을 피함

산란 이론과 그린 함수 이론에서 후자 처방이 자주 등장한다. Plemelj 공식

$$\frac{1}{x \pm i\epsilon} = P\frac{1}{x} \mp i\pi\, \delta(x)$$

로 두 처방이 연결된다.

### 7. 이산 ↔ 연속 비교

| 항목 | 이산 | 연속 |
|--|--|--|
| 분해 | $\sum_i \lambda_i\, \vert v_i\rangle\langle v^i\vert$ | $\int du\, \lambda(u)\, \vert u\rangle\langle u^d\vert$ |
| 직교 | $\langle v^i\vert v_j\rangle = \delta^i_j$ | $\langle u^d\vert u'\rangle = \delta(u-u')$ |
| 미분 (깔끔) | $\sum_i \dot\lambda_i\, \vert v_i\rangle\langle v^i\vert$ | $\int du\, \dot\lambda\, \vert u\rangle\langle u^d\vert$ |
| 섭동 분모 | $\lambda_i - \lambda_j$ | $\lambda(u) - \lambda(u')$ |
| 합/적분 | $\sum_{j\neq i}$ | $\int du'$ (주값) |

구조는 동일하고, 기호만 갈아끼우는 셈이다.

### 8. 정리

**1)** 연속 스펙트럼 분해는 합을 적분으로, 크로네커 델타를 디랙 델타로 바꾼 형태. 쌍대 기저 표기는 $\langle u^d\vert$ 로 마커를 붙인다.

**2)** 세 항 분해, 깔끔한 경우, 일반 섭동 공식 모두 이산과 같은 구조로 연속에 그대로 옮겨진다.

**3)** 기술적 차이는 *분모 영점의 주값/$i\epsilon$ 처리*, *일반화된 고유상태의 정규화*, *분배 이론 수준의 수학적 정당화* 등이다.

**4)** 결국 §1~§7의 도구들이 연속 스펙트럼 경우로 자연스럽게 확장된다.
