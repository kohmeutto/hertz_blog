+++
title = "(b) Trigonometric - IOPM"
weight = 2
+++

---

**미분방정식의 해는 일반해+특수해 이다.**

아래 예제의 풀이는 일반해를 생략하고, 특수해만 구하는 것이다. 

---

### 1. 유형1

$$
\frac{1}{f\left(D\right)}\cos\alpha x=\operatorname{Re}\left\lbrack\frac{1}{f\left(D\right)}e^{i\alpha x}\right\rbrack
$$

$$
\frac{1}{f\left(D\right)}\sin\alpha x=\operatorname{\operatorname{Im}}\left\lbrack\frac{1}{f\left(D\right)}e^{i\alpha x}\right\rbrack
$$

<hr>

**example1)**

$$
y''-y'-2y=\cos x
$$

{{< details summary="sol" >}}

$$
\left(D^2-D-2\right)y_{p}=\operatorname{Re}\left\lbrack e^{ix}\right\rbrack
$$

$$
y_{p}=\operatorname{Re}\left\lbrack\frac{1}{\left(D^2-D-2\right)\left|_{D=i}\right.}e^{ix}\right\rbrack=\operatorname{Re}\left\lbrack\frac{1}{-3-i}e^{ix}\right\rbrack 
$$

$$
=\operatorname{Re}\left\lbrack\frac{-3+i}{10}\left(\cos x+i\sin x\right)\right\rbrack=-\frac{3}{10}\cos x-\frac{1}{10}\sin x
$$

<hr>

{{< /details >}}

**example2)**

$$
y''-3y'-4y=\sin 2x
$$

{{< details summary="sol" >}}

$$
\left(D^2-3D-4\right)y_{p}=\operatorname{Im}\left\lbrack e^{i2x}\right\rbrack 
$$

$$
y_{p}=\operatorname{\operatorname{Im}}\left\lbrack\frac{1}{\left(D^2-3D-4\right)\left|_{D=2i}^{}\right.}e^{i2x}\right\rbrack=\operatorname{\operatorname{Im}}\left\lbrack\frac{1}{-8-6i}e^{i2x}\right\rbrack
$$

$$
=\operatorname{\operatorname{Im}}\left\lbrack\frac{-8+6i}{100}\left(\cos2x+i\sin2x\right)\right\rbrack=-\frac{2}{25}\sin2x+\frac{3}{50}\cos2x
$$

<hr>

{{< /details >}}

**example3)**

$$
y''+y'-2y=4\sin 2x
$$

{{< details summary="sol" >}}

$$
\left(D^2+D-2\right)y_{p}=4\sin2x 
$$

$$
y_{p}=\operatorname{Im}\left\lbrack\frac{1}{\left(D^2+D-2\right)\left|_{D=2i}\right.}4e^{2ix}\right\rbrack=\operatorname{Im}\left\lbrack\frac{2}{-3+i}e^{2ix}\right\rbrack 
$$

$$
=\operatorname{Im}\left\lbrack\frac{-6+2i}{10}\left(\cos2x+i\sin2x\right)\right\rbrack=\frac15\cos2x-\frac35\sin2x
$$

<hr>

{{< /details >}}

**example4)**

$$
y''+25y=32\cos 3x
$$

{{< details summary="sol" >}}

$$
\left(D^2+25\right)y_{p}=32\cos3x 
$$

$$
y_{p}=\operatorname{Re}\left\lbrack\frac{1}{\left(D+5i\right)\left(D-5i\right)\left|_{D=3i}\right.}32e^{i3x}\right\rbrack=\operatorname{Re}\left\lbrack\frac{1}{16}32e^{i3x}\right\rbrack=2\cos3x
$$

<hr>

{{< /details >}}

**example5)**

$$
y''+4y=\sin 2x
$$

{{< details summary="sol" >}}

$$
\left(D^2+4\right)y_{p}=\sin2x 
$$

$$
y_{p}=\operatorname{Im}\left\lbrack\frac{1}{\left.\left(D+2i\right)\right|_{D=2i}\left(D-2i\right)}e^{2ix}\right\rbrack=\operatorname{Im}\left\lbrack\frac{1}{4i}\cdot x\cdot e^{2ix}\right\rbrack 
$$

$$=\operatorname{Im}\left\lbrack\frac{1}{4i}\cdot x\cdot\left(\cos2x+i\sin2x\right)\right\rbrack=-\frac{x}{4}\cos2x
$$

<hr>

{{< /details >}}

**example6)**

$$x^2y''-2xy'+2y=\cos x$$

{{< details summary="sol" >}}

$$
\left(D^2-3D+2\right)y_{p}=\operatorname{Re}\left\lbrack e^{ix}\right\rbrack 
$$

$$
y_{p}=\operatorname{Re}\left\lbrack\frac{1}{\left(D^2-3D+2\right)\left|_{D=i}\right.}e^{ix}\right\rbrack=\operatorname{Re}\left\lbrack\frac{1}{-3i+1}e^{ix}\right\rbrack 
$$

$$=\operatorname{Re}\left\lbrack\frac{3i+1}{10}\left(\cos x+i\sin x\right)\right\rbrack=\frac{1}{10}\cos x-\frac{3}{10}\sin x
$$

<hr>

{{< /details >}}

**example7)**

$$
x^2y^{\prime\prime}+xy^{\prime}+25y=3\sin3x
$$

{{< details summary="sol" >}}

$$
\left(D^2+5\right)y_{p}=3\sin3x 
$$

$$
y_{p}=\operatorname{\operatorname{\operatorname{\operatorname{Im}}}}\left\lbrack\frac{1}{\left(D+5i\right)\left(D-5i\right)\left|_{D=3i}^{}\right.}3e^{i3x}\right\rbrack=\operatorname{Im}\left\lbrack\frac{1}{16}3e^{i2x}\right\rbrack 
$$

$$
=\operatorname{Im}\left\lbrack\frac{1}{16}\cdot 3\cdot\left(\cos3x+i\sin3x\right)\right\rbrack=\frac{3}{16}\sin3x
$$

{{< /details >}}