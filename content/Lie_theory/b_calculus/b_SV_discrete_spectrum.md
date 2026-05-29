+++
title = "(b) SV discrete spectrum"
weight = 2
+++

---

### 1. 일반 형태: 세 항 분해

매개변수 $\tau$에 의존하는 행렬 $\hat{A}(\tau)$의 스펙트럼 분해를 다음과 같이 쓴다.

$$
\hat{A}(\tau) = \sum_i \lambda_i(\tau)\, \vert \lambda_i(\tau)\rangle\langle \lambda^i(\tau)\vert
$$

고유값 $\lambda_i(\tau)$와 고유벡터 $\vert \lambda_i(\tau)\rangle$ 둘 다 $\tau$에 따라 변할 수 있다 (쌍대 기저 $\langle \lambda^i(\tau)\vert$ 도 함께 변한다).

$$
\frac{d\hat{A}}{d\tau} = \sum_i \Big[\dot\lambda_i\, \vert \lambda_i\rangle\langle \lambda^i\vert + \lambda_i\, \vert\dot \lambda_i\rangle\langle \lambda^i\vert + \lambda_i\, \vert \lambda_i\rangle\langle \dot \lambda^i\vert\Big]
$$

여기서 점은 $\tau$에 대한 미분이다 ($\dot\lambda_i = d\lambda_i/d\tau$ 등). 세 항의 의미:

- 고유값 변화 항
- 켓 고유벡터 회전 항
- 브라 고유벡터 회전 항

---

### 2. 고유벡터가 고정일 경우

$\vert \lambda_i\rangle$ 와 $\langle \lambda^i\vert$ 가 $\tau$ 와 무관하면 ($\vert\dot \lambda_i\rangle = 0$, $\langle\dot \lambda^i\vert = 0$), 뒤의 두 항이 사라진다.

$$
\frac{d\hat{A}}{d\tau} = \sum_i \dot\lambda_i\, \vert \lambda_i\rangle\langle \lambda^i\vert
$$

**1) 고유값이 매개변수에 명시 주어진 경우 - 직접 미분**

$\lambda_i(\tau)$ 가 $\tau$ 의 명시적 함수로 손에 들려 있으면 그냥 미분한다.

$$
\dot\lambda_i = \frac{d\lambda_i}{d\tau}
$$

이 경우의 예는 아래의 [3. (중요) 고유벡터가 고정: $\text{exp}(\tau \hat{X})$를 참고한다.

**2) 중요: 보편적 적용 방법: 헬만-파인만 정리**

$\lambda_i(\tau)$ 가 명시적 함수 형태로 알 수 없는 경우, 또는 복잡하여 미분이 쉽지않거나 불가능한 경우가 일반적으로 더 흔한 상황이다.( 특성 다항식의 근을 닫힌 형태로 적기 어려운 경우 (Abel–Ruffini, $n \geq 5$ 의 경우 거의 항상; $n = 2, 3, 4$ 여도 식이 번거로움) 보편적으로 다루기 위해 헬만-파인만을 적용한다.

$$
\dot\lambda_i = \langle\lambda^i|\frac{d\hat A}{d\tau}|\lambda_i\rangle
$$

proof)

고유값 방정식 $\hat A|\lambda_i\rangle = \lambda_i|\lambda_i\rangle$ 의 양변을 $\tau$ 로 미분한다.

좌우변에 곱셈 규칙 적용한다.

$$
\frac{d}{d\tau}(\hat A|\lambda_i\rangle) = \frac{d\hat A}{d\tau}|\lambda_i\rangle + \hat A\frac{d|\lambda_i\rangle}{d\tau}
,\quad \frac{d}{d\tau}(\lambda_i|\lambda_i\rangle) = \dot\lambda_i|\lambda_i\rangle + \lambda_i\frac{d|\lambda_i\rangle}{d\tau}
$$

좌변 = 우변

$$\frac{d\hat A}{d\tau}|\lambda_i\rangle + \hat A\frac{d|\lambda_i\rangle}{d\tau} = \dot\lambda_i|\lambda_i\rangle + \lambda_i\frac{d|\lambda_i\rangle}{d\tau}$$

