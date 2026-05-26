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

---

### 3. 고유벡터가 고정: $\exp(\tau X)$의 미분

$\hat{X}$ 가 $\tau$ 에 무관하고 대각화 가능할 때,

$$
\dfrac{d}{d\tau}\exp(\tau X) = X\, \exp(\tau X)
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

### 4. 고유벡터가 변하는 상황: 비퇴화

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

### 5. 고유벡터가 변하는 상황: 퇴화

§4 공식이 적용 불가능한 경우 ($\hat A$의 어떤 고유값이 중복도 $d \geq 2$로 나타나는 경우)를 다룬다. 그 고유값을 $\lambda_0$, $\hat A$의 인덱스 중 $\lambda_i = \lambda_0$인 것을 $\alpha, \beta = 1, \dots, d$로, $\lambda_i \neq \lambda_0$인 것을 $j, k$로 표기한다. $\hat A$의 $\lambda_0$에 대응하는 $d$차원 우고유부공간의 임의의 알려진 기저 $\{\vert\phi_\alpha\rangle\}$ (작업용 기저)와 쌍대 $\{\langle\phi^\beta\vert\}$ ($\langle\phi^\beta\vert\phi_\alpha\rangle = \delta^\beta_\alpha$)를 잡고, $d \times d$ 행렬

$$
M_{\gamma\delta} \equiv \langle\phi^\gamma\vert\dot A\vert\phi_\delta\rangle
$$

를 정의한다. **$M$의 고유값이 모두 서로 다른 경우 가정** 한다 (1차에서 퇴화가 완전히 풀리는 경우).

$$
\vert\dot\lambda_\alpha\rangle = \sum_j\frac{\langle\lambda^j\vert\dot A\vert\lambda_\alpha\rangle}{\lambda_0 - \lambda_j}\vert\lambda_j\rangle + \sum_{\substack{\beta=1\\\beta\neq\alpha}}^d \frac{1}{\dot\lambda_\alpha - \dot\lambda_\beta}\left[\sum_j\frac{\langle\lambda^\beta\vert\dot A\vert\lambda_j\rangle\langle\lambda^j\vert\dot A\vert\lambda_\alpha\rangle}{\lambda_0 - \lambda_j} + \frac{1}{2}\langle\lambda^\beta\vert\ddot A\vert\lambda_\alpha\rangle\right]\vert\lambda_\beta\rangle
$$

우변에 등장하는 0차 고유벡터 $\vert\lambda_\alpha\rangle = \sum_\beta c_{\beta\alpha}\vert\phi_\beta\rangle$의 계수 $\mathbf{c}_\alpha = (c_{1\alpha}, \dots, c_{d\alpha})^T$와 1차 고유값 보정 $\dot\lambda_\alpha$는

$$
M\mathbf{c}_\alpha = \dot\lambda_\alpha\mathbf{c}_\alpha
$$

로 결정된다.

- 작업용 기저는 임의이며, 다른 선택을 해도 $\dot\lambda_\alpha$와 $\vert\lambda_\alpha\rangle$는 변하지 않는다 ($M$의 성분 표현만 바뀐다)
- 비퇴화 한계 ($d = 1$): 둘째 합이 사라지고 $\dot\lambda_1 = \langle\phi^1\vert\dot A\vert\phi_1\rangle$이 단일 식으로 결정되어 §4 공식과 일치한다
- 선형 $\hat A(\tau)$ ($\ddot A = 0$)인 경우 둘째 합 안의 $\ddot A$ 항이 사라진다

proof)

**1) §4 한계와 인덱스 분리.**

§4 공식의 분모 $\lambda_i - \lambda_j$는 $\lambda_i = \lambda_j$인 ($i \neq j$) 항에서 0이 되어 정의되지 않는다. 본 절은 그 경우, 즉 어떤 고유값 $\lambda_0$가 중복도 $d \geq 2$로 나타나는 경우를 다룬다. 분모 0 항을 식별하기 위해 §4의 인덱스 $i$를 분리한다. $\lambda_i = \lambda_0$인 인덱스를 $\alpha, \beta$, $\lambda_i \neq \lambda_0$인 인덱스를 $j, k$로 표기한다. §4 공식을 $i = \alpha$인 경우에 형식적으로 적용해 합을 분해하면

