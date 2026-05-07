+++
title = "(b) Theory3"
weight = 12
+++

---

### 1. 변분 연산자 $\delta$의 정의와 위계

변분 연산자 $\delta$는 힐베르트 공간의 벡터를 다루는 일반 연산자보다 상위 층위에 존재하는 **슈퍼 연산자(Super-operator)** 이다. 이는 연산자 대수(Operator Algebra) 위에서 정의되는 **미분 사상(Derivation)** 으로 규정된다.

변분 연산자는 다음의 세 가지 공리를 완벽하게 만족한다.

**1) 선형성 (Linearity)**

$$
\delta(c_1 \hat{A} + c_2 \hat{B}) = c_1 \delta \hat{A} + c_2 \delta \hat{B}
$$

**2) 라이프니츠 법칙 (Leibniz Rule)**

$$
\delta(\hat{A} \hat{B}) = (\delta \hat{A}) \hat{B} + \hat{A} (\delta \hat{B})
$$

이는 연산자 곱셈의 비가환 구조를 보존하면서 변화량을 측정하는 핵심 원리이다.

**3) 수반 가환성**
   
$$
(\delta \hat{A})^\dagger = \delta (\hat{A}^\dagger)
$$

---

### 2. 자코비안: 행렬 생성기로서의 형상화

추상적인 변화의 원리인 $\delta$가 물리적 격자계(Grid System) $|\delta u\rangle$를 만날 때, 그 인과관계를 기술하는 매핑(Mapping)이 바로 자코비안이다.

**1) 인과적 매핑 식**

$$
\delta \hat{L} = \mathcal{J}_L |\delta u\rangle
$$

- **$|\delta u\rangle$ ($N \times 1$):** 원인 (격자 변위 벡터)
- **$\delta \hat{L}$ ($N \times N$):** 결과 (연산자 행렬의 일그러짐)
- **$\mathcal{J}_L$ ($N \times N \times N$):** 번역기 (자코비안 텐서)

**2) 텐서 인덱스의 물리적 주소**

자코비안의 성분 $J_{ijk}$는 다음과 같은 수리적 주소를 가진다. 이는 **"$k$번째 격자를 움직였을 때, 연산자 $L$의 $(i, j)$ 성분이 변하는 감도"** 를 의미한다.

$$
J_{ijk} = \frac{\partial L_{ij}}{\partial u_k}
$$

---

### 3. 조립 법칙 기반 2차 미분의 자코비안 유도

조립 법칙 레지듀 $\mathcal{R}(D^2) = D(RD) + (RD)D$에 슈퍼 연산자 $\delta$를 적용하여 전체 자코비안을 조립한다.

**1) 전체 변분의 전개**

라이프니츠 법칙에 의해 전체 변화량은 각 항의 변화량의 합으로 나타난다.

$$
\delta \hat{R}_{total}:= \delta \mathcal{R}(D^2) = \delta [D(RD)] + \delta [(RD)D]
$$

**2) 항별 자코비안 분해**

(1) 항 1 ($\mathcal{J}_1$)

$$\delta [D(RD)] = (\delta D)(RD) + D(\delta(RD))$$
$$\mathcal{J}_1 |\delta u\rangle = [(\mathcal{J}_D |\delta u\rangle)(RD) + D(\mathcal{J}_{RD} |\delta u\rangle)]$$

(2) 항 2 ($\mathcal{J}_2$)

$$
\delta [(RD)D] = (\delta(RD))D + (RD)(\delta D)
$$

$$
\mathcal{J}_2 |\delta u\rangle = [(\mathcal{J}_{RD} |\delta u\rangle)D + (RD)(\mathcal{J}_D |\delta u\rangle)]
$$

(3) 최종 자코비안 합성

전체 시스템의 변화율은 개별 감도 지도의 선형 합으로 완성된다.


$$
\delta \hat{R}_{total} = \mathcal{J}_1 |\delta u\rangle + \mathcal{J}_2 |\delta u\rangle = (\mathcal{J}_1 + \mathcal{J}_2) |\delta u\rangle
$$

---

### 3. 조건수

조건수(Condition Number) $\kappa(T)$는 선형 연산자 $T$가 정의된 공간에서 입력의 미세한 변화(perturbation)가 가 출력에 어느 정도의 오차를 유발하는지를 나타내는 민감도 지수이다. 바나흐 공간(Banach space) $V, W$ 사이의 가역적 선형 연산자 $T: V \to W$에 대하여, 조건수 $\kappa(T)$는 다음과 같이 정의다.

