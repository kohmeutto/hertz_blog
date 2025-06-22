+++
title = "(b) Gradient for scalar"
weight = 5
+++

---

### 1. Gradient의 의미

등위선 또는 등위면에서 법선(수직) 뱡향의 기울기 이다.

---

### 2. Gradient for scalar 

**매개변수 공간 → 실공간 직교좌표계**

$$
\nabla_u
:=\hat{u}_j\frac{\partial}{\partial u_j} \implies
\nabla
:=\hat{e}_j\frac{\partial}{h_j\partial u_j}
$$

- 데카르트좌표계:

$$\hat{u}_1=\hat{u}_x, \hat{u}_2=\hat{u}_y, \hat{u}_3=\hat{u}_z$$

$$h_1=1, h_2=1, h_3=1$$

$$\hat{e}_1=\hat{x}, \hat{e}_2=\hat{y}, \hat{e}_3=\hat{z}$$

- 원통좌표계:

$$\hat{u}_1=\hat{u}_\rho, \hat{u}_2=\hat{u}_\phi, \hat{u}_3=\hat{u}_z$$

$$h_1=1, h_2=\rho, h_3=1$$

$$\hat{e}_1=\hat{\rho}, \hat{e}_2=\hat{\phi}, \hat{e}_3=\hat{z}$$

- 구좌표계:

$$\hat{u}_1=\hat{u}_r, \hat{u}_2=\hat{u}_\theta, \hat{u}_3=\hat{u}_\phi$$

$$h_1=1, h_2=r, h_3=r\sin\theta$$

$$\hat{e}_1=\hat{r}, \hat{e}_2=\hat{\theta}, \hat{e}_3=\hat{\phi}$$

---

[Gradient - 위키백과, 우리 모두의 백과사전](https://en.wikipedia.org/wiki/Gradient)