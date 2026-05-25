+++
title = "약자와 표기 약속"
weight = 1
+++

### 1. 이 절의 동기

리 군 분야는 약자가 많다. $SO$, $SU$, $U$, $O$, $GL$, $SL$, $Sp$, $Spin$, $PSL$, $BCH$ 등. 각 약자는 *영어 원형의 머리글자*에서 왔는데, 어원을 모르면 외우기 어렵고 정의도 흐려진다.

본격적 정의로 들어가기 전에 이 약자들을 한자리에 모아 *영어 원형 — 한국어 명칭 — 정의식 — 차원 — 컴팩트성 — 연결성* 의 여섯 항목으로 정리한다. 약자가 시리즈 어디서 갑자기 튀어나와도 이 절로 돌아와 확인할 수 있게 한다.

이 절에서는 약속만 한다. *리 군의 정의 자체*는 §1, *리 대수*는 §8, *컴팩트·연결성의 의미와 결과*는 §2 와 §12–§14 에서 본격적으로 다룬다.

### 2. 행렬군 명명의 일반 규칙

리 군에서 자주 보는 약자들은 대부분 *행렬군*의 이름이다. 명명에는 일관된 패턴이 있어서 한 번 익히면 새 약자도 어렵지 않게 읽힌다.

**1)** *머리글자* 는 어떤 *조건으로 좁힌* 부분군인지를 나타낸다.
- *G* (General) : 가역이라는 가장 약한 조건만 부과
- *S* (Special) : 행렬식 $\det = 1$ 조건 추가
- *P* (Projective) : 중심(center)으로 *몫(quotient)* 을 취함
- 추가로 *U* 가 또 다른 의미로 등장하는 경우가 있다 ($USp$ 같은 표기 — 뒤에서 설명).

**2)** *본체 문자* 는 행렬 자체가 어떤 *종류* 의 행렬인지를 가리킨다.
- *L* (Linear) : 가역 행렬 전체
- *O* (Orthogonal) : 실 직교 행렬, $M^T M = I$
- *U* (Unitary) : 복소 유니타리 행렬, $M^\dagger M = I$
- *Sp* (Symplectic) : 표준 심플렉틱 형식을 보존하는 행렬
- *Spin* : 직교군의 *이중 덮개*

**3)** *괄호 안의 인자* 는 행렬 *크기* 와 *바탕체(field)* 를 나타낸다.
- 표기 형태 : $G(N, \mathbb{F})$
- $N$ : 행렬의 가로·세로 크기 (자연수)
- $\mathbb{F}$ : 바탕체. 보통 실수 $\mathbb{R}$, 복소 $\mathbb{C}$, 가끔 사원수 $\mathbb{H}$
- $\mathbb{F}$ 생략 시 *맥락 표준* 을 따름. 예 — $O(N)$ 은 표준적으로 $O(N, \mathbb{R})$, $U(N)$ 은 표준적으로 복소 $U(N, \mathbb{C})$.

**4)** *차원 표기* 는 시리즈 전체에서 *실 다양체 차원* ($\dim_{\mathbb{R}}$) 을 기본으로 한다. 복소 리 군의 복소 차원도 필요하면 $\dim_{\mathbb{C}}$ 로 따로 적는다.

> 같은 군이라도 *실 차원* 과 *복소 차원* 이 다를 수 있다. 예 — $GL(N, \mathbb{C})$ 는 복소 다양체로 보면 $\dim_{\mathbb{C}} = N^2$ 이지만, 실 다양체로 보면 $\dim_{\mathbb{R}} = 2N^2$.

### 3. 일반 선형군 계열 : $GL$, $SL$

**1)** $GL(N, \mathbb{F})$ — *General Linear group*. 한국어로 *일반 선형군*. $N \times N$ *가역* 행렬 전체.

$$GL(N, \mathbb{F}) = \{ M \in M_N(\mathbb{F}) : \det M \neq 0 \}$$

여기서 $M_N(\mathbb{F})$ 는 $N \times N$ 행렬 전체의 집합 (군 구조 아직 없음).

