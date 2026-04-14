+++
title = "CHAPTER 3"
weight = 15
+++

---

### 3.1 이산 공간 국소 비대칭 지표 $S_{kj}$

본 절에서는 2장에서 확립된 연속계의 진정한 대류 잔차 약형식을 이산 격자 공간(discrete space)의 선형 대수 시스템으로 사상(mapping)한다. 이 과정에서 발생하는 이산 교환자 오차(discrete commutator error)를 수학적으로 규명하여 수치적 업윈드(upwind) 기법의 대수적 기원을 입증하고, 이를 기반으로 물리적 해상도를 최적화하는 r-적응형(r-adaptive) 위상 사상 방법론을 전개한다.

**1) 역산 추출 전략 (Inverse Extraction Strategy)**

제2장에서 도출된 비선형 자코비안의 1계 대류 연산자 내부 잔차 약형식은 $\langle \phi, \mathcal{R}(J)_{int}\psi \rangle_\Omega = \langle \phi, \left[ (Dv)\psi + 2v(D\psi) \right] \rangle_\Omega$ 로 규명되었다. 여기서 이산화의 핵심 대상은 속도장의 발산이 상태 함수에 작용하는 성분인 $(Dv)\psi$ 이다. (단, 유효 속도장 $v = (\partial p/\partial u) Du$

이 항을 격자 노드 $k$에 대하여 정직한 점-평가(point-wise evaluation)로 직접 이산화할 경우, 고립된 중심 노드의 상태량에 의존하게 되어 공간적 구배가 극심한 영역에서 필연적으로 수치적 진동(spurious oscillation)을 유발한다. 따라서 $(Dv)\psi$ 의 안정적인 이산 형태를 도출하기 위해, 연속 공간의 라이프니츠 법칙(Leibniz rule)인 $D(v\psi) = (Dv)\psi + v(D\psi)$ 를 역으로 변환한 다음의 관계식을 이용한다

$$
(Dv)\psi = D(v\psi) - v(D\psi)
$$

즉, $(Dv)\psi$ 의 올바른 이산 형태를 직접 구하는 대신, 전체 물리량의 전미분인 $[D(v\psi)]_k$ 를 먼저 이산화한 뒤, 동질적 이류항 $v(D\psi)$ 의 이산 형태를 감산하여 목표 항을 추출하는 대수적 역산(Inverse extraction) 전략을 채택한다.

**2) 영합 조건(Zero-Sum Condition)과 구배의 대수적 생성**

상태 함수 $\psi$ 와 유효 속도장 $v$ 의 곱으로 이루어진 전체 물리량 $v\psi$ 에 대한 노드 $k$ 에서의 이산 미분을 전개한다. 이산 미분 연산자(차분 행렬) $\hat{D}_{kj}$ 에 의한 일차적 합산은 다음과 같다.

$$
[D(v\psi)]_k = \sum_{j} \hat{D}_{kj} (v_j \psi_j)
$$

이 수식은 절대값의 합산일 뿐, 물리적 변화량을 나타내는 구배(Gradient)의 형태를 갖추지 못하고 있다. 구배 형태를 강제로 조성하기 위해 이산 미분 연산자의 해석학적 공리를 도입한다. 모든 이산 미분 연산자는 상수장에 작용할 때 그 결과가 항등적으로 0이 되어야 하므로, 각 행에 대한 가중치의 합은 반드시 0이 된다($\sum_j \hat{D}_{kj} = 0$).

이 영합 조건에 중심 노드의 물리량 $v_k \psi_k$ 를 곱하면 그 결과 역시 0이다.

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
e_k^T \mathcal{R}_{int} \psi = \sum_{j} (v_j + v_k) \hat{D}_{kj} \psi_j
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

### 3.2 대수적 전제조건화(Preconditioning)와 유효 자코비안 분리

본 절에서는 앞서 산출된 메트릭 $\hat{G}$를 바탕으로, 시스템의 표류 방향성을 포텐셜 장으로 사상하는 자동 적분 인자(Automated Integrating Factor) $\hat{C}$를 유도한다. 나아가 2.4절의 벌크-경계 소산 정리를 이산 공간에 적용하여, 반복 선형 솔버의 안정성을 확보하기 위한 대칭 전제조건자(Symmetric Preconditioner) $\hat{J}_{pure}$의 설계 과정을 설명한다.

**1) 적분 인자 행렬 $\hat{C}$의 산출과 구속 조건**