양변에 $\langle\lambda^i|$ 를 왼쪽에서 곱한다.

$$\langle\lambda^i|\frac{d\hat A}{d\tau}|\lambda_i\rangle + \langle\lambda^i|\hat A\frac{d|\lambda_i\rangle}{d\tau} = \langle\lambda^i|\dot\lambda_i|\lambda_i\rangle + \langle\lambda^i|\lambda_i\frac{d|\lambda_i\rangle}{d\tau}$$

우변 첫째 항:

$$
\langle\lambda^i|\dot\lambda_i|\lambda_i\rangle = \dot\lambda_i\langle\lambda^i|\lambda_i\rangle
=\dot\lambda_i \cdot 1 = \dot\lambda_i
$$

우변 둘째 항

$$
\langle\lambda^i|\lambda_i\frac{d|\lambda_i\rangle}{d\tau} = \lambda_i\langle\lambda^i|\frac{d|\lambda_i\rangle}{d\tau}
$$

이 결과를 원 식에 대입:

$$
\langle\lambda^i|\frac{d\hat A}{d\tau}|\lambda_i\rangle + \lambda_i\langle\lambda^i|\frac{d|\lambda_i\rangle}{d\tau} = \dot\lambda_i + \lambda_i\langle\lambda^i|\frac{d|\lambda_i\rangle}{d\tau}
$$

따라서,

$$
\dot\lambda_i = \langle\lambda^i|\frac{d\hat A}{d\tau}|\lambda_i\rangle
$$

도출 과정에서 고유벡터 미분 $d|\lambda_i\rangle/d\tau$ 가 형식적으로 식에 들어왔지만 양변에서 정확히 상쇄되어 사라진다는 점이 핵심 이다. 즉, **고유값 미분을 계산하려고 고유벡터 미분을 미리 알 필요가 없다**. 이 경우의 예는 아래의 [4. 고유벡터 고정: 헬만-파인만 정리를 참고한다.

---

### 3. (중요) 고유벡터가 고정: $\text{exp}(\tau X)$

$\hat{X}$ 가 $\tau$ 에 무관하고 대각화 가능할 때,

$$
\dfrac{d}{d\tau}\exp(\tau X) = X\, \exp(\tau\hat{X})
$$

proof)

$\hat{A}(\tau) = \exp(\tau \hat{X})$ 를 스펙트럼 분해로 본다.

$$
\hat{X}=\sum_i \lambda_i\, \vert \lambda_i\rangle\langle \lambda^i\vert
$$

$$
\hat{A}(\tau) = \exp(\tau \hat{X}) = \sum_i e^{\tau \lambda_i}\, \vert \lambda_i\rangle\langle \lambda^i\vert
$$

즉, $\hat{A}(\tau)$ 의 고유값은 $e^{\tau\lambda_i}$ ($\tau$-의존), 고유벡터는 $\vert \lambda_i\rangle$ ($\tau$-무관, $\hat{X}$ 와 동일). 따라서,

$$\frac{d\hat{A}}{d\tau} = \sum_i \frac{d}{d\tau}\big(e^{\tau\lambda_i}\big)\, \vert \lambda_i\rangle\langle \lambda^i\vert = \sum_i \lambda_i\, e^{\tau\lambda_i}\, \vert \lambda_i\rangle\langle \lambda^i\vert$$

이 결과는 $\hat{X} \cdot \hat{A}(\tau)$ 와 같다.

$$
\hat{X} \cdot \hat{A}(\tau) = \left(\sum_j \lambda_j\, \vert \lambda_j\rangle\langle \lambda^j\vert\right) \left(\sum_i e^{\tau\lambda_i}\, \vert \lambda_i\rangle\langle \lambda^i\vert\right)
= \sum_i \lambda_i\, e^{\tau\lambda_i}\, \vert \lambda_i\rangle\langle \lambda^i\vert
$$

따라서,

$$
\dfrac{d}{d\tau}\exp(\tau X) = X\, \exp(\tau X)
$$

---

### 4. 고유벡터 고정: 헬만-파인만 정리의 적용

$$\hat A(\tau) = \begin{pmatrix} \tau^3 & e^\tau \\ e^\tau & \sin\tau \end{pmatrix}$$

