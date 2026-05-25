+++
title = "컴팩트 연결의 경우 — 전사성 증명과 직관"
weight = 17
+++

### 1. 이 절의 동기

§7 §6 와 §7 §10 에서 *지수 사상이 항등원 근방에서만 미분 동형사상*, *전역적으로는 단사·전사 둘 다 깨질 수 있음* 이라 예고했다. §2 §5 (1) 에서 *컴팩트 연결 리 군에서는 지수가 전사* 라는 정리를 간략히 언급했다.

이 절에서 이 정리를 *본격 다룬다*.

> *정리 (지수 사상의 전사성)*. 컴팩트 연결 리 군 $G$ 에 대해, 모든 $g \in G$ 에 대해 어떤 $X \in \mathfrak{g}$ 가 존재하여 $g = \exp(X)$.

즉 *컴팩트 연결의 모든 원소가 단일 지수* 로 표현. *전체 군이 리 대수의 지수 이미지*. 매우 강한 결과.

이 절은 (i) 정리의 정확한 진술, (ii) 증명 전략 (Hopf-Rinow), (iii) 행렬군에서 *스펙트럼 분해를 통한 직접 증명*, (iv) 컴팩트 가환 ($T^N$) 의 경우, (v) 단사성은 깨질 수 있음 (주기성), (vi) 구체 예 — $U(N), SU(N), SO(N)$ — 의 순서.

증명의 핵심 도구는 *리만 기하학* — 컴팩트 연결 리 군에 *불변 리만 메트릭* 을 잡으면, *1-매개변수 부분군이 측지선* 이 되고 *측지선 완비성* 으로 임의 점에 도달. 입문 수준에서는 *핵심 아이디어와 행렬군 직접 증명* 에 집중.

### 2. 정리의 정확한 진술

**1)** *정리 (지수 사상의 전사성)*.

> 컴팩트 연결 리 군 $G$ 에 대해
> $$\exp : \mathfrak{g} \to G \quad \text{이 전사 (surjective)}$$
> 즉 모든 $g \in G$ 에 대해 어떤 $X \in \mathfrak{g}$ 가 존재 ($\exp(X) = g$).

**2)** *주의 — 단사성은 보장 안 됨*. 정리는 *전사만* 주장. 같은 $g$ 에 대해 *여러 $X$* 가 가능. 예 — $U(1)$ 에서 $g = 1$ 에 대해 $X = 2\pi i n$ ($n \in \mathbb{Z}$) 가 모두 $\exp(X) = 1$.

**3)** *조건의 필수성*. 두 조건 *컴팩트 + 연결* 모두 필수.
- *비컴팩트* — 전사 깨짐 (§13). 예 $SL(2, \mathbb{R})$.
- *비연결* — 항등원 성분에만 도달, 다른 성분은 도달 못 함 (§14). 예 $O(N)$ 의 $\det = -1$ 부분.

**4)** *연결성의 의미*. 컴팩트 연결 리 군은 *전체가 항등원 성분*. 지수 이미지 $\exp(\mathfrak{g})$ 가 *항등원을 포함하는 연결 부분집합* — 만약 전사면 *전체* 가 도달됨.

### 3. 증명 전략 — Hopf-Rinow 와 리만 기하

증명의 *핵심 아이디어* 를 짚는다. 완전한 증명은 미분기하학 교재에 (예 — Helgason 의 *Differential Geometry, Lie Groups, and Symmetric Spaces*).

**1)** *컴팩트 연결 리 군에 불변 리만 메트릭 도입*. 컴팩트 리 군 $G$ 위에는 *왼쪽·오른쪽 모두 불변인 리만 메트릭* $\langle \cdot, \cdot \rangle$ 이 존재.

*구성 방법* (Weyl unitary trick) — 임의의 양의 정부호 내적을 $\mathfrak{g}$ 에 놓고, *Haar 측도로 군 평균* 해서 $\text{Ad}$-불변 내적을 얻음. 이를 *왼쪽 옮김* 으로 모든 점에 확장 — 왼쪽·오른쪽 모두 불변.

*핵심 — 컴팩트성 필요*. Haar 측도가 *유한* 이어야 평균이 잘 정의. 비컴팩트는 안 됨.

