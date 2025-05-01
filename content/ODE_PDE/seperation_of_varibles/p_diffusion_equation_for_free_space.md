+++
title = "(p) Diffusion equation for free-space"
weight = 4
+++

---

Diffusion equation

$$
\frac{\partial^2u}{\partial x^2}=\frac{1}{D}\frac{\partial u}{\partial t}
$$

free-space 에서 해는 다음과 같다.

$$
u\left(x,t\right)=\int_{-\infty}^{\infty}dk\left\lbrack c\left(k\right)e_{}^{-\left(Dtk^2-ixk\right)}\right\rbrack
$$

---

**proof)**

$$
\frac{\partial^2}{\partial x^2}X\left(x\right)T\left(t\right)=-k^2X\left(x\right)T\left(t\right)
$$

(1) $k\ne0$

$$
X\left(x\right)=ae_{}^{-ikx}+be_{}^{+i_{}kx}
$$

(2) $k_{0}=0$

$$
X_0\left(x\right)=0
$$

시간에 대해 구하면,

$$
LG(x, x') = 0
$$

$$
G(x, x') = 
\begin{cases}
    c_1(x') u_1(x)  x < x' \\
    c_2(x') u_2(x)  x > x'
\end{cases}
$$

연속적인 고유값에 대한, eigen-expansion 을 수행하면, 다음과 같다.

$$
u\left(x,t\right)=\int_{-\infty}^{\infty}dk\left\lbrack c\left(k\right)e_{}^{-\left(Dtk^2-ixk\right)}\right\rbrack
$$

만약, c(k)=c 인 단일 상수 라면, 가우시안 적분법([(a) Gaussian integral](https://www.notion.so/a-Gaussian-integral-1cc8bc3f140681639295fb6bf0fd44d6?pvs=21) )을 사용하여 아래와 같이 표현할 수 있다.

$$
u\left(x,t\right)=c\int_{-\infty}^{\infty}dk\left\lbrack e_{}^{-\left(Dtk^2-ixk\right)}\right\rbrack=c\sqrt{\frac{\pi}{Dt}}e^{-\frac{x^2}{4Dt}}
$$

푸리에 변환을 이용한 풀이는 [(a) Fourier transform for PDE]({{% ref "ODE_PDE/transformation/a_Fourier_transform_for_PDE/index.md" %}}) 을 참고한다.