의 $\tau = 0$ 에서의 $\dot\lambda_+$ 를 구한다.

sol)

*(1) $\tau = 0$ 평가*

$\hat A$ 의 각 성분을 $\tau = 0$ 에서 평가:

$$\hat A(0) = \begin{pmatrix} 0^3 & e^0 \\ e^0 & \sin 0 \end{pmatrix} = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}$$


*(2) 고유값과 고유벡터*

- 고유값:

$$
\det\begin{pmatrix} -\lambda & 1 \\ 1 & -\lambda \end{pmatrix} = \lambda^2 - 1 = 0\implies
\lambda_\pm = \pm 1
$$

- 고유벡터:

$$
\begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}\begin{pmatrix} a \\ b \end{pmatrix} = \begin{pmatrix} b \\ a \end{pmatrix} = \begin{pmatrix} a \\ b \end{pmatrix}\implies
|\lambda_+\rangle = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ 1 \end{pmatrix},\quad
\langle\lambda^+| = \langle\lambda_+| = \frac{1}{\sqrt{2}}(1, 1)
$$

(3) *닫힌 형태 시도와 그 한계*

- $\hat A(\tau)$ 의 특성 다항식

$$
(\tau^3 - \lambda)(\sin\tau - \lambda) - e^{2\tau} = 0\implies
\lambda^2 - (\tau^3 + \sin\tau)\lambda + (\tau^3 \sin\tau - e^{2\tau}) = 0
$$

$$
\lambda_\pm(\tau) = \frac{(\tau^3 + \sin\tau) \pm \sqrt{(\tau^3 + \sin\tau)^2 - 4(\tau^3 \sin\tau - e^{2\tau})}}{2}
$$

이를 일일이 미분하는 것이 직접 미분 경로지만, 다음 단점이 있다.

- 위 표현이 닫힌 형태이긴 하지만 *명시적으로 매끄러운 친숙한 함수* 형태는 아니다.
- 판별식 안에 $\tau$ 의 비선형 결합이 들어가 있어 미분이 번거롭다.
- $n \geq 5$ 일반 행렬이면 Abel–Ruffini 정리에 의해 이런 닫힌 형태조차 존재하지 않는다.

따라서, 직접 미분 대신 헬만-파인만으로 우회한다.

(4) *미분 행렬 $d\hat A/d\tau$*

- 성분별 미분:

$$\frac{d\hat A}{d\tau} = \begin{pmatrix} d(\tau^3)/d\tau & d(e^\tau)/d\tau \\ d(e^\tau)/d\tau & d(\sin\tau)/d\tau \end{pmatrix} = \begin{pmatrix} 3\tau^2 & e^\tau \\ e^\tau & \cos\tau \end{pmatrix}$$

- $\tau = 0$ 평가:

$$\frac{d\hat A}{d\tau}\bigg|_{\tau=0} = \begin{pmatrix} 3 \cdot 0 & e^0 \\ e^0 & \cos 0 \end{pmatrix} = \begin{pmatrix} 0 & 1 \\ 1 & 1 \end{pmatrix}$$

*(5) 헬만-파인만 정리 적용*

$$\dot\lambda_+ = \langle\lambda^+|\frac{d\hat A}{d\tau}|\lambda_+\rangle\implies
\dot\lambda_+\big|_{\tau=0} = \left(\frac{1}{\sqrt{2}}(1, 1)\right) \begin{pmatrix} 0 & 1 \\ 1 & 1 \end{pmatrix} \left(\frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ 1 \end{pmatrix}\right)
=\frac{3}{2}
$$

---

### 5. 고유벡터가 변하는 상황: 비퇴화

일반적으로 $\hat{A}(\tau)$ 의 고유벡터도 $\tau$ 에 따라 변한다. **비퇴화 고유값 ($\lambda_i \neq \lambda_j$ for $i \neq j$) 가정** 한다.

$$
\vert \dot \lambda_i \rangle = \sum_{j\neq i} \frac{\langle \lambda^j \vert \dot{A} \vert \lambda_i\rangle}{\lambda_i - \lambda_j}\, \vert \lambda_j\rangle
$$

