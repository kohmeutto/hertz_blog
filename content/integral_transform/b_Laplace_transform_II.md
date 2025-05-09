+++
title = "(b) Laplace transform II"
weight = 4
+++

---

양방향 라플라스 변환은 사용 빈도가 낮으나, 푸리에 변환과의 관계를 이해하고 표준 푸리에 역변환이 라플라스 변환의 틀 안에서 어떻게 설명되는지 파악하는 데 유용하다.

---

### 1. 라플라스 변환

$$
\mathcal{L}\left\lbrace f\left(t\right)u(t)\right\rbrace\left(s\right)
=\langle s|f\cdot u\rangle
=\int_0^{\infty}dt\left[e^{-st}f\left(t\right)u(t)\right\rbrack
$$

$$
\mathcal{L}\left\lbrace f\left(t\right)\right\rbrace\left(s\right)
=\langle s|f\rangle
=\int_{-\infty}^{\infty}dt\left[e^{-st}f\left(t\right)\right\rbrack
$$

Region of Convergence(ROC) 는 라플라스 변환이 존재할 수 있는 s의 수렴영역 이다.

아래 계산을 통해 **라플라스 변환의 극점과 ROC의 관계** 를 살펴보자.

---

### 2. 중요변환

**1-1) 디렉 델타 함수**

$$
\mathcal{L}\left\lbrace\delta\left(t\right)\right\rbrace\left(s\right)
=\langle s|\delta\rangle
$$

{{< details summary="sol" >}}
    
$$
F(s)=\int_{-\infty}^{\infty}dt\left\lbrack\delta\left(t\right)e^{-st}\right\rbrack=1\cdot\int_{-\infty}^{\infty}dt\left\lbrack\delta\left(t\right)\right\rbrack=1, \quad
\text{ROC: 모든 } s
$$

<hr>

{{< /details >}}

**1-2) 디렉 델타 함수**

$$
\mathcal{L}\left\lbrace\delta\left(t\right)u(t)\right\rbrace\left(s\right)
=\langle s|\delta u\rangle
$$

{{< details summary="sol" >}}
    
$$
F(s)=\int_{0-}^{\infty}dt\left\lbrack\delta\left(t\right)e^{-st}\right\rbrack
=1\cdot\int_{0-}^{\infty}dt\left\lbrack\delta\left(t\right)\right\rbrack=1, \quad
\text{ROC: 모든 } s
$$

<hr>

{{< /details >}}

**2-1) 단위 계단 함수**

$$
\mathcal{L}\left\lbrace u\left(t\right)\right\rbrace\left(s\right)
=\langle s|u\rangle
$$

{{< details summary="sol" >}}
    
$$
F(s)=\int_0^{\infty}dt\left\lbrack e^{-st}\right\rbrack=\frac{1}{s},\quad
\text{ROC: } \operatorname{Re}\lbrace s \rbrace>0
$$

<br>

극점은 0에서 존재한다. 이 때, ROC는 우측영역에서 형성된다.

<hr>

{{< /details >}}

**2-2) 단위 계단 함수**

$$
\mathcal{L}\left\lbrace u\left(-t\right)\right\rbrace\left(s\right)
=\langle s|u(-t)\rangle
$$

{{< details summary="sol" >}}
    
$$
F(s)=\int_{-\infty}^{0}dt\left\lbrack e^{-st}\right\rbrack=-\frac{1}{s},\quad
\text{ROC: } \operatorname{Re}\lbrace s \rbrace < 0
$$

<br>

극점은 0에서 존재한다. 이 때, ROC는 왼쪽영역에서 형성된다.

<hr>

{{< /details >}}

**2-3) 상수 함수**

$$
\mathcal{L}\left\lbrace 1\right\rbrace\left(s\right)
=\langle s|1\rangle
$$

{{< details summary="sol" >}}
    
적분은 발산한다. 라플라스 변환은 존재하지 않는다.

<hr>

{{< /details >}}

**3-1) cosine 함수**

$$
\mathcal{L}\left\lbrace\cos at\cdot u\left(t\right)\right\rbrace\left(s\right)
=\langle s|\cos at\cdot u(t)\rangle
$$

{{< details summary="sol" >}}
    
$$
F(s)=\int_0^{\infty}dt\left\lbrack\cos at\cdot e^{-st}\right\rbrack=\operatorname{Re}\left\lbrace\int_0^{\infty}dt\left\lbrack e^{iat}\cdot e^{-st}\right\rbrack\right\rbrace
$$
    
