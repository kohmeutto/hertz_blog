+++
title = "(p) Non free-space"
weight = 6
+++

---

example1) wave equation

The vertical displacement u(x,t) of a string of length L that is freely vibrating in the vertical plane.

$$
\frac{\partial^2}{\partial x^2}u\left(x,t\right)=\frac{1}{v^2}\frac{\partial^2}{\partial t^2}u\left(x,t\right)
$$

$$
\left\lbrack \text{B.C}\right\rbrack\quad u\left(0,t\right)=u\left(L,t\right)=0
$$

$$
\left\lbrack \text{I.C}\right\rbrack\quad u\left(x,0\right)=f\left(x\right),\quad u_{t}\left(x,0\right)=g\left(x\right)
$$

{{< details summary="sol" >}}

$$
u_{n}\left(x,t\right)=X_{n}\left(x\right)T_{n}\left(t\right)
$$

$$
\nabla^2u_{n}\left(x,t\right)=-k_{n}^2u_{n}\left(x,t\right)\implies\nabla^2X_{n}\left(x\right)=-k_{n}^2X_{n}\left(x\right)
$$

$$
\left(\nabla^2+k_{n}^2\right)X_{n}\left(x\right)=0
$$

$$
X_{n}\left(x\right)=a_{x,n}\cos k_{n}x+b_{x,n}\sin k_{n}x
$$

B.C을 적용한다.

$$
X_{n}\left(0\right)=0=a_{x,n}
$$

$$
X_{n}\left(L\right)=0=b_{x,n}\sin k_{n}x
$$

따라서,

$$
k_{n}L=n\pi,\quad n=1,2,3,\cdots
$$

$$
k_{n}=\frac{n\pi}{L},\quad n=1,2,3,\cdots
$$

$$
X_{n}\left(x\right)=b_{x,n}\sin\frac{n\pi}{L}x,\quad n=1,2,3,\cdots
$$

$$
\frac{\partial^2}{\partial t^2}T_{n}\left(t\right)=-\omega_{n}^2T_{n}\left(t\right),\quad\omega_{n}^2=v^2k_{n}^2
$$

$$
T_{n}\left(t\right)=a_{t,n}\cos\omega_{n}t+b_{t,n}\sin\omega_{n}t
$$

따라서,

$$
u_{n}\left(x,t\right)=\left(A_{n}\cos\omega_{n}t+B_{n}\sin\omega_{n}t\right)\sin\left(\frac{n\pi}{L}x\right)
$$

eigen-expansion 을 수행한다.

$$
u\left(x,t\right)=\sum\left(c_{n,1}\cos\omega_{n}t+c_{n,2}\sin\omega_{n}t\right)\sin\left(\frac{n\pi}{L}x\right)
$$

[I.C] $u\left(x,0\right)=f\left(x\right)$

$$
u\left(x,0\right)=\sum c_{n,1}\sin\left(\frac{n\pi}{L}x\right)=f\left(x\right)
$$

$$
c_{n,1}\int_0^{L}dx\left\lbrack\sin^2\left(\frac{n\pi}{L}x\right)\right\rbrack=\int_0^{L}dx\left\lbrack f\left(x\right)\sin\left(\frac{n\pi}{L}x\right)\right\rbrack
$$

$$
\int_0^{L}dx\left\lbrack\sin^2\left(\frac{n\pi}{L}x\right)\right\rbrack=\frac12\int_{-L}^{L}dx\left\lbrack\sin^2\left(\frac{n\pi}{L}x\right)\right\rbrack=\frac{L}{2}
$$

$$
c_{n,1}=\frac{2}{L}\int_0^{L}dx\left\lbrack f\left(x\right)\sin\left(\frac{n\pi}{L}x\right)\right\rbrack
$$

[I.C] $u_{t}\left(x,0\right)=g\left(x\right)$

$$
u_{t}\left(x,0\right)=\sum c_{n,2}\omega_{n}\sin\left(\frac{n\pi}{L}x\right)
$$

$$
c_{n,2}\omega_{n}\int_0^{L}dx\left\lbrack\sin^2\left(\frac{n\pi}{L}x\right)\right\rbrack=\int_0^{L}dx\left\lbrack g\left(x\right)\sin\left(\frac{n\pi}{L}x\right)\right\rbrack
$$

