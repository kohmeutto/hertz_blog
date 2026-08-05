+++
title = "(a) Nonlinear Operator"
weight = 1
+++

---

### 1. 비선형 연산자의 대수적 본질: 상태 종속성 (State-dependence)

선형 연산자 $\hat{\mathcal{A}}$는 작용하는 상태 $|\mathbf{q}\rangle$와 무관하게 고정된 구조(Constant Structure)를 유지하지만, 비선형 연산자 $\hat{\mathcal{N}}[\mathbf{q}]$는 **작용하는 상태에 따라 연산자 자신의 성분과 매핑 규칙이 변화** 한다.

**1) 함수형 표현**

상태 함수 $u(x)$에 작용하는 미분 연산자를 생각하자.

* **선형 미분 연산자:** 

$$
\mathcal{L} = \frac{d}{dx} \text{또는} \mathcal{L} = a(x) \frac{d}{dx}
\quad \text{($a(x)$는 공간 좌표 $x$만의 함수)}
$$

* **비선형 미분 연산자:** 

$$
\mathcal{N}[u] = u(x) \frac{d}{dx}
$$

비선형 미분 연산자 $\mathcal{N}[u]$는 계수 자체가 상태 $u(x)$에 의해 결정되므로, 연산 대상인 함수 $u(x)$가 바뀌면 연산자 $\mathcal{N}$ 자체의 구조가 바뀐다.

**2) 브라켓 표현**

상태 켓 $|\mathbf{q}\rangle$에 작용하는 연산자에 대해:

* **선형 연산자:**

$$
\hat{\mathcal{L}} \left[ c_1 |\mathbf{q}_1\rangle + c_2 |\mathbf{q}_2\rangle \right] = c_1 \hat{\mathcal{L}}|\mathbf{q}_1\rangle + c_2 \hat{\mathcal{L}}|\mathbf{q}_2\rangle
$$

* **비선형 연산자:** 

$$
\hat{\mathcal{N}}\left[c_1 |\mathbf{q}_1\rangle + c_2 |\mathbf{q}_2\rangle\right] \neq c_1\hat{\mathcal{N}}\left[\mathbf{q}_1\right] + c_2\hat{\mathcal{N}}\left[\mathbf{q}_2\right]
$$

따라서 비선형 연산자 작용 전체는 상태의 선형 결합에 대해 중첩 원리(Superposition Principle)가 성립하지 않는다.상태 공간 내에서 입력 벡터의 크기와 방향에 따라 변형률이 달라지는 비선형 사상 $\mathbf{F}[\mathbf{q}]$를 정의해야 한다.

**국소 해석의 필요성:** 비선형 연산자를 다루기 위해서는 상태 공간의 특정 점 주변에서 연산자를 **국소적으로 선형화(Local Linearization)** 하는 해석 체계가 필요하며, 이를 위해 변분 연산자 $\delta$의 정의가 후속챕터에서 다루어진다.

---