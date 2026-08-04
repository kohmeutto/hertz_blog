+++
title = "(b) Nonlinear Operator"
weight = 1
+++

## 1. 두 가지 수학적 표현 체계 (Dual Mathematical Frameworks)

비선형 연산자(Nonlinear Operator)는 작용하는 상태 변수 자체에 종속되는 연산자이다. 이에 선형 변분연산자 $\delta$가 작용할 때, 고전적 함수형 표현과 디랙 브라켓 표현의 대응 관계는 다음과 같다.

| 구분 | (1) 고전적 함수형 표현 (Functional Form) | (2) 디랙 브라켓 표현 (Dirac Bra-Ket Form) |
| :--- | :--- | :--- |
| **비선형 대상** | 상태 종속 사상 $F(u)$ 또는 $\mathcal{L}(u)u$ | 상태 종속 연산자 $\hat{\mathbf{F}}(\mathbf{q})$ 또는 $\hat{\mathcal{L}}(\mathbf{q})$ |
| **선형 연산자 작용** | 변분연산자 작용 $\delta F(u)$ | 브라켓 변분 작용 $\hat{\delta}(\hat{\mathbf{F}}|\mathbf{q}\rangle)$ |
| **교환성 파괴** | $\delta \big( \mathcal{L}(u) u \big) \neq \mathcal{L}(u) (\delta u)$ | $\hat{\delta} \big( \hat{\mathcal{L}}(\mathbf{q}) |\mathbf{q}\rangle \big) \neq \hat{\mathcal{L}}(\mathbf{q}) |\delta \mathbf{q}\rangle$ |
| **국소 선형화 결과** | 게토 도함수 $F'[u] \delta u$ | 자코비안 연산자 작용 $\hat{J}(\mathbf{q}) |\delta \mathbf{q}\rangle$ |
| **잉여항 출현** | 연산자 자체 변분항 $\big( \delta \mathcal{L}(u) \big) u$ | 연산자 자체 변분항 $\Big( \hat{J}_{\mathcal{L}}(\mathbf{q}) |\delta \mathbf{q}\rangle \Big) |\mathbf{q}\rangle$ |

---

## 2. 비선형 연산자의 2대 핵심 특성

선형 연산자와 달리, 상태 변수 $\mathbf{q}$에 의존하는 비선형 연산자에 변분연산자 $\delta$를 적용할 때 발생하는 **2가지 치명적 수학적 특성**은 다음과 같다.

---

### 특성 1. 변분연산자 $\delta$와의 교환성 파괴 (Breakdown of Commutativity)

연산자 내부 계수나 구조가 상태 변수 $\mathbf{q}$에 종속(State-dependent)되어 있으면, 변분 매개변수 $\epsilon$ 관점에서 해당 연산자는 더 이상 상수가 아니다. 따라서 변분연산자 $\delta$와 연산자의 순서를 교환할 수 없다.

#### (1) 함수형 표현
상태 $u(x)$에 의존하는 미분 연산자 $\mathcal{L}(u) = u(x) \frac{d}{dx}$를 생각하자.

$$
\delta \Big( \mathcal{L}(u) u \Big) = \delta \left( u \frac{du}{dx} \right) \neq \mathcal{L}(u) (\delta u) = u \frac{d(\delta u)}{dx}
$$

좌변은 연산자 자체의 변분항이 함께 발생하므로, 단순 연산자 교환 법칙 $\delta \mathcal{L} = \mathcal{L} \delta$는 완전히 성립하지 않는다.

#### (2) 브라켓 표현
상태 켓 $|\mathbf{q}\rangle$에 종속적인 연산자 $\hat{\mathcal{L}}(\mathbf{q})$에 대해:

$$
\hat{\delta} \Big( \hat{\mathcal{L}}(\mathbf{q}) |\mathbf{q}\rangle \Big) \equiv \left. \frac{d}{d\epsilon} \Big( \hat{\mathcal{L}}(\mathbf{q} + \epsilon \delta \mathbf{q}) |\mathbf{q} + \epsilon \delta \mathbf{q}\rangle \Big) \right\vert_{\epsilon = 0} \neq \hat{\mathcal{L}}(\mathbf{q}) |\delta \mathbf{q}\rangle
$$

---

### 특성 2. 라이프니츠 법칙에 의한 자코비안 잉여항의 출현 (Appearance of Jacobian Extra Terms)

교환성이 파괴되는 수학적 원인은 연산자 자체에 적용되는 **곱의 미분법(Leibniz Rule)** 때문이다. 섭동 시 **연산자 자체의 변화량(자코비안)**과 **상태의 변화량**이 모두 피미분체로 작동하여 잉여항(Extra Term)이 출현한다.

#### (1) 함수형 표현
비선형 연산자 작용 $\mathcal{L}(u) u$에 대해 변분 연산을 전개하면:

