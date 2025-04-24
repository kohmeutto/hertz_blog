+++
title = "(p) 1D Wave equation for free-space"
weight = 2
+++

---

1차원 파동방정식의 해는 아래와 같다.

$$
\frac{\partial^2}{\partial x^2}u\left(x,t\right)=\frac{1}{v^2}\frac{\partial^2}{\partial t^2}u\left(x,t\right)
$$

자유 공간에서,

- 파수 중첩의 해

$$
u\left(x,t\right)=\int_{-\infty}^{\infty}dk\left\lbrack c_1\left(k\right)e^{i\left(kx-\omega t\right)}+c_2\left(k\right)e^{i\left(kx+\omega t\right)}\right\rbrack
$$

- 주파수 중첩의 해

$$
u\left(x,t\right)=\int_{-\infty}^{\infty}d\omega\left\lbrack c_1\left(\omega\right)e^{i\left(kx-\omega t\right)}+c_2\left(\omega\right)e^{i\left(kx+\omega t\right)}\right\rbrack
$$

---

**proof1) 양자역학에서 보는 관점(스텀-리우빌 적용), 아주 엄밀한 풀이**

$$
\frac{\partial^2}{\partial x^2}u\left(x,t\right)=\frac{1}{v^2}\frac{\partial^2}{\partial t^2}u\left(x,t\right)
$$

자유공간에서 라플라시안 연산자에 대해, 고유값과 고유함수를 구한다. 고유값과 고유함수가 연속적임을 이해해야 한다.

$$
L:=\frac{\partial^2}{\partial x^2}
$$

$$
\frac{\partial^2}{\partial x^2}X\left(x\right)T\left(x\right)_{}=-k^2X\left(x\right)T\left(x\right)
$$

$$
\left(\frac{\partial^2}{\partial x^2}+k^2\right)X\left(x\right)=0
$$

(1) $k\ne0$

$$
X\left(x\right)=a_1e^{-ikx}+a_2e^{ikx}
$$

(2) $k=0$

$$
X\left(x\right)=0
$$

eigen-expansion 을 수행한다. 미분연산자는 self-adjoint 함을 알고 있기 때문에, 적분 범위는 실수축에서 수행됨을 알아야 한다. 해는 다음과 같다.

$$
u\left(x,t\right)=\int_{-\infty}^{\infty}dk\left\lbrack c\left(k\right)e^{ikx}T\left(t\right)\right\rbrack
$$

위는 파동 방정식의 해 이므로, 파동 방정식에 대입하면, T(t)를 구할 수 있다.

$$
k^2T\left(t\right)=\frac{1}{v^2}\frac{\partial^2}{\partial t^2}T\left(t\right)
$$

$$
\left(\frac{\partial^2}{\partial t^2}+\omega^2\right)T\left(t\right)=0,\quad\omega^2=k^2v^2
$$

$$
T\left(x\right)=b_1e^{-i\omega t}+b_2e^{i\omega t}
$$

따라서, 최종적으로 파동방정식의 해는 다음과 같다.

$$
u\left(x,t\right)=\int_{-\infty}^{\infty}dk\left\lbrack c_1\left(k\right)e^{i\left(kx-\omega t\right)}+c_2\left(k\right)e^{i\left(kx+\omega t\right)}\right\rbrack
$$

주파수 공간에서는 k를 ω로 바꾸기만 하면 된다.

$$
u\left(x,t\right)=\int_{-\infty}^{\infty}d\omega\left\lbrack c_1\left(\omega\right)e^{i\left(kx-\omega t\right)}+c_2\left(\omega\right)e^{i\left(kx+\omega t\right)}\right\rbrack
$$

푸리에 (역)변환과 동일한 형태이다. 잘 생각해보면, 파동의 중첩을 만족하기 때문에, 위의 결과는 당연하다.

---

**proof2) 페이저 변환과 중첩을 사용한 쉬운 풀이, 고전역학 & 전자기학 에서 많이 사용**

$e^{-i \omega t}$를 기준으로, 페이저 변환을 수행한다.

$$
\nabla^2\tilde u\left(x\right)=-\frac{\omega^2}{v^2}\tilde u\left(x\right)
$$

$$
\left(\nabla^2+\frac{\omega^2}{v^2}\right)\tilde u\left(x\right)=0
$$

$\displaystyle k=\frac{\omega}{v}$이면,

$$
\left(\nabla^2+k^2\right)\tilde u\left(x\right)=0
$$

따라서,

$$
u\left(x,t\right)=\operatorname{Re}\left\lbrack\tilde u\left(x\right)e^{-i\omega t}\right\rbrack
$$

1차원의 x방향 & 주파수가 중첩이 되어 있다고 하면,

$$
u\left(x,t\right)=\operatorname{Re}\left\lbrack\int d\omega\left\lbrack c_1\left(\omega\right)e^{i\left(kx-\omega t\right)}+c_2\left(\omega\right)e^{-i\left(kx+\omega t\right)}\right\rbrack\right\rbrack
$$

---

**proof3) 푸리에 변환을 사용한 풀이**

[(a) Fourier transform for PDE]({{% ref "ODE_PDE/transformation/b_phasor_transform_for_PDE.md" %}}) 를 참조한다.

---

###### Q) 왜 증명 2와 3은 엄밀하지 않은가.

---

[ABC for waves](https://www.ibiblio.org/e-notes/webgl/gpu/boundary.htm)