$$\
\kappa(T) = \|T\| \cdot \|T^{-1}\|
$$

여기서 $\|T\|$는 연산자 노름(Operator Norm)을 의미한다. 만약 $T$가 가역적이지 않다면 조건수는 $\infty$로 정의된다. 이 수치는 $T$라는 연산자가 벡터의 크기를 최대 얼마큼 늘릴 수 있는지($\|T\|$)와, 역연산 $T^{-1}$이 벡터를 최대 얼마큼 늘릴 수 있는지($\|T^{-1}\|$)의 곱으로 이해할 수 있다.

상대 오차의 전파 (Error Propagation)연산자 방정식 $Tx = b$를 생각한다. 입력 $b$에 오차 $\delta b$가 발생하여 해가 $x + \delta x$가 되었다고 가정하면 다음과 같은 관계가 성립한다.

$$
T(x + \delta x) = b + \delta b \implies T \delta x = \delta b \implies \delta x = T^{-1} \delta b
$$

노름의 성질에 의해,

$$
\|\delta x\| \le \|T^{-1}\| \|\delta b\|, \quad $\|b\| = \|Tx\| \le \|T\| \|x\| \implies \frac{1}{\|x\|} \le \frac{\|T\|}{\|b\|} 
$$

위 식들을 결합하면 상대 오차에 대한 상한선을 도출할 수 있다.

$$
\frac{\|\delta x\|}{\|x\|} \le (\|T\| \|T^{-1}\|) \frac{\|\delta b\|}{\|b\|} = \kappa(T) \frac{\|\delta b\|}{\|b\|}
$$

이 식은 입력의 상대 오차 $\frac{|\delta b|}{|b|}$가 연산 과정에서 최대 $\kappa(T)$배만큼 증폭되어 결과의 상대 오차 $\frac{|\delta x|}{|x|}$에 영향을 줄 수 있음을 시사합니다.


---

### 4. 연산자 힐링

**1) 연산자 힐링의 목표 (Operator-level Objective)**

특정 해($|\psi\rangle$)에 의존하는 에러를 줄이는 것이 아니라, 시스템의 연산자 구조($\hat{R}$) 자체가 가진 비대칭성을 개선하는 것이다. 따라서 목적 함수는 다음과 같이 정의되어야 한다. 여기서 $u$는 연산자 인덱스 위치에서의 값에 대한 집합을 의미한다.

$$
\hat{R}(u + \delta u) = \mathbf{0} \quad (\text{Zero Operator/Matrix})
$$

선형화와 자코비안의 작용이를 현재 격자 위치 $u$에서 다음과 같다.

$$
\hat{R}(u) + \delta \hat{R} = \mathbf{0}
$$

여기서 $\delta \hat{R}$은 연산자의 변화량이며, 슈퍼 연산자(자코비안 텐서) $\mathcal{J}$와 격자 변위 $|\delta u\rangle$의 결합으로 유도된다.

$$
\delta\hat{R} = \mathcal{J}_{total} |\delta u\rangle
$$

이제 이 관계식을 위 식에 대입하면, 상태 벡터가 배제된 순수한 연산자 방정식이 도출된다.

$$
\mathcal{J}_{total} |\delta u\rangle = - \hat{R}_{total}(u)
$$

여기서 격자를 얼마만큼 옮겨야 하는지 알아야 하므로, 자코비안의 역행렬을 양변에 취하면, 구할 수 있다.

$$
|\delta u\rangle = - \mathcal{J}_{total}^{-1} \hat{R}_{total}(u)
$$

**2) 자코비안 알고리즘의 적합성 논거**

왜 이 합성 자코비안이 힐링에 최적인가?

- 결합(Coupling)의 동시 제어: 하나의 격자 이동 $|\delta u\rangle$이 유발하는 $\hat{D}(\mathcal{R}\hat{D})$와 $(\mathcal{R}\hat{D})\hat{D}$의 상호 간섭을 자코비안 행렬 내에서 동시에 처리한다.
- 수리적 정직성: 근사적인 $\mathcal{R}(\hat{D}^2)$가 아닌, 조립 법칙을 통한 엄밀한 변분 경로를 따르므로 수치적 수렴 속도가 기하급수적으로 향상된다.

---

### 5. weight의 적용

**1) 왜 선형대수학은 $W=1$을 가정하는가?**

표준 선형대수학 교과서에서 내적(Inner Product)은 보통 다음과 같이 정의된다.
$$\langle \mathbf{a}, \mathbf{b} \rangle = \mathbf{a}^T \mathbf{b} = \sum_{i=1}^N a_i b_i$$

