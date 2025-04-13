+++
title = "(b) Wave equation for free-space"
weight = 1
+++

---

### 1. free-space 의 수학적 기술

자유 공간은 수학적으로 다음과 같이 모델링할 수 있다.

- **무한 공간:** 3차원 유클리드 공간 전체를 자유 공간으로 간주한다.
- **경계 조건:** 경계면이 없으므로 경계 조건은 필요하지 않다.
- **무한 부피:** 자유 공간 전체의 부피는 무한대이다.
- **(물리학에 적용) 에너지 보존 법칙: 에너지는 유한하다. 가상의 무한대 경계면에서 값은 0 이다.**

---

### 2. 자유공간에서, wave equation 은 self-adjoint 하다.

$$
\nabla^2u\left(\vec{r},t\right)=\frac{1}{v^2}\frac{\partial^2}{\partial t^2}u\left(\vec{r},t\right)
$$

**proof1)**

$$L:=\nabla^2-\frac{1}{v^2}\frac{\partial^2}{\partial t^2}$$

임의의 함수 f와 g에 대하여, 아래임을 보이면 된다.

$$\langle g|Lf \rangle=\langle Lg|f \rangle$$

(1) 오른쪽 항

$$
\langle g|Lf \rangle=\int_{V}d^3V\left\lbrack g^{\ast}\left\lbrace\nabla^2f-\frac{1}{v^2}\frac{\partial^2}{\partial t^2}f\right\rbrace\right\rbrack
$$

$$
=\int_{V}d^3V\left\lbrack\nabla\cdot\left(g^{\ast}\nabla f\right)-\nabla g^{\ast}\cdot\nabla f - g^{\ast}\cdot\frac{1}{v^2}\frac{\partial^2}{\partial t^2} f \right\rbrack
$$

$$
=\int_{s}d^2\vec{s}\cdot\left\lbrack g^{\ast}\cdot\nabla f\right\rbrack-\int_{V}d^3V\left\lbrack\nabla g^{\ast}\cdot\nabla f+g^{\ast}\cdot\frac{1}{v^2}\frac{\partial^2}{\partial t^2}f\right\rbrack
$$

$$
=-\int_{V}d^3V\left\lbrack\nabla g^{\ast}\cdot\nabla f+g^{\ast}\cdot\frac{1}{v^2}\frac{\partial^2}{\partial t^2}f\right\rbrack
$$

(2) 왼쪽 항

$$
\langle Lg|f\rangle=-\int_{V}d^3V\left\lbrack\nabla g^{\ast}\cdot\nabla f+g^{\ast}\cdot\frac{1}{v^2}\frac{\partial^2}{\partial t^2}f\right\rbrack
$$

**proof2)**

전자기파는 에너지 보존 법칙을 만족해야 한다. 위의 파동방정식으로부터, 슈뢰딩거 방정식을 유도할 수 있으며, 따라서, self-adjoint 해야 한다.