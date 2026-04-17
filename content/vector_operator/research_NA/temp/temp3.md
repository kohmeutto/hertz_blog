+++
title = "temp 3"
weight = 23
+++

---

### 3.1 이산 공간 국소 비대칭 지표 $S_{kj}$

본 절에서는 2장에서 확립된 연속계의 진정한 대류 잔차 약형식을 이산 격자 공간(discrete space)의 선형 대수 시스템으로 사상(mapping)한다. 이 과정에서 발생하는 이산 교환자 오차(discrete commutator error)를 수학적으로 규명하여 수치적 업윈드(upwind) 기법의 대수적 기원을 입증하고, 이를 기반으로 물리적 해상도를 최적화하는 r-적응형(r-adaptive) 위상 사상 방법론을 전개한다.

**1) 역산 추출 전략 (Inverse Extraction Strategy)**

제2장에서 도출된 비선형 자코비안의 1계 대류 연산자 내부 잔차 약형식은 $\langle \phi, \mathcal{R}(J)\psi \rangle_\Omega = \langle \phi, \left[ (Dv)\psi + 2v(D\psi) \right] \rangle_\Omega$ 로 규명되었다. 여기서 이산화의 핵심 대상은 속도장의 발산이 상태 함수에 작용하는 성분인 $(Dv)\psi$ 이다. (단, 유효 속도장 $v = (\partial p/\partial u) Du$)

이 항을 격자 노드 $k$에 대하여 정직한 점-평가(point-wise evaluation)로 직접 이산화할 경우, 고립된 중심 노드의 상태량에 의존하게 되어 공간적 구배가 극심한 영역에서 필연적으로 수치적 진동(spurious oscillation)을 유발한다. 따라서 $(Dv)\psi$ 의 안정적인 이산 형태를 도출하기 위해, 연속 공간의 라이프니츠 법칙(Leibniz rule)인 $D(v\psi) = (Dv)\psi + v(D\psi)$ 를 역으로 변환한 다음의 관계식을 이용한다.

$$
(Dv)\psi = D(v\psi) - v(D\psi)
$$

즉, $(Dv)\psi$ 의 올바른 이산 형태를 직접 구하는 대신, 전체 물리량의 전미분인 $[D(v\psi)]_k$ 를 먼저 이산화한 뒤, 동질적 이류항 $v(D\psi)$ 의 이산 형태를 감산하여 목표 항을 추출하는 대수적 역산(Inverse extraction) 전략을 채택한다.

**2) 영합 조건(Zero-Sum Condition)과 구배의 대수적 생성**

상태 함수 $\psi$ 와 유효 속도장 $v$ 의 곱으로 이루어진 전체 물리량 $v\psi$ 에 대한 노드 $k$ 에서의 이산 미분을 전개한다. 이산 미분 연산자(차분 행렬) $\hat{D}_{kj}$ 에 의한 일차적 합산은 다음과 같다.

$$
[D(v\psi)]_k = \sum_{j} \hat{D}_{kj} (v_j \psi_j)
$$

이 수식은 절댓값의 합산일 뿐, 물리적 변화량을 나타내는 구배(Gradient)의 형태를 갖추지 못하고 있다. 구배 형태를 강제로 조성하기 위해 이산 미분 연산자의 해석학적 공리를 도입한다. 모든 이산 미분 연산자는 상수장에 작용할 때 그 결과가 항등적으로 0이 되어야 하므로, 각 행에 대한 가중치의 합은 반드시 0이 된다($\sum_j \hat{D}_{kj} = 0$).이 영합 조건에 중심 노드의 물리량 $v_k \psi_k$ 를 곱하면 그 결과 역시 0이다.

$$
v_k \psi_k \sum_{j} \hat{D}_{kj} = \sum_{j} \hat{D}_{kj} (v_k \psi_k) = 0
$$

식의 대수적 가치를 훼손하지 않으면서, 도출된 0을 초기 합산식에서 감산한다.

$$
[D(v\psi)]_k = \sum_{j} \hat{D}_{kj} (v_j \psi_j) - \sum_{j} \hat{D}_{kj} (v_k \psi_k) = \sum_{j} \hat{D}_{kj} (v_j \psi_j - v_k \psi_k)
$$

이 영합 조건의 대수적 개입을 통해, 비로소 이산 격자망은 절대값의 합산에서 벗어나 중심 노드와 이웃 노드 간의 상대적 차이인 $(v_j \psi_j - v_k \psi_k)$ 를 평가하는 미분 연산의 본질적 구조를 갖추게 된다.

**3) 이산 라이프니츠 사상과 이산 교환자 오차(Discrete Commutator Error)**

결합된 차이항 $(v_j \psi_j - v_k \psi_k)$ 에 대하여, 다음과 같은 자명한 대수적 항등식을 적용하여 속도장의 차이와 상태 함수의 차이로 분리한다.

