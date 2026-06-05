+++
title = "(b) Generalization"
weight = 1
+++

---

### 1. 고유벡터의 결핍과 대수적 퇴화

임의의 선형 연산자 $\hat{A}$의 고윳값 $\lambda$는 특성 방정식 $\det(\hat{A} - \lambda\hat{I}) = 0$을 통해 산출된다. 이 다항식의 근이 중복해서 나타나는 횟수를 대수적 중복도(Algebraic multiplicity, $\alpha$)라 한다. 

고윳값이 결정되면, 이를 고유 방정식 $(\hat{A} - \lambda\hat{I})|\lambda\rangle = 0$에 대입하여 고유벡터 $|\lambda\rangle$를 찾는다. 이 방정식을 만족하는 선형 독립적인 벡터를 진성 고유벡터(True eigenvector)라 하며, 확보된 진성 고유벡터의 총 개수를 기하적 중복도(Geometric multiplicity, $\gamma$)라 한다.

대각화가 가능하기 위해서는 방정식의 근의 개수만큼 독립적인 기저 벡터가 존재해야 하므로 $\alpha = \gamma$가 성립해야 한다. 그러나 특정 연산자 구조에서는 고유 방정식을 풀어도 대수적 중복도 $\alpha$에 미치지 못하는 수의 진성 고유벡터만 산출된다. 

$$
\gamma < \alpha
$$

이러한 상태를 연산자의 대수적 퇴화(Algebraic degeneracy)라 한다. 진성 고유벡터의 수가 부족하므로 이들만으로는 전체 공간을 구성할 수 있는 완비적 기저(Complete basis) 행렬을 완성할 수 없으며 대수적인 대각화는 불가능해진다.

---

### 2. 일반화된 고유벡터 (Generalized eigenvector)

대각화가 불가능한 연산자를 해석하기 위해, 진성 고유벡터의 개념을 일반화된 고유벡터(Generalized eigenvector)로 확장하여 부족한 기저 공간을 보완한다. 

**1) 이산 공간 (유한 차원)**

하나의 고윳값 $\lambda_m$에 종속된 상태들은 고윳값 기호가 아닌 조르당 사슬(Jordan chain) 내부의 랭크 인덱스 $k$를 통해 $|\lambda_{m,k}\rangle$로 명확히 구분된다. 결함 연산자 계의 지배 방정식은 랭크 인덱스 강하를 동반하여 다음과 같이 기술된다.

$$
\hat{A}|\lambda_{m,k}\rangle = \lambda_m|\lambda_{m,k}\rangle + |\lambda_{m,k-1}\rangle \quad (\text{단, } |\lambda_{m,0}\rangle = 0)
$$
$$
\hat{A}|\lambda_{m,1}\rangle = \lambda_m|\lambda_{m,1}\rangle \quad (\text{진성 고유벡터})
$$

**2) 연속 공간 (무한 차원)**

비유계 연산자의 연속 스펙트럼에서는 이산적인 랭크 강하 대신, 고윳값 구간 전체에 걸쳐 기하학적 중복도가 결핍되는 현상이 분포 함수의 형태로 발현된다. 단, 이러한 결핍(잉여 상태)은 자기수반이 아닌 결함계에서만 나타나며, 자기수반 연산자의 경우에는 $|w(\nu)\rangle = 0$이 되어 잉여 항이 소멸한다.

비자기수반 결함계에 한하여, 연속 변수 $\nu$에 종속된 일반화된 고유벡터의 지배 방정식은 국소적 잉여 상태(Surplus state) 밀도 $|w(\nu)\rangle$를 수반하여 다음과 같이 기술된다.

$$
\hat{A}|\lambda(\nu)\rangle = \lambda(\nu)|\lambda(\nu)\rangle + |w(\nu)\rangle \quad (\text{자기수반계의 경우 } |w(\nu)\rangle = 0)
$$

proof)

*(1) 대각화 가능한 경우 예 (이산)*

대각화 가능한 연산자 $\hat{A}$가 서로 다른 고윳값 $\lambda_1, \lambda_2$와 이에 대응하는 진성 고유벡터 $|\lambda_{1,1}\rangle, |\lambda_{2,1}\rangle$을 가지는 경우 다음과 같이 기술된다.

$$
\hat{A}|\lambda_{1,1}\rangle = \lambda_1|\lambda_{1,1}\rangle \implies (\hat{A}-\lambda_1 \hat{I})|\lambda_{1,1}\rangle=0
$$
$$
\hat{A}|\lambda_{2,1}\rangle = \lambda_2|\lambda_{2,1}\rangle \implies (\hat{A}-\lambda_2 \hat{I})|\lambda_{2,1}\rangle=0
$$

