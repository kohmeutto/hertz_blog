+++
title = "(b) Theory 2"
weight = 10
+++

---

### 1. Derivation of Global Conservation Identities

앞에서 언급된 바와 같이, 임의의 선형 연산자 $\hat{L}$에 대하여, 시스템의 경계 비대칭성을 추출하는 **레지듀 변환 $\mathcal{R}$** 은 힐베르트 공간 내에서 다음과 같이 정의된다. 이 정의는 모든 유도 과정의 출발점이자, 시스템의 '객관적 실재'와 '예측' 사이의 간극을 규정하는 공리이다.

$$
\langle \phi \mid \mathcal{R}\hat{L} \mid \psi \rangle \equiv \langle \phi \mid \hat{L} \psi \rangle - \langle \hat{L}^\dagger \phi \mid \psi \rangle
$$

**1) Operator Conservation Law**

아래 식은 연산자의 비정규성(Non-normality)이 상태 함수의 노름 변화와 경계 플럭스에 의해 어떻게 결정되는지 보여준다.

$$
\langle \psi \mid [\hat{L}^\dagger, \hat{L}] \mid \psi \rangle = \left( \|\hat{L}\psi\|^2 - \|\hat{L}^\dagger \psi\|^2 \right) + \langle \psi \mid \mathcal{R}_W(\hat{L}^\dagger, \hat{L}) \mid \psi \rangle
$$

$$
\mathcal{R}_\mathcal{W} = \begin{vmatrix} \mathcal{R}\hat{L}^\dagger & \mathcal{R}\hat{L} \\ \hat{L}^\dagger & \hat{L} \end{vmatrix}
$$

proof)

교환자 기댓값의 전개상태 $|\psi\rangle$에 대한 교환자 $[\hat{L}^\dagger, \hat{L}]$의 기댓값을 구한다. 순수 수학적 정의이지만 직관적으로 이해하기 위해, "소자의 공간이 뒤틀린 것($[\hat{L}^\dagger, \hat{L}]$)이라면, 그 길을 지나가던 전자($|\psi\rangle$)가 겪은 변화의 기댓값이다." 라고 비유적으로 해석할 수 있다. 

$$
\langle \psi \mid [\hat{L}^\dagger, \hat{L}] \mid \psi \rangle = \langle \psi \mid \hat{L}^\dagger \hat{L} \mid \psi \rangle - \langle \psi \mid \hat{L} \hat{L}^\dagger \mid \psi \rangle
$$

레지듀 정의의 적용첫 번째 항 $\langle \psi \mid \hat{L}^\dagger (\hat{L}\psi) \rangle$에 대해, $\hat{L}^\dagger$를 브라 쪽으로 넘기기 위해 레지듀 정의를 적용한다.

$$
\langle \psi \mid \hat{L}^\dagger (\hat{L}\psi) \rangle = \langle \hat{L}\psi \mid \hat{L}\psi \rangle + \langle \psi \mid \mathcal{R}\hat{L}^\dagger \mid \hat{L}\psi \rangle = \|\hat{L}\psi\|^2 + \langle \psi \mid \mathcal{R}\hat{L}^\dagger \mid \hat{L}\psi \rangle
$$

$$
\langle \psi \mid \hat{L} (\hat{L}^\dagger \psi) \rangle = \langle \hat{L}^\dagger \psi \mid \hat{L}^\dagger \psi \rangle + \langle \psi \mid \mathcal{R}\hat{L} \mid \hat{L}^\dagger \psi \rangle = \|\hat{L}^\dagger \psi\|^2 + \langle \psi \mid \mathcal{R}\hat{L} \mid \hat{L}^\dagger \psi \rangle
$$

두 항을 결합한다.

$$
\langle \psi \mid [\hat{L}^\dagger, \hat{L}] \mid \psi \rangle = \left( \|\hat{L}\psi\|^2 - \|\hat{L}^\dagger \psi\|^2 \right) + \underbrace{\langle \psi \mid \mathcal{R}\hat{L}^\dagger \mid \hat{L}\psi \rangle - \langle \psi \mid \mathcal{R}\hat{L} \mid \hat{L}^\dagger \psi \rangle}_{\text{Residue Wronskian}}
$$

여기서 **레지듀 론스키안(Residue Wronskian) $\mathcal{R}_\mathcal{W}$** 를 다음과 같이 정의함으로써 첫 번째 최종 식을 얻는다.

$$
\mathcal{R}_\mathcal{W} = \begin{vmatrix} \mathcal{R}\hat{L}^\dagger & \mathcal{R}\hat{L} \\ \hat{L}^\dagger & \hat{L} \end{vmatrix}$$

