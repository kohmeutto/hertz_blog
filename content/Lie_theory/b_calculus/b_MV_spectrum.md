+++
title = "(b) MV spectrum"
weight = 5
+++

### 1. 동기

앞서 단일 매개변수 행렬 $\hat{A}(\tau)$의 미분이 고유값 변화, 켓 고유벡터 변화, 브라 고유벡터 변화의 세 항으로 분해됨을 다루었다. 본 장에서는 다변수 매개변수 공간 $\tau = (\tau^1, \ldots, \tau^n)$으로 확장하여, 각 편미분 작용소 $\partial \hat{A}/\partial \tau^a$가 스펙트럼 표상 위에서 분해되는 구조를 서술한다. 단일 매개변수 유도 과정의 기계적 중복을 배제하고, 다변수 체계에서 도출되는 연산자 간의 비교환성 구조를 정립한다.

---

### 2. 다변수 스펙트럼 분해

매개변수 영역 내에서 행렬 $\hat{A}(\tau)$가 비축퇴 고유값을 가지며, 고유값과 매개변수에 대해 유한 차수까지 매끄럽게 변화한다고 가정한다. 각 매개변수 지점 $\tau$에서 스펙트럼 분해는 다음과 같이 정의된다.

**1) 다변수 이산 스팩트럼**

$$
\hat{A}(\tau) = \sum_i \lambda_i(\tau)\, |\lambda_i(\tau)\rangle \langle \lambda_i^i(\tau)|
$$

**2) 다변수 연속 스팩트럼**

$$
\hat{A}(\tau) = \int du\; c(\lambda, \tau)\, |\lambda(\tau)\rangle \langle \lambda^d(\tau)|
$$

---

### 3. 스펙트럼의 편미분

매개변수 공간의 각 성분 $\tau^a$에 대한 편미분 연산은 다른 매개변수 성분을 고정하므로, 앞서 도출된 단일 매개변수 미분 규칙이 선형성에 의해 동일하게 적용된다. 편미분 분해의 결과식은 다음과 같다.

**1) 다변수 이산 스팩트럼**
$$
\frac{\partial \hat{A}}{\partial \tau^a} = \sum_i \left[ \frac{\partial \lambda_i}{\partial \tau^a}\, |v_i\rangle \langle v^i| + \lambda_i \frac{\partial |v_i\rangle}{\partial \tau^a} \langle v^i| + \lambda_i |v_i\rangle \frac{\partial \langle v^i|}{\partial \tau^a} \right]
$$

비대각 성분에 대한 투영을 통해 도출되는 헬만-파인만 정리와 고유벡터의 1차 보정식 또한 단일 매개변수 공식의 편미분 확장 형태를 띤다. 다변수 고유값 편미분은 다음과 같다.

$$
\frac{\partial \lambda_i}{\partial \tau^a} = \langle v^i | \frac{\partial \hat{A}}{\partial \tau^a} | v_i \rangle
$$

고유벡터의 1차 보정식은 다음과 같이 결정된다.

$$
\frac{\partial |v_i\rangle}{\partial \tau^a} = \sum_{j \neq i} \frac{\langle v^j | \partial \hat{A} / \partial \tau^a | v_i \rangle}{\lambda_i - \lambda_j} |v_j\rangle
$$

**2) 다변수 연속 스팩트럼**

$$
\frac{\partial \hat{A}}{\partial \tau^a} = \int du \left[ \frac{\partial \lambda(u, \tau)}{\partial \tau^a}\, |\lambda\rangle \langle u^d| + \lambda(u, \tau) \frac{\partial |\lambda\rangle}{\partial \tau^a} \langle u^d| + \lambda(u, \tau) |\lambda\rangle \frac{\partial \langle u^d|}{\partial \tau^a} \right]
$$

연속 스펙트럼 표상에서의 헬만-파인만 정리는 고유상태 투영을 통해 다음과 같이 성분별로 도출된다.

$$
\frac{\partial \lambda(u, \tau)}{\partial \tau^a} = \langle u^d | \frac{\partial \hat{A}}{\partial \tau^a} | \lambda \rangle
$$

고유벡터의 1차 보정식은 다음과 같이 결정된다.

---


### 3. 자유 입자 섭동과 지연 그린 함수 표상

다변수 연속 스펙트럼 섭동 이론의 해석적 구조를 확인하기 위해 1차원 공간 행렬학에 기반한 자유 입자 해밀토니안을 상정한다. 계수 $\tau^1$과 $\tau^2$로 제어되는 두 개의 국소 포텐셜 미분 연산자를 도입한다.

$$
\hat{A}(\tau^1, \tau^2) = -\frac{d^2}{dx^2} + \tau^1 V_1(x) + \tau^2 V_2(x)
$$

