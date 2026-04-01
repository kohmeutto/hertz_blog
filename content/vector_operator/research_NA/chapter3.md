+++
title = "CHAPTER 3"
weight = 15
+++

---

### 3.1 이산 공간 국소 비대칭 지표 $S_k$와 기하학적 메트릭 $\hat{G}$의 대수적 매핑

본 절에서는 2장에서 확립된 연속계 공리가 이산 공간으로 투영될 때 발생하는 대수적 매핑(isomorphic mapping) 과정을 수학적으로 보여준다. 연속 공간의 물성 결합 미분 연산자 내부 레지듀가 이산 공간의 전역적 비대칭 지표로 환원되는 과정을 전개하고 이를 바탕으로 시스템의 기하학적 대칭성을 1차적으로 제어하는 메트릭 $\hat{G}$가 대수적 필수 조건으로서 선언되는 수리적 근거를 확립한다.

**1) 이산 공간 국소 비대칭 지표 $S_k$의 대수적 사상 정의**

2.5절에서 도출된 연속 공간의 잔류 구배 사상 $\mathcal{R}(p\nabla)$를 유한 차원 이산 격자망(Discrete Mesh) 위로 투영하기 위해, 국소 변동성 범함수(Local Variation Functional) $\mathcal{V}_k$를 정의한다. 도메인 내의 임의의 중심 노드 $k$와 그에 인접한 위상적 이웃 노드 집합을 $\mathcal{N}(k)$라 할 때, $\mathcal{V}_k$는 국소 물성 장(Local property field)을 단일한 스칼라 텐션 지표로 변환하는 사상(Mapping)으로 작동한다. 즉, $\mathcal{V}_k : \mathbb{R}^{|\mathcal{N}(k)|+1} \to \mathbb{R}_{\ge 0}$ 이며, 국소 비대칭 지표 $S_k$는 다음과 같이 형식화된다.

$$
S_k = \mathcal{V}_k(p) = \left\| \left\{ \mathcal{D}(p_k, p_j) \right\}_{j \in \mathcal{N}(k)} \right\|_{\ell}
$$

여기서 연산자 $\mathcal{D}: \mathbb{R} \times \mathbb{R} \to \mathbb{R}$ 는 중심 노드 $k$와 이에 위상적으로 연결된(Topologically connected) 이웃 노드 $j$ 사이에서 발현되는  국소적 상태 변동(Local state variation)을 추출하는 차분 연산자이며, $\| \cdot \|_{\ell}$ 은 추출된 변동량의 집합을 노드 $k$에 대한 단일 스칼라값으로 집계하는 이산 공간 노름(Discrete Spatial Norm)이다.이 대수적 구조는 연속계에 고립되어 있던 물성 구배의 비대칭성 정보를, 특정 이산화 기법(FDM, FEM, FVM 등)의 기하학적 형태에 종속되지 않고 이산 위상 공간(Discrete topological space)의 텐션으로 1:1 치환(Isomorphic projection)하는 일반화된 틀을 제공한다.물성 $p$의 공간적 변화가 국소적으로 완만하여 선형적 테일러 전개가 유효한 경우, 차분 연산자를 순수 이산 그래디언트($\mathcal{D}(p_k, p_j) = \hat{\nabla}_{kj} p_j$)로 취하고, 합산 노름($\ell = 1$, $L_1$-norm)을 적용한다.

$$
S_k = \left| \sum_{j \in \mathcal{N}(k)} \hat{\nabla}_{kj} p_j \right|
$$

이는 이산 그래디언트 행렬의 영공간(Null-space) 보존 원리를 가장 직관적으로 만족하는 고전적 형태이다. 그러나 반도체 물성 모델($p \propto \exp(-2u)$)과 같이 물리량이 지수함수적으로 급변하는 특이계(Singular system)에서는 절대적인 변화량 $\Delta p$를 거리로 나누는 선형적 접근을 취할 경우, 분모의 거리가 수축함에 따라 텐션이 무한대로 폭발하는 수치적 블랙홀 현상(Mesh tangling)이 발생한다.이를 억제함과 동시에 방향 도함수(Directional derivative)의 물리적 차원을 엄밀하게 보존하기 위해, 본 연구는 차분 연산자에 대수 사영(Logarithmic Projection)을 적용한다. 단순히 로그의 단차를 구하는 것에 그치지 않고, 이를 노드 간의 기하학적 거리 $L_{kj}$로 나누어 순수한 선밀도(Linear density) 차원의 구배로 치환한 뒤 국소 상한 노름($\ell = \infty$, $L_\infty$-norm)을 채택한다.

$$
S_k = \max_{j \in \mathcal{N}(k)} \frac{\left| \log(p_k) - \log(p_j) \right|}{L_{kj}}
$$