**2)** *측지선 = 1-매개변수 부분군*. 위 메트릭에서 *측지선 (geodesic)* 이 정확히 *1-매개변수 부분군 $\exp(tX)$* 와 일치 (또는 그 왼쪽 옮김).

직관 — *지수 사상이 "최단 경로" 를 만든다*. $\exp(tX)$ 가 $X$ 방향으로의 *상수 속도 측지선*.

**3)** *Hopf-Rinow 정리*.

> *Hopf-Rinow 정리*. 컴팩트 연결 리만 다양체는 *측지적으로 완비 (geodesically complete)* — 모든 측지선이 *모든 $t \in \mathbb{R}$ 에서 정의됨*. 또한 *임의 두 점이 측지선으로 연결*.

(컴팩트성으로부터 자동으로 측지적 완비성 따라옴.)

**4)** *정리 적용*. 임의 $g \in G$ 와 항등원 $e$ 가 *측지선으로 연결*. 그 측지선은 *1-매개변수 부분군* — 즉

$$\gamma(t) = \exp(tX), \quad \gamma(0) = e, \quad \gamma(1) = g$$

인 $X \in \mathfrak{g}$ 존재. 따라서 $g = \exp(X)$. *전사*. ∎

**5)** *증명 흐름 요약*.
- 컴팩트 → Haar 측도 유한 → $\text{Ad}$-불변 내적 → 양변 불변 리만 메트릭
- 1-매개변수 부분군 = 측지선
- 컴팩트 → 측지적 완비 (Hopf-Rinow) → 모든 두 점 측지선 연결
- 항등원과 $g$ 잇는 측지선 = $\exp(tX)$ → $g = \exp(X)$

### 4. 행렬군에서의 직접 증명 — 스펙트럼 분해

행렬 컴팩트 연결 리 군의 경우, *스펙트럼 분해* 를 직접 사용한 명시적 증명이 가능. 직관에 도움.

**1)** *$U(N)$ 의 경우*. 임의 $U \in U(N)$ 의 *스펙트럼 분해*

$$U = \sum_i e^{i\theta_i} |u_i\rangle \langle u_i|$$

(유니타리 → 정규 연산자, 고유값 모듈러스 1, 정규 직교 고유벡터.)

각 고유값 $\lambda_i = e^{i\theta_i}$ 에 대해 *로그* 잡으면 — $\log \lambda_i = i\theta_i$ (선택, $\theta_i \in (-\pi, \pi]$).

*반에르미트 행렬* $X$ 구성

$$X = \sum_i i\theta_i \, |u_i\rangle \langle u_i| \in \mathfrak{u}(N)$$

— 고유값 $i\theta_i$ 가 순허수이므로 반에르미트. 확인 — $X^\dagger = \sum_i \overline{i\theta_i} |u_i\rangle \langle u_i| = \sum_i (-i\theta_i) |u_i\rangle \langle u_i| = -X$. ✓

**2)** *$\exp(X) = U$ 확인*. §7 §8 의 스펙트럼 분해 공식

$$\exp(X) = \sum_i e^{i\theta_i} |u_i\rangle \langle u_i| = U$$

✓.

*결론* — 모든 $U \in U(N)$ 가 어떤 $X \in \mathfrak{u}(N)$ 에 대해 $U = \exp(X)$. 전사. ∎

**3)** *$SU(N)$ 의 경우*. $U \in SU(N)$ 는 $\det U = 1$ 추가. 위 구성에서

$$\det U = \prod_i e^{i\theta_i} = e^{i \sum \theta_i} = 1 \implies \sum_i \theta_i \in 2\pi \mathbb{Z}$$

$X$ 의 $\text{tr}$ — $\text{tr}(X) = \sum_i i\theta_i = i \sum_i \theta_i$. 

$\sum \theta_i$ 가 일반적으로 $2\pi n$ ($n \in \mathbb{Z}$) — 안 $0$ 일 수 있다.

*해결* — 고유값의 *로그 선택* 을 조정해 $\sum \theta_i = 0$ 으로 만든다. $\theta_i \to \theta_i - 2\pi n / N$ 같은 *이동*. 새 $\theta_i'$ 도 $e^{i\theta_i'} = e^{i\theta_i}$ (변화는 $2\pi$ 배수) 이라 $\exp$ 결과 그대로. 그리고 $\sum \theta_i' = 0$ 이 되도록 조정.

