+++
title = "CHAPTER 2"
weight = 15
+++

---

### 2.1 기초 지표의 공리적 정의와 레지듀 변환

본 절에서는 선형 연산자 $L$에 대한 레지듀 변환(residue transform) $\mathcal{R}L$을 정의하고, 이를 통해 연산자의 비정규성(non-normality)을 정량화하는 대수적 체계를 수립한다. 증명의 엄밀성을 위해 기하학적 도메인의 위상적 제약을 배제한 추상 힐베르트 공간(abstract Hilbert space)에서 공리를 먼저 선언하며, 이후 이를 물리적 연속계로 환원하여 해석학적 실체를 규명한다.

**1) 레지듀 변환의 대수적 공리**

복소 힐베르트 공간 $\mathcal{H}$에 속하는 임의의 상태 함수 $\phi, \psi \in \mathcal{H}$와 선형 연산자 $L$에 대하여, 레지듀 변환 연산자 $\mathcal{R}$을 다음의 항등식을 만족하는 사상으로 정의한다.

$$
\langle \phi, \mathcal{R}L \psi \rangle \equiv \langle \phi, L \psi \rangle - \langle L^\dagger \phi, \psi \rangle
$$

이때 $\langle \cdot, \cdot \rangle$는 $\mathcal{H}$ 상에서 정의된 보편적 쌍선형 형식(bilinear form)이며, $L^\dagger$는 $L$의 형식적 수반 연산자(formal adjoint operator)이다. 식 (2.1.1)은 연산자 $L$과 그 수반 연산자 $L^\dagger$ 사이의 대수적 괴리를 추출하는 핵심 공리로 기능한다.

**2) 병렬 결합의 선형성 증명**

정의된 레지듀 변환 $\mathcal{R}$은 선형 연산자의 기본적인 가산성을 만족한다. 임의의 복소 스칼라 $\alpha, \beta$와 선형 연산자 $A, B$에 대하여, 병렬 결합된 연산자에 레지듀 변환을 적용하면 다음과 같다.

$$
\langle \phi, \mathcal{R}(\alpha A + \beta B) \psi \rangle_{\partial \Omega} = \langle \phi, (\alpha A + \beta B) \psi \rangle_\Omega - \langle (\alpha A + \beta B)^\dagger \phi, \psi \rangle_\Omega
$$

수반 연산자의 분배 법칙인 $(\alpha A + \beta B)^\dagger = \alpha^* A^\dagger + \beta^* B^\dagger$을 적용하고 내적 연산의 선형성을 이용하여 식을 분리한 뒤, 각각 $A$와 $B$에 대하여 정리한다

$$
\langle \phi, \mathcal{R}(\alpha A + \beta B) \psi \rangle_{\partial \Omega} = \alpha \left( \langle \phi, A \psi \rangle_\Omega - \langle A^\dagger \phi, \psi \rangle_\Omega \right) + \beta \left( \langle \phi, B \psi \rangle_\Omega - \langle B^\dagger \phi, \psi \rangle_\Omega \right)
$$

괄호 안의 식은 각각 $A$와 $B$에 대한 레지듀 변환 정의와 동일하므로, 레지듀 사상은 다중 연산자의 병렬 결합에 대해 선형성을 가짐을 알 수 있다.

$$
\mathcal{R}(\alpha A + \beta B) = \alpha \mathcal{R}A + \beta \mathcal{R}B
$$

**3) 직렬 결합의 조립 법칙 증명**

두 선형 연산자의 직렬 결합(composition) $AB$에 대한 레지듀 변환의 전개 규칙을 유도한다. 결합된 연산자의 내적 $\langle \phi, AB \psi \rangle_\Omega$에서 연산자를 순차적으로 좌변으로 이동시킨다. 먼저 연산자 $A$에 대해 레지듀 변환 정의를 적용한다. 이때 상태 함수 $\psi$ 대신 $B\psi$를 하나의 함수로 취급하여 전개한다.

$$
\langle \phi, A(B \psi) \rangle_\Omega = \langle A^\dagger \phi, B \psi \rangle_\Omega + \langle \phi, (\mathcal{R}A) B \psi \rangle_{\partial \Omega}
$$

다음으로 우변에 생성된 내적 항 $\langle A^\dagger \phi, B \psi \rangle_\Omega$에 포함된 연산자 $B$에 대하여 동일한 정의를 적용한다.

