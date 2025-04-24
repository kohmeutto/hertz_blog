+++
title = "(b) Polynomial - IOPM"
weight = 3
+++

---

**미분방정식의 해는 일반해+특수해 이다.**

아래 예제의 풀이는 일반해를 생략하고, 특수해만 구하는 것이다. 

---

### 1. 유형1

$$
\frac{1}{f\left(D\right)}\left\lbrace \text{polynomial}\right\rbrace
$$

<hr>

**example1)**

$$
y''+y=x^2
$$

{{< details summary="sol" >}}

$$
\left(D^2+1\right)y_{p}=x^2
$$

$$
y_{p}=\operatorname{}\frac{1}{1+D^2}x^2=\left(1-D^2\right)x^2=x^2-2
$$

<hr>

{{< /details >}}

**example2)**

$$
y''+y'-6y=6x^3-3x^2+12
$$

{{< details summary="sol" >}}

$$
\left(D^2+D-6\right)y_{p}=6x^3-3x^2+12x
$$

$$
y_{p}=-\frac16\cdot\frac{1}{1-\frac16D-\frac16D^2}\left\lbrack6x^3-3x^2+12\right\rbrack
$$

$$
=-\frac16\cdot\left(1+\frac16D+\frac{7}{36}D^2+\frac{13}{216}D^3\right)\left\lbrack6x^3-3x^2+12x\right\rbrack
$$

$$
=-x^3-3x-\frac12
$$

<hr>

{{< /details >}}

**example3)**

$$
\frac{1}{4} y''+y'+y=x^2-2x
$$

{{< details summary="sol" >}}

$$
\frac{1}{1-x}=1+x+x^2+x^3\cdots
$$

$$
y_{p}=\frac{1}{1+D+\frac14D^2}_{}\left\lbrack x^2-2x\right\rbrack
$$

$$
=\left(1-D+\frac34D^2\right)\left\lbrack x^2-2x\right\rbrack
$$

$$
=x^2-4x+\frac{7}{2}
$$

<hr>

{{< /details >}}

**example4)**

$$
x^2y''+3xy'+3y=2x^2-2
$$

{{< details summary="sol" >}}

$$
\left(D^2+2D+3\right)y_{p}=x^2-2x
$$

$$
y_{p}=\frac13\cdot\frac{1}{1+\frac{2}{3}D+\frac{1}{3}D^2}\left\lbrack2x^2-2\right\rbrack 
$$

$$=\left(1-\frac23D+\frac{1}{9}D^2\right)\left\lbrack2x^2-x\right\rbrack
$$

$$
=\frac23x^2-\frac{8}{3}x
$$

{{< /details >}}

---

### 2. 유형2

$$
\frac{1}{Df\left(D\right)}\left\lbrack R\left(x\right)\right\rbrack=\int_{x=x'}dx'\left\lbrack\frac{1}{f\left(D\right)}\left\lbrack R\left(x'\right)\right\rbrack\right\rbrack
$$

<hr>

**example1)**

$$
y''+y'=2x
$$

{{< details summary="sol" >}}

$$
D\left(D+1\right)y_{p}=2x 
$$

$$
y_{p}=\frac{1}{D\left(1+D\right)}2x=\int_{x=x'}dx'\left\lbrack\left(1-D\right)2x'\right\rbrack=\int_{x=x'}dx'\left\lbrack2x'-2\right\rbrack=x^2-2x
$$

<hr>

{{< /details >}}

**example2)**

$$
y''-2y'=x
$$

{{< details summary="sol" >}}

$$
D\left(D-2\right)y_{p}=x 
$$

$$
y_{p}=\operatorname{}\frac{1}{D\left(D-2\right)}x=\int_{x=x'}dx'\left\lbrack-\frac12\left(1+\frac12D\right)x'\right\rbrack=\int_{x=x'}dx'\left\lbrack-\frac12x'-\frac14\right\rbrack
$$

$$
=-x^2-\frac14x
$$

<hr>

{{< /details >}}

**example3)**

$$
x^2y''-2xy'=3x
$$

{{< details summary="sol" >}}

$$
D\left(D-3\right)y_{p}=3x
$$

$$
y_{p}=\frac{1}{D\left(D-3\right)}x=\int_{x=x'}dx'\left\lbrack-\frac13\left(1+\frac13D\right)x'\right\rbrack=\int_{x=x'}dx'\left\lbrack-\frac13x'-\frac19\right\rbrack
$$

$$
=-\frac16x^2-\frac19x
$$

{{< /details >}}