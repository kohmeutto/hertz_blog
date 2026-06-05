+++
title = "(b) Generalized"
weight = 3
+++

---

### 1. 고유벡터의 결핍과 대수적 퇴화

임의의 선형 연산자 $\hat{A}$ 의 고유값 $\lambda$ 는 특성 방정식 $\det(\hat{A} - \lambda\hat{I}) = 0$ 을 통해 계산된다. 이 다항식의 근이 중복해서 나타나는 횟수를 대수적 중복도(Algebraic multiplicity, $\alpha$)라 한다. 

고유값이 결정되면, 이를 고유 방정식 $(\hat{A} - \lambda\hat{I})|u\rangle = 0$ 에 대입하여 고유벡터 $|u\rangle$ 를 찾는다. 이 방정식을 만족하는 선형 독립적인 벡터를 진성 고유벡터(True eigenvector)라 하며, 확보된 진성 고유벡터의 총 개수를 기하적 중복도(Geometric multiplicity, $\gamma$)라 한다.

대각화가 가능하기 위해서는 방정식의 근의 개수만큼 독립적인 벡터가 존재해야 하므로 $\alpha = \gamma$ 가 성립해야 한다. 그러나 특정 연산자 구조에서는 고유 방정식 $(\hat{A} - \lambda\hat{I})|u\rangle = 0$ 을 풀어도, 대수적 중복도 $\alpha$ 에 미치지 못하는 수의 진성 고유벡터만 산출된다. 

$$
\gamma < \alpha
$$

이러한 상태를 대수적 퇴화(Algebraic degeneracy)라 한다. 진성 고유벡터의 수가 부족하므로, 이들만으로는 전체 공간을 구성할 수 있는 완비적 기저(Complete basis) 행렬을 완성할 수 없으며 대수적인 대각화는 불가능해진다.

---

### 2. 영공간(Null Space)의 확장과 일반화된 고유벡터

결손된 차원을 복원하여 완비적 기저를 구축하기 위해, 진성 고유벡터의 탐색 조건을 대수적으로 확장한다. 진성 고유벡터는 연산자 $(\hat{A} - \lambda\hat{I})$ 를 한 번만 곱해도 영벡터가 되는 성질을 갖는다.

$$
(\hat{A} - \lambda\hat{I})^1 |u_1\rangle = 0
$$

차원을 추가로 확보하기 위해 이 조건을 완화한다. 연산자를 한 번 곱했을 때는 0이 되지 않지만, 두 번 거듭제곱해서 곱했을 때 비로소 0이 되는 새로운 독립 벡터 $|u_2\rangle$ 를 탐색한다.

$$
(\hat{A} - \lambda\hat{I})^2 |u_2\rangle = 0 \quad \text{단, } \quad (\hat{A} - \lambda\hat{I})^1 |u_2\rangle \neq 0
$$

동일한 논리로 세 번 곱해야 0이 되는 벡터 $|u_3\rangle$, 최고 차수 $k$ 번 곱해야 0이 되는 벡터 $|u_k\rangle$ 를 순차적으로 정의할 수 있다.

$$
(\hat{A} - \lambda\hat{I})^k |u_k\rangle = 0 \quad \text{단, } \quad (\hat{A} - \lambda\hat{I})^{k-1} |u_k\rangle \neq 0
$$

이러한 거듭제곱 조건을 통해 영공간을 확장하여 추가로 발굴해 낸 벡터들을 일반화된 고유벡터(Generalized eigenvector)라 정의한다. 이 과정을 통해 대수적 중복도 $\alpha$ 에 도달할 때까지 차원을 지속적으로 확장함으로써 기하학적 완비성을 강제로 복원한다.

---

### 3. 조단 사슬(Jordan Chain)과 밀어내기(Shift) 점화식

확장된 정의를 통해 구한 일반화된 고유벡터들은 공간에 무작위로 존재하는 것이 아니라, 연산자 작용을 통해 엄밀한 사슬(Chain) 형태로 연결된다. 이를 조단 사슬이라 한다.

가장 높은 차수 $k$ 에 해당하는 벡터 $|u_k\rangle$ 에 연산자 $(\hat{A} - \lambda\hat{I})$ 를 한 번 곱하는 계산을 수행한다.

$$
(\hat{A} - \lambda\hat{I}) |u_k\rangle
$$

