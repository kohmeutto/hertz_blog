+++
title = "CHAPTER 3"
weight = 16
+++

---

### CHAPTER 3. 이산 교환자 오차 및 대수적 전제조건화

본 장에서는 2장에서 도출된 대류 잔차 약형식을 이산 공간의 선형 대수 시스템으로 사상한다. 이를 기반으로 r-적응형(r-adaptive) 위상 사상을 수행하고, 시스템의 비대칭성을 제어하기 위한 대칭 전제조건자(symmetric preconditioner)를 설계한다.

---

### 3.1 이산 교환자 오차 기반의 국소 비대칭 지표 도출

이산화 대상은 유효 속도장의 발산이 상태 함수에 작용하는 성분인 $(Dv)\psi$ 이다. 이를 직접 점-평가(point-wise evaluation)할 경우 발생하는 수치적 진동을 제어하기 위해, $D(v\psi) = (Dv)\psi + v(D\psi)$ 를 역으로 변환한 관계식을 이용한다.

$$
(Dv)\psi = D(v\psi) - v(D\psi)
$$

상태 함수 $\psi$ 와 유효 속도장 $v$ 에 대한 노드 $k$ 에서의 전체 물리량 이산 미분 합산은 $[D(v\psi)]_k = \sum_{j} \hat{D}_{kj} (v_j \psi_j)$ 이다. 이산 미분 연산자의 특성에 따라 각 행의 가중치 합은 영($\sum_j \hat{D}_{kj} = 0$)이 되므로, 이에 기초하여 $v_k \psi_k \sum_j \hat{D}_{kj} = 0$ 이 성립한다. 이를 초기 합산식에서 감산한다.

$$
[D(v\psi)]_k = \sum_{j} \hat{D}_{kj} (v_j \psi_j - v_k \psi_k)
$$

대수적 항등식 $v_j \psi_j - v_k \psi_k = (v_j - v_k)\psi_j + v_k(\psi_j - \psi_k)$ 를 적용하여 식을 분리한다.

$$
[D(v\psi)]_k = \sum_{j} (v_j - v_k) \hat{D}_{kj} \psi_j + \sum_{j} v_k \hat{D}_{kj} (\psi_j - \psi_k)
$$

두 번째 합산항은 $\sum_j v_k \hat{D}_{kj} \psi_j - v_k \psi_k \sum_j \hat{D}_{kj}$ 로 전개되며 영합 조건에 의해 $\sum_j v_k \hat{D}_{kj} \psi_j$ 로 환원된다. 이는 이류항 $v(D\psi)$ 의 이산 형태이다. 결과적으로 $(Dv)\psi$ 의 이산 사상 결과는 첫 번째 합산항으로 확정되며, 이를 수식으로 나타내면 다음과 같다.

$$
(Dv)\psi = \sum_{j} (v_j - v_k) \hat{D}_{kj} \psi_j
$$

연속계 잔차 $(Dv)\psi + 2v(D\psi)$ 에 해당하는 이산 형태를 각각 대입하여 결합하면 노드 $k$ 에 작용하는 국소적 단방향 텐션(directional tension) $\mathcal{T}_{kj}$ 가 산출된다.

$$
\mathcal{T}_{kj} = (v_j + v_k) \hat{D}_{kj} \psi_j
$$

노드 간 교차 텐션 지표 $S_{kj}$ 는 방향성 상쇄를 방지하기 위해 절댓값의 산술 평균으로 정의한다.

$$
S_{kj} = \frac{1}{2} \left( |\mathcal{T}_{kj}| + |\mathcal{T}_{jk}| \right)
$$

정규화된 지표 $\bar{S}_{kj}$를 바탕으로 노드 간 가중치 행렬 $W_{kj} = 1.0 + \bar{S}_{kj}$ 를 정의한다. 이 가중치 $W_{kj}$ 는 이산 격자망을 가상의 스프링 네트워크로 간주할 때, 인접한 두 노드를 연결하는 스프링의 국소적 강성으로 작용한다. 시스템의 전체 변형 에너지가 최소화되는 평형 상태는 각 내부 노드 $i$ 에 작용하는 장력의 합이 영벡터가 되는 조건으로 규명된다.

