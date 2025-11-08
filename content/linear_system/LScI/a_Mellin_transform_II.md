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

**(1)  Scale Derivative $\leftrightarrow$ s-Multiply
(LSI: $\hat{D}_t \to s$)**

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

{{< /details >}}


---

### 5. Inverse Operator Duality (역변환 쌍대성)



**(6) convolution**

$$
\langle s^L|(h\cdot u)\ast (f\cdot u)\rangle
=\langle s^L|h\cdot u\rangle\langle s^L|f\cdot u\rangle
$$

$$
\langle s^L|h\ast f\rangle
=\langle s^L|h\rangle\langle s^L|f\rangle
$$

{{< details summary="proof" >}}

$$
\int^{\infty}_{0}dt\left[e^{-st}\int^{\infty}_{0}d\tau\left[h\right(t-\tau\left)f\left(\tau\right)\right]\right]
$$

$$
=\int^{\infty}_{0}dt\left[e^{-s\left(t-\tau+\tau\right)}\int^{\infty}_{0}d\tau\left[h\right(t-\tau\left)f\left(\tau\right)\right]\right]
$$

$$
=\int^{\infty}_{0}dt\left[\int^{\infty}_{0}d\tau\left[h\left(t-\tau\right)e^{-s\left(t-\tau\right)}f\left(\tau\right)e^{-s\tau}\right]\right]
$$

$$
=\int^{\infty}_{0}d\tau\left[ f\left(\tau\right)e^{-s\tau}\int^{\infty}_{0}dt\left[h\left(t-\tau\right)e^{-s\left(t-\tau\right)}\right]\right]
$$

$$
=\int^{\infty}_{0}d\tau\left[ f\left(\tau\right)e^{-s\tau}H\left(s\right)\right]
$$

$$
=H\left(s\right)\int^{\infty}_{0}d\tau\left[ f\left(\tau\right)e^{-s\tau}\right]
$$

$$
=H\left(s\right)F\left(s\right)
$$

<hr>

{{< /details >}}

**(7) 시간영역미분, evolution, dynamics - 아주 중요함**

- 단방향 라플라스 변환

$$
\left\langle s^L\middle|u(t)\frac{d^n}{dt^n}f(t)\right\rangle
=s^{n}\langle s^L|f\cdot u\rangle-s^{n-1}f\left(0\right)-s^{n-2}f^{\left(1\right)}\left(0\right)-s^{n-3}f^{\left(2\right)}\left(0\right)-\cdots
$$

$$
\left\langle s^L\middle|f'\cdot u\right\rangle
=s\langle s^L|f\cdot u\rangle-f(0)
$$

$$
\left\langle s^L\middle|f''\cdot u\right\rangle
=s\langle s^L|f\cdot u\rangle-sf(0)-f'(0)
$$


함수 $f(t)$의 "진화(evolution)" $f^{(n)}$ 를 $t=0$에서 "자른 $u(t)$ " 신호의 변환이다. **초기값 문제(Initial Value Problem)** 를 푸는 데 특화된 공식이다.

{{< details summary="proof" >}}

$$
\int^{\infty}_{0}dt\left[e^{-st}\frac{d^{n}}{dt^{n}}f\left(t\right)\right]
=\int^{\infty}_{0}dt\left[\frac{\partial}{\partial t}\left\lbrace e^{-st}\frac{\partial^{n-1}}{\partial t^{n-1}} f\left(t\right)\right\rbrace-\left(-s\right)e^{-st}\frac{\partial^{n-1}}{\partial t^{n-1}} f\left(t\right)\right]
$$

$$
=\left[ e^{-st}\frac{\partial^{n-1}}{\partial t^{n-1}} f\left(t\right)\right]^{\infty}_{0}
+s\int^{\infty}_{0}dt\left[e^{-st}\frac{\partial^{n-1}}{\partial t^{n-1}} f\left(t\right)\right]
$$

$∣f^{(n−1)}(t)∣≤Me^{αt}$, 이면 $\operatorname{Re}\lbrace s\rbrace>α$ 이어야 수렴한다. 

$$
=-f^{\left(n-1\right)}\left(0\right)
+s\left\lbrace-f^{\left(n-2\right)}\left(0\right)+s\int^{\infty}_{0}dt \left[e^{-st}\frac{\partial^{n-2}}{\partial t^{n-2}} f\left(t\right)\right]\right\rbrace
$$

따라서, 반복하면,