이 결과 벡터에 연산자를 $k-1$ 번 더 곱하면 총 $k$ 번 곱한 것이 되므로 결과는 0이 된다. 정의에 따라 $k-1$ 번 곱해서 0이 되는 벡터는 그 하위 계층의 일반화된 고유벡터인 $|u_{k-1}\rangle$ 이다. 따라서 다음의 대수적 관계가 성립한다.

$$
(\hat{A} - \lambda\hat{I}) |u_k\rangle = |u_{k-1}\rangle
$$

이 원리를 모든 계층에 적용하면 다음과 같은 연쇄적인 점화식이 완성된다.

$$
(\hat{A} - \lambda\hat{I}) |u_k\rangle = |u_{k-1}\rangle
$$

$$
(\hat{A} - \lambda\hat{I}) |u_{k-1}\rangle = |u_{k-2}\rangle
$$

$$
\vdots
$$

$$
(\hat{A} - \lambda\hat{I}) |u_2\rangle = |u_1\rangle \quad (\text{진성 고유벡터})
$$

$$
(\hat{A} - \lambda\hat{I}) |u_1\rangle = 0
$$

이 점화식은 연산자 $(\hat{A} - \lambda\hat{I})$ 의 대수적 역할을 명확하게 규정한다. 이 연산자는 특정 계층의 상태 벡터를 입력받아, 사슬 구조를 타고 한 단계 아래 계층의 벡터로 변환하는 밀어내기(Shift) 작용을 수행한다. 최하단에 위치한 유일한 진성 고유벡터 $|u_1\rangle$ 은 더 이상 밀려날 하위 계층이 없으므로 영벡터로 소멸한다.

---

### 4. 조단 블록(Jordan Block)의 대수적 실체

조단 사슬을 구성하는 선형 독립적인 벡터 집합 $\{|u_1\rangle, |u_2\rangle, |u_3\rangle, \dots, |u_k\rangle\}$ 을 새로운 기저로 삼아, 전체 연산자 $\hat{A}$ 가 이 공간에서 어떠한 행렬 형태를 띠는지 전개한다. 앞서 구한 점화식 $(\hat{A} - \lambda\hat{I}) |u_j\rangle = |u_{j-1}\rangle$ 을 원래의 연산자 $\hat{A}$ 에 대해 정리한다.

$$
\hat{A} |u_1\rangle = \lambda |u_1\rangle
$$

$$
\hat{A} |u_2\rangle = \lambda |u_2\rangle + |u_1\rangle
$$

$$
\hat{A} |u_3\rangle = \lambda |u_3\rangle + |u_2\rangle
$$

이 관계를 바탕으로, 연산자 $\hat{A}$ 가 기저 행렬 $\hat{V} = [|u_1\rangle \quad |u_2\rangle \quad |u_3\rangle]$ 에 작용하는 결과를 행렬 곱셈으로 표현한다. (설명의 편의를 위해 $k=3$ 인 경우를 서술한다.)

$$
\hat{A} \begin{bmatrix} |u_1\rangle & |u_2\rangle & |u_3\rangle \end{bmatrix} = \begin{bmatrix} \lambda|u_1\rangle & \lambda|u_2\rangle + |u_1\rangle & \lambda|u_3\rangle + |u_2\rangle \end{bmatrix}
$$

우변의 행렬을 기저 벡터들의 묶음과 스칼라 계수들의 행렬 곱으로 분리한다.

$$
\begin{bmatrix} \lambda|u_1\rangle & \lambda|u_2\rangle + |u_1\rangle & \lambda|u_3\rangle + |u_2\rangle \end{bmatrix} = \begin{bmatrix} |u_1\rangle & |u_2\rangle & |u_3\rangle \end{bmatrix} \begin{bmatrix} \lambda & 1 & 0 \\ 0 & \lambda & 1 \\ 0 & 0 & \lambda \end{bmatrix}
$$

우변의 가장 오른쪽에 도출된 행렬이 조단 블록(Jordan block) $\hat{J}$ 이다.

$$
\hat{J} = \begin{bmatrix} \lambda & 1 & 0 \\ 0 & \lambda & 1 \\ 0 & 0 & \lambda \end{bmatrix}
$$

