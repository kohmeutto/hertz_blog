+++
title = "(a) Mellin transform II"
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

LSI의 (시간 이동 $\leftrightarrow$ 주파수 곱셈)과 (주파수 이동 $\leftrightarrow$ 시간 곱셈)은 LScI에서 다음과 같이 완벽한 대칭을 이룬다.

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

LSI의 대수 구조 $(\hat{D}_t = \frac{d}{dt}, \hat{t})$가 LScI의 대수 구조 $(\hat{\Theta} = x\frac{d}{dx}, \hat{L} = \ln x)$와 완벽한 거울 대칭을 이룬다.

**(1)  Scale Derivative**

$$
\left\langle s^M\middle|\left(x\frac{d}{dx}\right)^n f(x)\right\rangle
=\left\langle s^M\middle|(\hat{\Theta})^n\middle|f\right\rangle
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

**(2) Log-Multiply $\leftrightarrow$ s-Derivative(LSI: $\hat{t} \to -\frac{d}{ds}$)**

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

(1) Scale Integration(LSI: $\hat{D}_t^{-1} \to s^{-1}$)

$$
\left\langle s^M\middle| \int_0^x \frac{dx'}{x'}f(x') \right\rangle
=\left\langle s^M\middle|\hat{\Theta}^{-1}\middle|f\right\rangle
=(-s)^{-1}\left\langle s^M\middle|f\right\rangle
$$

(2) Log-Integration(LSI: $\hat{t}^{-1} \to \int_s^\infty$)

$$
\left\langle s^M\middle|\frac{f(x)}{\ln x}\right\rangle
=\left\langle s^M\middle|\hat{L}^{-1}\middle|f\right\rangle
=\int_{s}^{\infty}ds'\left\langle s'^M\middle|f\right\rangle
$$

---

### 8. Boundary Value Theorems (경계값 정리)

LSI의 $t \to 0$과 $t \to \infty$는 LScI의 $x \to 0$과 $x \to \infty$에 완벽하게 대응된다.

(1) Initial Value Theorem (IVT, $x \to 0$)

$$
f(0)
=\lim_{x\to 0} \langle x|f \rangle
=\lim_{s\to \infty} s \langle s^M|f \rangle
$$

(2) Final Value Theorem (FVT, $x \to \infty$)

$$
f(\infty)
=\lim_{x\to \infty} \langle x|f \rangle
=\lim_{s\to 0} s \langle s^M|f \rangle
$$

(단, $s\langle s^M|f\rangle$의 모든 극점이 $s=0$을 제외하고 좌반평면(LHP)에 존재해야 함)