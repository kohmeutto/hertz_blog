+++
title = "(b) Linearization"
weight = 3
+++

## 1. 두 가지 수학적 표현 체계 (Dual Mathematical Frameworks)

비선형 연산자에 선형 변분 연산자 $\delta$를 작용하는 과정은 비선형 사상을 국소적으로 1차 선형화(Local Linearization)하는 게토 미분(Gâteaux Derivative)을 수행하는 것에 해당한다. 

비선형 연산자는 상태 변수에 종속되므로, 변분 작용 시 연산자 자체의 변분이 수반되어 **선형 연산자에서 성립하던 교환성($\delta \mathcal{L} = \mathcal{L} \delta$)이 완전히 파괴**된다.

| 구분 | (1) 고전적 함수형 표현 (Functional Form) | (2) 디랙 브라켓 표현 (Dirac Bra-Ket Form) |
| :--- | :--- | :--- |
| **비선형 사상** | $F[u] \equiv \mathcal{N}[u] u$ | $|\mathbf{F}\rangle \equiv \hat{\mathcal{N}}[\mathbf{q}] |\mathbf{q}\rangle$ |
| **변분 연산 작용** | $\delta F[u] = \delta \Big[ \mathcal{N}[u] u \Big]$ | $|\delta \mathbf{F}\rangle = \hat{\delta} \Big( \hat{\mathcal{N}}[\mathbf{q}] |\mathbf{q}\rangle \Big)$ |
| **교환성 파괴** | $\delta \Big[ \mathcal{N}[u] u \Big] \neq \mathcal{N}[u] \delta u$ | $\hat{\delta} \Big( \hat{\mathcal{N}}[\mathbf{q}] |\mathbf{q}\rangle \Big) \neq \hat{\mathcal{N}}[\mathbf{q}] |\delta \mathbf{q}\rangle$ |
| **선형화 결과** | $\delta F[u] = J[u] \delta u$ (게토 도함수) | $|\delta \mathbf{F}\rangle = \hat{J}[\mathbf{q}] |\delta \mathbf{q}\rangle$ (자코비안 작용) |
| **자코비안 구조** | $J[u] = \mathcal{N}[u] + \left( \dfrac{\partial \mathcal{N}[u]}{\partial u} [\cdot] \right) u$ | $\hat{J}[\mathbf{q}] = \hat{\mathcal{N}}[\mathbf{q}] + \left( \dfrac{\delta \hat{\mathcal{N}}[\mathbf{q}]}{\delta \mathbf{q}} [\cdot] \right) |\mathbf{q}\rangle$ |

---

## 2. 변분 연산자와 비선형 연산자의 비가환성 (Non-commutativity)

선형 연산자 $\mathcal{L}$의 경우 $\delta \Big[ \mathcal{L}[u] \Big] = \mathcal{L}[\delta u]$가 성립하지만, 비선형 연산자 $\mathcal{N}[u]$는 작용 대상인 상태 $u$에 직접 종속되므로 **라이프니츠 곱의 미분법칙(Leibniz Rule)**에 의해 연산자 자체의 변분항이 발생한다.

### 2.1. 함수형 표현에서의 비가환성 증명

비선형 사상 $F[u] = \mathcal{N}[u] u$에 변분 연산자 $\delta$를 작용하자.

$$
\delta \Big[ \mathcal{N}[u] u \Big] \equiv \left. \frac{d}{d\epsilon} \left( \mathcal{N}[u + \epsilon \delta u] \Big( u + \epsilon \delta u \Big) \right) \right\vert_{\epsilon = 0}
$$

우변의 곱에 대해 $\epsilon = 0$에서 미분을 수행하면:

$$
\begin{aligned}
\delta \Big[ \mathcal{N}[u] u \Big] &= \mathcal{N}[u] \left( \left. \frac{d}{d\epsilon} [u + \epsilon \delta u] \right\vert_{\epsilon = 0} \right) + \left( \left. \frac{d}{d\epsilon} \mathcal{N}[u + \epsilon \delta u] \right\vert_{\epsilon = 0} \right) u \\[10pt]
&= \underbrace{\mathcal{N}[u] \delta u}_{\text{순수 연산자 작용항}} + \underbrace{\Big( \delta \mathcal{N}[u] \Big) u}_{\text{연산자 변분 잉여항}}
\end{aligned}
$$

여기서 $\delta \mathcal{N}[u] \equiv \left. \frac{d}{d\epsilon} \mathcal{N}[u + \epsilon \delta u] \right\vert_{\epsilon = 0}$는 **상태 섭동에 의한 연산자 자체의 게토 미분**이다.

