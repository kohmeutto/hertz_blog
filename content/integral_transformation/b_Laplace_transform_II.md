+++
title = "(b) Laplace transform II"
weight = 4
+++

---

이 챕터에서는 단방향 라플라스 변환을 의미한다. 여기에 제시된 내용은 모두 암기한다.

---

### 1. 라플라스 변환의 중요 조건 - 수렴영역

**수렴 영역(ROC)** 은 라플라스 변환 정의 적분이 수렴하는 복소수 s의 집합을 의미한다. s 값이 ROC 안에 있으면 적분은 유한한 값으로 수렴하고, ROC 밖에 있으면 적분은 발산한다.

---

### 2. 중요변환

**example1)**

$$
\mathcal{L}\left\lbrace\delta\left(t\right)\right\rbrace\left(s\right)
$$

{{< details summary="sol" >}}
    
$$
F(s)=\int_0^{\infty}dt\left\lbrack\delta\left(t\right)e^{-st}\right\rbrack=1\cdot\int_0^{\infty}dt\left\lbrack\delta\left(t\right)\right\rbrack=1
$$

<hr>

{{< /details >}}

**example2)**

$$
\mathcal{L}\left\lbrace\cos at\cdot u\left(t\right)\right\rbrace\left(s\right)
$$

{{< details summary="sol" >}}
    
$$
F(s)=\int_0^{\infty}dt\left\lbrack\cos at\cdot e^{-st}\right\rbrack=\operatorname{Re}\left\lbrack\int_0^{\infty}dt\left\lbrack e^{iat}\cdot e^{-st}\right\rbrack\right\rbrack
$$
    
$$
=\operatorname{Re}\left\lbrack\int_0^{\infty}dt\left\lbrack e^{-\left(s-ia\right)t}\right\rbrack\right\rbrack=\frac{s}{s^2+a^2}
$$

<hr>

{{< /details >}}

**example3)**

$$
\mathcal{L}\left\lbrace\sin at\cdot u\left(t\right)\right\rbrace\left(s\right)
$$

{{< details summary="sol" >}}
    
$$
F(s)=\int_0^{\infty}dt\left\lbrack\sin at\cdot e^{-st}\right\rbrack=\operatorname{Im}\left\lbrack\int_0^{\infty}dt\left\lbrack e^{iat}\cdot e^{-st}\right\rbrack\right\rbrack
$$
    
$$
=\operatorname{Im}\left\lbrack\int_0^{\infty}dt\left\lbrack e^{-\left(s-ia\right)t}\right\rbrack\right\rbrack=\frac{a}{s^2+a^2}
$$

<hr>

{{< /details >}}

**example4)**

$$
\mathcal{L}\left\lbrace u\left(t\right)\right\rbrace\left(s\right)
$$

{{< details summary="sol" >}}
    
$$
F(s)=\int_0^{\infty}dt\left\lbrack e^{-st}\right\rbrack=\frac{1}{s}
$$
    
<hr>

{{< /details >}}

**example5)**

$$
\mathcal{L}\left\lbrace e^{at}u\left(t\right)\right\rbrace\left(s\right)
$$

{{< details summary="sol" >}}

$$
F(s)=\int_0^{\infty}dt\left\lbrack e^{at}e^{-st}\right\rbrack=\int_0^{\infty}dt\left\lbrack e^{-\left(s-a\right)t}\right\rbrack=\frac{1}{s-a}
$$

<hr>

{{< /details >}}

**example6)**

$$
\mathcal{L}\left\lbrace tu\left(t\right)\right\rbrace\left(s\right)
$$

{{< details summary="sol" >}}
    
$$
F(s)=\int_0^{\infty}dt\left\lbrack te^{-st}\right\rbrack=\frac{1}{s^2}
$$
    
<hr>

{{< /details >}}
    

**example7)**

$$
\mathcal{L}\left\lbrace t^{n}u\left(t\right)\right\rbrace\left(s\right)
$$

{{< details summary="sol" >}}
    
$$
F(s)=\int_0^{\infty}dt\left\lbrack t^{n}e^{-st}\right\rbrack=\frac{n!}{s^{n+1}}
$$