이 대수적 구조는 연속 공간에서의 상대적 물성 변화율 $\nabla(\ln p) = \nabla p / p$를 국소 연산 스텐실(Local computational stencil) 상에 수치적으로 안정되면서도 물리적 차원을 잃지 않도록 모사한 형태이다.

**2) 기하학적 메트릭 $\hat{G}$**

확립된 지표 $S_k$는 이산 시스템이 기하학적으로 내포하고 있는 국소적인 위상적 텐션(topological tension)을 나타낸다. 이산 공간에서 연속계의 내적 공리를 무결하게 유지하기 위해서는 이 국소 지표 $S_k$의 공간적 요동을 온전히 수용하고 대칭성을 1차적으로 보존할 수 있는 측도 행렬(measure matrix)이 선험적으로(a priori) 요구된다.각 노드 $k$가 지배하는 기하학적 제어 체적(control volume) $V_k^*$를 대각 원소로 가지는 듀얼 체적 메트릭(dual volume metric) $\hat{G}$를 다음과 같이 대수적으로 선언한다.

$$
\hat{G} = \text{diag}(V_0^*, V_1^*, \dots, V_{N-1}^*)
$$

일반적인 공간 이산화 방정식에서 불균일한 체적 $V_k^*$는 분모에 위치하여 연산자 시스템의 대수적 비대칭성($\hat{L}_{ij} \neq \hat{L}_{ji}$)을 유발하는 근원이 된다. 선언된 메트릭 $\hat{G}$를 원시 연산자에 사전 곱(pre-multiplication)하여 $\tilde{L} = \hat{G}\hat{L}$로 사영하면 체적 편차에 의한 기하학적 비대칭 요소가 대수적으로 상쇄되어 시스템의 형식적 수반성(formal-adjointness)이 1차적으로 회복된다.결과적으로 $\hat{G}$는 지표 $S_k$가 지시하는 기하학적 텐션을 극복하기 위해 이산 공간이 필연적으로 갖추어야 할 절대적 기준 좌표계가 된다. 지표 $S_k$를 목적 함수로 삼아 시스템의 총 탄성 에너지를 최소화함으로써 이 최적의 메트릭 $\hat{G}$를 동역학적으로 조립하는 과정은 4장의 대수적 진공 상태 실험을 통해 별도로 입증한다. 본 3장에서는 이 $\hat{G}$ 행렬이 이산 공간의 해석적 기반으로 작용함을 전제로 하여 시스템 내부의 비선형 동적 비대칭성을 추적하는 전역 스펙트럼 지표의 도출로 전개를 이어간다.

---

### 3.2 이산 위상 틀어짐과 대수적 텐션 스펙트럼 지표

본 절에서는 기하학적 메트릭 $\hat{G}$ 적용 이후에도 이산 격자의 비균일성에 의해 발현되는 동적 비대칭성을 정량화하고, 2.4절의 보편적 소멸 조건을 이산 자코비안 공간에 강제하여 대수적 텐션 지표를 도출한다.

**1) 시스템 연산자 보정과 유효 자코비안의 고립**

이산 격자 상에서 시스템의 비정규성을 교정하기 위해, 기하학적 메트릭 $\hat{G}$와 대각 행렬 $\hat{C}$를 원시 잔차 벡터 $R(u)$에 투영하여 보정된 잔차 시스템 $\tilde{R}(u)=\hat{C}\hat{G}R(u)=0$을 정의한다. 상태 벡터가 $u$에서 $u+\delta u$로 변할 때 1차 변분(First-order variation)을 전개하여 $\delta u$를 지배하는 선형 연산자를 추출한다.

$$
\tilde{R}(u+\delta u)\approx\tilde{R}(u)+\left(\frac{\partial\hat{C}}{\partial u}\hat{G}R(u)+\hat{C}\frac{\partial\hat{G}}{\partial u}R(u)\right)\delta u+\hat{C}\hat{G}\hat{J}\delta u
$$

