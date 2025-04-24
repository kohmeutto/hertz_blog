+++
title = "(b) Strum-Liouville operator"
weight = 1
+++

---

### 1. 스텀-리우빌 선형 연산자

스텀-리우빌 형태는 아래와 같다.

$$
L_{p}=\frac{d}{dx}\left(p\left(x\right)\frac{d}{dx}\right)+q\left(x\right), \quad p\left(x\right)>0, \quad p\left(x\right)\text{는 일차 미분 가능해야 함}
$$

---

### 2. Integrating factor

'임의의 2차 상미분방정식'을 모두 스텀텀-리우빌 미분방정식으로 표현하여 해의 특성에 대해 미리 예측하고 성질을 파악할 수 있다.

###### (1) $p'_0\left(x\right)=p_1\left(x\right)$ 경우

$$
L=p_0\left(x\right)\frac{d^2}{dx^2}+p_1\left(x\right)\frac{d}{dx}+p_2\left(x\right) 
$$

$$
L=\frac{d}{dx}\left(p_0\left(x\right)\frac{d}{dx}\right)+p_2\left(x\right)
$$

###### (2) $p_0'\left(x\right)\ne p_1\left(x\right)$ 경우

위 (1)번과 같이 바꿀 수 없다. 따라서, 적절한 함수를 곱하여, 스텀-리우빌 형태로 만들어보자.

$$
L=p_0\left(x\right)\frac{d^2}{dx^2}+p_1\left(x\right)\frac{d}{dx}+p_2\left(x\right)\implies L_{p}=\frac{d}{dx}\left(p\left(x\right)\frac{d}{dx}\right)+q\left(x\right)
$$

스트룸-리우빌 형태로 만들기 위해, 적절한 함수를 곱한다. 따라서,

$$
r\left(x\right)L=r\left(x\right)p_0\left(x\right)\frac{d^2}{dx^2}+r\left(x\right)p_1\left(x\right)\frac{d}{dx}+r\left(x\right)p_2\left(x\right) 
$$

$$
L_{p}=r\left(x\right)L=\left\lbrack\frac{d}{dx}\left(p\left(x\right)\frac{d}{dx}\right)+q\left(x\right)\right\rbrack,\quad r\left(x\right)p_0\left(x\right)=p\left(x\right)
$$

$\left\lbrack r\left(x\right)p_0^{}\left(x\right)\right\rbrack'=r\left(x\right)p_1\left(x\right)$를 만족시키는 r(x)를 구하면, 스트룸-리우빌 형태로 만들 수 있다.

$$
\left\lbrack r\left(x\right)p_0\left(x\right)\right\rbrack'=r\left(x\right)p_1\left(x\right)
$$

$$
r'\left(x\right)p_0\left(x\right)+r\left(x\right)p_0'\left(x\right)=r\left(x\right)p_1\left(x\right) 
$$

$$
\frac{r'\left(x\right)}{r\left(x\right)}=\frac{p_1\left(x\right)-p_0'\left(x\right)}{p_0^{}\left(x\right)}
$$

위의 미분방정식을 풀면,

$$
\int dx\left\lbrack\frac{r'\left(x\right)}{r\left(x\right)}\right\rbrack=\int dx\left\lbrack\frac{p_1\left(x\right)-p_0'\left(x\right)}{p_0\left(x\right)}\right\rbrack 
$$

$$
\ln\left\lbrack r\left(x\right)\right\rbrack=-\ln\left\lbrack p_0\left(x\right)\right\rbrack+\int dx\left\lbrack\frac{p_1\left(x\right)}{p_0\left(x\right)}\right\rbrack 
$$

$$
r\left(x\right)=\frac{1}{p_0\left(x\right)}\exp\left(\int dx\left\lbrack\frac{p_1\left(x\right)}{p_0^{}\left(x\right)}\right\rbrack\right)
$$

위 식은, 스트룸-리우빌 형로 만들기 위한 함수이다.

---

**example1) Hermitle's ODE**

$$
y''-2xy'+2ny=0
$$

{{< details summary="sol" >}}

$$
y''-2xy'=-2ny $$
$$
r\left(x\right)=\exp\left(\int dx\left\lbrack-2x\right\rbrack\right)=e^{-x^2} 
$$

$$
e^{-x^2}\left(D^2-2xD\right)u_{n}=-2ne^{-x^2}u_{n} 
$$

$$
D\left\lbrack e^{-x^2}D\right\rbrack u_{n}=-2ne^{-x^2}u_{n} 
$$

$$
\lambda_{n}=2n,\quad w\left(x\right)=e^{-x^2}
$$

{{< /details >}}

**example2) Laguerre’s ODE (라게르 미분방정식)**

$$
xy''+\left(1-x\right)y'+ay=0
$$

{{< details summary="sol" >}}

$$
\left(D^2+\frac{1-x}{x}D\right)u_{n}=-a\frac{1}{x}u_{n} 
$$

$$
r\left(x\right)=\exp\left(\int dx\left\lbrack\frac{1-x}{x}\right\rbrack\right)=\exp\left(-x+\ln x\right)=xe^{-x} 
$$

$$
\frac{d}{dx}\left(xe^{-x}\frac{d}{dx}\right)u_{n}=-ae^{-x}u_{n} 
$$

$$
\lambda_{n}=a,\quad w\left(x\right)=e^{-x}
$$

{{< /details >}}

**example3) Legendre’s ODE**

$$
\left(1-x^2\right)y''-2xy'+l\left(l+1\right)y=0
$$

{{< details summary="sol" >}}

$$
\left\lbrack D^2-\frac{2x}{1-x^2}D\right\rbrack u_{n}=-\frac{l\left(l+1\right)}{1-x^2}u_{n} 
$$

$$
r\left(x\right)=\exp\left(\int dx\left\lbrack-\frac{2x}{1-x^2}\right\rbrack\right)=1-x^2 
$$

$$
D\left\lbrack\left(1-x^2\right)D\right\rbrack u_{n}=-l\left(l+1\right)u_{n} 
$$

$$
\lambda_{n}=l\left(l+1\right),\quad w\left(x\right)=1
$$

{{< /details >}}

**example4) Chebyshev’s ODE**

$$
\left(1-x^2\right)y''-xy'+n^2y=0
$$

{{< details summary="sol" >}}

$$
y''-\frac{x}{1-x^2}y'=-\frac{n^2}{1-x^2}y 
$$

$$
r\left(x\right)=\exp\left(\int dx\left\lbrack-\frac{x}{1-x^2}\right\rbrack\right)=\exp\left(\frac12\ln\left(1-x^2\right)\right)=\sqrt{1-x^2} 
$$

$$
\frac{d}{dx}\left(\sqrt{1-x^2}\frac{d}{dx}\right)u_{n}=-\frac{n^2}{\sqrt{1-x^2}}u_{n} 
$$

$$
\lambda_{n}=n^2,\quad w\left(x\right)=\frac{1}{\sqrt{1-x^2}}
$$

{{< /details >}}