$$
\langle \psi \mid [\hat{L}^\dagger, \hat{L}] \mid \psi \rangle = \left( \|\hat{L}\psi\|^2 - \|\hat{L}^\dagger \psi\|^2 \right) + \langle \psi \mid \mathcal{R}_W(\hat{L}^\dagger, \hat{L}) \mid \psi \rangle
$$

**2) Bulk-Boundary Dissipation Theorem**

아래 식은 하이젠베르크 운동 방정식에 기반하여 시스템의 에너지 변화(소산)를 정량화한다. 즉, 시스템 내부의 저항적 변화량(Internal Friction)은 벌크 영역의 에너지 비대칭성과 경계면에서의 유출입량의 합으로 결정된다.

$$
\underbrace{\langle \psi \mid [\hat{H}, \hat{A}] \mid \psi \rangle}_{\text{Internal Friction}} = \frac{1}{2} \underbrace{\left( \|\hat{L}\psi\|^2 - \|\hat{L}^\dagger \psi\|^2 \right)}_{\text{Net Energy Gap}} + \underbrace{\langle \psi \mid \mathcal{R}_W (\hat{H}, \hat{A}) \mid \psi \rangle}_{\text{Residue Wronskian}}
$$

proof)

해밀토니안 소산 구조를 설정한다. 임의의 연산자 $\hat{L}$ 에 대하여, 허미션 파트 $\hat{H}$ 와 반-허미션 파트 $\hat{A}$ 는 다음과 같이 정의된다.

$$\hat{L} = \hat{H} + \hat{A}$$
$$\hat{L}^\dagger = \hat{H} - \hat{A} \quad (\text{단, } \hat{H}^\dagger = \hat{H}, \hat{A}^\dagger = -\hat{A})$$

교환자의 내적 전개 (Expansion of Commutator)를 한다. 에너지로 비유를 하면, 순간 내부 마찰에 의해 에너지가 열로 전환되고 있는 소산율(Dissipation Rate)의 기댓값을 의미한다. 예시가 아닌 식 자체로의 본질적인 해석은 시스템의 동역학적 불일치를 보여주는 핵심 지표이다.
 
$$
\langle \psi \mid [\hat{H}, \hat{A}] \mid \psi \rangle = \langle \psi \mid \hat{H}\hat{A} \mid \psi \rangle - \langle \psi \mid \hat{A}\hat{H} \mid \psi \rangle
$$
  
여기서 우리가 이전에 정의한 **레지듀 변환($\mathcal{R}$)** 을 사용한다. 연산자를 브라(Bra) 쪽으로 넘길 때 발생하는 경계 오차를 보정해주는 규칙이다.

$$
\langle \psi \mid \hat{H}(\hat{A}\psi) \rangle = \langle \hat{H}^\dagger \psi \mid \hat{A}\psi \rangle + \langle \psi \mid \mathcal{R}\hat{H} \mid \hat{A}\psi \rangle$$

$$\langle \psi \mid \hat{A}(\hat{H}\psi) \rangle = \langle \hat{A}^\dagger \psi \mid \hat{H}\psi \rangle + \langle \psi \mid \mathcal{R}\hat{A} \mid \hat{H}\psi \rangle$$

두 식을 빼면 다음과 같다.

$$
\langle \psi \mid [\hat{H}, \hat{A}] \mid \psi \rangle = \left( \langle \hat{H} \psi \mid \hat{A} \psi \rangle + \langle \hat{A} \psi \mid \hat{H} \psi \rangle \right) + \left( \langle \psi \mid \mathcal{R} \hat{H} (\hat{A}\psi) \rangle - \langle \psi \mid \mathcal{R} \hat{A} (\hat{H}\psi) \rangle \right)
$$

위 식에서 첫번째 괄호는 복소 내적의 성질을 이용해 다음과 같이 변환된다.

$$
\langle \hat{H} \psi \mid \hat{A} \psi \rangle + \langle \hat{A} \psi \mid \hat{H} \psi \rangle = 2 \text{Re} \langle \hat{H} \psi \mid \hat{A} \psi \rangle
$$

여기서 $\hat{L} = \hat{H} + \hat{A}$ 와 $\hat{L}^\dagger = \hat{H} - \hat{A}$ 의 노름(Norm) 차이를 계산해 본다.

$$
\|\hat{L}\psi\|^2 = \|\hat{H}\psi + \hat{A}\psi\|^2 = \|\hat{H}\psi\|^2 + \|\hat{A}\psi\|^2 + 2 \text{Re} \langle \hat{H} \psi \mid \hat{A} \psi \rangle
$$

