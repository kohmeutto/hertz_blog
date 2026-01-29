+++
title = "(a) Displacement - IOPM"
weight = 4
+++

---

**미분방정식의 해는 일반해+특수해 이다.**

아래 예제의 풀이는 일반해를 생략하고, 특수해만 구하는 것이다. 

---

### 1. 유형1

$$
\frac{1}{f\left(D\right)}\left\lbrack e^{\alpha x}R\left(x\right)\right\rbrack=e^{\alpha x}\frac{1}{f\left(D+\alpha\right)}\left\lbrack R\left(x\right)\right\rbrack
$$

<hr>

**example1)**

$$
y''-3y'-4y=xe^{-2x}
$$

{{< details summary="sol" >}}

$$
\left(D-4\right)\left(D+1\right)y_{p}=xe^{-2x}
$$

$$
y_{p}=\frac{1}{\left(D-4\right)\left(D+1\right)}\left\lbrack xe^{-2x}\right\rbrack=e^{-2x}\frac{1}{\left(D-6\right)\left(D-1\right)}\left\lbrack x\right\rbrack
$$

$$
=\frac{e^{-2x}}{6}\left(1+\frac76D\right)\left\lbrack x\right\rbrack=\frac{e^{-2x}}{6}\left(x+\frac76\right)
$$

<hr>

{{< /details >}}

**example2)**

$$
y''-y'-2y=e^{3x}\sin x
$$

{{< details summary="sol" >}}

$$
\left(D-2\right)\left(D+1\right)y_{p}=e^{3x}\sin x
$$

$$
y_{p}=e^{3x}\frac{1}{\left(D+1\right)\left(D+4\right)}\sin x
$$

$$=e^{3x}\operatorname{Im}\left\lbrack\frac{1}{\left(D+1\right)\left(D+4\right)\left|_{D=i}\right.}e^{ix}\right\rbrack=e^{3x}\operatorname{Im}\left\lbrack\frac{1}{5i+3}e^{ix}\right\rbrack
$$

$$
=e^{3x}\operatorname{Im}\left\lbrack\frac{1}{5i+3}e^{ix}\right\rbrack=e^{3x}\left(\frac{5}{34}\cos x-\frac{3}{34}\sin x\right)
$$

<hr>

{{< /details >}}

**example3)**

$$
y''-y'-2y=x\cos x
$$

{{< details summary="sol" >}}

$$
\left(D^2-D-2\right)y_{p}=x\cos x
$$

$$
y_{p}=\frac{1}{\left(D^2-D-2\right)}x\cos x
$$

$$
=\operatorname{Re}\left\lbrack e^{ix}\cdot\frac{1}{\left(D+i\right)^2-\left(D+i)-2\right.}\left\lbrace x\right\rbrace\right\rbrack
$$

$$
=\operatorname{Re}\left\lbrack e^{ix}\cdot\frac{1}{D^2+\left(2i-1\right)D-\left(3+i\right)}\left\lbrace x\right\rbrace\right\rbrack=\operatorname{Re}\left\lbrack-\frac{e^{ix}}{3+i}\cdot\frac{1}{1-\frac{2i-1}{i+3}D}x\right\rbrack
$$

$$
=\operatorname{Re}\left\lbrack-\frac{e^{ix}}{3+i}\left(1+\frac{2i-1}{i+3}D\right)\left\lbrace x\right\rbrace\right\rbrack=\operatorname{Re}\left\lbrack-\frac{e^{ix}}{3+i}\left(x+\frac{2i-1}{i+3}\right)\right\rbrack 
$$

$$
=\operatorname{Re}\left\lbrack-\frac{3-i}{10}\left(x+\frac{\left(2i-1\right)\left(-i+3\right)}{10}\right)\left(\cos x+i\sin x\right)\right\rbrack
$$

$$
=-\frac{3}{10}x\cos x-\frac{1}{10}x\sin x-\frac{1}{25}\cos x+\frac{11}{50}\sin x
$$

{{< /details >}}