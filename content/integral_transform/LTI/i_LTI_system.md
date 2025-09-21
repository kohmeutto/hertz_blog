+++
title = "(i) LTI system"
weight = 1
+++

---

- LTI system 의 의미에 대해 살펴본다
- LTI system 과 convolution, Laplace transform 의 연관성을 살펴본다 

---

### 1. LTI vs. LTI+causality

- **LTI**: **L**inearity(선형성) + **T**ime 
**I**nvarient(시불변) 의 축약어 이다.

- **LTI+causality**: LTI 특성 + causality(인과성) 이다.

모든 LTI 시스템이 causality 특성을 가지는것이 아니라는 의미이다. 예로, 이상적인 필터는 LTI 특성을 가지지만, 비인과적이다.

---

### 2. LTI

LTI system 이 가지는 특성은 아래와 같다.

**(1) Linearity(선형성)=Superpostion**

Superposition은 Linearity 와 동치이다. 따라서, 두가지 용어를 system 에서 혼용해서 사용해도 같은 의미임을 상기하라.

$$
\text{Superposition}=\text{Addictivity}+\text{Scaling}
$$

$$
f(ax_1+bx_2)=af(x_1)+bf(x_2)
$$

**(2) Time invarient**

시불변은 입력 신호의 시간 공간에 대한 shift가 출력에 **그대로 반영**된다는 것을 의미한다.

먼저, 시스템 f에 의해 입력 x(t)가 출력 y(t)를 생성한다고 가정한다.

$$
y(t)=f\{x(t)\}(t)
$$

시간 입력이 $t_0$ 만큼 shift 되어 있을 때, 출력 역시 **동일하게 $t_0$ 만큼 shift** 되어 있으면, 이것을 time invarient 라고 한다. 

$$
y(t-t_0)=f\{x(t-t_0)\}(t)
$$

만약, $t_1\ne t_0$ 라고 하자. $y(t-t_1)=f\{x(t-t_0)\}(t)$ 이면, 이것은 시불변을 만족하지 않는다.

---

### 3. LTI & Convolution & Laplace transform

이해를 쉽게 하기 위해, 신호가 초당 **해당 순간에만 LTI 시스템 $\mathcal{H}$ 에 입력**한다고 가정한다. $x_k$는 시간 $k$ 에서의 입력의 크기이다.

$$
x_{impulse}(t)
=\cdots+x_{-1}\delta(t+1)+x_0
\delta(t+0)+x_{+1}\delta(t-1)+\cdots
=\sum_{k=-\infty}^{\infty}x_k\delta(t-k)
$$

$$
y(t)
=\mathcal{H}\{x_{impulse}(t)\}(t)
=\mathcal{H}\left\{\sum_{k=-\infty}^{\infty}x_k\delta(t-k)\right\}(t)
$$

**LTI 특성 중 superposition** 을 사용한다.

$$
y(t)
=\mathcal{H}\left\{\sum_{k=-\infty}^{\infty}x_k\delta(t-k)\right\}(t)
=\sum_{k=-\infty}^{\infty}x_k\mathcal{H}\left\{\delta(t-k)\right\}(t)
$$

**LTI 특성 중 time-invariance** 를 사용한다. 시스템 $\mathcal{H}$ 에 대한 impulse 응답은 아래와 같이 표현하자. impluse 응답에 대한 자세한 내용은 다음 아래를 참고한다.

$$
h(t-k)=\mathcal{H}\left\{\delta(t-k)\right\}(t)
$$

따라서,

$$
y(t)
=\sum_{k=-\infty}^{\infty}x_kh(t-k)
$$

연속적인 입력으로 확장하면, $x_k$는 $k$대한 함수, $\sum_{k}$은 $\int_k dk$ 로 쓸 수 있다.

$$
y(t)
=\int_{-\infty}^{\infty} dk\left[x(k)h(t-k)\right]
$$

위 식은 전형적인 convolution 형태이다. 따라서, **LTI 시스템의 출력은 convolution 으로 표현할 수 있음**을 말한다. 여기에서 주의해야 한다.

$$
y(t)
=\int_{-\infty}^{\infty} dk\left[x(k)h(t-k)\right]
=x(t)\ast h(t)
$$

또한, convolution 연산을 쉽게 하기 위해, Laplace transform을 수행할 수 있다. 이것은 아래와 같이 표현된다.

$$
\langle s|x(t)\ast h(t)\rangle=\langle s|x\rangle\langle s|h\rangle
$$

---

### 4. Impulse response

임펄스 응답 $h(t)$는 시스템 $\mathcal{H}$에 **순간적인 충격(임펄스 $\delta(t)$)을 가했을 때 나오는 출력**을 말한다. 앞서 보았듯이 수학적으로 $h(t)=\mathcal{H}\lbrace\delta(t)\rbrace$ 로 정의된다. 하지만 이 $h(t)$가 시스템 전체를 '대표'하고 모든 입력에 대한 출력을 예측하는 데 사용될 수 있는 것은 **오직 LTI(선형 시불변) 시스템의 경우에만 해당**한다.

* **LTI 시스템의 경우:** 임펄스 응답 $h(t)$는 시스템의 모든 특성을 담고 있어, 어떤 입력 $x(t)$가 들어오더라도 출력 $y(t)$를 **합성곱**($x(t) \ast h(t)$)으로 **정확히 예측**할 수 있다. 이것이 LTI 시스템의 핵심이다.

* **LTI 시스템이 아닌 경우:** 임펄스 입력에 대한 출력이 나타나긴 하지만, 이 출력이 $h(t)$처럼 시스템 전체를 대표하거나 다른 입력에 대한 출력을 합성곱으로 예측하는 데 사용될 수는 없다.

$$
\mathcal{H}\left\{\delta(t)\right\}(t)
=\int_{-\infty}^{\infty} d\tau\left[\delta(\tau)h(t-\tau)\right]
=\delta(t)\ast h(t)
=h(t)
$$

위 식을 잘 살펴보면, '$\delta(t)\ast$' 는 **어떠한 함수(시스템)를 sampling 하는 연산자**라는 것을 알수 있다. 다시한번 언급하지만, '$\delta(t)\ast$' 의 샘플링 연산 결과가 의미가 있으려면, 해당 시스템이 LTI 여야 한다.

---


