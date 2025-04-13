+++
title = "(b) Exponential - IOPM"
weight = 1
+++

---

**미분방정식의 해는 일반해+특수해 이다.**

아래 예제의 풀이는 일반해를 생략하고, 특수해만 구하는 것이다. 

---

### 1. 유형1

$$
\frac{1}{f\left(D\right)}e^{\alpha x}=\frac{1}{f\left(\alpha\right)}e^{\alpha x,}, \quad f\left(\alpha\right)\ne0
$$

<hr>

**example1)**

$$
y''+y'-2y=e^{3x}
$$

{{< details summary="sol" >}}

$$
\left(D+2\right)\left(D-1\right)y_{p}=e^{3x}
$$

$$
y_{p}=\frac{1}{\left(D+2\right)\left(D-1\right)\left|_{D=3}\right.}e^{3x}=\frac{1}{10}e^{3x}
$$

{{< /details >}}

**example2)**

$$
y''-y'-6y=e^{-x}
$$

{{< details summary="sol" >}}

$$
\left(D-3\right)\left(D+2\right)y_{p}=e^{-x}
$$

$$
y_{p}=\frac{1}{\left(D-3\right)\left(D+2\right)\left|_{D=-1}^{}\right.}e^{-x}=-\frac14e^{-x}
$$

{{< /details >}}

**example3)**

$$
y''-4y'+3y=10e^{-2x}
$$

{{< details summary="sol" >}}

$$
\left(D-3\right)\left(D-1\right)y_{p}=10e^{-2x}
$$

$$
y_{p}=\frac{1}{\left(D-3\right)\left(D-1\right)\left|_{D=-2}\right.}10_{}e^{-2x}=\frac23e^{-2x}
$$
{{< /details >}}

**example4)**

$$
y''+4y'+3y=-5e^{5x}
$$

{{< details summary="sol" >}}

$$
\left(D+1\right)\left(D+3\right)y_{p}=-5e^{5x}
$$

$$
y_{p}=\frac{1}{\left(D+1\right)\left(D+3\right)\left|_{D=5}\right.}-5e^{5x}=-\frac{5}{48}e^{5x}
$$

{{< /details >}}

**example5)**

$$
x^2y''-4xy'+6y=2e^{4x}
$$

{{< details summary="sol" >}}

$$
\left(D-3\right)\left(D-2\right)y_{p}=2e^{4x} 
$$

$$
y_{p}=\frac{1}{\left(D-3\right)\left(D-2\right)\left|_{D=4}\right.}2e^{4x}=e^{4x}
$$

{{< /details >}}

**example6)**

$$
x^2y''-xy'-8y=9e^{-7x}
$$

{{< details summary="sol" >}}

$$
\left(D-4\right)\left(D+2\right)y_{p}=9e^{-7x} 
$$

$$
y_{p}=\frac{1}{\left(D-4\right)\left(D+2\right)\left|_{D=-7}\right.}9e^{-7x}=-\frac{9}{55}e^{-7x}
$$

{{< /details >}}

---

### 2. 유형2

$$
\frac{1}{\left(D-\alpha\right)^{n}}e^{\alpha x}=\frac{x^{n}}{n!}e^{\alpha x}
$$

<hr>

**example1)**

$$
y''+2y'+y=e^{-x}
$$

{{< details summary="sol" >}}

$$
\left(D+1\right)^2y_{p}=e^{-x}
$$

$$
y_{p}=\frac{1}{\left(D+1\right)^2}e^{-x}=\frac{x^2}{2}e^{-x}
$$

{{< /details >}}


**example2)**

$$
y''-6y'+9y=-e^{3x}
$$

{{< details summary="sol" >}}

$$
\left(D-3\right)^2y_{p}=-e^{3x}
$$

$$
y_{p}=-\frac{1}{\left(D-3\right)^2}e^{3x}=-\frac{x^2}{2}e^{3x}
$$

{{< /details >}}

**example3)**

$$
y''+4y'+4y=3e^{-2x}
$$

{{< details summary="sol" >}}

$$
\left(D+2\right)^2y_{p}=3e^{-2x} 
$$

$$
y_{p}=\frac{1}{\left(D+2\right)^2}3e^{-2x}=\frac{3x^2}{2}e^{-2x}
$$

{{< /details >}}

---

### 3. 유형3

$$
\frac{1}{f\left(D\right)\left(D-\alpha\right)^{n}}e^{\alpha x}=\frac{x^{n}}{f\left(\alpha\right)n!}e^{\alpha x}
$$

<hr>

**example1)**

$$
y''+y'-2y=e^{x}
$$

{{< details summary="sol" >}}

$$
\left(D+2\right)\left(D-1\right)y_{p}=e^{x} 
$$

$$
y_{p}=\frac{1}{\left.\left(D+2\right)\right|_{D=1}\left(D-1\right)^{}}e^{x}=\frac13\cdot xe^{-x}
$$

{{< /details >}}

**example2)**

$$
y''-4y'+3y=-2e^{3x}
$$

{{< details summary="sol" >}}

$$
\left(D-1\right)\left(D-3\right)y_{p}=-2e^{3x} 
$$

$$
y_{p}=\frac{1}{\left.\left(D-1\right)\right|_{D=3}\left(D-3\right)}-2e^{3x}=\frac12\cdot x\cdot-2e^{3x}
$$

{{< /details >}}

**example3)**

$$
x^2y''-4xy'+6y=2e^{3x}
$$

{{< details summary="sol" >}}

$$
\left(D-3\right)\left(D-2\right)y_{p}=2e^{3x} 
$$

$$
y_{p}=\frac{1}{\left(D-2\right)\left|_{D=3}^{}\right.\left(D-3\right)^{}}2e^{3x}=2xe^{3x}
$$

{{< /details >}}

**example4)**

$$
x^2y''-4xy'-14y=3e^{-2x}
$$

{{< details summary="sol" >}}

$$
\left(D+2\right)\left(D-7\right)y_{p}=3e^{-2x} 
$$

$$
y_{p}=\frac{1}{\left(D-7\right)\left|_{D=-2}\right.\left(D+2\right)}3e^{-2x}=-\frac{x}{3}e^{-2x}
$$

{{< /details >}}