$$
\therefore \quad \delta \Big[ \mathcal{N}[u] u \Big] \neq \mathcal{N}[u] \delta u \quad \left( \because \Big( \delta \mathcal{N}[u] \Big) u \neq 0 \right)
$$

---

### 2.2. 브라켓 표현에서의 비가환성 증명

상태 켓 $|\mathbf{q}\rangle$에 작용하는 비선형 연산자 $\hat{\mathcal{N}}[\mathbf{q}]$에 대해 변분 연산자 $\hat{\delta}$를 작용한다.

$$
|\delta \mathbf{F}\rangle = \hat{\delta} \Big( \hat{\mathcal{N}}[\mathbf{q}] |\mathbf{q}\rangle \Big) \equiv \left. \frac{d}{d\epsilon} \left( \hat{\mathcal{N}}[\mathbf{q} + \epsilon \delta \mathbf{q}] \Big( |\mathbf{q}\rangle + \epsilon |\delta \mathbf{q}\rangle \Big) \right) \right\vert_{\epsilon = 0}
$$

곱의 미분법을 적용하여 전개하면:

$$
\begin{aligned}
|\delta \mathbf{F}\rangle &= \hat{\mathcal{N}}[\mathbf{q}] \left( \left. \frac{d}{d\epsilon} \big[ |\mathbf{q}\rangle + \epsilon |\delta \mathbf{q}\rangle \big] \right\vert_{\epsilon = 0} \right) + \left( \left. \frac{d}{d\epsilon} \hat{\mathcal{N}}[\mathbf{q} + \epsilon \delta \mathbf{q}] \right\vert_{\epsilon = 0} \right) |\mathbf{q}\rangle \\[10pt]
&= \underbrace{\hat{\mathcal{N}}[\mathbf{q}] |\delta \mathbf{q}\rangle}_{\text{순수 연산자 작용항}} + \underbrace{\Big( \hat{\delta} \hat{\mathcal{N}}[\mathbf{q}] \Big) |\mathbf{q}\rangle}_{\text{연산자 변분 잉여항}}
\end{aligned}
$$

$$
\therefore \quad \hat{\delta} \Big( \hat{\mathcal{N}}[\mathbf{q}] |\mathbf{q}\rangle \Big) \neq \hat{\mathcal{N}}[\mathbf{q}] |\delta \mathbf{q}\rangle \quad \left( \because \Big( \hat{\delta} \hat{\mathcal{N}}[\mathbf{q}] \Big) |\mathbf{q}\rangle \neq \mathbf{0} \right)
$$

---

## 3. 국소 자코비안 연산자(Jacobian Operator)의 도출

변분 연산자의 작용 결과는 입력 섭동 $\delta u$ 또는 $|\delta \mathbf{q}\rangle$에 대해 **1차 선형(Linear)**이어야 한다. 연산자 변분 잉여항을 섭동량에 대한 선형 작용으로 재구성함으로써 **국소 자코비안 연산자 $J[u]$ 및 $\hat{J}[\mathbf{q}]$**가 도출된다.

### 3.1. 게토 연쇄 법칙과 자코비안 잉여항

#### (1) 함수형 표현
연산자 변분항 $\delta \mathcal{N}[u]$에 방향 미분의 연쇄 법칙(Chain Rule)을 적용하면 다음과 같다.

$$
\Big( \delta \mathcal{N}[u] \Big) u = \left( \frac{\partial \mathcal{N}[u]}{\partial u} [\delta u] \right) u
$$

따라서 전체 변분 $\delta F[u]$는 다음과 같이 선형화된다.

$$
\begin{aligned}
\delta F[u] &= \mathcal{N}[u] \delta u + \left( \frac{\partial \mathcal{N}[u]}{\partial u} [\delta u] \right) u \\[8pt]
&= \left[ \mathcal{N}[u] + \left( \frac{\partial \mathcal{N}[u]}{\partial u} [\cdot] \right) u \right] \delta u \equiv J[u] \delta u
\end{aligned}
$$

여기서 **국소 자코비안 연산자 $J[u]$**는 다음과 같이 정의된다.

$$
J[u] \equiv \mathcal{N}[u] + \left( \frac{\partial \mathcal{N}[u]}{\partial u} [\cdot] \right) u
$$

#### (2) 브라켓 표현
동일하게 브라켓 표현에서 연산자 변분항을 가상 변위 켓 $|\delta \mathbf{q}\rangle$에 대한 선형 연산으로 변환한다.

$$
\Big( \hat{\delta} \hat{\mathcal{N}}[\mathbf{q}] \Big) |\mathbf{q}\rangle = \left( \frac{\delta \hat{\mathcal{N}}[\mathbf{q}]}{\delta \mathbf{q}} [\delta \mathbf{q}] \right) |\mathbf{q}\rangle
$$

