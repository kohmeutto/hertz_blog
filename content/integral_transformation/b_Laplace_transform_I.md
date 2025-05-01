+++
title = "(b) Laplace transform I"
weight = 3
+++

---

### 0. 정리

(1) $L:=h(t)\ast$ 라고 하자. 이 연산자에 대한 eigenfunction은 $e^{st}$ 이다

$$
e^{st},\quad s\in\mathbb{C}
$$

(2) 이 eigenfuction에 대한 eigenvalue를 라플라스 변환이라고 한다.

$$
\lambda_{s}=\int_{-\infty}^{\infty}dt\left[ h\left(t\right)e^{-st}\right]
$$

---

### 1. Eigenfunction & Eigenvalue

**모든 합성곱에 대한 공통적인 eigenfunction이 존재한다.** **eigenfunction**의 의미는 연산자를 통과하였을 때, '기본성질이 변하지않는 함수`를 의미한다.

이 eigenfunction은

$$
e^{st},\quad s\in\mathbb{C}
$$

이 eigenfunction에 대한 eigenvalue는

$$
h\left(t\right) \ast e^{st}=\int_{-\infty}^{\infty}d\tau\left[h\left(\tau\right) e^{s\left(t-\tau\right)}\right]
=\left\lbrace\int_{-\infty}^{\infty}d\tau\left[h\left(\tau\right)e^{-s\tau}\right]\right\rbrace e^{st}
=\lambda_{s}e^{st}
$$

$$
\lambda_{s}=H\left(s\right)=\int_{-\infty}^{\infty}dt\left[h\left(t\right)e^{-st}\right]
$$

---

### 2. Laplace transformation

위 eigenvalue를 라플라스 변환이라고 한다. 즉, **라플라스 변환**은 연산자의 입력 $e^{st}$에 대한 **eigenvalue**(고유값)을 찾아 내는 방법이다.

$$
\lambda_{s}=L\left\lbrace h\left(t\right)\right\rbrace\left(s\right)=\int_{-\infty}^{\infty}dt\left[h\left(t\right)e^{-st}\right]
$$

---

### 3. 대수방정식

eigenfuction과 eigenvalue를 이용한다는 것은, 복잡한 식을 단순하게 바꿀 수 있는 편리한 도구라는 사용한다는 말과 같다.
convolution에 대한, eigenfuction, $e^{st}$ 은 모두 동일하므로, $e^{st}$은 나눠져서 사라지게 된다.

**즉, eigenvalue에 대한 대수 방정식으로 바뀐다.** 아래의 예를 보면, 쉽게 이해할 수 있다.

$$
y''-7y'=7e^{t}
$$

$$
\implies y''\ast e^{st}-7y'\ast e^{st}=7e^{t}\ast e^{st}
$$

$$
\implies\lambda_1e^{st}+\lambda_2e^{st}=\lambda_3e^{st}
$$

$$
\implies\lambda_1+\lambda_2=\lambda_3
$$

---

### 4. 주의사항

**Laplace transform**은 함수 $h\left(t\right)$ 이 **선형/비선형 인지 상관없이** 수학적으로 수행할 수 있다.