{{< /details >}}

---

### 3. Properties

**1) time scaling**

$$
\mathcal{L}\left\lbrace f\left(at\right)\right\rbrace\left(s\right)=\frac{1}{\left|a\right|}\mathcal{L}\left\lbrace f\left(at\right)\right\rbrace\left(\frac{s}{a}\right)
$$

{{< details summary="proof" >}}

$$
\mathcal{L}\left\lbrace f\left(at\right)\right\rbrace\left(s\right)=\int_0^{\infty}\frac{1}{a}d\tau\left\lbrack f\left(\tau\right)e^{-\frac{s}{a}\tau}\right\rbrack=\frac{1}{a}F\left(\frac{s}{a}\right)
$$

<hr>

{{< /details >}}

**2) time shifting**

$$
\mathcal{L}\left\lbrace f\left(t-t'\right)\right\rbrace\left(s\right)=e^{-st'}\left\lbrace f\left(t\right)\right\rbrace\left(s\right)
$$

{{< details summary="proof" >}}

$$
\mathcal{L}\left\lbrace f\left(t-t'\right)\right\rbrace\left(s\right)=\int_0^{\infty}dt\left\lbrack f\left(t-t'\right)e^{-st}\right\rbrack=\int_{-\infty}^{\infty}d\tau\left\lbrack f\left(\tau\right)e^{-s\left(\tau+t'\right)}\right\rbrack
$$
    
$$
=e^{-st'}F\left(\omega\right)
$$

<hr>

{{< /details >}}


**3) frequency shifting**

$$
\mathcal{L}\left\lbrace e^{at}f\left(t\right)\right\rbrace\left(s\right)=\mathcal{L}\left\lbrace f\left(t\right)\right\rbrace\left(s-a\right)
$$

{{< details summary="proof" >}}
    
$$
\mathcal{L}\left\lbrace e^{at}f\left(t\right)\right\rbrace\left(s\right)=\int_0^{\infty}dt\left\lbrack f\left(t\right)e^{-\left(s-a\right)t}\right\rbrack=F\left(s-a\right)
$$

<hr>

{{< /details >}}

**4) convolution**

$$
\mathcal{L}\left\lbrace h\left(t\right)\ast f\left(t\right)\right\rbrace\left(s\right)=H\left(s\right)F\left(s\right)
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

**5) differentiation**

$$
\mathcal{L}\left\lbrace\frac{d^{n}}{dt^{n}}f\left(t\right)\right\rbrace\left(s\right)=s^{n}F\left(s\right)-s^{n-1}f\left(0\right)-s^{n-2}f^{\left(1\right)}\left(0\right)-s^{n-3}f^{\left(2\right)}\left(0\right)-\cdots
$$

{{< details summary="proof" >}}

$$
\int^{\infty}_{0}dt\left[e^{-st}\frac{d^{n}}{dt^{n}}f\left(t\right)\right]
=\int^{\infty}_{0}dt\left[\frac{\partial}{\partial t}\left\lbrace e^{-st}\frac{\partial^{n-1}}{\partial t^{n-1}} f\left(t\right)\right\rbrace-\left(-s\right)e^{-st}\frac{\partial^{n-1}}{\partial t^{n-1}} f\left(t\right)\right]
$$

$$
=\left[ e^{-st}\frac{\partial^{n-1}}{\partial t^{n-1}} f\left(t\right)\right]^{\infty}_{0}
+s\int^{\infty}_{0}dt\left[e^{-st}\frac{\partial^{n-1}}{\partial t^{n-1}} f\left(t\right)\right]
$$

t가 무한대에서 수렴해야하므로, s의 실수값은 0보다 커야
한다. 

$$
=-f^{\left(n-1\right)}\left(0\right)
+s\left\lbrace-f^{\left(n-2\right)}\left(0\right)+s\int^{\infty}_{0}dt \left[e^{-st}\frac{\partial^{n-2}}{\partial t^{n-2}} f\left(t\right)\right]\right\rbrace
$$

따라서, 반복하면,