$$
=\operatorname{Re}\left\lbrace\int_0^{\infty}dt\left\lbrack e^{-\left(s-ia\right)t}\right\rbrack\right\rbrace=\frac{s}{s^2+a^2},\quad
\text{ROC: } \operatorname{Re}\lbrace s \rbrace>0
$$

극점은 $\pm ia$ 이다. 이 때, ROC 는 우측영역에서 형성된다.  

<hr>

{{< /details >}}

**3-2) cosine 함수**

$$
\mathcal{L}\left\lbrace\cos at\cdot u\left(-t\right)\right\rbrace\left(s\right)
=\langle s|\cos at\cdot u(-t)\rangle
$$

{{< details summary="sol" >}}
    
$$
F(s)=\int_{-\infty}^0 dt\left\lbrack\cos at\cdot e^{-st}\right\rbrack
=\operatorname{Re}\left\lbrace\int_{-\infty}^0 dt\left\lbrack e^{iat}\cdot e^{-st}\right\rbrack\right\rbrace
$$
    
$$
=\operatorname{Re}\left\lbrace\int_{-\infty}^0 dt\left\lbrack e^{-\left(s-ia\right)t}\right\rbrack\right\rbrace
=-\frac{s}{s^2+a^2},\quad
\text{ROC: } \operatorname{Re}\lbrace s \rbrace<0
$$

극점은 $\pm ia$ 이다. 이 때, ROC 는 좌측영역에서 형성된다.

<hr>

{{< /details >}}

**3-3) cosine 함수**

$$
\mathcal{L}\left\lbrace\cos at\right\rbrace\left(s\right)
=\langle s|\cos at\rangle
$$

{{< details summary="sol" >}}
    
위의 cosine 예에서 겹치는 ROC 영역이 없으므로, 라플라스 변환은 존재하지 않는다. 또한 직관적으로보면, 적분은 발산한다.

<hr>

{{< /details >}}

**4-1) sine 함수**

$$
\mathcal{L}\left\lbrace\sin at\cdot u\left(t\right)\right\rbrace\left(s\right)
=\langle s|\sin at\cdot u(t)\rangle
$$

{{< details summary="sol" >}}
    
$$
F(s)=\int_0^{\infty}dt\left\lbrack\sin at\cdot e^{-st}\right\rbrack=\operatorname{Im}\left\lbrack\int_0^{\infty}dt\left\lbrace e^{iat}\cdot e^{-st}\right\rbrack\right\rbrace
$$
    
$$
=\operatorname{Im}\left\lbrace\int_0^{\infty}dt\left\lbrack e^{-\left(s-ia\right)t}\right\rbrack\right\rbrace=\frac{a}{s^2+a^2},\quad
\text{ROC: } \operatorname{Re}\lbrace s \rbrace>0
$$

극점은 $\pm ia$ 이다. 이 때, ROC 는 우측영역에서 형성된다.  

<hr>

{{< /details >}}

**4-2) sine 함수**

$$
\mathcal{L}\left\lbrace\sin at\cdot u\left(-t\right)\right\rbrace\left(s\right)
=\langle s|\sin at\cdot u(-t)\rangle
$$

{{< details summary="sol" >}}
    
$$
F(s)=\int_{-\infty}^{0}dt\left\lbrack\sin at\cdot e^{-st}\right\rbrack=\operatorname{Im}\left\lbrack\int_{-\infty}^{0}dt\left\lbrace e^{iat}\cdot e^{-st}\right\rbrack\right\rbrace
$$
    
$$
=\operatorname{Im}\left\lbrace\int_{-\infty}^{0}dt\left\lbrack e^{-\left(s-ia\right)t}\right\rbrack\right\rbrace=-\frac{a}{s^2+a^2},\quad
\text{ROC: } \operatorname{Re}\lbrace s \rbrace<0
$$

극점은 $\pm ia$ 이다. 이 때, ROC 는 좌측영역에서 형성된다.  

<hr>

{{< /details >}}

**4-3) sine 함수**

$$
\mathcal{L}\left\lbrace\sin at\right\rbrace\left(s\right)
=\langle s|\sin at\rangle
$$

{{< details summary="sol" >}}
    