→ $X = \sum i \theta_i' |u_i\rangle \langle u_i| \in \mathfrak{su}(N)$ (반에르미트 + tr 0) 존재. $\exp(X) = U$. ∎

**4)** *$SO(N)$ 의 경우* (조금 더 미묘). $R \in SO(N)$ 의 *실 표준형* 은 $2\times 2$ 회전 블록과 (홀수 차원 시) $1$ 블록으로 분해

$$R = O \begin{pmatrix} R(\theta_1) & & & \\ & R(\theta_2) & & \\ & & \ddots & \\ & & & 1 \end{pmatrix} O^T$$

($O \in O(N)$ 직교 행렬, $R(\theta_k)$ 는 $2 \times 2$ 회전.) 각 $R(\theta_k) = \exp(\theta_k J_k)$ (§6 §10) 인데 $J_k$ 가 반대칭 ($\in \mathfrak{so}(N)$). 직접 종합으로

$$R = O \exp(A) O^T = \exp(O A O^T)$$

where $A$ 가 블록 대각 반대칭 행렬. $OAO^T$ 도 반대칭 → $\in \mathfrak{so}(N)$. $\exp(OAO^T) = R$. ∎

### 5. 컴팩트 가환의 경우 — 토러스 $T^N$

가환 컴팩트 연결 리 군은 *토러스 $T^N$* (§3 §4). 지수 사상이 어떻게 동작하는지 본다.

**1)** *$T^N = (U(1))^N$ 의 리 대수* — $\mathfrak{u}(1)^N \cong i \mathbb{R}^N$.

**2)** *지수 사상*. $X = (i\alpha_1, \cdots, i\alpha_N) \in i\mathbb{R}^N$ 에 대해

$$\exp(X) = (e^{i\alpha_1}, \cdots, e^{i\alpha_N}) \in T^N$$

**3)** *전사 확인*. 임의 $(e^{i\theta_1}, \cdots, e^{i\theta_N}) \in T^N$ 에 대해 $X = (i\theta_1, \cdots, i\theta_N)$ 잡으면 $\exp(X) = (e^{i\theta_1}, \cdots, e^{i\theta_N})$. ✓ 전사.

**4)** *단사 깨짐 — 격자 주기성*. $\exp(X_1) = \exp(X_2)$ ⟺ $X_2 - X_1 \in 2\pi i \mathbb{Z}^N$ — *$2\pi$ 배수 격자만큼 다름*.

따라서 *$\exp$ 의 단사가 깨지는 곳* 이 *격자 $2\pi i \mathbb{Z}^N \subset \mathfrak{g}$*. 이 격자가 *기본군 $\pi_1(T^N) = \mathbb{Z}^N$* 과 1:1 대응. *위상적 정보* 가 격자에 인코딩.

**5)** *일반 컴팩트 가환에서의 패턴*. 컴팩트 가환 연결 리 군이 $T^N$ 이라 $\exp$ 가 전사 + 격자만큼 단사 깨짐. *기본군이 격자로 나타남*. 핵심 시각 — *컴팩트 가환 리 군 = 리 대수 / 격자*.

### 6. 단사성은 깨질 수 있음 — 비가환의 경우

가환에서는 *격자 주기성* 으로 단사 깨짐. 비가환에서는 어떻게 되는가.

**1)** *$U(1)$ — 가장 단순*. $\exp(i\theta) = e^{i\theta}$, $2\pi$ 주기.

**2)** *$SU(2)$* — 단순연결, 컴팩트, 비가환. $\mathfrak{su}(2)$ 의 일반 원소 $X = i(a\sigma_x + b\sigma_y + c\sigma_z)$ 에 대해 §9 §9 (3) 의 공식

$$\exp(X) = \cos(r) I + i \frac{\sin(r)}{r} (a\sigma_x + b\sigma_y + c\sigma_z), \quad r = \sqrt{a^2 + b^2 + c^2}$$

$r = \pi$ 에서 $\exp(X) = -I$ — *방향 무관*. 즉 *반지름 $\pi$ 인 $\mathfrak{su}(2)$ 의 구면 전체가 $-I$ 한 점으로* 매핑.