$$
\sum_{j \in \mathcal{N}(i)} W_{ij} (\mathbf{X}_j - \mathbf{X}_i) = \mathbf{0}
$$

이 국소 평형 조건들을 전역 시스템으로 확장하면 그래프 라플라시안 $\hat{L}_{sys} = \hat{K} - \hat{W}$ 을 통한 행렬식 $\tilde{L}_{sys} \mathbf{X}_{new} = \mathbf{B}_{ref}$ 가 구성된다. 이를 통해 도출된 좌표계 $\mathbf{X}_{new}$ 상의 각 노드 체적 $V_k^*$를 다시 계산하여 다음의 듀얼 체적 메트릭(dual volume metric)을 산출한다.

$$
\hat{G} = \text{diag}(V_0^*, V_1^*, \dots, V_{N-1}^*)
$$

교환자 오차 기반의 국소 지표를 가중 그래프 라플라시안(Weighted Graph Laplacian) 시스템으로 추상화하여 조화 사상을 수행하는 본 방식은, 오차 구배가 집중되는 영역으로 노드를 밀집시키면서도 이산 시간 적분 과정에서 자코비안 행렬식의 양수(positivity) 특성을 대수적으로 보존한다. 이를 통해 극단적인 특이 섭동 조건 하에서도 격자 요소가 뒤집히는 격자 꼬임(mesh tangling) 현상을 원천적으로 회피하며 기하학적 정칙성(regularity)을 유지할 수 있다.

---

### 3.2 대수적 투영 기반의 대칭 전제조건자 설계

산출된 기하학적 메트릭 $\hat{G}$와 변환을 위한 대각 행렬 $\hat{C}$를 잔차 벡터 $F(u)$에 적용하여 새로운 시스템 $\tilde{F}(u) = \hat{C}\hat{G}F(u) = 0$을 구성한다. 상태 변수가 $u+\delta u$로 섭동할 때 1차 근사는 다음과 같다.

$$
\tilde{F}(u+\delta u) \approx \tilde{F}(u) + \left( \frac{\partial\hat{C}}{\partial u}\hat{G}F(u) + \hat{C}\frac{\partial\hat{G}}{\partial u}F(u) \right) \delta u + \hat{C}\hat{G}\hat{J}\delta u
$$

뉴턴 반복이 진행됨에 따라 $F(u) \to 0$ 이면, 유효 자코비안은 $\tilde{J} = \hat{C}\hat{G}\hat{J}$로 근사된다. ($\hat{J}$는 원본 자코비안이다.)

유효 자코비안 $\tilde{J}$의 대칭성을 유도하기 위해 교차 비대각 성분에 대한 크기 보존 제약 조건 $|\tilde{J}_{ij}| = |\tilde{J}_{ji}|$ 를 부과한다. 이를 성분별로 전개하면 다음과 같은 등식이 요구된다.

$$
c_i |(\hat{G}\hat{J})_{ij}| = c_j |(\hat{G}\hat{J})_{ji}|
$$

대각 성분을 지수 함수 $c_i = e^{x_i}$ 로 설정하여 양수 조건을 만족시킨 후 양변에 자연로그(natural logarithm)를 취하여 대수적 차이 $b_{ij}$를 도출한다. 이것은 인접한 두 노드 $i$ 와 $j$ 를 연결하는 간선(Edge) 상에 정의되는 벡터적 지표이다.

$$
\ln(c_i) - \ln(c_j) = \ln\left( \frac{|(\hat{G}\hat{J})_{ji}|}{|(\hat{G}\hat{J})_{ij}|} \right) \equiv b_{ij}
$$

