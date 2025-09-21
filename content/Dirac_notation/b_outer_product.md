+++
title = "(b) Outer product"
weight = 4
+++

---

### 1. 수학적 정의과 계산

**(1) 유한차원**

유한차원에서, Ket-Bra → matrix 연산으로 정의된다. 예를 들어, 두 개의 2차원 벡터 |a⟩와 |b⟩가 있다.

$$
|a\rangle
=\left[\begin{matrix}
    a_1 \\ 
    a_2
\end{matrix}\right],\quad
|b\rangle
=\left[\begin{matrix}
    b_1 \\ 
    b_2
\end{matrix}\right]
$$

outer product의 결과는 matrix이며, **matrix는 연산자** 로 간주할 수 있다. 따라서, 아래와 같이 쓸 수 있다.

$$
\hat{A}
=|a\rangle\langle b|
=\left[\begin{matrix}
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

만약, 기저 $|u_i⟩$ 가 **정규직교 기저(orthogonal basis)** 라면, 위 식으로 부터 듀얼 기저는 $⟨u_i|$ 가 된다. 

**특성1) 이산 기저의 사영연산자는 반드시 멱등성을 만족한다.**

$$
\hat{P}_i^n=\hat{P}_i
$$

proof)

$$
\hat{P}_i^2
=(|u_i\rangle\langle u^i|)(|u_i\rangle\langle u^j|)
=|u_i\rangle\delta_i^i\langle u^j|
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