$$
v_j \psi_j - v_k \psi_k = (v_j - v_k)\psi_j + v_k(\psi_j - \psi_k)
$$

이를 전체 전미분 식에 대입하여 두 개의 합산 기호로 분배한다.

$$
[D(v\psi)]_k = \underbrace{\sum_{j} (v_j - v_k) \hat{D}_{kj} \psi_j}_{\text{항 A}} + \underbrace{\sum_{j} v_k \hat{D}_{kj} (\psi_j - \psi_k)}_{\text{항 B}}
$$

여기서 항 B를 먼저 정리한다. $v_k$ 는 인덱스 $j$ 에 독립적이므로 괄호를 전개하면 $\sum_j v_k \hat{D}_{kj} \psi_j - v_k \psi_k \sum_j \hat{D}_{kj}$ 가 된다. 영합 조건에 의해 두 번째 감산항이 소멸하므로, 항 B는 $\sum_j v_k \hat{D}_{kj} \psi_j$ 로 환원된다. 이는 정확히 연속계의 이류항 $v(D\psi)$ 가 이산화된 형태이다.

이제 1)에서 설정한 연속계의 역산 공식 $[D(v\psi)]_k - v(D\psi) = (Dv)\psi$ 와 이산 전개 결과를 1:1로 대응시킨다. 그 결과, 우리가 목표로 했던 $(Dv)\psi$ 의 이산 사상 결과는 필연적으로 항 A 로 확정된다.

$$
(Dv)\psi \quad \longrightarrow \quad \sum_{j} (v_j - v_k) \hat{D}_{kj} \psi_j
$$

**4) 대수적 텐션 기반의 위상 공간 조화 사상**

이러한 해석학적 결론을 바탕으로, 노드 $k$ 에 작용하는 전체 이산 레지듀 방정식을 조합한다. 연속계 잔차 $(Dv)\psi + 2v(D\psi)$ 에 해당하는 3)의 도출 결과를 결합한다.

$$
e_k^T \mathcal{R}_{int} \psi = \underbrace{\sum_{j} (v_j - v_k) \hat{D}_{kj} \psi_j}_{\text{구배 작용 (} (Dv)\psi \text{)}} + \underbrace{\sum_{j} (2v_k) \hat{D}_{kj} \psi_j}_{\text{동질적 이류 작용 (} 2v(D\psi) \text{)}}
$$

이를 단일 합산 기호로 결합하면, 격자망 내부의 비대칭성을 유발하는 최종적인 결합 계수가 산출된다.

$$
e_k^T \mathcal{R} \psi = \sum_{j} (v_j + v_k) \hat{D}_{kj} \psi_j
$$

도출된 이산 레지듀의 결합 계수를 이용하여, 각 노드 $k$ 에서 이웃 노드 $j$ 로 향하는 국소적 비대칭 단방향 텐션(directional tension) $\mathcal{T}_{kj}$ 를 엄밀하게 정의한다.

$$
\mathcal{T}_{kj} = (v_j + v_k) \hat{D}_{kj} \psi_j
$$

두 노드 사이의 대칭적인 교차 텐션 지표 $S_{kj}$ 는 양방향 텐션 절대값의 산술 평균으로 정의하여 방향성에 의한 상쇄를 방지한다.

$$
S_{kj} = \frac{1}{2} \left( |\mathcal{T}_{kj}| + |\mathcal{T}_{jk}| \right)
$$

**5) r-적응형(r-adaptive) 매핑 과정**

지표 $S_{kj}$를 이용하여 격자의 좌표를 능동적으로 재배치하는 r-적응형(r-adaptive) 매핑 과정을 설명한다. 격자가 꼬이는 것을 막고 스케일의 영향을 받지 않도록, 전체 도메인에서의 최댓값을 이용하여 지표를 0과 1 사이의 값으로 정규화한다.

$$
\bar{S}_{kj} = \frac{S_{kj}}{\max_{\Omega_h}(S_{kj})} \quad \in [0, 1]
$$

이를 바탕으로 노드 간의 간격을 조절하는 가중치(weight) 행렬 $\hat{W}$의 비대각 성분 $W_{kj}$를 다음과 같이 정의한다.

$$
W_{kj} = 1.0 + \bar{S}_{kj} \quad (\text{단, } j \in \mathcal{N}(k))
$$

이 수식은 수치해석적으로 격자의 과도한 밀집을 막는 제한 조건(Trust-Region) 역할을 한다. 텐션이 0에 가까운 구역에서는 가중치가 1이 되어 기본적인 격자 간격을 유지하지만, 텐션이 큰 곳에서는 가중치가 최대 2까지만 증가한다. 이를 통해 하나의 계산 단계에서 격자가 압축되는 비율을 최대 2배로 제한하여, 격자의 순서가 뒤집히는 위상 역전(topological inversion) 현상을 방지한다. 이 가중치 행렬 $\hat{W}$를 이용하여, 노드의 좌표 벡터 $\mathbf{X}$를 안정적으로 이동시키기 위한 조화 사상(Harmonic Mapping) 방정식을 세운다. 각 내부 노드 $i$에 작용하는 가중치의 합이 0이 되는 평형 상태를 다음과 같이 나타낼 수 있다.