→ *전사하지만 심하게 비단사*. 정상.

**3)** *일반 컴팩트 연결 — 단사 깨짐의 위치*. 단사가 깨지는 곳이 *지수 사상의 임계점 (critical points)*. 이들이 *위상적 정보 (기본군, 켤레류 등) 를 인코딩*. 자세한 분석은 *최대 토러스 (maximal torus)* 와 *Weyl 군* 의 이론 — 본 시리즈에서 다루지 않음.

**4)** *결과 — 컴팩트 연결의 지수 사상의 모습*.

| 성질 | 컴팩트 연결 |
|---|---|
| 전사? | ✓ (모든 $g \in G$ 가 $\exp(X)$) |
| 단사? | ✗ (가환은 격자, 비가환은 특이점) |
| 결과 | *덮개 사상* — $\mathfrak{g}$ 가 $G$ 의 *덮개* (위상적 의미는 아니지만 비슷한 그림) |

### 7. 컴팩트성의 필요성 — 비컴팩트 반례 미리

§13 의 예고로, *컴팩트성이 필수* 임을 한 예로 본다.

**1)** *$SL(2, \mathbb{R})$ — 비컴팩트 연결*. $\det = 1$ 인 $2 \times 2$ 실 행렬.

**2)** *반례 — $\exp$ 의 이미지에 없는 원소*.

$$M = \begin{pmatrix} -1 & 1 \\ 0 & -1 \end{pmatrix} \in SL(2, \mathbb{R})$$

(확인 — $\det M = (-1)(-1) - 1 \cdot 0 = 1$, OK.)

**3)** *$M = \exp(X)$ 가 가능한가*. $X \in \mathfrak{sl}(2, \mathbb{R})$ — 트레이스 0 $2 \times 2$ 실 행렬.

만약 $M = \exp(X)$ 면, $\det M = \exp(\text{tr}(X)) = \exp(0) = 1$ ✓ (필요 조건 만족).

그러나 $\text{tr}(M) = -2$ 가 *문제*. $\exp(X)$ 의 트레이스 분석으로 (§13 §3 본격) — $\text{tr}(\exp X) = -2$ 가 가능한 $X \in \mathfrak{sl}(2, \mathbb{R})$ 가 있지만, *그 $X$ 에 대해 $\exp(X) = -I$* 만 가능 ($X$ 의 고유값이 $\pm i\pi$ — 회전 행렬 형태). $M \neq -I$ 이라 도달 못 함.

→ $M \notin \exp(\mathfrak{sl}(2, \mathbb{R}))$. 비전사.

**4)** *해결* (§13). *지수의 곱* 으로 도달 가능 — $M = \exp(X_1) \exp(X_2)$. *단일 $\exp$* 만으로는 비컴팩트에서 부족.

### 8. 구체 적용 — $SU(N)$ 의 모든 원소

컴팩트 연결의 핵심 예 — $SU(N)$ — 에서 정리의 직접 활용.

**1)** *주장*. 모든 $U \in SU(N)$ 가 어떤 *반에르미트 트레이스 0 행렬* $H \in \mathfrak{su}(N)$ 에 대해 $U = \exp(H)$.

**2)** *물리적 의미*. *모든 $SU(N)$ 변환이 지수 형태 $\exp(i T)$* ($T = -iH$ 가 *에르미트 트레이스 0*). 양자역학에서 *모든 유니타리 변환이 에르미트 생성자의 지수*. *해밀토니안이 모든 가능 시간 진화를 만든다* 의 군 이론적 기반.

**3)** *$SU(2)$ 구체*. §9 §9 (3) 의 공식 — 모든 $U \in SU(2)$ 가

$$U = \cos(r/2) I + i \sin(r/2) (\hat n \cdot \vec \sigma)$$

($\hat n$ 단위 벡터, $r \in [0, 2\pi]$.) *축 $\hat n$ + 각도 $r$* 으로 매개변수화 — *모든 회전이 축-각 표현*. 

이때 $X = i (r/2)(\hat n \cdot \vec \sigma) \in \mathfrak{su}(2)$. 전사성 확인.

