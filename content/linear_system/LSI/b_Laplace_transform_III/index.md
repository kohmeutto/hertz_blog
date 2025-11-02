+++
title = "(b) Laplace transform III"
weight = 5.5
+++

---

- 수렴여부에 따라, 분포 라플라스 변환, 표준 라플라스 변환이 존재한다.
- 일반적인 라플라스 변환의 적용은 표준 라플라스 변환을 사용한다.
- **99%의 공학 문제는 안정적인 신호를 다루므로 표준 라플라스로 충분하다.**
- 여기에 나온, **표준 라플라스 변환은 모두 암기** 해야 한다.
- 분포 라플라스 변환에서, **허수축의 경우 푸리에 변환과 동일** 하다.

---

### 1. 중요 변환

- Region of Convergence(ROC) 는 적분값이 수렴하는 s의 영역 이다.
- 중요 계산을 통해 **라플라스 변환의 극점과 ROC의 관계** 를 살펴보자.

**1-1) 디렉 델타 함수**

$$
\langle s^L|\delta\rangle=1,\quad\text{표준 ROC: 모든 } s
$$

<img src="image1-1.png" width="85%" height="auto">

{{< details summary="sol" >}}
    
$$
\int_{-\infty}^{\infty}dt\left\lbrack\delta\left(t\right)e^{-st}\right\rbrack=1\cdot\int_{-\infty}^{\infty}dt\left\lbrack\delta\left(t\right)\right\rbrack=1,\quad
\text{ROC: 모든 } s
$$

<hr>

{{< /details >}}

**1-2) 디렉 델타 함수**

$$
\langle s^L|\delta \cdot u\rangle=1\quad\text{표준 ROC: 모든 } s
$$

<img src="image1-2.png" width="85%" height="auto">

{{< details summary="sol" >}}
    
$$
\int_{0-}^{\infty}dt\left\lbrack\delta\left(t\right)e^{-st}\right\rbrack
=1\cdot\int_{0-}^{\infty}dt\left\lbrack\delta\left(t\right)\right\rbrack=1, \quad
\text{ROC: 모든 } s
$$

<hr>

{{< /details >}}

**2-1) 상수 함수, 분포**

$$
\langle s^L|1\rangle=2\pi\delta(\omega),\quad\text{분포 ROC: }\operatorname{Re}\left\lbrace s\right\rbrace=0
$$

<img src="image2-1.png" width="85%" height="auto">

{{< details summary="sol" >}}
    
시간 신호 $f(t)=1$의 표준적인 양방향 라플라스 변환 적분 $\int_{-\infty}^{\infty}dt\left[e^{-st}\right]$는 어떤 열린 수렴 영역(ROC)에서도 수렴하지 않으므로, 표준적인 양방향 라플라스 변환은 존재하지 않는다. 

그럼에도 불구하고, <b>분포(Distribution)의 영역에서는 양방향 라플라스 변환이 존재</b>한다.

$$
\left. \int_{-\infty}^{\infty}dt\left[e^{-st}\right] \right|_{\operatorname{Re}\left\lbrace s\right\rbrace=0} = \int_{-\infty}^{\infty}dt\left[e^{-j\omega t}\right] = 2\pi\delta(\omega)
$$

$$
\langle s|1\rangle
=2\pi\delta\left(s\right),\quad
\text{ROC: }\operatorname{Re}\left\lbrace s\right\rbrace=0
$$

<hr>

{{< /details >}}

**2-2) 단위 계단 함수**

$$
\langle s^L|u\rangle=\frac{1}{s},\quad\text{표준 ROC: }\operatorname{Re}\left\lbrace s\right\rbrace>0
$$

$$
\langle s^L|u\rangle
=\pi\delta(\omega)+\operatorname{p.v.}\left(\frac{1}{i\omega}\right),\quad\text{분포 ROC: }\operatorname{Re}\left\lbrace s\right\rbrace=0
$$

<img src="image2-2.png" width="85%" height="auto">

{{< details summary="sol" >}}
    