$$
\sum_{j \in \mathcal{N}(i)} W_{ij} (\mathbf{X}_j - \mathbf{X}_i) = \mathbf{0}
$$

이 방정식을 격자 전체에 대한 선형 행렬 시스템으로 확장하기 위해 그래프 라플라시안(Graph Laplacian) 연산자 $\hat{L}_{sys}$를 구성한다.

$$
\hat{L}_{sys} = \hat{K} - \hat{W}
$$

여기서 대각 행렬 $\hat{K}$는 각 노드에 연결된 가중치의 합($K_{ii} = \sum_j W_{ij}$)이다. 연산자 $\hat{L}_{sys}$는 공간의 차원이나 격자의 모양에 관계없이, 노드의 연결 상태에 의해서만 결정되는 양의 준정부호(Symmetric Positive Semi-Definite) 행렬이다. 이 행렬 시스템이 유일한 해를 가지도록 도메인의 외부 경계 및 이질 매질 간의 계면(interface)에 속하는 고정 노드들에 디리클레 경계 조건(Dirichlet boundary condition)을 적용한다. 해당 노드들의 행을 항등식으로 바꾸고, 기준이 되는 좌표계 $\mathbf{B}_{ref}$를 대입하여 다음과 같은 행렬식으로 정리한다.

$$
\tilde{L}_{sys} \mathbf{X}_{new} = \mathbf{B}_{ref}
$$

여기서 기준점 $\mathbf{B}_{ref}$는 이전 계산에서 안정성이 확인된 좌표를 사용하여 수치적인 진동을 줄인다. 이 행렬식을 풀면($\mathbf{X}_{new} = \tilde{L}_{sys}^{-1} \mathbf{B}_{ref}$), 격자의 노드들은 오차 지표 $\bar{S}_{kj}$가 큰 곳을 향해 자연스럽게 밀집되며 새로운 평형 상태에 도달한다. 좌표 이동이 완료된 후, 새로운 좌표계 $\mathbf{X}_{new}$ 위에서 각 노드 $k$가 차지하는 체적(control volume) $V_k^*$를 다시 계산한다. 이 체적들을 대각 성분으로 하는 듀얼 체적 메트릭(dual volume metric) $\hat{G}$를 다음과 같이 정의한다.

$$
\hat{G} = \text{diag}(V_0^*, V_1^*, \dots, V_{N-1}^*)
$$

결과적으로 기하학적 메트릭 $\hat{G}$는 도메인 내부의 표류 구배에 대응하여 물리적 해상도가 최적화된 공간 이산화의 결과물이다.

---

### 3.2 Preconditioning

본 절에서는 앞서 산출된 메트릭 $\hat{G}$를 바탕으로, 시스템의 표류 방향성을 포텐셜 장으로 사상하는 자동 적분 인자(Automated Integrating Factor) $\hat{C}$를 유도한다. 나아가 반복 선형 솔버의 안정성을 확보하기 위한 대칭 전제조건자(Symmetric Preconditioner) $\hat{J}_{pure}$의 설계 과정을 설명한다.

이산 격자에서 시스템의 비대칭성을 교정하기 위해, 기하학적 메트릭 $\hat{G}$와 대각 행렬 $\hat{C}$를 기존 잔차 벡터 $R(u)$에 곱하여 새로운 잔차 시스템 $\tilde{F}(u) = \hat{C}\hat{G}F(u) = 0$을 정의한다. 상태 벡터가 $u$에서 $u+\delta u$로 변할 때 1차 근사(first-order variation)를 전개하여 변화량 $\delta u$를 결정하는 선형 행렬을 구성한다.

$$
\tilde{F}(u+\delta u)\approx\tilde{F}(u)+\left(\frac{\partial\hat{C}}{\partial u}\hat{G}F(u)+\hat{C}\frac{\partial\hat{G}}{\partial u}F(u)\right)\delta u+\hat{C}\hat{G}\hat{J}\delta u
$$

여기서 $\hat{J} = \partial F/\partial u$는 원본 비선형 자코비안 행렬이다. 뉴턴-랩슨(Newton-Raphson) 해법이 진행됨에 따라 물리적 잔차가 0에 수렴($F(u) \to 0$)하면, 괄호 안의 항들은 소거되며 유효 자코비안은 마지막 항인 $\tilde{J} = \hat{C}\hat{G}\hat{J}$로 근사된다. 이는 행렬 조작($\hat{C}$, $\hat{G}$)이 원래 지배 방정식의 평형 상태를 훼손하지 않음을 의미한다.

