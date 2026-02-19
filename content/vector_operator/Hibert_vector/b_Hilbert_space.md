+++
title = "(b) Hilbert space"
weight = 4
+++

---

Ket($| \psi \rangle$)과 Bra($\langle \phi |$)는 일반적으로 힐버트 공간(Hilbert Space)의 원소라고 하나, 이 문서에서는 특정 공간에 관계없는 벡터의 표기법으로 사용한다.

---

### 1. 위상 벡터 공간(Topological Vector Spaces) 구조

**벡터 공간** ⊃ 노름 공간 ⊃ {**내적 공간**, 바나흐 공간} ⊃ **힐버트 공간** ⊃ 실체 공간 ( 유클리드 공간, L2 공간 ...)

**1) 벡터 공간 (Vector Space)**

- 덧셈과 스칼라 곱 연산이 정의되는 가장 기초적인 공간.

**2) 노름 공간 (Normed Space)**

- 벡터 공간 + 노름($||\cdot||$)벡터의 '길이'를 잴 수 있는 공간. 

**3.1) 내적 공간 (Inner Product Space)**

- 벡터 공간 + 내적($\langle \cdot, \cdot \rangle$)
- 벡터의 '각도'와 '길이'를 모두 잴 수 있는 공간.
- 내적이 정의되면 노름은 자동으로 유도되므로($||x||=\sqrt{\langle x,x\rangle}$), 내적 공간은 노름 공간의 부분집합이다.

**3.2) 바나흐 공간 (Banach Space)**

- 노름 공간 + 완비성(Completeness)
- 공간 안의 모든 코시 수열(Cauchy sequence)이 그 공간 안의 한 점으로 수렴하는, 즉 '빈틈이 없는' 노름 공간이다.
- 미적분학이나 해석학을 전개하기에 매우 좋은 환경을 제공한다.

**4) 힐버트 공간 (Hilbert Space)**

- 내적 공간+완비성을 만족하는 공간. 즉, **완비 내적 공간(Complete Inner Product Space)** 이다.

---

### 2. 벡터 공간

벡터 공간(Vector Space) 또는 선형 공간(Linear Space)은 **체 $F$ 위의 아벨군 $V$** 로 정의된다. 즉, 사칙연산이 완벽한 지반(체) 위에 덧셈과 역원이 정의된 구조물(아벨군)을 세운 것과 같다.

**1) 덧셈에 대한 아벨군 $(V, +, -)$**

집합 $V$의 원소인 벡터들 사이에는 다음의 성질이 성립해야 한다.

(1) 결합법칙 (Associativity): 임의의 $\lbrace|u\rangle, |v\rangle, |w\rangle\rbrace \in V$에 대해, $(|u\rangle+|v\rangle)+|w\rangle=|u\rangle+(|v\rangle+|w\rangle)$  
(2) 항등원 (Identity): 모든 $|v\rangle \in V$에 대해, $|v\rangle+|0\rangle=|v\rangle$ 를 만족하는 영벡터 $|0\rangle$ 이 존재한다.  
(3) 역원 (Inverse): 모든 $|v\rangle \in V$에 대해, $|v\rangle+|-v\rangle=|0\rangle$ 를 만족하는 역원 $|-v\rangle$ 이 존재한다.  
(4) 교환법칙 (Commutativity): 임의의 $\lbrace|u\rangle, |v\rangle\rbrace \in V$에 대해, $|u\rangle+|v\rangle=|v\rangle+|u\rangle$

**2) 스칼라 체$(F,+,-,\times,\div)$와 아벨군$(V,+,-)$의 관계**

체 $F$의 원소인 스칼라$(a, b)$와 벡터$(|u\rangle, |v\rangle)$ 사이에는 스칼라 곱이라는 외부 작용이 정의되며, 다음의 선형성을 만족해야 한다.

(1) 분배법칙(Distributivity):

- 스칼라에 대한 분배: $a(|v\rangle+|u\rangle)=a|v\rangle+a|u\rangle$
- 벡터에 대한 분배: $(a+b)|v\rangle=(ab)|v\rangle$

(2) 결합법칙(Associativity of Scalar Multiplication): $a(b|v\rangle)=(ab)|v\rangle$  
(3) 항등원(Unitary Property)): 체 $F$의 곱셈 항등원 $\hat{I}$에 대해 $\hat{I}|v\rangle=|v\rangle$

---

### 3. 노름 공간

