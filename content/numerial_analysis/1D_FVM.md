+++
title = "(b) 1D FVM"
weight = 2
+++

---
### 1. 기본 연산자

**1) 두 종류의 기저 공간**

1차원 격자에는 두 종류의 영토가 존재한다.

- 노드 기저 ($|i\rangle$): 전위($u$)나 물성($p$)이 살고 있는 곳이다. (Primal Grid)

$$
\langle i | j \rangle = \delta_{ij}
$$

- 에지 기저 ($|i+1/2\rangle$): 기울기($\nabla u$)나 유량($F$)이 살고 있는 **이웃 간의 통로** 이다. (Dual/Edge Grid)

$$
\langle i+1/2 | j+1/2 \rangle = \delta_{ij}
$$

**2) 차분 연산자 $\hat{D}$의 대수적 정의**

차분 연산자 $\hat{D}$는 노드 기저를 받아서 에지 기저로 뱉어내는 연산자이다. 이 연산자를 외적(Outer product) 형식으로 엄밀하게 쓰면 다음과 같다.

$$
\hat{D} = \sum_{j=1}^{N-1} \frac{1}{h_j} \left( |j+1/2\rangle \langle j+1| - |j+1/2\rangle \langle j| \right)
$$

상태 벡터 $|u\rangle = \sum_k u_k |k\rangle$라고 할 때,

$$
\langle i+1/2 | \hat{D} | u \rangle = \langle i+1/2 | \left[ \sum_j \frac{1}{h_j} \left( |j+1/2\rangle \langle j+1| - |j+1/2\rangle \langle j| \right) \right] | u \rangle
$$

에지 기저의 직교성($\langle i+1/2 | j+1/2 \rangle = \delta_{ij}$)에 의해 $j=i$인 항만 살아남는다.

$$
g_{e,E} 
= \frac{1}{h_i} \left( \langle i+1 | u \rangle - \langle i | u \rangle \right)
= \frac{u_{i+1} - u_i}{h_i}
$$

이번엔 좌측 엣지 성분을 구해보자.

$$
\langle i-1/2 | \hat{D} | u \rangle = \langle i-1/2 | \left[ \sum_j \frac{1}{h_j} \left( |j+1/2\rangle \langle j+1| - |j+1/2\rangle \langle j| \right) \right] | u \rangle
$$

$$
g_{e,W} 
= \frac{1}{h_{i-1}} \left( \langle i | u \rangle - \langle i-1 | u \rangle \right)
= \frac{u_{i} - u_{i-1}}{h_{i-1}}
$$

**3) 매핑 연산자 $\hat{M}$**

유량($J$)은 노드 사이의 통로(Edge)에서 정의되는데, 물성($p$)은 노드에만 살고 있다. 따라서 물성을 에지로 옮겨주는 매핑 연산자 $\hat{M}$이 필요하다.

$$
\hat{M} = \sum_{j} | j+1/2 \rangle \frac{\langle j | + \langle j+1 |}{2}
$$

마찬가지로 물성 $|p\rangle$에 대해, 아래와 같이 쓸 수 있다.

$$
p_{e,E}
= \langle i+1/2 | \hat{M} | p \rangle
= 0.5(\langle i | p \rangle + \langle i+1 | p \rangle)
= 0.5(p_i+p_{i+1})
$$

$$
p_{e,W}
= \langle i-1/2 | \hat{M} | p \rangle
= 0.5(\langle i-1 | p \rangle + \langle i | p \rangle)
= 0.5(p_{i-1}+p_{i})
$$

$$
dp_{e,E}
= \langle i+1/2 | \hat{M} | dp \rangle
= 0.5(\langle i | dp \rangle + \langle i+1 | dp \rangle)
= 0.5(dp_i+dp_{i+1})
$$

$$
dp_{e,W}
= \langle i-1/2 | \hat{M} | dp \rangle
= 0.5(\langle i-1 | dp \rangle + \langle i | dp \rangle)
= 0.5(dp_{i-1}+dp_{i})
$$

**4) 대각 연산자**

