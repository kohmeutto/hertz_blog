+++
title = "(b) Linearization"
weight = 3
+++

---

### 1. 게토 변분(Gâteaux Variation)의 정의와 논리적 한계

바나흐 공간(Banach Space) $\mathcal{V}, \mathcal{W}$ 사이의 연산자 $F: \mathcal{V} \to \mathcal{W}$에 대해, 상태 $u \in \mathcal{V}$에서 방향 $\delta u \in \mathcal{V}$로의 게토 변분 $\delta F(u; \delta u)$는 실수 매개변수 $\epsilon \in \mathbb{R}$에 대한 미분으로 정의된다.

$$
\delta F(u; \delta u) \equiv \left. \frac{d}{d\epsilon} F[u + \epsilon \delta u] \right|_{\epsilon = 0} = \lim_{\epsilon \to 0} \frac{F[u + \epsilon \delta u] - F[u]}{\epsilon}
$$

---

## 2. 게토 미분가능성 및 국소 자코비안 연산자 $J_u$

상태 $u \in \mathcal{V}$에서 모든 방향 $\delta u \in \mathcal{V}$에 대해 게토 변분 $\delta F(u; \delta u)$가 존재하고, 사상 $\delta u \mapsto \delta F(u; \delta u)$가 유계 선형 연산자(Bounded Linear Operator)를 이룰 때, 연산자 $F$는 $u$에서 **게토 미분가능(Gâteaux Differentiable)** 하다고 정의한다.

이때 정의되는 연속 선형 연산자 $J_u \equiv DF(u) \in \mathcal{L}(\mathcal{V}, \mathcal{W})$를 상태 $u$에서의 **자코비안 연산자(Jacobian Operator)** 라 하며, 다음 공리를 만족한다.

* **동차성 (Homogeneity):**
  $$
  \delta F(u; c \delta u) = J_u [c \delta u] = c J_u [\delta u] \quad (\forall c \in \mathbb{R})
  $$
* **가산성 (Additivity):**
  $$
  \delta F(u; \delta u_1 + \delta u_2) = J_u [\delta u_1 + \delta u_2] = J_u [\delta u_1] + J_u [\delta u_2] \quad (\forall \delta u_1, \delta u_2 \in \mathcal{V})
  $$

---

## 3. 프레셰 미분(Fréchet Derivative)을 통한 선형화 보장

방향미분의 선형성을 공리화하지 않고 테일러 전개의 1차 근사(First-order Approximation)로서 도출하기 위해서는 프레셰 미분가능성을 전제해야 한다.

### 정의 1.3 (프레셰 미분가능성)
연산자 $F: \mathcal{V} \to \mathcal{W}$에 대해 상태 $u \in \mathcal{V}$에서 다음을 만족하는 유계 선형 연산자 $J_u \in \mathcal{L}(\mathcal{V}, \mathcal{W})$가 존재할 때, $F$는 $u$에서 **프레셰 미분가능(Fréchet Differentiable)**하다고 정의한다.

$$
F[u + \delta u] - F[u] = J_u [\delta u] + R_u [\delta u]
$$

여기서 나머지항 $R_u [\delta u]$는 다음 강력한 극한 조건을 만족한다.

$$
\lim_{\|\delta u\|_{\mathcal{V}} \to 0} \frac{\|R_u [\delta u]\|_{\mathcal{W}}}{\|\delta u\|_{\mathcal{V}}} = 0 \quad \text{즉, } R_u [\delta u] = o(\|\delta u\|_{\mathcal{V}})
$$

> **정리 (Gâteaux와 Fréchet의 관계):**  
> 연산자 $F$가 상태 $u$에서 프레셰 미분가능하면 항상 게토 미분가능하며, 두 자코비안 연산자 $J_u$는 유일하게 일치한다.

---

## 4. 준선형 연산자(Quasi-linear Operator)의 자코비안 구조 도출

### 구조 설정
연산자 $F: \mathcal{V} \to \mathcal{W}$가 상태 $u$에 의존하는 선형 연산자 사상 $\mathcal{A}: \mathcal{V} \to \mathcal{L}(\mathcal{V}, \mathcal{W})$에 의해 다음과 같은 준선형 구조(Quasi-linear Structure)로 주어진다고 하자.

$$
F[u] = \mathcal{A}(u)[u]
$$

### 엄밀한 선형화 유도 과정 (스타일 B: 쌍선형 텐서 표기)