$$
\int_0^{\infty}dt\left\lbrack e^{-st}\right\rbrack=\frac{1}{s},\quad
\text{ROC: } \operatorname{Re}\lbrace s \rbrace>0
$$

극점은 0에서 존재한다. 이 때, ROC는 우측영역에서 형성된다. 이 극점을 포함한 허수축에서 분포 수렴을 확인한다.

$$
\lim_{\sigma\to 0}\langle s^L|u\rangle
=\lim_{\sigma\to 0}\left\langle s^L\middle|\frac{1}{2}+\frac{1}{2}\text{sgn}\right\rangle
=\pi\delta(\omega)+\operatorname{p.v.}\left(\frac{1}{i\omega}\right),\quad
\text{ROC: } \operatorname{Re}\lbrace s \rbrace=0
$$

<hr>

{{< /details >}}

**2-3) 단위 계단 함수**

$$
\langle s^L|u(-t)\rangle=-\frac{1}{s},\quad\text{표준 ROC: }\operatorname{Re}\left\lbrace s\right\rbrace<0
$$

$$
\langle s^L|u(-t)\rangle
=\pi\delta(\omega)-\operatorname{p.v.}\left(\frac{1}{i\omega}\right),\quad\text{분포 ROC: }\operatorname{Re}\left\lbrace s\right\rbrace=0
$$

<img src="image2-3.png" width="85%" height="auto">

{{< details summary="sol" >}}
    
$$
\int_{-\infty}^{0}dt\left\lbrack e^{-st}\right\rbrack=-\frac{1}{s},\quad
\text{ROC: } \operatorname{Re}\lbrace s \rbrace < 0
$$

극점은 0에서 존재한다. 이 때, ROC는 좌측영역에서 형성된다. 이 극점을 포함한 허수축에서 분포 수렴을 확인한다.

$$
\lim_{\sigma\to 0}\langle s^L|u(-t)\rangle
=\lim_{\sigma\to 0}\left\langle s^L\middle|\frac{1}{2}-\frac{1}{2}\text{sgn}\right\rangle
=\pi\delta(\omega)-\operatorname{p.v.}\left(\frac{1}{i\omega}\right),\quad
\text{ROC: } \operatorname{Re}\lbrace s \rbrace=0
$$

<hr>

{{< /details >}}

**3-1) cosine 함수, 분포**

$$
\langle s^L|\cos at\rangle=\pi\delta(\omega-a)+\pi\delta(\omega+a),\quad\text{분포 ROC: }\operatorname{Re}\left\lbrace s\right\rbrace=0
$$

<img src="image3-1.png" width="85%" height="auto">

{{< details summary="sol" >}}
    
위의 cosine 예에서 겹치는 ROC 영역이 없으므로, 표준 라플라스 변환은 존재하지 않는다. 또한 직관적으로보면, 적분은 발산한다.

그럼에도 불구하고, <b>분포(Distribution)의 영역에서는 양방향 라플라스 변환이 존재</b>한다.

$$
\left\langle s^L|\cos at\right\rangle
= \left\langle s^L \middle|\frac{1}{2}\left(e^{+iat}+e^{-iat}\right)\right\rangle
=\frac{1}{2} \left\langle s^L \middle|e^{+iat}\right\rangle+\frac{1}{2} \left\langle s^L \middle|e^{-iat}\right\rangle
$$

$$
=\frac{1}{2} \left\langle (s-ia)^L \middle|1\right\rangle+\frac{1}{2} \left\langle (s+ia)^L \middle|1\right\rangle
$$

$$
=\pi\delta(\omega-a)+\pi\delta(\omega+a),\quad
\text{ROC: } \operatorname{Re}\lbrace s \rbrace=0
$$

<hr>

{{< /details >}}

**3-2) cosine 함수**

$$
\langle s^L|\cos at\cdot u(t)\rangle
=\frac{s}{s^2+a^2},\quad
\text{표준 ROC: } \operatorname{Re}\lbrace s \rbrace>0
$$

