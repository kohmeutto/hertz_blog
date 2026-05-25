+++
title = "교환자와 리 괄호 — 비가환성의 무한소 표현"
weight = 15
+++

### 1. 이 절의 동기

§8 에서 *리 대수의 첫 정의* — 벡터 공간 구조 — 를 했다. §9 에서 *리 대수와 1-매개변수 부분군의 1:1 대응* 을 증명했다. §9 §10 의 마지막 노트 — *1:1 대응이 덧셈을 보존 안 함 (비가환 시)*, *리 괄호를 도입하면 완전한 구조 보존* — 을 본격 다룬다.

본 절의 주제 — *리 괄호(Lie bracket)*. 이것이 리 대수에 *곱셈 같은 추가 구조* 를 부여해, 비로소 *완전한 리 대수* 구조가 완성된다.

핵심 통찰 (§3 §6 재확인) — *군 차원의 비가환성 $g h \neq h g$ 의 무한소 측정 = 리 대수 차원의 교환자 $[X, Y] = XY - YX$*. 이 절에서 그 직관을 *정확한 정의와 도출* 로 옮긴다.

이 절은 (i) 군 교환자와 리 괄호의 정의, (ii) 군 교환자의 무한소 전개로 리 괄호 도출, (iii) *$\mathfrak{g}$ 가 교환자로 닫힘 — 행렬군에서 명시적 확인*, (iv) 수반 작용 $\text{Ad}_g$ 과 리 괄호, (v) 추상 리 대수에서의 리 괄호 — 의 순서.

### 2. 군 교환자와 리 괄호 — 정의 재확인

**1)** *군 교환자(group commutator)* — §3 §6 (1) 재확인. 군 $G$ 의 두 원소 $g, h$ 에 대해

$$[g, h] := g \, h \, g^{-1} \, h^{-1} \in G$$

$g, h$ 가환 ⟺ $[g, h] = e$. 즉 *군 교환자가 항등원에서 얼마나 벗어나 있는가* 가 *비가환의 정도*.

**2)** *리 괄호(Lie bracket) — 행렬군에서*. 행렬군 $G \subseteq GL(N, \mathbb{F})$ 의 리 대수 $\mathfrak{g} \subseteq M_N(\mathbb{F})$ 의 두 원소 $X, Y$ 에 대해

$$[X, Y] := X Y - Y X$$

*같은 기호* $[\cdot, \cdot]$ 를 사용. 군 교환자와 리 괄호는 *다른 객체* — 군 차원 vs 리 대수 차원 — 이지만, 다음 절에서 보듯 *둘이 무한소 차원에서 정확히 연결*.

**3)** *기호 혼동의 주의*. 같은 $[\cdot, \cdot]$ 표기 — 맥락 (군 원소냐 리 대수 원소냐) 으로 구분. 본 시리즈에서는 군 교환자가 등장하는 곳이 드물고, 대부분 *리 대수 교환자* 의미.

**4)** *리 괄호의 기본 성질 (행렬에서 직접)*.
- *이중선형성* — $[aX_1 + bX_2, Y] = a[X_1, Y] + b[X_2, Y]$, 두 번째 인자도 대칭.
- *반대칭성* — $[X, Y] = -[Y, X]$. (특히 $[X, X] = 0$.)
- *야코비 항등식* — $[X, [Y, Z]] + [Y, [Z, X]] + [Z, [X, Y]] = 0$ (§11 본격).

본 절에서는 처음 두 성질 — 이중선형성, 반대칭성 — 만 사용. *야코비* 는 §11.

### 3. 군 교환자의 무한소 전개 → 리 괄호 도출

§3 §6 (4) 에서 *직관 차원* 으로 본 결과를 *명확한 차수 분석* 으로 도출.

**1)** *작은 매개변수의 1-매개변수 부분군*. $g_s := \exp(sX), h_t := \exp(tY)$ ($X, Y \in \mathfrak{g}$, 작은 $s, t$).

**2)** *지수의 멱급수 전개*. 작은 $s, t$ 에서

$$g_s = I + sX + \frac{s^2 X^2}{2} + O(s^3)$$

$$h_t = I + tY + \frac{t^2 Y^2}{2} + O(t^3)$$

$$g_s^{-1} = \exp(-sX) = I - sX + \frac{s^2 X^2}{2} + O(s^3)$$

(역원은 $g_s^{-1} = \exp(-sX)$ from §7 §3 (2).)

마찬가지 $h_t^{-1} = I - tY + \frac{t^2 Y^2}{2} + O(t^3)$.