- 벡터 공간 + 노름($\|\cdot\|$)
- 벡터의 '크기' 또는 '길이'를 측정할 수 있는 규칙이 정의된 공간이다.
- 노름은 반드시 **유클리드 거리($\sqrt{x^2+y^2}$)** 일 필요는 없으며, 아래의 3가지 공리를 만족하는 임의의 함수는 모두 노름이 될 수 있다. (예: 맨해튼 거리 $|x|+|y|$, 최대 거리 $\max(|x|,|y|)$ 등)

**1) 노름의 3대 공리**

(1) 양의 정부호성: 길이는 0보다 크거나 같아야 한다. 

$$\| |v\rangle \| \ge 0, \| |v\rangle \|=0 \iff |v\rangle=0$$

(2) 동차성 (스칼라 곱): 벡터가 늘어나면 길이도 비례해서 늘어난다. 

$$\| |cv\rangle \| = |c|\cdot\| |v\rangle \|$$  

(3) 삼각 부등식: 돌아가는 길은 직선 거리보다 짧을 수 없다. 

$$\| |u\rangle+|v\rangle \| \le \| |u\rangle \| + \| |v\rangle \|$$

---

### 4. 내적 공간

내적 공간은 **벡터 공간** 에 **내적 연산(Inner Product Operation)** 이 추가로 정의된 공간이다. 수학적으로 벡터 공간 $V$ 위의 내적은 순서가 있는 두 벡터의 쌍을 스칼라로 보내는 함수이다. 앞서 정의한 켓 벡터 $|u\rangle, |v\rangle \in V$에 대하여, 내적을 다음과 같이 **정의**한다. (이 단계에서 내적은 기하학적 각도와 길이를 정의하는 연산이며, 앞서 정의한 브라 $\langle u |$와의 관계는 추후 힐버트 공간의 성질을 통해 연결된다.)

$$
(|u\rangle, |v\rangle) := \langle u , v \rangle
$$


**1) 내적의 공리 (Axioms)**

임의의 켓 $|\psi\rangle, |\phi\rangle, |\omega\rangle \in V$와 스칼라 $c \in F$에 대해, 내적 연산 $\langle \cdot , \cdot \rangle$은 다음을 만족해야 한다.

(1) 선형성 (Linearity): 두 번째 인자(오른쪽 켓)에 대해 선형적이다.

$$
\langle \omega , (c|\psi\rangle + |\phi\rangle) \rangle = c\langle \omega , \psi \rangle + \langle \omega , \phi \rangle
$$

(2) 켤레 대칭성 (Conjugate Symmetry): 순서를 바꾸면 켤레 복소수가 된다.

$$
\langle \phi , \psi \rangle = \langle \psi , \phi \rangle^{\ast}
$$

(3) 양의 정부호성 (Positive-Definiteness): 자기 자신과의 내적은 항상 0보다 크거나 같은 실수이다.

$$
\langle \psi , \psi \rangle \ge 0 \quad \text{ (단,} \langle \psi , \psi \rangle = 0 \text{ 인 것은} |\psi\rangle = |0\rangle \text{일 때뿐이다.)}
$$

**2) 주요 성질 (Properties)**

위의 정의로부터 유도되는 **내적 공간** 의 기하학적 성질들이다. (이 성질들은 공간의 완비성 여부와 무관하게 성립하므로, 힐버트 공간이 아니더라도 유효하다.)

(1) 반선형성 (Antilinearity): 켤레 대칭성에 의해, 첫 번째 인자(왼쪽)에 걸리는 스칼라는 켤레($c^{\ast}$)가 되어 밖으로 나온다.

$$
\langle c\phi , \psi \rangle = c^{\ast}\langle \phi , \psi \rangle
$$

{{< details summary="proof)" >}}

$$
\langle c\phi , \psi \rangle
=\langle \psi , c\phi \rangle^{\ast}
=(c\langle \psi , \phi \rangle)^{\ast}
=c^{\ast}\langle \psi , \phi \rangle^{\ast}
=c^{\ast}\langle \phi , \psi \rangle
$$

{{< /details >}}

(2) 코시-슈바르츠 부등식 (Cauchy-Schwarz)

$$
|\langle \phi , \psi \rangle|^2 \le \langle \phi , \phi \rangle \langle \psi , \psi \rangle
$$

{{< details summary="proof)" >}}

임의의 복소수 $\lambda$에 대하여,

$$
|\psi+\lambda\phi\rangle:=|\psi\rangle+\lambda|\phi\rangle 
$$