연속계에서 발생하는 자코비안의 물리적 비대칭성은 이산 행렬의 조건수(condition number)를 악화시킨다. 선형 솔버의 탐색 안정성을 확보하기 위해, 본 연구는 구성될 유효 자코비안 $\tilde{J}$가 대칭성을 갖도록 하는 다음의 대수적 구속 조건(Target Constraint)을 도입한다.

$$
\mathcal{R}(\tilde{J})_{ij}=\tilde{J}_{ij}-\tilde{J}_{ji}=0\quad(\text{for all } i, j\in\mathcal{I})
$$

위 조건에 $\tilde{J} = \hat{C}\hat{G}\hat{J}$를 대입하여 행렬 성분으로 정리하면 $c_i (\hat{G}\hat{J})_{ij} = c_j (\hat{G}\hat{J})_{ji}$ 가 요구된다. 그러나 국소 페클레 수(Cell Péclet number)가 1을 초과하는 대류 지배 영역에서는 자코비안의 마주보는 비대각 성분 간에 부호 역전이 발생할 수 있으므로, 실수 공간에서 위 등식을 항등적으로 만족하는 해는 존재하지 않을 수 있다. 따라서 행렬 성분의 크기 비대칭성을 보존하기 위해, 대상 조건식의 양변에 절댓값을 취하여 전개한다.

$$
|c_i (\hat{G}\hat{J})_{ij}| = |c_j (\hat{G}\hat{J})_{ji}|
$$

절댓값의 곱셈 분배 법칙을 적용하여 식을 분리한다.

$$
|c_i| |(\hat{G}\hat{J})_{ij}| = |c_j| |(\hat{G}\hat{J})_{ji}|
$$

여기서 구하고자 하는 대각 성분 $c$는 지수 함수 형태($c_i = e^{x_i}$)로 정의되므로 항상 양수($c_i > 0$)이다. 즉, $|c_i| = c_i$ 가 성립하므로 식은 다음과 같이 환원된다.

$$
c_i |(\hat{G}\hat{J})_{ij}| = c_j |(\hat{G}\hat{J})_{ji}|
$$

이 식의 양변에 자연 로그(natural logarithm)를 취하여 정리하면, 부호 역전에 의한 연산 단절 없이 대수적인 차이 $b_{ij}$를 산출할 수 있다.

$$
\ln(c_i) - \ln(c_j) = \ln\left( \frac{|(\hat{G}\hat{J})_{ji}|}{|(\hat{G}\hat{J})_{ij}|} \right) \equiv b_{ij}
$$

$b_{ij}$는 2장에서 설명한 유효 표류 속도 $v \equiv (\partial p/\partial u) Du$ 와 관련이 있다. Appendix I 에 따라, $b_{ij}$는 아래와 같이 단순화 될 수 있다.

$$
b_{ij}
= \ln\left(\frac{V_j^*}{V_i^*}\right) + \int_i^j \left(\frac{v}{p}\right) \cdot d\mathbf{l}
$$

치환 변수 $x_i = \ln(c_i)$를 도입하면, 본 식은 간선(edge)에 정의된 국소 비대칭 비율 $b_{ij}$로부터 각 내부 노드(node)의 절대 보정값 $x_i$를 산출하는 $\hat{S}x = b$ 형태의 과결정(overdetermined) 선형 연립방정식이 된다. 해의 유일성 확보를 위해 디리클레 경계 노드 집합 $\mathcal{B}$에 대하여 $c_k = 1.0$($x_k = 0$)의 기준점(anchoring) 조건을 부과한다. 최소자승법(least squares method)으로 해를 산출하고 지수 함수($c_i = e^{x_i}$)를 취해 대각 행렬 $\hat{C}$를 확립한다. Appendix II 는 원시 자코비안 대비 1 이하임을 보여준다.

---

### Appendix I. 이산 헬름홀츠-호지 분해와 잔류 비대칭성 평가

본 절에서는 3.2절에서 구성된 과결정 선형 연립방정식 $\hat{S}x = b$의 최소자승(Least-Squares) 근사해 $x_{LS}$가 시스템의 비대칭성을 상쇄하는 비율을 정량적으로 도출한다.

**1) 다차원 변분 플럭스의 1차원 방향 도함수 투영**

제2장에서 확립된 상태 변수 미소 섭동 $\psi$ 에 대한 연속계 자코비안 연산자 $J$ 내부의 식은 확산 매개변수 $p$ 와 유효 표류 속도 $v \equiv (\partial p/\partial u) Du$ 로 구성된 다차원 벡터장 $-p\nabla \psi + v\psi$ 의 발산($\nabla \cdot$)으로 정의된다. 유한체적법(FVM)의 원리에 따라, 임의의 노드 $i$ 를 둘러싼 검사 체적 $\Omega_i$ 에 대한 잔차 방정식 $F_i = 0$ 은 가우스 발산 정리에 의해 체적 표면적 $\partial \Omega_i$ 에 대한 면적분으로 변환된다.