*(2) 대각화가 불가능한 경우 (이산)*

대수적 중복도가 2이고 기하학적 중복도가 1인 특정 고윳값 $\lambda_1$에 대한 연산자는 다음과 같이 기술된다.

$$
(\hat{A}-\lambda_1\hat{I})^2|\lambda_{1,2}\rangle=0
$$

*(3) 쉬운 예: 고유벡터의 확장*

이때 고유벡터는 1개만 존재하므로 대각화가 불가능하다. 방정식의 차수를 분리하여 잉여 기저를 확보한다.

$$
(\hat{A}-\lambda_1\hat{I})^2|\lambda_{1,2}\rangle=0 \implies (\hat{A}-\lambda_1\hat{I})\{(\hat{A}-\lambda_1\hat{I})|\lambda_{1,2}\rangle\}=0
$$

여기에서 아래와 같이 정의하면 재귀적 구조가 형성된다.

$$
|\lambda_{1,1}\rangle = (\hat{A}-\lambda_1\hat{I})|\lambda_{1,2}\rangle \implies (\hat{A}-\lambda_1\hat{I})|\lambda_{1,1}\rangle=0
$$

여기서의 $|\lambda_{1,2}\rangle$는 확장된 고유벡터이다. 직관적 의미를 위해 연산자 $\hat{A}$에 대해 정리한다.

$$
\hat{A}|\lambda_{1,2}\rangle = \lambda_1|\lambda_{1,2}\rangle + |\lambda_{1,1}\rangle
$$

위 식은 다음과 같은 의미를 가진다.
- $|\lambda_{1,1}\rangle$과 $|\lambda_{1,2}\rangle$는 공통된 고윳값 $\lambda_1$을 가진다.
- 랭크 2의 고유벡터 $|\lambda_{1,2}\rangle$는 랭크 1의 고유벡터 $|\lambda_{1,1}\rangle$ 상태를 추가로 유발한다.

*(4) 좀 더 복잡한 예: 고유벡터의 확장*

특성 방정식의 대수적 중복도가 3인 경우를 전개한다.

$$
(\hat{A}-\lambda_1\hat{I})^3|\lambda_{1,3}\rangle=0
$$

조르당 사슬을 구축하기 위해 결합 법칙으로 상태를 분해한다.

$$
(\hat{A}-\lambda_1\hat{I}) \left\{ \underbrace{ (\hat{A}-\lambda_1\hat{I}) \underbrace{ (\hat{A}-\lambda_1\hat{I})|\lambda_{1,3}\rangle }_{ |\lambda_{1,2}\rangle } }_{ |\lambda_{1,1}\rangle } \right\} = 0
$$

이에 따라 랭크가 구분된 3개의 기저가 생성되며, 연산자 거동은 다음과 같이 일반화된다.

$$
\hat{A}|\lambda_{1,3}\rangle = \lambda_1|\lambda_{1,3}\rangle + |\lambda_{1,2}\rangle
$$
$$
\hat{A}|\lambda_{1,2}\rangle = \lambda_1|\lambda_{1,2}\rangle + |\lambda_{1,1}\rangle
$$
$$
\hat{A}|\lambda_{1,1}\rangle = \lambda_1|\lambda_{1,1}\rangle
$$

*(5) 고유벡터의 일반화*

임의의 멱영 지수 $k_m$에 대하여 $(\hat{A}-\lambda_m\hat{I})^{k_m}|\lambda_{m,k_m}\rangle=0$을 만족하는 일반화된 고유벡터는 랭크 인덱스 강하를 통해 다음과 같이 규정된다.

$$
\hat{A}|\lambda_{m,k}\rangle = \lambda_m|\lambda_{m,k}\rangle + |\lambda_{m,k-1}\rangle \quad (\text{단, } 1 \le k \le k_m)
$$

---

### 3. 일반화된 연산자 분해

결함 연산자의 기저는 스스로 직교하지 않으므로, 대수적 연산자 분해를 성립시키기 위해 상호 쌍대 기저(Bi-dual basis)를 도입한다. 

**1) 이산 공간의 분해**

이산 공간에서는 직교 규격화 조건($\langle \lambda^{m,j}|\lambda_{n,k}\rangle = \delta^m_n \delta^j_k$)을 만족하도록 인덱스를 윗첨자(반변, Contravariant)로 올려 $\langle \lambda^{m,k}|$로 표기한다.

