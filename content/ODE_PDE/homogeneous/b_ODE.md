+++
title = "(b) ODE - Homogenous"
weight = 1
+++

### 1. 상미분제차차방정식

$$
y''+ay'+by=0
$$

$$
D^2+aD+b=0
$$

---

### 2. 서로 다른, 실수 해

$$
D=\alpha,\beta
$$

$$
y=c_1e^{\alpha x}+c_2e^{\beta x}
$$

---

**example1)**

$$
y''-y'-2y'=0
$$

{{< details summary="sol" >}}

$$
\left(D-2\right)\left(D+1\right)=0\rightarrow D=-1,2 
$$

$$
y=c_1e^{-1x}+c_2e^{2x}
$$

<hr>

{{< /details >}}

**example2)**

$$
y''-4y'=0
$$

{{< details summary="sol" >}}

$$
D\left(D-4\right)=0\rightarrow D=0,4
$$

$$
y=c_1+c_2e^{4x}
$$

{{< /details >}}

---

### 2. 중근

$$
D=\alpha
$$

$$
y=\left(c_1+c_2x\right)e^{\alpha x}
$$

---

**example1)**

$$
y''+6y'+9y=0
$$

{{< details summary="sol" >}}

$$
\left(D+3\right)^2=0 \rightarrow D=-3
$$

$$
y=\left(c_1+c_2x\right)e^{-3x}
$$

{{< /details >}}

---

### 3. 서로 다른, 복소수 해

$$
D=\alpha\pm i\beta
$$

$$
y=e^{\alpha x}\left(c_1\cos\beta x+c_2\sin\beta x\right)
$$

$$
y=e^{\alpha x}\left(c_1e^{+i\beta x}+c_2e^{-i\beta x}\right)
$$

---

**example1)**

$$
y''+4y=0
$$  

{{< details summary="sol" >}}

$$
D^2+4=0\rightarrow D=\pm 2i
$$

$$
y=c_1\cos 2x+c_2\sin 2x
$$

<hr>

{{< /details >}}

**example2)**

$$
y''+2y'+2y=0
$$  

{{< details summary="sol" >}}

$$
D^2+2D+2=0\rightarrow D=-1\pm \sqrt{1-2}=-1\pm i
$$

$$
y=e^{-x}\left(c_1\cos x+c_2\sin x\right)
$$

<hr>

{{< /details >}}

**example3)**

$$
y''-2y'+10y=0
$$  

{{< details summary="sol" >}}

$$
D^2-2D+10=0\rightarrow D=1\pm \sqrt{1-10}=-1\pm 3i
$$

$$
y=e^{x}\left(c_1\cos 3x+c_2\sin 3x\right)
$$

<hr>

{{< /details >}}

**example4)**

$$
y'''-2y''+3y'-6y=0
$$  

{{< details summary="sol" >}}

$$
D^3-2D^2+4D-6=0\rightarrow \left(D-2\right)\left(D^2+3\right)=0
$$

$$
y=c_1e^{2x}+c_2\cos 3x+c_3\sin 3x
$$

<hr>

{{< /details >}}

**example5)**

$$
y'''-6y''+12y'-8y=0
$$  

{{< details summary="sol" >}}

$$
D^3-6D^2+12D-8=0\rightarrow \left(D-2\right)^3=0
$$

$$
y=e^{2x}\left(c_1+c_2x+c_3 x^2\right)
$$

{{< /details >}}