따라서 선형화된 켓 $|\delta \mathbf{F}\rangle$는 자코비안 연산자 $\hat{J}[\mathbf{q}]$의 작용으로 정립된다.

$$
\begin{aligned}
|\delta \mathbf{F}\rangle &= \hat{\mathcal{N}}[\mathbf{q}] |\delta \mathbf{q}\rangle + \left( \frac{\delta \hat{\mathcal{N}}[\mathbf{q}]}{\delta \mathbf{q}} [\delta \mathbf{q}] \right) |\mathbf{q}\rangle \\[8pt]
&= \left[ \hat{\mathcal{N}}[\mathbf{q}] + \left( \frac{\delta \hat{\mathcal{N}}[\mathbf{q}]}{\delta \mathbf{q}} [\cdot] \right) |\mathbf{q}\rangle \right] |\delta \mathbf{q}\rangle \equiv \hat{J}[\mathbf{q}] |\delta \mathbf{q}\rangle
\end{aligned}
$$

$$
\hat{J}[\mathbf{q}] \equiv \hat{\mathcal{N}}[\mathbf{q}] + \left( \frac{\delta \hat{\mathcal{N}}[\mathbf{q}]}{\delta \mathbf{q}} [\cdot] \right) |\mathbf{q}\rangle
$$

---

### 3.2. 구체적 예시: 1차원 비선형 미분 연산자 (Burgers-type Advection)

이해를 돕기 위해 비선형 미분 연산자 $\mathcal{N}[u] = u \frac{d}{dx}$가 상태 $u(x)$에 작용하는 비선형 사상 $F[u] = u \frac{du}{dx}$의 선형화를 검증한다.

1. **사상 정의:** 
   $$F[u] = \mathcal{N}[u] u = u \frac{du}{dx}$$
2. **변분 연산자 $\delta$ 작용:**
   $$
   \delta F[u] = \delta \left( u \frac{du}{dx} \right) = (\delta u) \frac{du}{dx} + u \delta \left( \frac{du}{dx} \right)
   $$
3. **선형 미분 가환성 적용 ($\delta \frac{d}{dx} = \frac{d}{dx} \delta$):**
   $$
   \delta F[u] = (\delta u) \frac{du}{dx} + u \frac{d}{dx}(\delta u)
   $$
4. **항 재배치 및 자코비안 분해:**
   $$
   \delta F[u] = \underbrace{u \frac{d}{dx} (\delta u)}_{\mathcal{N}[u] \delta u} + \underbrace{\left( \frac{du}{dx} \right) \delta u}_{\text{자코비안 잉여항 } (\delta \mathcal{N}[u])u} = \left( u \frac{d}{dx} + \frac{du}{dx} \right) \delta u
   $$

* **결론:** 
  단순히 연산자와 변분 기호의 위치를 바꾼 $\mathcal{N}[u] \delta u = u \frac{d(\delta u)}{dx}$만으로는 정확한 변분을 얻을 수 없으며, 반드시 연산자 자체의 변분에서 기인한 **잉여항 $\left(\frac{du}{dx}\right) \delta u$**가 더해져야 완전한 자코비안 연산자 $J[u] = u \frac{d}{dx} + \frac{du}{dx}$가 도출된다.

---

## 4. 최종 종합: 연산자 유형별 변분 작용 비교

선형 연산자 $\mathcal{L}$과 비선형 연산자 $\mathcal{N}[u]$에 변분 연산자 $\delta$가 작용할 때의 본질적 차이는 다음과 같이 요약된다.

| 연산자 유형 | 변분 작용 식 | 교환 성질 | 자코비안 연산자 $J$ |
| :--- | :--- | :--- | :--- |
| **상태 독립 선형 연산자 ($\mathcal{L}$)** | $\delta \Big[ \mathcal{L} u \Big] = \mathcal{L} [\delta u]$ | **완벽 가환** ($\delta \mathcal{L} = \mathcal{L} \delta$) | $J = \mathcal{L}$ (상수 연산자) |
| **상태 종속 비선형 연산자 ($\mathcal{N}[u]$)** | $\delta \Big[ \mathcal{N}[u] u \Big] = \mathcal{N}[u] \delta u + (\delta \mathcal{N}[u]) u$ | **비가환** ($\delta \mathcal{N} \neq \mathcal{N} \delta$) | $J[u] = \mathcal{N}[u] + \left( \dfrac{\partial \mathcal{N}[u]}{\partial u} [\cdot] \right) u$ |