치환 변수 $x_i = \ln(c_i)$에 대하여, 위 식은 $\hat{S}\mathbf{x} = \mathbf{b}$ 형태의 과결정(overdetermined) 선형 연립방정식이다. 이것을 통해 산출된 $x_i$ 는 각 간선들에 흩어져 있는 국소 비대칭 지표 $b_{ij}$ 의 보존성(무회전) 성분을 도메인 전체에 대해 공간 적분하여 도출해 낸 전역적 포텐셜 장(Potential field)을 의미한다.

 디리클레 경계 노드에 기준점 조건을 부과한 후 최소자승법(least squares method)을 통해 해 $\mathbf{x}_{LS}$를 산출하고 대각 행렬 $\hat{C}$를 확정한다. 해당 선형 시스템을 해석하기 위해 적용된 이산 헬름홀츠-호지 분해(DHHD)와 비대칭 성분의 상쇄 효율 분석은 Appendix A에 상술되어 있다.

---

### 3.3 대수적 맵핑 벡터의 기하학적·물리적 동치성 증명

$b_{ij}$ 지표는 원본 자코비안 행렬 내부에서 물리적 표류 속도와 기하학적 체적비에 의해 발생하는 플럭스의 국소적 불균형(Imbalance)을 나타낸다. 연속계 자코비안 연산자 내부의 식 $-p\nabla \psi + \mathbf{v}\psi$ 에 대한 잔차 방정식 $F_i = 0$ 은 유한체적법(FVM) 원리에 따라 가우스 발산 정리가 적용되어 노드 $i$ 의 체적 표면적 $\partial \Omega_i$ 에 대한 면적분으로 변환된다.

$$
\iint_{\partial \Omega_i} (-p \nabla \psi + \mathbf{v} \psi) \cdot \mathbf{n} dA = \sum_{j} \Gamma_{i \to j}
$$

간선의 단위 방향 벡터를 $\mathbf{e}_{ij}$ 라 하고 1차원 좌표를 $\xi$ 로 설정하면, 단면적 $A_{ij}$ 에 대한 1차원 방향 도함수는 $\Gamma_{i \to j} = A_{ij} ( -p(\xi)\frac{d\psi}{d\xi} + v(\xi)\psi )$ 이다. (단, $v(\xi) = \mathbf{v} \cdot \mathbf{e}_{ij}$).간선 내부는 소스항이 부재하므로 해당 상미분방정식은 공간에 독립적인 상수 $C^*$ 이다. 적분 인자(integrating factor)를 적용하여 완전 미분 형태로 치환한다.

$$
\frac{C^*}{p(\xi)} \exp\left(-\int_{\xi_i}^\xi \frac{v(s)}{p(s)} ds\right) = -\frac{d}{d\xi} \left[ \psi(\xi) \exp\left(-\int_{\xi_i}^\xi \frac{v(s)}{p(s)} ds\right) \right]
$$

구간 $[\xi_i, \xi_j]$ 에 대하여 정적분하면 노드 상태 변수에 대한 관계식이 도출된다.

$$
C^* = \frac{1}{R_{ij}} \psi_i - \frac{1}{R_{ij}}\exp\left(-\int_{\xi_i}^{\xi_j} \frac{v(s)}{p(s)} ds\right) \psi_j
$$

여기서 유효 기하 저항 $R_{ij}$ 는 다음과 같이 정의된다.

$$
R_{ij} \equiv \int_{\xi_i}^{\xi_j} \frac{1}{p(\xi)} \exp\left(-\int_{\xi_i}^\xi \frac{v(s)}{p(s)} ds\right) d\xi
$$

이산 자코비안 행렬 $\hat{J}$ 의 교차 결합 성분은 $\hat{J}_{ij} = \partial F_i / \partial \psi_j$ 이다. 대각 메트릭 $\hat{G}$ 가 곱해진 맵핑 벡터 $b_{ij}$ 에 이를 대입한다.

$$
b_{ij} \equiv \ln \left( \frac{V_j^* |\hat{J}_{ji}|}{V_i^* |\hat{J}_{ij}|} \right)
$$

면적 대칭성($A_{ij} = A_{ji}$)으로 인해 단면적과 기하 저항 $R_{ij}$ 가 약분되며, 벡터 $b_{ij}$ 는 기하 체적비와 물리적 페클레 장(Péclet field)의 1차원 선적분 합으로 환원된다.

