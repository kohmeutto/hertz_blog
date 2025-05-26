+++
title = "(b) Wave equation for free-space"
weight = 1
+++

---

### 1. free-space 의 수학적 기술

자유 공간은 수학적으로 다음과 같이 모델링할 수 있다.

- **무한 공간:** 3차원 유클리드 공간 전체를 자유 공간으로 간주한다.
- **무한 부피:** 자유 공간 전체의 부피는 무한대이다.
- **(물리학에 적용) 에너지 개념:** 자유 공간 전체에 걸친 파동의 총 에너지는 무한대일 수 있다 (예: 평면파). 하지만 에너지 밀도는 유한하며, 유한한 영역에 국한된 소스가 방출하는 총 에너지는 유한하다.

---

### 2. 자유공간에서, wave equation 의 self-adjoint 여부

**자유공간에서 wave equation 이 self-adjoint 하기 위해서는, 무한대 경계면에서 0**이어야 한다.

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

---

### 3. 자유공간에서, wave equation 해의 유일성

자유공간이라는 조건이 (물리학적으로 수렴), wave equation 해의 유일성을 보장하는 것은 아니다. 자유공간에서, 해의 유일성을 보장하기 위해서는 대표적으로 아래의 조건을 만족해야 한다.

- 초기 조건이 주어져야 함. 즉, 해의 모양을 결정
- Inhomogeneous 미분방정식 (소스항이 있어야 함) + 파동의 진행방향이 외향파(방사조건) 이여야 한다.