기준점 $(\tau^1, \tau^2) = (0, 0)$에서 연산자는 자유 입자 시스템 $\hat{A}(0,0) = -d^2/dx^2$으로 환원된다. 고유값 방정식 $-d^2/dx^2 \psi_\lambda(x) = \lambda \psi_\lambda(x)$를 풀면 양의 실수 영역에서 연속 스펙트럼 $c(\lambda) = \lambda^2$을 얻는다. 연속 인덱스 $u$에 의해 매개변수화되는 고유함수는 공간 기저에서 다음과 같이 평면파 형태로 결정된다.

$$
\langle x | \lambda \rangle = \psi_\lambda(x) = \frac{1}{\sqrt{2\pi}} e^{iux}
$$

공간 영역 전역에 대한 적분을 통해 디랙 델타 정규화 조건이 엄밀하게 성립함을 확인한다.

$$
\langle \lambda' | \lambda \rangle = \int_{-\infty}^{\infty} dx \psi_{\lambda'}^*(x) \psi_\lambda(x) = \frac{1}{2\pi} \int_{-\infty}^{\infty} dx e^{i(u - \lambda')x} = \delta(u - \lambda')
$$

매개변수에 대한 편미분 작용소는 각각 외장 포텐셜 함수로 직결된다.

$$
\frac{\partial \hat{A}}{\partial \tau^1} = V_1(x), \qquad \frac{\partial \hat{A}}{\partial \tau^2} = V_2(x)
$$

헬만-파인만 정리에 따라 1차 고유값 변화율은 공간 기저 위에서의 적분으로 평가된다.

$$
\frac{\partial c(\lambda)}{\partial \tau^a} = \langle u | V_a | \lambda \rangle = \int_{-\infty}^{\infty} dx \psi_u^*(x) V_a(x) \psi_\lambda(x) = \frac{1}{2\pi} \int_{-\infty}^{\infty} dx V_a(x)
$$

고유벡터의 매개변수 방향 변화율을 기술하는 섭동 공식은 비대각 투영 성분들의 연속 적분 형태로 표현된다.

$$
\frac{\partial |\lambda\rangle}{\partial \tau^a}\bigg|_{\tau=0} = \int_{-\infty}^{\infty} d\lambda'\; \frac{\langle \lambda' | V_a | \lambda \rangle}{\lambda^2 - (\lambda')^2}\, |\lambda'\rangle
$$

피적분 함수의 분모 $\lambda^2 - (\lambda')^2$은 적분 경로 상의 $\lambda' = \lambda$ (전방 산란) 및 $\lambda' = -\lambda$ (후방 산란) 지점에서 0이 되며, 이로 인해 대수적 특이점이 발생하여 적분값이 정의되지 않는다. 인과율을 충족하는 물리적 해를 도출하기 위해 복소 평면 위에서 적분 경로를 이동시키는 $+i\varepsilon$ 처방(정칙화)을 도입한다.

$$
\frac{\partial |\lambda\rangle}{\partial \tau^a} = \lim_{\varepsilon \to 0^+} \int_{-\infty}^{\infty} d\lambda'\; \frac{\langle \lambda' | V_a | \lambda \rangle}{\lambda^2 - (\lambda')^2 + i\varepsilon}\, |\lambda'\rangle
$$

이 공식을 공간 기저(위치 표현)로 투영하여 1차 파동함수 보정항 $\delta \psi_\lambda(x)$를 재구성한다. 내적 $\langle \lambda' | V_a | \lambda \rangle$을 위치 공간 적분 $\int dy \psi_{\lambda'}^*(y) V_a(y) \psi_\lambda(y)$로 풀어서 대입한다.

$$
\delta \psi_\lambda(x) = \int_{-\infty}^{\infty} d\lambda' \frac{\int_{-\infty}^{\infty} dy \psi_{\lambda'}^*(y) V_a(y) \psi_\lambda(y)}{\lambda^2 - (\lambda')^2 + i\varepsilon} \psi_{\lambda'}(x)
$$

푸비니 정리에 의해 적분 순서를 $dy$와 $d\lambda'$ 사이에서 교환하여 적분핵(Kernel)을 분리한다.

$$
\delta \psi_\lambda(x) = \int_{-\infty}^{\infty} dy \left[ \int_{-\infty}^{\infty} d\lambda' \frac{\psi_{\lambda'}(x) \psi_{\lambda'}^*(y)}{\lambda^2 - (\lambda')^2 + i\varepsilon} \right] V_a(y) \psi_\lambda(y)
$$

대괄호 안의 항은 정확히 연속 스펙트럼 고유상태들의 외적분으로 정의되는 자유 입자의 지연 그린 함수(Retarded Green's function) 공간 표상과 일치한다.

$$
G_0^R(x, y; \lambda^2) = \int_{-\infty}^{\infty} d\lambda' \frac{\psi_{\lambda'}(x) \psi_{\lambda'}^*(y)}{\lambda^2 - (\lambda')^2 + i\varepsilon}
$$

다변수 연속 스펙트럼 환경에서 각 매개변수 축으로의 파동함수 섭동은 자유 입자 지연 그린 함수와 교란 포텐셜의 합성곱(Convolution)으로 환원된다.