내적의 양의 정부호성에 의해,

$$
\langle\psi+\lambda\phi , \psi+\lambda\phi\rangle
=\langle\psi , \psi\rangle+\lambda\langle\psi , \phi\rangle+\lambda^{\ast}\langle\phi , \psi\rangle+\lambda\lambda^{\ast}\langle\phi , \phi\rangle \ge 0
$$

편의상 각 항을 $A, B, C$로 치환하면 ($C = \langle\phi , \phi\rangle \neq 0$),

$$
\implies A+\lambda B+\lambda^{\ast}B^{\ast}+\lambda\lambda^{\ast} C\ge 0
\implies C\left(\frac{A}{C}+\lambda \frac{B}{C}+\lambda^{\ast}\frac{B^{\ast}}{C}+\lambda\lambda^{\ast}\right)\ge 0
$$

완전제곱식 꼴로 정리하면,

$$
\implies C\left(\lambda+\frac{B^{\ast}}{C}\right)\left(\lambda^{\ast}+\frac{B}{C}\right)-\frac{BB^{\ast}}{C}+A\ge 0
\implies C\left|\lambda+\frac{B^{\ast}}{C}\right|^2 + \left( A - \frac{|B|^2}{C} \right) \ge 0
$$

모든 $\lambda$에 대해서 위 식이 항상 만족해야 한다. 따라서 좌변을 최소로 만드는 $\lambda = -B^{\ast}/C$를 대입했을 때도 성립해야 한다. (이때 제곱항은 0이 된다.)

$$
A - \frac{|B|^2}{C} \ge 0
\implies |B|^2 \le AC
\implies |\langle \phi , \psi \rangle|^2 \le \langle \phi , \phi \rangle \langle \psi , \psi \rangle
$$

{{< /details >}}

(3) 노름의 유도 (Induced Norm): 내적을 통해 벡터의 길이를 정의한다.

$$
\| |\psi\rangle \| := \sqrt{\langle \psi , \psi \rangle}
$$

---

### 5. 완비성

내적 공간(Inner Product Space)이 기하학적인 무대(각도, 길이)를 제공한다면, **완비성(Completeness)** 은 그 무대의 바닥이 '구멍 없이' 매끄러움을 보장하는 해석학적 조건이다. 양자역학에서 상태의 중첩(Superposition)이나 무한 급수($\sum c_n |n\rangle$)를 다룰 때, 계산의 결과가 공간 밖으로 도망가지 않고 안전하게 존재함을 보장하기 위해 반드시 필요한 성질이다. 

**1) 코시 수열 (Cauchy Sequence)**

완비성을 정의하기 위해서는 먼저 수열이 '수렴할 자격'을 갖추었는지 판단하는 기준이 필요하다. 이를 **코시 수열** 이라 한다.

(1) 정의 (Definition)

벡터 공간 $V$의 수열 $\{|\psi_n\rangle\}$에 대하여, 항 번호가 커질수록 항들 사이의 거리가 무한히 가까워진다면 이를 코시 수열이라 한다.

$$
\forall \epsilon > 0, \exists N \in \mathbb{N} \text{ s.t. } n, m > N \implies \| |\psi_n\rangle - |\psi_m\rangle \| < \epsilon
$$

(2) 의미

- 수렴 수열: "특정 목적지(극한값)로 다가가는 수열"
- 코시 수열: "목적지는 모르겠지만, 자기들끼리 옹기종기 모이는 수열"

**2) 완비성의 정의 (Completeness)**

어떤 내적 공간 $V$가 다음 조건을 만족하면, 이 공간을 **완비적(Complete)** 이라고 한다. **"공간 $V$ 내부의 모든 코시 수열이, 다시 $V$ 내부의 한 점(원소)으로 수렴한다."** 즉, "모일 자격(코시 성질)을 갖춘 원소들에게는 반드시 공간 내에 쉴 곳(극한값)이 마련되어 있는 공간"을 의미한다.

$$
\{|\psi_n\rangle\} \text{ is Cauchy} \implies \exists |\psi\rangle \in V \text{ s.t. } \lim_{n \to \infty} \| \underbrace{|\psi_n\rangle}_{\text{현재 위치}} - \underbrace{|\psi\rangle}_{\text{목표 지점}} \| = 0
$$

**3) 예시: 유리수 vs 실수**