**4)** *$SU(3)$ — QCD*. QCD 의 게이지 변환이 $SU(3)$ 의 원소. 모두 $\exp(i \sum_a \alpha_a \lambda_a)$ 형태 ($\lambda_a$ Gell-Mann 행렬). 8 개의 *실 매개변수* $\alpha_a$ 로 *모든 색 변환* 표현.

### 9. 구체 적용 — $SO(N)$ 의 모든 회전

**1)** *주장*. 모든 회전 $R \in SO(N)$ 가 어떤 *반대칭 행렬* $A \in \mathfrak{so}(N)$ 에 대해 $R = \exp(A)$.

**2)** *$SO(3)$ — Rodrigues 공식*. 축 $\hat n \in S^2$, 각도 $\theta \in [0, \pi]$ 회전이

$$R = \exp(\theta A_{\hat n}), \quad A_{\hat n} = \hat n \cdot \vec L$$

($L_1, L_2, L_3$ 가 §8 §5 (8) 의 $\mathfrak{so}(3)$ 기저.) *모든 회전이 축-각도 표현*.

**3)** *명시적 형태* — Rodrigues 공식

$$R = \cos\theta \, I + \sin\theta \, A_{\hat n} + (1 - \cos\theta) \hat n \hat n^T$$

(§17 본격.)

**4)** *$SO(N)$ 일반* (§4 (4) 의 구성). 임의 $R$ 가 *블록 대각화* 후 각 $2 \times 2$ 회전 블록을 $\exp(\theta_k J_k)$ 로 표현, 종합해 $R = \exp(A)$. 

### 10. Haar 측도와 지수의 야코비안 (참고)

전사성을 *측도 이론적* 으로 활용하는 응용을 간단히 짚는다.

**1)** *컴팩트 연결의 지수 매개변수화*. $\exp$ 가 전사이므로, *$G$ 위 적분이 $\mathfrak{g}$ 위 적분으로 환원* 가능.

$$\int_G f(g) \, d\mu(g) = \int_{\mathfrak{g}} f(\exp X) \, |J(X)| \, dX$$

여기 $J(X)$ 가 *지수 사상의 야코비안*. 본 시리즈에서 명시하지는 않지만, *컴팩트 군 위 적분의 표준 도구*.

**2)** *야코비안 공식*. $J(X) = \det\left( \frac{1 - e^{-\text{ad}_X}}{\text{ad}_X} \right)$. (Helgason 의 책 참조.) 

**3)** *응용*. 표현론의 *문자 (characters)*, Plancherel 측도, 양자장론의 게이지 평균 등이 이 형태를 활용.

### 11. 이 절을 닫으며

이 절에서 점검한 것.

(1) *주 정리* — 컴팩트 연결 리 군에서 $\exp : \mathfrak{g} \to G$ 가 *전사*. 모든 $g = \exp(X)$ 형태.

(2) *증명 전략* — Hopf-Rinow + 불변 리만 메트릭. 1-매개변수 부분군 = 측지선, 컴팩트 → 완비 → 모든 두 점 측지선 연결.

(3) *행렬군 직접 증명* — 스펙트럼 분해. $U(N)$ 에서 고유값 $e^{i\theta_i}$ → $X = \sum i\theta_i |u_i\rangle\langle u_i|$ 로 직접 구성. $SU(N), SO(N)$ 도 유사.

(4) *컴팩트 가환 $T^N$* — 격자 $2\pi i \mathbb{Z}^N$ 만큼 단사 깨짐. 컴팩트 가환 = 리 대수 / 격자.

(5) *단사성 깨짐* — 가환은 격자, 비가환은 특이점 (예 $SU(2)$ 에서 $r = \pi$ 구면 전체가 $-I$).

(6) *컴팩트성의 필수성* — $SL(2, \mathbb{R})$ 반례 미리 (§13 본격).

(7) *물리 응용* — $SU(N)$ 모든 유니타리가 에르미트 생성자의 지수, $SO(N)$ 모든 회전이 축-각 표현 (Rodrigues).

다음 §13 에서 *비컴팩트의 경우* — $SL(2, \mathbb{R})$ 같은 군에서 *지수가 전사 안 되는* 구체적 분석과 *지수의 곱이 필요* 한 이유를 본격 다룬다.
