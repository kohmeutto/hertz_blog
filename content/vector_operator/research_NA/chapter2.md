+++
title = "CHAPTER 2"
weight = 15
+++

---

### 2. 연산자 레지듀 변환과 내부 비정규성 분석

본 절에서는 임의의 선형 연산자 $L$에 대한 경계 비대칭성 추출 및 레지듀 변환(residue transform)의 수학적 정의를 수립한다. 유계 도메인(bounded domain) $\Omega \subset \mathbb{R}^d$와 그 경계 $\partial \Omega$에서 정의된 함수 공간을 고려하여 연속계에서의 관계식을 전개한다.

**1) 레지듀 변환 정의와 해석**

미분 연산자의 대수적 및 수학적 특성을 엄밀하게 분석하기 위해, 우선 완비된 복소 힐베르트 공간(complex Hilbert space) $\mathcal{H}$를 도입한다. 이 공간에 속하는 임의의 상태 함수 $\phi, \psi \in \mathcal{H}$에 대하여 보편적 내적 $\langle \cdot, \cdot \rangle$이 정의된다고 가정한다. 이 추상적 내적 공간에서 선형 연산자 $L$이 작용할 때, 그 형식적 수반 연산자(formal adjoint operator) $L^\dagger$는 내적의 우측 인자에서 좌측 인자로 전이되는 대수적 규칙을 따른다.

일반적인 경계치 문제나 이산화된 수치 공간에서는 공간의 유계성(boundedness)이나 절단 오차로 인해 시스템 전체에서 전역적인 자기 수반성(global self-adjointness)이 보존되지 않는다. 즉, 임의의 연산자 $L$과 그 형식적 수반 연산자 $L^\dagger$ 사이에 대수적 괴리가 발생한다. 연산자의 비정규성(non-normality)을 정량화하기 위해, 확립된 힐베르트 공간 $\mathcal{H}$ 위에서 레지듀 변환 연산자 $\mathcal{R}$을 다음의 대수적 항등식을 만족하는 사상으로 정의한다.

$$
\langle \phi, \mathcal{R}L \psi \rangle \equiv \langle \phi, L \psi \rangle - \langle L^\dagger \phi, \psi \rangle
$$

이러한 추상 대수적 공리를 물리적 공간의 실체로 환원하기 위해 유계 도메인 $\Omega$를 고려한다. 상태 함수 $\phi, \psi$에 대한 연속 공간 내적을 다음과 같이 구체화하여 정의한다.

$$
\langle \phi, \psi \rangle_\Omega = \int_\Omega \phi^* \psi d\Omega
$$

위 식에서 $\phi^*$는 $\phi$의 복소 공액(complex conjugate)을 의미한다. 이 연속 내적 공간에서 미분 연산자 $L$의 수반 연산자 $L^\dagger$는 부분 적분(integration by parts) 혹은 가우스 발산 정리(divergence theorem)를 적용하여 도출할 수 있다. 주기적 경계 조건이 없는 일반적인 유계 도메인에서는 미분 연산자를 내적의 우변에서 좌변으로 이동시킬 때, 경계 $\partial \Omega$에서 평가되는 적분 항이 발생한다. 이러한 해석학적 원리에 따라, 앞서 정의된 대수적 레지듀 사상은 물리적 공간에서 다음과 같은 약형식(weak form) 내적 관계로 사상된다.

$$
\langle \phi, \mathcal{R}L \psi \rangle_{\partial \Omega} \equiv \langle \phi, L \psi \rangle_\Omega - \langle L^\dagger \phi, \psi \rangle_\Omega
$$

만약 연산자가 도메인 내부에서 형식적 자기 수반성(formal self-adjointness)을 만족한다면, 부분 적분의 원리에 따라 두 내적의 차이는 외부 경계 $\partial \Omega$ 상의 표면 적분으로 환원된다. 즉, 경계 조건에 의해 우변에 값이 남더라도 이는 시스템의 외부 경계에만 존재할 뿐, 도메인 내부(interior bulk)에서는 0이 된다. 반면, 상태 종속적 비선형성으로 인해 연산자의 수반성이 유지되지 않는 계에서는, 내적의 차이가 경계로 완전히 환원되지 못하고 시스템의 내부 도메인 $\Omega$에 0이 아닌 적분항을 남긴다. 본 프레임워크는 이처럼 경계로 배출되지 못하고 도메인 내부에 남는 값을 연산자의 비정규성 및 물리적 대류/표류(convection/drift) 강도를 측정하는 독립적인 척도로 사용한다.

