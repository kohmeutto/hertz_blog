+++
title = "CHAPTER 2"
weight = 15
+++

---

본 절에서는 비선형 시스템의 자코비안(Jacobian) 행렬이 이산 공간에서 조건수(condition number) 악화를 유발하는 수학적 근원을 해석적으로 규명한다. 이를 위해 임의의 선형 연산자 $L$에 대한 레지듀 변환(residue transform)의 수학적 정의를 수립하고, 프레셰 도함수(Fréchet derivative)의 항별 레지듀 소멸 증명을 통해 비대칭성을 유발하는 1계 대류 연산자(Advection operator)의 내부 잔차 약형식을 엄밀하게 도출한다.

---

### 2.1 연산자 레지듀 변환

미분 연산자의 대수적 특성을 분석하기 위해, 완비된 복소 힐베르트 공간(complex Hilbert space) $\mathcal{H}$ 상에서 상태 함수 $\phi, \psi \in \mathcal{H}$ 에 대한 보편적 내적 $\langle \phi, \psi \rangle = \int_\Omega \phi^* \psi d\Omega$ 를 정의한다.

시스템의 전역적 자기 수반성(self-adjointness)이 보존되지 않는 경우, 임의의 연산자 $L$과 그 형식적 수반 연산자(formal adjoint operator) $L^\dagger$ 사이에는 대수적 괴리가 발생한다. 본 프레임워크에서는 이 비정규성을 정량화하기 위해, 레지듀 변환 연산자 $\mathcal{R}$을 오직 우측 상태 함수 $\psi$에만 작용하는 단방향 연산자로 확립한다.

$$
\mathcal{R}(L) \equiv L - L^\dagger
$$ 

내적 공간의 약형식(weak form) 전개는 다음과 같다.

$$
\langle \phi, \mathcal{R}(L) \psi \rangle \equiv \langle \phi, (L - L^\dagger) \psi \rangle = \langle \phi, L \psi \rangle - \langle \phi, L^\dagger \psi \rangle
$$

이 레지듀 연산자는 선형 연산자의 기본적인 가산성(additivity)과 동차성(homogeneity)을 보존한다. 물리계의 실수 스칼라 계수 $\alpha, \beta \in \mathbb{R}$ 와 임의의 선형 연산자 $A, B$ 의 선형 결합에 대하여, 수반 연산자의 분배 법칙 $(\alpha A + \beta B)^\dagger = \alpha A^\dagger + \beta B^\dagger$ 을 적용하면 다음이 성립한다.

$$\mathcal{R}(\alpha A + \beta B) = (\alpha A + \beta B) - (\alpha A + \beta B)^\dagger = \alpha(A - A^\dagger) + \beta(B - B^\dagger)
$$

$$
= \alpha \mathcal{R}(A) + \beta \mathcal{R}(B)
$$

---

### 2.2 비선형 자코비안 연산자의 프레셰 도함수 유도

강타원형(strongly elliptic) 보존계 지배 방정식 $F(u) = D(p(u)Du) - q(u) = 0$ 의 프레셰 도함수(Fréchet derivative)인 자코비안 $J = \partial F / \partial u$ 를 전개한다. 상태 변수 $u$에 가해진 미소 섭동 $\delta u$ 에 대하여, 물성 $p(u)$와 소스 $q(u)$를 1차 테일러 전개하고 $O(\delta u^2)$ 을 소거하면 자코비안 연산자 방정식 $J \delta u = F(u + \delta u) - F(u)$ 는 다음과 같이 도출된다.

$$
J \delta u = \underbrace{D(p(u) D\delta u)}_{L_2: \text{2계 항}} + \underbrace{D \left( \frac{\partial p}{\partial u} Du \delta u \right)}_{L_1: \text{1계 항}} \underbrace{- \frac{\partial q}{\partial u} \delta u}_{L_0: \text{0계 항}}
$$

여기서 상태 변수 구배($Du$)와 물성 변화율($\frac{\partial p}{\partial u}$)의 곱을 유효 표류 속도(Effective Drift Velocity) $v \equiv \frac{\partial p}{\partial u} Du$ 로 정의하면, 1계 항은 $L_1 = D(v \cdot)$ 형태의 대류 연산자(Advection operator)로 환원된다.