$$
b_{ij} = \ln\left(\frac{V_j^*}{V_i^*}\right) + \int_{\xi_i}^{\xi_j} \frac{v(s)}{p(s)} ds \equiv \ln\left(\frac{V_j^*}{V_i^*}\right) + \int_i^j \left(\frac{\mathbf{v}}{p}\right) \cdot d\mathbf{l}
$$

---

### 3.4 유효 자코비안의 반대칭 성분 고립과 탐색 행렬 구성

유효 자코비안 $\tilde{J}$는 대칭 성분 $\hat{H} = \frac{1}{2}(\tilde{J} + \tilde{J}^T)$와 반대칭 성분 $\hat{A}{raw} = \frac{1}{2}(\tilde{J} - \tilde{J}^T)$로 분리된다. 내부 도메인 $\mathcal{I}$에 대응하는 반대칭 성분 $\hat{A}_{int}$를 고립시키기 위해, 경계 노드에서 0, 내부 노드에서 1을 가지는 대각 행렬 $\hat{M}_s$를 사용하여 전후에 곱한다.

$$
\hat{A}_{int} = \hat{M}_s \hat{A}_{raw} \hat{M}_s
$$

고유 비대칭 성분 $\hat{A}_{int}$를 지배 방정식의 우변 잔차 $F(u)$에는 보존하되, 선형 솔버의 탐색 행렬인 전제조건자 $\hat{J}_{pure}$ 를 구성할 때에는 이를 대수적으로 감산하여 분리한다.

$$
\hat{J}_{pure} = \tilde{J} - \hat{A}_{int}
$$

본 연구는 대칭 전제조건자 $\hat{J}_{pure}$를 탐색 행렬로 사용하는 부정확 뉴턴법(Inexact Newton Method)을 채택한다. 선형화 시스템 $\hat{J}_{pure} \delta u = -F(u)$ 에 대하여 수렴 상태($\delta u \to 0$)에 도달하면 항등적으로 물리적 잔차 $F(u^*) = 0$ 이 성립한다. 이와 같이 구성된 전제조건자 연산자의 스펙트럼(spectrum)이 제한된 복소 원판 내에 위치하여 수렴성이 보장됨을 입증하는 해석학적 증명은 Appendix B에 기술되어 있다.

---

### Appendix A. 그래프 라플라시안과 이산 헬름홀츠-호지 분해

과결정 연립방정식 $\hat{S}\mathbf{x} = \mathbf{b}$ 의 목적 함수를 최소화하는 해 $\mathbf{x}_{LS}$ 를 구하기 위한 정규 방정식(Normal equation)을 구성한다. 

$$
(\hat{S}^T \hat{S}) \mathbf{x}_{LS} = \hat{S}^T \mathbf{b}
$$

여기서 행렬 $\hat{S}^T \hat{S}$ 는 그래프 라플라시안(Graph Laplacian) 연산자이다. 이산 헬름홀츠-호지 정리(DHHD)에 근거하여, 임의의 간선 벡터 $\mathbf{b}$ 는 다음과 같이 직교 분해된다.

$$
\mathbf{b} = \hat{S} \mathbf{x}_{LS} + \mathbf{r}
$$

투영 성분 $\hat{S} \mathbf{x}_{LS}$ 는 보존적 무회전(Irrotational) 성분으로, 이는 대수적인 스칼라 포텐셜 장으로 사상된다. 잔차 $\mathbf{r}$ 은 순환(circulation) 성분으로 행렬의 좌영공간(Left null space)에 속하며 직교 조건을 만족한다($\hat{S}^T \mathbf{r} = 0$).

두 벡터는 직교하므로 피타고라스 정리에 의해 $\| \mathbf{b} \|_2^2 = \| \hat{S}\mathbf{x}_{LS} \|_2^2 + \| \mathbf{r} \|_2^2$ 식이 성립한다. 이 관계로부터 시스템의 보존성 비대칭 성분이 해소되는 상쇄 효율(cancellation ratio) $\eta$ 를 산출한다.