$$
F_i \equiv \iiint_{\Omega_i} (J\delta u) dV = \iiint_{\Omega_i} \nabla \cdot (-p \nabla \delta u + v \delta u) dV - \iiint_{\Omega_i} \frac{\partial q}{\partial u} \delta u dV = 0
$$

좌변의 발산항은 발산 정리에 의해 체적 표면적 $\partial \Omega_i$ 에 대한 면적분으로 변환된다. 이산 격자망에서 이 면적분은 노드 $i$ 와 인접 노드 $j$ 들을 연결하는 간선(edge) 단면을 통과하는 플럭스 성분 $\Gamma_{i \to j}$ 들의 합으로 환원된다.

$$
\iint_{\partial \Omega_i} (-p \nabla \psi + v \psi) \cdot \mathbf{n} dA = \sum_{j} \Gamma_{i \to j}
$$

따라서, 노드 $i$ 의 최종 이산 잔차 방정식 $F_i$ 는 인접 노드로의 간선 플럭스 합과 자기 자신의 국소 소스항의 결합으로 구성된다.

$$
F_i = \sum_{j} \Gamma_{i \to j} - \iiint_{\Omega_i} \frac{\partial q}{\partial u} \psi dV = 0
$$

이산 격자망에서 위 면적분은 노드 $i$ 와 인접한 노드 $j$ 를 연결하는 각 간선(edge)의 단면을 통과하는 성분들의 합으로 환원된다. 간선의 단위 방향 벡터를 $\mathbf{e}_{ij}$ 라 하고, 해당 간선 방향의 1차원 거리 좌표를 $\xi \in [\xi_i, \xi_j]$ 로 설정하면, 방향 도함수의 정의에 의해 간선 상의 국소 연산자 성분 $\Gamma_{i \to j}$ 는 다음과 같이 도출된다.

$$
\Gamma_{i \to j} = A_{ij} \left( -p(\xi)\frac{d\psi}{d\xi} + v(\xi)\psi \right)
$$

여기서, $A_{ij}$ 는 간선 단면적이며, $v(\xi) \equiv v \cdot \mathbf{e}_{ij}$ 는 유효 속도의 1차원 투영 성분이다. 간선 내부에 소스(Source) 항이 부재하므로 해당 1차원 국소 연산자의 공간 미분값은 영이다. 따라서 괄호 내부의 식은 해석적으로 상수 $C^*$ 로 고정된다.

$$
-p(\xi)\frac{d\psi}{d\xi} + v(\xi)\psi = C^*
$$

이 1계 선형 상미분방정식을 풀기 위해 양변을 $p(\xi)$ 로 나누고, 적분 인자(Integrating factor)를 곱하여 완전 미분 형태로 재배열한다.

$$
\frac{C^*}{p(\xi)} \exp\left(-\int_{\xi_i}^\xi \frac{v(s)}{p(s)} ds\right) = -\frac{d}{d\xi} \left[ \psi(\xi) \exp\left(-\int_{\xi_i}^\xi \frac{v(s)}{p(s)} ds\right) \right]
$$

간선 전체 구간 $[\xi_i, \xi_j]$ 에 대하여 양변을 정적분하면 다음과 같다.

$$
C^* \cdot R_{ij} = -\left[ \psi(\xi) \exp\left(-\int_{\xi_i}^\xi \frac{v(s)}{p(s)} ds\right) \right]_{\xi_i}^{\xi_j}
$$

여기서 좌변의 적분항 $R_{ij}$는 유효 기하 저항(Effective Geometric Resistance)으로 정의되며, 확산 계수 $p(\xi)$와 대류 속도 $v(\xi)$의 공간적 분포에 의해 결정되는 간선 고유의 스칼라 값이다.

$$
R_{ij} \equiv \int_{\xi_i}^{\xi_j} \frac{1}{p(\xi)} \exp\left(-\int_{\xi_i}^\xi \frac{v(s)}{p(s)} ds\right) d\xi
$$

이 정의를 바탕으로 상수 $C^*$ 에 대해 정리하면, 노드 $i$와 $j$의 상태 변수에 대한 선형 대수식이 도출된다.

$$
C^* = \frac{1}{R_{ij}} \psi_i - \frac{1}{R_{ij}}\exp\left(-\int_{\xi_i}^{\xi_j} \frac{v(s)}{p(s)} ds\right) \psi_j
$$

**2) 이산 자코비안 편미분과 대수적 맵핑 벡터 추출**