**2)** $GL(N, \mathbb{F})$ 의 차원·위상.
- $\dim_{\mathbb{R}} GL(N, \mathbb{R}) = N^2$
- $\dim_{\mathbb{R}} GL(N, \mathbb{C}) = 2N^2$
- 두 경우 모두 *비컴팩트*. 행렬 원소가 무한히 커질 수 있다.
- $GL(N, \mathbb{R})$ 은 *비연결*. $\det > 0$ 부분과 $\det < 0$ 부분 두 조각으로 나뉜다. $\det$ 가 $0$ 을 지나지 못하니 두 조각을 연결하는 길이 없다.
- $GL(N, \mathbb{C})$ 은 *연결*. 복소 행렬식은 $\mathbb{C} \setminus \{0\}$ 안에 머무는데 이 공간이 연결이라 한 조각이다.

**3)** $SL(N, \mathbb{F})$ — *Special Linear group*. *특수 선형군*. $GL(N, \mathbb{F})$ 에서 행렬식이 정확히 $1$ 인 부분군.

$$SL(N, \mathbb{F}) = \{ M \in GL(N, \mathbb{F}) : \det M = 1 \}$$

**4)** $SL(N, \mathbb{F})$ 의 차원·위상.
- $\dim_{\mathbb{R}} SL(N, \mathbb{R}) = N^2 - 1$. ($\det = 1$ 한 조건이 차원 하나를 깎는다.)
- $\dim_{\mathbb{R}} SL(N, \mathbb{C}) = 2(N^2 - 1)$.
- 두 경우 모두 *비컴팩트*. ($\det$ 는 묶었지만 다른 원소는 여전히 무한히 클 수 있다.)
- 두 경우 모두 *연결*. ($SL(N, \mathbb{R})$ 의 연결성은 비자명한 사실인데, *모든 행렬식 1 행렬은 항등원에서 매끄럽게 도달 가능* 하다는 결과로 따라온다.)

**5)** *동기*. $GL$ 은 *가장 큰* 행렬군, $SL$ 은 거기에 *부피 보존* 조건을 추가한 것이다. 행렬식이 *부피 척도* 라는 기하적 의미에서 $SL$ 은 "부피를 안 바꾸는 선형변환" 의 군이다.

### 4. 직교군 계열 : $O$, $SO$

**1)** $O(N)$ — *Orthogonal group*. *직교군*. 실 $N \times N$ 행렬 중 *내적을 보존* 하는 것들.

$$O(N) = \{ M \in M_N(\mathbb{R}) : M^T M = I_N \}$$

$M^T M = I_N$ 조건은 다음과 동치다.
- 모든 $x, y \in \mathbb{R}^N$ 에 대해 $\langle Mx, My \rangle = \langle x, y \rangle$ (내적 보존)
- $M$ 의 열벡터들이 *정규 직교 기저* 를 이룸

**2)** $O(N)$ 의 차원·위상.
- $\dim_{\mathbb{R}} O(N) = N(N-1)/2$. ($M^T M = I$ 가 *대칭 행렬 조건* 이라 $N(N+1)/2$ 개 제약, $N^2$ 에서 빼면 $N(N-1)/2$.)
- *컴팩트*. ($M^T M = I$ 에서 $|M_{ij}| \le 1$ 이 강제되어 유계, 닫힘.)
- *비연결*. $\det M = \pm 1$ 인데 $\det$ 가 $0$ 을 지나지 못하니 $\det = +1$ 성분과 $\det = -1$ 성분이 따로 논다.

**3)** $SO(N)$ — *Special Orthogonal group*. *특수 직교군*. $O(N)$ 중 행렬식 $+1$ 인 부분군 = *회전군*.

$$SO(N) = \{ M \in O(N) : \det M = 1 \}$$

