+++
title = "(b) Gradient for scalar"
weight = 5
+++

---

### 1. Gradient의 의미

등위선 또는 등위면에서 법선(수직) 뱡향의 기울기 이다.

---

### 2. Gradient for scalar 

**매개변수 공간 -> 실공간 직교좌표계**

$$
\nabla_u
:=\hat{u}^j\frac{\partial}{\partial u^j} \implies
\nabla
:=\vec{h}^j\frac{\partial}{\partial u^j}
$$

- 데카르트좌표계: $h_1=1, h_2=1, h_3=1$
- 원통좌표계: $h_1=1, h_2=\rho, h_3=1$
- 구좌표계: $h_1=1, h_2=r, h_3=r\sin\theta$

**(2) 실공간 직교좌표계**

$$
\nabla
:=\hat{e}_j\frac{\partial}{h_j\partial u^j}
$$

proof)

- 일반적으로, suffix가 동일한 공변가저와 반변기저의 내적은 1이다.
- 직교좌표계에서, 공변기저와 반변기저의 방향은 동일하다.

$$
\vec{h}^j
=h^j\hat{e}^j
=h^j\hat{e}_j
,\quad
h_jh^j
=1
$$

따라서,

$$
\vec{h}^j
=\hat{e}_j\frac{1}{h_j}
$$

위 식을 일반식에 대입하면,

$$
\nabla
:=\vec{h}^j\frac{\partial}{\partial u^j}
=\vec{e}_j\frac{\partial}{h_j\partial u^j}
$$

---

[Gradient - 위키백과, 우리 모두의 백과사전](https://en.wikipedia.org/wiki/Gradient)