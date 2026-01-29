+++
title = "(b) Copy-shift II"
weight = 2
+++

---

### 1. 이동연산자의 생성자(Generator)

함수의 기울기를 구할 있듯 연산자의 기울기를 생성자(Generator)라고 한다.

$$
\hat{G}=-\frac{d}{d u}
$$

proof)

이동연산자의 생성자는 덧셈의 항등원($\tau=0$) 지점에서의 접선의 기울기를 계산하는 것이다.

$$
\hat{G}
=\hat{D}_{\tau\to0}\hat{S}_\tau
=\left.\frac{\partial}{\partial\tau}\hat{S}_\tau\right|_{\tau=0}
$$

$u$로 사영하여 표현한다.

$$
\hat{G}\psi(u)
=\left.\frac{\partial}{\partial\tau}\hat{S}_\tau\psi(u)\right|_{\tau=0}
=\left.\frac{\partial}{\partial\tau}\psi(u-\tau)\right|_{\tau=0}
$$

여기에서, $X=u-\tau$ 라고 하면,

$$
\left.\frac{\partial}{\partial\tau}\psi(u-\tau)\right|_{\tau=0}
=\left.\frac{\partial\psi}{\partial X}\frac{\partial X}{\partial\tau}\right|_{\tau=0}
=-\frac{d}{du}\psi(u)
$$

따라서,

$$
\hat{G}=-\frac{d}{d u}
$$

---

### 2. 생성자 & 이동연산자의 고유값과 고유벡터

**(1) 생성자와 이동연산자의 교환자**

생성자와 이동연산자의 고유벡터는 동일하므로,

$$
[\hat{S}_\tau,\hat{G}]=0
$$

**(2) 생성자**

$$
\hat{G}|s\rangle=-s|s\rangle
$$

$$
\text{eigenvalue: } -s
$$

$$
\text{eigenvector: } |s\rangle=\int du\,e^{su}|u\rangle\implies
\langle u^d|s\rangle=e^{su}
$$

**(3) 이동연산자**

$$
\hat{S}_\tau|s\rangle=e^{-s\tau}|s\rangle
$$

$$
\text{eigenvalue: } \lambda(\tau)=e^{-s\tau}
$$

$$
\text{eigenvector: } |s\rangle=\int du\,e^{su}|u\rangle\implies
\langle u^d|s\rangle=e^{su}
$$

proof)

$$
\hat{S}_\tau|s\rangle=\lambda(\tau)|s\rangle,
\text{ where } \lambda(0)=1
$$

$u$ 로 사영하면,

$$
\hat{S}_\tau \psi_s(u)
=\psi_s(u-\tau)
=\lambda(\tau)\psi_s(u)
$$

양변을 $\tau=0$ 지점에서 미분한다. 이것은 위에서의 생성자 과정과 동일하다. 따라서,

$$
\hat{D}_{\tau\to0}\hat{S}_\tau\psi_s(u)
=\hat{G}\psi_s(u)
=-\frac{d}{du}\psi_s(u)
$$

$$
\left.\frac{d}{d\tau}\lambda(\tau)\psi_s(u)\right|_{\tau\to0}=\lambda'(0)\psi_s(u)
$$

위 2개의 식이 동일함을 사용한다. $\lambda'(0)=-s$로 놓고, 미분방정식을 푼다. 따라서,

$$
\psi_s(u)
=\langle u^d|s\rangle
=Ce^{s u}
$$

$\psi_s(u-\tau)=\lambda(\tau)\psi_s(u)$, $\lambda'(0)=-s$, $\lambda(0)=1$ 를 사용하여, 고유값을 구하면,

$$
\lambda(\tau)
=e^{-s\tau}
$$

---

### 3. 생성자를 사용한 이동연산자의 표현 (연산자의 지수화)

$$
\hat{S}_\tau = e^{\tau \hat{G}}
$$

proof)

위 결과들을 종합하여 이동 연산자를 스펙트럼 분해(Spectral Decomposition)하면, 생성자와 이동 연산자 사이의 지수 함수 관계를 대수적으로 증명할 수 있다.

$$
\hat{S}_\tau
= \hat{S}_\tau \hat{I}
= \int ds \, \hat{S}_\tau |s\rangle \langle s^d|
= \int ds \, e^{-s\tau} |s\rangle \langle s^d|
$$

여기서 연산자 함수의 성질을 적용한다. 테일러 급수 전개에 의해서,

$$
e^{\tau\hat{G}}
=\hat{I}+\tau\hat{G}+\frac{\tau^2}{2!}\hat{G}^2+\cdots
$$

$$e^{\tau\hat{G}}|s\rangle
= \left(\sum_{n=0}^{\infty} \frac{\tau^n}{n!} \hat{G}^n \right) |s\rangle
= \sum_{n=0}^{\infty} \frac{\tau^n}{n!} (-s)^n |s\rangle
= \left(\sum_{n=0}^{\infty} \frac{(-s\tau)^n}{n!} \right) |s\rangle
= e^{-s\tau}|s\rangle
$$

따라서,

$$
\hat{S}_\tau
= \int ds \, e^{\tau \hat{G}} |s\rangle \langle s^d|
= e^{\tau \hat{G}} \left( \int ds |s\rangle \langle s^d| \right)
$$

괄호 안은 항등 연산자 $\hat{I}$ 이므로, 최종적으로 다음 관계가 성립한다.

$$
\hat{S}_\tau = e^{\tau \hat{G}}
$$

---

### 4. 리 군(Lie Group)의 적분을 이용한 유도

---

### 5. Unitary 가 될 조건