겹치는 ROC 영역이 없으므로, 라플라스 변환값이 존재하지 않는다. 또한 직관적으로보면, 적분은 발산한다.

<hr>

{{< /details >}}

**5-1) cosh 함수**

$$
\mathcal{L}\left\lbrace\cosh at\cdot u\left(t\right)\right\rbrace\left(s\right)
=\langle s|\cosh at\cdot u(t)\rangle
$$

{{< details summary="sol" >}}
    
$$
F(s)=\int_0^{\infty}dt\left\lbrack e^{-st}\cosh at\right\rbrack
=\int_0^{\infty}dt\left\lbrack e^{-st}\cdot\frac{e^{+at}+e^{-at}}{2}\right\rbrack
$$
    
$$
=\frac{1}{2}\int_0^{\infty}dt\left\lbrack e^{-(s-a)t}+e^{-(s+a)t} \right\rbrack
=\frac{s}{s^2-a^2},\quad
\text{ROC: } \operatorname{Re}\lbrace s \rbrace>|\operatorname{Re}\lbrace a\rbrace|
$$

극점은 $\pm a$ 이다. 이 때, ROC 는 $|\operatorname{Re}\lbrace a\rbrace|$ 보다 큰 우측영역에서 형성된다. 

<hr>

{{< /details >}}

**5-2) cosh 함수**

$$
\mathcal{L}\left\lbrace\cosh at\cdot u\left(-t\right)\right\rbrace\left(s\right)
=\langle s|\cosh at\cdot u(-t)\rangle
$$

{{< details summary="sol" >}}
    
$$
F(s)=\int_{-\infty}^{0}dt\left\lbrack e^{-st}\cosh at\right\rbrack
=\int_{-\infty}^{0}dt\left\lbrack e^{-st}\cdot\frac{e^{+at}+e^{-at}}{2}\right\rbrack
$$
    
$$
=\frac{1}{2}\int_{-\infty}^{0}dt\left\lbrack e^{-(s-a)t}+e^{-(s+a)t} \right\rbrack
=-\frac{s}{s^2-a^2},\quad
\text{ROC: } \operatorname{Re}\lbrace s \rbrace<-|\operatorname{Re}\lbrace a\rbrace|
$$

극점은 $\pm a$ 이다. 이 때, ROC 는 $-|\operatorname{Re}\lbrace a\rbrace|$ 보다 작은 좌측영역에서 형성된다. 

<hr>

{{< /details >}}

**5-3) cosh 함수**

$$
\mathcal{L}\left\lbrace\cosh at\right\rbrace\left(s\right)
=\langle s|\cosh at\rangle
$$

{{< details summary="sol" >}}
    
겹치는 ROC 영역이 존재하지 않으므로, 라플라스 변환은 존재하지 않는다. 또한 직관적으로보면, 적분은 발산한다.

<hr>

{{< /details >}}

**6-1) sinh 함수**

$$
\mathcal{L}\left\lbrace\sinh at\cdot u\left(t\right)\right\rbrace\left(s\right)
=\langle s|\sinh at\cdot u(t)\rangle
$$

{{< details summary="sol" >}}
    
$$
F(s)=\int_0^{\infty}dt\left\lbrack e^{-st}\sinh at\right\rbrack
=\int_0^{\infty}dt\left\lbrack e^{-st}\cdot\frac{e^{+at}-e^{-at}}{2}\right\rbrack
$$
    
$$
=\frac{1}{2}\int_0^{\infty}dt\left\lbrack e^{-(s-a)t}-e^{-(s+a)t} \right\rbrack
=\frac{a}{s^2-a^2},\quad
\text{ROC: } \operatorname{Re}\lbrace s \rbrace>|\operatorname{Re}\lbrace a\rbrace|
$$

극점은 $\pm a$ 이다. 이 때, ROC 는 $|\operatorname{Re}\lbrace a\rbrace|$ 보다 큰 우측영역에서 형성된다.  

{{< /details >}}

**6-2) sinh 함수**

$$
\mathcal{L}\left\lbrace\sinh at\cdot u\left(-t\right)\right\rbrace\left(s\right)
=\langle s|\sinh at\cdot u(-t)\rangle
$$

{{< details summary="sol" >}}
    
$$
F(s)=\int_{-\infty}^{0}dt\left\lbrack e^{-st}\sinh at\right\rbrack
=\int_{-\infty}^{0}dt\left\lbrack e^{-st}\cdot\frac{e^{+at}-e^{-at}}{2}\right\rbrack
$$
    
