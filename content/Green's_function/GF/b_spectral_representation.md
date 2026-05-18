+++
title = "(b) Spectral representation"
weight = 2
+++

---

### 1. 왜 스펙트럼 표현인가

앞 문서에서는 일반 연속 기저 $|u\rangle$ 에서 그린함수의 정의

$$
G(u,u') = \langle u^d|\hat{A}^{-1}|u'\rangle
$$

를 얻었다. 본 문서에서는 추가로 $\hat{A}$ 의 **고유기저** $\{|\lambda_i\rangle\}$ 를 도입한다. 자연스럽게 묻게 되는 질문은: **왜 추가 기저가 필요한가?**

답은 단순하다.

**일반 기저 $|u\rangle$ 에서 $\hat{A}^{-1}$ 의 적분 커널을 직접 구하는 것은 어렵지만, 고유기저 $|\lambda_i\rangle$ 에서는 자명하다.**

b_spectral_theory.md 에서 확인한 대로, 연산자의 스펙트럼 분해는 다음과 같다.

$$
\hat{A} = \sum_i \lambda_i\,|\lambda_i\rangle\langle\lambda^i|
$$

고유기저에서 $\hat{A}$ 는 대각이므로, 역연산자도 자명하게

$$
\hat{A}^{-1} = \sum_i \frac{1}{\lambda_i}\,|\lambda_i\rangle\langle\lambda^i|
$$

이다. 즉, **고유값 문제를 풀 수만 있다면 $\hat{A}^{-1}$ 은 즉시 얻어진다.**

따라서 그린함수 계산에서 두 기저가 자연스럽게 등장한다.

- **표현 기저** $|u\rangle$ : 그린함수를 $G(u,u')$ 로 읽고자 하는 기저 (위치, 운동량 등)
- **계산 기저** $|\lambda_i\rangle$ : $\hat{A}^{-1}$ 이 자명한 고유기저

**스펙트럼 표현은 이 두 기저 사이의 다리이다.** 표현 기저에서 그린함수를 읽으면서, 계산은 고유기저에서 수행한다. 두 기저 사이의 변환은 두 사영 $\langle u^d|\lambda_i\rangle$ 와 $\langle\lambda^i|u'\rangle$ 가 담당한다.

이 발상을 구체화하면, 그린함수는 다음과 같이 표현된다 (이산 스펙트럼의 경우).

$$
G(u,u') = \sum_i \frac{\psi_i(u)\,\psi^i(u')}{\lambda_i}
$$

여기서 $\psi_i(u) = \langle u^d|\lambda_i\rangle$ 는 **표현 기저에서 본 $i$ 번째 고유함수** 이다. 이 추상적 정의가 구체적으로 무엇을 뜻하는지는 본 문서의 example1 (이산 표현 기저) 과 example2 (연속 표현 기저) 에서 명확히 드러난다. 다음 절들에서 이산/연속/혼합 케이스로 구체화한다.

(아래에서는 $\hat{A}$ 의 고유벡터가 완비함을 가정한다. 완비성 조건은 b_spectral_theory.md §3 참조.)

---

### 2. 이산 스펙트럼

$\hat{A}$ 의 스펙트럼이 이산적인 경우, 고유값과 고유벡터 집합 $\{(\lambda_i, |\lambda_i\rangle)\}$ 이 다음을 만족한다.

$$
\hat{A}|\lambda_i\rangle = \lambda_i|\lambda_i\rangle, \quad \langle\lambda^i|\lambda_j\rangle = \delta^i_j
$$

이 때 그린함수는 다음과 같이 표현된다.

$$
G(u,u') = \sum_i \frac{\psi_i(u)\,\psi^i(u')}{\lambda_i}
$$

여기서

$$
\psi_i(u) := \langle u^d|\lambda_i\rangle, \quad \psi^i(u') := \langle\lambda^i|u'\rangle
$$

는 각각 표현 기저에서 본 **고유함수** 와 **쌍대 고유함수** 이다. 표현 기저가 이산이면 성분(숫자)으로, 연속이면 함수의 값으로 구체화된다 (example1, example2 참조).

proof)

스펙트럼 분해 형태의 $\hat{A}^{-1}$ 을 그린함수 정의에 대입한다.