- 고유값이 가까울수록 분모가 작아져 고유벡터의 변화율이 커진다 (작은 섭동에도 큰 회전)
- 고유값이 겹치는 경우(퇴화)는 분모가 0이 돼 위 공식이 직접 적용되지 않는다. 이 경우 퇴화 섭동 이론이 필요하다

proof)

고유값 식 $\hat{A}\vert \lambda_i\rangle = \lambda_i \vert \lambda_i\rangle$ 양변을 미분한다.

$$
\dot A\vert \lambda_i\rangle + \hat{A} \vert \dot \lambda_i\rangle = \dot\lambda_i\vert \lambda_i\rangle + \lambda_i\vert \dot \lambda_i\rangle
$$

좌변에 $\langle \lambda^j\vert$ ($j \neq i$)를 곱한다. $\langle \lambda^j\vert \lambda_i\rangle = 0$ 이고 $\langle \lambda^j\vert \hat{A} = \lambda_j\langle \lambda^j\vert$ 이므로

$$
\langle \lambda^j\vert \dot A \vert \lambda_i\rangle + \lambda_j\langle \lambda^j\vert \dot \lambda_i\rangle = 0 + \lambda_i\langle \lambda^j\vert \dot \lambda_i\rangle
$$

정리하면:

$$
\langle \lambda^j\vert \dot \lambda_i\rangle = \frac{\langle \lambda^j\vert\dot A\vert \lambda_i\rangle}{\lambda_i - \lambda_j}
$$

이를 $\vert\dot \lambda_i\rangle = \sum_j \langle \lambda^j\vert\dot \lambda_i\rangle\, \vert \lambda_j\rangle$ 에 대입하면 위 공식이 나온다.

---

### 6. (참고) 고유벡터가 변하는 상황: 퇴화

**1) 문제의 정의 및 한계**

비퇴화(Non-degenerate) 가정 하에 유도된 1차 보정 공식은 연산자 $\hat{A}$의 특정 고유값이 중복도 $d \geq 2$로 나타날 경우 적용할 수 없다. 분모에 나타나는 고유값 차이 $\lambda_i - \lambda_j$가 0이 되어 특이점(Singularity)이 발생하기 때문이다.이를 해결하기 위해 인덱스를 분리한다.

중복된 고유값을 $\lambda_0$라 할 때, $\lambda_i = \lambda_0$인 인덱스를 $\alpha, \beta = 1, \dots, d$로, $\lambda_i \neq \lambda_0$인 비퇴화 인덱스를 $j, k$로 표기한다.

**2) 핵심 결과**

퇴화가 1차 보정에서 완전히 풀린다고 가정할 때($M$의 고유값이 모두 서로 다름), 0차 고유벡터의 계수와 1차 고유값 및 고유벡터 보정항은 다음과 같이 결정된다.

*(1) $M$ 행렬의 정의와 고유값 문제*

$\hat{A}$의 $\lambda_0$에 대응하는 $d$차원 우고유부공간의 임의의 기저(작업용 기저) $\{\vert\phi_\alpha\rangle\}$와 그 쌍대 $\{\langle\phi^\beta\vert\}$($\langle\phi^\beta\vert\phi_\alpha\rangle = \delta^\beta_\alpha$)를 도입하여 $d \times d$ 행렬 $M$을 정의한다.

$$
M_{\gamma\delta} \equiv \langle\phi^\gamma\vert\dot{A}\vert\phi_\delta\rangle
$$

0차 고유벡터를 $\vert\lambda_\alpha\rangle = \sum_\beta c_{\beta\alpha}\vert\phi_\beta\rangle$로 전개할 때, 미지 계수 벡터 $\mathbf{c}_\alpha = (c_{1\alpha}, \dots, c_{d\alpha})^T$와 1차 고유값 보정 $\dot{\lambda}_\alpha$는 행렬 $M$의 고유값 방정식으로 결정된다.

$$
M\mathbf{c}_\alpha = \dot{\lambda}_\alpha\mathbf{c}_\alpha
$$

*(2) 1차 고유벡터 보정식*