$$
\langle A^\dagger \phi, B \psi \rangle_\Omega = \langle B^\dagger A^\dagger \phi, \psi \rangle_\Omega + \langle A^\dagger \phi, \mathcal{R}B \psi \rangle_{\partial \Omega}
$$

$$
\langle A^\dagger \phi, \mathcal{R}B \psi \rangle_{\partial \Omega} = \langle \phi, A(\mathcal{R}B) \psi \rangle_{\partial \Omega} - \langle \phi, (\mathcal{R}A)(\mathcal{R}B) \psi \rangle_{\partial \Omega}
$$

수반 연산자의 직렬 결합 법칙인 $(AB)^\dagger = B^\dagger A^\dagger$를 적용하여 도출된 항들을 종합하면, 두 연산자의 곱에 대한 전체 레지듀 변환은 2차 교차항(second-order interaction)을 포함하는 미분의 곱 법칙(Leibniz Rule)과 유사한 구조로 유도된다.

$$
\langle \phi, \mathcal{R}(AB) \psi \rangle_{\partial \Omega} = \langle \phi, (\mathcal{R}A) B \psi \rangle_{\partial \Omega} + \langle \phi, A(\mathcal{R}B) \psi \rangle_{\partial \Omega} - \langle \phi, (\mathcal{R}A)(\mathcal{R}B) \psi \rangle_{\partial \Omega}
$$

$$
\mathcal{R} (AB) = (\mathcal{R}A)B + A(\mathcal{R}B) - (\mathcal{R}A)(\mathcal{R}B)
$$

도출된 결합 법칙은 다중 미분 연산자가 결합될 때 레지듀 항이 전개되는 대수적 규칙을 나타낸다. 이 관계식은 이어지는 2.2절에서 다차원 미분 연산자의 결합 특성을 분석하고 공간 불균일성 지표를 유도하는 데 활용된다.

---

### 2.2 대수적 소멸과 국소 잔류

**1) 2계 보존 연산자 $\mathcal{R}(DpD)$의 대수적 특성: 수치적 최적화의 목적 함수**

본 연구에서 분석하는 대상은 물성 계수 $p$가 공간상에서 항상 0보다 큰 일정한 하한값을 가지는 강타원형(strongly elliptic) 연산자는 에너지를 안정적으로 확산시켜 열역학적 평형을 이루는 보존계임을 의미한다. 공간의 차원이나 좌표계에 의존하지 않는 연산자 관계식을 구성하기 위해, 일반화된 1계 미분 연산자 $D$를 도입한다. 시스템의 2계 강타원형 연산자 $L$은 순수 미분 연산자 $D$와 물성 결합 연산자 $pD$의 직렬 결합인 $L = DpD$로 나타낼 수 있다. 도메인 경계 $\partial \Omega$ 근방에서 소멸하는 콤팩트 지지(compact support) 검사 함수 공간 $C_c^\infty(\Omega)$에서의 부분 적분 원리에 의해, 연산자 $D$는 형식적 반대칭성(formal skew-adjointness, $D^\dagger = -D$)을 만족하며, 연산자 대수 내에서 곱의 미분 법칙인 라이프니츠 규칙 $D(p \cdot) = (Dp)\cdot + pD$ 가 성립한다.  이를 바탕으로 두 기본 연산자 $D$와 $pD$의 레지듀 변환을 구하면 다음과 같다.

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

이 결과는 2계 보존 연산자의 경우, 적분 시 도메인 내부에 남는 항이 없음을 보여준다. 연산자 $D$는 유한체적법(FVM)에서 사용하는 경계면 미분(edge derivative)과 구조적으로 같으므로 이 성질은 이산 공간에도 적용할 수 있다. 그러나 실제 이산 격자에서는 절단 오차(truncation error)로 인해 항들이 완전히 지워지지 않아 내부에 오차(레지듀)가 남게 된다. 따라서 본 연구에서는 이 내부 잔류항을 0으로 수렴시키는 조건($\mathcal{R}L_{int} \to 0$)을 이산화 오차를 줄이기 위한 최적화 목적 함수(objective function)로 설정한다.

**2) 1계 물성 결합 연산자 $\mathcal{R}(pD)$: 국소 지표의 활용**

앞서 구한 1계 물성 결합 연산자의 레지듀 사상 $\mathcal{R}(pD) = 2pD + (Dp)$의 특성을 살펴본다. 이 식을 임의의 상태 함수 $\psi$에 작용시키고 내적 공간의 약형식으로 표현하여 적분 정리를 수행하면 다음과 같은 적분 등식을 얻는다.