$$
\langle s^L|\cos at\cdot u(t)\rangle
=\frac{\pi}{2}\delta(\omega-a)+\frac{\pi}{2}\delta(\omega+a)-\frac{i\omega}{\omega^2-a^2},
\quad\text{분포 ROC: } \operatorname{Re}\lbrace s \rbrace=0
$$

<img src="image3-2.png" width="85%" height="auto">

{{< details summary="sol" >}}
    
$$
\int_0^{\infty}dt\left\lbrack\cos at\cdot e^{-st}\right\rbrack=\operatorname{Re}\left\lbrace\int_0^{\infty}dt\left\lbrack e^{iat}\cdot e^{-st}\right\rbrack\right\rbrace
$$
    
$$
=\operatorname{Re}\left\lbrace\int_0^{\infty}dt\left\lbrack e^{-\left(s-ia\right)t}\right\rbrack\right\rbrace=\frac{s}{s^2+a^2},\quad
\text{ROC: } \operatorname{Re}\lbrace s \rbrace>0
$$

극점은 $\pm ia$ 이다. 이 때, ROC 는 우측영역에서 형성된다. 이 극점을 포함한 허수축에서 분포 수렴을 확인한다.

$$
\langle s^L|\cos at\cdot u\rangle
=\left\langle s^L\middle|\frac{1}{2}(e^{iat}\cdot u+e^{-iat}\cdot u)\right\rangle
=\frac{1}{2}\left\langle (s+ia)^L\middle|u\right\rangle+\frac{1}{2}\left\langle (s-ia)^L\middle|u\right\rangle
$$

$$
=\frac{\pi}{2}\delta(i\omega+ia)+\frac{1}{2i(\omega+a)}+\frac{\pi}{2}\delta(i\omega-ia)+\frac{1}{2i(\omega-a)} 
$$

$$
=\frac{\pi}{2}\delta(\omega+a)+\frac{\pi}{2}\delta(\omega-a)-\frac{i\omega}{\omega^2-a^2},\quad\text{ROC: } \operatorname{Re}\lbrace s \rbrace=0
$$

<hr>

{{< /details >}}

**3-3) cosine 함수**

$$
\langle s^L|\cos at\cdot u(-t)\rangle
=-\frac{s}{s^2+a^2},\quad\text{표준 ROC: } \operatorname{Re}\lbrace s \rbrace<0
$$

$$
\langle s^L|\cos at\cdot u(-t)\rangle
=\frac{\pi}{2}\delta(\omega-a)+\frac{\pi}{2}\delta(\omega+a)+\frac{i\omega}{\omega^2-a^2},\quad\text{분포 ROC: } \operatorname{Re}\lbrace s \rbrace=0
$$

<img src="image3-3.png" width="85%" height="auto">
{{< details summary="sol" >}}
    
$$
\int_{-\infty}^0 dt\left\lbrack\cos at\cdot e^{-st}\right\rbrack
=\operatorname{Re}\left\lbrace\int_{-\infty}^0 dt\left\lbrack e^{iat}\cdot e^{-st}\right\rbrack\right\rbrace
$$
    
$$
=\operatorname{Re}\left\lbrace\int_{-\infty}^0 dt\left\lbrack e^{-\left(s-ia\right)t}\right\rbrack\right\rbrace
=-\frac{s}{s^2+a^2},\quad
\text{ROC: } \operatorname{Re}\lbrace s \rbrace<0
$$

극점은 $\pm ia$ 이다. 이 때, ROC 는 좌측영역에서 형성된다. 이 극점을 포함한 허수축에서 분포 수렴을 확인한다.

$$
\langle s^L|\cos at\cdot u(-t)\rangle
=\left\langle s^L\middle|\frac{1}{2}(e^{iat}\cdot u(-t)+e^{-iat}\cdot u(-t))\right\rangle
$$

$$
=\frac{1}{2}\left\langle (s+ia)^L\middle|u(-t)\right\rangle+\frac{1}{2}\left\langle (s-ia)^L\middle|u(-t)\right\rangle
$$