전체 자코비안 $J = L_2 + L_1 + L_0$ 의 비대칭성을 규명하기 위해, 앞서 증명된 선형성에 의거하여 레지듀 연산자를 각 항에 개별적으로 분배 적용한다.

$$\mathcal{R}(J) = \mathcal{R}(L_2) + \mathcal{R}(L_1) + \mathcal{R}(L_0)$$콤팩트 지지(compact support) 검사 함수 공간 $C_c^\infty(\Omega)$에서의 부분 적분(경계 항 소멸)을 통해 각 항의 레지듀를 평가한다.0계 소스 항 ($L_0$): $L_0 = -\frac{\partial q}{\partial u}$ 는 순수 실수 스칼라 함수이다. 스칼라 곱은 공간 내적에서 교환 법칙이 성립하므로 $\langle \phi, L_0 \psi \rangle = \langle L_0 \phi, \psi \rangle$ 이다. 따라서 형식적 수반 연산자 $L_0^\dagger = L_0$ 이 되며, 레지듀 사상 결과는 항등적으로 소멸한다.$$\mathcal{R}(L_0) = L_0 - L_0^\dagger = 0$$2계 주항 ($L_2$):$L_2 = D(pD \cdot)$ 에 대하여 약형식 전개를 수행한다.$$\langle \phi, D(pD\psi) \rangle = -\langle D\phi, pD\psi \rangle$$여기서 물성 $p$는 실수 스칼라이므로 $pD\psi$ 에 곱해지나 $D\phi$ 에 곱해지나 동일하다. 한 번 더 부분 적분을 수행하여 미분 연산자를 이동시킨다.$$-\langle pD\phi, D\psi \rangle = \langle D(pD\phi), \psi \rangle$$결과적으로 $L_2^\dagger = D(pD \cdot) = L_2$ 이며, 2계 확산 연산자는 완전한 형식적 자기 수반성을 가지므로 레지듀는 소멸한다.$$\mathcal{R}(L_2) = L_2 - L_2^\dagger = 0$$결론: 0계 항과 2계 항의 레지듀가 대수적으로 소멸함에 따라, 전체 자코비안의 비정규성을 지배하는 연산자는 오직 1계 대류 연산자 $L_1$ 으로 귀결된다.$$\mathcal{R}(J) = \mathcal{R}(L_1)$$4) 1계 대류 연산자의 내부 잔차 약형식 도출살아남은 1계 대류 연산자 $L_1 = D(v \cdot)$ 에 레지듀 사상 $\mathcal{R}(L) = L - L^\dagger$ 를 적용한다.부분 적분에 의해 대류 연산자의 형식적 수반 연산자는 $\langle \phi, D(v\psi) \rangle = \langle -vD\phi, \psi \rangle$ 로부터 $L_1^\dagger = -vD$ 로 결정된다. 이를 대입하여 1계 레지듀 사상을 전개한다.$$\mathcal{R}(L_1)\psi = (L_1 - L_1^\dagger)\psi = D(v\psi) - (-vD\psi) = D(v\psi) + v(D\psi)$$여기에 연속 공간의 라이프니츠 법칙(Leibniz rule) $D(v\psi) = (Dv)\psi + v(D\psi)$ 를 첫 번째 항에 적용하여 분해한다.$$\mathcal{R}(L_1)\psi = \left[ (Dv)\psi + v(D\psi) \right] + v(D\psi) = (Dv)\psi + 2v(D\psi)$$이를 내적 공간의 약형식으로 최종 표현하면, 비선형 자코비안 행렬에서 발생하는 내부 잔차(Internal Residue)의 대수적 실체가 다음과 같이 규명된다.$$\langle \phi, \mathcal{R}(J)_{int}\psi \rangle_\Omega = \langle \phi, \left[ (Dv)\psi + 2v(D\psi) \right] \rangle_\Omega$$본 증명은 유효 표류 속도의 발산량($Dv$)과 동질적 이류 작용($2vD$)이 결합될 때 시스템 내부의 비대칭성이 폭발함을 수학적으로 확정짓는다. 이 도출된 1계 대류 잔차 약형식은 3장에서 이산 공간의 교환자 오차(commutator error)를 분석하고 위상 공간을 재배치하는 국소 비대칭 지표 산출의 엄밀한 대수적 근거로 활용된다.