**4)** $SO(N)$ 의 차원·위상.
- $\dim_{\mathbb{R}} SO(N) = N(N-1)/2$. ($O(N)$ 과 같다 — 한 조각만 떼어낸 것이라 차원은 그대로.)
- *컴팩트, 연결* ($N \ge 1$).
- 단순연결인가 — $SO(2)$ 는 단순연결 *아님* ($\pi_1 = \mathbb{Z}$ — 원이라 한 바퀴 도는 길이 줄어들지 않음). $SO(N)$ 은 $N \ge 3$ 에서도 단순연결 *아님* ($\pi_1 = \mathbb{Z}_2$). 단순연결 덮개가 *Spin(N)* (§7 참조).

**5)** *작은 차원 동형* (외워두면 유용).
- $SO(2) \cong S^1$ (원)
- $SO(3) \cong \mathbb{R}P^3$ (실 사영 3-공간)

**6)** *물리 등장*. $SO(3)$ — 3차원 실공간의 회전. $SO(N)$ — 일반 차원의 회전. $O(N)$ — 회전 + 거울반사. 응집계 물리의 시간 역전·공간 반전 대칭 분류에서 $O$ 와 $SO$ 의 구분이 핵심.

### 5. 유니타리군 계열 : $U$, $SU$

**1)** $U(N)$ — *Unitary group*. *유니타리군*. 복소 $N \times N$ 행렬 중 *에르미트 내적을 보존* 하는 것들.

$$U(N) = \{ M \in M_N(\mathbb{C}) : M^\dagger M = I_N \}$$

여기서 $M^\dagger = (\overline{M})^T$ 는 *에르미트 켤레* (복소켤레 + 전치).

**2)** $U(N)$ 의 차원·위상.
- $\dim_{\mathbb{R}} U(N) = N^2$. ($M^\dagger M = I$ 가 *에르미트 조건* 이라 실 자유도로 $N^2$ 개 제약, 복소 $N \times N$ 의 실 자유도 $2N^2$ 에서 빼면 $N^2$.)
- *컴팩트*. ($M^\dagger M = I$ 에서 $|M_{ij}| \le 1$.)
- *연결*. ($\det M$ 이 $U(1)$ 안을 움직이는데, $U(1)$ 이 연결이라.)
- 단순연결 *아님*. ($\pi_1(U(N)) = \mathbb{Z}$ — $\det$ 의 위상이 그대로 떨어진다.)

**3)** $SU(N)$ — *Special Unitary group*. *특수 유니타리군*. $U(N)$ 중 행렬식 $+1$ 인 부분군.

$$SU(N) = \{ M \in U(N) : \det M = 1 \}$$

**4)** $SU(N)$ 의 차원·위상.
- $\dim_{\mathbb{R}} SU(N) = N^2 - 1$. ($\det = 1$ 이 실 자유도 하나 제거.)
- *컴팩트, 연결*.
- *단순연결* ($N \ge 1$). ($U(N)$ 의 비단순연결성은 전적으로 $\det$ 가 가져온 것인데, $SU(N)$ 에서는 그게 제거되었다.)

**5)** *작은 차원 동형*.
- $U(1) \cong S^1$ (원, 복소수 $e^{i\theta}$)
- $SU(2) \cong S^3$ (3-구면)

**6)** *물리 등장*.
- $U(1)$ — 전하 보존·게이지 대칭의 가장 기본
- $SU(2)$ — 스핀 회전, 약작용 게이지
- $SU(3)$ — 강작용 게이지 (색깔)
- $SU(N)$ — 허바드 모형 등 $N$ 종 페르미온의 일반 회전 대칭

### 6. 심플렉틱군 : $Sp$ (표기 혼동 주의)

심플렉틱군은 *두 가지 다른 군* 이 비슷한 기호로 불려서 혼동을 일으킨다. 이 절에서 명확히 구분한다.

**1)** *표준 심플렉틱 형식* $\Omega$ 의 정의. $2N \times 2N$ 행렬.

$$\Omega = \begin{pmatrix} 0_N & I_N \\ -I_N & 0_N \end{pmatrix}$$

