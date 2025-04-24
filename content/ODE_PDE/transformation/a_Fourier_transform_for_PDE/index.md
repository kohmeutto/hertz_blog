+++
title = "(a) Fourier transform for PDE"
weight = 4
+++

---

**푸리에 변환을 수행할 수 있는 조건**

- 적분 범위를 -무한대 부터 무한대로 잡을 수 있는 경계조건이어야 한다.

---

### 1. Expansion

여기에서는 변환 의미인 푸리에 변환을 사용한다.

$$
\hat{f}\left(k\right)=\int_{-\infty}^{\infty}dk\left\lbrack f\left(x\right)e^{-ikx}\right\rbrack
$$

$$
f\left(x\right)=\frac{1}{2\pi}\int_{-\infty}^{\infty}dk\left\lbrack\hat{f}\left(k\right)e^{+ikx}\right\rbrack
$$

---

### 2. Solving PDEs with Fourier methods

**[필수조건] $f(\pm\infty)=0$**

The Fourier transform is one example of an integral transform: a general technique for solving
differential equations. Transformation of a PDE (e.g. from x to k) often leads to simpler equations (algebraic or ODE typically) for the integral transform of the unknown function. This is because spatial derivatives
turn into factors of ik. Similar behaviour is seen in higher numbers of dimensions. When is a
single Fourier mode,

- **1D**

$$
F\left\lbrace\frac{\partial}{\partial x}f\right\rbrace\left(k\right)=\int_{-\infty}^{\infty}dx\left\lbrack e^{-ikx}\frac{\partial}{\partial x}f\left(x\right)\right\rbrack=\int_{-\infty}^{\infty}dx\left\lbrack\frac{\partial}{\partial x}\left\lbrack e^{-ikx}f\left(x\right)\right\rbrack+ike^{ikx}f\left(x\right)\right\rbrack
$$

$$
=\left.e^{-ikx}f\left(x\right)\right|_{-\infty}^{\infty}+ik\int_{-\infty}^{\infty}dx\left\lbrack e^{-ikx}f\left(x\right)\right\rbrack=ikF\left\lbrace f\left(x\right)\right\rbrace\left(k\right)
$$

$$
\frac{\partial}{\partial x}\to ik
$$

$$
\frac{\partial^2}{\partial x^2}\to-k^2
$$

- **3D**

$$
F\left\lbrace\frac{\partial}{\partial\vec{r}}f\right\rbrace\left(\vec{k}\right)=\int_{-\infty}^{\infty}d^3\vec{r}\left\lbrack e^{-i\vec{k}\cdot\vec{r}}\frac{\partial}{\partial\vec{r}}f\left(\vec{r}\right)\right\rbrack=\int_{-\infty}^{\infty}d^3\vec{r}\left\lbrack\frac{\partial}{\partial\vec{r}}\left\lbrack e^{-i\vec{k}\cdot\vec{r}}f\left(\vec{r}\right)\right\rbrack+i\vec{k}e^{-i\vec{k}\cdot\vec{r}}f\left(\vec{r}\right)\right\rbrack
$$

$$
\frac{\partial}{\partial\vec{r}}\to i\vec{k}
$$

$$
\frac{\partial^2}{\partial\vec{r}^2}\to-\left|\left|\vec{k}\right|\right|^2
$$

---

**example1) the diffusion equation**

We add a small drop of ink to a large tank of water (assumed 1 dimensional). We want to find the density of ink as a function of space and time, n(x,t). Initially, all the ink (S particles) is concentrated at one point (call it the origin)

$$
\frac{\partial^2}{\partial x^2}u=\frac{1}{D}\frac{\partial}{\partial t}u,\quad -\infty < x < \infty, \quad t > 0
$$

$$
\text{[I.C]}\quad u\left(x,0\right)=S\delta\left(x\right)
$$

{{< details summary="sol" >}}
    
경계조건이 필요없는 경우 이므로, 공간에 대해, 푸리에 변환을 수행한다.
    
$$
-k^2D\underline{u}\left(k,t\right)=\frac{\partial}{\partial t}\underline{u}\left(k,t\right),\quad -\infty < x < \infty,\quad t > 0
$$

$$
\underline{u}\left(k,t\right)=c_1e^{-k^2Dt}
$$
    
[I.C] 조건을 적용한다.
    
$$
F\left\lbrace u\left(x,0\right)\right\rbrace\left(k,0\right)=S
$$
    
$$
\underline{u}\left(k,0\right)=c_1=S
$$
    
해를 구하기 위해 역 푸리에 변환을 수행한다.
    
$$
F^{-1}\left\lbrace\underline{u}\left(k,t\right)\right\rbrace\left(x,t\right)=\frac{1}{2\pi}\int_{-\infty}^{\infty}dk\left\lbrack c_1e^{-k^2Dt}e^{ikx}\right\rbrack=\frac{S}{2\pi}\int_{-\infty}^{\infty}dk\left\lbrack e^{-\left(Dtk^2-ixk\right)}\right\rbrack
$$
    