$$
\mathcal{L}\left\lbrace\frac{d^{n}}{dt^{n}}f\left(t\right)u(t)\right\rbrace\left(s\right)=s^{n}F\left(s\right)-s^{n-1}f\left(0\right)-s^{n-2}f^{\left(1\right)}\left(0\right)-s^{n-3}f^{\left(2\right)}\left(0\right)-\cdots
$$

<hr>

{{< /details >}}

- 양방향 라플라스 변환 - causual
  
$$
\left\langle s^L\middle|\frac{d^n}{dt^n}\{f(t)u(t)\}\right\rangle
=\left\langle s^L|\hat{D}^n|f\cdot u\right\rangle
=s^{n}\langle s^L|f\cdot u\rangle
$$

 $f(t)$를 $u(t)$로 먼저 곱해서 **"인과 함수(causal function)" $g(t) = f(t)u(t)$** 를 만들고, 그 전체를 미분한 신호의 변환이다.

 {{< details summary="proof" >}}

$$
\langle s^L|\hat{D}|f\cdot u \rangle
=\langle s^L|f'(t)u(t)+f(t)\delta(t)\rangle
=\langle s^L| \underbrace{f'(t)u(t)}_{\text{진화 성분}}+\underbrace{f(0)\delta(t)}_{\text{초기 성분}}\rangle
$$

(1) 진화성분

$$
\langle s^L|f'(t)u(t)\rangle=\int_0^{\infty} dt e^{-st}\frac{d}{dt}f(t)
=\int_0^{\infty} dt\left[\frac{\partial}{\partial t} e^{-st}f(t)+sf(t)e^{-st}\right]
$$

$$
=-f(0)+s\langle s^L|f\cdot u\rangle
$$

(2) 초기성분

$$
\langle s^L|f(0)\delta(t)\rangle
=f(0)\langle s^L|\delta(t)\rangle
=f(0)
$$

진화성분과 초기성분을 합치면,

$$
s\langle s^L|f\cdot u\rangle
$$

<hr>

{{< /details >}}    

- 양방향 라플라스 변환 - 일반

$$
\left\langle s^L\middle|\frac{d^n}{dt^n}f(t)\right\rangle
=\langle s^L|\hat{D}^n|f\rangle
=s^{n}\langle s^L|f\rangle
$$

라플라스 변환이 수렴(converge)한다는 가정 자체가 $t=\pm\infty$에서 $f(t)e^{-st}$ 항이 0이 된다는 것을 의미하므로, 경계항(초기값)이 아예 발생하지 않는다. $t=0$이라는 특정 시작점을 가정하지 않고, 시스템의 순수한 "동특성(dynamics)"($\hat{D}^n \to s^n$) 그 자체를 분석할 때 사용한다.

**(8) 시간영역적분**

이것은 적분연산자가 convolution으로 귀결됨을 보여주는 예이다.

$$
\left\langle s^L\middle|\int_0^{t}dt'\left\lbrack f\left(t'\right)u(t')\right\rbrack\right\rangle
=\left\langle s^L\middle|\hat{D}^{-1}|f\right\rangle
=\langle s^L|u\ast f\rangle
=\langle s^L|u\rangle\langle s^L|f\rangle
=\frac{1}{s}\langle s^L|f\rangle
$$

$$
\left\langle s^L\middle|\int_{-\infty}^{t}dt'\left\lbrack f\left(t'\right)\right\rbrack\right\rangle
=\left\langle s^L\middle|\hat{D}^{-1}|f\right\rangle
=\langle s^L|u\ast f\rangle
=\langle s^L|u\rangle\langle s^L|f\rangle
=\frac{1}{s}\langle s^L|f\rangle
$$

**(9) s-영역미분**

$$
\langle s^L|t^n\cdot f\cdot u\rangle
=\langle s^L|\hat{t}^n|f\cdot u\rangle
=(-1)^n\frac{d^n}{ds^n}\langle s^L|f\cdot u\rangle
$$

$$
\langle s^L|t^n\cdot f\rangle
=\langle s^L|\hat{t}^n|f\rangle=(-1)^n\frac{d^n}{ds^n}\langle s^L|f\rangle
$$

$$
\langle s^L|t\cdot u\rangle
=\langle s^L|\hat{t}|u\rangle
=(-1)^1\frac{d}{ds}\langle s^L|u\rangle
=\frac{1}{s^2}
$$

$$
\langle s^L|t^n\cdot u\rangle
=\langle s^L|\hat{t}^n|u\rangle
=(-1)^n\frac{d^n}{ds^n}\langle s^L|u\rangle
=\frac{n!}{s^{n+1}}
$$

