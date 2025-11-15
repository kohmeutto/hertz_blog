+++
title = "(b) Mellin transform II"
weight = 3
+++

---

### 1. 멜린 변환

$$
\langle s^M|f\rangle
=\int_0^{\infty}\frac{dx}{x}x^{s}f\left(t\right)
$$

---

### 2. linearity

적분연산자 자체가 선형연산자이다.

$$
\langle s^M|af+bg\rangle
=a\langle s^M|f\rangle+b\langle s^M|g\rangle
$$

---

### 3. Core LScI duality (핵심 쌍대성)

**(1) Scaling in x-domain (축척 변환)**

$$
\langle s^M|f(ax)\rangle
=\langle s^M|\hat{Z}_a|f\rangle
=a^{-s}\langle s^M|f\rangle
$$

{{< details summary="proof" >}}

$$
\langle s^M|\hat{Z}_a
=\int \frac{dx}{x} x^s\langle x^d|\hat{Z}_a
=\int \frac{dx}{x} x^s\langle (ax)^d|
=\int \frac{dk}{k} (k/a)^s\langle k^d| 
=a^{-s}\int \frac{dk}{k} k^s \langle k^d| 
$$

<hr>

{{< /details >}}

**(2) Power Scaling in x-domain (멱함수 곱)**

$$
\langle s^M|x^af(x)\rangle
=\langle s^M|\hat{x}^a|f\rangle
=\langle (s+a)^M|f\rangle
$$

{{< details summary="proof" >}}

$$
\langle s^M|\hat{x}^a
=\int \frac{dx}{x} x^s\langle x^d|\hat{x}^a
=\int \frac{dx}{x} x^s\langle x^{a^\ast}x^d|
=\int \frac{dx}{x} x^{s+a}\langle x^d|
$$

{{< /details >}}

---

### 4. Mellin convolution (멜린 컨볼루션)

$$
\langle s^M|f\circledast g\rangle
=\langle s^M|f\rangle\langle s^M|g\rangle
$$

{{< details summary="proof" >}}

$$
\langle s^M|f\circledast g\rangle
=\int \frac{dx}{x} x^s\langle x^d|f\circledast g\rangle
=\int \frac{dx}{x} x^s\int \frac{dx'}{x'}f(x/x')g(x')
$$

$$
=\int \frac{dk}{k} (kx')^s\int \frac{dx'}{x'}f(k)g(x')
=\int \frac{dx'}{x'} x'^sg(x')\int \frac{dk}{k}k^sf(k)
$$

$$
=\langle s^M|f\rangle\langle s^M|g\rangle
$$

{{< /details >}}

---

### 5. Operator Duality

**(1)  Scale Derivative $\leftrightarrow$ s-Multiply**

$$
\left\langle s^M\middle|\left(x\frac{d}{dx}\right)^n f(x)\right\rangle
=\left\langle s^M\middle|\hat{\Theta}^n\middle|f\right\rangle
=(-s)^n\left\langle s^M\middle|f\right\rangle
$$

{{< details summary="proof" >}}
    
$$
\left\langle s^M\middle|\left(x\frac{d}{dx}\right)^1 f(x)\right\rangle
=\int \frac{dx}{x}x^s x\frac{d}{dx} f(x)
=\int dx \left\{x^{s} \frac{d}{dx} f(x)\right\}
$$

$$
=\int dx \left\{ \frac{d}{dx}x^{s} f(x)\right\}-\int dx \left\{ sx^{s-1} f(x)\right\}
$$

$$
=[x^{s} f(x)]^{\infty}_0-\int dx \left\{ sx^{s-1}f(x)\right\}
$$

무한대에서 0으로 수렴한다면,

$$
=-s\left\langle s^M\middle|f\right\rangle
$$

<hr>

{{< /details >}}

$$
\left\langle s^M\middle|\frac{d^n}{dx^n}f(x)\right\rangle
=(-1)^n(s-n)_n\left\langle (s-n)^M\middle|f\right\rangle
$$

{{< details summary="proof" >}}
    
$$
\left\langle s^M\middle|x\frac{d}{dx}f(x)\right\rangle
=\left\langle (s+1)^M\middle|\frac{d}{dx} f(x)\right\rangle
=-s\left\langle s^M\middle|f\right\rangle
$$

$s\to s-1$ 로 놓으면,

$$
\left\langle s^M\middle|\frac{d}{dx} f(x)\right\rangle
=-(s-1)\left\langle (s-1)^M\middle|f\right\rangle
$$

연속적으로,

$$
\left\langle s^M\middle|\frac{d}{dx} f'(x)\right\rangle
=-(s-1)\left\langle (s-1)^M\middle|f'\right\rangle
=(s-2)(s-1)\left\langle (s-2)^M\middle|f'\right\rangle
$$

<hr>

{{< /details >}}

$$
\left\langle s^M\middle|\frac{d^n}{dx^n}\{x^nf(x)\}\right\rangle
=(-1)^n (s-n)_n\left\langle s^M\middle|f\right\rangle
$$