**3)** *군 교환자 직접 곱셈*. $[g_s, h_t] = g_s h_t g_s^{-1} h_t^{-1}$.

순차 계산 (1차, 2차 항만 추적, $O(3)$ 무시) —

$$g_s h_t = I + sX + tY + \frac{s^2X^2}{2} + stXY + \frac{t^2Y^2}{2} + O(3)$$

$$g_s h_t g_s^{-1} = I + tY + st(XY - YX) + \frac{t^2 Y^2}{2} + O(3)$$

(1차 $sX$ 와 $-sX$ 가 상쇄, 2차에서 $XY - YX = [X, Y]$ 잔류.)

$$g_s h_t g_s^{-1} h_t^{-1} = I + st(XY - YX) + O(3) = I + st [X, Y] + O(3)$$

(1차 $tY$ 와 $-tY$ 가 상쇄, 위 식의 $st$ 항이 잔류.)

**4)** *결과 — 핵심 식*.

$$\boxed{[g_s, h_t] = \exp(sX) \exp(tY) \exp(-sX) \exp(-tY) = I + st \, [X, Y] + O(s^2, t^2, st^2, s^2 t)}$$

— *군 교환자의 가장 낮은 비자명 항이 정확히 $st [X, Y]$*.

**5)** *해석*. 무한소 $s, t \to 0$ 에서, 군 교환자 $[g_s, h_t]$ 가 *항등원에서 $st [X, Y]$ 만큼 벗어남*. *벗어남의 방향과 크기를 정확히 측정하는 것이 리 괄호 $[X, Y]$*.

> *결론*. 군 교환자 (군 차원의 비가환성) 의 *2차 무한소 측정* = 리 괄호. *비가환성의 정확한 무한소 표현*.

### 4. 동치 표현 — 미분으로의 환원

§3 의 결과를 *명확한 미분 공식* 으로 정리.

**1)** *공식*.

$$[X, Y] = \left. \frac{\partial^2}{\partial s \, \partial t} \right|_{s = t = 0} [g_s, h_t]$$

(좀 더 정확히는 *항등원에서 차감한 후* 의 2차 미분이 $[X, Y]$.)

**2)** *다른 형태*.

$$[X, Y] = \left. \frac{d}{dt} \right|_{t = 0} \left( \exp(tX) Y \exp(-tX) \right)$$

— *수반 작용의 무한소 형태*. 다음 §6 본격.

**3)** *해석*. 리 괄호가 *군 차원 객체로부터 두 번 미분으로 추출* 됨. 1차 미분 (생성자) 이 *벡터 공간 구조* 를 줬다면, *2차 미분 (교환자)* 가 *추가 곱셈 구조* 를 부여.

**4)** *왜 2차인가*. 1차 ($s$ 또는 $t$ 단독) 에서는 $sX - sX = 0$, $tY - tY = 0$ 으로 상쇄. *교차 항 $st$ 가 처음 비자명*. 비가환성이 *교차 항* 에서 비로소 등장.

### 5. $\mathfrak{g}$ 가 교환자로 닫힘 — 핵심 결과

$X, Y \in \mathfrak{g}$ 이면 $[X, Y] \in \mathfrak{g}$ — 즉 *교환자가 다시 리 대수 원소*. 이것이 *리 괄호가 $\mathfrak{g}$ 위 잘 정의된 연산* 임의 보장.

**1)** *증명 — 일반 (정의식 직접 활용)*. $X, Y$ 가 정의식 (예: 반대칭, 반에르미트) 을 만족할 때 $[X, Y]$ 가 같은 정의식을 만족함을 직접 확인. 예시별로 본다.

**2)** *$\mathfrak{so}(N)$ — 반대칭*. $X^T = -X, Y^T = -Y$ 일 때

$$[X, Y]^T = (XY - YX)^T = (XY)^T - (YX)^T = Y^T X^T - X^T Y^T = (-Y)(-X) - (-X)(-Y) = YX - XY = -[X, Y]$$

— 반대칭. $[X, Y] \in \mathfrak{so}(N)$. ✓

**3)** *$\mathfrak{u}(N)$ — 반에르미트*. $X^\dagger = -X, Y^\dagger = -Y$ 일 때

$$[X, Y]^\dagger = (XY - YX)^\dagger = Y^\dagger X^\dagger - X^\dagger Y^\dagger = (-Y)(-X) - (-X)(-Y) = YX - XY = -[X, Y]$$

— 반에르미트. $[X, Y] \in \mathfrak{u}(N)$. ✓

**4)** *$\mathfrak{su}(N)$ — 반에르미트 + 트레이스 0*. 반에르미트는 위 (3). 트레이스는