[(a) Gaussian integral](https://www.notion.so/a-Gaussian-integral-1cc8bc3f140681639295fb6bf0fd44d6?pvs=21) 를 사용한다.
    
$$
u\left(x,t\right)=\frac{S}{2\pi}\int_{-\infty}^{\infty}dk\left\lbrack e^{-\left(Dtk^2-ixk\right)}\right\rbrack=\frac{S}{2\pi}\sqrt{\frac{\pi}{Dt}}e^{\frac{-x^2}{4Dt}}=\frac{S}{\sqrt{2\pi}\sqrt{2Dt}}e^{\frac{-x^2}{4Dt}}
$$

{{< /details >}}

---

**example2) Fourier solution of the wave equation, 중요**

One is used to thinking of solutions to the wave equation being sinusoidal, but they don’t have to be. We can use Fourier Transforms to show this elegantly, applying a partial FT (x→k, but keeping t as is).

$$
\frac{\partial^2}{\partial x^2}u=\frac{1}{c^2}\frac{\partial^2}{\partial t^2}u,\quad -\infty < x < \infty, \quad t > 0
$$

{{< details summary="sol" >}}

경계조건이 필요 없는 경우 이므로, 공간에 대해, 푸리에 변환을 수행한다. k는 실수이다.

$$    
-k^2c^2\underline{u}\left(k,t\right)=\frac{\partial^2}{\partial t^2}\underline{u}\left(k,t\right), \quad -\infty < x < \infty, \quad t > 0
$$
 
$$
\underline{u}\left(k,t\right)=a_1e^{-i\omega t}+a_2e^{+i\omega t},\quad\omega^2=k^2v^2
$$
    
변수분리 형태를 적용하면,
    
$$
\underline{u}\left(k,t\right)=\underline{f}\left(k\right)e^{-i\omega t}+\underline{g}\left(k\right)e^{+i\omega t},\quad\omega^2=k^2v^2,
$$
      
해를 구하기 위해 역 푸리에 변환을 수행한다.
    
$$
F^{-1}\left\lbrace\underline{u}\left(k,t\right)\right\rbrace\left(x,t\right)=\frac{1}{2\pi}\int_{-\infty}^{\infty}dk\left\lbrack\underline{f}\left(k\right)e^{-i\omega t}+\underline{g}\left(k\right)e^{+i\omega t}\right\rbrack e^{ikx}
$$
    
$$
u\left(x,t\right)=\frac{1}{2\pi}\int_{-\infty}^{\infty}dk\left\lbrack\underline{f}\left(k\right)e^{-i\left(\omega t-kx\right)}+\underline{g}\left(k\right)e^{+i\left(\omega t+kx\right)}\right\rbrack
$$
    
{{< /details >}}

---

**example3) Fourier solution of the Schrodinger equation in 2D, 매우중요**

Consider the time-dependent Schrodinger equation in 2D, for a particle trapped in a (zero) potential 2D square well with infinite potentials on walls at x =0,L, y =0,L

$$
-\frac{\hbar^2}{2m}\nabla^2\psi\left(\vec{r},t\right)=i\hbar\frac{\partial}{\partial t}\psi\left(\vec{r},t\right)
$$

{{< details summary="sol" >}}
   
$$
\frac{\hbar^2}{2m}\left|\left|\vec{k}\right|\right|^2\underline{\psi}\left(\vec{k},t\right)=i\hbar\frac{\partial}{\partial t}\underline{\psi}\left(\vec{k},t\right),\quad\left|\left|\vec{k}\right|\right|^2=k_{x}^2+k_{y}^2
$$

    
변수분리 형태를 적용하고, 위 미분방정식의 해는
    
$$
\underline{\psi}\left(\vec{k},t\right)=\underline{f}\left(k_{x}\right)\underline{g}\left(k_{y}\right)e^{-i\frac{\hbar\left|\left|\vec{k}\right|\right|^2}{2m}t}
$$

해를 구하기 위해 역 푸리에 변환을 수행한다. 에너지가 외부로 전달되지 않는 갇혀 있는 구조에서는 공진이 발생한다. 공진은 시간에 따라, 위아래로 진동하며, 길이는 반파장의 정수배이다. 이미 알고 있는 결과를 사용하면,
    
$$
L=n\frac{\lambda_{n,x}}{2}\implies k_{x}=\frac{n\pi}{L},\quad L=m\frac{\lambda_{m,y}}{2}\implies k_{y}=\frac{m\pi}{L}
$$
    
$$
F^{-1}\left\lbrace\underline{f}\left(k_{x}\right)\right\rbrace\left(x\right)=A_{n}\sin\frac{n\pi x}{L},\quad F^{-1}\left\lbrace\underline{f}\left(k_{y}\right)\right\rbrace\left(y\right)=B_{m}\sin\frac{m\pi y}{L}
$$
    
$$
\psi_{nm}\left(x,y,t\right)=C_{nm}\sin\frac{n\pi x}{L}\sin\frac{m\pi y}{L}\exp\left\lbrack-i\frac{\hbar}{2m}t\left\lbrace\left(\frac{n\pi}{L}\right)^2+\left(\frac{m\pi}{L}\right)^2\right\rbrace\right\rbrack
$$
    
{{< /details >}}

---

[fourier_lectures_part5.pdf](fourier_lectures_part5.pdf)

[도함수의 푸리에 변환 : 네이버 블로그](https://blog.naver.com/pro_000/220850807099)