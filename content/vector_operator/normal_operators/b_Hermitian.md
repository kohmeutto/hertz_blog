+++
title = "(b) Hermitian"
weight = 2
+++

---

## 1. 허미션 연산자 (Hermitian Operator)

**1) 정의**

연산자 $\hat{A}$가 자신의 허미션 켤레($\hat{A}^\dagger$)와 같을 때, 즉 $\hat{A} = \hat{A}^\dagger$일 때, 이를 에르미트 연산자라고 한다. 이는 정규 연산자($[\hat{A}, \hat{A}^\dagger]=0$)의 조건을 자명하게 만족한다.

**2) 물리적 의미**

양자역학에서 **측정 가능한 모든 물리량(Observable)**, 예를 들어 에너지, 위치, 운동량 등은 반드시 에르미트 연산자로 표현된다.

---

### 2. 고유값은 항상 실수이다

고유값은 항상 실수이다

proof)

(1) $\hat{A}|v\rangle = \lambda|v\rangle$ 에서, 양변에 $\langle v|$를 내적하면 $\langle v|\hat{A}|v\rangle = \lambda\langle v|v\rangle$ 이다.  
(2) 위 식의 에르미트 켤레를 취하면 $(\langle v|\hat{A}|v\rangle)^\dagger = (\lambda\langle v|v\rangle)^\dagger$ 이다.  
(3) $(\hat{A}|v\rangle)^\dagger = \langle v|\hat{A}^\dagger$ 이므로, $\langle v|\hat{A}^\dagger|v\rangle = \lambda^*\langle v|v\rangle$ 이다.  
(4) $\hat{A} = \hat{A}^\dagger$ 이므로, $\langle v|\hat{A}|v\rangle = \lambda^*\langle v|v\rangle$ 이다.  
(5) 1번과 4번 결과를 비교하면 $\lambda\langle v|v\rangle = \lambda^*\langle v|v\rangle$ 이고, $\langle v|v\rangle \neq 0$ 이므로 $\lambda=\lambda^*$ 이다. 따라서 고유값 $\lambda$는 실수이다.

---

### 3. 예

**1) 파울리 스핀 행렬 $\sigma_y$**

$$
\sigma_y = \begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix}
$$

(1) 허미션 확인

$$
\sigma_y^\dagger = (\sigma_y^*)^T = \begin{pmatrix} 0 & i \\ -i & 0 \end{pmatrix}^T = \begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix} = \sigma_y
$$

(2) 고유값

$$
\det(\sigma_y - \lambda I) = \lambda^2 - 1 = 0 \implies \lambda = 1, -1
$$

(3) 고유벡터

$$
\lambda=1 \text{:} \quad |v_1\rangle \rightarrow \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ i \end{pmatrix}
$$

$$
\lambda=-1 \text{:} \quad |v_2\rangle \rightarrow \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ -i \end{pmatrix}
$$

(4) 직교성 확인

$$
\langle v_1|v_2\rangle = \frac{1}{2}\begin{pmatrix} 1 & -i \end{pmatrix}\begin{pmatrix} 1 \\ -i \end{pmatrix} = \frac{1}{2}(1 - 1)=0
$$

**2) 운동량 연산자 (함수 공간)**

$$
\hat{P} = -i\hbar\frac{d}{dx}
$$

(1) 에르미트 확인

부분적분을 통해 (함수가 무한대에서 0이 된다는 가정 하에, $\mathcal{R}\hat{P}=0$), 아래임을 보일 수 있다.

$$
\langle f|\hat{P}|g\rangle = \langle \hat{P}f|g\rangle
$$


(2) 고유함수 및 고유값

$$
\hat{P}e^{ikx} = (\hbar k)e^{ikx}
$$

- 고유함수: $e^{ikx}$
- 고유값(측정 가능한 운동량): $\hbar k$이며, $k$가 실수이므로 항상 실수이다.
