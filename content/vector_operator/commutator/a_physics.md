+++
title = "(a) Physics"
weight = 2
+++

---

### 1. 물리적 의미1, 동시측정 가능성

교환자는 두 물리량을 동시에 얼마나 정확하게 알 수 있는지를 판별하는 '측정 호환성 테스트'이다. **측정이란 어떤 고유값을 선택(중복포함하여)하는 것** 이다. 예로, $\hat{H}$ 를 기준으로 측정하여라 하면, $\hat{H}$ 고유값(중복고유값 포함) 중 하나가 임의로 선택되는 것을 말한다.

$$
|\psi\rangle \xrightarrow{\text{Measure=Pick}} \lambda^\text{중복도,3}(|\lambda_1^3\rangle+|\lambda_2^3\rangle+|\lambda_3^3\rangle)
$$


**(1) 교환하는 경우 ($[\hat{A}, \hat{B}] = 0$): 양립 가능한 측정량**

두 물리량은 **'양립 가능(compatible)'** 하며 동시에 확정된 값을 가질 수 있다. 하나의 양을 측정하는 행위가 다른 양의 상태를 교란시키지 않는다.

**(2) 교환하지 않는 경우 ($[\hat{A}, \hat{B}] \neq 0$): 양립 불가능한 측정량**

두 물리량 사이에는 **불확정성 원리(Uncertainty Principle)** 가 존재한다. 하나의 양을 정확하게 측정하면 다른 양의 정보가 필연적으로 불확실해진다.

---

### 2. 물리적 의미2, CSCO

연산자는 고유벡터를 만나면, 고유벡터를 스케일링 한다. 하지만 하나의 연산자만으로는 시스템의 상태를 완벽하게 특정할 수 없는 경우가 많다. 이때 **완비적 교환 연산자 집합(CSCO, Complete Set of Commuting Observables)** 이 필요하다. 예로 수소원자의 CSCO를 살펴보자. 수소 원자 시스템에서 에너지 연산자($\hat{H}$)만으로는 상태를 특정할 수 없다. 이는 고유값 $E_n$에 대해 여러 개의 상태가 존재하기 때문이다.

$$
\hat{H} |n, l, m_l, m_s\rangle = -\frac{13.6\text{ eV}}{n^2} |n, l, m_l, m_s\rangle
$$

여기서 고유값 $E_n$은 $l, m_l, m_s$ 에 의존하지 않는다. 즉, 하나의 $n$에 대해 $2n^2$개의 상태가 겹쳐 있다.  아래의 연산자들은 서로 교환 가능하다. 따라서, 공통 고유함수 존재가 보장된다.

$$
[\hat{H}, \hat{L}^2] = [\hat{H}, \hat{L}_z] = [\hat{L}^2, \hat{L}_z] = 0
$$


- 궤도 모양 특정: $\hat{L}^2 |n, l, m_l, m_s\rangle = l(l+1)\hbar^2 |n, l, m_l, m_s\rangle$
- 궤도 방향 특정: $\hat{L}_z |n, l, m_l, m_s\rangle = m_l\hbar |n, l, m_l, m_s\rangle$
- 스핀 방향 특정: $\hat{S}_z |n, l, m_l, m_s\rangle = m_s\hbar |n, l, m_l, m_s\rangle$

이 네 가지 고유값의 집합 ${n, l, m_l, m_s}$이 결정되어야만 힐베르트 공간 내의 단 하나의 벡터 $|n, l, m_l, m_s\rangle$를 지칭할 수 있다. 이것이 CSCO의 수학적 실체이다. 이해를 돕기 위해, 중복된 고유값을 가진 행렬 $A$를 다른 행렬 $B$로 분리하는 과정을 수식화해 보자.

$$
A = \begin{bmatrix}
2 & 0 & 0 \\
0 & 2 & 0 \\
0 & 0 & 5
\end{bmatrix}, \quad
B = \begin{bmatrix}
1 & 0 & 0 \\
0 & -1 & 0 \\
0 & 0 & 3
\end{bmatrix}
$$

- 연산자 $A$의 관측: 고유값 $2$를 측정했을 때, 시스템은 $|u_1\rangle = \begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix}^T$ 인지 $|u_2\rangle = \begin{bmatrix} 0 \\ 1 \\ 0 \end{bmatrix}^T$ 인지 알 수 없다. (중복도 2)
- 연산자 $B$의 도입: $[A, B] = 0$이므로 공통 기저를 가진다. $B$를 측정하여 고유값 $1$을 얻었다면, 우리는 시스템이 정확히 $|u_1\rangle$ 상태임을 확신할 수 있다.

---
