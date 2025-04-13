+++
title = "(i) Self-adjoint for SL"
weight = 3
+++

---

### 1. self-adjoint 를 만족하는 스텀-리우빌 연산자

아래와 같은 연산자와 미분 방정식이 있다.

$$
L=-\frac{1}{w\left(x\right)}\left\lbrack D\left(p\left(x\right)D\right)+q\left(x\right)\right\rbrack 
$$

$$
Lu=f
$$

위 선형 미분연산자의 해는 아래와 같다.

$$
u=\sum_{n}c_{n}\varphi_{n}
$$

**다음과 같은 boundary condition을 만족하면,** **위 미분 연산자는 self-adjoint 하다.**

$$
a_1u\left(x_1\right)+a_2u'\left(x_1\right)=0,\quad a_1^2+a_2^2\ne0 
$$

$$
b_1u\left(x_2\right)+b_2u'\left(x_2\right)=0,\quad b_1^2+b_2^2\ne0
$$

또는, 주기적 경계조건 일 경우, self-adjoint 하다.

$$
u\left(x_1\right)=u\left(x_2\right) 
$$

$$
u'\left(x_1\right)=_{}u'\left(x_2\right)
$$

ℹ️ 여기서 주의해야 할 사항은,

스텀-리우빌 경계 조건은 **특정 종류의 2계 미분 연산자가 Hermitian임을 보장하는 데 사용되는 조건**이다. **하지만 모든 Hermitian 연산자가 스텀-리우빌 경계 조건을 만족해야 하는 것은 아니다.** 스텀-리우빌 경계 조건은 2계 미분 연산자가 self-adjoint임을 보장하는 **충분 조건이지만, 필요 조건은 아니다**. 즉, 스텀-리우빌 경계 조건을 만족하지 않더라도 self-adjoint한 2계 미분 연산자가 존재할 수 있다. 관련 내용은 [(r) Singular Sturm-Liouville](r_Singular_Sturm_Liouville.md) 를 참조한다.

---

### 2. 증명 과정

아래와 같이 만족시키면, self-adjoint 하다.

$$
\langle\varphi_{m}|L\varphi_{n}\rangle_{w}=\langle L\varphi_{m}|\varphi_{n}\rangle_{w}
$$

both 항에 대한 차이는 아래와 같이 쓸 수 있다.

$$
\langle\varphi_{m}|L\varphi_{n}\rangle_{w}-\langle L\varphi_{m}|\varphi_{n}\rangle_{w}=\left\lbrack p\left(x\right)W\left(\varphi_{m}^{\ast},\varphi_{n}\right)\right\rbrack_{x_1}^{x_2}
$$

{{< details summary="proof" >}}

(1)

$$
\langle\varphi_{m}|L\varphi_{n}\rangle _{w}=\int_{x_1}^{x_2}dx\left\lbrack\varphi_{m}^{\ast}\cdot\left\lbrack D\left(p\left(x\right)D\right)+q \left(x\right) \right\rbrack \varphi_{n} \right\rbrack
$$

$$
=\int_{x_1}^{x_2}dx \left\lbrack\varphi_{m}^{\ast} \cdot \left \lbrack D \left(p\left(x\right)D\right) \right\rbrack \varphi_{n}\right\rbrack + \int_{x_1}^{x_2}dx \left\lbrack q\left(x\right)\varphi_{m}^{\ast} \varphi_{n} \right\rbrack
$$

(2)

$$
\langle L\varphi_{m}|\varphi_{n}\rangle _{w}=\int_{x_1}^{x_2}dx\left\lbrack\varphi_{n}\cdot\left\lbrack D\left(p\left(x\right)D\right)+q\left(x\right)\right\rbrack\varphi_{m}^{\ast}\right\rbrack 
$$

$$
=\int_{x_1}^{x_2}dx\left\lbrack\varphi_{n}\cdot\left\lbrack D\left(p\left(x\right)D\right)\right\rbrack\varphi_{m}^{\ast}\right\rbrack+\int_{x_1}^{x_2}dx\left\lbrack q\left(x\right)\varphi_{m}^{\ast}\varphi_{n}\right\rbrack
$$

따라서, 아래를 보이면 된다.