$$
\int_\Omega \mathcal{R}(pD) \psi d\Omega = \oint_{\partial \Omega} p \psi \vec{n} dS + \int_\Omega (2pD + Dp) \psi d\Omega
$$

이 결과는 내부 적분항이 0이 되는 2계 연산자의 경우와 차이를 보인다. 우변의 두 번째 항 $\int_\Omega (2pD + Dp) \psi d\Omega$는 전미분 형태로 묶이지 않아 경계 적분으로 변환되지 않고 도메인 내부에 남는다. 이는 물성의 공간적 변화량($Dp$)이 존재할 경우, 도메인 내부에서 추가적인 대수적 항이 발생함을 의미한다. 연속계에서 나타나는 이러한 특성은 3장에서 다룰 이산 격자 공간에서 전역적 비대칭 지표 $S_{kj}$를 정의하고 메트릭(Metric)을 조립하기 위한 기초 지표로 사용된다.

**3) 비선형 자코비안 연산자의 대수적 소멸성 확장**

앞서 살펴본 선형 2계 강타원형 연산자의 특성은 상태 변수 $u$에 종속적인 비선형 잔차 방정식 $R(u)=0$의 자코비안 연산자 $J = \partial R / \partial u$로 확장할 수 있다. 임의의 섭동(perturbation) $v$에 대한 자코비안의 선형 방정식을 연산자 $D$를 이용해 전개하면 다음과 같다.

$$
Jv = D(p(u) Dv) + D \left( \frac{\partial p}{\partial u} v Du \right) + \frac{\partial q}{\partial u} v
$$

이 식에서 2계 주항인 $D(pD\cdot)$와 0계 항인 $\frac{\partial q}{\partial u}\cdot$는 내적 공간에서 자기 수반성(self-adjointness)을 갖는다. 상태 변수의 변화와 물성 변화량 사이의 관계를 나타내는 1계 결합항 $D \left( \frac{\partial p}{\partial u} (Du) \cdot \right)$의 경우, 대상 시스템을 강타원형 보존계로 한정하였으므로 교차 대칭성(cross-symmetry)을 갖는 것으로 다룰 수 있다.

이러한 자코비안의 내부 특성을 외부 경계의 간섭 없이 파악하기 위해, 도메인 경계 $\partial \Omega$에서 값이 0이 되는 매끄러운 함수들의 집합인 콤팩트 지지 공간(compact support space) $C_c^\infty(\Omega)$을 검사 함수 공간으로 도입한다. 이 공간에 속하는 임의의 함수 $\phi, \psi$에 대하여 약형식 내적 $\langle \phi, J \psi \rangle_\Omega$을 계산하면, 부분 적분을 수행할 때 경계 적분 항이 모두 소거된다.

따라서 연산자 $D$의 반대칭성($D^\dagger = -D$)에 의해 적분 기호 내부에서 $\phi$와 $\psi$의 위치를 바꿀 수 있으며, 결과적으로 1차 변분 공간(first variational space)에서 자코비안 연산자 $J$는 형식적으로 자기 수반성($J = J^\dagger$)을 만족하게 된다.

$$
\mathcal{R}J_{int} = J - J^\dagger = 0 \quad \text{in } \Omega
$$

이러한 성질은 연속계에서 비선형 자코비안이 도메인 내부에 레지듀를 생성하지 않음을 보여준다. 그러므로 이산 격자 공간에서 뉴턴-랩슨(Newton-Raphson) 방법과 같은 비선형 해법을 사용할 때 나타나는 자코비안 행렬의 비대칭성(non-normality)은 물리적인 특성이 아니라 공간 이산화 과정에서 생기는 수치적 오차로 해석할 수 있다. 이를 바탕으로, 비선형 시스템에서도 내부 레지듀를 0으로 만드는 조건($\mathcal{R}J_{int} \to 0$)을 이산 행렬의 대칭성을 보정하는 기준으로 활용한다.

---

### 2.3 연산자 보존 법칙 (Operator Conservation Law)

본 절에서는 2.1절에서 정의한 레지듀 변환 $\mathcal{R}$을 이용하여, 선형 연산자가 내적 공간에서 만족하는 대수적 관계식을 유도한다. 이를 통해 연산자의 비대칭성(non-normality)과 상태 함수의 크기(norm) 변화, 그리고 경계에서 발생하는 레지듀 사이의 관계를 설명한다.

