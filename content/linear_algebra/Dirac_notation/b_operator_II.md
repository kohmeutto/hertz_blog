+++
title = "(b) Operator II"
weight = 3
+++

---

### 1. Bra vs. 연산자

**(1) Ket 벡터 $|f\rangle$: 본질**

추상적인 Ket 벡터 **$∣f\rangle$** 는 그 자체로 하나의 완벽한 **'설계도' 또는 'DNA'** 와 같다. 이 설계도 안에는 함수에 대한 모든 정보(특정 지점에서의 값, 변화율, 에너지, 운동량 등)가 **잠재적** 으로 전부 담겨 있다.

**(2) Bra 벡터 $\langle v|$: 추출 연산자 (Extraction Operator)**

- **역할** : $|f\rangle$가 가진 수많은 정보 중에서, 특정 정보 하나($v\rangle$ 성분)만을 **추출(extract)** 하여 하나의 숫자로 보여주는 연산자이다.
- **비유** : 전체 DNA($|f\rangle$)에서 눈 색깔 유전자($\langle v|$)정보만 쏙 뽑아내어 갈색이라는 값(스칼라)을 읽어내는 **유전자 분석기** 와 같다.
- **결과** : $\langle v∣f\rangle$ → **스칼라 (숫자)**

**(3) $\hat{A}$: 변환 연산자 (Transformation Operator)**

- **역할** : 연산자 $\hat{A}$는 벡터 $|f\rangle$의 잠재된 정보 중 어떤것을 **‘실제로(actually)’ 꺼내** 보며 이것을 **변환(transform)** 시켜 새로운 상태 벡터 $|g\rangle$를 만들어내는 연산자이다.
- **비유** : DNA($|f\rangle$)에 어떤 약품($\hat{A}$)을 처리한다. 이 약품은 **어떤 유전자만 찾아 '발현'** 시키는  역할을 한다. 이 '발현'의 결과가 바로  $|g\rangle$ 이다.
- **결과**: $\hat{A}|f\rangle$ → **Ket (새로운 벡터)**

---

### 2. 연산자의 수학적 정의와 표현

**(1) 유한차원**

유한차원에서, Ket-Bra → matrix 연산으로 표현된다. 예를 들어, 두 개의 2차원 벡터 |a⟩와 |b⟩가 있다.

$$
|a\rangle
\to\left[\begin{matrix}
    a_1 \\ 
    a_2
\end{matrix}\right],\quad
|b\rangle
\to\left[\begin{matrix}
    b_1 \\ 
    b_2
\end{matrix}\right]
$$

outer product의 결과는 matrix이며, **matrix는 연산자** 로 간주할 수 있다. 따라서, 아래와 같이 쓸 수 있다.

$$
\hat{A}
=|a\rangle\langle b|
\to\left[\begin{matrix}
    a_1 \\ 
    a_2
\end{matrix}\right]
\left[\begin{matrix}
    b_1^\ast & b_2^\ast
\end{matrix}\right]
=\left[\begin{matrix}
    a_1b_1^\ast & a_1b_2^\ast \\
    a_2b_1^\ast & a_2b_2^\ast
\end{matrix}\right]
$$

**(2) 무한차원**

유한차원과 동일하게, 무한차원에서 outer product는 두 함수를 이용해 새로운 **연산자(operator)** 를 만드는 방법이다. 구체적으로는 적분 커널(integral kernel) 형태의 연산자가 된다. 함수 f(x)에 해당하는 벡터 |f⟩와 함수 g(x)에 해당하는 벡터 |g⟩가 있을 때,

$$
\hat{A}
=|f\rangle\langle g|
$$

---

### 2. 연산자의 작동 방식

이 연산자 Â가 임의의 함수 벡터 |ψ⟩에 어떻게 작용하는지 보면 그 정체를 알 수 있다.

$$
\hat{A}|\psi\rangle
=(|f\rangle\langle g|)|\psi\rangle
=|f\rangle(\langle g|\psi\rangle)
=c|f\rangle
$$

즉, 연산자 Â는 입력 벡터 |ψ⟩를 받아서, 상수 c를 곱한 새로운 벡터 c|f⟩를 출력한다.

---

### 3. 이산 기저의 사영 연산자 (Projection operator)

벡터 공간에서 사영 연산자를 만드는 방법은 **벡터 $|u_i⟩$** 와 그에 대응하는 **듀얼 벡터(dual vector) $⟨u^i|$** 의 **외부곱(outer product)** 을 이용하는 것이다.

$$
\hat{P}_i=|u_i\rangle\langle u^i|
$$

이산기저 기저 $|u^j⟩$ 와 그에 대응하는 듀얼 기저(dual vector) $⟨u_i|$ 은 다음을 만족해야 한다.

$$
\langle u_i|u^j\rangle=\delta_i^j
$$

만약, 기저 $|u_i⟩$ 가 **정규직교 기저(orthononal basis)** 라면, 위 식으로 부터 듀얼 기저는 $⟨u_i|$ 가 된다. 

**특성1) 이산 기저의 사영연산자는 반드시 멱등성을 만족한다.**

$$
\hat{P}_i^n=\hat{P}_i
$$

proof)

$$
\hat{P}_i^2
=(|u_i\rangle\langle u^i|)(|u_j\rangle\langle u^j|)
=|u_i\rangle\delta^i_{.j}\langle u^j|
=|u_i\rangle\langle u^i|
=\hat{P}_i
$$

**특성2) 완전한(complete) 이산 기저의 사영연산자의 모든 합은 항등연산자이다.**

$$
\hat{I}=\sum_i|u_i\rangle\langle u^i|
$$

proof)

$$
|\psi\rangle
=\sum_i\langle u^i|\psi\rangle|u_i\rangle
=\sum_i|u_i\rangle\langle u^i|\psi\rangle
=\hat{I}|\psi\rangle
$$

---

### 4. 연속 기저의 사영 연산자 "밀도" (Projection operator "density")

벡터 공간에서 사영 연산자를 만드는 방법은 **벡터 $|x⟩$** 와 그에 대응하는 **듀얼 벡터(dual vector) $⟨x|$** 의 **외부곱(outer product)** 을 이용하는 것이다.

$$
\hat{P}_x=|x\rangle\langle x|
$$

연속기저 기저 $|x'⟩$ 와 그에 대응하는 듀얼 기저(dual vector) $⟨x|$ 은 다음을 만족해야 한다.

$$
\langle x|x'\rangle=\delta(x-x')
$$

**비교) 개별 사영 연산자 밀도는 멱등성을 만족하지 않는다.**

$$
\hat{P}_x^2
=(|x\rangle\langle x|)(|x\rangle\langle x|)
=|x\rangle\delta(0)\langle x|
=|x\rangle\langle x|\cdot\infty
\ne \hat{P}_x
$$

**특성) 완전한(complete) 연속 기저의 사영연산자 밀도의 모든 합(적분)은 항등연산자이다.**

$$
\hat{I}
=\int^\infty_{-\infty}dx|x\rangle\langle x|
$$

proof)

$$
|\psi\rangle
=\int^\infty_{-\infty}dx\langle x|\psi\rangle|x\rangle
=\int^\infty_{-\infty}dx|x\rangle\langle x|\psi\rangle
=\hat{I}|\psi\rangle
$$


---