시스템 선형화를 위한 이산 자코비안 행렬 $\hat{J} = \partial F / \partial \psi$ 의 교차 결합 성분은 각 노드의 잔차 방정식($F_i, F_j$)을 대상 노드의 상태 변수로 편미분(Partial derivative)하여 엄밀하게 산출된다. 이때, 노드 $i$ 의 국소 소스항은 오직 $\psi_i$ 에만 종속되므로 교차 편미분 과정($\partial / \partial \psi_j$)에서 항등적으로 소멸하여 오직 간선 플럭스 $\Gamma$ 만이 행렬 성분에 기여한다.

$$
\hat{J}_{ij} \equiv \frac{\partial F_i}{\partial \psi_j} = \frac{\partial \Gamma_{i \to j}}{\partial \psi_j} = - \frac{A_{ij}}{R_{ij}} \exp\left(-\int_{\xi_i}^{\xi_j} \frac{v(s)}{p(s)} ds\right)
$$

$$
\hat{J}_{ji} \equiv \frac{\partial F_j}{\partial \psi_i} = \frac{\partial \Gamma_{j \to i}}{\partial \psi_i} = - \frac{A_{ji}}{R_{ij}}
$$

3.1절의 대각 메트릭 $\hat{G}$ 의 작용에 의해 행렬 성분은 $(\hat{G}\hat{J})_{ij} = V_i^* \hat{J}_{ij}$ 로 전개되므로 타겟 벡터 $b_{ij}$ 는 다음과 같이 정의된다.

$$
b_{ij} \equiv \ln \left( \frac{|(\hat{G}\hat{J})_{ji}|}{|(\hat{G}\hat{J})_{ij}|} \right) = \ln \left( \frac{V_j^* |\hat{J}_{ji}|}{V_i^* |\hat{J}_{ij}|} \right)
$$

여기에 앞서 도출된 자코비안 성분 절댓값의 비율을 대입한다. 인접한 두 노드 사이의 간선 단면적은 기하학적으로 대칭이므로 $A_{ij} = A_{ji}$ 가 성립한다. 따라서 분모와 분자에 위치한 단면적과 유효 기하 저항 $R_{ij}$ 가 완벽하게 소거되며 순수 지수 함수비만 남는다. 로그 곱셈 법칙($\ln(AB) = \ln A + \ln B$)을 적용하여 항을 분리한다.

$$
b_{ij} = \ln \left( \frac{V_j^*}{V_i^*} \right) + \ln \left( \exp \left( \int_{\xi_i}^{\xi_j} \frac{v(s)}{p(s)} ds \right) \right)
$$

자연로그($\ln$)와 지수 함수($\exp$)의 역연산 상쇄 효과, 그리고 1차원 정적분의 선적분(Line integral) 사상 정의에 의해 최종적인 대수적 맵핑 데이터 $b_{ij}$ 가 기하학적 체적비 구배항과 연속계 페클레 장(Péclet field, $v/p$)의 물리적 선적분항의 결합으로 확정된다.

$$
b_{ij} = \ln\left(\frac{V_j^*}{V_i^*}\right) + \int_{\xi_i}^{\xi_j} \frac{v(s)}{p(s)} ds \equiv \ln\left(\frac{V_j^*}{V_i^*}\right) + \int_i^j \left(\frac{v}{p}\right) \cdot d\mathbf{l}
$$

---

### Appendix II. 그래프 라플라시안과 산 헬름홀츠-호지 분해(DHHD)

노드 간 비대칭 비율 $b_{ij}$로부터 대각 보정 변수 $x$를 도출하는 방정식 $\hat{S}x = b$는 일반적으로 해가 존재하지 않는 과결정 시스템이다. 목적 함수 $f(x) = \|\hat{S}x - b\|_2^2$를 최소화하는 해 $x_{LS}$를 구하기 위해 다음의 정규 방정식(Normal equation)을 구성한다.

$$
(\hat{S}^T \hat{S}) x_{LS} = \hat{S}^T b
$$

여기서 $\hat{S}^T \hat{S}$는 격자망의 연결 구조를 나타내는 대칭 행렬인 그래프 라플라시안(Graph Laplacian)으로 환원된다.

이산 헬름홀츠-호지 정리에 의거하여, 간선 벡터 $b$는 다음과 같이 직교 분해된다.

$$
b = \hat{S} x_{LS} + r
$$

여기서 투영 성분 $\hat{S} x_{LS}$ 는 연속계 벡터 미적분학의 보존장 항등식($\nabla \times \nabla \phi \equiv 0$)에 대응하는 무회전(Irrotational) 성분이다. 반면 잔차 $r$ 은 대수적 투영 과정에서 제거되지 못한 비대칭 성분을 의미한다. 최소자승법의 기하학적 정의에 따라 잔차 $r$ 은 결합 행렬의 열공간에 직교하므로($\hat{S}^T r = 0$), 좌영공간(Left null space)에 속하게 되며 물리적으로 발산이 없는 순환(circulation) 성분으로 정의된다.

피타고라스 정리에 의해 다음의 관계가 성립한다.

