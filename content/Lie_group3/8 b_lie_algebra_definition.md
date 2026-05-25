+++
title = "항등원에서의 접공간 = 리 대수"
weight = 13
+++

### 1. 이 절의 동기

§6, §7 에서 *생성자 $X \in T_e G$* 가 1-매개변수 부분군과 1:1 대응함을 보았다. §0-4 §10 와 §6 §9 에서 *$T_e G = \mathfrak{g}$ (리 대수)* 라 예고만 했다. 이 절에서 이 등식을 *본격 증명* 한다.

세 단계로 진행 —
- (i) *추상 정의* — 리 대수의 첫 모습 — $\mathfrak{g} := T_e G$. *벡터 공간 구조* 가 §0-4 의 일반 결과로 자동.
- (ii) *행렬군에서의 구체 도출* — *정의식의 미분* 기법으로 각 행렬군 ($SO, U, SU, Sp$ 등) 의 리 대수가 어떤 행렬 조건 ($X^T = -X$, $X^\dagger = -X$ 등) 으로 결정되는지 직접 계산.
- (iii) *벡터 공간 구조의 명시적 확인* — 행렬 표현에서 $X, Y \in \mathfrak{g}$ 이면 $X + Y, cX \in \mathfrak{g}$ 임을 정의식의 선형성에서 확인.

3부 (§8–§11) 의 전체 그림 —
- §8 (이 절) — 리 대수의 벡터 공간 구조와 행렬 표현
- §9 — 리 대수 ↔ 1-매개변수 부분군 1:1 대응 본격 증명
- §10 — *리 괄호 (교환자)* 추가, 비가환성의 무한소 측정
- §11 — *리 대수 공리* (이중선형성, 반대칭성, *야코비 항등식*)

이 절은 *벡터 공간 부분* 만 다루고, *리 괄호 구조* 가 §10 에서 추가되어 비로소 완전한 *리 대수* 가 완성됨.

### 2. 리 대수의 첫 정의 — 항등원에서의 접공간

**1)** *정의 (리 대수의 첫 모습)*. 리 군 $G$ 의 *리 대수(Lie algebra)* 는 항등원에서의 접공간

$$\mathfrak{g} := T_e G$$

**2)** *벡터 공간 구조*. $T_e G$ 가 *벡터 공간* 임은 §0-4 §6 의 일반 결과 — 모든 매끄러운 다양체의 한 점에서의 접공간이 벡터 공간. 차원

$$\dim \mathfrak{g} = \dim T_e G = \dim G$$

**3)** *표기 약속* (§0-1 §10).
- 리 군 — 대문자 로마자 $G$
- 리 대수 — 대응되는 *프락투어(고딕)* 체 $\mathfrak{g}$
- 예 — $G = SO(N)$ ↔ $\mathfrak{g} = \mathfrak{so}(N)$, $G = U(N)$ ↔ $\mathfrak{u}(N)$, $G = SU(N)$ ↔ $\mathfrak{su}(N)$ 등

**4)** *불완전한 정의*. 이 절의 정의 $\mathfrak{g} = T_e G$ 는 *벡터 공간 구조만* 담는다. *완전한 리 대수 구조* (벡터 공간 + 리 괄호 + 야코비 항등식) 는 §10, §11 에서 완성. 본 절에서는 *벡터 공간 부분 + 리 괄호 도입 직전* 까지.

**5)** *왜 항등원인가 — §6 §2 재확인*. 군 구조 덕에 한 점의 접공간이 *모든 점의 접공간을 결정*. 그 한 점으로 가장 자연스러운 것이 항등원. 모든 분석이 *항등원 근방의 1차 정보* 로 압축됨이 리 군 이론의 큰 그림.

### 3. 행렬군의 리 대수 — 일반 표현

**1)** *행렬군에서의 접공간*. 행렬군 $G \subseteq GL(N, \mathbb{F})$ 에 대해 항등원이 $I \in M_N(\mathbb{F})$. 접공간은

$$T_I G \subseteq T_I M_N(\mathbb{F}) = M_N(\mathbb{F})$$

— $G$ 가 $M_N(\mathbb{F})$ 의 부분 다양체이므로 *접공간이 $M_N(\mathbb{F})$ 의 부분공간*.