**1) 비정규성의 대수적 분해와 연산자 보존 법칙**

선형 연산자 $L$의 대수적 비대칭성을 확인하기 위해, 연산자 $L$과 수반 연산자 $L^\dagger$의 교환자(commutator) $[L^\dagger, L] = L^\dagger L - L L^\dagger$를 계산한다. 임의의 상태 함수 $\psi$에 대한 이 교환자의 기댓값은 다음과 같이 두 내적의 차이로 나타낼 수 있다.

$$
\langle \psi, [L^\dagger, L] \psi \rangle_\Omega = \langle \psi, L^\dagger L \psi \rangle_\Omega - \langle \psi, L L^\dagger \psi \rangle_\Omega
$$

우변의 각 내적 항에 2.1절에서 정의한 레지듀 변환을 적용한다. 연산자를 내적의 좌변으로 이동시키고 $(L^\dagger)^\dagger = L$의 성질을 이용하면, 각 항은 함수의 노름(norm)의 제곱($\|\cdot\|^2$)과 경계 레지듀 항의 합으로 정리된다.

$$
\langle \psi, L^\dagger (L\psi) \rangle_\Omega = \|L\psi\|^2 + \langle \psi, \mathcal{R}L^\dagger L \psi \rangle_{\partial \Omega}
$$

$$
\langle \psi, L (L^\dagger \psi) \rangle_\Omega = \|L^\dagger \psi\|^2 + \langle \psi, \mathcal{R}L L^\dagger \psi \rangle_{\partial \Omega}
$$

이 식들을 처음의 교환자 기댓값 식에 대입하여 정리하면 다음과 같은 항등식을 얻을 수 있다.

$$
\langle \psi, [L^\dagger, L] \psi \rangle_\Omega = \left( \|L\psi\|^2 - \|L^\dagger \psi\|^2 \right) + \langle \psi, (\mathcal{R}L^\dagger L - \mathcal{R}L L^\dagger) \psi \rangle_{\partial \Omega}
$$

이 식은 교환자의 기댓값이 도메인 내부에서의 노름 차이와 경계에서 발생하는 레지듀 항들의 결합으로 나뉨을 보여준다. 본 논문에서는 우변의 경계 레지듀 결합 항인 $\mathcal{R}L^\dagger L - \mathcal{R}L L^\dagger$를 연산자의 비정규성을 나타내는 지표로 보고, 이 관계를 연산자 보존 법칙(Operator Conservation Law)이라고 부른다.

**2) 레지듀 론스키안 행렬의 조립과 스펙트럼 왜곡**

앞서 구한 레지듀 결합 항은 변환된 연산자 $(\mathcal{R}L^\dagger, \mathcal{R}L)$와 원래의 연산자 $(L^\dagger, L)$가 결합된 형태를 가진다. 이를 행렬 형태로 나타내기 위해 다음과 같이 $2 \times 2$ 크기의 레지듀 론스키안(Residue Wronskian) 행렬 $W_\mathcal{R}$을 구성한다.

$$
W_\mathcal{R}(L^\dagger,L) = \begin{pmatrix} \mathcal{R}L^\dagger & \mathcal{R}L \\\ L^\dagger & L \end{pmatrix}
$$

이 행렬을 이용하면 연산자의 수반성(adjointness)이 성립하지 않는 정도를 행렬식(determinant)을 통해 확인할 수 있다. 연산자의 곱 순서를 유지하면서 행렬식을 계산하면 다음과 같은 결과를 얻는다.

$$
\text{det}(W_\mathcal{R}(L^\dagger,L)) = \mathcal{R}L^\dagger L - \mathcal{R}L L^\dagger
$$

이 행렬식의 값은 연산자 $L$과 수반 연산자 $L^\dagger$가 내적 공간에서 서로 얼마나 다른 방향으로 작용하는지를 나타낸다. 만약 $\text{det}(W_\mathcal{R}) = 0$이라면, 두 연산자는 선형 종속 관계를 가지므로 대수적인 차이가 없음을 의미한다. 반면, 이류(advection)와 같은 비가역적인 흐름이 포함된 비대칭 연산자에서는 두 연산자가 서로 독립적으로 작용하여 $\text{det}(W_\mathcal{R}) \neq 0$이 된다. 본 논문에서는 이 행렬식이 0이 아닌 상태를 연산자의 스펙트럼 왜곡(Spectral Skewness)이라고 부른다. 이는 에너지가 보존되지 않고 한 방향으로 흐르는 정도를 나타내며, 이어지는 3장에서 대수적 텐션 지표 $\hat{C}$를 구하기 위해 이 왜곡을 0으로 만드는 조건($\text{det}(W_\mathcal{R}) = 0$)을 기준으로 사용하게 된다.