이 $\Omega$ 를 보존하는 행렬이 심플렉틱.

**2)** $Sp(2N, \mathbb{F})$ — *Symplectic group over $\mathbb{F}$*. *심플렉틱군*. $\Omega$ 를 보존하는 $2N \times 2N$ 행렬.

$$Sp(2N, \mathbb{F}) = \{ M \in M_{2N}(\mathbb{F}) : M^T \Omega M = \Omega \}$$

**3)** $Sp(2N, \mathbb{F})$ 의 차원·위상.
- $\dim_{\mathbb{R}} Sp(2N, \mathbb{R}) = N(2N+1)$.
- $\dim_{\mathbb{R}} Sp(2N, \mathbb{C}) = 2N(2N+1)$.
- 두 경우 모두 *비컴팩트, 연결*.

**4)** $Sp(N)$ — *Compact Symplectic group*. *컴팩트 심플렉틱군*. $USp(2N)$ 으로 적기도 한다. *주의* — 인자 $N$ 의 의미가 (2) 와 *다르다*.

$$Sp(N) = Sp(2N, \mathbb{C}) \cap U(2N)$$

즉 복소 심플렉틱이면서 동시에 유니타리인 행렬들. 다른 시각으로는 *사원수 유니타리군* — 사원수 벡터공간 $\mathbb{H}^N$ 의 내적 보존 변환들.

**5)** $Sp(N)$ 의 차원·위상.
- $\dim_{\mathbb{R}} Sp(N) = N(2N+1)$.
- *컴팩트, 단순연결*.

**6)** 작은 차원 동형.
- $Sp(1) \cong SU(2) \cong S^3$

**7)** *표기 정리 — 헷갈리지 않도록*.

| 기호 | 의미 | 차수 | 컴팩트 |
|---|---|---|---|
| $Sp(2N, \mathbb{R})$ | 실 심플렉틱 | $2N \times 2N$ | 아님 |
| $Sp(2N, \mathbb{C})$ | 복소 심플렉틱 | $2N \times 2N$ | 아님 |
| $Sp(N)$ 또는 $USp(2N)$ | 컴팩트 (사원수 유니타리) | $2N \times 2N$ | 컴팩트 |

이 시리즈에서는 *컴팩트 심플렉틱군* 을 가리킬 때 $Sp(N)$, *실 심플렉틱군* 을 가리킬 때 $Sp(2N, \mathbb{R})$ 처럼 *바탕체를 명시* 한다.

**8)** *물리 등장*. $Sp(2N, \mathbb{R})$ — 해밀턴 역학의 정준 변환. $Sp(N)$ — 응집계 물리의 대칭 분류 (Altland–Zirnbauer 10중 분류에서 시간역전 제곱 $-1$ 인 부류).

### 7. 스핀군 : $Spin$

**1)** $Spin(N)$ — $SO(N)$ 의 *이중 덮개(double cover)*. $N \ge 3$ 에서 *보편 덮개(universal cover)* 가 된다.

정확한 정의는 클리포드 대수(Clifford algebra)를 거쳐 들어가야 하는데, 이 시리즈에서는 직접 다루지 않는다. 여기서는 *덮개 관계*만 약속한다.

$$\pi : Spin(N) \to SO(N), \qquad \ker \pi = \mathbb{Z}_2 = \{ +1, -1 \}$$

즉 $SO(N)$ 의 한 원소가 $Spin(N)$ 의 *두 원소* 에 대응된다.

**2)** $Spin(N)$ 의 차원·위상.
- $\dim_{\mathbb{R}} Spin(N) = N(N-1)/2$. ($SO(N)$ 과 같다 — 덮개는 *국소적으로 동형* 이라 리 대수가 같고 따라서 차원도 같다.)
- *컴팩트*.
- $N \ge 3$ 에서 *단순연결*.

