+++
title = "(i) GF from SL"
weight = 9
+++

---

미분방정식이 아래와 같이 표현되었을 때,

$$
Ly=f
$$

미분연산자가 self-adjoint 하면, 아래와 같이 eigen-expansion 을 수행할 수 있다.

$$
y=\sum_{n=1}^{\infty}\frac{\left<\varphi_{n}|f\right>_{w}}{\lambda_{n}}\varphi_{n}
$$

$$
=\sum_{n=1}^{\infty}\int_{x_1}^{x_2}dx'\left\lbrack\frac{w\left(x'\right)f\left(x'\right)\varphi_{n}^{\ast}\left(x'\right)}{\lambda_{n}}\right\rbrack\varphi_{n}\left(x\right)
$$

$$
=\int_{x_1}^{x_2}dx'\left\lbrack\sum_{n=1}^{\infty}\frac{w\left(x'\right)\varphi_{n}^{\ast}\left(x'\right)\varphi_{n}\left(x\right)}{\lambda_{n}}f\left(x'\right)\right\rbrack
$$

$$
=\int_{x_1}^{x_2}dx'\left\lbrack G\left(x,x'\right)f\left(x'\right)\right\rbrack
$$

따라서,

$$
G\left(x,x'\right)=\sum_{n=1}^{\infty}\frac{w\left(x'\right)\varphi_{n}^{\ast}\left(x'\right)\varphi_{n}\left(x\right)}{\lambda_{n}}
$$

ℹ️ **미분방정식이 self-adjoint 라면, 그린함수를 사용하여 구한 특수해는 전체해와 동일하다.**

만약, self-adjoint 하지 않다라면, 특수해를 구하기 위한 조건을 self-adjoint로 만들고, 일반해는 따로 구한다.

---

실제적으로는 이전 챕터에서 사용하는 방식을 사용한다. 위와 같은 표현법은 무한합을 포함하기 때문에, 계산이 복잡하다. **이번 챕터에서의 중요한 사실은, 그린함수는
- 변수 분리가 가능
- 교환법칙이 가능
- self -adjoint인 경우, 그린함수 풀이법이 전체 해

$$
G\left(x,x'\right)=g_1\left(x\right)g_2\left(x'\right)
$$

$$
G\left(x,x'\right)=G\left(x',x\right)
$$

---

[Green's function for Sturm-Liouville problems](https://www.youtube.com/watch?v=8l4VsNSX_kw)

[Green's functions | Advanced Linear Algebra](https://faculty.washington.edu/kutz/am568/page/page-4/)

[sl_green.pdf](sl_green.pdf)