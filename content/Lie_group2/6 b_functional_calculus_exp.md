+++
title = "함수 미적분과 지수 사상"
weight = 6
+++

### 1. 동기

§5에서 곡선 $A(\tau)$의 미분 $\dfrac{dA}{d\tau}$를 계산하는 법을 봤다. 이제 그 *역*의 문제를 생각한다. 매개변수 $\tau = 0$에서의 미분값(어떤 행렬 $X$)이 주어졌을 때, *전체 곡선* $A(\tau)$를 복원할 수 있는가?

이 복원을 가능하게 하는 도구가 *지수 사상(exponential map)*이다. 이를 정확히 이해하려면 *함수 미적분(functional calculus)*— 스칼라 함수를 행렬에 적용하는 일반적 방법— 을 먼저 짚어야 한다.

### 2. 스펙트럼 분해

**1)** 행렬 $A$가 충분히 많은 일차독립 고유벡터를 가져 *대각화 가능*하다고 가정한다. 이 경우 다음 분해가 성립한다.

$$A = \sum_i \lambda_i\, \vert v_i\rangle\langle v^i\vert$$

여기서:
- $\lambda_i$는 $A$의 고유값
- $\vert v_i\rangle$는 대응되는 고유벡터
- $\langle v^i\vert$는 *쌍대 기저*. 정의로부터 $\langle v^i\vert v_j\rangle = \delta^i_j$ (§1 참조).

**2)** 이 분해의 핵심: $A$의 작용이 *고유벡터별로 단순한 스칼라 곱*으로 환원된다.

$$A\, \vert v_j\rangle = \sum_i \lambda_i\, \vert v_i\rangle \underbrace{\langle v^i\vert v_j\rangle}_{=\delta^i_j} = \lambda_j\, \vert v_j\rangle$$

### 3. 함수 미적분의 스펙트럼 정의

**1)** 스칼라 함수 $f: \mathbb{C} \to \mathbb{C}$가 주어지면, 행렬 $A$에 대한 $f(A)$를 다음으로 정의한다.

$$f(A) = \sum_i f(\lambda_i)\, \vert v_i\rangle\langle v^i\vert$$

즉 *고유벡터는 그대로 두고, 고유값에만 $f$를 적용*한다.

**2)** 직관: 행렬을 "각 고유방향에 다른 스칼라($\lambda_i$)를 곱하는 작용"으로 보면, 그 작용에 $f$를 적용하는 것은 *각 스칼라에 $f$를 따로 적용*하는 것과 같다.

**3)** example1) $f(x) = x^2$이면 $f(A) = A^2 = \sum_i \lambda_i^2\, \vert v_i\rangle\langle v^i\vert$. (직접 행렬곱 $A \cdot A$와 일치)

**4)** example2) $f(x) = e^x$이면 $f(A) = e^A = \sum_i e^{\lambda_i}\, \vert v_i\rangle\langle v^i\vert$.

### 4. 지수 사상: 두 가지 정의

**1)** *스펙트럼 정의*:

$$\exp(A) = \sum_i e^{\lambda_i}\, \vert v_i\rangle\langle v^i\vert$$

**2)** *테일러 급수 정의*:

$$\exp(A) = I + A + \frac{A^2}{2!} + \frac{A^3}{3!} + \cdots = \sum_{n=0}^{\infty} \frac{A^n}{n!}$$

**3)** 대각화 가능 행렬에서는 두 정의가 일치한다 (스펙트럼 분해를 대입하면 같은 식). 더 일반적으로 테일러 급수 정의는 대각화 가능성에 의존하지 않으므로 *임의의 정사각 행렬*에 대해 잘 정의된다.

### 5. 지수 사상의 핵심 성질

**1)** $\exp(0) = I$. (영행렬을 넣으면 단위행렬.)

**2)** $\exp(A) \exp(-A) = I$. 따라서 $\exp(A)$는 항상 가역이고 $\exp(A)^{-1} = \exp(-A)$.

**3)** $A$와 $B$가 *교환*하면 ($AB = BA$):

$$\exp(A + B) = \exp(A) \exp(B)$$

교환하지 않으면 이 공식은 일반적으로 *성립하지 않는다*.

**4)** 매개변수 $\tau$에 무관한 행렬 $A$에 대해:

$$\frac{d}{d\tau} \exp(\tau A) = A\, \exp(\tau A) = \exp(\tau A)\, A$$

proof) 테일러 급수를 항별로 미분한다.
$$\frac{d}{d\tau}\sum_{n=0}^\infty \frac{(\tau A)^n}{n!} = \sum_{n=1}^\infty \frac{n\, \tau^{n-1} A^n}{n!} = A \sum_{n=1}^\infty \frac{(\tau A)^{n-1}}{(n-1)!} = A\, \exp(\tau A)$$

$A$가 $\exp(\tau A)$와 교환하는 것은 $\exp(\tau A)$가 $A$의 다항식의 극한이라는 사실에서 따라온다.

이 성질은 *지수 사상이 곡선 $A(\tau) = \exp(\tau X)$의 미분과 자연스럽게 어울린다*는 것을 보여준다.

### 6. SO(2) 예제: 회전 행렬의 복원