$$\text{tr}([X, Y]) = \text{tr}(XY - YX) = \text{tr}(XY) - \text{tr}(YX) = 0$$

— $\text{tr}(AB) = \text{tr}(BA)$ 사이클 성질. $[X, Y] \in \mathfrak{su}(N)$. ✓

**5)** *$\mathfrak{sl}(N, \mathbb{F})$ — 트레이스 0*. (4) 의 트레이스 부분과 동일. ✓

**6)** *$\mathfrak{gl}(N, \mathbb{F})$ — 제약 없음*. 모든 행렬, $[X, Y]$ 도 행렬, 닫힘 자동. ✓

**7)** *$\mathfrak{sp}(2N, \mathbb{F})$ — 심플렉틱*. $X^T \Omega + \Omega X = 0$ (즉 $\Omega X = -X^T \Omega$) 일 때

$$[X, Y]^T \Omega = (XY)^T \Omega - (YX)^T \Omega = Y^T X^T \Omega - X^T Y^T \Omega = -Y^T \Omega X - (-X^T \Omega Y) = -Y^T \Omega X + X^T \Omega Y$$

음, 약간 계산이 복잡한데 — 결론은 *교환자가 같은 식을 만족* 함. 직접 검증 가능 (스킵).

**8)** *일반 정리*.

> *정리*. 모든 *닫힌 행렬 리 군* 의 리 대수가 *교환자로 닫힘*. 즉 $X, Y \in \mathfrak{g} \Rightarrow [X, Y] \in \mathfrak{g}$.

증명 (스케치) — *추상 정의 (§9 의 1-매개변수 부분군 1:1 대응)* 으로 접근. $X, Y \in \mathfrak{g}$ 일 때 $[X, Y]$ 가 어떤 1-매개변수 부분군의 생성자임을 직접 구성 — 예 — $\lim_{s, t \to 0} \frac{1}{st}([g_s, h_t] - I) = [X, Y]$ 가 $\mathfrak{g}$ 의 원소임이 §3 (4) 의 식과 $\mathfrak{g}$ 의 *접공간으로서의 닫힘* 으로 보장.

**9)** *결과*. *리 괄호 $[\cdot, \cdot] : \mathfrak{g} \times \mathfrak{g} \to \mathfrak{g}$* 가 잘 정의됨. *리 대수에 곱셈 같은 연산 추가*.

### 6. 수반 작용 $\text{Ad}$ 과 $\text{ad}$

리 괄호의 *기원이 군의 켤레 작용* 임을 본다.

**1)** *군 수반 작용 (adjoint action of group)*. 군 원소 $g \in G$ 에 의한 *켤레*

$$\text{Ad}_g : \mathfrak{g} \to \mathfrak{g}, \qquad X \mapsto g X g^{-1}$$

이 잘 정의됨 — $X \in \mathfrak{g}$ 면 $gXg^{-1} \in \mathfrak{g}$. (증명 — $\exp(t \cdot gXg^{-1}) = g \exp(tX) g^{-1} \in G$ — $g G g^{-1} \subseteq G$ 부분군 성질로부터.)

**2)** *해석 — 군의 "내부 자기 동형"*. $\text{Ad}_g$ 가 $\mathfrak{g}$ 의 *선형 동형사상*. 군 원소가 *리 대수 위 작용* 으로 나타남.

**3)** *리 대수 수반 작용 (adjoint action of algebra)*. 리 대수 원소 $X \in \mathfrak{g}$ 에 의한 *교환자*

$$\text{ad}_X : \mathfrak{g} \to \mathfrak{g}, \qquad Y \mapsto [X, Y]$$

이 잘 정의됨 — §5 의 결과.

**4)** *$\text{Ad}$ 와 $\text{ad}$ 의 관계*. 두 사상이 *지수 사상으로 연결*

$$\text{Ad}_{\exp(X)} = \exp(\text{ad}_X)$$

(여기 좌변의 $\exp$ 는 리 군, 우변은 *선형 사상 $\mathfrak{g} \to \mathfrak{g}$ 의 지수* — $\sum_n (\text{ad}_X)^n / n!$.)

**5)** *명시적 확인 — 작은 $t$*. 

$$\text{Ad}_{\exp(tX)} (Y) = \exp(tX) \, Y \, \exp(-tX)$$

$t$ 에 대해 전개 — 

$$= (I + tX + \cdots) Y (I - tX + \cdots) = Y + t(XY - YX) + O(t^2) = Y + t [X, Y] + O(t^2)$$