**2)** *해석 — 무한소 변환*. $X \in \mathfrak{g} = T_I G$ 라 함은

$$I + tX \in G \quad \text{(1차 정확도로, 작은 $t$)}$$

또는 더 정확히 — *$X$ 를 속도 벡터로 가지는 $G$ 안의 매끄러운 곡선이 존재* (§0-4 §3 의 정의).

**3)** *지수 사상과의 연결 (§7)*. $X \in \mathfrak{g}$ 라 함은 1-매개변수 부분군

$$\gamma_X(t) = \exp(tX) \in G \quad \text{(모든 $t \in \mathbb{R}$ 에서)}$$

가 존재. 즉

$$\mathfrak{g} = \{ X \in M_N(\mathbb{F}) : \exp(tX) \in G \text{ for all } t \in \mathbb{R} \}$$

> *주의* — 이 등식이 *닫힌 부분 리 군* 에 대해 성립 (§1 §9). 임베디드 부분 리 군의 표준 경우. 본 시리즈 모든 행렬군이 이 경우.

### 4. 정의식의 미분 — 리 대수 도출의 일반 패턴

행렬군 $G$ 가 *정의식* ($f(M) = c$ 같은 조건) 으로 정의될 때, 리 대수 $\mathfrak{g}$ 가 그 정의식의 *미분* 으로 결정.

**1)** *일반 패턴*. 행렬군 $G$ 가 정의식 $f(M) = c$ ($f$ 매끄러움, $c$ 상수) 로 정의될 때, $X \in \mathfrak{g}$ 인지 확인하려면

$$M = I + tX \quad \text{대입} \to \quad f(I + tX) = c + t \cdot (\text{1차 항}) + O(t^2)$$

1차 항이 *모든 $t$ 에서 $0$* 이려면 — *1차 항이 항상 $0$*. 이 조건이 *$X$ 의 선형 조건* 으로 떨어진다.

**2)** *왜 이 방법인가*. $G$ 의 정의식이 $M$ 에 대해 *매끄러움* 이므로, $I + tX$ 가 $G$ 에 머무는지의 *국소적 조건* 이 *1차 미분* 으로 결정. 더 높은 차수 ($t^2$ 이상) 는 1차 조건이 성립한 후 자동 처리 (지수 사상 $\exp(tX)$ 가 *모든 차수에서* $G$ 안에 머묾).

**3)** *동치 표현*.

$$X \in \mathfrak{g} \iff \left. \frac{d}{dt} \right|_{t=0} f(\exp(tX)) = 0 \quad (\text{정의식 미분})$$

$\exp(tX) = I + tX + O(t^2)$ 이라 위 미분이 정의식의 1차 항 도출과 같다.

**4)** *명시*. 다음 §5–§8 에서 주요 행렬군 ($SO, U, SU, Sp$ 등) 에 이 패턴을 적용한다.

### 5. 핵심 예 — $SO(N)$ 의 리 대수 $\mathfrak{so}(N)$

**1)** *$O(N)$ 의 정의식*. $M^T M = I_N$. (§0-1 §4.)

**2)** *$I + tX$ 대입*.

$$(I + tX)^T (I + tX) = (I + tX^T)(I + tX) = I + tX + tX^T + t^2 X^T X$$

$$= I + t (X^T + X) + t^2 X^T X$$

**3)** *1차 항 조건*. $(I + tX)^T (I + tX) = I$ 가 *작은 $t$ 에서 1차 정확도로* 성립하려면 1차 항이 $0$ —

$$X^T + X = 0 \quad \Leftrightarrow \quad X^T = -X$$

즉 *반대칭(skew-symmetric)* 행렬.

**4)** *결과*. $O(N)$ 의 리 대수는

$$\mathfrak{o}(N) = \{ X \in M_N(\mathbb{R}) : X^T = -X \}$$

**5)** *$SO(N)$ 도 같다*. $SO(N)$ 은 $O(N)$ 의 *항등원 성분* (§2 §6 (4)). 리 대수는 항등원 *근방* 의 무한소 구조라 *연결 성분에 무관* — *$SO(N)$ 과 $O(N)$ 이 같은 리 대수*