**1)** §5에서 $R(\tau)$의 $\tau = 0$에서의 미분이 다음과 같음을 봤다.

$$X = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix}, \quad X^2 = -I$$

**2)** 이제 $X$로부터 $\exp(\tau X)$를 계산해서 $R(\tau)$를 복원해 본다.

**3)** $X$의 거듭제곱:
- $X^0 = I$
- $X^1 = X$
- $X^2 = -I$
- $X^3 = X \cdot X^2 = -X$
- $X^4 = (X^2)^2 = I$
- 이후 주기 4로 반복

**4)** 테일러 급수에 대입:

$$\exp(\tau X) = I + \tau X + \frac{\tau^2}{2!} X^2 + \frac{\tau^3}{3!} X^3 + \frac{\tau^4}{4!} X^4 + \cdots$$

거듭제곱 값을 넣으면:

$$\exp(\tau X) = I + \tau X - \frac{\tau^2}{2!} I - \frac{\tau^3}{3!} X + \frac{\tau^4}{4!} I + \cdots$$

**5)** $I$ 항과 $X$ 항을 따로 모으면:

$$\exp(\tau X) = \left(1 - \frac{\tau^2}{2!} + \frac{\tau^4}{4!} - \cdots\right) I + \left(\tau - \frac{\tau^3}{3!} + \frac{\tau^5}{5!} - \cdots\right) X$$

$$= \cos\tau \cdot I + \sin\tau \cdot X$$

**6)** 행렬로 풀어 쓰면:

$$\exp(\tau X) = \cos\tau \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} + \sin\tau \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} = \begin{pmatrix} \cos\tau & -\sin\tau \\ \sin\tau & \cos\tau \end{pmatrix} = R(\tau)$$

**7)** *결론: $\tau = 0$에서의 미분 $X$만 알면 지수 사상으로 곡선 전체 $R(\tau)$가 복원된다.*

### 7. 미분과 지수의 역대응

**1)** 다음 두 도구가 서로의 *역*에 해당한다.

- *미분* ($\tau = 0$에서): 곡선 $A(\tau)$를 받아 행렬 $X = \dfrac{dA}{d\tau}\big|_{\tau=0}$을 내놓음
- *지수 사상*: 행렬 $X$를 받아 곡선 $A(\tau) = \exp(\tau X)$를 내놓음

**2)** 메커니즘은 다르다:
- 미분은 *성분별* 작용 (§5)
- 지수 사상은 *스펙트럼별* 작용 (이 장)

**3)** 그러나 위의 SO(2) 예에서 봤듯, 두 도구를 차례로 적용하면 원래 곡선으로 돌아온다.

<svg viewBox="0 0 400 200" xmlns="http://www.w3.org/2000/svg" style="display:block;margin:auto;max-width:400px">
  <defs>
    <marker id="arr6blue" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
      <path d="M 0,0 L 10,5 L 0,10 z" fill="#0066cc"/>
    </marker>
    <marker id="arr6red" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
      <path d="M 0,0 L 10,5 L 0,10 z" fill="#cc0000"/>
    </marker>
  </defs>
  <rect x="30" y="60" width="100" height="80" fill="none" stroke="black" stroke-width="2" rx="8"/>
  <text x="80" y="95" text-anchor="middle" font-size="13">곡선</text>
  <text x="80" y="115" text-anchor="middle" font-size="13">A(τ)</text>
  <rect x="270" y="60" width="100" height="80" fill="none" stroke="black" stroke-width="2" rx="8"/>
  <text x="320" y="95" text-anchor="middle" font-size="13">행렬</text>
  <text x="320" y="115" text-anchor="middle" font-size="13">X</text>
  <path d="M 130,80 Q 200,30 270,80" fill="none" stroke="#0066cc" stroke-width="2" marker-end="url(#arr6blue)"/>
  <text x="200" y="32" text-anchor="middle" font-size="11" fill="#0066cc">d/dτ at τ=0</text>
  <path d="M 270,120 Q 200,170 130,120" fill="none" stroke="#cc0000" stroke-width="2" marker-end="url(#arr6red)"/>
  <text x="200" y="180" text-anchor="middle" font-size="11" fill="#cc0000">exp(τ·)</text>
</svg>

### 8. 정리

**1)** *함수 미적분*은 스칼라 함수 $f$를 행렬에 적용하는 도구. 스펙트럼 정의는 *고유값에만 $f$를 적용*: $f(A) = \sum_i f(\lambda_i)\,\vert v_i\rangle\langle v^i\vert$.

**2)** *지수 사상* $\exp(A)$는 스펙트럼 정의 또는 테일러 급수로 정의된다. 핵심 성질 $\dfrac{d}{d\tau}\exp(\tau A) = A\,\exp(\tau A)$.

**3)** 회전 행렬 예에서: $\tau = 0$에서의 미분 $X$로부터 $\exp(\tau X) = R(\tau)$가 정확히 복원된다.

**4)** 미분과 지수 사상은 *서로의 역*에 해당한다. 미분은 곡선에서 한 점의 방향(행렬)을 뽑아내고, 지수 사상은 그 방향에서 다시 곡선 전체를 복원한다.