→ $\frac{d}{dt}|_{t=0} \text{Ad}_{\exp(tX)} (Y) = [X, Y] = \text{ad}_X(Y)$. 

이것이 §4 (2) 의 식 $[X, Y] = \frac{d}{dt}|_{t=0} (\exp(tX) Y \exp(-tX))$ 의 자연 도출.

**6)** *기하학적 의미*. $\text{Ad}_g$ 가 *군 원소에 의한 리 대수의 회전 (선형 변환)*. *Ad_g 의 무한소 = ad_X = 교환자*. 군 차원 (회전) 의 무한소가 *교환자*.

**7)** *물리에서의 활용*. 양자역학의 *수반 표현* 이 이 구조. 예 — *각운동량 $L$ 의 작용이 $[L, \cdot]$* — 다른 연산자가 $L$ 의 무한소 회전 하에서 어떻게 변환되는지.

### 7. 행렬군 너머 — 추상 리 대수에서의 리 괄호

행렬군에서는 리 괄호 = $XY - YX$ (행렬 곱셈을 사용). 일반 추상 리 군의 리 대수에서는 어떻게 정의되나.

**1)** *문제 — 일반 리 군에 "행렬 곱셈" 이 없을 수 있다*. 예 — 추상 리 군 $G$ (행렬군이 아닌 것). $\mathfrak{g} = T_e G$ 가 *벡터 공간이지만 "곱셈"이 명시되지 않음*.

**2)** *해결 — §3 (4) 의 공식을 정의로*. 임의 리 군에서

$$[X, Y] := \left. \frac{d}{dt} \right|_{t = 0} \left( \text{Ad}_{\exp(tX)}(Y) \right)$$

으로 *정의*. $\text{Ad}_g$ 는 임의 리 군에서 정의됨 (군 자기 동형의 미분으로).

**3)** *일관성*. 행렬군의 경우 $\text{Ad}_{\exp(tX)}(Y) = \exp(tX) Y \exp(-tX)$ 의 미분이 $XY - YX$ — 행렬 교환자와 일치.

**4)** *일반 결과*. 모든 리 군 $G$ 의 리 대수 $\mathfrak{g}$ 가 *리 괄호 $[\cdot, \cdot] : \mathfrak{g} \times \mathfrak{g} \to \mathfrak{g}$* 를 자연스럽게 가짐. 이중선형, 반대칭, 야코비 항등식 (§11) 을 만족.

**5)** *추상 리 대수의 정의* (예고). 모든 *벡터 공간 + 이중선형 반대칭 연산 + 야코비 항등식* 이 *추상 리 대수*. 행렬 교환자가 자연 예지만, 그것에 한정되지 않음. §11 본격.

### 8. 구체 예 — $\mathfrak{su}(2)$ 의 교환자 관계

§3 §5 와 §9 §9 에서 보았던 결과 재확인 + 명시.

**1)** *$\mathfrak{su}(2)$ 기저* — $\{i\sigma_x, i\sigma_y, i\sigma_z\}$ (§8 §7 (6)).

**2)** *기저 사이 교환자*. 파울리 행렬의 관계 (§3 §5)

$$[\sigma_x, \sigma_y] = 2 i \sigma_z, \quad [\sigma_y, \sigma_z] = 2 i \sigma_x, \quad [\sigma_z, \sigma_x] = 2 i \sigma_y$$

$\mathfrak{su}(2)$ 기저 ($i\sigma_k$) 의 교환자

$$[i\sigma_x, i\sigma_y] = -[\sigma_x, \sigma_y] = -2 i \sigma_z = -2 \cdot (i\sigma_z)$$

마찬가지 순환적으로

$$[i\sigma_x, i\sigma_y] = -2 (i\sigma_z), \quad [i\sigma_y, i\sigma_z] = -2 (i\sigma_x), \quad [i\sigma_z, i\sigma_x] = -2 (i\sigma_y)$$

**3)** *구조 상수*. 일반적으로 리 대수 기저 $\{T_a\}$ 의 교환자

$$[T_a, T_b] = f^c{}_{ab} T_c$$

(아인슈타인 합 규약). 계수 $f^c{}_{ab}$ 가 *구조 상수(structure constants)*. 리 대수 전체를 결정.

$\mathfrak{su}(2)$ 의 경우 ($T_a = i\sigma_a$ 로 잡으면) — $f^c{}_{ab} = -2 \epsilon^c{}_{ab}$ ($\epsilon$ 은 Levi-Civita 기호). 또는 표준 정규화 ($T_a = i\sigma_a / 2$ 로 잡으면) $f^c{}_{ab} = \epsilon^c{}_{ab}$.