우리가 흔히 쓰는 대각 행렬 $\text{diag}(|V\rangle)$를 추상 연산자 수준에서 엄밀하게 정의하면 다음과 같다.

$$
\text{diag}(|V\rangle) = \sum_{j} v_j |j+1/2\rangle \langle j+1/2|
$$

여기서 $v_j$는 에지 $j+1/2$에서의 스칼라 물성값이다. 이 식의 의미는 **각 에지 지점을 그 지점의 물성값만큼 스케일링하여 제자리에 돌려놓는 투영 연산자의 합** 이다. 이제 이 연산자에 에지 관찰자 $\langle i+1/2 |$를 왼쪽에서 작용시켜 본다.

$$
\langle i+1/2 | \text{diag}(|V\rangle) = \langle i+1/2 | \left( \sum_{j} v_j |j+1/2\rangle \langle j+1/2| \right)
$$

선형성에 의해 브라가 합 기호($\sum$) 안으로 들어가면 기저끼리의 내적이 발생한다.

$$
= \sum_{j} v_j \underbrace{\langle i+1/2 | j+1/2 \rangle}_{\delta_{ij}} \langle j+1/2 |
$$

에지 기저의 직교 정규성(Orthonormality)에 의해 $j=i$인 항만 살아남고 나머지는 모두 산화되어 사라진다.

$$
= v_i \langle i+1/2 |
$$

여기서 $v_i$는 곧 $\langle i+1/2 | V \rangle$를 의미하므로, 다음의 식이 유도된다.

$$
\langle i+1/2 | \text{diag}(|V\rangle) = \langle i+1/2 | V \rangle \cdot \langle i+1/2 |
$$

**5) Divergence 연산자**

발산 연산자는 **에지 공간의 정보를 노드 공간으로 모으는** 외적(Outer product) 형식으로 정의된다.
 
$$
\hat{\hat{D}}_{div} = \sum_{j} \frac{1}{V_j} | j \rangle \left( \langle j+1/2 | - \langle j-1/2 | \right)
$$
 
이제 이 연산자를 유량 상태 $|F\rangle$에 작용시키고 노드 $\langle i |$에서 관찰한다.
 
$$
\langle i | \hat{D}_{div} | F \rangle = \langle i | \left[ \sum_{j} \frac{1}{V_j} | j \rangle \left( \langle j+1/2 | F \rangle - \langle j-1/2 | F \rangle \right) \right]
$$
 
$\langle i | j \rangle = \delta_{ij}$에 의해 $j=i$인 항만 살아남는다.
 
$$
= \frac{1}{V_i} \left( \langle i+1/2 | F \rangle - \langle i-1/2 | F \rangle \right)
= \frac{1}{V_i} \left( F_E - F_W \right)
$$

---

### 2. 혼합 연산자

**1) 유량 연산자**

"물리의 실체"유량 연산자는 노드 전위를 에지 유량으로 바꾸는 기계이다.

$$
\hat{F} = \text{diag}(\hat{M}|p(u)\rangle) \cdot \hat{D}
$$

우리가 알고 싶은 것은 지금 이 전압에서 전류가 얼마나 흐르는가? 이다. 에지 기저 $\langle i+1/2 |$ 위에서 정의된다. 전체 유량 상태 벡터 $|F\rangle$는 다음과 같이 정의된다.

$$
|F\rangle = \text{diag}(\hat{M}|p(u)\rangle) \cdot \hat{D} |u\rangle
$$

여기서 특정 에지 $i+1/2$에서의 값인 $\langle i+1/2 | J \rangle$를 알고 싶다면, 식의 양변 왼쪽에 에지 관찰자인 $\langle i+1/2 |$를 곱해준다.

$$
\langle i+1/2 | F \rangle = \langle i+1/2 | \left[ \text{diag}(\hat{M}|p(u)\rangle) \cdot \hat{D} |u\rangle \right]
= \left( \langle i+1/2 | \hat{M} | p(u) \rangle \right) \cdot \langle i+1/2 | \hat{D} | u \rangle
= p_{e,E}\,g_{e,E}
$$

**2) 잔차 연산자**

