+++
title = "(b) M-normal"
weight = 3
+++

---

### 1. M-정규 연산자 (M-Normal Operator)

연산자 $\hat{A}$가 자신의 M-수반 연산자 $\hat{A}^\sharp$와 교환 법칙이 성립할 때, 이를 **M-정규 연산자** 라고 한다. 모든 특성 및 조건들은 정규 연산자와 같다.

$$
[\hat{A}, \hat{A}^\sharp] = \hat{A}\hat{A}^\sharp - \hat{A}^\sharp\hat{A} = 0
$$

---

### 2. M-공간에서 연산자의 스팩트럼 분해

$$
\hat{A} = \sum_i \lambda_i |\lambda_i\rangle \langle \lambda_i | \hat{M}
$$

proof)

일반적인 쌍대 기저를 이용한 연산자의 스펙트럼 표현은 다음과 같다.

$$
\hat{A} = \sum_i \lambda_i |\lambda_i\rangle \langle \lambda^i|
$$

다음의 식을 적용한다.

$$
\langle \lambda^i | = \langle \lambda_i | \hat{M}
$$

결과적으로 $\hat{M}$-정규 연산자의 스펙트럼 분해 공식은 추상적인 쌍대 기저 마커를 소거하고 계량 연산자 $\hat{M}$을 명시한 형태로 확정된다.

$$
\hat{A} = \sum_i \lambda_i |\lambda_i\rangle \langle \lambda_i | \hat{M}
$$

---

### 3. 우측 및 좌측 고유벡터의 M-켤레 대응

$\hat{M}$-정규 연산자 구조에서는 우고유벡터를 $\hat{M}$-수반화하여 좌측 고유 상태를 취할 때 고유값의 복소수 부호만이 반전된다.

$$
\hat{A}^\sharp |\lambda_i\rangle = \lambda_i^\ast |\lambda_i\rangle
$$

proof)

임의의 고유값 $\lambda$와 고유벡터 $|\lambda\rangle$에 대하여 $\hat{A}|\lambda\rangle = \lambda|\lambda\rangle$가 성립한다고 가정한다. 새로운 연산자 $\hat{T} = \hat{A} - \lambda\hat{I}$를 정의하면, $\hat{A}$가 $\hat{M}$-정규 연산자이므로 $\hat{T}$ 역시 $\hat{M}$-교환자 가환성을 유지한다.

$$
[\hat{T}, \hat{T}^\sharp] = [ \hat{A} - \lambda\hat{I}, \hat{A}^\sharp - \lambda^\ast\hat{I} ] = [\hat{A}, \hat{A}^\sharp] = 0
$$

$\hat{M}$-정규 연산자의 노름 보존 성질에 의하여 $\|\hat{T}\lambda\|_M = \|\hat{T}^\sharp \lambda\|_M$가 성립하므로, 다음의 동치 관계가 성립한다.

$$
\|(\hat{A} - \lambda\hat{I})\lambda\|_M = 0 \iff \|(\hat{A}^\sharp - \lambda^\ast\hat{I})\lambda\|_M = 0
$$

$\hat{M}$-노름의 정의상 위 조건은 다음 방정식과 동치이다.

$$
\hat{A}^\sharp |\lambda\rangle = \lambda^\ast |\lambda\rangle
$$

---

### 4. 서로 다른 고유값의 고유벡터는 M-직교

$\hat{A}|\lambda_i\rangle = \lambda_i|\lambda_i\rangle$, $\hat{A}|\lambda_j\rangle = \lambda_j|\lambda_j\rangle$, $\lambda_i \neq \lambda_j$ 이면 다음이 성립한다.

$$
\langle \lambda_i|\lambda_j\rangle_M = \langle \lambda_i| \hat{M} |\lambda_j\rangle = 0
$$

proof)

특성 1의 결과인 $\hat{A}^\sharp |\lambda_i\rangle = \lambda_i^\ast |\lambda_i\rangle$를 이용한다. 
$\hat{M}$-내적 공간에서의 행렬 요소 $\langle \lambda_i | \hat{A} | \lambda_j \rangle_M$를 두 가지 방향으로 전개하여 대조한다.

(1) 우측 작용: $\langle \lambda_i | (\hat{A} | \lambda_j \rangle)_M = \lambda_j \langle \lambda_i | \lambda_j \rangle_M$  
(2) 좌측 작용: $\hat{M}$-수반 연산자의 정의에 의해 좌측 브라에 작용시킨다.
$$
\langle \hat{A}^\sharp \lambda_i | \lambda_j \rangle_M = \langle \lambda_i^\ast \lambda_i | \lambda_j \rangle_M = \lambda_i \langle \lambda_i | \lambda_j \rangle_M
$$

두 전개 결과는 일치해야 하므로 다음의 구속 조건이 도출된다.

$$
(\lambda_i - \lambda_j) \langle \lambda_i | \lambda_j \rangle_M = 0
$$

$\lambda_i \neq \lambda_j$이므로 스칼라 항은 0이 될 수 없다. 따라서 서로 다른 고유상태 간의 $\hat{M}$-내적은 0이다.

$$
\langle \lambda_i | \lambda_j \rangle_M = 0 \quad (i \neq j)
$$

자기 자신에 대해 M-노름의 크기를 1로 정규화($\langle \lambda_i | \lambda_i \rangle_M = 1$)하면, 최종적으로 크로네커 델타 조건 $\langle \lambda_i | \hat{M} | \lambda_j \rangle = \delta_{ij}$가 성립한다.

---