$$
=\frac{\pi}{2}\delta(i\omega+ia)-\frac{1}{2i(\omega+a)}+\frac{\pi}{2}\delta(i\omega-ia)-\frac{1}{2i(\omega-a)} 
$$

$$
=\frac{\pi}{2}\delta(\omega+a)+\frac{\pi}{2}\delta(\omega-a)+\frac{i\omega}{\omega^2-a^2},\quad\text{ROC: } \operatorname{Re}\lbrace s \rbrace=0
$$

<hr>

{{< /details >}}

**4-1) sine 함수, 분포**

$$
\langle s^L|\sin at\rangle
=-i\pi\delta(\omega-a)+i\pi\delta(\omega+a),\quad
\text{분포 ROC: } \operatorname{Re}\lbrace s \rbrace=0
$$

<img src="image4-1.png" width="85%" height="auto">

{{< details summary="sol" >}}
    
위의 cosine 예에서 겹치는 ROC 영역이 없으므로, 표준 라플라스 변환은 존재하지 않는다. 또한 직관적으로보면, 적분은 발산한다.

그럼에도 불구하고, <b>분포(Distribution)의 영역에서는 양방향 라플라스 변환이 존재</b>한다.

$$
\left\langle s^L|\sin at\right\rangle
= \left\langle s \middle|\frac{1}{2i}\left(e^{+iat}-e^{-iat}\right)\right\rangle
=\frac{1}{2i} \left\langle s^L\middle|e^{+iat}\right\rangle-\frac{1}{2i}\left\langle s^L\middle|e^{-iat}\right\rangle
$$

$$
=\frac{1}{2i}\left\langle (s-ia)^L\middle|1\right\rangle-\frac{1}{2i} \left\langle (s+ia)^L \middle|1\right\rangle
$$

$$
=-i\pi\delta(\omega-a)+i\pi\delta(\omega+a),\quad
\text{ROC: } \operatorname{Re}\lbrace s \rbrace=0
$$

<hr>

{{< /details >}}

**4-2) sine 함수**

$$
\langle s^L|\sin at\cdot u(t)\rangle=\frac{a}{s^2+a^2},\quad \text{표준 ROC: } \operatorname{Re}\lbrace s \rbrace>0
$$

$$
\langle s^L|\sin at\cdot u(t)\rangle
=-i\frac{\pi}{2}\delta(\omega-a)+i\frac{\pi}{2}\delta(\omega+a)-\frac{a}{\omega^2-a^2},\quad \text{분포 ROC: } \operatorname{Re}\lbrace s \rbrace=0
$$

<img src="image4-2.png" width="85%" height="auto">

{{< details summary="sol" >}}
    
$$
\int_0^{\infty}dt\left\lbrack\sin at\cdot e^{-st}\right\rbrack=\operatorname{Im}\left\lbrack\int_0^{\infty}dt\left\lbrace e^{iat}\cdot e^{-st}\right\rbrack\right\rbrace
$$
    
$$
=\operatorname{Im}\left\lbrace\int_0^{\infty}dt\left\lbrack e^{-\left(s-ia\right)t}\right\rbrack\right\rbrace=\frac{a}{s^2+a^2},\quad
\text{ROC: } \operatorname{Re}\lbrace s \rbrace>0
$$

극점은 $\pm ia$ 이다. 이 때, ROC 는 우측영역에서 형성된다. 극점을 포함하는 허수축에서 분포라플라스 변환이 존재한다.

$$
\langle s^L|\sin at\cdot u\rangle
=\left\langle s^L\middle|\frac{1}{2i}(e^{iat}\cdot u-e^{-iat}\cdot u)\right\rangle
$$

$$
=\frac{1}{2i}\left\langle (s-ia)^L\middle|u\right\rangle-\frac{1}{2i}\left\langle (s+ia)^L\middle|u\right\rangle
$$