$$
\int_{x_1}^{x_2}dx\left\lbrack\varphi_{m}^{\ast}\cdot\left\lbrack D\left(p\left(x\right)D\right)\right\rbrack\varphi_{n}\right\rbrack=\int_{x_1}^{x_2}dx\left\lbrack\varphi_{n}\cdot\left\lbrack D\left(p\left(x\right)D\right)\right\rbrack\varphi_{m}^{\ast}\right\rbrack
$$

위 식의 오른쪽 항과 왼쪽 항은 각각 다음과 같다.

$$
\int_{x_1}^{x_2}dx\left\lbrack\varphi_{m}^{\ast}\cdot\left\lbrack D\left(p\left(x\right)D\right)\right\rbrack\varphi_{n}\right\rbrack=\left\lbrack p\left(x\right)\varphi_{m}^{\ast}\varphi_{n}'\right\rbrack_{x_1}^{x_2}-\int_{x_1}^{x_2}dx\left\lbrack p\left(x\right)\varphi_{m}'^{\ast}\varphi_{n}'\right\rbrack 
$$

$$
=\int_{x_1}^{x_2}dx\left\lbrack\varphi_{m}^{\ast}\cdot\left\lbrack D\left(p\left(x\right)D\right)\right\rbrack\varphi_{n}\right\rbrack+\int_{x_1}^{x_2}dx\left\lbrack q\left(x\right)\varphi_{m}^{\ast}\varphi_{n}\right\rbrack
$$

따라서, 아래를 보이면 된다.

$$
\left\lbrack p\left(x\right)\varphi_{m}^{\ast}\varphi_{n}'\right\rbrack_{x_1}^{x_2}=\left\lbrack p\left(x\right)\varphi_{n}\varphi_{m}^{\ast\prime}\right\rbrack_{x_1}^{x_2}
$$

{{< /details >}}

---

### 2. boundary condition 적용

$$
a_1u\left(x_1\right)+a_2u'\left(x_1\right)=0,\quad a_1^2+a_2^2\ne0 
$$

$$
b_1u\left(x_2\right)+b_2u'\left(x_2\right)=0,\quad b_1^2+b_2^2\ne0
$$

또한, 해는 eigen-decomposition으로 표현할 수 있다. 적합한 해를 표현하기 위해서는, summation 의 계수는 모두 0이 될 수 없다.

- **Dirichlet BC**

eigenfunction 은 선형 독립이므로,

$$
a_2=b_2=0\implies u\left(x_1\right)=u^{}\left(x_2\right)=0\implies\varphi_{n,m}\left(x_1\right)=\varphi_{n,m}\left(x_2\right)=0
$$

계수 c$_{n}$은 0이 아니어야 하므로,

$$
\varphi_{n}\left(x_1\right)=\varphi_{n}\left(x_2\right)=0
$$

따라서, 아래식은 성립한다.

$$
\left\lbrack p\left(x\right)W\left(\varphi_{m}^{\ast},\varphi_{n}\right)\right\rbrack_{x_1}^{x_2}=0
$$

- **Neumann BC**

eigenfunction 은 선형 독립이므로,

$$
a_1=b_1=0\implies u'\left(x_1\right)=u'\left(x_2\right)=0\implies\varphi_{n,m}'\left(x_1\right)=\varphi_{n,m}'\left(x_2\right)=0
$$

따라서, 아래식은 성립한다.

$$
\left\lbrack p\left(x\right)W\left(\varphi_{m}^{\ast},\varphi_{n}\right)\right\rbrack_{x_1}^{x_2}=0
$$

- **Periodic BC**

eigenfunction 은 선형 독립이므로,

$$
u\left(x_1\right)=u\left(x_2\right)\implies\varphi_{n,m}\left(x_1\right)=\varphi_{n,m}\left(x_2\right) 
$$

$$
u'\left(x_1\right)=_{}u'\left(x_2\right)\implies\varphi_{n,m}'\left(x_1\right)=\varphi_{n,m}'\left(x_2\right)
$$

따라서, 아래식은 성립한다.

$$
\left\lbrack p\left(x\right)W\left(\varphi_{m}^{\ast},\varphi_{n}\right)\right\rbrack_{x_1}^{x_2}=0
$$

---

[ordinary differential equations - Why boundary conditions in Sturm-Liouville problem are homogeneous? - Mathematics Stack Exchange](https://math.stackexchange.com/questions/2605619/why-boundary-conditions-in-sturm-liouville-problem-are-homogeneous)