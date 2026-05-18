+++
title = "(b) Green's function"
weight = 1
+++

---

### 1. 역연산자의 적분 커널

연산자 방정식

$$
\hat{A}|v\rangle = |f\rangle
$$

에서, 출력 $|f\rangle$ 로부터 입력 $|v\rangle$ 를 구하는 문제를 생각하자. $\hat{A}$ 의 역연산자가 존재한다면, 형식적으로

$$
|v\rangle = \hat{A}^{-1}|f\rangle
$$

이다.

**1) 이산 기저: 역행렬**

유한 차원에서 이 역연산자는 **역행렬** $(A^{-1})_{ij}$ 로 표현되며, 성분 단위로 다음과 같이 나타난다.

$$
\psi_i = \sum_j (A^{-1})_{ij}\,\phi_j
$$

**2) 연속 기저: 그린함수**

무한 차원(함수 공간)에서는 어떻게 표현될까. 적분 커널의 정의에 의해, 임의의 연산자 $\hat{H}$ 는 연속 기저에서 다음과 같이 표현된다.

$$
\hat{H} = \iint du\,du'\,h(u,u')\,|u\rangle\langle u'^d|, \quad h(u,u') = \langle u^d|\hat{H}|u'\rangle
$$

이 표현을 역연산자 $\hat{A}^{-1}$ 에 그대로 적용하면, 그 적분 커널이 곧 **그린함수(Green's function)** 가 된다.

$$
G(u,u') = \langle u^d|\hat{A}^{-1}|u'\rangle
$$

$$
\hat{A}^{-1} = \iint du\,du'\,G(u,u')\,|u\rangle\langle u'^d|
$$

**즉, 그린함수는 새로운 개념이 아니라, 이미 정의된 적분 커널을 역연산자에 적용한 결과이다.**

위치 기저 $|x\rangle$ 와 같은 **정규직교 연속 기저** 의 경우 $\langle u^d|=\langle u|$ 이 성립하여 표기가 단순해진다.

$$
G(x,x') = \langle x|\hat{A}^{-1}|x'\rangle \quad (\text{정규직교 기저의 경우})
$$

---

### 2. 정의 방정식

표준 교재에서 그린함수는 다음 방정식으로 정의되는 경우가 많다.

$$
\hat{A}_u\,G(u,u') = \delta(u-u')
$$

여기서 $\hat{A}_u$ 는 $\hat{A}$ 가 $u$ 변수에 작용함을 명시하는 표기이다. 이 식은 항등 관계 $\hat{A}\hat{A}^{-1}=\hat{I}$ 의 연속 기저 표현일 뿐이다.

proof)

$\hat{A}\hat{A}^{-1}=\hat{I}$ 의 양변을 $\langle u^d|\cdots|u'\rangle$ 로 끼운다.

$$
\langle u^d|\hat{A}\hat{A}^{-1}|u'\rangle = \langle u^d|\hat{I}|u'\rangle
$$

우변은 쌍대 기저의 정의에 의해 델타 함수가 된다.

$$
\langle u^d|\hat{I}|u'\rangle = \langle u^d|u'\rangle = \delta(u-u')
$$

좌변은 $\hat{A}$ 가 $u$ 변수에 작용함을 살려서

$$
\langle u^d|\hat{A}\hat{A}^{-1}|u'\rangle 
= \hat{A}_u\,\langle u^d|\hat{A}^{-1}|u'\rangle
= \hat{A}_u\,G(u,u')
$$

이다. 따라서

$$
\hat{A}_u\,G(u,u') = \delta(u-u')
$$

이 방정식의 직관: **$u'$ 위치에 가해진 단위 점원(delta source)에 대한 시스템 $\hat{A}$ 의 응답이 $G(u,u')$ 이다.**

---

### 3. 그린함수를 이용한 출력의 계산

임의의 입력 $f$ 에 대한 출력 $v$ 는 그린함수에 의해 다음과 같이 표현된다.

$$
v(u) = \int du'\,G(u,u')\,f(u')
$$

여기서 $v(u) := \langle u^d|v\rangle$, $f(u') := \langle u'^d|f\rangle$ 는 함수 표현이다.

proof)

$|v\rangle = \hat{A}^{-1}|f\rangle$ 의 양변에 $\langle u^d|$ 를 작용시킨다.

$$
\langle u^d|v\rangle = \langle u^d|\hat{A}^{-1}|f\rangle
$$

좌변은 $v(u)$ 이다. 우변에 항등 연산자 $\hat{I} = \int du'\,|u'\rangle\langle u'^d|$ 를 삽입하면

$$
\langle u^d|\hat{A}^{-1}|f\rangle 
= \int du'\,\langle u^d|\hat{A}^{-1}|u'\rangle\langle u'^d|f\rangle 
= \int du'\,G(u,u')\,f(u')
$$

이다.

이 식의 직관적 의미는 다음과 같다. **임의의 입력 $f$ 에 대한 응답은, 각 위치 $u'$ 에서의 점원 응답 $G(u,u')$ 들의 가중합이다.** 가중치는 입력 함수의 값 $f(u')$ 이다.

비유: 임펄스 응답

- 시스템 $\hat{A}$ 는 어떤 물리 시스템(진동하는 줄, 전자 회로 등)을 표현한다.
- $G(u,u')$ 는 $u'$ 지점에 순간적 충격이 가해졌을 때 $u$ 지점에서 관측되는 반응이다.
- 일반 입력 $f$ 에 대한 응답은, 입력의 각 점이 만드는 임펄스 응답들의 합이다.

이는 신호처리의 임펄스 응답 함수, 회로의 단위 전압 응답 등과 정확히 같은 개념이다.

---

### 4. 그린함수와 역행렬의 대응

이산 기저(행렬)와 연속 기저(적분 커널)의 두 측면을 한 표에 정리한다.

| | 이산 기저 | 연속 기저 |
|---|---|---|
| 연산자의 성분 | $A_{ij} = \langle u^i \vert \hat{A} \vert u_j\rangle$ | $h(u,u') = \langle u^d \vert \hat{H} \vert u'\rangle$ |
| 출력 계산 | $\phi_i = \sum_j A_{ij}\,\psi_j$ | $\varphi(u) = \int du'\,h(u,u')\,\psi(u')$ |
| 역연산자의 성분 | $(A^{-1})_{ij}$ | $G(u,u') = \langle u^d \vert \hat{A}^{-1} \vert u'\rangle$ |
| 역연산 | $\psi_i = \sum_j (A^{-1})_{ij}\,\phi_j$ | $v(u) = \int du'\,G(u,u')\,f(u')$ |
| 항등 조건 | $\sum_k A_{ik}(A^{-1})_{kj} = \delta_{ij}$ | $\hat{A}_u\,G(u,u') = \delta(u-u')$ |

즉, **그린함수는 역행렬의 연속판이다.** 새로운 객체가 아니라, 이미 갖춰진 적분 커널 프레임워크의 자연스러운 확장이다. 특히 **델타 함수 $\delta(u-u')$ 는 크로네커 델타 $\delta_{ij}$ 의 연속판** 임을 표의 마지막 행이 명확히 보여준다.

표현 기저가 이산인지 연속인지에 따라 그린함수가 어떻게 구체화되는지, example1 과 example2 에서 각각 확인한다.

---

**example1)** 이산 표현 기저: 3×3 그린행렬

연속 그린함수의 직관을 위해, 이산 버전인 "그린행렬"을 손으로 계산하자.

$$
A = \begin{bmatrix} 2 & 1 & 0 \\ 1 & 2 & 0 \\ 0 & 0 & 5 \end{bmatrix}
$$

sol)

(1) 역행렬

여인수 전개 또는 분할 행렬로 역행렬을 계산하면,

$$
A^{-1} = \begin{bmatrix} 2/3 & -1/3 & 0 \\ -1/3 & 2/3 & 0 \\ 0 & 0 & 1/5 \end{bmatrix}
$$

이 행렬의 성분 $(A^{-1})_{ij}$ 가 그린함수 $G(u,u')$ 의 이산 대응이다. 구체적으로

- $(A^{-1})_{11} = 2/3$ : 1번 자리에 단위 점원이 있을 때 1번 자리에서 보이는 응답
- $(A^{-1})_{21} = -1/3$ : 1번 자리에 단위 점원이 있을 때 2번 자리에서 보이는 응답 (음의 응답은 두 채널의 결합 구조를 반영)
- $(A^{-1})_{33} = 1/5$ : 3번 자리에 단위 점원이 있을 때 3번 자리에서 보이는 응답 (3번 채널이 다른 채널과 분리됨)

(2) 출력 계산

입력 $f = [3,\ 3,\ 10]^T$ 에 대한 출력은

$$
v = A^{-1}f 
= \begin{bmatrix} 2/3\cdot 3 - 1/3\cdot 3 \\ -1/3\cdot 3 + 2/3\cdot 3 \\ 1/5\cdot 10 \end{bmatrix} 
= \begin{bmatrix} 1 \\ 1 \\ 2 \end{bmatrix}
$$

성분별로 보면

$$
v_i = \sum_j (A^{-1})_{ij}\,f_j
$$

이고, 이는 연속판 $v(u) = \int du'\,G(u,u')\,f(u')$ 의 정확한 이산 대응이다.

(3) 검증

$A A^{-1} = I$ 의 성분 형태는

$$
\sum_k A_{ik}(A^{-1})_{kj} = \delta_{ij}
$$

이며, 이는 연속판 $\hat{A}_u\,G(u,u') = \delta(u-u')$ 와 정확히 일치한다.

---

**example2)** 연속 표현 기저: 1차원 디리클레 박스

연속 그린함수가 구체적으로 어떻게 생겼는지 보이기 위한 표준 예제이다.

**연산자**: $\hat{A} = -\dfrac{d^2}{dx^2}$, 정의역 $[0,L]$

**경계 조건**: $\psi(0) = \psi(L) = 0$ (Dirichlet)

**표현 기저**: 위치 기저 $|x\rangle$, $x \in [0,L]$ (정규직교이므로 $\langle x^d|=\langle x|$)

sol)

(1) 정의 방정식 풀이

정의 방정식 $\hat{A}_x G(x,x') = \delta(x-x')$ 와 경계 조건 $G(0,x') = G(L,x') = 0$ 을 만족하는 $G$ 를 구한다.

$x \neq x'$ 영역에서는 $-G''(x;x') = 0$, 즉 $G$ 가 $x$ 에 대해 선형이다.

영역 분할 + 경계 조건:

- $0 \le x \le x'$ 에서: $G(0,x') = 0$ 으로부터 $G = b\,x$
- $x' \le x \le L$ 에서: $G(L,x') = 0$ 으로부터 $G = d\,(x-L)$