$$
=\frac{1}{2}\int_{-\infty}^{0}dt\left\lbrack e^{-(s-a)t}-e^{-(s+a)t} \right\rbrack
=-\frac{a}{s^2-a^2},\quad
\text{ROC: } \operatorname{Re}\lbrace s \rbrace<-|\operatorname{Re}\lbrace a\rbrace|
$$

극점은 $\pm a$ 이다. 이 때, ROC 는 $-|\operatorname{Re}\lbrace a\rbrace|$ 보다 작은 좌측영역에서 형성된다.  

{{< /details >}}

**6-3) sinh 함수**

$$
\mathcal{L}\left\lbrace\sinh at\right\rbrace\left(s\right)
=\langle s|\sinh at\rangle
$$

{{< details summary="sol" >}}
    
겹치는 ROC 영역이 없다. 라플라스 변환은 존재하지 않는다. 또한 직관적으로보면, 적분은 발산한다.

{{< /details >}}

---

### 3. Properties


**1) linearity**

적분연산자 자체가 선형연산자이다.

$$
\mathcal{L}\left\lbrace af\left(t\right)u\left(t\right)+bg\left(t\right)u\left(t\right)\right\rbrace\left(s\right)=a\langle s|f\cdot u\rangle+b\langle s|f\cdot u\rangle
$$

$$
\mathcal{L}\left\lbrace af\left(t\right)+bg\left(t\right)\right\rbrace\left(s\right)=a\langle s|f\rangle+b\langle s|f\rangle
$$

**2) time scaling**

$$
\mathcal{L}\left\lbrace f\left(at-b\right)u\left(at-b\right)\right\rbrace\left(s\right)=\langle s|f\left(at-b\right)u\left(at-b\right)\rangle=\frac{1}{a} e^{-\frac{b}{a}s}\left\langle \frac{s}{a} \middle|f\right\rangle,\quad
\text{단, } a>0, b>0
$$

$$
\mathcal{L}\left\lbrace f\left(at-b\right)\right\rbrace\left(s\right)=\langle s|f\left(at-b\right)\rangle=\frac{1}{|a|}e^{-\frac{b}{a}s}\left\langle \frac{s}{a} \middle|f\right\rangle
$$

{{< details summary="proof, 단방향" >}}

$$
\mathcal{L}\left\lbrace f\left(at-b\right)u\left(at-b\right)\right\rbrace\left(s\right)=e^{-\frac{b}{a}s}\int_0^{\infty}\frac{1}{a}d\tau\left\lbrack f\left(\tau\right)e^{-\frac{s}{a}\tau}\right\rbrack=\frac{1}{a}e^{-\frac{b}{a}s}F\left(\frac{s}{a}\right)
$$

<hr>

{{< /details >}}

{{< details summary="proof, 양방향" >}}

(1) a>0

$$
\mathcal{L}\left\lbrace f\left(at-b\right)\right\rbrace\left(s\right)
=e^{-\frac{b}{a}s}\int_{-\infty}^{\infty}\frac{1}{a}d\tau\left\lbrack f\left(\tau\right)e^{-\frac{s}{a}\tau}\right\rbrack=\frac{1}{a}e^{-\frac{b}{a}s}\mathcal{L}\left\lbrace f\left(t\right)\right\rbrace\left(\frac{s}{a}\right)
$$

(2) a<0

$$
\mathcal{L}\left\lbrace f\left(at-b\right)\right\rbrace\left(s\right)
=e^{-\frac{b}{a}s}\int_{-\infty}^{\infty}-\frac{1}{a}d\tau\left\lbrack f\left(\tau\right)e^{-\frac{s}{a}\tau}\right\rbrack=-\frac{1}{a}e^{-\frac{b}{a}s}\mathcal{L}\left\lbrace f\left(t\right)\right\rbrace\left(\frac{s}{a}\right)
$$

<hr>

{{< /details >}}

**3) time shifting**