$$
\begin{aligned}
\delta \Big( \mathcal{L}(u) u \Big) &= \left. \frac{\partial}{\partial \epsilon} \Big( \mathcal{L}(u + \epsilon \delta u) [u + \epsilon \delta u] \Big) \right\vert_{\epsilon = 0} \\[8pt]
&= \underbrace{\left( \left. \frac{\partial \mathcal{L}(u + \epsilon \delta u)}{\partial \epsilon} \right\vert_{\epsilon = 0} \right) u}_{\text{연산자 자체 변분 (자코비안 잉여항)}} + \underbrace{\mathcal{L}(u) \left. \frac{\partial (u + \epsilon \delta u)}{\partial \epsilon} \right\vert_{\epsilon = 0}}_{\text{상태 변분항}} \\[8pt]
&= \left( \frac{\partial \mathcal{L}}{\partial u} \delta u \right) u + \mathcal{L}(u) \delta u
\end{aligned}
$$

#### (2) 브라켓 표현
비선형 연산자 $\hat{\mathcal{L}}(\mathbf{q})$의 국소 자코비안 연산자를 $\hat{J}_{\mathcal{L}}(\mathbf{q}) \equiv \frac{\delta \hat{\mathcal{L}}}{\delta \mathbf{q}}$라 정의할 때:

$$
\begin{aligned}
\hat{\delta} \Big( \hat{\mathcal{L}}(\mathbf{q}) |\mathbf{q}\rangle \Big) &= \left. \frac{d}{d\epsilon} \Big[ \hat{\mathcal{L}}(\mathbf{q} + \epsilon \delta \mathbf{q}) \cdot |\mathbf{q} + \epsilon \delta \mathbf{q}\rangle \Big] \right\vert_{\epsilon = 0} \\[8pt]
&= \left( \left. \frac{d\hat{\mathcal{L}}(\mathbf{q} + \epsilon \delta \mathbf{q})}{d\epsilon} \right\vert_{\epsilon = 0} \right) |\mathbf{q}\rangle + \hat{\mathcal{L}}(\mathbf{q}) \left( \left. \frac{d}{d\epsilon} |\mathbf{q} + \epsilon \delta \mathbf{q}\rangle \right\vert_{\epsilon = 0} \right) \\[8pt]
&= \underbrace{\Big( \hat{J}_{\mathcal{L}}(\mathbf{q}) |\delta \mathbf{q}\rangle \Big) |\mathbf{q}\rangle}_{\text{연산자 섭동에 의한 자코비안 잉여항}} + \underbrace{\hat{\mathcal{L}}(\mathbf{q}) |\delta \mathbf{q}\rangle}_{\text{상태 섭동항}}
\end{aligned}
$$

---

## 3. 비선형 연산자의 국소 선형화와 자코비안 연산자 (Jacobian Operator)

비선형 연산자 $\hat{\mathbf{F}}(\mathbf{q}) \equiv \hat{\mathcal{L}}(\mathbf{q})|\mathbf{q}\rangle$ 전체에 대해 변분 연산을 취한 최종 결과는, 잉여항과 상태 섭동항이 합쳐져 **하나의 국소 자코비안 연산자 $\hat{J}(\mathbf{q})$가 가상 변위 $|\delta \mathbf{q}\rangle$에 선형 작용하는 형태**로 귀결된다.

$$
|\delta \mathbf{F}\rangle = \hat{\delta} \hat{\mathbf{F}}(\mathbf{q}) = \hat{J}(\mathbf{q}) |\delta \mathbf{q}\rangle
$$

이때 전체 자코비안 연산자 $\hat{J}(\mathbf{q})$의 구성을 분해하면 다음과 같다.

$$
\hat{J}(\mathbf{q}) = \underbrace{\frac{\partial \hat{\mathcal{L}}}{\partial \mathbf{q}} |\mathbf{q}\rangle}_{\text{연산자 종속 잉여항}} + \underbrace{\hat{\mathcal{L}}(\mathbf{q})}_{\text{기존 연산자}}
$$

---

## 4. 선형 vs 비선형 연산자의 변분 작용 비교 요약

$$
\begin{array}{rcccl}
\text{선형 연산자 } \hat{\mathcal{L}} & \quad \implies \quad & \hat{\delta}(\hat{\mathcal{L}} |\mathbf{q}\rangle) = \hat{\mathcal{L}} |\delta \mathbf{q}\rangle & \quad & (\text{교환성 성립, 잉여항 } 0) \\[12pt]
\text{비선형 연산자 } \hat{\mathcal{L}}(\mathbf{q}) & \quad \implies \quad & \hat{\delta}(\hat{\mathcal{L}}(\mathbf{q}) |\mathbf{q}\rangle) = \hat{J}_{\mathcal{L}}(\mathbf{q})|\delta \mathbf{q}\rangle |\mathbf{q}\rangle + \hat{\mathcal{L}}(\mathbf{q}) |\delta \mathbf{q}\rangle & \quad & (\text{교환성 파괴, 자코비안 잉여항 발생})
\end{array}
$$