$$\|\hat{L}^\dagger\psi\|^2 = \|\hat{H}\psi - \hat{A}\psi\|^2 = \|\hat{H}\psi\|^2 + \|\hat{A}\psi\|^2 - 2 \text{Re} \langle \hat{H} \psi \mid \hat{A} \psi \rangle
$$

따라서, 두 노름의 차이는 다음과 같이 정의된다.

$$
\frac{1}{2} \left( \|\hat{L}\psi\|^2 - \|\hat{L}^\dagger \psi\|^2 \right) = 2 \text{Re} \langle \hat{H} \psi \mid \hat{A} \psi \rangle
$$

이것이 바로 시스템의 벌크 영역에서 발생하는 Net Energy Gap (순수 에너지 불균형) 항이다. 유도 과정에서 남은 경계 보정 항들을 묶어 레지듀 론스키안 $\mathcal{R}_W$로 정의한다.

$$
\langle \psi \mid \mathcal{R}_W (\hat{H}, \hat{A}) \mid \psi \rangle = \langle \psi \mid \mathcal{R}\hat{H} \mid \hat{A} \psi \rangle - \langle \psi \mid \mathcal{R}\hat{A} \mid \hat{H} \psi \rangle
$$

이 항은 연산자의 비가환성(Non-commutativity)이 경계면(Boundary)에서 어떻게 소산으로 나타나는지를 수학적으로 포착한다. 위의 과정들을 병합하면 최종 정리 형태가 도출된다.

$$
\langle \psi \mid [\hat{H}, \hat{A}] \mid \psi \rangle = \frac{1}{2} \left( \|\hat{L}\psi\|^2 - \|\hat{L}^\dagger \psi\|^2 \right) + \langle \psi \mid \mathcal{R}_W (\hat{H}, \hat{A}) \mid \psi \rangle
$$

**3) 레지듀 론스키안의 물리적 의미**

레지듀 론스키안은 단순한 수학적 잔여항이 아니라, 시스템의 **실재(Reality)** 와 이를 수용하는 경계의 관측(Observation) 사이의 위상적 불일치를 정량화하는 지표이다. 이를 **'위상적 틀어짐(Topological Skewness)'** 의 관점에서 기술한다.

(1) 열벡터 구조와 위상 공간의 축 정의

레지듀 론스키안 행렬 $\mathcal{R}_\mathcal{W}$를 구성하는 두 열벡터는 시스템을 기술하는 두 개의 독립적인 위상 축(Basis)으로 해석된다.

$$
\mathcal{R}_\mathcal{W} = \begin{vmatrix} \mathbf{v}_1 & \mathbf{v}_2 \end{vmatrix} = \begin{vmatrix} \mathcal{R}\hat{L}^\dagger & \mathcal{R}\hat{L} \\ \hat{L}^\dagger & \hat{L} \end{vmatrix}
$$

- 제1열 ($\mathbf{v}_1$, 관측 축): 전극(Contact)이 전자를 받아들이기 위해 설정한 **수용 조건(Lens Profile)** 이다. 이는 시스템이 외부와 소통하는 관측의 기준선을 의미한다.
- 제2열 ($\mathbf{v}_2$, 실재 축): 채널(Channel) 내부에서 전자가 실제로 보여주는 **물리적 거동(Object Profile)** 이다. 이는 관측자와 무관하게 존재하는 시스템의 실재를 의미한다.

(2) 행렬식(Determinant)과 에너지 소산의 메커니즘

행렬식 $\mathcal{R}_\mathcal{W}$은 두 위상 축이 이루는 평행사변형의 면적을 의미하며, 이는 곧 '관측'과 '실재'가 경계면에서 얼마나 어긋나 있는지를 나타내는 **'위상적 마찰 계수'** 가 된다.

- 정합 상태 ($\text{det} \approx 0$): 관측 축과 실재 축이 평행하거나 직교성을 유지하여, 전자가 자신의 파동 형태를 바꾸지 않고 전극으로 부드럽게 전이되는 상태이다.
- 뒤틀림 상태 ($\text{det} \neq 0$): 두 축 사이의 각도가 좁아지며 위상 공간이 찌그러지는 상태이다. 전자는 전극의 수용 조건에 맞추기 위해 자신의 양자 상태를 억지로 변형시켜야 하며, 이 과정에서 발생하는 **'수학적 불일치의 총량'** 이 물리적인 **에너지 소산(Dissipation)** 으로 치환된다.