**3)** 작은 차원 동형 (외워두면 유용 — *예외적 동형(exceptional isomorphism)* 이라고도 한다).
- $Spin(3) \cong SU(2)$
- $Spin(4) \cong SU(2) \times SU(2)$
- $Spin(5) \cong Sp(2)$ (컴팩트 심플렉틱)
- $Spin(6) \cong SU(4)$
- $Spin(N)$ 의 작은 차원 동형은 $N = 6$ 까지만 있고 이후 끊긴다.

**4)** *물리 등장*. 페르미온(전자, 양성자 등)은 *공간 회전 $2\pi$ 회전 시 부호 반전* 하는 성질을 가져서 $SO(3)$ 가 아닌 $Spin(3) = SU(2)$ 의 표현으로 기술된다. 일반화하면 *스피너* 는 $Spin(N)$ 의 표현.

**5)** *친척*. $Pin(N)$ 은 $O(N)$ 의 이중 덮개. 그런데 두 종류 $Pin^+(N)$, $Pin^-(N)$ 가 존재해서 이중 덮개가 *유일하지 않다*. 이 시리즈에서는 다루지 않음.

### 8. 사영군 : $PSL$

**1)** $PSL(N, \mathbb{F})$ — *Projective Special Linear group*. *사영 특수 선형군*. $SL(N, \mathbb{F})$ 를 그 *중심* 으로 나눈 몫군.

$$PSL(N, \mathbb{F}) = SL(N, \mathbb{F}) / Z(SL(N, \mathbb{F}))$$

여기서 $Z(G)$ 는 군 $G$ 의 *중심* — 모든 원소와 가환인 원소들로 이뤄진 부분군.

**2)** $SL(N, \mathbb{F})$ 의 중심.
- $Z(SL(N, \mathbb{C})) = \{ \zeta I : \zeta^N = 1 \} \cong \mathbb{Z}_N$ (1의 $N$ 제곱근)
- $Z(SL(N, \mathbb{R})) = \{ I \}$ ($N$ 홀수), $\{ \pm I \}$ ($N$ 짝수)

**3)** $PSL$ 의 차원.
- 중심은 *유한군* 이라 몫을 취해도 차원은 같다. $\dim PSL(N, \mathbb{F}) = \dim SL(N, \mathbb{F})$.

**4)** 작은 차원 동형 (참고).
- $PSL(2, \mathbb{R}) \cong \mathrm{Isom}^+(\mathbb{H}^2)$ — 쌍곡 평면의 방향 보존 등거리군
- $PSL(2, \mathbb{C}) \cong$ 뫼비우스 변환군

**5)** 응집계 물리에서는 그렇게 자주 등장하지 않지만, *사영 표현* 개념과 함께 양자역학의 표현론에서 중요해 약자만 익혀둔다.

### 9. $BCH$ 공식

**1)** $BCH$ — *Baker–Campbell–Hausdorff*. 세 수학자 (Campbell 1897, Baker 1902, Hausdorff 1906) 가 독립적으로 발견한 공식의 이름.

**2)** 내용. 두 *비가환* 행렬 $X, Y$ 에 대해

$$\exp(X) \exp(Y) = \exp(Z)$$

가 되는 $Z$ 가 (수렴 영역 안에서) 존재하며, 이 $Z$ 가 *교환자 $[X, Y] = XY - YX$ 만으로* 표현된다는 공식.

처음 몇 항.

$$Z = X + Y + \frac{1}{2}[X, Y] + \frac{1}{12}\bigl( [X, [X, Y]] - [Y, [X, Y]] \bigr) + \cdots$$

**3)** 의미. $X, Y$ 가 *가환* ($[X, Y] = 0$) 이면 $Z = X + Y$ 로 단순화 — 익숙한 지수 법칙. 비가환이면 *교환자 보정항* 이 따라붙는다.

**4)** $BCH$ 공식의 본격적 도입은 §10 (교환자와 리 괄호) 이후, *지수 사상의 한계* 를 다루는 §13 에서 사용된다.

### 10. 기타 표기 약속

이 시리즈에서 사용하는 일반 표기들을 모아둔다.