$$
\mathcal{L}\left\lbrace f\left(t-t'\right)u(t-t')\right\rbrace\left(s\right)
=e^{-st'}\langle s|f\cdot u\rangle
$$

$$
\mathcal{L}\left\lbrace f\left(t-t'\right)\right\rbrace\left(s\right)
=e^{-st'}\langle s|f\rangle
$$

{{< details summary="proof" >}}

$$
\mathcal{L}\left\lbrace f\left(t-t'\right)\right\rbrace\left(s\right)
=\int_{-\infty}^{\infty}dt\left\lbrack f\left(t-t'\right)e^{-st}\right\rbrack
=\int_{-\infty}^{\infty}d\tau\left\lbrack f\left(\tau\right)e^{-s\left(\tau+t'\right)}\right\rbrack
$$
    
$$
=e^{-st'}F\left(s\right)
$$

<hr>

{{< /details >}}

**4) frequency shifting**

$$
\mathcal{L}\left\lbrace e^{at}f\left(t\right)u(t)\right\rbrace\left(s\right)
=\langle s-a|f\cdot u\rangle
$$

$$
\mathcal{L}\left\lbrace e^{at}f\left(t\right)\right\rbrace\left(s\right)
=\langle s-a|f\rangle
$$

{{< details summary="proof" >}}
    
$$
\mathcal{L}\left\lbrace e^{at}f\left(t\right)\right\rbrace\left(s\right)=\int_{-\infty}^{\infty}dt\left\lbrack f\left(t\right)e^{-\left(s-a\right)t}\right\rbrack=F\left(s-a\right)
$$

<hr>

{{< /details >}}

**5) convolution**

$$
\mathcal{L}\left\lbrace h\left(t\right)u(t)\ast f\left(t\right)u(t)\right\rbrace\left(s\right)=\langle s|h\cdot u\ast f\cdot u\rangle=\langle s|h\cdot u\rangle\langle s|f\cdot u\rangle
$$

$$
\mathcal{L}\left\lbrace h\left(t\right)\ast f\left(t\right)\right\rbrace\left(s\right)=\langle s|h\ast f\rangle=\langle s|h\rangle\langle s|f\rangle
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

**6) 시간영역미분**

$$
\mathcal{L}\left\lbrace\frac{d^{n}}{dt^{n}}f\left(t\right)u(t)\right\rbrace\left(s\right)=s^{n}\langle s|f\cdot u\rangle-s^{n-1}f\left(0\right)-s^{n-2}f^{\left(1\right)}\left(0\right)-s^{n-3}f^{\left(2\right)}\left(0\right)-\cdots
$$

$$
\mathcal{L}\left\lbrace\frac{d^{n}}{dt^{n}}f\left(t\right)\right\rbrace\left(s\right)=s^{n}\langle s|f\rangle
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

$∣f^{(n−1)}(t)∣≤Me^{αt}$, 이면 $\operatorname{Re}\lbrace s\rbrace>α$ 이어야 수렴한다. 

$$
=-f^{\left(n-1\right)}\left(0\right)
+s\left\lbrace-f^{\left(n-2\right)}\left(0\right)+s\int^{\infty}_{0}dt \left[e^{-st}\frac{\partial^{n-2}}{\partial t^{n-2}} f\left(t\right)\right]\right\rbrace
$$

따라서, 반복하면,

$$
\mathcal{L}\left\lbrace\frac{d^{n}}{dt^{n}}f\left(t\right)u(t)\right\rbrace\left(s\right)=s^{n}F\left(s\right)-s^{n-1}f\left(0\right)-s^{n-2}f^{\left(1\right)}\left(0\right)-s^{n-3}f^{\left(2\right)}\left(0\right)-\cdots
$$

양방향 변환에서는 

$$
\left[ e^{-st}\frac{\partial^{n-1}}{\partial t^{n-1}} f\left(t\right)\right]^{\infty}_{0} \to \left[ e^{-st}\frac{\partial^{n-1}}{\partial t^{n-1}} f\left(t\right)\right]^{\infty}_{-\infty} =0
$$

<hr>

{{< /details >}}    

**7) 시간영역적분**

$$
\mathcal{L}\left\lbrace\int_0^{t}dt'\left\lbrack f\left(t'\right)\right\rbrack\right\rbrace\left(s\right)=\langle s|u\ast f\rangle
=\langle s|u\rangle \langle s|f\rangle
=\frac{1}{s}\langle s|f\rangle
$$

$$
\mathcal{L}\left\lbrace\int_{-\infty}^{t}dt'\left\lbrack f\left(t'\right)\right\rbrack\right\rbrace\left(s\right)=\langle s|u\ast f\rangle
=\langle s|u\rangle \langle s|f\rangle
=\frac{1}{s}\langle s|f\rangle
$$

{{< details summary="proof" >}}

$$
\mathcal{L}\left\lbrace\int_{-\infty}^{t}dt'\left\lbrack u\left(t-t'\right)f\left(t'\right)\right\rbrack\right\rbrace\left(s\right)=\mathcal{L}\left\lbrace u\left(t\right)\ast f\left(t\right)\right\rbrace\left(s\right)=\frac{1}{s}F\left(s\right)
$$

<hr>

{{< /details >}}    

**8) s-영역미분**

$$
\mathcal{L}\left\lbrace t^{n}f\left(t\right)u(t)\right\rbrace\left(s\right)
=\langle s|t^n\cdot fu\rangle=\langle s|(\hat{t})^n|fu\rangle=(-1)^n\frac{d^n}{ds^n}\langle s|fu\rangle
$$

$$
\mathcal{L}\left\lbrace t^{n}f\left(t\right)\right\rbrace\left(s\right)
=\langle s|t^n\cdot f\rangle=\langle s|(\hat{t})^n|f\rangle=(-1)^n\frac{d^n}{ds^n}\langle s|f\rangle
$$

$$
\mathcal{L}\left\lbrace tu\left(t\right)\right\rbrace\left(s\right)
=\langle s|t\cdot u\rangle=\langle s|\hat{t}|u\rangle=(-1)^1\frac{d}{ds}\langle s|u\rangle
=\frac{1}{s^2}
$$

$$
\mathcal{L}\left\lbrace t^{n}u\left(t\right)\right\rbrace\left(s\right)
=\langle s|t^n\cdot u\rangle=\langle s|(\hat{t})^n|u\rangle=(-1)^n\frac{d^n}{ds^n}\langle s|u\rangle
=\int_0^{\infty}dt\left\lbrack t^{n}e^{-st}\right\rbrack
=\frac{n!}{s^{n+1}}
$$

{{< details summary="proof" >}}

$$
\mathcal{L}\left\lbrace t^{n}f\left(t\right)\right\rbrace\left(\omega\right)
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

**9) initial value**