$$
\sum_{\beta \neq \alpha}\frac{\langle\lambda^\beta\vert\dot A\vert\lambda_\alpha\rangle}{\lambda_0 - \lambda_0}\vert\lambda_\beta\rangle + \sum_j\frac{\langle\lambda^j\vert\dot A\vert\lambda_\alpha\rangle}{\lambda_0 - \lambda_j}\vert\lambda_j\rangle
$$

이 나온다. 첫째 합의 분모가 0이라 이 표현이 정의되지 않으며 §4가 무너지는 지점은 첫째 합이다. 둘째 합의 분모는 0이 아니다.

**2) 1차 미분 식.**

§4 절차에 따라 고유값 식 $\hat A\vert\lambda_\alpha\rangle = \lambda_0\vert\lambda_\alpha\rangle$ 양변을 $\tau$로 미분한다.

$$
\dot A\vert\lambda_\alpha\rangle + \hat A\vert\dot\lambda_\alpha\rangle = \dot\lambda_\alpha\vert\lambda_\alpha\rangle + \lambda_0\vert\dot\lambda_\alpha\rangle \quad (\star)
$$

$(\star)$의 양변에 좌고유벡터를 곱해 정보를 추출한다. 인덱스 분리에 따라 두 종류의 곱셈을 따로 검토한다.

**3) (I) $\langle\lambda^j\vert$ ($\lambda_j \neq \lambda_0$) 곱하기.**

목적은 $\vert\dot\lambda_\alpha\rangle$의 $\vert\lambda_j\rangle$ 성분 $\langle\lambda^j\vert\dot\lambda_\alpha\rangle$를 결정하는 것이다. $(\star)$ 양변에 $\langle\lambda^j\vert$를 곱하면

$$
\langle\lambda^j\vert\dot A\vert\lambda_\alpha\rangle + \langle\lambda^j\vert\hat A\vert\dot\lambda_\alpha\rangle = \dot\lambda_\alpha\langle\lambda^j\vert\lambda_\alpha\rangle + \lambda_0\langle\lambda^j\vert\dot\lambda_\alpha\rangle
$$

이다. 좌변 둘째 항 $\langle\lambda^j\vert\hat A\vert\dot\lambda_\alpha\rangle$는 $\hat A$가 미지의 $\vert\dot\lambda_\alpha\rangle$에 작용하는 형태다. $\langle\lambda^j\vert$가 좌고유벡터라는 성질 $\langle\lambda^j\vert\hat A = \lambda_j\langle\lambda^j\vert$를 사용해 $\hat A$를 $\lambda_j$로 환원한다. 우변 첫째 항 $\dot\lambda_\alpha\langle\lambda^j\vert\lambda_\alpha\rangle$는 $\langle\lambda^j\vert$와 $\vert\lambda_\alpha\rangle$가 서로 다른 고유값 ($\lambda_j \neq \lambda_0$)에 속한 좌/우 고유벡터이므로 직교성 $\langle\lambda^j\vert\lambda_\alpha\rangle = 0$에 의해 사라진다. 정리하면

$$
\langle\lambda^j\vert\dot\lambda_\alpha\rangle = \frac{\langle\lambda^j\vert\dot A\vert\lambda_\alpha\rangle}{\lambda_0 - \lambda_j}
$$

이다 (1) 분해의 둘째 합이 §4 절차로 그대로 도출).

**4) (II) $\langle\lambda^\beta\vert$ ($\lambda_\beta = \lambda_0$) 곱하기.**

$\langle\lambda^\beta\vert\hat A = \lambda_0\langle\lambda^\beta\vert$, $\langle\lambda^\beta\vert\lambda_\alpha\rangle = \delta^\beta_\alpha$이므로 $(\star)$ 양변 곱은

$$
\langle\lambda^\beta\vert\dot A\vert\lambda_\alpha\rangle + \lambda_0\langle\lambda^\beta\vert\dot\lambda_\alpha\rangle = \dot\lambda_\alpha\delta^\beta_\alpha + \lambda_0\langle\lambda^\beta\vert\dot\lambda_\alpha\rangle
$$