이 식에는 **웨이트 $W$가 없는 것이 아니라, $W=1$인 단위 행렬($I$)이 생략된 것** 이다.

- 추상화(Abstraction): 수학자들에게 인덱스 $i$는 단순히 "데이터가 담긴 칸"일 뿐이다. 그 칸과 칸 사이의 물리적 거리나 기하학적 의미는 고려 대상이 아니다.
- 균일 격자(Uniform Grid): 격자가 일정하다면 $W$는 전체 식에서 공통 상수로 묶여 밖으로 빠져나간다. 결국 정규화(Normalization) 과정에서 사라지므로 굳이 쓸 필요가 없다.

**2) '데이터 공간'과 '물리 공간'의 충돌**

- **데이터 공간**: 단순히 $N$개의 숫자가 나열된 벡터. (선형대수의 관점)
- **물리 공간**: 어떤 점은 $0.1\text{nm}$를 담당하고, 어떤 점은 $10\text{nm}$를 담당하는 불평등한 세계. (수치 해석의 관점)
- 만약 $W$ 없이 내적을 수행한다면, 그것은 **"서울의 인구 밀도"와 "강원도의 인구 밀도"를 그냥 더해서 "대한민국의 총 인구"라고 주장하는 것** 과 같다. 면적($W$)을 곱하지 않은 총량은 물리적으로 아무런 의미가 없다.
- Sturm-Liouville 문제에서 가중치 함수 $w(x)$가 등장하는 이유도, 그 함수가 정의된 공간이 **'평평하지 않기 때문'** 이다. $W$를 곱해주는 행위는 이 구부러진 공간에서 **'물리적 보존 법칙'을 회복** 하는 유일한 수단이다.

**3) 연산자에 웨이트가 필요한 이유**

아래를 반영해야 정확한 해석이 가능하다.

- 격자 위에서 물리량이 얼마나 변하는가? ($\delta \psi$)
- **격자가 이동하면서 그 격자가 차지하는 '영토'가 얼마나 변하는가? ($\delta W$)**

이 때, 웨이트를 반영한 레지듀 연산자는 다음과 같다.

$$
\hat{R} = \mathcal{R}(\hat{W}\hat{L}) = \hat{W}\hat{L} - \hat{L}^\dagger \hat{W}
$$

proof)

공리에서 행렬(이산 공간) 표현을 빌려오면, 슈퍼 연산자 $\mathcal{R}$의 작용은 대수적으로 다음과 같이 정의된다.

$$
\mathcal{R}(\hat{A}) = \hat{A} - \hat{A}^\dagger
$$

실수 행렬 공간에서는 $\hat{A}^\dagger = \hat{A}^T$이다. 조립한 가중치가 부여된 물리적 연산자(Stiffness Matrix) $\hat{A} = \hat{W}\hat{L}$ 을 슈퍼 연산자 $\mathcal{R}$ 에 대입한다.

$$
\mathcal{R}(\hat{W}\hat{L}) = (\hat{W}\hat{L}) - (\hat{W}\hat{L})^\dagger
$$

여기서 수반 연산자의 분배 법칙 $(AB)^\dagger = B^\dagger A^\dagger$ 를 적용한다.

$$
\mathcal{R}(\hat{W}\hat{L}) = \hat{W}\hat{L} - \hat{L}^\dagger \hat{W}^\dagger
$$

$\hat{W}$는 각 격자의 부피(Weight)를 나타내는 '실수 대각 행렬'이므로, 그 자체로 완벽한 자기 수반(Self-adjoint)이다. 즉, $\hat{W}^\dagger = \hat{W}$ 이다. 이를 대입하면 최종적으로 다음 식이 도출된다.

$$
\mathcal{R}(\hat{W}\hat{L}) = \hat{W}\hat{L} - \hat{L}^\dagger \hat{W}
$$

**4) 최종 힐링 레지듀의 변분 전개

$$
\delta \hat{R} = \delta (\hat{W}\hat{L} - \hat{L}^\dagger \hat{W})
$$

라이프니츠 법칙 $\delta(\hat{A}\hat{B}) = (\delta\hat{A})\hat{B} + \hat{A}(\delta\hat{B})$ 를 엄밀하게 적용하면 다음과 같이 네 개의 항으로 분해된다.

$$
\delta \hat{R} = (\delta \hat{W})\hat{L} + \hat{W}(\delta \hat{L}) - (\delta \hat{L}^\dagger)\hat{W} - \hat{L}^\dagger(\delta \hat{W})
$$

---
