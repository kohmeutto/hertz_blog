+++
title = "(p) Diffusion equation for periodic boundary condition"
weight = 5
+++

---

Diffusion equation

$$
\frac{\partial^2u}{\partial x^2}=\frac{1}{D}\frac{\partial u}{\partial t}
$$

periodic boundary condition

$$
u\left(0,t\right)=u\left(L,t\right)
$$

$$
\frac{\partial}{\partial x}\left(0,t\right)=\frac{\partial}{\partial x}u\left(L,t\right)
$$

해는 다음과 같다.

$$
u\left(x,t\right)=a_0+\sum_{n=1}^{\infty}\left(a_{n}\cos k_{n}x+b_{n}\sin k_{n}x\right)e_{}^{-Dk_{n}^2t}
$$

$$
u\left(x,t\right)=\sum_{n=1}^{\infty}c_{n}e_{}^{-\left(Dk_{n}^2t-ik_{n}x\right)}
$$

---

**proof1)**

$$
\frac{\partial^2}{\partial x^2}X_{n}\left(x\right)T_{n}\left(t\right)=-k_{n}^2X_{n}\left(x\right)T_{n}\left(t\right)
$$

(1) $k_{n}\ne0$

$$
X_{n}\left(x\right)=a_{n}\cos k_{n}x+b_{n}\sin k_{n}x
$$

(2) $k_{0}=0$

$$
X_{n}\left(x\right)=a_{n}+b_{n}x
$$

boundary condition 을 적용한다.

(1) $k_{n}\ne0$

$$
X_{n}\left(0\right)=a_{n}
$$

$$
X_{n}\left(L\right)=a_{n}\cos k_{n}L+b_{n}\sin k_{n}L
$$

$$
k_{n}=\frac{2n\pi}{L}
$$

(2) $k_{0}=0$

$$
b_0=0
$$

$$
X_0\left(x\right)=a_0
$$

연산자가 self-adjoint 함을 이용하여 각 계수를 구한다.

(1) $k_{n}\ne0$

$$
1=\int_0^{L}dx\left\lbrack\left|X\left(x\right)\right|^2\right\rbrack
$$

$$
=\int_0^{L}dx\left\lbrack a_{n}^2\cos^2k_{n}x+b_{n}^2\sin^2k_{n}L+2a_{n}b_{n}\cos k_{n}x\sin k_{n}x\right\rbrack
$$

$$
=\frac{L}{2}\left(a_{n}^2+b_{n}^2\right)
$$

(2) $k_{0}=0$

$$
1=\int_0^{L}dx\left\lbrack\left|X_0\left(x\right)\right|^2\right\rbrack=a_0^2L
$$

$$
a_0=\pm\frac{1}{\sqrt{L}}
$$

시간에 대해 구하면,

$$
k_{n}^2T_{n}\left(t\right)=\frac{1}{D}\frac{\partial}{\partial t}T_{n}\left(t\right)
$$

$$
\left(\frac{\partial}{\partial t}+Dk_{n}^2\right)T_{n}\left(t\right)=0
$$

$$
T_{n}\left(t\right)=e^{-Dk_{n}^2t}
$$

eigen-expansion 을 수행하면, 다음과 같다.

$$
u\left(x,t\right)=a_0+\sum_{n=1}^{\infty}\left(a_{n}\cos k_{n}x+b_{n}\sin k_{n}x\right)e^{-Dk_{n}^2t}
$$

만약, 초기 조건이 주어진다면, 각 계수를 구할 수 있다.

$$
a_0=\frac{1}{L}\langle1,u\left(x,0\right)\rangle
$$

$$
a_{n}=\frac{2}{L}\langle\cos k_{n}x,u\left(x,0\right)\rangle
$$

$$
b_{n}=\frac{2}{L}\langle\sin k_{n}x,u\left(x,0\right)\rangle
$$

---

**proof2)**

$$
\frac{\partial^2}{\partial x^2}X_{n}\left(x\right)T_{n}\left(t\right)=-k_{n}^2X_{n}\left(x\right)T_{n}\left(t\right)
$$

(1) $k_{n}≠0$

$$
X_{n}\left(x\right)=a_{n}e_{}^{-ik_{n}x}+b_{n}e_{}^{+ik_{n}x}
$$

(2) $k_{0}=0$

$$
X_0\left(x\right)=a_0+b_0x
$$

boundary condition 을 적용한다.

(1) $k_{n}\ne0$

주기적 boundary condition 이므로, 아래와 같이 볼 수 있다.

$$
X_{n}\left(x\right)=b_{n}e^{+ik_{n}x}
$$

$$
b_{n}=b_{n}e^{+ik_{n}L}
$$

$$
k_{n}=\frac{2n\pi}{L}
$$

(2) $k_{0}=0$

$$
b_0=0
$$

$$
X_0\left(x\right)=a_0
$$

따라서, x에 대한 변수분리 해는 다음과 같다.

$$
X_{n}\left(x\right)=b_{n}e_{}^{+i_{}k_{n}x}
$$

연산자가 self-adjoint 함을 이용하여 계수를 구한다.

$$
1=\int_0^{L}dx\left\lbrack\left|X_{n}\left(x\right)\right|^2\right\rbrack=b_{n}^2L
$$

$$
b_{n}=\pm\frac{1}{\sqrt{L}}
$$

시간에 대해 구하면,

$$
k_{n}^2T_{n}\left(t\right)=\frac{1}{D}\frac{\partial}{\partial t}T_{n}\left(t\right)
$$

$$
\left(\frac{\partial}{\partial t}+Dk_{n}^2\right)T_{n}\left(t\right)=0
$$

$$
T_{n}\left(t\right)=e_{}^{-Dk_{n}^2t}
$$

eigen-expansion 을 수행하면, 다음과 같다.

$$
u\left(x,t\right)=\sum_{n=1}^{\infty}c_{n}e_{}^{-\left(Dk_{n}^2t-ik_{n}x\right)}
$$

만약, 초기 조건이 주어진다면, 계수를 구할 수 있다.

$$
c_{n}=\frac{1}{L}\langle e_{}^{ik_{n}x},u\left(x,0\right)\rangle
$$

---

[Separation of Variables III: Periodic Boundaries - Partial Differential Equations | Lecture 8](https://www.youtube.com/watch?v=KD85qwNt9Ak)