$$
G(u,u') = \langle u^d|\hat{A}^{-1}|u'\rangle = \langle u^d|\left(\sum_i \frac{|\lambda_i\rangle\langle\lambda^i|}{\lambda_i}\right)|u'\rangle
$$

브라켓의 선형성에 의해

$$
= \sum_i \frac{\langle u^d|\lambda_i\rangle\langle\lambda^i|u'\rangle}{\lambda_i}
= \sum_i \frac{\psi_i(u)\,\psi^i(u')}{\lambda_i}
$$

이다.

---

### 3. 연속 스펙트럼

$\hat{A}$ 의 스펙트럼이 연속적인 경우 (예: 자유 입자의 운동 에너지 연산자, 무한 영역의 미분 연산자 등), 고유값/고유함수 집합은 연속 파라미터 $\lambda$ 로 인덱싱된다.

$$
\hat{A}|\lambda\rangle = \lambda|\lambda\rangle, \quad \langle\lambda^d|\lambda'\rangle = \delta(\lambda-\lambda')
$$

이 때 합 대신 적분으로 표현된다.

$$
G(u,u') = \int d\lambda\,\frac{\psi_\lambda(u)\,\psi^\lambda(u')}{\lambda}
$$

여기서

$$
\psi_\lambda(u) := \langle u^d|\lambda\rangle, \quad \psi^\lambda(u') := \langle\lambda^d|u'\rangle
$$

이다.

proof)

연속 스펙트럼 분해된 $\hat{A}^{-1}$ 은

$$
\hat{A}^{-1} = \int d\lambda\,\frac{|\lambda\rangle\langle\lambda^d|}{\lambda}
$$

이다. 그린함수 정의에 대입하면

$$
G(u,u') = \langle u^d|\hat{A}^{-1}|u'\rangle 
= \int d\lambda\,\frac{\langle u^d|\lambda\rangle\langle\lambda^d|u'\rangle}{\lambda}
= \int d\lambda\,\frac{\psi_\lambda(u)\,\psi^\lambda(u')}{\lambda}
$$

이다.

**주의: 0이 스펙트럼에 포함되는 경우**

만약 $0 \in \sigma(\hat{A})$ 이면 ($\lambda=0$ 이 스펙트럼에 포함되면), 위 적분의 피적분함수가 발산하여 그린함수가 정규(regular) 의미에서 존재하지 않는다. 이 경우 **resolvent** $\hat{R}(z) = (\hat{A}-z\hat{I})^{-1}$ 또는 일반화된 그린함수의 도입이 필요하다. 자세한 처리는 문서 4 (존재성과 성질) 에서 다룬다.

---

### 4. 혼합 스펙트럼

일반적인 물리 시스템에서는 이산 스펙트럼과 연속 스펙트럼이 공존한다. 대표적인 예는 양자역학의 수소 원자 해밀토니안 $\hat{H}$ 이다.

- **이산 스펙트럼** : 속박 상태 (bound states) $E_n < 0$
- **연속 스펙트럼** : 산란 상태 (scattering states) $E > 0$

이 때 그린함수는 두 기여의 합으로 표현된다.

$$
G(u,u') 
= \sum_i \frac{\psi_i(u)\,\psi^i(u')}{\lambda_i} + \int d\lambda\,\frac{\psi_\lambda(u)\,\psi^\lambda(u')}{\lambda}
$$

이산 기여는 속박 상태로부터, 연속 기여는 산란 상태로부터 온다. 두 부분 모두 $\hat{A}^{-1}$ 의 완비성에 의해 자연스럽게 도출된다.

이 혼합 형태는 NEGF 챕터의 양자 수송 응용 (속박 채널 + 산란 채널) 에서 본질적인 역할을 한다.

---

### 5. 정규 연산자에서의 단순화

지금까지는 일반 연산자를 다루어왔으므로, 고유함수 $\psi_i(u)$ 와 쌍대 고유함수 $\psi^i(u')$ 가 별도로 등장하였다. 그러나 **정규 연산자 (normal operator)** 의 경우 표기가 단순해진다.

$\hat{A}$ 가 정규 연산자이면 ($[\hat{A},\hat{A}^\dagger]=0$, 특히 허미션 또는 유니타리 연산자), 고유벡터들은 정규직교화 가능하다 (b_normal_operators.md §2 참조).

$$
\langle\lambda_i|\lambda_j\rangle = \delta_{ij}
$$

이 때 쌍대 기저는 단순히 허미션 켤레와 일치한다.

$$
\langle\lambda^i| = \langle\lambda_i|
$$

따라서

$$
\psi^i(u') = \langle\lambda^i|u'\rangle = \langle\lambda_i|u'\rangle = \psi_i^*(u')
$$

가 되어, 스펙트럼 표현이 다음과 같이 단순해진다.

**1) 이산 스펙트럼 (정규 연산자)**

$$
G(u,u') = \sum_i \frac{\psi_i(u)\,\psi_i^*(u')}{\lambda_i}
$$

**2) 연속 스펙트럼 (정규 연산자)**

$$
G(u,u') = \int d\lambda\,\frac{\psi_\lambda(u)\,\psi_\lambda^*(u')}{\lambda}
$$

이 단순화된 형태가 물리 교재에서 가장 자주 마주치는 표현이다. 그러나 **비-에르미트 연산자 등 일반 연산자에서는 $\psi^i \neq \psi_i^*$ 이며**, 본래의 쌍대 형태를 유지해야 함을 명심한다.

---

**example1)** 이산 표현 기저: 2×2 허미션 행렬

$$
A = \begin{bmatrix} 2 & 1 \\ 1 & 2 \end{bmatrix}
$$

의 그린함수(역행렬)를 스펙트럼 표현으로 구하고, 직접 역행렬과 비교하라.

sol)

(1) 고유값과 고유벡터 (b_eigenvalue.md example1 참조)

$$
\lambda_1=1,\ |\lambda_1\rangle = \frac{1}{\sqrt 2}\begin{bmatrix} 1 \\ -1 \end{bmatrix}; \quad
\lambda_2=3,\ |\lambda_2\rangle = \frac{1}{\sqrt 2}\begin{bmatrix} 1 \\ 1 \end{bmatrix}
$$

여기서 표현 기저는 이산적이므로, $\psi_k(i)$ 는 $|\lambda_k\rangle$ 의 $i$ 번째 **성분(숫자)** 이다. 예를 들어 $\psi_1(1) = 1/\sqrt{2}$, $\psi_1(2) = -1/\sqrt{2}$ 이다.

행렬이 허미션(정규)이므로 §5의 단순화된 형태를 사용한다.

$$
G_{ij} = \sum_k \frac{\psi_k(i)\,\psi_k^*(j)}{\lambda_k}
$$

(2) 각 고유값 기여 계산

$\lambda_1=1$ 기여:

$$
\frac{1}{1}\cdot\frac{1}{2}\begin{bmatrix} 1 \\ -1 \end{bmatrix}\begin{bmatrix} 1 & -1 \end{bmatrix}
= \frac{1}{2}\begin{bmatrix} 1 & -1 \\ -1 & 1 \end{bmatrix}
$$

$\lambda_2=3$ 기여:

$$
\frac{1}{3}\cdot\frac{1}{2}\begin{bmatrix} 1 \\ 1 \end{bmatrix}\begin{bmatrix} 1 & 1 \end{bmatrix}
= \frac{1}{6}\begin{bmatrix} 1 & 1 \\ 1 & 1 \end{bmatrix}
$$

(3) 합산

$$
G = \frac{1}{2}\begin{bmatrix} 1 & -1 \\ -1 & 1 \end{bmatrix} + \frac{1}{6}\begin{bmatrix} 1 & 1 \\ 1 & 1 \end{bmatrix}
= \begin{bmatrix} 2/3 & -1/3 \\ -1/3 & 2/3 \end{bmatrix}
$$

(4) 직접 역행렬과 비교

$$
A^{-1} = \frac{1}{\det A}\begin{bmatrix} 2 & -1 \\ -1 & 2 \end{bmatrix} 
= \frac{1}{3}\begin{bmatrix} 2 & -1 \\ -1 & 2 \end{bmatrix} 
= \begin{bmatrix} 2/3 & -1/3 \\ -1/3 & 2/3 \end{bmatrix}
$$

스펙트럼 표현으로 얻은 $G$ 와 정확히 일치한다.

---

**example2)** 연속 표현 기저: 1차원 디리클레 박스

연속 기저에서 $\psi_n(u)$ 가 구체적으로 무엇인지 보이기 위한 표준 예제이다.

**연산자**: $\hat{A} = -\dfrac{d^2}{dx^2}$, 정의역 $[0, L]$

**경계 조건**: $\psi(0) = \psi(L) = 0$ (Dirichlet)

**표현 기저**: 위치 기저 $|x\rangle$, $x \in [0, L]$

sol)

