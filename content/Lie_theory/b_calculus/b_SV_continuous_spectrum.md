+++
title = "(b) SV continuous spectrum"
weight = 3
+++

---

### 1. 연속 스펙트럼에서의 미분: 세 항

$$A(\tau) = \int du\, \lambda(u, \tau)\, \vert u(\tau)\rangle\langle u^d(\tau)\vert$$

곱셈 규칙을 세 인자에 모두 적용:

$$\frac{dA}{d\tau} = \int du\, \Big[\dot\lambda(u, \tau)\, \vert u\rangle\langle u^d\vert + \lambda(u, \tau)\, \vert\dot u\rangle\langle u^d\vert + \lambda(u, \tau)\, \vert u\rangle\langle \dot{u^d}\vert\Big]$$

---

### 2. 특정 경우: 고유상태 고정

$\vert u\rangle$ 가 $\tau$ 와 무관하면 뒤의 두 항이 사라지고

$$
\frac{dA}{d\tau} = \int du\, \dot\lambda(u, \tau)\, \vert u\rangle\langle u^d\vert
$$

example)

위치 연산자가 곱해진 형태에서

$$
A(\tau) = \tau \hat{x}
$$

위치 기저는 $\hat{x}\vert x\rangle = x\vert x\rangle$ 로 고유상태가 고정 ($\tau$ 와 무관).

- 고유값: $\lambda(x, \tau) = \tau x$
- 고유상태: $\vert x\rangle$ ($\tau$-무관)

따라서

$$\frac{dA}{d\tau} = \int dx\, x\, \vert x\rangle\langle x\vert = \hat{x}$$

이것은 직접 미분 $\dfrac{d}{d\tau}(\tau \hat{x}) = \hat{x}$ 과 일치한다.

---

### 3. 일반 경우: 고유상태가 변함

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

---

### 7. 이산 ↔ 연속 비교

| 항목 | 이산 | 연속 |
|--|--|--|
| 분해 | $\sum_i \lambda_i\, \vert v_i\rangle\langle v^i\vert$ | $\int du\, \lambda(u)\, \vert u\rangle\langle u^d\vert$ |
| 직교 | $\langle v^i\vert v_j\rangle = \delta^i_j$ | $\langle u^d\vert u'\rangle = \delta(u-u')$ |
| 미분 (깔끔) | $\sum_i \dot\lambda_i\, \vert v_i\rangle\langle v^i\vert$ | $\int du\, \dot\lambda\, \vert u\rangle\langle u^d\vert$ |
| 섭동 분모 | $\lambda_i - \lambda_j$ | $\lambda(u) - \lambda(u')$ |
| 합/적분 | $\sum_{j\neq i}$ | $\int du'$ (주값) |

구조는 동일하고, 기호만 갈아끼우는 셈이다.

---

### 8. 정리

**1)** 연속 스펙트럼 분해는 합을 적분으로, 크로네커 델타를 디랙 델타로 바꾼 형태. 쌍대 기저 표기는 $\langle u^d\vert$ 로 마커를 붙인다.

**2)** 세 항 분해, 깔끔한 경우, 일반 섭동 공식 모두 이산과 같은 구조로 연속에 그대로 옮겨진다.

**3)** 기술적 차이는 *분모 영점의 주값/$i\epsilon$ 처리*, *일반화된 고유상태의 정규화*, *분배 이론 수준의 수학적 정당화* 등이다.

**4)** 결국 §1~§7의 도구들이 연속 스펙트럼 경우로 자연스럽게 확장된다.
