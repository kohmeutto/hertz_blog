+++
title = "(p) 3D Wave equation for free-space"
weight = 3
+++

---

$$
\nabla^2u\left(\vec{r},t\right)=\frac{1}{v^2}\frac{\partial^2}{\partial t^2}u\left(\vec{r},t\right)
$$

자유 공간에서,

- 파수 중첩의 해

$$
u\left(\vec{r},t\right)=\int_{-\infty}^{\infty}d^3k\left\lbrack c_1\left(\vec{k}\right)e_{}^{i\left(\vec{k}\cdot\vec{r}-\omega t\right)}+c_2\left(\vec{k}\right)e_{}^{i\left(\vec{k}\cdot\vec{r}-\omega t\right)}\right\rbrack
$$

- 주파수 중첩의 해

$$
u\left(\vec{r},t\right)=\int_{-\infty}^{\infty}d\omega\left\lbrack c_1\left(\omega\right)e^{i\left(\vec{k}\cdot\vec{r}-\omega t\right)}+c_2\left(\omega\right)e^{i\left(\vec{k}\cdot\vec{r}-\omega t\right)}\right\rbrack
$$

---

proof) 파수 공간에서의 해, 일반적인 변수 분리법, 전자기학에서 많이 사용 (이전 챕터의 엄밀한 방법은 매우 귀찮음)

라플라시안 연산자에 대한, 변수 분리 방법을 수행한다.

$$
\left(\frac{\partial^2}{\partial x^2}+\frac{\partial^2}{\partial y^2}+\frac{\partial^2}{\partial z^2}\right)X\left(x\right)Y\left(y\right)Z\left(z\right)T\left(t\right)=-k^2X\left(x\right)Y\left(y\right)Z\left(z\right)T\left(t\right)
$$

$$
\frac{1}{X\left(x\right)}\frac{\partial^2}{\partial x^2}X\left(x\right)+\frac{1}{Y\left(y\right)}\frac{\partial^2}{\partial y^2}Y\left(y\right)+\frac{1}{Z\left(y\right)}\frac{\partial^2}{\partial z^2}Z\left(z\right)=-k^2
$$

$$
\frac{\partial^2}{\partial x^2}X\left(x\right)=-k_{x}^2X\left(x\right),\quad X\left(x;k_{x}\right)=a_1e^{-ik_{x}x}+a_2e^{+ik_{x}x}
$$

$$
k^2=k_{x}^2+k_{y}^2+k_{z}^2
$$

$$
\frac{\partial^2}{\partial y^2}Y\left(y\right)=-k_{y}^2Y\left(y\right),\quad Y\left(y;k_{y}\right)=b_1e^{-ik_{y}y}+b_2e^{+ik_{y}y}
$$

$$
\frac{\partial^2}{\partial z^2}Z\left(z\right)=-k_{z}^2Z\left(z\right),\quad Z\left(z;k_{z}\right)=c_1e^{-ik_{z}z}+c_2e^{+ik_{z}z}
$$

시간에 대해서,

$$
k^2\varphi\left(x,y,z,t\right)=\frac{1}{v^2}\frac{\partial^2}{\partial t^2}\varphi\left(x,y,z,t\right)
$$

$$
\left(\frac{\partial^2}{\partial t^2}+\omega^2\right)T\left(t\right)=0,\quad\omega^2=k^2v^2
$$

$$
T\left(x;\omega\right)=d_1e^{-i\omega t}+d_2e^{+i\omega t}
$$

연속적인 k가 존재한다면, 중첩형태로 표현할 수 있다.

$$
u\left(\vec{r},t\right)=\int_{-\infty}^{\infty}\int_{-\infty}^{\infty}\int_{-\infty}^{\infty}dk_{x}dk_{y}dk_{z}\left\lbrack X\left(x;k_{x}\right)Y\left(y;k_{y}\right)Z\left(z;k_{z}\right)T\left(t;\omega\right)\right\rbrack
$$

$$
=\int_{-\infty}^{\infty}\int_{-\infty}^{\infty}\int_{-\infty}^{\infty}dk_{x}dk_{y}dk_{z}\left\lbrack c\left(k_{x},k_{y},k_{z}\right)e_{}^{i\left(k_{x}x+k_{y}y+k_{z}z\right)}\left(d_1e^{_{}-i\omega t}+d_2e^{_{}+i\omega t}\right)\right\rbrack
$$

$$
=\int_{-\infty}^{\infty}d^3\vec{k}\left\lbrack c_1\left(\vec{k}\right)e_{}^{i\left(\vec{k}\cdot\vec{r}-\omega t\right)}+c_2\left(\vec{k}\right)e_{}^{i\left(\vec{k}\cdot\vec{r}-\omega t\right)}\right\rbrack
$$