$$\mathfrak{so}(N) = \mathfrak{o}(N) = \{ X \in M_N(\mathbb{R}) : X^T = -X \}$$

> *주의 — 같은 리 대수, 다른 리 군*. $O(N)$ 과 $SO(N)$ 이 *다른 리 군이지만 같은 리 대수*. 비연결 ($O(N)$) vs 연결 ($SO(N)$) 의 차이가 *리 대수에 안 보임* — 리 대수는 *항등원 성분 정보만* 담는다. 이것이 §17 (이중 덮개) 와 §14 (비연결 처리) 의 핵심 동기.

**6)** *$\mathfrak{so}(N)$ 의 차원*. 반대칭 행렬 $X$ 의 자유도 — 대각 성분 $X_{ii} = -X_{ii}$ 이라 모두 $0$, 비대각 $X_{ij} = -X_{ji}$ 이라 상삼각만 자유 — $N(N-1)/2$. 

$$\dim \mathfrak{so}(N) = \frac{N(N-1)}{2}$$

§0-1 §11 의 $\dim SO(N) = N(N-1)/2$ 와 일치.

**7)** *예 — $\mathfrak{so}(2)$*. $\mathfrak{so}(2) = \{ \alpha J : \alpha \in \mathbb{R} \}$ where $J = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix}$. 차원 $1$. (§6 §10.)

**8)** *예 — $\mathfrak{so}(3)$*. $\mathfrak{so}(3) = \{ \text{반대칭 } 3 \times 3 \text{ 실 행렬} \}$. 차원 $3$. 표준 기저

$$L_1 = \begin{pmatrix} 0 & 0 & 0 \\ 0 & 0 & -1 \\ 0 & 1 & 0 \end{pmatrix}, \quad L_2 = \begin{pmatrix} 0 & 0 & 1 \\ 0 & 0 & 0 \\ -1 & 0 & 0 \end{pmatrix}, \quad L_3 = \begin{pmatrix} 0 & -1 & 0 \\ 1 & 0 & 0 \\ 0 & 0 & 0 \end{pmatrix}$$

— $i$ 번째 좌표축 회전의 생성자. §17 본격.

### 6. 핵심 예 — $U(N)$ 의 리 대수 $\mathfrak{u}(N)$

**1)** *$U(N)$ 의 정의식*. $M^\dagger M = I$. (§0-1 §5.)

**2)** *$I + tX$ 대입*. ($X$ 는 복소 행렬 가능, $t$ 는 실수.)

$$(I + tX)^\dagger (I + tX) = (I + tX^\dagger)(I + tX) = I + t (X^\dagger + X) + t^2 X^\dagger X$$

**3)** *1차 조건*.

$$X^\dagger + X = 0 \quad \Leftrightarrow \quad X^\dagger = -X$$

즉 *반에르미트(anti-Hermitian, skew-Hermitian)* 행렬.

**4)** *결과*.

$$\mathfrak{u}(N) = \{ X \in M_N(\mathbb{C}) : X^\dagger = -X \}$$

**5)** *$\mathfrak{u}(N)$ 의 차원*. 반에르미트 행렬 $X$ 의 *실* 자유도.
- 대각 성분 — $X_{ii} = -\overline{X_{ii}} \Rightarrow X_{ii}$ 는 *순허수*. $N$ 개 실 자유도.
- 비대각 성분 — $X_{ij} = -\overline{X_{ji}}$ 이라 $i < j$ 만 자유. $N(N-1)/2$ 쌍, 각 쌍이 *자유 복소수 (2 실 자유도)* — 총 $N(N-1)$ 실 자유도.

$$\dim \mathfrak{u}(N) = N + N(N-1) = N^2$$

(§0-1 §11 의 $\dim U(N) = N^2$ 와 일치.)

**6)** *주의 — 실 차원과 복소 차원*. $\mathfrak{u}(N)$ 은 *복소 행렬* 들의 모임이지만 *실 벡터 공간* — *복소 스칼라 배에 닫혀 있지 않다*. $X$ 가 반에르미트면 $iX$ 는 에르미트 ($X^\dagger = -X \Rightarrow (iX)^\dagger = -iX^\dagger = iX$). 즉 *실 스칼라 배만* 닫혀 있다.