$$
=\frac{1}{2i}\left\lbrace\pi\delta(i\omega-ia)+\frac{1}{i\omega-ia}\right\rbrace-
\frac{1}{2i}\left\lbrace\pi\delta(i\omega+ia)+\frac{1}{i\omega+ia}\right\rbrace
$$

$$
=-i\frac{\pi}{2}\delta(\omega-a)+i\frac{\pi}{2}\delta(\omega+a)-\frac{a}{\omega^2-a^2},\quad\text{ROC: } \operatorname{Re}\lbrace s \rbrace=0
$$

<hr>

{{< /details >}}

**4-3) sine 함수**

$$
\langle s^L|\sin at\cdot u(-t)\rangle
=-\frac{a}{s^2+a^2},\quad
\text{ROC: } \operatorname{Re}\lbrace s \rbrace<0
$$

$$
\langle s^L|\sin at\cdot u(-t)\rangle
=-i\frac{\pi}{2}\delta(\omega-a)+i\frac{\pi}{2}\delta(\omega+a)+\frac{a}{\omega^2-a^2},\quad\text{ROC: } \operatorname{Re}\lbrace s \rbrace=0
$$

<img src="image4-3.png" width="85%" height="auto">

{{< details summary="sol" >}}
    
$$
\int_{-\infty}^{0}dt\left\lbrack\sin at\cdot e^{-st}\right\rbrack=\operatorname{Im}\left\lbrack\int_{-\infty}^{0}dt\left\lbrace e^{iat}\cdot e^{-st}\right\rbrack\right\rbrace
$$
    
$$
=\operatorname{Im}\left\lbrace\int_{-\infty}^{0}dt\left\lbrack e^{-\left(s-ia\right)t}\right\rbrack\right\rbrace
=-\frac{a}{s^2+a^2},\quad
\text{ROC: } \operatorname{Re}\lbrace s \rbrace<0
$$

극점은 $\pm ia$ 이다. 이 때, ROC 는 좌측영역에서 형성된다. 극점을 포함하는 허수축에서 분포라플라스 변환이 존재한다.

$$
\langle s^L|\sin at\cdot u(-t)\rangle
=\left\langle s^L\middle|\frac{1}{2i}(e^{iat}\cdot u(-t)-e^{-iat}\cdot u(-t))\right\rangle
$$

$$
=\frac{1}{2i}\left\langle (s-ia)^L\middle|u(-t)\right\rangle-\frac{1}{2i}\left\langle (s+ia)^L\middle|u(-t)\right\rangle
$$

$$
=\frac{1}{2i}\left\lbrace\pi\delta(i\omega-ia)-\frac{1}{i\omega-ia}\right\rbrace-
\frac{1}{2i}\left\lbrace\pi\delta(i\omega+ia)-\frac{1}{i\omega+ia}\right\rbrace
$$

$$
=-i\frac{\pi}{2}\delta(\omega-a)+i\frac{\pi}{2}\delta(\omega+a)+\frac{a}{\omega^2-a^2},\quad\text{ROC: } \operatorname{Re}\lbrace s \rbrace=0
$$

<hr>

{{< /details >}}


**5-1) cosh 함수, 분포**

$$
\langle s^L|\cosh at\rangle,\quad\text{존재하지 않는다.}
$$

<img src="image5-1.png" width="85%" height="auto">

{{< details summary="sol" >}}

$$
\left\langle s^L|\cosh at\right\rangle
= \left\langle s^L \middle|\frac{1}{2}\left(e^{+at}+e^{-at}\right)\right\rangle
=\frac{1}{2} \left\langle s^L \middle|e^{+at}\right\rangle+\frac{1}{2} \left\langle s^L \middle|e^{-at}\right\rangle
$$

$$
=\frac{1}{2} \left\langle (s-a)^L \middle|1\right\rangle+\frac{1}{2} \left\langle (s+a)^L \middle|1\right\rangle
$$

$$
=\pi\delta(s-a)+\pi\delta(s+a),\quad
\text{ROC: } 공집합
$$

<br>
    
