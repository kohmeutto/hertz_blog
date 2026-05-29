+++
title = "(b) MV continuous spectrum"
weight = 6
+++

---

### 1. 다변수 연속 스펙트럼 분해 가정

연산자 $A(\tau)$가 매개변수 영역 내에서 연속 스펙트럼을 지니며, 고유값 함수 $\lambda(u, \tau)$와 고유벡터 $|u(\tau)\rangle$, $\langle u^d(\tau)|$가 매개변수 공간과 연속 인덱스 $u$ 전역에서 매끄럽게 변화한다고 가정한다. 임의의 매개변수 지점 $\tau$에서 스펙트럼 분해식은 다음과 같이 정의된다.

$$
A(\tau) = \int du\; \lambda(u, \tau)\, |u(\tau)\rangle \langle u^d(\tau)|
$$

연속 직교 관계는 모든 매개변수 지점에서 $\langle u^d(\tau) | u'(\tau) \rangle = \delta(u - u')$를 만족한다.

---

### 2. 편미분의 선형 확장 및 헬만-파인만 정리

단일 매개변수 연속 스펙트럼 공식의 선형 확장에 따라, 각 매개변수 성분 $\tau^a$에 대한 1계 편미분 공식은 유도 과정의 중복을 배제하고 아래와 같이 정리된다.

$$
\frac{\partial A}{\partial \tau^a} = \int du \left[ \frac{\partial \lambda(u, \tau)}{\partial \tau^a}\, |u\rangle \langle u^d| + \lambda(u, \tau) \frac{\partial |u\rangle}{\partial \tau^a} \langle u^d| + \lambda(u, \tau) |u\rangle \frac{\partial \langle u^d|}{\partial \tau^a} \right]
$$

연속 스펙트럼 표상에서의 헬만-파인만 정리는 고유상태 투영을 통해 다음과 같이 성분별로 도출된다.

$$
\frac{\partial \lambda(u, \tau)}{\partial \tau^a} = \langle u^d | \frac{\partial A}{\partial \tau^a} | u \rangle
$$

---

### 3. 자유 입자 섭동과 지연 그린 함수 표상

다변수 연속 스펙트럼 섭동 이론의 해석적 구조를 확인하기 위해 1차원 공간 행렬학에 기반한 자유 입자 해밀토니안을 상정한다. 계수 $\tau^1$과 $\tau^2$로 제어되는 두 개의 국소 포텐셜 미분 연산자를 도입한다.

$$
A(\tau^1, \tau^2) = -\frac{d^2}{dx^2} + \tau^1 V_1(x) + \tau^2 V_2(x)
$$

기준점 $(\tau^1, \tau^2) = (0, 0)$에서 연산자는 자유 입자 시스템 $A(0,0) = -d^2/dx^2$으로 환원된다. 고유값 방정식 $-d^2/dx^2 \psi_u(x) = \lambda \psi_u(x)$를 풀면 양의 실수 영역에서 연속 스펙트럼 $\lambda(u) = u^2$을 얻는다. 연속 인덱스 $u$에 의해 매개변수화되는 고유함수는 공간 기저에서 다음과 같이 평면파 형태로 결정된다.

$$
\langle x | u \rangle = \psi_u(x) = \frac{1}{\sqrt{2\pi}} e^{iux}
$$

공간 영역 전역에 대한 적분을 통해 디랙 델타 정규화 조건이 엄밀하게 성립함을 확인한다.

$$
\langle u' | u \rangle = \int_{-\infty}^{\infty} dx \psi_{u'}^*(x) \psi_u(x) = \frac{1}{2\pi} \int_{-\infty}^{\infty} dx e^{i(u - u')x} = \delta(u - u')
$$

매개변수에 대한 편미분 작용소는 각각 외장 포텐셜 함수로 직결된다.

$$
\frac{\partial A}{\partial \tau^1} = V_1(x), \qquad \frac{\partial A}{\partial \tau^2} = V_2(x)
$$

헬만-파인만 정리에 따라 1차 고유값 변화율은 공간 기저 위에서의 적분으로 평가된다.

$$
\frac{\partial \lambda(u)}{\partial \tau^a} = \langle u | V_a | u \rangle = \int_{-\infty}^{\infty} dx \psi_u^*(x) V_a(x) \psi_u(x) = \frac{1}{2\pi} \int_{-\infty}^{\infty} dx V_a(x)
$$

고유벡터의 매개변수 방향 변화율을 기술하는 섭동 공식은 비대각 투영 성분들의 연속 적분 형태로 표현된다.

$$
\frac{\partial |u\rangle}{\partial \tau^a}\bigg|_{\tau=0} = \int_{-\infty}^{\infty} du'\; \frac{\langle u' | V_a | u \rangle}{u^2 - (u')^2}\, |u'\rangle
$$

피적분 함수의 분모 $u^2 - (u')^2$은 적분 경로 상의 $u' = u$ (전방 산란) 및 $u' = -u$ (후방 산란) 지점에서 0이 되며, 이로 인해 대수적 특이점이 발생하여 적분값이 정의되지 않는다. 인과율을 충족하는 물리적 해를 도출하기 위해 복소 평면 위에서 적분 경로를 이동시키는 $+i\varepsilon$ 처방(정칙화)을 도입한다.

$$
\frac{\partial |u\rangle}{\partial \tau^a} = \lim_{\varepsilon \to 0^+} \int_{-\infty}^{\infty} du'\; \frac{\langle u' | V_a | u \rangle}{u^2 - (u')^2 + i\varepsilon}\, |u'\rangle
$$

이 공식을 공간 기저(위치 표현)로 투영하여 1차 파동함수 보정항 $\delta \psi_u(x)$를 재구성한다. 내적 $\langle u' | V_a | u \rangle$을 위치 공간 적분 $\int dy \psi_{u'}^*(y) V_a(y) \psi_u(y)$로 풀어서 대입한다.

$$
\delta \psi_u(x) = \int_{-\infty}^{\infty} du' \frac{\int_{-\infty}^{\infty} dy \psi_{u'}^*(y) V_a(y) \psi_u(y)}{u^2 - (u')^2 + i\varepsilon} \psi_{u'}(x)
$$

푸비니 정리에 의해 적분 순서를 $dy$와 $du'$ 사이에서 교환하여 적분핵(Kernel)을 분리한다.

$$
\delta \psi_u(x) = \int_{-\infty}^{\infty} dy \left[ \int_{-\infty}^{\infty} du' \frac{\psi_{u'}(x) \psi_{u'}^*(y)}{u^2 - (u')^2 + i\varepsilon} \right] V_a(y) \psi_u(y)
$$

대괄호 안의 항은 정확히 연속 스펙트럼 고유상태들의 외적분으로 정의되는 자유 입자의 지연 그린 함수(Retarded Green's function) 공간 표상과 일치한다.

$$
G_0^R(x, y; u^2) = \int_{-\infty}^{\infty} du' \frac{\psi_{u'}(x) \psi_{u'}^*(y)}{u^2 - (u')^2 + i\varepsilon}
$$

다변수 연속 스펙트럼 환경에서 각 매개변수 축으로의 파동함수 섭동은 자유 입자 지연 그린 함수와 교란 포텐셜의 합성곱(Convolution)으로 환원된다.