$$
f\left(0\right)=\lim_{s\to\infty}s\mathcal{L}\left\lbrace f\left(t\right)u(t)\right\rbrace\left(s\right)
=\lim_{s\to\infty}s \langle s|f\cdot u \rangle
$$

{{< details summary="proof" >}}

$$
\mathcal{L}\left\lbrace \frac{d}{dt} f\left(t\right)u(t)\right\rbrace\left(s\right)=s\mathcal{L}\left\lbrace f\left(t\right)u(t)\right\rbrace\left(s\right)-f\left(0\right)
$$

$$
\int^{\infty}_{0}dt\left[e^{-st}f'\right(t\left)\right]=s\mathcal{L}\left\lbrace f\left(t\right)u(t)\right\rbrace\left(s\right)-f\left(0\right)\quad
$$

<hr>

$$
\lim_{s\to\infty}\int^{\infty}_{0}dt\left[e^{-st}f'\right(t\left)\right]=\lim_{s\to\infty}\left[s\mathcal{L}\left\lbrace f\left(t\right)u(t)\right\rbrace\left(s\right)-f\left(0\right)\right]
$$

만약, $f'(t)$ 가 $e^{-st}$의 감소보다 증가량이 크지 않다면, (에너지 보존 법칙으로 인해, 물리 시스템의 응답, 공학적인 신호 등의 대부분 이 조건을 만족하는 함수들임)

$$
0=\lim_{s\to\infty}\left[s\mathcal{L}\left\lbrace f\left(t\right)u(t)\right\rbrace\left(s\right)-f\left(0\right)\right]
$$

$$
f\left(0\right)=\lim_{s\to\infty}s\mathcal{L}\left\lbrace f\left(t\right)u(t)\right\rbrace\left(s\right)
$$

<hr>

{{< /details >}}    

**10) final value**

- 단방향 라플라스 변환

$$
f\left(\infty\right)=\lim_{s\to0}s\mathcal{L}\left\lbrace f\left(t\right)u(t)\right\rbrace\left(s\right)
=\lim_{s\to 0}s \langle s|f\cdot u \rangle
$$

- 양방향 라플라스 변환

$$
f\left(\infty\right)=\lim_{s\to0}s\mathcal{L}\left\lbrace f\left(t\right)\right\rbrace\left(s\right)
=\lim_{s\to 0}s \langle s|f \rangle
$$

$$
f\left(-\infty\right)=\lim_{s\to0}s\mathcal{L}\left\lbrace f\left(t\right)\right\rbrace\left(s\right)
=-\lim_{s\to 0}s \langle s|f\rangle
$$

{{< details summary="proof" >}}

<b>단방향 라플라스 변환.</b>

단, sF(s)의 모든 극점이 복소 평면의 좌반부(Re{s}<0)에 위치

$$
\mathcal{L}\left\lbrace \frac{d}{dt} f\left(t\right)u(t)\right\rbrace\left(s\right)=s\mathcal{L}\left\lbrace f\left(t\right)u(t)\right\rbrace\left(s\right)-f\left(0\right)
$$

$$
\int^{\infty}_{0}dt\left[e^{-st}f'\right(t\left)\right]=s\mathcal{L}\left\lbrace f\left(t\right)u(t)\right\rbrace\left(s\right)-f\left(0\right)\quad
$$

$$
\lim_{s\to 0}\int^{\infty}_{0}dt\left[e^{-st}f'\right(t\left)\right]=\lim_{s\to 0}\left[s\mathcal{L}\left\lbrace f\left(t\right)u(t)\right\rbrace\left(s\right)-f\left(0\right)\right]
$$

$$
f\left(\infty\right)-f\left(0\right)=\lim_{s\to 0}\left[s\mathcal{L}\left\lbrace f\left(t\right)u(t)\right\rbrace\left(s\right)-f\left(0\right)\right]
$$

$$
f\left(\infty\right)=\lim_{s\to0}s\mathcal{L}\left\lbrace f\left(t\right)u(t)\right\rbrace\left(s\right)
$$

<hr>

<b>양방향 라플라스 변환</b>

$$
\mathcal{L}\left\lbrace \frac{d}{dt} f\left(t\right)\right\rbrace\left(s\right)
=s\langle s|f\rangle
$$

$$
\lim_{s\to 0}\int^{\infty}_{-\infty}dt\left[e^{-st}f'\right(t\left)\right]
=\lim_{s\to 0}\left\lbrace\int^{\infty}_{0}dt\left[e^{-st}f'\right(t\left)\right]+\int^{0}_{-\infty}dt\left[e^{-st}f'\right(t\left)\right]\right\rbrace
$$

$$
f\left(\infty\right)-f\left(-\infty\right)
=\lim_{s\to 0}s\langle s|f\rangle
$$

<b>$f(\infty)$ 최종값</b>, 우측신호일 경우, $f(-\infty)=0$ 이고. ROC는 허수축을 포함해야 함

$$
f\left(\infty\right)
=\lim_{s\to 0}s\langle s|f\rangle
$$

<b>$f(-\infty)$ 최종값</b>, 죄측신호일 경우, $f(\infty)=0$ 이고, ROC는 허수축을 포함해야 함

$$
f\left(-\infty\right)
=-\lim_{s\to 0}s\langle s|f\rangle
$$

{{< /details >}}

---

### 4. 라플라스 변환의 극점과 ROC

라플라스 변환의 **극점은 라플라스 변환이 존재하지 않는 위치**이다. 이것은 원함수가 이 위치에 해당하는 $e^{-(\sigma+i\omega)t}$ 의 성분을 가지고 있다는 의미이다.

- **단방향 라플라스 변환**

단방향 라플라스 변환이 존재하려면 **$t=+\infty$** 에서 수렴해야 하므로, ROC는 $\operatorname{Re}\lbrace s\rbrace>\sigma_{max}$ 인 영역에 존재해야 한다. 정리하면, 다음과 같다. **단방향 라플라스 변환의 수렴 영역은 극점의 가장 큰 실수 값의 우측 영역이다. 극점이 없다면, 모든 영역에서 수렴한다.**

- **양방향 라플라스 변환**

양방향 라플라스 변환이 존재하려면 **$t=\pm\infty$** 에서 수렴해야 하므로, **ROC는 교집힙 영역** 에 존재해야 한다.

---

### 5. Practice

연구실 구성원들에게만 허용된 자료 입니다. [연습문제](https://hertz2hnu.atlassian.net/wiki/spaces/AJpAH3tcG9Jk/pages/53608611/b+LTI+System)

---