$$
\hat{A}\hat{P}_m = \lambda_m\hat{P}_m + \hat{N}_m\iff
\hat{A} = \sum_m (\lambda_m\hat{P}_m + \hat{N}_m)
$$

- 사영 연산자(Projection): $\hat{P}_m = \sum_{k=1}^{k_m} |\lambda_{m,k}\rangle\langle \lambda^{m,k}|$
- 멱영 연산자(Nilpotent): $\hat{N}_m = \sum_{k=2}^{k_m} |\lambda_{m,k-1}\rangle\langle \lambda^{m,k}|$

**2) 연속 공간의 분해**

연속 공간에서는 상태가 미소 구간 단위로 투영되므로, 델타 함수 직교 규격화 조건($\langle \lambda^d(\nu')|\lambda(\nu)\rangle = \delta(\nu-\nu')$)을 만족하는 연속 쌍대 기저 $\langle \lambda^d(\nu)|$를 도입하여 측도(Measure)를 포함하는 밀도(Density)의 형태로 분해한다.

$$
\hat{A}\,d\hat{P}(\nu) = \lambda(\nu)\, d\hat{P}(\nu) + d\hat{N}(\nu)\iff
\hat{A} = \int_\nu \big[\lambda(\nu)\, d\hat{P}(\nu) + d\hat{N}(\nu)\big]
$$

- 사영 밀도(Projection density): $d\hat{P}(\nu) = d\nu\,|\lambda(\nu)\rangle\langle \lambda^d(\nu)|$
- 멱영 밀도(Nilpotent density): $d\hat{N}(\nu) = d\nu\,|w(\nu)\rangle\langle \lambda^d(\nu)|$

*proof1) 직접 방법*

조르당 사슬 내 특정 랭크 $k$의 지배 방정식 양변 우측에 해당 랭크의 쌍대 기저 $\langle \lambda^{m,k}|$를 외적(Outer product)한다.

$$
\hat{A}|\lambda_{m,k}\rangle\langle \lambda^{m,k}| = \lambda_m|\lambda_{m,k}\rangle\langle \lambda^{m,k}| + |\lambda_{m,k-1}\rangle\langle \lambda^{m,k}|
$$

해당 고윳값 공간 $\lambda_m$에 속하는 전체 랭크 $k$에 대하여 합산($\sum_{k=1}^{k_m}$)을 수행한다.

$$
\sum_{k=1}^{k_m} \hat{A}|\lambda_{m,k}\rangle\langle \lambda^{m,k}| = \lambda_m \sum_{k=1}^{k_m} |\lambda_{m,k}\rangle\langle \lambda^{m,k}| + \sum_{k=2}^{k_m} |\lambda_{m,k-1}\rangle\langle \lambda^{m,k}|
$$

여기서 특정 고윳값 공간 내의 기저들을 모두 합산한 $\sum_{k=1}^{k_m} |\lambda_{m,k}\rangle\langle \lambda^{m,k}|$는 해당 공간으로 투영하는 국소적 항등원(Resolution of identity within the local block)을 형성하므로 사영 연산자 $\hat{P}_m$을 구성한다.

따라서, 분해 항등식 $\hat{A}\hat{P}_m = \lambda_m\hat{P}_m + \hat{N}_m$이 성립한다.

*proof2) 테일러 급수 이용*

해석 함수 $f$를 점 $\lambda_m$ 둘레에서 테일러 전개한 뒤, 변수 $x$ 자리에 연산자 $\hat{A}$를 대입한다. 이때 변위 항 $(x-\lambda_m)$은 $(\hat{A}-\lambda_m\hat{I})$로 치환된다.

$$
f(x)=\sum_{k=0}^{\infty} \frac{f^{(k)}(\lambda_m)}{k!}(x-\lambda_m)^k \implies
f(\hat{A})=\sum_{k=0}^{\infty} \frac{f^{(k)}(\lambda_m)}{k!}(\hat{A}-\lambda_m\hat{I})^k
$$

여기에 사영 연산자 $\hat{P}_m$ 를 곱한다.

$$
f(\hat{A})\hat{P}_m=\sum_{k=0}^{\infty} \frac{f^{(k)}(\lambda_m)}{k!}(\hat{A}-\lambda_m\hat{I})^k\hat{P}_m
$$