정의된 레지듀 변환 $\mathcal{R}$은 선형 연산자의 기본적인 가산성(additivity)과 동차성(homogeneity)을 만족한다. 임의의 복소 스칼라 $\alpha, \beta \in \mathbb{C}$와 선형 연산자 $A, B$에 대하여, 병렬 결합된 연산자에 레지듀 변환 공리를 적용하면 다음과 같다.

**2) 선형성**

$$
\langle \phi, \mathcal{R}(\alpha A + \beta B) \psi \rangle_{\partial \Omega} = \langle \phi, (\alpha A + \beta B) \psi \rangle_\Omega - \langle (\alpha A + \beta B)^\dagger \phi, \psi \rangle_\Omega
$$

수반 연산자의 분배 법칙인 $(\alpha A + \beta B)^\dagger = \alpha^* A^\dagger + \beta^* B^\dagger$을 적용하고 내적 연산의 선형성을 이용하여 식을 분리한 뒤, 각각 $A$와 $B$에 대하여 스칼라 계수를 기준으로 정리한다.

$$
\langle \phi, \mathcal{R}(\alpha A + \beta B) \psi \rangle
= \alpha \left( \langle \phi, A \psi \rangle - \langle A^\dagger \phi, \psi \rangle \right) + \beta \left( \langle \phi, B \psi \rangle - \langle B^\dagger \phi, \psi \rangle \right)
$$

$$
= \alpha \langle \phi, \mathcal{R}A\psi \rangle + \beta \alpha \langle \phi, \mathcal{R}A\psi \rangle
$$

---

### 2.2 대수적 소멸과 국소 잔류

**1) 2계 보존 연산자 $\mathcal{R}(DpD)$의 대수적 특성: 수치적 최적화의 목적 함수**

본 연구에서 분석하는 대상은 강타원형(strongly elliptic) 연산자 시스템이다. 이는 물성 계수 $p$가 공간상에서 항상 0보다 큰 일정한 하한값을 가지며, 에너지를 안정적으로 확산시켜 열역학적 평형을 이루는 보존계(conservative system)임을 의미한다. 공간의 차원이나 좌표계에 의존하지 않는 보편적 연산자 관계식을 구성하기 위해, 일반화된 1계 미분 연산자 $D$를 도입한다. 시스템의 2계 강타원형 연산자 $L$은 순수 미분 연산자 $D$와 물성 결합 연산자 $pD$의 직렬 결합인 $L = DpD$로 나타낼 수 있다.

"연산자 $D$의 본질적인 대수적 특성을 규명하기 위해, 도메인 경계 $\partial \Omega$ 근방에서 소멸하는 콤팩트 지지(compact support) 검사 함수 공간 $C_c^\infty(\Omega)$를 시험 공간(test space)으로 도입한다. 이 공간에서의 부분 적분을 수행하면 경계 배출 항이 소멸되므로, 연산자 $D$는 내부 도메인에서 형식적 반대칭성(formal skew-adjointness, $D^\dagger = -D$)을 만족함을 대수적으로 확정할 수 있다. 이렇게 규명된 $D$의 성질과 라이프니츠 규칙 $D(p \cdot) = (Dp)\cdot + pD$ 가 성립한다. 이를 바탕으로 두 기본 연산자 $D$와 $pD$의 레지듀 변환을 구하면 다음과 같다.

$$
\mathcal{R}(D) = D - D^\dagger = 2D
$$

$$
\mathcal{R}(pD) = pD - D^\dagger p = pD + Dp = 2pD + (Dp)
$$

구해진 1계 연산자의 레지듀를 직렬 조립 법칙 $\mathcal{R}(AB) = (\mathcal{R}A)B + A(\mathcal{R}B) - (\mathcal{R}A)(\mathcal{R}B)$에 대입하여 전개한다.

$$
\mathcal{R}(DpD) = \underbrace{(2D)(pD)}_{\text{Term 1}} + \underbrace{D(2pD + (Dp))}_{\text{Term 2}} - \underbrace{(2D)(2pD + (Dp))}_{\text{Term 3}}
$$

위 식을 분배 법칙을 이용해 풀어서 쓰면 아래와 같이 나타난다.

$$
\mathcal{R}(DpD) = [2DpD] + [2DpD + D((Dp) \cdot)] - [4DpD + 2D((Dp) \cdot)]
$$

이 수식을 정리하면 동질적인 결합을 갖는 $DpD$ 항들은 서로 지워지고, 다음과 같이 하나의 연산자 형태로 단순해진다. 임의의 상태 함수 $\psi$에 작용시킨 결과는 다음과 같다.

$$
\mathcal{R}(DpD) \psi = -D((Dp)\psi)
$$