$$
\eta = \frac{\|\hat{S}\mathbf{x}_{LS}\|_2^2}{\|\mathbf{b}\|_2^2} = 1 - \frac{\|\mathbf{r}\|_2^2}{\|\mathbf{b}\|_2^2}
$$

---

### Appendix B. 전제조건화된 연산자의 스펙트럼 상한 및 수렴성 증명

목표 연산자 $\hat{J}_{pure}^{-1} \tilde{J}$의 고유값을 $\lambda \in \mathbb{C}$, 이에 대응하는 고유 벡터를 $\mathbf{x} \in \mathbb{C}^n$이라 정의한다. 연산자는 대칭 성분 $\hat{H}$ 와 반대칭 성분의 합으로 구성되어 $\tilde{J} = \hat{H} + \hat{A}_{raw}$ 이며 $\hat{J}_{pure} = \hat{H} + \hat{A}_{bnd}$ 로 분해된다. (단, $\hat{A}_{bnd} = \hat{A}_{raw} - \hat{A}_{int}$ 이다.) 이를 기반으로 일반화된 고유값 문제 $\tilde{J} \mathbf{x} = \lambda \hat{J}_{pure} \mathbf{x}$ 에 대입하고 전개한다.

$$
(\hat{J}_{pure} + \hat{A}_{int}) \mathbf{x} = \lambda \hat{J}_{pure} \mathbf{x}
$$

$$
\hat{A}_{int} \mathbf{x} = (\lambda - 1) \hat{J}_{pure} \mathbf{x}
$$

양변의 좌측에 고유 벡터의 켤레 전치 $\mathbf{x}^*$를 곱하여 이차 형식을 구성한다(정규화 조건 $\|\mathbf{x}\| = 1$). 양의 정부호 성질에 의해 $\mathbf{x}^* \hat{H} \mathbf{x} = h > 0$ 이며, 반대칭성에 의해 실수 $\alpha, \beta \in \mathbb{R}$ 에 대하여 $\mathbf{x}^* \hat{A}_{int} \mathbf{x} = i\alpha$, $\mathbf{x}^* \hat{A}_{bnd} \mathbf{x} = i\beta$ 로 정의된다. 이를 치환하면 다음 식을 얻는다.

$$
i\alpha = (\lambda - 1)(h + i\beta)
$$

위 식을 전개하여 $\lambda - 1 = \frac{i\alpha}{h + i\beta}$ 를 유도한 뒤, 고유값 중심 이동 규모 $|\lambda - 1|^2$을 산출한다.

$$
|\lambda - 1|^2 = \frac{\alpha^2}{h^2 + \beta^2}
$$

분모에서 $\beta^2 \ge 0$ 이므로 다음 부등식이 확립된다.$$|\lambda - 1| \le \frac{|\alpha|}{h} = \frac{|\mathbf{x}^* \hat{A}_{int} \mathbf{x}|}{\mathbf{x}^* \hat{H} \mathbf{x}}$$대칭 연산자 $\hat{H}$에 대한 반대칭 연산자 $\hat{A}_{int}$의 상대적 연속성 상수(relative continuity constant)를 $\gamma_{int} \equiv \sup_{\mathbf{x} \ne 0} \frac{|\mathbf{x}^* \hat{A}_{int} \mathbf{x}|}{\mathbf{x}^* \hat{H} \mathbf{x}}$ 로 정의할 때, 전제조건화된 연산자의 스펙트럼 $\sigma(\hat{J}_{pure}^{-1} \tilde{J})$는 다음 부등식 집합에 포함된다.

$$
\sigma(\hat{J}_{pure}^{-1} \tilde{J}) \subset \{ \lambda \in \mathbb{C} : |\lambda - 1| \le \gamma_{int} \}
$$

이는 제안된 전제조건자가 선형화 연산자의 고유값 분포를 복소 평면 상의 제한된 원판 내로 군집시킴을 의미하며, 이를 통해 Krylov 해법의 선형 수렴성이 대수적으로 보장된다.

---