1차 고유벡터 보정 $\vert\dot{\lambda}_\alpha\rangle$는 비퇴화 공간 성분과 퇴화 공간 성분으로 나뉘어 완전하게 결정된다.

$$
\vert\dot{\lambda}_\alpha\rangle = \sum_j\frac{\langle\lambda^j\vert\dot{A}\vert\lambda_\alpha\rangle}{\lambda_0 - \lambda_j}\vert\lambda_j\rangle + \sum_{\substack{\beta=1\\\beta\neq\alpha}}^d \frac{1}{\dot{\lambda}_\alpha - \dot{\lambda}_\beta}\left[\sum_j\frac{\langle\lambda^\beta\vert\dot{A}\vert\lambda_j\rangle\langle\lambda^j\vert\dot{A}\vert\lambda_\alpha\rangle}{\lambda_0 - \lambda_j} + \frac{1}{2}\langle\lambda^\beta\vert\ddot{A}\vert\lambda_\alpha\rangle\right]\vert\lambda_\beta\rangle
$$

작업용 기저의 선택은 임의적이며, 기저가 달라져도 최종적인 $\dot{\lambda}_\alpha$와 $\vert\lambda_\alpha\rangle$의 물리적 결과는 변하지 않는다.비퇴화 한계($d = 1$)에서는 두 번째 합이 소거되어 $\dot{\lambda}_1 = \langle\phi^1\vert\dot{A}\vert\phi_1\rangle$ 단일항으로 환원된다.연산자 $\hat{A}(\tau)$가 선형적으로 변할 경우($\ddot{A} = 0$), 두 번째 합 내부의 $\ddot{A}$ 항은 소거된다.

proof)

[1단계] 1차 미분식 전개고유값 방정식 $\hat{A}\vert\lambda_\alpha\rangle = \lambda_0\vert\lambda_\alpha\rangle$의 양변을 매개변수 $\tau$에 대해 미분한다.

$$
\dot{A}\vert\lambda_\alpha\rangle + \hat{A}\vert\dot{\lambda}_\alpha\rangle = \dot{\lambda}_\alpha\vert\lambda_\alpha\rangle + \lambda_0\vert\dot{\lambda}_\alpha\rangle \quad (\star)
$$

[2단계] 비퇴화 성분 투영 및 결정식 $(\star)$의 양변에 비퇴화 공간의 좌고유벡터 $\langle\lambda^j\vert$($\lambda_j \neq \lambda_0$)를 곱한다. 좌고유벡터의 성질 $\langle\lambda^j\vert\hat{A} = \lambda_j\langle\lambda^j\vert$과 직교성 $\langle\lambda^j\vert\lambda_\alpha\rangle = 0$을 적용한다.

$$
\langle\lambda^j\vert\dot{A}\vert\lambda_\alpha\rangle + \lambda_j\langle\lambda^j\vert\dot{\lambda}_\alpha\rangle = 0 + \lambda_0\langle\lambda^j\vert\dot{\lambda}_\alpha\rangle
$$

이를 정리하여 $\vert\dot{\lambda}_\alpha\rangle$의 비퇴화 공간 성분을 추출한다.

$$
\langle\lambda^j\vert\dot{\lambda}_\alpha\rangle = \frac{\langle\lambda^j\vert\dot{A}\vert\lambda_\alpha\rangle}{\lambda_0 - \lambda_j}
$$

[3단계] 퇴화 공간 성분 투영 및 조건 도출식 $(\star)$의 양변에 퇴화 공간의 좌고유벡터 $\langle\lambda^\beta\vert$($\lambda_\beta = \lambda_0$)를 곱한다. $\langle\lambda^\beta\vert\hat{A} = \lambda_0\langle\lambda^\beta\vert$이며, 직교 규격화 조건 $\langle\lambda^\beta\vert\lambda_\alpha\rangle = \delta^\beta_\alpha$를 적용한다.

$$
\langle\lambda^\beta\vert\dot{A}\vert\lambda_\alpha\rangle + \lambda_0\langle\lambda^\beta\vert\dot{\lambda}_\alpha\rangle = \dot{\lambda}_\alpha\delta^\beta_\alpha + \lambda_0\langle\lambda^\beta\vert\dot{\lambda}_\alpha\rangle
$$