$$
\|b\|_2^2 = \|\hat{S}x_{LS}\|_2^2 + \|r\|_2^2
$$

써야함.

---

### 3.3 유효 자코비안 분리

대수적 변환이 적용된 유효 자코비안 $\tilde{J}$는 대칭 성분(Hermitian part, $\hat{H}$)과 다차원 공간의 교차 결합에 의해 발생하는 반대칭 성분(anti-Hermitian part, $\hat{A}_{raw}$)의 합으로 분리된다.

$$
\tilde{J} = \hat{H} + \hat{A}_{raw}
$$

각 행렬은 다음과 같이 계산된다.

$$
\hat{H} = \frac{1}{2} \left( \tilde{J} + \tilde{J}^T \right), \quad \hat{A}_{raw} = \frac{1}{2} \left( \tilde{J} - \tilde{J}^T \right)
$$

이산 시스템이 연속계의 성질을 잘 따르도록 하기 위해, 값이 고정된 디리클레 경계 $\mathcal{B}$에서 반대칭 성분의 영향을 제외하는 추가적인 처리를 수행한다. 이를 위해 경계 노드에서는 0, 내부 노드에서는 1을 가지는 대각 행렬 $\hat{M}_s$를 정의한다.

$$
(\hat{M}_s)_{ii} = 
\begin{cases} 
0, & \text{if } i \in \mathcal{B} \\
1, & \text{otherwise}
\end{cases}
$$

이 행렬을 반대칭 행렬의 양쪽에 곱하여, 내부 도메인 $\mathcal{I}$에만 해당하는 반대칭 성분 $\hat{A}_{int}$를 따로 분리해낸다.

$$
\hat{A}_{int} = \hat{M}_s \hat{A}_{raw} \hat{M}_s
$$

이 $\hat{A}{int}$는 다차원 공간의 교차 결합이나 물리적 와도(vorticity) 등 변환 행렬 $\hat{C}$의 스칼라 포텐셜 장으로 환원되지 않는 시스템의 고유한 비대칭 성분을 포함한다. 이 성분은 지배 방정식의 물리적 거동을 나타내는 유효한 정보이나, 역행렬 연산 시 선형 솔버의 조건수를 악화시키는 주원인이 된다. 따라서 본 연구에서는 이 성분이 우변의 물리적 잔차 $F(u)$에는 온전히 반영되도록 보존하되, 탐색 방향을 결정하는 좌변의 전제조건자 $\hat{J}_{pure}$를 구성할 때에 한하여 이를 대수적으로 분리한다.

$$
\hat{J}_{pure} = \tilde{J} - \hat{A}_{int}
$$

본 연구는 원본 자코비안 $\hat{J}$ 대신, 대칭 전제조건자 $\hat{J}_{pure}$를 탐색 행렬로 사용하여 변화량 $\delta u$를 산출하는 부정확 뉴턴법(Inexact Newton Method)을 적용한다. 선형 탐색 행렬은 대칭화되나 우변의 물리적 잔차 벡터 $F(u)$는 원본 상태를 유지한다. 알고리즘이 수렴 조건($\delta u \to 0$)에 도달하면, $\hat{J}_{pure} \delta u = -F(u)$ 관계식에 의해 항등적으로 $F(u^*) = 0$ 이 성립한다. 이는 제안된 대수적 대칭화 과정이 선형 탐색의 수치적 안정성만을 개선할 뿐, 최종 고정점(fixed point)의 물리적 엄밀성(exact solution)을 보장함을 증명한다. Appendix III 는 분리된 자코비안을 사용하더라도 해가 수렴됨을 증명한다.

---

### Apendix III. 수렴성 증명

본 절에서는 3.2절에서 산출된 투영 기반 전제조건자 $\hat{J}_{pure}$가 유효 자코비안 $\tilde{J}$에 적용되었을 때, 전제조건화된 연산자 $\hat{J}_{pure}^{-1} \tilde{J}$의 고유값(eigenvalue) 분포가 복소 평면(complex plane) 내의 제한된 원판(bounded disk)에 군집함을 대수적으로 증명한다. 이를 통해 제안된 대수적 제어 프레임워크가 Krylov 부분 공간 해법의 수렴성을 보장함을 해석적으로 규명한다.

**1) 일반화된 고유값 문제(Generalized Eigenvalue Problem)의 구성**

$\hat{J}_{pure}^{-1} \tilde{J}$의 고유값을 $\lambda \in \mathbb{C}$, 이에 대응하는 0이 아닌 고유 벡터를 $x \in \mathbb{C}^n$이라 정의하면, 이는 다음의 일반화된 고유값 문제로 치환된다.

$$
\tilde{J} x = \lambda \hat{J}_{pure} x
$$