$\hat{L}=-\hat{D}p\hat{D}+q$로 정의되어 있다면,
$$
\hat{R}
=-\hat{D}_{div}\text{diag}(\hat{M}|p(u)\rangle)\hat{D}+\text{diag}(|q(u)\rangle)
=-\hat{D}_{div}\hat{F}+\text{diag}(|q(u)\rangle)
$$

인덱스 작용을 살펴본다.

$$
\langle i|\hat{R}|u\rangle
=-\langle i|\hat{D}_{div}\hat{F}|u\rangle+\langle i|\text{diag}(|q(u)\rangle)|u\rangle
=-\langle i|\hat{D}_{div}\hat{F}|u\rangle+\langle i|q(u)\rangle\langle i|u\rangle
$$

$$
\implies R_i=-\frac{1}{V_i} \left( F_E - F_W \right)+q_i(u_i)u_i
$$

---

### 3. Jacobian

**1) 잔차 상태 벡터**

$$
|R\rangle = \hat{R}|u\rangle
$$

- 상태 벡터 ($|u\rangle \in \mathcal{H}$)시스템의 전위 분포를 나타내는 물리적 상태이다.
- 잔차 연산자 ($\hat{R} : \mathcal{H} \to \mathcal{V}$)상태 $|u\rangle$를 입력받아 물리적 불평형량을 산출하는 함수적 기계이다.
- 잔차 벡터 ($|R\rangle \in \mathcal{V}$)연산자 $\hat{R}$이 특정 상태 $|u\rangle$에 작용하여 뱉어낸 결과물입니다.

**2) 벡터의 변화량**

뉴턴-랩슨 루프에서 우리가 추적하는 변화량은 연산자라는 기계의 변화가 아니라, 그 기계가 출력하는 **잔차 값의 변화** 이다. 상태가 $|u\rangle$에서 $|u + \delta u\rangle$로 미소하게 변할 때, 출력되는 잔차 벡터의 변화 $|\delta R\rangle$은 다음과 같이 정의된다.

$$
|\delta R\rangle = \hat{R}(|u + \delta u\rangle) - \hat{R}(|u\rangle)
$$

여기서 $|\delta R\rangle$은 잔차 공간 $\mathcal{V}$에 존재하는 엄연한 **벡터(Ket)** 이다. 각 노드 $i$에서 발생하는 스칼라 잔차 변화량 $\delta R_i$는 이 벡터를 해당 노드의 기저 브라 $\langle i |$로 관측(Projection)한 결과이다.

$$
\delta R_i = \langle i | \delta R \rangle
$$

**3) 자코비안 연산자 $\hat{J}$**

이 지점에서 자코비안 $\hat{J}$의 역할이 정의된다. 자코비안은 상태의 변화($|\delta u\rangle$)를 잔차 벡터의 변화($|\delta R\rangle$)로 변환해주는 선형 연산자이다.

$$
|\delta R\rangle = \hat{J} |\delta u\rangle
$$

이 식의 양변에 브라 $\langle i |$를 걸고, 우변에 완비성 관계 $\sum_j |j\rangle \langle j| = I$를 삽입하면,

$$
\langle i | \delta R \rangle = \langle i | \hat{J} | \delta u \rangle = \sum_j \langle i | \hat{J}_R | j \rangle \langle j | \delta u \rangle
\implies \delta R_i =\sum_j J_{ij} \delta u_j = J_{i1}\delta u_1+J_{i2}\delta u_2+\cdots
$$

전미분 관계에 의해서,

$$
J_{ij}
=\frac{\partial R_i}{\partial u_j}
$$

위에서 구한 잔차 연산자의 결과를 대입하면,

$$
J_{ij}
=-\frac{1}{V_i} \left(\frac{\partial F_E}{\partial u_j} - \frac{\partial F_W}{\partial u_j} \right)+\frac{\partial}{\partial u_j}(q_i(u_i)u_i)=-\frac{1}{V_i} \left(\frac{\partial F_E}{\partial u_j} - \frac{\partial F_W}{\partial u_j} \right)+u_i\frac{\partial q_i}{\partial u_j}+q_i\frac{\partial u_i}{\partial u_j}
$$  

---