**1)** *군과 리 대수의 분리 표기*.
- 리 군 — 대문자 로마자 : $G$, $H$, $SO(N)$ 등
- 리 대수 — 대문자 *프락투어(고딕)* 체 : $\mathfrak{g}$, $\mathfrak{h}$, $\mathfrak{so}(N)$ 등
- 대응 관계 — 리 군 $G$ 의 항등원에서의 접공간이 리 대수 $\mathfrak{g}$ (§8 에서 증명).

**2)** *주요 행렬군의 리 대수*.

| 리 군 | 리 대수 | 정의 |
|---|---|---|
| $GL(N, \mathbb{F})$ | $\mathfrak{gl}(N, \mathbb{F})$ | 모든 $N \times N$ 행렬 |
| $SL(N, \mathbb{F})$ | $\mathfrak{sl}(N, \mathbb{F})$ | 트레이스 $0$ 행렬 |
| $O(N), SO(N)$ | $\mathfrak{so}(N)$ | 반대칭 실 행렬 ($X^T = -X$) |
| $U(N)$ | $\mathfrak{u}(N)$ | 반에르미트 행렬 ($X^\dagger = -X$) |
| $SU(N)$ | $\mathfrak{su}(N)$ | 반에르미트 + 트레이스 $0$ |
| $Sp(2N, \mathbb{F})$ | $\mathfrak{sp}(2N, \mathbb{F})$ | $X^T \Omega + \Omega X = 0$ |
| $Spin(N)$ | $\mathfrak{spin}(N) = \mathfrak{so}(N)$ | $\mathfrak{so}(N)$ 과 *같다* |

> $Spin(N)$ 과 $SO(N)$ 은 *다른 군* 이지만 *리 대수가 같다*. 덮개 관계는 *국소적으로 동형* 이라 무한소 구조 (리 대수) 가 일치한다. 이것이 §8 이후의 핵심 동기 — 군 자체보다 *항등원 근방의 무한소 구조* 가 더 다루기 쉽고 더 보편적이다.

**3)** *항등원 표기*.
- 군의 항등원 — $e$ (또는 맥락에 따라 $1$, $I$)
- 행렬군의 항등원 — $I$ 또는 $I_N$ ($N \times N$ 항등 행렬)
- 가산 가능 항등 행렬을 강조할 때 — $\mathbb{1}$

**4)** *핵심 사상 표기*.
- $\exp : \mathfrak{g} \to G$ — *지수 사상*. 리 대수에서 리 군으로 가는 사상. 행렬군의 경우 행렬 지수 $\exp(X) = \sum_{k=0}^\infty X^k / k!$.
- $\log : G \to \mathfrak{g}$ — *로그 사상*. 항등원 근방에서 $\exp$ 의 역.
- $[\cdot, \cdot] : \mathfrak{g} \times \mathfrak{g} \to \mathfrak{g}$ — *리 괄호*. 행렬군의 경우 교환자 $[X, Y] = XY - YX$.

**5)** *수반 표현* (참고).
- $\mathrm{Ad}_g : \mathfrak{g} \to \mathfrak{g}, \ X \mapsto g X g^{-1}$ — 군 원소 $g$ 에 의한 켤레.
- $\mathrm{ad}_X : \mathfrak{g} \to \mathfrak{g}, \ Y \mapsto [X, Y]$ — 리 대수 원소 $X$ 의 무한소 켤레.
- 관계 — $\mathrm{Ad}_{\exp(X)} = \exp(\mathrm{ad}_X)$ (이 식은 §13 에서 다룸).

**6)** *바탕체와 행렬 공간*.
- $\mathbb{R}$ — 실수
- $\mathbb{C}$ — 복소수
- $\mathbb{H}$ — 사원수 (Hamilton's quaternions)
- $M_N(\mathbb{F})$ — $N \times N$ 행렬 전체 (군 구조 없음)
- $\mathbb{F}^N$ — $N$ 차원 벡터공간

**7)** *유한군 표기* (가끔 등장).
- $\mathbb{Z}_N = \mathbb{Z}/N\mathbb{Z}$ — $N$ 원소 순환군
- $\mathbb{Z}_2 = \{ +1, -1 \}$ — 두 원소 군
- $T^N = U(1)^N$ — $N$ 차원 토러스 (가환 컴팩트 연결 리 군)