위의 cosh 에서 겹치는 ROC 영역이 없으므로, 라플라스 변환은 존재하지 않는다. 또한 직관적으로보면, 적분은 발산한다.

<hr>

{{< /details >}}

**5-2) cosh 함수**

$$
\langle s^L|\cosh at\cdot u(t)\rangle=\frac{s}{s^2-a^2},\quad
\text{표준 ROC: } \operatorname{Re}\lbrace s \rbrace>|\operatorname{Re}\lbrace a\rbrace|
$$

$$
\langle s^L|\cosh at\cdot u(t)\rangle,\quad\text{분포 라플라스 변환은 존재하지 않는다.}
$$

<img src="image5-2.png" width="85%" height="auto">

{{< details summary="sol" >}}
    
$$
\int_0^{\infty}dt\left\lbrack e^{-st}\cosh at\right\rbrack
=\int_0^{\infty}dt\left\lbrack e^{-st}\cdot\frac{e^{+at}+e^{-at}}{2}\right\rbrack
$$
    
$$
=\frac{1}{2}\int_0^{\infty}dt\left\lbrack e^{-(s-a)t}+e^{-(s+a)t} \right\rbrack
=\frac{s}{s^2-a^2},\quad
\text{ROC: } \operatorname{Re}\lbrace s \rbrace>|\operatorname{Re}\lbrace a\rbrace|
$$

극점은 $\pm a$ 이다. 이 때, ROC 는 $|\operatorname{Re}\lbrace a\rbrace|$ 보다 큰 우측영역에서 형성된다. 우측 영역에 해당하는 경계에서 분포 라플라스 변환이 존재하는지를 구해보자.

$$
\langle s^L|\cosh at\rangle,\quad\text{존재하지 않는다.}
$$

<br>

위 식은 경계에서도 존재하지 않음을 의미한다.

<hr>

{{< /details >}}

**5-3) cosh 함수**

$$
\langle s^L|\cosh at\cdot u(-t)\rangle=-\frac{s}{s^2-a^2},\quad
\text{ROC: } \operatorname{Re}\lbrace s \rbrace<-|\operatorname{Re}\lbrace a\rbrace|
$$

$$
\langle s^L|\cosh at\cdot u(-t)\rangle\quad
\text{분포 라플라스 변환은 존재하지 않는다.}
$$

<img src="image5-3.png" width="85%" height="auto">

{{< details summary="sol" >}}
    
$$
\int_{-\infty}^{0}dt\left\lbrack e^{-st}\cosh at\right\rbrack
=\int_{-\infty}^{0}dt\left\lbrack e^{-st}\cdot\frac{e^{+at}+e^{-at}}{2}\right\rbrack
$$
    
$$
=\frac{1}{2}\int_{-\infty}^{0}dt\left\lbrack e^{-(s-a)t}+e^{-(s+a)t} \right\rbrack
=-\frac{s}{s^2-a^2},\quad
\text{ROC: } \operatorname{Re}\lbrace s \rbrace<-|\operatorname{Re}\lbrace a\rbrace|
$$

극점은 $\pm a$ 이다. 이 때, ROC 는 $-|\operatorname{Re}\lbrace a\rbrace|$ 보다 작은 좌측영역에서 형성된다.  좌측 영역에 해당하는 경계에서 분포 라플라스 변환이 존재하는지를 구해보자.

$$
\langle s^L|\cosh at\rangle,\quad\text{존재하지 않는다.}
$$

<br>

위 식은 경계에서도 존재하지 않음을 의미한다.

<hr>

{{< /details >}}

**6-1) sinh 함수, 분포**

$$
\langle s^L|\sinh at\rangle,\quad\text{존재하지 않는다.}
$$

<img src="image6-3.png" width="85%" height="auto">

{{< details summary="sol" >}}
    
$$
\left\langle s|\sinh at\right\rangle
=\left\langle s \middle|\frac{1}{2}\left(e^{+at}-e^{-at}\right)\right\rangle
=\frac{1}{2} \left\langle s \middle|e^{+at}\right\rangle-\frac{1}{2} \left\langle s \middle|e^{-at}\right\rangle
$$

