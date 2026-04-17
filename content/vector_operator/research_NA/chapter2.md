+++
title = "CHAPTER 2"
weight = 15
+++

---

### CHAPTER 2. 비정규 연산자의 레지듀 사상과 프레셰 도함수 전개

본 장에서는 비선형 시스템의 자코비안(Jacobian) 행렬이 이산 공간에서 조건수(condition number) 악화를 유발하는 근원을 대수적으로 분석한다. 선형 연산자 $L$에 대한 레지듀 변환(residue transform)을 정의하고, 이를 바탕으로 프레셰 도함수(Fréchet derivative)에서 비대칭성을 유발하는 1계 대류 연산자(Advection operator)의 약형식(weak form)을 도출한다.

---

### 2.1 비정규 연산자의 대수적 레지듀 사상

미분 연산자의 대수적 특성을 분석하기 위해, 복소 힐베르트 공간(complex Hilbert space) $\mathcal{H}$ 상에서 상태 함수 $\phi, \psi \in \mathcal{H}$ 에 대한 내적 $\langle \phi, \psi \rangle = \int_\Omega \phi^* \psi d\Omega$ 를 정의한다. 시스템의 전역적 자기 수반성(self-adjointness)이 성립하지 않는 경우, 임의의 연산자 $L$과 그 형식적 수반 연산자(formal adjoint operator) $L^\dagger$ 사이의 차이를 정량화하기 위해 레지듀 변환 연산자 $\mathcal{R}$을 다음과 같이 정의한다.

$$
\mathcal{R}(L) \equiv L - L^\dagger
$$

내적 공간의 약형식 전개는 다음과 같다.

$$
\langle \phi, \mathcal{R}(L) \psi \rangle \equiv \langle \phi, (L - L^\dagger) \psi \rangle = \langle \phi, L \psi \rangle - \langle \phi, L^\dagger \psi \rangle
$$

레지듀 연산자는 선형 연산자의 가산성(additivity)과 동차성(homogeneity)을 보존한다. 스칼라 계수 $\alpha, \beta \in \mathbb{R}$ 와 연산자 $A, B$ 의 선형 결합에 대하여 다음이 성립한다.

$$
\mathcal{R}(\alpha A + \beta B) = \alpha \mathcal{R}(A) + \beta \mathcal{R}(B)
$$

일반적으로 비선형 편미분 방정식의 이산화 시스템이 강한 대류 성분을 포함할 경우, 자코비안 연산자는 구조적인 비정규성(non-normality)을 띠게 된다. 비정규 연산자 시스템의 스펙트럼은 고유벡터들이 서로 직교하지 않는 찌그러진 기저(skewed basis)를 형성한다. 이로 인해 시스템의 고유값들이 모두 복소 평면의 안정 영역에 위치하여 점근적 수렴성이 보장되는 경우라 할지라도, 단기적인 뉴턴 반복 척도에서는 비직교성에 의한 섭동의 거대한 과도 성장(transient growth)이 발생하게 된다. 따라서 본 연구의 레지듀 사상은 고유값 분석만으로는 포착할 수 없는 이러한 비정규성 증폭 원인을 대수적으로 진단하는 도구로 작용한다.

---

### 2.2 프레셰 도함수 전개와 1계 대류 잔차의 대수적 분리

보존계 지배 방정식 $F(u) = D(p(u)Du) - q(u) = 0$ 의 프레셰 도함수인 자코비안 $J = \partial F / \partial u$ 를 전개한다. (단, $D$는 공간 상의 추상 미분 연산자이다.) 상태 변수 $u$에 대한 미소 섭동 $\delta u$ 에 대하여 자코비안 연산자 방정식 $J \delta u = F(u + \delta u) - F(u)$ 는 다음과 같이 도출된다.

$$
J \delta u = \underbrace{D(p(u) D\delta u)}_{L_2} + \underbrace{D \left( \frac{\partial p}{\partial u} Du \delta u \right)}_{L_1} \underbrace{- \frac{\partial q}{\partial u} \delta u}_{L_0}
$$

상태 변수 구배($Du$)와 물성 변화율($\partial p/\partial u$)의 곱을 유효 표류 속도 $v \equiv (\partial p/\partial u) (Du)$ 로 정의하면, 1계 항은 $L_1 = D(v \cdot)$ 형태의 대류 연산자로 환원된다. 자코비안 $J = L_2 + L_1 + L_0$ 에 레지듀 연산자를 분배한다.

$$
\mathcal{R}(J) = \mathcal{R}(L_2) + \mathcal{R}(L_1) + \mathcal{R}(L_0)
$$

콤팩트 지지(compact support) 검사 함수 공간 $C_c^\infty(\Omega)$에서의 부분 적분을 통해 각 항을 평가한다. 

0계 항 $L_0 = -\partial q/\partial u$ 와 2계 항 $L_2 = D(pD \cdot)$ 는 형식적 자기 수반성을 가지므로 레지듀가 소멸한다 ($\mathcal{R}(L_0) = 0, \mathcal{R}(L_2) = 0$). 따라서 자코비안의 비정규성은 1계 대류 연산자 $L_1$ 에 의존한다. 부분 적분에 의해 $L_1^\dagger = -vD$ 로 결정되므로 레지듀 사상은 다음과 같이 전개된다.

$$
\mathcal{R}(L_1)\psi = (L_1 - L_1^\dagger)\psi = D(v\psi) - (-vD\psi) = D(v\psi) + v(D\psi)
$$

라이프니츠 법칙(Leibniz rule) $D(v\psi) = (Dv)\psi + v(D\psi)$ 를 적용하여 식을 분해하면 다음과 같다.

$$
\mathcal{R}(L_1)\psi = \left[ (Dv)\psi + v(D\psi) \right] + v(D\psi) = (Dv)\psi + 2v(D\psi)
$$

이를 약형식으로 표현하면, 비선형 자코비안 행렬 내부의 대류 잔차는 다음과 같이 규명된다.

$$
\langle \phi, \mathcal{R}(J)\psi \rangle_\Omega = \langle \phi, \left[ (Dv)\psi + 2v(D\psi) \right] \rangle_\Omega
$$

이 결과는 유효 표류 속도의 발산량($Dv$)과 동질적 이류 작용($2vD$)의 결합이 시스템 비대칭성의 근원이 됨을 나타내며, 3장에서 이산 공간의 교환자 오차(commutator error)를 분석하는 기준으로 활용된다.

---