분해 항등식 $\hat{A}\hat{P}_m-\lambda_m\hat{P}_m=\hat{N}_m$, 즉 $(\hat{A}-\lambda_m\hat{I})\hat{P}_m=\hat{N}_m$을 거듭제곱하면 $(\hat{A}-\lambda_m\hat{I})^k\hat{P}_m=\hat{N}_m^k$이 성립한다. 이를 대입한다.

$$
f(\hat{A})\hat{P}_m=\sum_{k=0}^{\infty} \frac{f^{(k)}(\lambda_m)}{k!}\hat{N}^k_m \quad (\hat{N}_m^0 := \hat{P}_m)
$$

$f(\hat{A})=\hat{A}$가 되려면 $f(x)=x$ 이므로, 도함수는 다음과 같다.

$$
f^{(0)}(\lambda_m)=\lambda_m, \quad f^{(1)}(\lambda_m)=1, \quad f^{(k \ge 2)}(\lambda_m)=0
$$

$k=0$ 항과 $k=1$ 항만 남으며, $\hat{N}_m^0=\hat{P}_m$ 규약에 의해 정리하면 다음과 같다.

$$
f(\hat{A})\hat{P}_m=\hat{A}\hat{P}_m=\lambda_m\hat{P}_m+\hat{N}_m
$$

*proof3) Nilpotent*

[이산 공간]

분리된 비대각 성분 $\hat{N}_m = \sum_{k=2}^{k_m} |\lambda_{m,k-1}\rangle\langle \lambda^{m,k}|$이 멱영(Nilpotent) 연산자가 되는 대수학적 인과율은 쌍대 기저의 직교성에 의해 증명된다. 단일 랭크 강하 항의 곱을 연산하면 다음과 같다.

$$
(|\lambda_{m,k-1}\rangle\langle \lambda^{m,k}|) (|\lambda_{m,j-1}\rangle\langle \lambda^{m,j}|) = |\lambda_{m,k-1}\rangle \langle \lambda^{m,k}|\lambda_{m,j-1}\rangle \langle \lambda^{m,j}|
$$

랭크가 어긋나는 상태들의 내적은 상호 쌍대 기저의 직교 규격화 조건에 의해 소멸한다 ($\langle \lambda^{m,k}|\lambda_{m,j-1}\rangle = \delta^k_{j-1}$). 스칼라 항의 대수적 조건에 따라 랭크가 일치하지 않는 모든 교차 항들이 제거되므로, 비대각 전이 연산자는 유한 번의 거듭제곱 내에서 즉각 영연산자 $\hat{0}$으로 붕괴한다.

[연속 공간]

연속 공간의 특정 상태 $\nu$에 대한 지배 방정식 양변 우측에 쌍대 기저 $\langle \lambda^d(\nu)|$를 외적하고 미소 구간 측도 $d\nu$를 취한다.

$$
\hat{A}\, d\nu\,|\lambda(\nu)\rangle\langle \lambda^d(\nu)| = \lambda(\nu)\, d\nu\,|\lambda(\nu)\rangle\langle \lambda^d(\nu)| + d\nu\,|w(\nu)\rangle\langle \lambda^d(\nu)|
$$

이를 각 밀도 기호로 치환하면 국소 구간에 대한 연산자 항등식 $\hat{A}\,d\hat{P}(\nu) = \lambda(\nu)\, d\hat{P}(\nu) + d\hat{N}(\nu)$가 도출된다. 연속 공간의 비대각 성분 밀도 $d\hat{N}(\nu)$가 멱영 특성을 가지는 인과율은 다음과 같이 전개된다.

$$
(d\nu\,|w(\nu)\rangle\langle \lambda^d(\nu)|) (d\nu'\,|w(\nu')\rangle\langle \lambda^d(\nu')|) = d\nu\,d\nu'\,|w(\nu)\rangle \langle \lambda^d(\nu)|w(\nu')\rangle \langle \lambda^d(\nu')|
$$

잉여 상태 $|w(\nu')\rangle$는 진성 고유공간과 대수적으로 선형 독립인 결함 공간을 구성하므로, 진성 상태를 투영하는 쌍대 기저 $\langle \lambda^d(\nu)|$와의 내적은 항상 0으로 소멸한다.

$$
\langle \lambda^d(\nu)|w(\nu')\rangle = 0
$$

이 스칼라 항이 교차 곱 과정에서 즉시 0이 되므로, 연속 공간의 비대각 전이 밀도는 자체적인 곱 연산에서 단번에 영연산자로 소멸한다.

$$
(d\hat{N})^2 = \hat{0}
$$

---