{{< details summary="proof" >}}
    
$$
\left\langle s^M\middle|\frac{d^n}{dx^n}\{x^nf(x)\}\right\rangle
=(-1)^n (s-n)_n\left\langle (s-n)^M\middle|x^nf(x)\right\rangle
$$

$$
=(-1)^n (s-n)_n\left\langle s^M\middle|f\right\rangle
$$

<hr>

{{< /details >}}

$$
\left\langle s^M\middle|x^n\frac{d^n}{dx^n}f(x)\right\rangle
=(-1)^n (s)_n\left\langle s^M\middle|f\right\rangle
$$

{{< details summary="proof" >}}
    
$$
\left\langle s^M\middle|x^n\frac{d^n}{dx^n}f(x)\right\rangle
=\left\langle(s+n)^M\middle|\frac{d^n}{dx^n}f(x)\right\rangle
=\left\langle(s+n)^M\middle|\frac{d^n}{dx^n}f(x)\right\rangle
$$

$$
=(-1)^n (s)_n\left\langle s^M\middle|f\right\rangle
$$

<hr>

{{< /details >}}

**(2) Log-Multiply $\leftrightarrow$ s-Derivative**

$$
\left\langle s^M\middle|(\ln x)^n f(x)\right\rangle
=\left\langle s^M\middle|(\hat{L})^n\middle|f\right\rangle
=\left(\frac{d}{ds}\right)^n\left\langle s^M\middle|f\right\rangle
$$

{{< details summary="proof" >}}

$$
\frac{d}{ds}x^{s-1}
=\frac{d}{ds}e^{(s-1)\ln x}
=e^{(s-1)\ln x}\ln x
=x^{s-1}\ln x
$$

따라서,

$$
\left\langle s^M\middle|\ln x \cdot f(x)\right\rangle
=\int dx \{x^{s-1} \ln x\cdot f(x)\}
=\int dx f(x)\frac{d}{ds}x^{s-1}
$$

$$
=\frac{d}{ds}\int \frac{dx}{x} f(x)x^s
$$

$$
=\frac{d}{ds}\left\langle s^M\middle|f\right\rangle
$$

{{< /details >}}

---

### 7. Integration Properties (적분 속성)

**(1) Scale Integration**

$$
\left\langle s^M\middle| \int_0^x \frac{dx'}{x'}f(x') \right\rangle
=\left\langle s^M\middle|\hat{\Theta}^{-1}\middle|f\right\rangle
=(-s)^{-1}\left\langle s^M\middle|f\right\rangle
$$

{{< details summary="proof" >}}

$$
g(x)=\int_0^x \frac{dx'}{x'}f(x')
$$

$\left\langle s^M\middle| g \right\rangle$ 를 구하는 것이 목적이다.

$$
\langle s^M|\hat{\Theta}g\rangle
=-s\langle s^M|g\rangle
$$

$$
\langle s^M|\hat{\Theta}g\rangle
=\left\langle s^M\middle|x\frac{d}{dx}\int^x_0 \frac{dx'}{x'}f(x')\right\rangle
=\langle s^M|f\rangle
$$

위 두개의 식을 비교하면,

$$
\langle s^M|g\rangle
=(-s)^{-1}\left\langle s^M\middle|f\right\rangle
$$

<hr>

{{< /details >}}

$$
\left\langle s^M\middle| \int_0^x dx' f(x') \right\rangle
=(-s)^{-1}\left\langle (s+1)^M\middle|f(x) \right\rangle
$$

{{< details summary="proof" >}}

$$
\left\langle s^M\middle| \int_0^x dx' f(x') \right\rangle
=\left\langle s^M\middle| \int_0^x \frac{dx'}{x'} x'f(x') \right\rangle
=(-s)^{-1}\left\langle s^M\middle|xf(x) \right\rangle
$$

$$
=(-s)^{-1}\left\langle (s+1)^M\middle|f(x) \right\rangle
$$

<hr>

{{< /details >}}

**(2) Log-Integration**

$$
\left\langle s^M\middle|\frac{1}{\ln x}f(x)\right\rangle
=\left\langle s^M\middle|\hat{L}^{-1}\middle|f\right\rangle
=-\int_{s}^{\infty}ds'\left\langle s'^M\middle|f\right\rangle
$$

{{< details summary="proof" >}}

$$
\left\langle s^M\middle|\ln x\cdot\frac{1}{\ln x}f(x)\right\rangle
=\frac{d}{ds}\left\langle s^M\middle|\frac{1}{\ln x}f(x)\right\rangle
=\int_{s}^{\infty}ds'\left\langle s'^M\middle|f\right\rangle
$$

$$
\int^{s}_{\infty} ds'\left\langle s'^M\middle|f(x)\right\rangle
=\left\langle s^M\middle|\frac{1}{\ln x}f(x)\right\rangle
$$

{{< /details >}}