단, $\hat{J}=\partial R/\partial u$는 프레셰 도함수(Fréchet derivative)로 정의되는 원시 자코비안이다. 뉴턴 반복법을 통해 시스템이 참해에 근접할수록 순수 물리 잔차는 영 벡터에 수렴한다($R(u)\to 0$). 따라서 괄호 안의 프레임워크 변분항(Framework Variation)은 소멸하며, 섭동 $\delta u$의 궤적을 지배하는 유효 자코비안(Effective Jacobian)은 마지막 항 $\tilde{J}=\hat{C}\hat{G}\hat{J}$로 환원된다. 이 변분적 결과는 대수적 보정 지표 $\hat{C}$가 원시 시스템이 아닌 섭동 공간의 자코비안에 직접 적용되어 전처리(Preconditioning)되어야 하는 해석학적 근거를 제공한다.고립된 진단 연산자 $\tilde{J}$가 수치적으로 안정된 섭동을 전파하기 위해서는, 2.4절에서 증명된 연속계 내부 레지듀의 보편적 소멸 정리($\mathcal{R}J_{int}=0$)를 이산 섭동 공간 위에서 수리적으로 만족시켜야 한다. 그러나 원시 자코비안 행렬 $\hat{J}$는 이산 절단 오차에 의해 도메인 내부 집합 $\mathcal{I}$에서 비영(non-zero) 잔류 레지듀를 발생시킨다. 따라서 보정된 자코비안 $\tilde{J}$가 연속계의 대수적 인과율을 회복하기 위한 필요충분조건은, 레지듀 사상 $\mathcal{R}(\tilde{J})$ 자체를 도메인 내부에서 강제로 영행렬화하는 것이다.

$$
\mathcal{R}(\tilde{J})_{ij}=\tilde{J}_{ij}-\tilde{J}_{ji}=0\quad(\text{for all } i, j\in\mathcal{I})
$$

**2) 수반 일관성 조건 도출과 로그 사상(Log-mapping)**

위에서 전개한 $\tilde{J}_{ij}=\tilde{J}_{ji}$ 조건에 $\tilde{J}=\hat{C}\hat{G}\hat{J}$를 대입하고 행렬 성분으로 전개하면, 다음과 같은 국소 노드 방정식이 연역된다.

$$
c_i(\hat{G}\hat{J})_{ij}=c_j(\hat{G}\hat{J})_{ji}
$$

이 비선형 결합을 선형 대수 시스템으로 변환하기 위해 양변에 로그 사상(log-mapping)을 적용한다. 이산 미분 연산자의 교차항 조립 원리에 따르면, 인접한 두 노드를 연결하는 자코비안 교차 결합 계수는 공간 간격과 물성치라는 양수 파라미터들의 조합으로 구성된다. 따라서 기하학적 편차나 비선형성에 의해 두 값의 크기가 다를지라도 대수적 부호는 동일하게 산출되는 부호 동형성(sign isomorphism)이 보장된다. 이는 로그 함수 내부가 음수가 되는 현상을 배제하며, 국소 구간의 대수적 비대칭성을 나타내는 실수 로그 비율 $b_{ij}$를 다음과 같이 추출할 수 있게 한다.

$$
\ln(c_i)-\ln(c_j)=\ln\left(\frac{(\hat{G}\hat{J})_{ji}}{(\hat{G}\hat{J})_{ij}}\right)\equiv b_{ij}
$$

새로운 변수 $x_i=\ln(c_i)$를 도입하면 격자망 상의 모든 연결 고리에 대한 비대칭 변위는 $x_i-x_j=b_{ij}$라는 선형 대수 시스템 $Ax=b$로 치환된다. 여기서 행렬 $A$는 격자의 위상적 연결 상태를 나타내는 희소 행렬(Sparse matrix)이다.

**3) 전역 해의 유일성 확보와 위상적 경계의 앵커링**

상기 유도된 선형 시스템 $x_i-x_j=b_{ij}$는 노드 간의 상대적인 대수적 텐션 차이만을 규정하므로, 계수 행렬(Coefficient matrix)이 랭크 결함(rank deficiency)을 갖는다. 전역적인 스케일을 결정하기 위해서는 최소 하나의 기준점(reference point)이 요구된다.이 기준점을 도메인 경계 부분 공간 $\mathcal{B}$로 설정하는 것은 2.3절의 벌크-경계 소산 정리를 만족하기 위한 해석학적 조치이다. 연속계 이론에서 경계 레지듀는 물리적 유량의 실체이며, 이산 공간에서는 연산자 스텐실(stencil)의 위상적 절단(topological truncation)이 발생하는 지점이다. 보정 지표 $\hat{C}$가 이 경계값을 변형하는 것은 물리적 경계 조건 자체를 왜곡하는 결과를 초래한다. 따라서 물리적 유량이 보존되어야 하는 위상적 경계 노드 집합 $\mathcal{B}$에 속하는 모든 노드 $k$에 대하여 앵커링(Anchoring) 조건을 구속한다.

$$
c_k=1.0\implies x_k=0\quad(\text{for all } k\in\mathcal{B})
$$

이 구속 조건 하에 최소자승법(least squares method)을 적용하여 $\|Ax-b\|^2$를 최소화하는 최적해 $x$를 산출한다. 이를 역변환($c_i=e^{x_i}$)하여 조립된 최종적인 전역 스펙트럼 지표 $\hat{C}=\text{diag}(e^x)$는, 위상적 경계 조건이 고정된 상태에서 내부의 동역학적 오차가 공간적으로 누적된 정도를 정량화한다.

---