+++
title = "(b) Laplace transform II"
weight = 4
+++

---

이 챕터에서는 단방향 라플라스 변환을 의미한다. 여기에 제시된 내용은 모두 암기한다.

---


### 1. 중요변환

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

### 2. Properties

**1) time scaling**

$$
\mathcal{L}\left\lbrace f\left(at\right)\right\rbrace\left(s\right)=\frac{1}{\left|a\right|}F\left(\frac{s}{a}\right)
$$

{{< details summary="proof" >}}

$$
\mathcal{L}\left\lbrace f\left(at\right)\right\rbrace\left(s\right)=\int_0^{\infty}\frac{1}{a}d\tau\left\lbrack f\left(\tau\right)e^{-\frac{s}{a}\tau}\right\rbrack=\frac{1}{a}F\left(\frac{s}{a}\right)
$$

<hr>

{{< /details >}}

**2) time shifting**

$$
\mathcal{L}\left\lbrace f\left(t-t^{\prime}\right)\right\rbrace\left(s\right)=e^{-st^{\prime}}\mathcal{L}\left\lbrack f\left(t\right)\right\rbrack
$$

{{< details summary="proof" >}}

$$
\mathcal{L}\left\lbrace f\left(t-t^{\prime}\right)\right\rbrace\left(s\right)=\int_0^{\infty}dt\left\lbrack f\left(t-t^{\prime}\right)e^{-st}\right\rbrack=\int_{-\infty}^{\infty}d\tau\left\lbrack f\left(\tau\right)e^{-s\left(\tau+t^{\prime}\right)}\right\rbrack
$$
    
$$
=e^{-st^{\prime}}F\left(\omega\right)
$$

<hr>

{{< /details >}}


**3) frequency shifting**

$$
\mathcal{L}\left\lbrace e^{at}f\left(t\right)\right\rbrace\left(s\right)=F\left(s-a\right)
$$

- proof
    
    $$
    \mathcal{L}\left\lbrace e^{at}f\left(t\right)\right\rbrace\left(s\right)=\int_0^{\infty}dt\left\lbrack f\left(t\right)e^{-\left(s-a\right)t}\right\rbrack=F\left(s-a\right)
    $$
    

**4) convolution**

$$
\mathcal{L}\left\lbrace h\left(t\right)\ast f\left(t\right)\right\rbrace\left(s\right)=H\left(\omega\right)F\left(\omega\right)
$$

- proof
    
    라플라스 변환을 사용 @Seungmin Son 
    
    ---
    
    라플라스 역변환을 사용한다. 입력 함수는, eigenfunction의 선형결합으로 **표현할 수 있다고 가정**해보자.  (표현할 수 없는 경우도 존재함)
    
    - -uriencoded--f\left(t\right)=\frac%7B1%7D%7BA%7D\int_%7Bc-i\infty%7D%5e%7Bc+i\infty%7DF\left(s\right)e%5e%7Bst%7Dds
    - -uriencoded--h\left\lbrack f\left(t\right)\right\rbrack=\frac%7B1%7D%7BA%7D\int_%7B-\infty%7D%5e%7B\infty%7Ddt%5e%7B\prime%7D\left\lbrack h\left(t%5e%7B\prime%7D\right)\int_%7Bc-i\infty%7D%5e%7Bc+i\infty%7Dds\left\lbrack F\left(s\right)e%5e%7Bs\left(t-t%5e%7B\prime%7D\right)%7D\right\rbrack\right\rbrack
    - -uriencoded--=\frac%7B1%7D%7BA%7D\int_%7Bc-i\infty%7D%5e%7Bc+i\infty%7Dds\left\lbrack F\left(s\right)\int_%7B-\infty%7D%5e%7B\infty%7Ddt%5e%7B\prime%7D\left\lbrack h\left(t%5e%7B\prime%7D\right)e%5e%7Bs\left(t-t%5e%7B\prime%7D\right)%7D\right\rbrack\right\rbrack
    - -uriencoded--=\frac%7B1%7D%7BA%7D\int_%7Bc-i\infty%7D%5e%7Bc+i\infty%7Dds\left\lbrack F\left(s\right)e%5e%7Bst%7D\int_%7B-\infty%7D%5e%7B\infty%7Ddt%5e%7B\prime%7D\left\lbrack h\left(t%5e%7B\prime%7D\right)e%5e%7B-st%5e%7B\prime%7D%7D\right\rbrack\right\rbrack
    - -uriencoded--=\frac%7B1%7D%7BA%7D\int_%7Bc-i\infty%7D%5e%7Bc+i\infty%7Dds\left\lbrack F\left(s\right)H\left(s\right)e%5e%7Bst%7D\right\rbrack
    
    **즉,** $h\left(t\right)\ast f\left(t\right)$**의** $e^{st}$**에 대한, 라플라스 변환에 해당하는 eigenvalue 는**
    
    $$
    \mathcal{L}\left\lbrace h\ast f\right\rbrace\left(s\right)=H\left(s\right)F\left(s\right)=F\left(s\right)H\left(s\right)
    $$
    

**5) differentiation**

$$
\mathcal{L}\left\lbrace\frac{d^{n}}{dx^{n}}f\left(t\right)\right\rbrace\left(s\right)=s^{n}F\left(\omega\right)-s^{n-1}f\left(0\right)-s^{n-2}f^{\left(1\right)}\left(0\right)-s^{n-3}f^{\left(2\right)}\left(0\right)-\cdots
$$

- proof
    
    @Seungmin Son 
    

**6) integration**

$$
\mathcal{L}\left\lbrace\int_0^{t}dt^{\prime}\left\lbrack f\left(t^{\prime}\right)\right\rbrack\right\rbrace\left(s\right)=\mathcal{L}\left\lbrace u\left(t\right)\ast f\left(t\right)\right\rbrace\left(s\right)=\frac{1}{s}F\left(s\right)
$$

- proof
    
    [최수인 (Unlicensed)](https://hertz2hnu.atlassian.net/wiki/people/712020:1f3af0d6-22e5-4b45-9a8a-7a617da825a0?ref=confluence)
    

**7) initial and final values**

$$
f\left(0\right)=\lim_{s\rightarrow\infty}\mathcal{sL}\left\lbrace f\left(t\right)\right\rbrace\left(s\right)
$$

$$
f\left(\infty\right)=\lim_{s\rightarrow0}\mathcal{sL}\left\lbrace f\left(t\right)\right\rbrace\left(s\right)
$$

- proof
    
    @Seungmin Son
    

---

### 3. Practice

[CH08-1 Laplace transform I.pdf](CH08-1_Laplace_transform_I.pdf)

[CH08-1 Laplace transform I.pdf](CH08-1_Laplace_transform_I%201.pdf)

---

### 4. 주의사항

**[주의] 컨볼루션의** $h,f$ **함수가 반드시 선형일 필요는 없다. 참조 (**[라플라스 변환(Laplace Transform) - 6. 합성곱(Convolution) :: jjycjn's Math Storehouse (tistory.com)](https://jjycjnmath.tistory.com/97))