{{< details summary="proof" >}}

$$
\langle s^L|t^n\cdot f\cdot u\rangle
=\int^{\infty}_{-\infty}dt\left[e^{-st}t^n f\left(t\right)\right]
$$

$$
=\int^{\infty}_{-\infty}dt\left[f\left(t\right)\left(\frac{1}{-1}\right)^n\frac{\partial^n}{\partial s^n}e^{-st}\right]
=(-1)^n\frac{\partial^n}{\partial s^n}\int^{\infty}_{-\infty}dt\left[e^{-st}f\left(t\right)\right]
$$

$$
=(-1)^n\frac{d^n}{ds^n}\mathcal{L}\left\lbrace f\left(t\right)\right\rbrace\left(\omega\right)
$$

<hr>

{{< /details >}}

**(10) s-영역 적분**

$$
\left\langle s^L\middle|t^{-1}\cdot f\cdot u \right\rangle
=\left\langle s^L\middle|\hat{t}^{-1}|f\cdot u \right\rangle
=\int^{\infty}_{s} ds'\left\langle s'^L\middle|f\cdot u \right\rangle
$$

$$
\left\langle s^L\middle|t^{-1}\cdot f\ \right\rangle
=\left\langle s^L|\hat{t}^{-1}|f \right\rangle
=\int^{\infty}_{s} ds'\left\langle s'^L|f\right\rangle
$$

**(11) initial value**

$$
f\left(0\right)
=\lim_{s\to\infty}\langle s|\hat{D}|f\cdot u \rangle
=\lim_{s\to\infty}s \langle s|f\cdot u \rangle
$$

{{< details summary="proof" >}}

$$
\langle s^L|\hat{D}|f\cdot u \rangle
=\langle s^L|f'(t)u(t)+f(t)\delta(t)\rangle
=\langle s^L| \underbrace{f'(t)u(t)}_{\text{진화 성분}}+\underbrace{f(0)\delta(t)}_{\text{초기 성분}}\rangle
=\langle s^L|f'\cdot u \rangle+f\left(0\right)
$$

$$
\lim_{s\to\infty}\langle s^L|\hat{D}|f\cdot u \rangle
=\lim_{s\to\infty}s\langle s^L|f'\cdot u \rangle+\lim_{s\to\infty}f\left(0\right)
$$

만약, $f'(t)$ 가 $e^{-st}$의 감소보다 증가량이 크지 않다면, (에너지 보존 법칙으로 인해, 물리 시스템의 응답, 공학적인 신호 등의 대부분 이 조건을 만족하는 함수들임)

$$
\lim_{s\to\infty}s\langle s^L|f'\cdot u \rangle=0
$$

따라서,

$$
f\left(0\right)
=\lim_{s\to\infty}\langle s|\hat{D}|f\cdot u \rangle
=\lim_{s\to\infty}s \langle s|f\cdot u \rangle
$$

<hr>

{{< /details >}}    

**(12) final value**

- 단방향 라플라스 변환

$$
f\left(\infty\right)
=\lim_{s\to 0}\langle s^L|\hat{D}|f\cdot u \rangle
=\lim_{s\to 0}s \langle s^L|f\cdot u \rangle
$$

{{< details summary="proof" >}}

$$
\langle s^L|f'\cdot u\rangle=s\langle s^L|f\cdot u\rangle-f(0)
$$

$$
\lim_{s\to0}\langle s^L|f'\cdot u\rangle+\lim_{s\to0}f(0)=\lim_{s\to0}s\langle s^L|f\cdot u\rangle
$$

$$
\lim_{s\to0}\langle s^L|f'\cdot u\rangle
=\int_0^{\infty}dtf'(t)=f(\infty)-f(0)
$$

따라서,

$$
f\left(\infty\right)
=\lim_{s\to 0}\langle s^L|\hat{D}|f\cdot u \rangle
=\lim_{s\to 0}s \langle s^L|f\cdot u \rangle
$$

<hr>

{{< /details >}}

- 양방향 라플라스 변환

$$
\text{Causal: }
f\left(\infty\right)
=\lim_{s\to0}\langle s^L|\hat{D}_t|f\rangle
=\lim_{s\to 0}s \langle s^L|f \rangle
$$

$$
\text{Anti-causal: }
f\left(-\infty\right)
=-\lim_{s\to0}\langle s^L|\hat{D}_t|f\rangle
=-\lim_{s\to 0}s \langle s^L|f\rangle
$$