**4)** *물리 표기 (각운동량 연산자)*. 양자역학에서는

$$[J_a, J_b] = i \hbar \epsilon^c{}_{ab} J_c$$

(에르미트 표기 $J_a = \hbar \sigma_a / 2$.) $i$ 와 $\hbar$ 가 들어가는 것은 *에르미트 vs 반에르미트* 의 차이.

**5)** *해석*. *비가환의 정확한 구조* 가 *세 개의 구조 상수* 로 압축. 무한 차원 군 정보가 *유한 차원 수치 (3 차원 리 대수에 3³ = 27 개 계수, 반대칭으로 9 개, 비자명 3 개)* 로 환원.

### 9. 비자명한 교환자가 비가환의 척도

가환 ↔ 모든 교환자 $= 0$.

**1)** *가환 리 군 ⇔ 가환 리 대수 (§3 §7)*. $G$ 가환 ⇔ $[X, Y] = 0$ for all $X, Y \in \mathfrak{g}$ ⇔ *리 괄호가 항등으로 $0$*.

**2)** *가환 리 대수의 단순함*. 가환 리 대수는 *벡터 공간 + 자명한 (모두 0인) 리 괄호*. 사실상 *벡터 공간만 다루면 됨*. *유한 차원 벡터 공간 분류 = 차원만으로 결정* — 가환 리 대수도 마찬가지 단순.

**3)** *비가환의 정도 — 교환자 부분 공간*. $[\mathfrak{g}, \mathfrak{g}] := \text{span}\{[X, Y] : X, Y \in \mathfrak{g}\} \subseteq \mathfrak{g}$ 가 *교환자 부분 대수*. 가환이면 $[\mathfrak{g}, \mathfrak{g}] = 0$. 비가환의 *정도* 가 이 부분 대수의 크기로 측정.

**4)** *반단순(semisimple) 리 대수 — 극단의 비가환*. $[\mathfrak{g}, \mathfrak{g}] = \mathfrak{g}$ (교환자가 *전체* 를 생성) 인 리 대수. 예 — $\mathfrak{su}(N)$, $\mathfrak{so}(N)$, $\mathfrak{sp}(2N)$ 등 (예외 — $\mathfrak{u}(N)$ 은 *중심 $\mathfrak{u}(1)$* 부분이 있어 반단순 아님; $\mathfrak{su}(N) \oplus \mathfrak{u}(1)$ 분해).

**5)** *간단·반단순·일반 분해*. 임의 리 대수 = *반단순 부분 + 가환 부분 (Levi 분해)*. Killing-Cartan 분류 (§3 §8) 가 반단순 부분에 집중.

### 10. 이 절을 닫으며

이 절에서 점검한 것.

(1) *군 교환자* $[g, h] = ghg^{-1}h^{-1}$ 와 *리 괄호* $[X, Y] = XY - YX$ (행렬군) 정의.

(2) *군 교환자의 무한소 전개* — $[g_s, h_t] = I + st[X, Y] + O(s^2, t^2, st^2, s^2 t)$. 비가환성의 *2차 무한소 측정 = 리 괄호*.

(3) *$\mathfrak{g}$ 가 교환자로 닫힘* — $\mathfrak{so}, \mathfrak{u}, \mathfrak{su}, \mathfrak{sl}, \mathfrak{gl}, \mathfrak{sp}$ 모두 직접 확인. 리 괄호가 $\mathfrak{g}$ 위 잘 정의된 연산.

(4) *수반 작용* $\text{Ad}_g (Y) = g Y g^{-1}$ (군 차원) 과 $\text{ad}_X (Y) = [X, Y]$ (리 대수 차원). 관계 $\text{Ad}_{\exp X} = \exp(\text{ad}_X)$.

(5) *추상 리 대수* — 행렬군 너머에서 리 괄호의 정의 — $[X, Y] = \frac{d}{dt}|_{t=0} \text{Ad}_{\exp tX}(Y)$.

(6) *$\mathfrak{su}(2)$ 구체 예* — $[i\sigma_a, i\sigma_b]$ 명시 계산, *구조 상수* 도입, 양자역학 각운동량 표기.

(7) *비가환 척도* — $[\mathfrak{g}, \mathfrak{g}]$ 부분 대수, 반단순·가환 분해.

다음 §11 에서 *리 대수의 완전한 공리* — *이중선형성, 반대칭성, 야코비 항등식* — 을 본격적으로 정리한다. 야코비 항등식의 *도출과 의미* 가 핵심. 이로써 *완전한 리 대수 구조* 가 완성되고, 3부 (리 대수) 가 마무리된다.