이산 격자에서 시스템의 비대칭성을 교정하기 위해, 기하학적 메트릭 $\hat{G}$와 대각 행렬 $\hat{C}$를 기존 잔차 벡터 $R(u)$에 곱하여 새로운 잔차 시스템 $\tilde{F}(u) = \hat{C}\hat{G}F(u) = 0$을 정의한다. 상태 벡터가 $u$에서 $u+\delta u$로 변할 때 1차 근사(first-order variation)를 전개하여 변화량 $\delta u$를 결정하는 선형 행렬을 구성한다.

$$
\tilde{F}(u+\delta u)\approx\tilde{F}(u)+\left(\frac{\partial\hat{C}}{\partial u}\hat{G}F(u)+\hat{C}\frac{\partial\hat{G}}{\partial u}F(u)\right)\delta u+\hat{C}\hat{G}\hat{J}\delta u
$$

여기서 $\hat{J} = \partial F/\partial u$는 원본 비선형 자코비안 행렬이다. 뉴턴-랩슨(Newton-Raphson) 해법이 진행됨에 따라 물리적 잔차가 0에 수렴($F(u) \to 0$)하면, 괄호 안의 항들은 소거되며 유효 자코비안은 마지막 항인 $\tilde{J} = \hat{C}\hat{G}\hat{J}$로 근사된다. 이는 행렬 조작($\hat{C}$, $\hat{G}$)이 원래 지배 방정식의 평형 상태를 훼손하지 않음을 의미한다.

연속계에서 발생하는 자코비안의 물리적 비대칭성은 이산 행렬의 조건수(condition number)를 악화시킨다. 선형 솔버의 탐색 안정성을 확보하기 위해, 본 연구는 구성될 유효 자코비안 $\tilde{J}$가 대칭성을 갖도록 하는 다음의 대수적 구속 조건(Target Constraint)을 도입한다.

$$
\mathcal{R}(\tilde{J})_{ij}=\tilde{J}_{ij}-\tilde{J}_{ji}=0\quad(\text{for all } i, j\in\mathcal{I})
$$

위 조건에 $\tilde{J} = \hat{C}\hat{G}\hat{J}$를 대입하여 행렬 성분으로 정리하면 $c_i (\hat{G}\hat{J})_{ij} = c_j (\hat{G}\hat{J})_{ji}$ 가 된다. 자코비안 행렬의 특성상 서로 마주보는 성분의 부호가 같으므로, 양변에 자연 로그(natural logarithm)를 취하여 다음과 같이 대수적인 차이 $b_{ij}$를 계산할 수 있다.

$$
\ln(c_i) - \ln(c_j) = \ln\left(\frac{(\hat{G}\hat{J})_{ji}}{(\hat{G}\hat{J})_{ij}}\right) \equiv b_{ij}
$$

치환 변수 $x_i = \ln(c_i)$를 도입하면, 본 식은 노드 간의 비대칭 플럭스 비율을 스칼라 포텐셜 장으로 맵핑하는 $\hat{S}x = b$ 형태의 과결정(overdetermined) 선형 연립방정식이 된다. 해의 유일성 확보를 위해 디리클레 경계 노드 집합 $\mathcal{B}$에 대하여 $c_k = 1.0$($x_k = 0$)의 기준점(anchoring) 조건을 부과한다. 최소자승법(least squares method)으로 해를 산출하고 지수 함수($c_i = e^{x_i}$)를 취해 대각 행렬 $\hat{C}$를 확립한다.

**2) 자코비안 분해**

대수적 변환이 적용된 유효 자코비안 $\tilde{J}$는 2.4절의 연산자 분해 방식($L = H + A$)에 따라 대칭 성분(Hermitian part, $\hat{H}$)과 다차원 공간의 교차 결합에 의해 발생하는 반대칭 성분(anti-Hermitian part, $\hat{A}_{raw}$)의 합으로 분리된다.

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

본 연구는 원본 자코비안 $\hat{J}$ 대신, 대칭 전제조건자 $\hat{J}_{pure}$를 탐색 행렬로 사용하여 변화량 $\delta u$를 산출하는 부정확 뉴턴법(Inexact Newton Method)을 적용한다. 선형 탐색 행렬은 대칭화되나 우변의 물리적 잔차 벡터 $F(u)$는 원본 상태를 유지한다. 알고리즘이 수렴 조건($\delta u \to 0$)에 도달하면, $\hat{J}_{pure} \delta u = -F(u)$ 관계식에 의해 항등적으로 $F(u^*) = 0$ 이 성립한다. 이는 제안된 대수적 대칭화 과정이 선형 탐색의 수치적 안정성만을 개선할 뿐, 최종 고정점(fixed point)의 물리적 엄밀성(exact solution)을 보장함을 증명한다.