양변에서 $\lambda_0\langle\lambda^\beta\vert\dot{\lambda}_\alpha\rangle$ 항이 상쇄되어 다음과 같은 조건식이 남는다.

$$\langle\lambda^\beta\vert\dot{A}\vert\lambda_\alpha\rangle = \dot{\lambda}_\alpha\delta^\beta_\alpha
$$

이 조건은 $\dot{A}$를 기저 ${\vert\lambda_\alpha\rangle}$에 대해 표현했을 때 대각행렬이 됨을 의미하며, 이를 통해 0차 고유벡터 $\vert\lambda_\alpha\rangle$가 결정된다.

[4단계] 작업용 기저 도입 및 $M$ 행렬 유도퇴화 부공간 내의 벡터 $\vert\lambda_\alpha\rangle$를 임의의 작업용 기저로 전개한다. $\vert\lambda_\alpha\rangle = \sum_\beta c_{\beta\alpha}\vert\phi_\beta\rangle$. 식 $(\star)$의 양변에 작업용 기저의 쌍대 $\langle\phi^\gamma\vert$를 곱하여 정리하면 다음 관계를 얻는다.

$$
\langle\phi^\gamma\vert\dot{A}\vert\lambda_\alpha\rangle = \dot{\lambda}_\alpha\langle\phi^\gamma\vert\lambda_\alpha\rangle
$$

여기에 전개식을 대입하고 쌍대성 $\langle\phi^\gamma\vert\lambda_\alpha\rangle = c_{\gamma\alpha}$를 적용한다.

$$
\sum_\delta c_{\delta\alpha}\langle\phi^\gamma\vert\dot{A}\vert\phi_\delta\rangle = \dot{\lambda}_\alpha c_{\gamma\alpha}
$$

따라서 행렬 $M_{\gamma\delta} \equiv \langle\phi^\gamma\vert\dot{A}\vert\phi_\delta\rangle$을 정의하면, $M\mathbf{c}_\alpha = \dot{\lambda}_\alpha\mathbf{c}_\alpha$라는 고유값 문제가 성립한다.

[5단계] 2차 미분식 전개 및 퇴화 공간 내 비대각 성분 결정1차 미분식에서는 $\vert\dot{\lambda}_\alpha\rangle$의 퇴화 공간 내 비대각 성분 $a_{\beta\alpha} \equiv \langle\lambda^\beta\vert\dot{\lambda}_\alpha\rangle$ ($\beta \neq \alpha$)이 정보 상쇄로 인해 결정되지 않는다. 이를 구하기 위해 고유값 방정식을 $\tau$에 대해 두 번 미분한다.

$$
\ddot{A}\vert\lambda_\alpha\rangle + 2\dot{A}\vert\dot{\lambda}_\alpha\rangle + \hat{A}\vert\ddot{\lambda}_\alpha\rangle = \ddot{\lambda}_\alpha\vert\lambda_\alpha\rangle + 2\dot{\lambda}_\alpha\vert\dot{\lambda}_\alpha\rangle + \lambda_0\vert\ddot{\lambda}_\alpha\rangle \quad (\star\star)
$$

양변에 $\langle\lambda^\beta\vert$ ($\beta \neq \alpha$)를 곱하여 정리한다.

$$
\langle\lambda^\beta\vert\ddot{A}\vert\lambda_\alpha\rangle + 2\langle\lambda^\beta\vert\dot{A}\vert\dot{\lambda}_\alpha\rangle = 2\dot{\lambda}_\alpha a_{\beta\alpha}
$$

