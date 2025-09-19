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

### 3. 사영 연산자 (Projection operator)

**(1) 사영연산자의 유일한 조건**



**(2) 직교사영**



**(3) [핵심] 정규직교사영**

