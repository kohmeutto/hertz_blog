+++
title = "(a) Material derivative"
weight = 3
+++

---

입자(물체)를 추적하면서 물리량을 구한다고 하자.**입자를 추적**하기에 오일리안 관점은 적합하지 않다. 결국, 라그랑지안 관점이 되어야 하는 것이다.

---

### 1. 라그랑지안 관점을 유지하면서, 오일리안 기술법으로 해석

![](image1.png)

<br>

- 벡터장 해석에서, 오일리안 기술법을 사용하여 표현되고 해석될 때, 계산적으로 더 효율적이이다.
- 그러나, **관측 대상(입자 또는 물체)이 정해져 있는 경우**, 해석은 라그랑지안 관점이 적합하다.
- 입자의 ‘진정한’ 변화율(라그랑지안 관점의 개념)을, 우리가 계산적으로 다루기 쉬운 오일러 기술법의 변수들을 사용하여 표현하는 방법이 필요하다. 이것이 바로 물질 미분을 통해 이루어진다.

$$
\vec{F}\left(\vec{r_0},t\right)\implies\vec{F}\left(M\left(\vec{r_0},t\right),t\right)
$$

$$
\frac{d}{dt}\vec{F}\left(\vec{r_0},t\right)\implies\frac{d}{dt}\vec{F}\left(M\left(\vec{r_0},t\right),t\right)
$$

---

### 2. 어떠한 속도를 가지고 움직이는 입자는 세상을 달리 본다.

- **고정된 지점에서의 변화**: 설령 입자가 움직이지 않고 특정 지점에 가만히 있었다고 가정해 보자. 이 지점의 온도가 시간 t에 따라 변할 수 있다 (예: 난방이 켜지면서 방의 온도가 점차 올라감). 입자가 이 지점에 머물렀다면, 시간이 지남에 따라 온도가 변하는 것을 느꼈을 것이다. 이것이 오일리안 관점에서 ∂T/∂t로 표현되는 국소 미분이다. 입자는 움직이면서도, '시간의 흐름'을 겪기 때문에 이 변화를 여전히 경험한다.
- **움직여서 변화**: 입자가 움직이면서 온도가 다른 공간의 다른 지점으로 이동하기 때문에 온도가 변한다. 예를 들어, 차가운 공기가 난로 쪽으로 이동하면 공기의 온도가 올라간다. 이때 공기 흐름 자체가 안정적이어서 난로 주변 공간의 온도는 시간에 따라 변하지 않는다고 해도 (즉, ∂T/∂t =0), 공기 입자는 이동하면서 더 높은 온도의 지역으로 들어가기 때문에 온도가 상승하는 것을 느낀다. 이것이 오일리안 관점에서 (v⋅∇)T로 표현되는 대류 미분이다. 입자는 움직이기 때문에, 이 '공간을 이동하며 겪는 변화'를 직접적으로 경험하게 된다.

---

### 3. 물질 미분

- 물체가 이동하므로, **시간에 따른 변화(국소 변화)** 와 **공간 이동에 따른 변화(대류 변화)** 를 동시에 겪는다. 따라서, 입자가 실제로 경험하는 전체 변화율을 나타내기 위해 단순히 시간에 대한 편미분(∂/∂t)이 아닌, 총 변화율을 나타내는 **물질 미분(d/dt)** 이 필요하다.

$$
d\vec{F}=dt\frac{\partial\vec{F}}{\partial t}+dx_{i}\frac{\partial\vec{F}}{\partial x_{i}}
$$

$$
\frac{d\vec{F}}{dt}=\left(\frac{\partial}{\partial t}+\frac{dx_{i}}{dt}\frac{\partial}{\partial x_{i}}\right)\vec{F}=\left(\frac{\partial}{\partial t}+v_{i}\frac{\partial}{\partial x_{i}}\right)\vec{F}
$$

$$
\displaystyle\frac{d}{dt}=\frac{\partial}{\partial t}+\vec{v}\cdot\nabla
$$

---

[Eulerian and Lagrangian Descriptions in Fluid Mechanics](https://www.youtube.com/watch?v=mdN8OOkx2ko)