양변의 $\lambda_0\langle\lambda^\beta\vert\dot\lambda_\alpha\rangle$가 정확히 상쇄되어 $\vert\dot\lambda_\alpha\rangle$의 정보가 식에서 사라진다. 남는 것은

$$
\langle\lambda^\beta\vert\dot A\vert\lambda_\alpha\rangle = \dot\lambda_\alpha\delta^\beta_\alpha
$$

이며, 이는 $\vert\dot\lambda_\alpha\rangle$의 성분이 아니라 $\vert\lambda_\alpha\rangle$ 자체가 만족해야 할 조건이다.

**5) 조건 해석.**

위 조건의 좌변은 $\dot A$의 행렬 원소 (기저 $\{\vert\lambda_\alpha\rangle\}$에서의 표현)이고 우변은 $\beta = \alpha$일 때만 $\dot\lambda_\alpha$, 그 외는 0이다. 즉 $\dot A$를 퇴화 인덱스의 $\vert\lambda_\alpha\rangle$들이 펼치는 $d$차원 부공간으로 제한한 표현이 기저 $\{\vert\lambda_\alpha\rangle\}$에서 대각 행렬이며, 대각 원소가 $\dot\lambda_\alpha$이다. 이 조건이 (1) $\vert\lambda_\alpha\rangle$의 결정과 (2) $\dot\lambda_\alpha$의 결정을 동시에 준다.

(1) $\vert\lambda_\alpha\rangle$의 결정

$\hat A\vert\lambda_\alpha\rangle = \lambda_0\vert\lambda_\alpha\rangle$만으로는 $\vert\lambda_\alpha\rangle$가 $d$차원 부공간 안에서 유일하게 결정되지 않는다 (부공간의 모든 일차결합이 같은 식을 만족). 위 조건이 추가됨으로써 $\vert\lambda_\alpha\rangle$는 그 부공간 위에서 $\dot A$를 대각화하는 기저로 결정된다.

(2) $\dot\lambda_\alpha$의 결정

대각 원소가 1차 고유값 보정 $\dot\lambda_\alpha = \langle\lambda^\alpha\vert\dot A\vert\lambda_\alpha\rangle$를 준다.

**6) 작업용 기저 도입.**

위 조건은 $\vert\lambda_\alpha\rangle$를 결정하지만, $\vert\lambda_\alpha\rangle$ 자체가 아직 미지수다 ($\hat A v = \lambda_0 v$를 만족하는 $d$차원 부공간 안의 벡터라는 것까지만 안다). 조건을 계수 수준에서 풀려면 $\vert\lambda_\alpha\rangle$를 좌표로 표현해야 한다. 위 부공간의 임의의 알려진 기저 $\{\vert\phi_\alpha\rangle\}_{\alpha = 1, \dots, d}$를 작업용 기저로 잡고, 쌍대 $\{\langle\phi^\beta\vert\}$를 $\langle\phi^\beta\vert\phi_\alpha\rangle = \delta^\beta_\alpha$를 만족하도록 잡는다.

$\vert\lambda_\alpha\rangle$가 부공간 안의 벡터이므로

$$
\vert\lambda_\alpha\rangle = \sum_\beta c_{\beta\alpha}\vert\phi_\beta\rangle
$$

으로 전개된다. 미지 계수 $c_{\beta\alpha}$를 결정하면 $\vert\lambda_\alpha\rangle$가 결정된다.

**7) $M$ 식 유도.**

미지 계수 $c_{\beta\alpha}$를 결정하는 식을 얻기 위해 $(\star)$ 양변에 작업용 기저의 쌍대 $\langle\phi^\gamma\vert$ ($\gamma = 1, \dots, d$)를 곱한다.

