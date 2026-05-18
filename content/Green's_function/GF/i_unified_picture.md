+++
title = "(i) Unified picture"
weight = 3
+++

---

### 1. 세 객체의 같은 구조

본 챕터에서 다음 세 객체를 만났다.

| 객체 | 어디서 | 의미 |
|---|---|---|
| $\delta(u-u')$ | 문서 1 §2 | 정의 방정식의 우변 |
| $A(u,u')$ | 문서 1 §1 | 연산자의 적분 커널 |
| $G(u,u')$ | 문서 1-2 | 역연산자의 적분 커널 (그린함수) |

언뜻 보기에 이 셋은 완전히 다른 객체이다. 그러나 스펙트럼 표현으로 본 모습은 놀랍도록 유사하다.

**1) 항등 연산자의 커널: 델타 함수**

b_operator.md §3-4의 항등 연산자 분해 $\hat{I} = \sum_i |\lambda_i\rangle\langle\lambda^i|$ 을 표현 기저에서 본다.

$$
\delta(u-u') = \langle u^d|\hat{I}|u'\rangle = \sum_i \psi_i(u)\,\psi^i(u')
$$

**2) 연산자의 커널**

b_spectral_theory.md §1의 스펙트럼 분해 $\hat{A} = \sum_i \lambda_i|\lambda_i\rangle\langle\lambda^i|$ 의 표현 기저 형태:

$$
A(u,u') = \langle u^d|\hat{A}|u'\rangle = \sum_i \lambda_i\,\psi_i(u)\,\psi^i(u')
$$

**3) 역연산자의 커널: 그린함수**

본 챕터 문서 2의 결과:

$$
G(u,u') = \langle u^d|\hat{A}^{-1}|u'\rangle = \sum_i \frac{\psi_i(u)\,\psi^i(u')}{\lambda_i}
$$

세 객체가 모두 같은 합 구조 ($\sum_i \cdots\,\psi_i(u)\,\psi^i(u')$) 를 가지며, **$\lambda_i$ 의 가중치만 다르다**.

---

### 2. λ-멱으로 본 통일

§1의 세 표현을 나란히 놓고 $\lambda$ 의 멱($n$)을 명시적으로 추출하면:

$$
\delta(u-u') = \sum_i \lambda_i^{0}\,\psi_i(u)\,\psi^i(u') \quad (n = 0)
$$

$$
A(u,u') = \sum_i \lambda_i^{+1}\,\psi_i(u)\,\psi^i(u') \quad (n = +1)
$$

$$
G(u,u') = \sum_i \lambda_i^{-1}\,\psi_i(u)\,\psi^i(u') \quad (n = -1)
$$

이를 한 식으로 통합하면, 임의의 정수 $n$ 에 대해

$$
\langle u^d|\hat{A}^n|u'\rangle = \sum_i \lambda_i^n\,\psi_i(u)\,\psi^i(u')
$$

이다. 이는 b_spectral_theory.md §4에서 도출한 $\hat{A}^n = \sum_i \lambda_i^n|\lambda_i\rangle\langle\lambda^i|$ 의 표현 기저 형태일 뿐이다.

특별한 경우들:

| $n$ | $\hat{A}^n$의 커널 | 객체 이름 |
|---|---|---|
| $-1$ | $G(u,u')$ | 그린함수 |
| $0$ | $\delta(u-u')$ | 델타 함수 |
| $+1$ | $A(u,u')$ | 연산자 자체 |
| $+2$ | $A^2(u,u')$ | $\hat{A}$ 의 제곱 |
| $\vdots$ | $\vdots$ | $\vdots$ |

세 (그리고 무한히 많은) 객체가 **같은 합 구조의 다른 멱**일 뿐이다. **그린함수는 이 일반화 사다리의 $n = -1$ 자리에 위치한 객체이다.**

연속 스펙트럼의 경우 합이 적분으로 바뀔 뿐, 구조는 같다.

$$
\langle u^d|\hat{A}^n|u'\rangle = \int d\lambda\,\lambda^n\,\psi_\lambda(u)\,\psi^\lambda(u')
$$

혼합 스펙트럼이면 두 부분 모두 등장한다.

---

### 3. 이퀄라이저 비유의 확장

b_spectral_theory.md §2의 오디오 이퀄라이저 비유를 확장하자.

- **시스템(연산자)**: 신호에 작용하는 필터
- **고유함수 $|\lambda_i\rangle$**: 시스템의 "채널" (예: 순수 주파수 성분)
- **고유값 $\lambda_i$**: 각 채널의 "볼륨 노브" 값

이 비유 안에서 본 챕터의 세 객체는 다음과 같이 해석된다.

| 객체 | 채널 $i$의 볼륨 | 의미 |
|---|---|---|
| $\hat{I}$ ($\delta$) | $1 = \lambda_i^0$ | **신호 통과** (변하지 않음) |
| $\hat{A}$ | $\lambda_i$ | **신호 처리** (필터 적용) |
| $\hat{A}^{-1}$ ($G$) | $1/\lambda_i$ | **신호 되돌림** ($\hat{A}$ 의 역작용) |
| $\hat{A}^2$ | $\lambda_i^2$ | 두 번 적용 |
| $\hat{A}^{1/2}$ | $\sqrt{\lambda_i}$ | 절반 적용 |

핵심 통일: **같은 채널들 ($|\lambda_i\rangle$) 을 가진 같은 시스템에서, 채널별 볼륨을 어떻게 설정하느냐의 차이**일 뿐이다.

- 모든 채널 볼륨을 $1$ 로 → 그대로 통과 = 항등 = 델타
- 각 채널 볼륨을 $\lambda_i$ 로 → 원래 시스템 = $\hat{A}$
- 각 채널 볼륨을 $1/\lambda_i$ 로 → 역작용 = 그린함수

---

### 4. Functional calculus 로의 확장

§2의 멱 $\lambda^n$ 패턴은 임의의 함수로 일반화된다. 임의의 함수 $f: \mathbb{C} \to \mathbb{C}$ 에 대해, **함수 캘큘러스(functional calculus)** 가 다음과 같이 정의된다.

$$
f(\hat{A}) = \sum_i f(\lambda_i)\,|\lambda_i\rangle\langle\lambda^i| \quad \text{또는} \quad f(\hat{A}) = \int d\lambda\,f(\lambda)\,|\lambda\rangle\langle\lambda^d|
$$

본 챕터의 통일된 그림은 이의 특수한 경우들 ($f(\lambda) = \lambda^0, \lambda^{+1}, \lambda^{-1}$) 이다.

| $f(\lambda)$ | $f(\hat{A})$ | 객체 / 용도 |
|---|---|---|
| $1$ | $\hat{I}$ | 항등 (델타 함수) |
| $\lambda$ | $\hat{A}$ | 원래 연산자 |
| $1/\lambda$ | $\hat{A}^{-1}$ | 역연산자 (**그린함수**) |
| $\lambda^n$ | $\hat{A}^n$ | $n$-번째 거듭제곱 |
| $e^{-\beta\lambda}$ | $e^{-\beta\hat{A}}$ | 통계역학 분배 연산자, 양자 시간 진화 |
| $1/(\lambda - z)$ | $(\hat{A}-z\hat{I})^{-1}$ | **resolvent** (다음 문서 4) |
| $1/(\lambda - z \mp i\eta)$ | $(\hat{A}-z\hat{I}\mp i\eta)^{-1}$ | **retarded/advanced 그린함수** (NEGF 챕터) |
| $\text{sign}(\lambda)$ | $\text{sign}(\hat{A})$ | 부호 연산자 |

함수 캘큘러스의 관점에서 본다면, **그린함수는 단지 함수 $f(\lambda) = 1/\lambda$ 를 $\hat{A}$ 에 적용한 결과**이다. 

이 일반화 시야가 본 챕터를 NEGF 챕터로 연결하는 다리이다. 다음 문서 4에서는 $f(\lambda) = 1/(\lambda - z)$ 의 resolvent 를, NEGF 챕터에서는 $f(\lambda) = 1/(\lambda - z \mp i\eta)$ 의 retarded/advanced 그린함수를 다룬다. 모두 같은 함수 캘큘러스 프레임의 일원이다.

---

**example1)** 2×2 허미션 행렬에서의 통일 확인

문서 2 example1 의 같은 행렬을 재사용한다.

$$
A = \begin{bmatrix} 2 & 1 \\ 1 & 2 \end{bmatrix}, \quad \lambda_1 = 1,\ \lambda_2 = 3
$$

고유벡터 (정규직교):

$$
|\lambda_1\rangle = \frac{1}{\sqrt 2}\begin{bmatrix} 1 \\ -1 \end{bmatrix}, \quad
|\lambda_2\rangle = \frac{1}{\sqrt 2}\begin{bmatrix} 1 \\ 1 \end{bmatrix}
$$

sol)

(1) 사영 연산자

$$
P_1 = |\lambda_1\rangle\langle\lambda_1| = \frac{1}{2}\begin{bmatrix} 1 & -1 \\ -1 & 1 \end{bmatrix}, \quad
P_2 = |\lambda_2\rangle\langle\lambda_2| = \frac{1}{2}\begin{bmatrix} 1 & 1 \\ 1 & 1 \end{bmatrix}
$$

완비성 확인: $P_1 + P_2 = I$ ✓

(2) 함수 캘큘러스로 객체들 구성

§2의 공식 $\hat{A}^n = \lambda_1^n P_1 + \lambda_2^n P_2$ 를 사용한다.

| $n$ | $\lambda_1^n P_1 + \lambda_2^n P_2$ | 결과 |
|---|---|---|
| $0$ | $1\cdot P_1 + 1\cdot P_2$ | $\begin{bmatrix}1 & 0\\0 & 1\end{bmatrix} = I\ (\delta)$ |
| $+1$ | $1\cdot P_1 + 3\cdot P_2$ | $\begin{bmatrix}2 & 1\\1 & 2\end{bmatrix} = A$ |
| $-1$ | $1\cdot P_1 + \frac{1}{3}\cdot P_2$ | $\begin{bmatrix}2/3 & -1/3\\-1/3 & 2/3\end{bmatrix} = G\ (\text{그린행렬})$ |
| $+2$ | $1\cdot P_1 + 9\cdot P_2$ | $\begin{bmatrix}5 & 4\\4 & 5\end{bmatrix} = A^2$ |

각 행은 같은 $P_1, P_2$ 로 구성되며, 단지 $\lambda^n$ 가중치만 다르다. **세 핵심 객체 ($I, A, G$) 가 같은 스펙트럼 분해의 세 멱 ($n = 0, +1, -1$) 임을 명시적으로 확인한다.**

(3) 연속 케이스 (1차원 디리클레 박스)

문서 2 example2 의 설정 ($\hat{A} = -d^2/dx^2$ on $[0,L]$, $\psi_n(x) = \sqrt{2/L}\sin(n\pi x/L)$, $\lambda_n = (n\pi/L)^2$) 에 본 통일을 적용:

**$n = 0$ (항등, 델타 함수)**

$$
\delta(x-x') = \sum_{n=1}^\infty \psi_n(x)\,\psi_n(x') = \frac{2}{L}\sum_{n=1}^\infty \sin\!\left(\frac{n\pi x}{L}\right)\sin\!\left(\frac{n\pi x'}{L}\right)
$$

이는 사인 급수 완비성 (Parseval-type identity).

**$n = -1$ (그린함수)**

$$
G(x,x') = \sum_{n=1}^\infty \frac{\psi_n(x)\,\psi_n(x')}{\lambda_n} = \frac{2L}{\pi^2}\sum_{n=1}^\infty \frac{\sin(n\pi x/L)\,\sin(n\pi x'/L)}{n^2}
$$

문서 2 example2에서 본 형태.

**$n = +1$ (연산자 자체)**

$$
A(x,x') = \sum_{n=1}^\infty \lambda_n\,\psi_n(x)\,\psi_n(x') = -\partial_x^2\,\delta(x-x')
$$

형식적 합은 분포 의미에서만 수렴하며, **$\hat{A} = -d^2/dx^2$ 가 위치 기저에서 본 미분 연산자의 분포적 표현**이다.

같은 사인 함수들 ($\psi_n$) 로 모든 객체가 구성되며, 단지 $\lambda_n = (n\pi/L)^2$ 의 멱만 다르다는 점이 명확히 드러난다.
