+++
title = "(b) Spectral theory"
weight = 3
+++

---

### 1. Spectral theroy

**고유벡터가 완비적이라면, 연산자, 입력, 출력 모두 고유벡터로 표현할 수 있다.** 고유벡터의 완비성에 대한 증명은 정규연산자에서 다룬다.

$$
\hat{A}|v\rangle=|f\rangle
$$

**(1) 입력벡터**

- 열벡터

$$
|v\rangle = \sum_i \alpha_i |\lambda_i\rangle
$$

- 함수벡터

$$
|v\rangle = \int d\lambda \alpha(\lambda) |\lambda\rangle
$$

**(2) 출력벡터**

- 열벡터

$$
|f\rangle = \sum_i \beta_i |\lambda_i\rangle
$$

- 함수벡터

$$
|f\rangle = \int d\lambda \beta(\lambda) |\lambda\rangle
$$


**(3) 연산자, 스팩트럼 분해(대각화)**

- 열벡터

$$
\hat{A}=\sum_i \lambda_i|\lambda_i\rangle\langle\lambda^i|
$$

만약, 고유벡터가 정규직교라면,

$$
\hat{A}=\sum_i \lambda_i|\lambda_i\rangle\langle\lambda_i| \implies A=PDP^{-1}
$$

연산자 $\hat{A}$의 작용은, 각 **고유 상태 방향으로 투영($|\lambda_i\rangle\langle \lambda_i|$)** 한 다음, 그 방향의 **고유값($\lambda_i$)** 만큼 크기를 조절해주는 행위를 모든 고유 방향에 대해 합산한 것과 같다.

proof)

$$
\hat{A}=\hat{A}\hat{I}
=\hat{A}\sum_i|\lambda_i\rangle\langle\lambda^i|
=\sum_i\hat{A}|\lambda_i\rangle\langle\lambda^i|
=\sum_i\lambda_i|\lambda_i\rangle\langle\lambda^i|
$$

- 함수벡터

$$
\hat{A}=\int d\lambda K(\lambda) |\lambda\rangle \langle\lambda|
$$

---

### 2. 스팩트럼 분해의 의미

고유벡터의 의미를 다시한번 살펴보자. 고유벡터가 어떤 시스템(연산자)에 입력되었을 경우, **입력(고유벡터)의 특성이 전혀 변하지(왜곡되지) 않으면서, 크기만 바뀌어 출력되는 입력을 의미한다.**

비유: 오디오 이퀄라이저

- 시스템 (연산자): 소리를 변화시키는 복잡한 오디오 필터.
- 임의의 벡터: 수많은 주파수가 섞여있는 '음악'.
- 고유벡터: '100Hz 순수 사인파', '250Hz 순수 사인파' 등 각각의 순수한 주파수 성분.
- 고유값: 각 주파수 채널의 볼륨 조절 값 (증폭 또는 감쇠).

복잡한 오디오 필터(연산자 $\hat{A}$)가 음악(벡터 $|v\rangle$)에 어떻게 작용하는지 이해하기는 어렵다. 하지만 이 필터의 고유벡터($|\lambda_i\rangle$, 순수 주파수들)를 안다면, 그 작용은 매우 단순해진다. 이 필터는 100Hz 성분은 1.5배 증폭($\lambda_1=1.5$)하고, 250Hz 성분은 0.8배 감쇠($\lambda_2=0.8$)시키는구나. **스팩트럼 분해(대각화)** 는 이 복잡한 필터를, **각 주파수 채널마다 독립적으로 작동하는 간단한 '볼륨 노브'들의 집합** 으로 보는 것과 같다. 결론적으로, 고유벡터를 안다는 것은 복잡하게 얽혀있는 시스템을, 서로 영향을 주지 않는 단순하고 독립적인 문제들의 합으로 분해하여 바라볼 수 있게 됨을 의미한다.

---

### 3. 연산자의 고유벡터들이 완비성을 가질 조건

**모든 고유값(eigenvalue)** 에 대해,

$$
\text{총 대수적 중복도}=\text{기하적 중복도}
$$

쉽게 말해, **중복된 고유값의 개수만큼, 선형 독립인 고유벡터를 찾을 수 있어야 한다.**

**(1) 대수적 중복도**

고유값을 계산하기 위해 특성 방정식을 풀었을 때, 특정 고유값이 **'근으로서 몇 번 중복되는가'** 를 의미한다. 

- 예시: $(\lambda-2)^2(\lambda-5)=0$ 의 특성방정식
    - 고유값 $\lambda=2$의 대수적 중복도는 2이다.
    - 고유값 $\lambda=5$의 대수적 중복도는 1이다.

**(2) 기하학적 중복도**

하나의 고유값에 대해, 서로 **'선형 독립인 고유벡터를 몇 개나 찾을 수 있는가'** 를 의미한다.

---

### 4. 연산자의 멱

$$
\hat{A}^n
=\sum_i (\lambda_i)^n|\lambda_i\rangle\langle\lambda^i|
$$

proof)

$$
\hat{A}^2=\sum_i\sum_j (\lambda_i|\lambda_i\rangle\langle\lambda^i|)(\lambda_j|\lambda_j\rangle\langle\lambda^j)
$$

$$
=\sum_i\sum_j \lambda_i\lambda_j|\lambda_i\rangle\langle\lambda^i|\lambda_j\rangle\langle\lambda^j|
$$

$$
=\sum_i\sum_j \lambda_i\lambda_j|\lambda_i\rangle\delta^i_j\langle\lambda^j|
$$

$$
=\sum_i (\lambda_i)^2|\lambda_i\rangle\langle\lambda^i|
$$

---

**example1)** 허미션 행렬 $A$를 대각화 하시오.

$$
A = \begin{bmatrix} 2 & 1 \\ 1 & 2 \end{bmatrix}
$$

sol)

$$
\hat{A}=\sum_i \lambda_i |\lambda_i\rangle\langle\lambda^i|
$$

(1) 고유값

$$
(2-\lambda)^2-1=0\implies\lambda_1=1,\lambda_2=3
$$

(2) 고유벡터

- $\lambda_1=1$에서, $|\lambda_1\rangle=[1\,-1]^T$, $\langle\lambda^1|=\cfrac{1}{2}[1\,-1]$
- $\lambda_2=3$에서, $|\lambda_2\rangle=[1\,1]^T$, $\langle\lambda^2|=\cfrac{1}{2}[1\,1]$

(3) 구성

$$
\lambda_1|\lambda_1\rangle\langle\lambda^1|
=\frac{1}{2}\begin{bmatrix}1 & -1 \\ -1 &1\end{bmatrix}
$$

$$
\lambda_2|\lambda_2\rangle\langle\lambda^2|
=\frac{3}{2}\begin{bmatrix}1 & 1 \\ 1 & 1\end{bmatrix}
$$