$$
c_{n,2}=\frac{2}{\omega_{n}L}\int_0^{L}dx\left\lbrack g\left(x\right)\sin\left(\frac{n\pi}{L}x\right)\right\rbrack
$$

{{< /details >}}

---

example2)

$$

f\left(x\right)\frac{\partial^2}{\partial x^2}u+g\left(x\right)\frac{\partial}{\partial x}u+h\left(x\right)u=\frac{\partial}{\partial t}u+k\left(t\right)u
$$

$$
u\left(a,t\right)=u\left(b,t\right)=0
$$

$$
u\left(x,0\right)=s\left(x\right)
$$

{{< details summary="sol" >}}

$$
u_{n}\left(x,t\right)=X_{n}\left(x\right)T_{n}\left(t\right)
$$

$$
\left\lbrack f\left(x\right)\frac{\partial^2}{\partial x^2}+g\left(x\right)\frac{\partial}{\partial x}+h\left(x\right)\right\rbrack X_{n}=\lambda_{n}X_{n}\left(x\right)
$$

Strum-Liouville 형태로 변형한다.

$$
\left\lbrack\frac{\partial^2}{\partial x^2}+\frac{g\left(x\right)}{f\left(x\right)}\frac{\partial}{\partial x}+\frac{h\left(x\right)}{f\left(x\right)}\right\rbrack X_{n}=\lambda_{n}\frac{1}{f\left(x\right)}X_{n}\left(x\right)
$$

$$
r\left(x\right)=e^{\int dx\left\lbrack\frac{g\left(x\right)}{f\left(x\right)}\right\rbrack}
$$

$$
\left\lbrack D\left(r\left(x\right)D\right)+r\left(x\right)\frac{h\left(x\right)}{f\left(x\right)}\right\rbrack X_{n}=\lambda_{n}\frac{r\left(x\right)}{f\left(x\right)}X_{n}
$$

아래와 같은 weight function 을 선택한다.

$$
w\left(x\right)=-\frac{r\left(x\right)}{f\left(x\right)}=-\frac{1}{f\left(x\right)}e^{\int dx\left\lbrack\frac{g\left(x\right)}{f\left(x\right)}\right\rbrack}
$$

B.C 을 만족해야 한다.

$$
X_{n}\left(a\right)=X_{n}\left(b\right)=0
$$

<hr>

$$
\lambda_{n}T_{n}=\left\lbrack\frac{\partial}{\partial t}+k\left(t\right)\right\rbrack T_{n}\implies\lambda_{n}-k\left(t\right)=\frac{1}{T_{n}}\frac{\partial T_{n}}{\partial t}
$$

$$
\int_0^{t}dt'\left\lbrack\lambda_{n}-k\left(t'\right)\right\rbrack=\int_0^{T_{n}}dT_{n}'\left\lbrack\frac{1}{T_{n}'}\right\rbrack\implies\ln T_{n}=\lambda_{n}t-\int_0^{t}dt'\left\lbrack k\left(t'\right)\right\rbrack
$$

$$
T_{n}=\exp\left(\lambda_{n}t-\int_0^{t}dt'\left\lbrack k\left(t'\right)\right\rbrack\right)
$$

I.C 을 만족해야한다.

$$
T_{n}\left(s\right)=0
$$

eigen-expansion 을 수행한다.

$$
u\left(x,t\right)=\sum c_{n}X_{n}\left(x\right)\exp\left(\lambda_{n}t-\int_0^{t}dt'\left\lbrack k\left(t'\right)\right\rbrack\right)
$$

I.C 을 만족해야 한다.

$$
u\left(x,0\right)=\sum c_{n}X_{n}\left(x\right)=s\left(x\right)
$$

$X_{n}$ 은 self-adjoint 한 연산자의 eigen-vector 이므로,

$$
c_{n}=\left\langle X_{n}\left(x\right)|s\left(x\right)\right\rangle_{w}
$$

{{< /details >}}

---

[Sturm–Liouville theory - Wikipedia](https://en.wikipedia.org/wiki/Sturm%E2%80%93Liouville_theory)

[Separable partial differential equation - Wikipedia](https://en.wikipedia.org/wiki/Separable_partial_differential_equation)