먼저 $\langle\phi^\gamma\vert\hat A = \lambda_0\langle\phi^\gamma\vert$를 확인한다. $\hat A$의 스펙트럼 분해 $\hat A = \lambda_0\sum_\alpha\vert\phi_\alpha\rangle\langle\phi^\alpha\vert + \sum_j\lambda_j\vert\lambda_j\rangle\langle\lambda^j\vert$ (작업용 기저 부분 + 비퇴화 부분)에 $\langle\phi^\gamma\vert$를 좌측에서 곱하면 전체 기저의 쌍대성 ($\langle\phi^\gamma\vert\phi_\alpha\rangle = \delta^\gamma_\alpha$, $\langle\phi^\gamma\vert\lambda_j\rangle = 0$)에 의해

$$
\langle\phi^\gamma\vert\hat A = \lambda_0\sum_\alpha\delta^\gamma_\alpha\langle\phi^\alpha\vert + 0 = \lambda_0\langle\phi^\gamma\vert
$$

이다.

$(\star)$ 양변에 $\langle\phi^\gamma\vert$를 곱하면

$$
\langle\phi^\gamma\vert\dot A\vert\lambda_\alpha\rangle + \lambda_0\langle\phi^\gamma\vert\dot\lambda_\alpha\rangle = \dot\lambda_\alpha\langle\phi^\gamma\vert\lambda_\alpha\rangle + \lambda_0\langle\phi^\gamma\vert\dot\lambda_\alpha\rangle
$$

좌변 둘째 항과 우변 둘째 항이 상쇄되어

$$
\langle\phi^\gamma\vert\dot A\vert\lambda_\alpha\rangle = \dot\lambda_\alpha\langle\phi^\gamma\vert\lambda_\alpha\rangle
$$

남는다. $\langle\phi^\gamma\vert\lambda_\alpha\rangle = c_{\gamma\alpha}$ (6) 전개식과 쌍대성)을 적용하고 좌변에 6)의 전개식을 대입하면

$$
\sum_\delta c_{\delta\alpha}\langle\phi^\gamma\vert\dot A\vert\phi_\delta\rangle = \dot\lambda_\alpha c_{\gamma\alpha}
$$

$d \times d$ 행렬 $M$을 $M_{\gamma\delta} \equiv \langle\phi^\gamma\vert\dot A\vert\phi_\delta\rangle$로 정의하면

$$
M\mathbf{c}_\alpha = \dot\lambda_\alpha\mathbf{c}_\alpha
$$

이다. $\mathbf{c}_\alpha$가 $M$의 고유벡터, $\dot\lambda_\alpha$가 그 고유값이다.

**8) A형: 1차 식까지의 결과.**

3)과 7)의 결과를 모은다. $\vert\dot\lambda_\alpha\rangle$의 전체 우고유벡터 기저 전개는

$$
\vert\dot\lambda_\alpha\rangle = \sum_{\beta=1}^d \langle\lambda^\beta\vert\dot\lambda_\alpha\rangle\,\vert\lambda_\beta\rangle + \sum_j\langle\lambda^j\vert\dot\lambda_\alpha\rangle\,\vert\lambda_j\rangle
$$

이다. 둘째 합 계수는 3)에서 $\frac{\langle\lambda^j\vert\dot A\vert\lambda_\alpha\rangle}{\lambda_0 - \lambda_j}$로 결정됐다. 첫째 합 자기 자신 평행 성분 $\langle\lambda^\alpha\vert\dot\lambda_\alpha\rangle$은 $\vert\lambda_\alpha\rangle$의 노름/위상 자유도로 0으로 설정한다 (§4와 같은 정규화). 첫째 합 비대각 성분 $\langle\lambda^\beta\vert\dot\lambda_\alpha\rangle$ ($\beta \neq \alpha$)은 4)에서 정보 상쇄로 1차 식에서 결정되지 않으며 2차 식이 필요하다.

A형으로서 1차 식 결정 부분만 적으면

$$
\vert\dot\lambda_\alpha\rangle\big|_{\text{1차 결정}} = \sum_j\frac{\langle\lambda^j\vert\dot A\vert\lambda_\alpha\rangle}{\lambda_0 - \lambda_j}\,\vert\lambda_j\rangle
$$

이며 완전한 표현은 아니다 (첫째 합 비대각 성분 누락). 우변 $\vert\lambda_\alpha\rangle$는 7)의 $M\mathbf{c}_\alpha = \dot\lambda_\alpha\mathbf{c}_\alpha$에서 결정된다.