**8)** *위상 표기*.
- $S^N$ — $N$ 차원 구면
- $\mathbb{R}P^N$ — 실 사영 $N$-공간
- $\pi_1(G)$ — 기본군 (loop의 호모토피류)

**9)** *스펙트럼 분해와 바이듀얼 표기* 는 §0-5 에서 별도로 다룬다. 이 시리즈에서 연산자는 가능한 한

$$H = \sum_i \lambda_i \vert \lambda_i \rangle \langle \lambda^i \vert$$

형태로 표현한다. 여기 켓 $\vert v_i \rangle$ 과 브라 $\langle v^i \vert$ 는 *쌍대 기저* — $\langle v^i \vert v_j \rangle = \delta^i_j$. 자세한 약속은 §0-5.

### 11. 약자 요약표

이 절의 핵심을 한 표로 정리한다.

| 약자 | 영어 원형 | 한국어 | 정의식 | $\dim_{\mathbb{R}}$ | 컴팩트 | 연결 |
|---|---|---|---|---|---|---|
| $GL(N, \mathbb{R})$ | General Linear | 일반 선형군 | $\det \neq 0$ | $N^2$ | 아님 | 아님 |
| $GL(N, \mathbb{C})$ | " | " | $\det \neq 0$ | $2N^2$ | 아님 | 연결 |
| $SL(N, \mathbb{R})$ | Special Linear | 특수 선형군 | $\det = 1$ | $N^2 - 1$ | 아님 | 연결 |
| $SL(N, \mathbb{C})$ | " | " | $\det = 1$ | $2(N^2 - 1)$ | 아님 | 연결 |
| $O(N)$ | Orthogonal | 직교군 | $M^T M = I$ | $N(N-1)/2$ | 컴팩트 | 아님 |
| $SO(N)$ | Special Orthogonal | 특수 직교군 (회전) | $O(N), \det = 1$ | $N(N-1)/2$ | 컴팩트 | 연결 |
| $U(N)$ | Unitary | 유니타리군 | $M^\dagger M = I$ | $N^2$ | 컴팩트 | 연결 |
| $SU(N)$ | Special Unitary | 특수 유니타리군 | $U(N), \det = 1$ | $N^2 - 1$ | 컴팩트 | 연결 |
| $Sp(2N, \mathbb{R})$ | Symplectic | 실 심플렉틱군 | $M^T \Omega M = \Omega$ | $N(2N+1)$ | 아님 | 연결 |
| $Sp(N)$ | Compact Symplectic | 컴팩트 심플렉틱 | $Sp(2N, \mathbb{C}) \cap U(2N)$ | $N(2N+1)$ | 컴팩트 | 연결 |
| $Spin(N)$ | Spin | 스핀군 | $SO(N)$ 의 이중 덮개 | $N(N-1)/2$ | 컴팩트 | 연결 |
| $PSL(N, \mathbb{F})$ | Projective Special Linear | 사영 특수 선형군 | $SL/Z(SL)$ | $\dim SL$ 과 동일 | 바탕체 따라 | 바탕체 따라 |
| $BCH$ | Baker–Campbell–Hausdorff | (수학자 이름) | $\exp X \exp Y = \exp Z$ 공식 | — | — | — |

### 12. 이 절을 닫으며

여기까지가 시리즈 전체에서 사용할 약자와 표기의 약속이다. 다음 절 §0-2 부터는 *군의 4공리 복습* 으로 들어가 본격적 준비를 시작한다.

이 절을 *완전히 외울* 필요는 없다. 시리즈 본문에서 약자가 처음 나올 때마다 짧게 풀어쓰기는 반복한다. 이 절은 *언제든 돌아와 확인* 할 수 있는 *참조 페이지* 역할이다.