따라서 $\mathfrak{u}(N)$ 은 *실 차원 $N^2$* 의 *실 벡터 공간*. (복소 벡터 공간으로는 만들 수 없는 구조.)

**7)** *예 — $\mathfrak{u}(1)$*. $1 \times 1$ 반에르미트 행렬 = 순허수 $\{i\alpha : \alpha \in \mathbb{R}\}$. 차원 1. *$U(1)$ 게이지의 생성자*.

### 7. 핵심 예 — $SU(N)$ 의 리 대수 $\mathfrak{su}(N)$

**1)** *$SU(N)$ 의 정의식*. $M^\dagger M = I$ *그리고* $\det M = 1$. (§0-1 §5.)

**2)** *유니타리 조건의 미분* — $X^\dagger = -X$ (§6 (3)).

**3)** *행렬식 조건의 미분*. $\det(I + tX)$ 의 $t$ 전개. Jacobi 공식 (§7 §3 (3)) 의 1차 형태

$$\det(I + tX) = 1 + t \, \text{tr}(X) + O(t^2)$$

(증명 — $\det \exp(Y) = \exp(\text{tr}(Y))$ 에서 $Y = tX$ 대입, $\exp(t \text{tr} X) = 1 + t \text{tr} X + O(t^2)$. 또는 $\det(I + tX) = $ 모든 $1 \times 1$ 소행렬식의 합 + 더 큰 항.)

$\det M = 1$ 이 1차로 성립하려면 1차 항 $= 0$ —

$$\text{tr}(X) = 0$$

**4)** *결과*.

$$\mathfrak{su}(N) = \{ X \in M_N(\mathbb{C}) : X^\dagger = -X, \ \text{tr}(X) = 0 \}$$

— *반에르미트 + 트레이스 0*.

**5)** *$\mathfrak{su}(N)$ 의 차원*. $\mathfrak{u}(N)$ ($N^2$ 차원) 에 *실 자유도 1 제거* ($\text{tr}(X) = 0$ 조건).

*왜 1만 제거되나*. 반에르미트의 $\text{tr}(X)$ 는 *대각 합* — 대각이 모두 순허수라 $\text{tr}(X)$ 가 순허수. $\text{tr}(X) = 0$ 이 *실 자유도 1 (허수부)* 제거.

$$\dim \mathfrak{su}(N) = N^2 - 1$$

**6)** *예 — $\mathfrak{su}(2)$*. $2 \times 2$ 반에르미트 + 트레이스 0. 일반 원소

$$X = i \begin{pmatrix} a & b - ic \\ b + ic & -a \end{pmatrix} = i(a \sigma_z + b \sigma_x + c \sigma_y), \quad a, b, c \in \mathbb{R}$$

자유도 3. 기저는 $\{i \sigma_x, i \sigma_y, i \sigma_z\}$ — *$i$ 곱한 파울리 행렬*.

(파울리 행렬 자체는 *에르미트* 라 $\mathfrak{su}(2)$ 에 직접 들어가지 않음. *$i$ 곱하면 반에르미트* — $\mathfrak{su}(2)$ 원소.)

**7)** *예 — $\mathfrak{su}(3)$*. 차원 $3^2 - 1 = 8$. 표준 기저는 *Gell-Mann 행렬* $\lambda_1, \cdots, \lambda_8$ — QCD의 색 생성자.

### 8. 추가 예 — $GL$, $SL$, $Sp$

**1)** *$GL(N, \mathbb{F})$* — $\det \neq 0$ 만 요구.

$I + tX$ 의 $\det = 1 + t \text{tr}(X) + O(t^2)$ 이 *$0$ 이 아님* 만 요구 — 작은 $t$ 에서 자동으로 $0$ 아님. 즉 *어떤 $X$ 든 OK*.

$$\mathfrak{gl}(N, \mathbb{F}) = M_N(\mathbb{F})$$

— *모든 행렬*. 차원 $N^2$ (실) 또는 $2N^2$ (실 자유도, 복소).

**2)** *$SL(N, \mathbb{F})$* — $\det = 1$.