이 식이 연속계의 도메인 내부에서 가지는 의미를 확인하기 위해 전체 도메인 $\Omega$에 대해 적분한다. 연산자 $D$가 순수 미분 형태이므로, 스토크스 정리(Stokes' theorem)를 적용하면 체적 적분은 다음과 같이 경계 $\partial \Omega$에서의 표면 적분으로 변환된다.

$$
\int_\Omega \mathcal{R}(DpD) \psi d\Omega = -\oint_{\partial \Omega} (Dp)\psi \cdot \vec{n} dS
$$

이 결과는 2계 보존 연산자의 경우, 적분 시 도메인 내부에 남는 항이 없음을 보여준다. 연산자 $D$는 유한체적법(FVM)에서 사용하는 경계면 미분(edge derivative)과 구조적으로 같으므로 이 성질은 이산 공간에도 적용할 수 있다. 그러나 실제 이산 격자에서는 절단 오차(truncation error)로 인해 항들이 완전히 지워지지 않아 내부에 오차가 남게 된다. 따라서 본 연구에서는 공간 이산화 과정에서 발생하는 잔류항을 억제하기 위해, 각 절점(node)에 할당된 제어 체적(control volume)을 기반으로 기하학적 메트릭을 구성하여 $\mathcal{R}(DpD)_{int} = 0$ 이 성립되도록 시스템을 이산화한다.

**2) 1계 물성 결합 연산자 $\mathcal{R}(pD)$: 국소 지표의 활용**

앞서 구한 1계 물성 결합 연산자의 레지듀 사상 $\mathcal{R}(pD) = 2pD + (Dp)$의 특성을 살펴본다. 이 식을 임의의 상태 함수 $\psi$에 작용시키고 내적 공간의 약형식으로 표현하여 적분 정리를 수행하면 다음과 같은 적분 등식을 얻는다.

$$
\int_\Omega \mathcal{R}(pD) \psi d\Omega = \oint_{\partial \Omega} p \psi \vec{n} dS + \int_\Omega (2pD + Dp) \psi d\Omega
$$

이 결과는 내부 적분항이 0이 되는 2계 연산자의 경우와 차이를 보인다. 우변의 두 번째 항 $\int_\Omega (2pD + Dp) \psi d\Omega$는 전미분 형태로 묶이지 않아 경계 적분으로 변환되지 않고 도메인 내부에 남는다. 이는 물성의 공간적 변화량($Dp$)이 존재할 경우, 도메인 내부에서 추가적인 대수적 항이 발생함을 의미한다. 연속계에서 나타나는 이러한 특성은 3장에서 다룰 이산 격자 공간에서 국소적 비대칭 지표 $S_{kj}$를 정의하고 메트릭(Metric)을 조립하기 위한 기초 지표로 사용된다.

**3) 비선형 자코비안 연산자의 비정규성 통제**

선형 강타원형 시스템의 특성은 상태 변수 $u$에 종속적인 비선형 지배 방정식 $F(u) = D(p(u)Du) - q(u) = 0$ 의 프레셰 도함수(Fréchet derivative)인 자코비안 연산자 $J = \partial F / \partial u$ 로 확장된다. 임의의 미소 섭동(perturbation) $\delta u$에 대한 자코비안 방정식은 다음과 같이 전개된다.

$$
J \delta u = D(p(u) D\delta u) + D \left( \frac{\partial p}{\partial u} \delta u Du \right) - \frac{\partial q}{\partial u} \delta u
$$

이 식에서 2계 주항인 $D(pD\cdot)$와 0계 항인 $-\frac{\partial q}{\partial u}\cdot$는 내적 공간에서 자기 수반성(self-adjointness)을 갖는다. 그러나 상태 변수의 변화와 물성 변화량 사이의 결합을 나타내는 1계 항 $D \left( \frac{\partial p}{\partial u} (Du) \cdot \right)$는 비선형 시스템에 고유한 방향성 흐름(Convection/Drift)을 생성한다.이러한 대류적 물리 특성으로 인해, 실제 자코비안 연산자 $J$는 도메인 내부에서 자기 수반성을 상실하며 내부 레지듀($\mathcal{R}J_{int} \neq 0$)를 필연적으로 생성한다. 이 물리적 비정규성은 수치적으로 행렬의 조건수(condition number)를 악화시켜 선형 해법의 발산을 초래하는 요인으로 작용한다. 따라서 수치적 안정성을 확보하기 위해, 내부 레지듀가 소멸되는 대칭 형태($\mathcal{R}\tilde{J}_{int} = 0$)를 유효 자코비안의 구속 조건으로 설정한다. 이를 바탕으로 3장에서는 물리적 잔차는 유지하면서 탐색 방향만을 안정화하는 대칭 전제조건자(Preconditioner) $\tilde{J}$를 대수적으로 유도한다.

---