좌변의 두 번째 항 내부에 존재하는 $\vert\dot{\lambda}_\alpha\rangle$를 $\sum_\gamma a_{\gamma\alpha}\vert\lambda_\gamma\rangle + \sum_j b_{j\alpha}\vert\lambda_j\rangle$ (단, $b_{j\alpha} = (\langle\lambda^j\vert\dot{A}\vert\lambda_\alpha\rangle/(\lambda_0 - \lambda_j)$) 전개하여 대입한다. 앞서 구한 조건 $\langle\lambda^\beta\vert\dot{A}\vert\lambda_\gamma\rangle = \dot{\lambda}_\gamma\delta^\beta_\gamma$을 적용하면 최종적인 계수를 도출할 수 있다.$$a_{\beta\alpha}(\dot{\lambda}_\alpha - \dot{\lambda}_\beta) = \sum_j b_{j\alpha}\langle\lambda^\beta\vert\dot{A}\vert\lambda_j\rangle + \frac{1}{2}\langle\lambda^\beta\vert\ddot{A}\vert\lambda_\alpha\rangle$$최종적으로 $M$ 행렬의 고유값이 비퇴화($\dot{\lambda}_\alpha \neq \dot{\lambda}_\beta$)라는 가정하에 정리하면 2절의 완전한 고유벡터 보정식이 완성된다.

---

### 6. 예제

$\tau_0 = 0$에서 $\vert\dot\lambda_\alpha\rangle$를 구하라.

$$
\hat A(\tau) = \begin{pmatrix} \tau & 0 & \tau \\ 0 & 2\tau & 0 \\ \tau & 0 & 1 \end{pmatrix}
$$

sol)

$\hat A(0) = \text{diag}(0, 0, 1)$로 고유값 0이 중복도 2, 고유값 1이 중복도 1. $\lambda_0 = 0$, $d = 2$. $\dot A = \begin{pmatrix} 1 & 0 & 1 \\ 0 & 2 & 0 \\ 1 & 0 & 0 \end{pmatrix}$, $\ddot A = 0$ (선형).

**1) 작업용 기저**

$$
\vert\phi_1\rangle = (1, 0, 0)^T,\quad \vert\phi_2\rangle = (0, 1, 0)^T
$$

$$
\langle\phi^1\vert = (1, 0, 0), \quad \langle\phi^2\vert = (0, 1, 0)
$$

**2) $M$**

$$M = \begin{pmatrix} 1 & 0 \\ 0 & 2 \end{pmatrix}$$

이미 대각.

$$\dot\lambda_1 = 1,\quad \dot\lambda_2 = 2,\quad \vert\lambda_1\rangle = (1, 0, 0)^T,\quad \vert\lambda_2\rangle = (0, 1, 0)^T$$

**3) 비퇴화 인덱스**

$$\vert\lambda_j\rangle = (0, 0, 1)^T,\quad \langle\lambda^j\vert = (0, 0, 1),\quad \lambda_j = 1$$

**4) $\sum_j$ 부분**

$$\langle\lambda^j\vert\dot A\vert\lambda_1\rangle = 1,\quad \langle\lambda^j\vert\dot A\vert\lambda_2\rangle = 0$$

따라서 $\vert\dot\lambda_1\rangle$의 $\sum_j$ 기여가 $\frac{1}{-1}(0, 0, 1)^T = (0, 0, -1)^T$, $\vert\dot\lambda_2\rangle$의 $\sum_j$ 기여가 0이다.

**5) $\sum_{\beta \neq \alpha}$ 부분 ($\ddot A = 0$이므로 둘째 항만)**

$$
\langle\lambda^2\vert\dot A\vert\lambda_j\rangle = (0, 1, 0),\quad\dot A(0, 0, 1)^T = 0
$$

이므로

$$a_{2, 1} = 0,\quad a_{1, 2} = 0$$

**6) 결과**

$$
\vert\dot\lambda_1\rangle = (0, 0, -1)^T, \qquad \vert\dot\lambda_2\rangle = 0
$$

**7) 직접 검증**

$\vert\lambda_2(\tau)\rangle = (0, 1, 0)^T$가 모든 $\tau$에서 고유값 $2\tau$의 고유벡터 (둘째 행 독립)이므로 $\vert\dot\lambda_2\rangle = 0$. $\vert\lambda_1(\tau)\rangle$은 첫째와 셋째 좌표가 펼치는 부공간에서 축소판 $\begin{pmatrix} \tau & \tau \\ \tau & 1 \end{pmatrix}$의 작은 고유값에 해당하는 고유벡터 $(1, 0, -\tau + O(\tau^2))^T$이므로 $\vert\dot\lambda_1\rangle = (0, 0, -1)^T$. 결과 일치.