위에서 본 것 — $\text{tr}(X) = 0$.

$$\mathfrak{sl}(N, \mathbb{F}) = \{ X \in M_N(\mathbb{F}) : \text{tr}(X) = 0 \}$$

차원 $N^2 - 1$ (실) 또는 $2(N^2 - 1)$ (복소).

**3)** *$Sp(2N, \mathbb{F})$* — $M^T \Omega M = \Omega$ ($\Omega$ 표준 심플렉틱 형식).

$$(I + tX)^T \Omega (I + tX) = \Omega + t (X^T \Omega + \Omega X) + O(t^2) = \Omega$$

1차 조건 —

$$X^T \Omega + \Omega X = 0$$

$$\mathfrak{sp}(2N, \mathbb{F}) = \{ X \in M_{2N}(\mathbb{F}) : X^T \Omega + \Omega X = 0 \}$$

차원 $N(2N+1)$ (실) 또는 $2N(2N+1)$ (복소).

**4)** *요약 표*.

| 리 군 | 리 대수 | 정의식 (미분 형태) | $\dim_{\mathbb{R}}$ |
|---|---|---|---|
| $GL(N, \mathbb{R})$ | $\mathfrak{gl}(N, \mathbb{R}) = M_N(\mathbb{R})$ | 제약 없음 | $N^2$ |
| $GL(N, \mathbb{C})$ | $\mathfrak{gl}(N, \mathbb{C}) = M_N(\mathbb{C})$ | 제약 없음 | $2N^2$ |
| $SL(N, \mathbb{R})$ | $\mathfrak{sl}(N, \mathbb{R})$ | $\text{tr}(X) = 0$ | $N^2 - 1$ |
| $SL(N, \mathbb{C})$ | $\mathfrak{sl}(N, \mathbb{C})$ | $\text{tr}(X) = 0$ | $2(N^2 - 1)$ |
| $O(N), SO(N)$ | $\mathfrak{so}(N)$ | $X^T = -X$ | $N(N-1)/2$ |
| $U(N)$ | $\mathfrak{u}(N)$ | $X^\dagger = -X$ | $N^2$ |
| $SU(N)$ | $\mathfrak{su}(N)$ | $X^\dagger = -X, \text{tr}(X) = 0$ | $N^2 - 1$ |
| $Sp(2N, \mathbb{F})$ | $\mathfrak{sp}(2N, \mathbb{F})$ | $X^T \Omega + \Omega X = 0$ | $N(2N+1)$ (실) |

§0-1 §10 (2) 의 표와 일관.

### 9. 벡터 공간 구조의 명시적 확인

행렬군의 리 대수가 *벡터 공간* (덧셈, 실 스칼라 배에 닫힘) 임을 정의식에서 직접 확인.

**1)** *왜 별도 확인이 필요한가*. $\mathfrak{g} = T_e G$ 가 *벡터 공간* 임은 §0-4 의 일반 다양체 결과로 자동. 그러나 *행렬 표현* 에서 정의식이 *선형 조건* 임을 직접 확인하는 것이 좋은 검증.

**2)** *$\mathfrak{so}(N)$ 확인*. $X, Y \in \mathfrak{so}(N)$ 즉 $X^T = -X, Y^T = -Y$.

- *덧셈* — $(X + Y)^T = X^T + Y^T = -X - Y = -(X+Y)$. 따라서 $X + Y \in \mathfrak{so}(N)$. ✓
- *스칼라 배* — $(cX)^T = c X^T = -cX$. $cX \in \mathfrak{so}(N)$. ✓
- *영원소* — $0^T = 0 = -0$. $0 \in \mathfrak{so}(N)$. ✓

→ $\mathfrak{so}(N)$ 이 *$M_N(\mathbb{R})$ 의 실 벡터 부분공간*.

**3)** *$\mathfrak{u}(N)$ 확인*. $X^\dagger + X = 0$ 이 *실 선형* 조건 (켤레 전치가 *반선형* 이라 실 스칼라 배에서만 보존). 따라서 $\mathfrak{u}(N)$ 이 *실 벡터 공간*. 