$$
=\frac{1}{2} \left\langle s-a\middle|1\right\rangle-\frac{1}{2} \left\langle s+a \middle|1\right\rangle
$$

$$
=\pi\delta(s-a)-\pi\delta(s+a),\quad
\text{ROC: } 공집합
$$

<br>

여기서 중요한 것은 ROC 가 존재하지 않는다. 따라서, 위에서 구한 라플리스 변환은 아무런 의미가 없으며, 라플라스 변환은 존재하지 않는다.

{{< /details >}}

**6-2) sinh 함수**

$$
\langle s^L|\sinh at\cdot u(t)\rangle=\frac{a}{s^2-a^2},\quad
\text{표준 ROC: } \operatorname{Re}\lbrace s \rbrace>|\operatorname{Re}\lbrace a\rbrace|
$$

$$
\langle s^L|\sinh at\cdot u(t)\rangle,\quad\text{분포 라플라스 변환은 존재하지 않는다.}
$$

<img src="image6-1.png" width="85%" height="auto">

{{< details summary="sol" >}}
    
$$
\int_0^{\infty}dt\left\lbrack e^{-st}\sinh at\right\rbrack
=\int_0^{\infty}dt\left\lbrack e^{-st}\cdot\frac{e^{+at}-e^{-at}}{2}\right\rbrack
$$
    
$$
=\frac{1}{2}\int_0^{\infty}dt\left\lbrack e^{-(s-a)t}-e^{-(s+a)t} \right\rbrack
=\frac{a}{s^2-a^2},\quad
\text{ROC: } \operatorname{Re}\lbrace s \rbrace>|\operatorname{Re}\lbrace a\rbrace|
$$

극점은 $\pm a$ 이다. 이 때, ROC 는 $|\operatorname{Re}\lbrace a\rbrace|$ 보다 큰 우측영역에서 형성된다. 우측 영역에 해당하는 경계에서 분포 라플라스 변환이 존재하는지를 구해보자.

$$
\langle s^L|\sinh at\rangle,\quad\text{존재하지 않는다.}
$$

<br>

위 식은 경계에서도 존재하지 않음을 의미한다.  

<hr>

{{< /details >}}

**6-3) sinh 함수**

$$
\langle s^L|\sinh at\cdot u(-t)\rangle=-\frac{a}{s^2-a^2},\quad
\text{표준 ROC: } \operatorname{Re}\lbrace s \rbrace<-|\operatorname{Re}\lbrace a\rbrace|
$$

$$
\langle s^L|\sinh at\cdot u(-t)\rangle,\quad
\text{분포 라플라스 변환은 존재하지 않는다.}
$$


<img src="image6-2.png" width="85%" height="auto">

{{< details summary="sol" >}}
    
$$
\int_{-\infty}^{0}dt\left\lbrack e^{-st}\sinh at\right\rbrack
=\int_{-\infty}^{0}dt\left\lbrack e^{-st}\cdot\frac{e^{+at}-e^{-at}}{2}\right\rbrack
$$
    
$$
=\frac{1}{2}\int_{-\infty}^{0}dt\left\lbrack e^{-(s-a)t}-e^{-(s+a)t} \right\rbrack
=-\frac{a}{s^2-a^2},\quad
\text{ROC: } \operatorname{Re}\lbrace s \rbrace<-|\operatorname{Re}\lbrace a\rbrace|
$$

극점은 $\pm a$ 이다. 이 때, ROC 는 $-|\operatorname{Re}\lbrace a\rbrace|$ 보다 작은 좌측영역에서 형성된다.  좌측 영역에 해당하는 경계에서 분포 라플라스 변환이 존재하는지를 구해보자.

$$
\langle s^L|\sinh at\rangle,\quad\text{존재하지 않는다.}
$$

<br>

위 식은 경계에서도 존재하지 않음을 의미한다. 

{{< /details >}}