조단 블록은 진성 고유벡터가 부족하여 일반화된 고유벡터를 도입하고, 그들이 이루는 사슬 관계($|u_j\rangle$ 변환 시 $|u_{j-1}\rangle$ 이 추가로 발생함)를 행렬로 사상했을 때 주대각선에는 $\lambda$ 가, 대각선 바로 위에는 $1$ 이 배열되는 수학적 필연이다.

---

### 5. 반단순 연산자($\hat{S}$)와 멱영 연산자($\hat{N}$)의 구조적 분리 (던포드 분해)

도출된 조단 블록 행렬이 두 가지 독립적인 거동의 합으로 구성되어 있음을 대수적으로 분해하여 확인한다.

$$
\hat{J} = \begin{bmatrix} \lambda & 0 & 0 \\ 0 & \lambda & 0 \\ 0 & 0 & \lambda \end{bmatrix} + \begin{bmatrix} 0 & 1 & 0 \\ 0 & 0 & 1 \\ 0 & 0 & 0 \end{bmatrix}
$$

기저 변환 행렬 $\hat{V}$ 를 통해 이 국소적 분해를 전체 상태 공간으로 환원하면, 연산자 $\hat{A}$ 는 대각화 가능한 성분과 본질적으로 대각화 불가능한 성분의 합으로 분리된다.

$$
\hat{A} = \hat{S} + \hat{N}
$$

**1) 반단순 연산자 성분 ($\hat{S}$)**

반단순 연산자의 대수적 본질은 특정 임의 기저에서 관찰되는 원소의 시각적 위치에 매몰되지 않는다. 이는 적절한 고유 기저 변환을 거쳤을 때 비대각 원소들이 모두 소멸하며 오직 주대각선 성분만으로 완전히 환원될 수 있는 **대각화 가능(Diagonalizable)** 성분을 의미한다. 대각화 가능한 연산자일지라도 표준 기저와 같은 임의의 관찰 축에서는 비대각 위치에 원소가 조밀하게 나타날 수 있으며, 이는 단지 기저축과 고유축의 어긋남에서 기인하는 기하학적 투영 효과일 뿐 시스템 고유의 구조적 결함이 아니다. 브라켓(Bra-ket) 표기법으로 표현하면 입력과 출력의 인덱스가 동일한 구조의 사영 연산자 결합으로 정의된다.

$$
\hat{S} = \sum_m \lambda_m \sum_p \sum_{j=0}^{k_p-1} |u_{m, p, j}\rangle \langle u^{d, m, p, j}|
$$

**2) 멱영 연산자 성분 ($\hat{N}$)**

멱영 연산자의 대수적 본질은 공간 상에서 어떠한 기저 변환 행렬을 도입하여 좌표계를 비틀고 회전시키더라도 주대각선 내부로 절대 흡수되거나 소멸하지 않는 **본질적 비대각(Intrinsically off-diagonal)** 성분이라는 점에 있다. 이는 단순히 기저의 선택에 따른 착시가 아니라 시스템의 비정규성이 임계에 달해 발생하는 기하학적 왜곡(Shear)의 실체이다. 조단 기저 상에서는 주대각선이 0이고 바로 위쪽 대각선에만 1이 남는 순수 상삼각 행렬의 형태를 취하며, 상태 벡터를 조단 사슬의 한 단계 아래로 밀어내는 전이(Shift) 작용만을 완벽하게 분리해 낸 결과물이다. 브라켓 표기법으로는 입력 인덱스 $j$ 가 출력 인덱스 $j-1$ 로 전이되는 엇갈린 외적 형태로 정의된다.

$$
\hat{N} = \sum_m \sum_p \sum_{j=1}^{k_p-1} |u_{m, p, j-1}\rangle \langle u^{d, m, p, j}|
$$

이 밀어내기 성분은 거듭제곱에 따라 비대각 원소들이 순차적으로 밀려나며 최종적으로 영작용소로 붕괴하는 대수적 불변성 공식 $\hat{N}^k = 0$ 을 충족하며, 시스템 내부의 구조적 결합 상태를 지시한다.

던포드 분해($\hat{A} = \hat{S} + \hat{N}$) 체계는 기저의 왜곡이나 투영 효과를 완전히 배제하고, 시스템 고유의 대각화 가능한 대수적 뼈대($\hat{S}$)와 어떤 좌표계에서도 제거할 수 없는 본질적인 기하학적 결함 사슬($\hat{N}$)을 엄밀하게 가르는 보편적 분해 이론으로 완결된다.