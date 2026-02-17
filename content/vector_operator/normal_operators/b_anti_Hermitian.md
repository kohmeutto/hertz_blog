+++
title = "(b) anti-Hermitian"
weight = 3
+++

---

## 2.3 반-에르미트 연산자 (Anti-Hermitian Operator)

**정의**: 연산자 $\hat{A}$가 자신의 에르미트 켤레($\hat{A}^\dagger$)에 음의 부호를 붙인 것과 같을 때, 즉 $\hat{A}^\dagger = -\hat{A}$일 때, 이를 **반-에르미트(또는 스큐-에르미트, Skew-Hermitian) 연산자**라고 한다. 이 연산자 역시 정규 연산자($[\hat{A}, \hat{A}^\dagger]=0$)의 조건을 만족한다.

**물리적 의미**: 반-에르미트 연산자는 직접적으로 물리량을 나타내지는 않지만, 유니타리 변환을 만들어내는 **'생성자(Generator)'**로서, 시스템의 동적인 변화를 기술하는 데 핵심적인 역할을 한다.

---
### 핵심 특성 및 증명

**1. 고유값은 항상 순수 허수이거나 0이다.**

> **증명**:
> 1. $\hat{A}|v\rangle = \lambda|v\rangle$ 에서, 양변에 $\langle v|$를 내적하면 $\langle v|\hat{A}|v\rangle = \lambda\langle v|v\rangle$ 이다.
> 2. 위 식의 에르미트 켤레를 취하면 $\langle v|\hat{A}^\dagger|v\rangle = \lambda^*\langle v|v\rangle$ 이다.
> 3. $\hat{A}^\dagger = -\hat{A}$ 이므로, $-\langle v|\hat{A}|v\rangle = \lambda^*\langle v|v\rangle$ 이다.
> 4. 1번 결과를 대입하면, $-\lambda\langle v|v\rangle = \lambda^*\langle v|v\rangle$ 이다.
> 5. $\langle v|v\rangle \neq 0$ 이므로 $\lambda = -\lambda^*$ 이다. 이를 만족하는 복소수 $\lambda$는 반드시 순수 허수이거나 0이다.

**2. 에르미트 연산자와의 관계**

> 어떤 에르미트 연산자 $\hat{H}$에 허수 단위 $i$를 곱한 $i\hat{H}$는 반-에르미트 연산자이다.
>
> **증명**: $(i\hat{H})^\dagger = i^*\hat{H}^\dagger = (-i)(\hat{H}) = -(i\hat{H})$.

---
### 예제

#### 1. 행렬 예제
$$
\hat{A} = \begin{pmatrix} 0 & 1 \\ -1 & 0 \end{pmatrix}
$$
- **반-에르미트 확인**: $\hat{A}^\dagger = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} = -\hat{A}$.
- **고유값**: $\det(\hat{A} - \lambda I) = \lambda^2 + 1 = 0 \implies \lambda = i, -i$ (순수 허수).
- **고유벡터**:
    - $\lambda=i$: $|v_1\rangle \rightarrow \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ i \end{pmatrix}$
    - $\lambda=-i$: $|v_2\rangle \rightarrow \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ -i \end{pmatrix}$
- **직교성 확인**: $\langle v_1|v_2\rangle = 0$.

#### 2. 미분 연산자 (함수 공간)
- **연산자**: $\hat{D} = \frac{d}{dx}$
- **반-에르미트 확인**: 부분적분을 통해 $\hat{D}^\dagger = -\hat{D}$ 임을 보일 수 있다.
- **고유함수 및 고유값**: $\hat{D}e^{ikx} = (ik)e^{ikx}$.
    - 고유함수는 평면파 $e^{ikx}$이다.
    - 고유값은 $ik$이며, $k$가 실수이므로 항상 순수 허수이다.