(1) 고유값 문제 풀이

$$
-\psi_n''(x) = \lambda_n\,\psi_n(x), \quad \psi_n(0) = \psi_n(L) = 0
$$

표준 해:

$$
\psi_n(x) = \sqrt{\frac{2}{L}}\sin\left(\frac{n\pi x}{L}\right), \quad \lambda_n = \left(\frac{n\pi}{L}\right)^2, \quad n=1,2,3,\ldots
$$

여기서 $\psi_n(x) = \langle x|\lambda_n\rangle$ 가 **"표현 기저에서 본 $n$ 번째 고유함수"** 의 구체적 모습이다. 단지 사인 함수이다.

example1 의 $\psi_k(i)$ 가 $|\lambda_k\rangle$ 의 $i$ 번째 **성분(숫자)** 이었다면, 본 예제의 $\psi_n(x)$ 는 $|\lambda_n\rangle$ 의 $x$ 에서의 **값(함수)** 이다. 둘 다 같은 추상 객체 $\langle u^d|\lambda_k\rangle$ 의 표현 기저 차이에 따른 구체화일 뿐이다.

$\hat{A}$ 가 허미션이고 위치 기저가 정규직교이므로 §5의 단순화된 형태를 사용한다 ($\psi^n = \psi_n^* = \psi_n$, 실수 함수).