**3) 벌크-경계 소산 정리 (Bulk-Boundary Dissipation Theorem)**

미분 연산자를 대칭 성분과 반대칭 성분으로 나누어 살펴본다. 이를 통해 도메인 내부(bulk)에서의 상호작용과 경계(boundary)에서 발생하는 레지듀 사이의 관계를 나타내는 벌크-경계 소산 정리를 설명한다. 힐베르트 공간에 정의된 임의의 선형 연산자 $L$은 자기 수반성을 갖는 대칭 성분(Hermitian part, $H$)과 반대칭 성분(anti-Hermitian part, $A$)의 합으로 나타낼 수 있다. 따라서 연산자 $L$과 그 수반 연산자 $L^\dagger$는 이 두 성분을 이용하여 각각 $L = H + A$ 와 $L^\dagger = H - A$ 로 쓸 수 있다. 이 분해 관계를 2.3절에서 다룬 교환자 $[L^\dagger, L]$에 대입하여 전개한다. 교환자의 성질에 따라 같은 성분끼리의 교환자인 $[H, H]$와 $[A, A]$는 0이 되고, 교차항들은 다음과 같이 하나로 합쳐진다.

$$
[L^\dagger, L] = [H - A, H + A] = 2[H, A]
$$

이 결과는 연산자의 비대칭성(non-normality)이 대칭 성분 $H$와 반대칭 성분 $A$ 간의 상호작용을 나타내는 교환자 $[H, A]$에 의해 결정됨을 의미한다.

위에서 구한 식을 연산자 보존 법칙에 대입한다. 상태 함수 $\psi$에 대한 교환자 기댓값의 좌변을 $2\langle \psi, [H, A] \psi \rangle_\Omega$로 바꾸고, 양변을 2로 나누어 정리하면 다음과 같은 벌크-경계 소산 정리(Bulk-Boundary Dissipation Theorem) 식을 얻는다.

$$
\langle \psi, [H, A] \psi \rangle_\Omega = \frac{1}{2} \left( \|L\psi\|^2 - \|L^\dagger \psi\|^2 \right) + \langle \psi, \text{det}(W_\mathcal{R}(H,A)) \psi \rangle_{\partial \Omega}
$$

이 식의 좌변은 도메인 내부에서 대칭 성분과 반대칭 성분 사이의 상호작용으로 인해 발생하는 내부 소산(internal dissipation)을 나타낸다. 우변의 첫 번째 항은 연산자 $L$과 수반 연산자 $L^\dagger$ 적용에 따른 전체적인 노름(norm) 차이를 의미한다. 즉, 시스템 내부에서의 상호작용 크기는 전체 공간에서의 상태 변화량과 경계에서 발생하는 레지듀의 합으로 이루어진다. 우변의 두 번째 항인 레지듀 론스키안의 행렬식 부분은 각 성분의 레지듀 사상 특성($\mathcal{R}H = 0$, $\mathcal{R}A = 2A$)을 반영하여 아래와 같이 계산된다.

$$
W_\mathcal{R}(H, A) = \begin{pmatrix} 0 & 2A \\\ H & A \end{pmatrix}
\implies \text{det}(W_\mathcal{R}(H, A)) = -2AH
$$

이러한 정리는 연산자의 비대칭성으로 인한 시스템 내부의 소산 작용이 주로 반대칭 성분 $A$에 의해 발생함을 보여준다. 공간을 이산화하여 격자망을 구성할 때 격자의 형태가 불균일하면, 이 반대칭 성분 부분에 이산화 오차에 의한 수치적 소산(artificial dissipation)이 더해질 수 있다. 따라서 벌크-경계 소산 정리는 시스템의 전체 상호작용을 내부 도메인에서의 작용($[H, A]$)과 경계에서의 작용($\text{det}(W_\mathcal{R})$)으로 나누어 분석할 수 있게 해준다. 이는 이어지는 3장에서 이산화된 전체 시스템 행렬을 대칭 행렬과 반대칭 행렬로 분리하고, 경계 처리를 통해 수치적 발산을 제어하는 방법론의 이론적 바탕이 된다.