$$
\mathcal{L}\left\lbrace\frac{d^{n}}{dt^{n}}f\left(t\right)\right\rbrace\left(s\right)=s^{n}F\left(s\right)-s^{n-1}f\left(0\right)-s^{n-2}f^{\left(1\right)}\left(0\right)-s^{n-3}f^{\left(2\right)}\left(0\right)-\cdots
$$

<hr>

{{< /details >}}    

**6) integration**

$$
\mathcal{L}\left\lbrace\int_0^{t}dt'\left\lbrack f\left(t'\right)\right\rbrack\right\rbrace\left(s\right)=\mathcal{L}\left\lbrace u\left(t\right)\ast f\left(t\right)\right\rbrace\left(s\right)=\frac{1}{s}F\left(s\right)
$$

{{< details summary="proof" >}}

$$
\mathcal{L}\left\lbrace\int_0^{t}dt'\left\lbrack u\left(t-t'\right)f\left(t'\right)\right\rbrack\right\rbrace\left(s\right)=\mathcal{L}\left\lbrace u\left(t\right)\ast f\left(t\right)\right\rbrace\left(s\right)=\frac{1}{s}F\left(s\right)
$$

<hr>

{{< /details >}}    

**7) initial and final values**

$$
f\left(0\right)=\lim_{s\to\infty}s\mathcal{L}\left\lbrace f\left(t\right)\right\rbrace\left(s\right)
$$

$$
f\left(\infty\right)=\lim_{s\to0}s\mathcal{L}\left\lbrace f\left(t\right)\right\rbrace\left(s\right)
$$

{{< details summary="proof" >}}

$$
\mathcal{L}\left\lbrace \frac{d}{dt} f\left(t\right)\right\rbrace\left(s\right)=s\mathcal{L}\left\lbrace f\left(t\right)\right\rbrace\left(s\right)-f\left(0\right)
$$

$$
\int^{\infty}_{0}dt\left[e^{-st}f'\right(t\left)\right]=s\mathcal{L}\left\lbrace f\left(t\right)\right\rbrace\left(s\right)-f\left(0\right)
$$

<hr>

(1) 첫번째 식의 증명

$$
\lim_{s\to\infty}\int^{\infty}_{0}dt\left[e^{-st}f'\right(t\left)\right]=\lim_{s\to\infty}\left[s\mathcal{L}\left\lbrace f\left(t\right)\right\rbrace\left(s\right)-f\left(0\right)\right]
$$

만약, $f'(t)$ 가 $e^{-st}$의 감소보다 증가량이 크지 않다면, (에너지 보존 법칙으로 인해, 물리 시스템의 응답, 공학적인 신호 등의 대부분 이 조건을 만족하는 함수들임)

$$
0=\lim_{s\to\infty}\left[s\mathcal{L}\left\lbrace f\left(t\right)\right\rbrace\left(s\right)-f\left(0\right)\right]
$$

$$
f\left(0\right)=\lim_{s\to\infty}s\mathcal{L}\left\lbrace f\left(t\right)\right\rbrace\left(s\right)
$$

<hr>

(2) 두번째 식의 증명,

$$
\lim_{s\to 0}\int^{\infty}_{0}dt\left[e^{-st}f'\right(t\left)\right]=\lim_{s\to 0}\left[s\mathcal{L}\left\lbrace f\left(t\right)\right\rbrace\left(s\right)-f\left(0\right)\right]
$$

$$
f\left(\infty\right)-f\left(0\right)=\lim_{s\to 0}\left[s\mathcal{L}\left\lbrace f\left(t\right)\right\rbrace\left(s\right)-f\left(0\right)\right]
$$

$$
f\left(\infty\right)=\lim_{s\to0}s\mathcal{L}\left\lbrace f\left(t\right)\right\rbrace\left(s\right)
$$

{{< /details >}}    

---

### 4. Practice

연구실 구성원들에게만 허용된 자료 입니다. [연습문제](https://hertz2hnu.atlassian.net/wiki/spaces/AJpAH3tcG9Jk/pages/53608611/b+LTI+System)

---