**9) B형: 완전 표현.**

8)에서 미결정으로 남은 비대각 퇴화 성분 $a_{\beta\alpha} \equiv \langle\lambda^\beta\vert\dot\lambda_\alpha\rangle$ ($\beta \neq \alpha$)을 결정한다. 1차 식에서 결정되지 않았으므로 2차 식이 필요하다.

고유값 식 양변을 $\tau$로 두 번 미분하면

$$
\ddot A\vert\lambda_\alpha\rangle + 2\dot A\vert\dot\lambda_\alpha\rangle + \hat A\vert\ddot\lambda_\alpha\rangle = \ddot\lambda_\alpha\vert\lambda_\alpha\rangle + 2\dot\lambda_\alpha\vert\dot\lambda_\alpha\rangle + \lambda_0\vert\ddot\lambda_\alpha\rangle \quad (\star\star)
$$

이다. 양변에 $\langle\lambda^\beta\vert$ ($\beta \neq \alpha$, 둘 다 퇴화 인덱스)를 곱한다. $\langle\lambda^\beta\vert\hat A = \lambda_0\langle\lambda^\beta\vert$, $\langle\lambda^\beta\vert\lambda_\alpha\rangle = 0$이므로 $\ddot\lambda_\alpha$ 항이 사라지고 $\lambda_0$ 항이 상쇄되어

$$
\langle\lambda^\beta\vert\ddot A\vert\lambda_\alpha\rangle + 2\langle\lambda^\beta\vert\dot A\vert\dot\lambda_\alpha\rangle = 2\dot\lambda_\alpha a_{\beta\alpha}
$$

가 남는다. 좌변 둘째 항에 $\vert\dot\lambda_\alpha\rangle = \sum_\gamma a_{\gamma\alpha}\vert\lambda_\gamma\rangle + \sum_j b_{j\alpha}\vert\lambda_j\rangle$ ($b_{j\alpha}$는 3) 결과)을 대입하면

$$
\langle\lambda^\beta\vert\dot A\vert\dot\lambda_\alpha\rangle = \sum_\gamma a_{\gamma\alpha}\langle\lambda^\beta\vert\dot A\vert\lambda_\gamma\rangle + \sum_j b_{j\alpha}\langle\lambda^\beta\vert\dot A\vert\lambda_j\rangle
$$

4)의 조건 $\langle\lambda^\beta\vert\dot A\vert\lambda_\gamma\rangle = \dot\lambda_\gamma\delta^\beta_\gamma$에 의해 첫째 합이 $a_{\beta\alpha}\dot\lambda_\beta$가 된다.

$$
\langle\lambda^\beta\vert\dot A\vert\dot\lambda_\alpha\rangle = a_{\beta\alpha}\dot\lambda_\beta + \sum_j b_{j\alpha}\langle\lambda^\beta\vert\dot A\vert\lambda_j\rangle
$$

위 식에 대입하고 $a_{\beta\alpha}$에 대해 정리하면

$$
a_{\beta\alpha}(\dot\lambda_\alpha - \dot\lambda_\beta) = \sum_j b_{j\alpha}\langle\lambda^\beta\vert\dot A\vert\lambda_j\rangle + \frac{1}{2}\langle\lambda^\beta\vert\ddot A\vert\lambda_\alpha\rangle
$$

$b_{j\alpha} = \frac{\langle\lambda^j\vert\dot A\vert\lambda_\alpha\rangle}{\lambda_0 - \lambda_j}$ 대입, $\dot\lambda_\alpha \neq \dot\lambda_\beta$ ($M$ 고유값 비퇴화) 가정 하에

$$
a_{\beta\alpha} = \frac{1}{\dot\lambda_\alpha - \dot\lambda_\beta}\left[\sum_j\frac{\langle\lambda^\beta\vert\dot A\vert\lambda_j\rangle\langle\lambda^j\vert\dot A\vert\lambda_\alpha\rangle}{\lambda_0 - \lambda_j} + \frac{1}{2}\langle\lambda^\beta\vert\ddot A\vert\lambda_\alpha\rangle\right]
$$

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