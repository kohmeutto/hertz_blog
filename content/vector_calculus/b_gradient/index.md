+++
title = "(b) Gradient"
weight = 3
+++

---

### 0.  Total derivative & Gradient

다변수 함수에 대한 전미분은 아래와 같다. 여기에서, 매개변수를 $u^i$ 라고 하자.

$$
df
=du^i\frac{\partial f}{\partial u^i}
$$

위 식을 벡터로 표현하면, 아래와 같다.

$$
df
=d\vec{u}\cdot\nabla_u f
$$

$$
\nabla_u
=\left[\frac{\partial}{\partial u^1}, \frac{\partial}{\partial u^2}, \frac{\partial}{\partial u^3}\right]^T
$$

여기에서 $f$ 를 제거하면, 유용한 관계식을 얻을 수 있다. (수학적으로 엄밀한 연산자 정의라기보다는, 전미분 연산자를 간략하게 표현하는 매우 유용한 방법이다.)

$$
d:=d\vec{u}\cdot\nabla_u
$$

---

### 1. Gradient for scalar

 
우선, 매개변수 공간($u^1,u^2,u^3$)은 실 공간 $v^1(u^1,u^2,u^3),v^2(u^1,u^2,u^3),v^3(u^1,u^2,u^3)$ 에 대응된다. 따라서, 스칼라 $f$는 다음과 같이 표현될 수 있다.

$$
f(u^2,u^2,u^3)=f(v^1(u^1,u^2,u^3),v^2(u^1,u^2,u^3),v^3(u^1,u^2,u^3))
$$

매개변수 공간과, 실공간에서 gradient는 아래와 같이 표현된다.

$$
\nabla_u f
=\left[\frac{\partial f}{\partial u^1}, \frac{\partial f}{\partial u^2}, \frac{\partial f}{\partial u^3}\right]^T
,\quad
\nabla_v f
=\left[\frac{\partial f}{\partial v^1}, \frac{\partial f}{\partial v^2}, \frac{\partial f}{\partial v^3}\right]^T
$$

단, **위와 달리**, 각 공간에서의 gradient 가 동일하지 않음을 주의하라.

$$
\nabla_u f \ne \nabla_v f
$$

이제 일반적으로, 임의의 공간 $q$ 에서, gradient가 무엇인지 살펴보자.

---

### 2. Gradient for vector

$$
\vec{c}=\vec{a}+\vec{b}
\rightarrow
c_i=a_i+b_i
$$

The suffix i is called a 'free suffix'. The choice of this free suffix is arbitrary, so the equation could equally well be written $c_j=a_j+b_j$ or $c_k=a_k+b_k$.

---