여기서 $b, d$ 는 $x'$ 의 함수이다.

연속성 ($x = x'$ 에서):

$$
b\,x' = d\,(x'-L)
$$

점프 조건 ($\hat{A}_x G$ 를 $x'$ 의 좌우 미소영역에서 적분):

$$
-\int_{x'-\epsilon}^{x'+\epsilon} G''(x;x')\,dx = \int_{x'-\epsilon}^{x'+\epsilon}\delta(x-x')\,dx = 1
$$

$$
\implies -\left[G'(x'^+;x') - G'(x'^-;x')\right] = 1
$$

$$
\implies -(d - b) = 1 \implies b - d = 1
$$

두 식을 연립하여 풀면 $b = (L-x')/L$, $d = -x'/L$. 따라서

$$
G(x,x') = \begin{cases} \dfrac{x\,(L-x')}{L} & 0 \le x \le x' \\[8pt] \dfrac{x'\,(L-x)}{L} & x' \le x \le L \end{cases}
$$

또는 더 간결하게

$$
G(x,x') = \frac{x_<\,(L-x_>)}{L}, \quad x_<=\min(x,x'),\ x_>=\max(x,x')
$$

(2) 의미: 단위 점원에 대한 응답

$x'$ 점에 가해진 단위 점원(delta source)에 대해, $x$ 점에서 관찰되는 응답이 $G(x,x')$ 이다. 구체적 형상:

- 응답은 양 끝 $x=0$, $x=L$ 에서 0 (경계 조건)
- 점원 위치 $x=x'$ 에서 최대값 $G(x',x') = x'(L-x')/L$
- 양쪽으로 갈수록 선형 감소 (텐트 모양)

이는 양 끝이 고정된 줄에 단위 힘이 가해진 정상상태 변형과 같다.

(3) 출력 계산: 상수 입력에 대한 응답

상수 입력 $f(x) = c$ 에 대한 출력은

$$
v(x) = \int_0^L dx'\, G(x,x')\,c = c\int_0^L dx'\,G(x,x')
$$

적분을 두 영역으로 나누면

$$
\int_0^L dx'\,G(x,x') 
= \int_0^x dx'\,\frac{x'(L-x)}{L} + \int_x^L dx'\,\frac{x(L-x')}{L}
= \frac{x(L-x)}{2}
$$

따라서 $v(x) = c\,x(L-x)/2$. 이는 $-v''(x) = c$ 와 $v(0)=v(L)=0$ 의 직접 적분 해와 일치한다.

(4) 이산 예제와의 비교

| | example1 (이산) | example2 (연속) |
|---|---|---|
| 표현 기저 | 3차원 이산 | 위치 기저 $\vert x\rangle$, $x\in[0,L]$ |
| $\hat{A}$ | $3\times 3$ 행렬 | 미분 연산자 $-d^2/dx^2$ |
| 그린함수 | 행렬 $(A^{-1})_{ij}$ | 함수 $G(x,x') = x_<(L-x_>)/L$ |
| 점원 응답 의미 | $(A^{-1})_{ij}$ : $j$ 자리 점원에 대한 $i$ 자리 응답 | $G(x,x')$ : $x'$ 점원에 대한 $x$ 응답 |
| 출력 계산 | $v_i = \sum_j (A^{-1})_{ij}\,f_j$ | $v(x) = \int_0^L dx'\,G(x,x')\,f(x')$ |
| 항등 조건 | $\sum_k A_{ik}(A^{-1})_{kj} = \delta_{ij}$ | $\hat{A}_x\,G(x,x') = \delta(x-x')$ |

**그린함수는 연속 인덱스 $(x,x')$ 를 갖는 행렬이라고 생각해도 무방하다.** 이산 인덱스 $(i,j)$ 가 연속 변수 $(x,x')$ 로, 행렬 곱이 적분으로, 크로네커 델타 $\delta_{ij}$ 가 디랙 델타 $\delta(x-x')$ 로 바뀐 것일 뿐이다.

(주: 본 예제의 그린함수는 다음 문서 (스펙트럼 표현) 에서 무한 급수 형태로 다시 도출된다. 같은 $G(x,x')$ 의 두 가지 표현 (폐형 vs 스펙트럼) 을 비교해보면 도움이 된다.)