완비성의 개념을 가장 잘 보여주는 예시는 유리수($\mathbb{Q}$)와 실수($\mathbb{R}$)의 차이이다.

(1) 유리수 공간 ($\mathbb{Q}$) : 불완비 공간

다음과 같은 수열을 생각해보자.

$$
1, 1.4, 1.41, 1.414, \dots
$$

- 이 수열은 유리수들로 이루어져 있으며, 서로 점점 가까워지므로 **코시 수열** 이다.
- 하지만 이 수열이 향하는 목적지는 $\sqrt{2}$이다.
- $\sqrt{2} \notin \mathbb{Q}$ 이므로, 이 수열은 유리수 공간 안에서 수렴하지 않는다. (구멍에 빠짐)
- **결론:** 유리수 공간은 완비적이지 않다.

(2) 실수 공간 ($\mathbb{R}$) : 완비 공간

* 실수 공간에는 유리수 사이의 빈틈을 무리수들이 메우고 있다.
* 따라서 위의 수열은 실수 공간 내의 점 $\sqrt{2}$로 안전하게 수렴한다.
* **결론:** 실수 공간은 완비적이다.

**4) 완비성의 판별(Proof Strategy)**

우리가 사용하는 구체적인 공간(예: $L^2$ 공간)이 완비적인지 증명해야 한다. (이를 **리즈-피셔 정리** 라고 한다.) 증명은 보통 다음 4단계를 따른다.

(1) 수열 선택: 공간 내의 임의의 코시 수열 $\{f_n\}$을 잡는다.  
(2) 후보 찾기: 수열이 수렴할 것으로 예상되는 극한 함수 $f$를 찾는다. (보통 실수/복소수의 완비성을 이용)  
(3) 소속 확인(**가장 중요**): 그 극한 함수 $f$가 여전히 공간의 조건(예: 유한한 에너지 $\int |f|^2 < \infty$)을 만족하는지 확인한다.  
(4) 수렴 확인: 노름 $\| f_n - f \|$가 실제로 0으로 가는지 확인한다.

---

### 6. 힐버트 공간의 완성

이제 힐버트 공간을 정의할 수 있다. **힐버트 공간 (Hilbert Space) $\mathcal{H}$**

(1) **내적 공간**이다. (내적 $\langle \cdot, \cdot \rangle$이 정의됨 $\rightarrow$ 기하학 가능)  
(2) **완비 공간**이다. (모든 코시 수열이 공간 내에서 수렴함 $\rightarrow$ 해석학 가능)

이 두 가지 조건이 결합됨으로써, 우리는 양자역학의 파동함수를 벡터처럼 다루면서도(기하학), 미분방정식을 풀고 무한 급수를 전개하는(해석학) 작업을 엄밀하게 수행할 수 있다.

---

### 7. 힐버트 공간 vs. 유클리드 공간 vs. L2 공간

세 공간의 관계는 단순한 포함 관계가 아니라, **"추상적 분류(Category)"** 와 **"구체적 사례(Instance)"** 의 관계이다. 힐버트 공간이라는 거대한 수학적 우산 아래에, 차원과 원소의 형태에 따라 유클리드 공간과 $L^2$ 공간이 각각 구체적인 구현체로 존재하는 구조이다.

**1) 힐버트 공간 (Hilbert Space : 추상적 뼈대)**

- '내적'과 '완비성'을 만족하는 모든 공간을 통칭하는 대수적·해석학적 조건이다.
- 원소가 행렬인지 함수인지, 차원이 유한인지 무한인지를 따지지 않는다.
- 양자역학의 모든 상태 벡터($|\psi\rangle$)는 원칙적으로 어떤 힐버트 공간 안에 살고 있다.

**2) 유클리드 공간 (Euclidean Space : 유한 차원의 사례)**

- 우리가 익히 아는 $n$차원 공간($\mathbb{R}^n$ 또는 $\mathbb{C}^n$)이다.
- 원소는 유한한 개수의 성분을 가진 열 벡터(Column vector) 형태이다.
- 유한 차원 내적 공간은 수학적으로 완비성이 보장되므로, 유클리드 공간은 힐버트 공간의 완벽한 일종(예시)이다.
- 양자역학적 적용: **스핀(Spin)** 이나 양자 컴퓨터의 **큐비트(Qubit)** 처럼 상태가 이산적이고 유한한 시스템을 계산할 때, 이 유한 차원의 복소 유클리드 공간(예: $\mathbb{C}^2$)을 힐버트 공간으로 선택하여 사용한다.

