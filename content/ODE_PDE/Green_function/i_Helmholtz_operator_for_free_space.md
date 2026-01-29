+++
title = "(i) Helmholtz operator for free-space"
weight = 7
+++

---

### 1. 구 대칭, free-space (결과 암기)

$$
\left(\nabla^2+k^2\right)G\left(\vec{r},\vec{r}'\right)=\delta^3\left(\vec{r}-\vec{r}'\right)
$$

그린함수는 다음과 같다.

(1) 방사방향이 e$^{+ikR}$

$$
G\left(\vec{r},\vec{r}'\right)=-\frac{e^{+ik\left|\vec{r}-\vec{r}'\right|}}{4\pi\left|\vec{r}-\vec{r}'\right|}=-\frac{e^{+ikR}}{4\pi R}
$$

(2) 방사방향이  e$^{-ikR}$

$$
G\left(\vec{r},\vec{r}'\right)=-\frac{e^{-ik\left|\vec{r}-\vec{r}'\right|}}{4\pi\left|\vec{r}-\vec{r}'\right|}=-\frac{e^{-ikR}}{4\pi R}
$$

<hr>

**proof)**

경계조건이 특정하게 주어져 있지 않은 경우, Helmholtz 연산자는 이동 불변성을 만족한다. 미분 연산은 기울기 이기 때문에, 위치가 이동하더라도, 기울기는 변하지 않는다. 또한 상수 곱셈의 경우, 위치가 이동하여도, 곱해지는 값은 동일하다.

$$
R=\left|\vec{r}-\vec{r}'\right|
$$

$$
\nabla^2:=\frac{1}{R^2}\frac{\partial}{\partial R}\left(R^2\frac{\partial}{\partial R}\right)
$$

$$
\left\lbrack\frac{1}{R^2}\frac{\partial}{\partial R}\left(R^2\frac{\partial}{\partial R}\right)+k^2\right\rbrack G\left(R\right)=\frac{\delta\left(R\right)}{4\pi R^2}
$$

위 미분 방정식은 구면 베셀 방정식 형태이다. 변수 치환을 사용하여 간단하게 만들 수 있다.

$$
G\left(R\right)=\frac{\varphi\left(R\right)}{R}
$$

$$
\left(\frac{\partial^2}{\partial R^2}+k^2\right)\varphi\left(R\right)=\frac{\delta\left(R\right)}{4\pi R}
$$

(1) R>0

$$
\varphi\left(R\right)=a_{-}e^{-ikx}+a_{+}e^{+ikx}
$$

$$
G\left(R\right)=\frac{a_{-}}{R}e^{-ikR}+\frac{a_{+}}{R}e^{+ikR}
$$

방사 방향을 e$^{+ikR}$로 설정하면,

$$
G\left(R\right)=\frac{a_{+}}{R}e^{+ikR}
$$

(2) Jump condition

$$
\left.R^2\frac{\partial}{\partial R}G\left(R\right)\right|_{0_{<}}=\left.\frac{1}{4\pi}u\left(R\right)\right|_{0_{<}}
$$

$$
\frac{\partial}{\partial R}G\left(R\right)=-\frac{a_{+}}{R^2}e^{+ikR}+ik\frac{a_{+}}{R}e^{+ikR}
$$

$$
\left.R^2\frac{\partial}{\partial R}G\left(R\right)\right|_{0_{<}}=-a_{+}
$$

$$a_{+}=\left.\frac{1}{4\pi}u\left(R\right)\right|_{0_{<}}=\frac{1}{4\pi}
$$

따라서,

$$
G\left(R\right)=-\frac{e^{+ikR}}{4\pi R}
$$

$$
G\left(\vec{r},\vec{r}'\right)=-\frac{e^{+ik\left|\vec{r}-\vec{r}'\right|}}{4\pi\left|\vec{r}-\vec{r}'\right|}
$$