유효 자코비안 $\tilde{J}$는 대칭 성분 $\hat{H}$와 반대칭 성분 $\hat{A}_{raw}$의 합($\tilde{J} = \hat{H} + \hat{A}_{raw}$)으로 구성된다. 전제조건자 $\hat{J}{pure}$는 내부 반대칭 성분 $\hat{A}{int}$가 제외된 형태이므로, 다음과 같이 표현할 수 있다.

$$
\hat{J}_{pure} = \tilde{J} - \hat{A}_{int} = \hat{H} + \hat{A}_{bnd}
$$

여기서 $\hat{A}_{bnd} = \hat{A}_{raw} - \hat{A}_{int}$는 디리클레 경계 $\mathcal{B}$에서만 0이 아닌 성분을 가지는 잔류 반대칭 연산자이다. 이를 고유값 방정식에 대입하면 다음과 같이 전개된다.

$$
(\hat{J}_{pure} + \hat{A}_{int}) x = \lambda \hat{J}_{pure} x
$$

$$
\hat{A}_{int} x = (\lambda - 1) \hat{J}_{pure} x
$$

**2) 이차 형식(Quadratic Form) 전개와 에너지 내적**

고유값 $\lambda$의 경계를 도출하기 위해, 식의 양변에 고유 벡터의 켤레 전치(conjugate transpose) $x^*$를 곱하여 이차 형식을 구성한다. (단, $\|x\| = 1$)

$$
x^* \hat{A}_{int} x = (\lambda - 1) x^* (\hat{H} + \hat{A}_{bnd}) x
$$

물리적 보존계의 강타원형(strongly elliptic) 확산 연산자에서 유래한 대칭 성분 $\hat{H}$는 양의 정부호(Symmetric Positive Definite) 특성을 가지므로, $x^* \hat{H} x = h$ 라 할 때 $h > 0$ 이 성립한다.

반면 $\hat{A}_{int}$와 $\hat{A}_{bnd}$는 반대칭 행렬(skew-symmetric matrix)이므로, 그 이차 형식은 순수 허수(pure imaginary)가 된다. 따라서 실수 $\alpha, \beta \in \mathbb{R}$에 대하여 다음과 같이 정의할 수 있다.

$$
x^* \hat{A}_{int} x = i\alpha, \quad x^* \hat{A}_{bnd} x = i\beta
$$

이를 이차 형식 방정식에 대입한다.

$$
i\alpha = (\lambda - 1)(h + i\beta)
$$

**3) 스펙트럼 상한(Spectral Upper Bound) 도출**

위 식을 고유값 $\lambda$에 대하여 정리하여 실수부 $Re(\lambda)$와 허수부 $Im(\lambda)$로 분리한다.

$$
\lambda - 1 
= \frac{i\alpha}{h + i\beta} 
= \frac{\alpha\beta}{h^2 + \beta^2} + i\frac{\alpha h}{h^2 + \beta^2}
$$

전제조건화된 연산자의 고유값 중심 이동(shift) 규모인 $|\lambda - 1|^2$을 산출한다.

$$
|\lambda - 1|^2 = \left(\frac{\alpha\beta}{h^2 + \beta^2}\right)^2 + \left(\frac{\alpha h}{h^2 + \beta^2}\right)^2 = \frac{\alpha^2 \beta^2 + \alpha^2 h^2}{(h^2 + \beta^2)^2} = \frac{\alpha^2 (h^2 + \beta^2)}{(h^2 + \beta^2)^2} = \frac{\alpha^2}{h^2 + \beta^2}
$$

분모의 $\beta^2 \ge 0$ 이므로, 다음의 부등식이 필연적으로 성립한다.

$$
|\lambda - 1| \le \frac{|\alpha|}{h} = \frac{|x^* \hat{A}_{int} x|}{x^* \hat{H} x}
$$

여기서 $\hat{A}_{int}$의 $\hat{H}$에 대한 에너지 노름(energy norm) 기준의 상대적 연속성 상수(relative continuity constant)를 다음과 같이 정의한다.

$$
\gamma_{int} \equiv \sup_{x \ne 0} \frac{|x^* \hat{A}_{int} x|}{x^* \hat{H} x}
$$

결과적으로, 전제조건화된 연산자 $\hat{J}_{pure}^{-1} \tilde{J}$의 모든 고유값 $\lambda$는 복소 평면 상에서 점 $(1, 0)$을 중심으로 하고 반지름이 $\gamma{int}$인 폐원판(closed disk) 내에 존재함이 증명된다. 해당 연산자가 가지는 모든 고유값들의 집합인 스펙트럼(spectrum)을 $\sigma(\hat{J}_{pure}^{-1} \tilde{J})$라 정의할 때, 위 결론은 다음과 같은 집합의 포함 관계로 엄밀하게 표현된다.

$$
\sigma(\hat{J}_{pure}^{-1} \tilde{J}) \subset \{ \lambda \in \mathbb{C} : |\lambda - 1| \le \gamma_{int} \}
$$

---