1. **상태 섭동 적용:**  
   상태 $u$에 미소 매개변수와 방향 성분이 결합된 섭동 $\epsilon \delta u$를 부여한다.
   $$
   F[u + \epsilon \delta u] = \mathcal{A}(u + \epsilon \delta u) [u + \epsilon \delta u]
   $$

2. **계수 연산자 사상의 프레셰 전개:**  
   사상 $u \mapsto \mathcal{A}(u)$가 상태 $u$에서 프레셰 미분가능하다고 가정하면, 고계 프레셰 도함수를 동형 공간인 연속 쌍선형 사상 공간 $D\mathcal{A}(u) \in \mathcal{L}_2(\mathcal{V} \times \mathcal{V}, \mathcal{W})$로 관주하여 다음과 같이 전개한다.
   $$
   \mathcal{A}(u + \epsilon \delta u) = \mathcal{A}(u) + \epsilon D\mathcal{A}(u)[\delta u, \,\cdot\,] + o(\epsilon)
   $$

3. **연산자 전개 및 쌍선형성 정리:**  
   쌍선형 사상의 인자 대수 성질을 이용해 전개한다.
   $$
   \begin{aligned}
   F[u + \epsilon \delta u] &= \Big( \mathcal{A}(u) + \epsilon D\mathcal{A}(u)[\delta u, \,\cdot\,] + o(\epsilon) \Big) [u + \epsilon \delta u] \\[6pt]
   &= \mathcal{A}(u)[u] + \epsilon \mathcal{A}(u)[\delta u] + \epsilon D\mathcal{A}(u)[\delta u, u] + \epsilon^2 D\mathcal{A}(u)[\delta u, \delta u] + o(\epsilon)[u + \epsilon \delta u]
   \end{aligned}
   $$
   이때 $\epsilon^2$항 및 $o(\epsilon)$ 관련 항들은 $\epsilon \to 0$일 때 모두 $o(\epsilon)$으로 수렴하므로 다음과 같이 정리된다.
   $$
   F[u + \epsilon \delta u] = \mathcal{A}(u)[u] + \epsilon \mathcal{A}(u)[\delta u] + \epsilon D\mathcal{A}(u)[\delta u, u] + o(\epsilon)
   $$

4. **게토 변분 한계를 통한 자코비안 추출:**  
   정의 1.1에 따라 극한을 수행하여 변분 구조를 획득한다.
   $$
   \delta F(u; \delta u) = \lim_{\epsilon \to 0} \frac{F[u + \epsilon \delta u] - F[u]}{\epsilon} = \mathcal{A}(u)[\delta u] + D\mathcal{A}(u)[\delta u, u]
   $$

### 최종 결론 (준선형 자코비안)
준선형 연산자 $F[u] = \mathcal{A}(u)[u]$의 자코비안 연산자 $J_u$는 쌍선형 텐서 표기 체계에 의해 다음과 같이 명확히 정립된다.

$$
J_u = \mathcal{A}(u) + D\mathcal{A}(u)[\,\cdot\,, u]
$$

이를 임의의 방향 섭동 $\delta u$에 작용시킨 후, 국소 공간 좌표 $x \in \Omega$에서 평가한 최종 국소 자코비안 식은 다음과 같다.

$$
J_u [\delta u](x) = \big( \mathcal{A}(u)[\delta u] \big)(x) + \big( D\mathcal{A}(u)[\delta u, u] \big)(x)
$$

---

## 5. Self-Verification Protocol (자가 검증 보고)

* **[검증 1] 차원 및 공간(Space) 일치성:**  
  $D\mathcal{A}(u) \in \mathcal{L}_2(\mathcal{V} \times \mathcal{V}, \mathcal{W})$는 쌍선형 사상입니다. 두 피연산자 $(\delta u, u) \in \mathcal{V} \times \mathcal{V}$가 대괄호 $[\delta u, u]$ 안에 명시적으로 전달되어 결과 공간 $\mathcal{W}$의 원소를 직접 산출하므로, 좌변 $J_u[\delta u] \in \mathcal{W}$와 차원이 완벽히 일치합니다.
* **[검증 2] 괄호 일관성 (Style B 규격 검증):**  
  1. **상태 및 함수 평가:** 소괄호 $(u), \mathcal{A}(u)$ 사용.
  2. **피연산자 입력:** 대괄호 $[\delta u]$ 및 쌍선형 대괄호 $[\delta u, u]$ 사용. 중첩 연산자 $[ \cdot ][ \cdot ]$ 제거.
  3. **공간점 평가:** 연산자 작용 전체를 소괄호 $\big( \text{연산자 작용} \big)(x)$ 형태로 감싸 공간점 대입 영역을 명확히 고정.