(2) 스펙트럼 그린함수

$$
G(x,x') = \sum_{n=1}^\infty \frac{\psi_n(x)\,\psi_n(x')}{\lambda_n}
= \frac{2L}{\pi^2}\sum_{n=1}^\infty \frac{\sin(n\pi x/L)\,\sin(n\pi x'/L)}{n^2}
$$

(3) 폐형(closed-form) 해

$\hat{A}_x G(x,x') = \delta(x-x')$ 를 분할 풀이(연속성과 점프 조건)로 풀면

$$
G(x,x') = \frac{x_<\,(L-x_>)}{L}, \quad x_<=\min(x,x'),\ x_>=\max(x,x')
$$

이 얻어진다. 본 예제는 같은 그린함수의 **스펙트럼 표현(무한 급수)** 과 **폐형 표현(닫힌 형태)** 의 두 모습이다.

(4) 검증 (특정점에서)

중앙점 $x=x'=L/2$ 에서:

- 폐형: $G(L/2, L/2) = \dfrac{(L/2)\cdot(L/2)}{L} = \dfrac{L}{4}$
- 스펙트럼: 

$$
\frac{2L}{\pi^2}\sum_{n=1}^\infty \frac{\sin^2(n\pi/2)}{n^2}
= \frac{2L}{\pi^2}\sum_{n\,\text{odd}}\frac{1}{n^2}
= \frac{2L}{\pi^2}\cdot\frac{\pi^2}{8} = \frac{L}{4}
$$

두 결과가 일치함을 확인한다.

(5) 이산 예제와의 비교

| | example1 (이산) | example2 (연속) |
|---|---|---|
| 표현 기저 | $\{u_i\}$, 2차원 | $\{\vert x\rangle\}$, $x\in[0,L]$ |
| $\psi_k(u)$ 의 의미 | $\vert\lambda_k\rangle$ 의 $i$ 번째 **성분** (숫자) | $\vert\lambda_n\rangle$ 의 $x$ 에서의 **값** (함수) |
| $\hat{A}^{-1}$ 의 표현 | 행렬 $(A^{-1})_{ij}$ | 함수 $G(x,x')$ |
| 스펙트럼 합 | 유한 합 ($k=1,2$) | 무한 급수 ($n=1,2,\ldots$) |

즉, **"$\psi_k(u)$ = 표현 기저에서 본 고유함수" 의 의미는 표현 기저가 이산이냐 연속이냐에 따라 "성분(숫자)" 또는 "함수의 값" 으로 구체화된다.** 둘 다 같은 추상 객체 $\langle u^d|\lambda_k\rangle$ 의 표현일 뿐이다.