*주의* — 복소 스칼라 배 안 됨. $iX$ 의 켤레 전치 $(iX)^\dagger = -i X^\dagger = iX$ 라 *에르미트* 가 됨. $iX \notin \mathfrak{u}(N)$.

**4)** *$\mathfrak{su}(N)$ 확인*. $\mathfrak{u}(N)$ 조건 + $\text{tr}(X) = 0$. $\text{tr}$ 가 선형이라 덧셈·실 스칼라 배에서 보존. ✓ 실 벡터 공간.

**5)** *$\mathfrak{sp}(2N, \mathbb{F})$ 확인*. $X^T \Omega + \Omega X$ 가 $X$ 에 대해 선형. $X + Y$, $cX$ 에서 조건 보존. ✓

**6)** *일반 패턴*. *정의식의 미분이 1차 (선형) 조건* 이므로 *자동으로 벡터 공간 구조*. 이것이 *접공간이 벡터 공간임* 의 행렬군 차원의 구체적 발현.

### 10. 차원 일치 — $\dim \mathfrak{g} = \dim G$

**1)** *일반 다양체에서의 사실* (§0-4 §6 (4)). $\dim T_p M = \dim M$ — 접공간의 차원이 다양체 차원과 같다.

**2)** *리 군에서 적용*. $\dim \mathfrak{g} = \dim T_e G = \dim G$. 

§5–§8 에서 모든 예가 이 결과를 *직접* 확인한 셈 — $\mathfrak{so}(N)$, $\mathfrak{u}(N)$, $\mathfrak{su}(N)$, $\mathfrak{sp}(2N)$ 의 차원이 §0-1 §11, §2 §3 의 $\dim$ 표와 정확히 일치.

**3)** *의의*. 리 군의 *모든 차원 정보가 리 대수에 들어 있다*. 리 군의 분류 (Killing-Cartan, §3 §8) 가 *리 대수 분류로 환원* 되는 이유.

**4)** *비연결과의 관계*. 비연결 리 군에서도 *각 성분의 차원이 같음* (§0-3 §9). 리 대수는 *항등원 성분* 의 차원을 표현. $O(N)$ 과 $SO(N)$ 이 다른 군이지만 *같은 리 대수, 같은 차원*.

### 11. 이 절을 닫으며

이 절에서 점검한 것.

(1) *리 대수의 첫 정의* — $\mathfrak{g} := T_e G$. 벡터 공간 구조 자동 (§0-4).

(2) *행렬군의 리 대수 도출* — *정의식의 미분* 패턴. $I + tX$ 대입 후 1차 항이 $0$.

(3) *주요 행렬군의 리 대수* —
- $\mathfrak{so}(N)$ : $X^T = -X$ (반대칭)
- $\mathfrak{u}(N)$ : $X^\dagger = -X$ (반에르미트)
- $\mathfrak{su}(N)$ : 반에르미트 + 트레이스 0
- $\mathfrak{sl}(N, \mathbb{F})$ : 트레이스 0
- $\mathfrak{gl}(N, \mathbb{F})$ : 모든 행렬
- $\mathfrak{sp}(2N, \mathbb{F})$ : $X^T \Omega + \Omega X = 0$

(4) *벡터 공간 구조 직접 확인* — 정의식의 *선형성* 이 덧셈·실 스칼라 배 닫힘을 보장.

(5) *차원 일치* — $\dim \mathfrak{g} = \dim G$ 일반 결과. 리 군의 차원 정보가 리 대수에 완전 보존.

(6) *비연결과의 무관성* — 비연결 리 군 ($O(N)$) 과 그 항등원 성분 ($SO(N)$) 이 *같은 리 대수*. 리 대수는 *국소 (항등원 근방) 정보*.

(7) *불완전한 정의* — 이 절은 *벡터 공간 부분* 만. *리 괄호 구조* 가 §10 에서 추가, *야코비 항등식* 까지 §11 에서. 그제서야 *완전한 리 대수* 구조 완성.

다음 §9 에서 *리 대수 ↔ 1-매개변수 부분군 1:1 대응* 을 본격 증명한다 — 지금까지 예고만 했던 결과. *지수 사상이 두 방향을 정확히 잇는* 다리임을 명시.