**3) $L^2$ 공간 (Square-integrable Space : 무한 차원의 사례)**

- 원소가 '제곱 적분 가능한 함수(Square-integrable function)'들로 이루어진 공간이다.
- 무한 차원 공간이며, 리즈-피셔 정리에 의해 완비성이 증명되었으므로 이 역시 힐버트 공간의 일종이다.
- 양자역학적 적용: **위치($x$)나 운동량($p$)** 처럼 연속적인 변수를 가지는 시스템을 계산할 때, 파동함수 $\psi(x)$가 서식하는 이 무한 차원 $L^2$ 공간을 힐버트 공간으로 골라서 사용한다.

**물리학에서 "힐버트 공간에서 계산한다"는 말은 단일한 공간 하나만 존재한다는 뜻이 아니다.** 우리가 다루는 물리적 시스템의 특성(이산적이냐, 연속적이냐)에 맞춰 힐버트 공간의 구체적인 '종류(유클리드 공간 또는 $L^2$ 공간)'를 **적절하게 골라서 쓰는 것** 이다.

---

### 8. 리그드 힐버트 공간 (Rigged Hilbert Space, RHS)

**1) 왜 필요한가?**

- 힐버트 공간은 물리적으로 의미 있는 상태(크기가 유한한 벡터)를 다루기에 매우 훌륭한 공간이다. 하지만 한 가지 문제가 있다. 위치 연산자($\hat{x}$)나 운동량 연산자($\hat{p}$)의 고유상태(eigenstate)인 |x⟩나 |p⟩는 크기가 무한대여서, 엄밀히는 힐버트 공간의 정식 멤버가 아니다.
- $|x_0\rangle$의 파동 함수 표현은 디랙 델타 함수 $\delta(x-x_0)$이며, 이 함수의 크기 제곱은 무한대이다.
- $|p_0\rangle$의 파동 함수 표현은 평면파 $e^{ip_0x/\hbar}$이며, 이 함수의 크기 제곱 또한 무한대이다.
- 물리적으로 매우 중요한 **이 기저 벡터들이 정작 힐버트 공간에 속하지 않는 수학적 문제를 해결하기 위해** 리그드 힐버트 공간이라는 확장된 개념을 도입한다.

**2) 겔판트 삼중항 (The Gelfand Triplet)**

리그드 힐버트 공간은 세 개의 공간이 샌드위치처럼 겹쳐진 **겔판트 삼중항(Gelfand triplet)** 이라는 구조로 이루어져 있다. 특정 위치 $x$의 함숫값을 뽑아내는 디랙 델타 범함수($\delta_x[\phi] = \phi(x)$) 를 생각하면 명쾌하게 이해된다.

$$
\Phi\subset \mathcal{H}\subset\Phi^\ast
$$
 
- $H$ (힐버트 공간): 우리가 지금까지 논의한 표준적인 힐버트 공간이다. 모든 물리적 상태 벡터($|\psi\rangle$)가 여기에 속한다.
- $\Phi \subset \mathcal{H}$ (함수 공간의 축소): $\Phi$는 $\mathcal{H}$($L^2$ 공간) 중에서도 무한 번 미분 가능한 아주 '예쁜' 함수들만 추려낸 좁은 공간이다.
- $\mathcal{H}$에서의 디렉 델타 (포함 불가): $\mathcal{H}$의 원소는 노름이 유한해야 하므로, 디랙 델타를 품을 수 없다. 따라서 $\delta_x \notin \mathcal{H}$ 이다.
- $\Phi^\ast$에서의 디렉 델타 (자연스러운 포함): 디랙 델타는 '예쁜 함수'($\Phi$)들의 범함수이므로, 당연히 그 쌍대 공간인 $\Phi^\ast$의 원소가 된다. 따라서 $\delta_x \in \Phi^\ast$ 이다.

**3) 의의**

이 구조를 통해 다음과 같은 이점을 얻는다.

- 물리적으로 실현 가능한 상태들은 여전히 힐버트 공간 $\mathcal{H}$에 존재한다.
- 수학적으로 문제가 되었던 위치 고유상태 $|x\rangle$나 운동량 고유상태 $|p\rangle$는 더 넓은 공간인 $\Phi^*$에 안전하게 존재할 수 있다.
- 결과적으로, 디랙이 사용했던 브라-켓 표기법 전체가 수학적으로 완벽하게 엄밀한 토대를 갖추게 된다.


