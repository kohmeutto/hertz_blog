+++
title = "(a) Parameter space transformation III - Jacobian"
weight = 5
+++

---

**중요사항: [매개변수 공간] → [실 공간]** 에 대한 것으로 **미소변위벡터변환**을 다룬다.

---

### 1. Jacobian

Jacobian은 매개변수 공간의 미소변위벡터를 실 공간의 미소변위벡터로 변환하는 연산자이다.

- **u 매개변수 공간**

$$
d\vec{u}=\left[\begin{matrix}
    du_1 \\ du_2 \\ du_3
\end{matrix}\right]
=\hat{u}_1du_1+\hat{u}_2du_2+\hat{u}_3du_3
$$

- **v 실 공간**

$$
d\vec{v}=\left[\begin{matrix}
    dv_1 \\ dv_2 \\ dv_3
\end{matrix}\right]
=\hat{v}_1dv_1+\hat{v}_2dv_2+\hat{v}_3dv_3
$$

- **변환 연산자 작용, [u 매개변수 공간] 미소변화량벡터 du → [v 좌표계 공간] 미소변위벡터 dv**

$$
d\vec{v}=d\vec{u}\cdot\nabla_{u}\vec{v}
$$

$$
=du_1\frac{\partial\vec{v}}{\partial u_1}+du_2\frac{\partial\vec{v}}{\partial u_2}+du_3\frac{\partial\vec{v}}{\partial u_3}
$$

수학적 벡터로 표현하면,

$$
\left[\begin{matrix}
    dv_1 \\ dv_2 \\ dv_3
\end{matrix}\right]
=du_1\left[\begin{matrix}
    \cfrac{\partial v_1}{\partial u_1} \\
    \cfrac{\partial v_2}{\partial u_1} \\
    \cfrac{\partial v_3}{\partial u_1}
\end{matrix}\right]+du_2
\left[\begin{matrix}
    \cfrac{\partial v_1}{\partial u_2} \\
    \cfrac{\partial v_2}{\partial u_2} \\
    \cfrac{\partial v_3}{\partial u_2}
\end{matrix}\right]+du_3
\left[\begin{matrix}
    \cfrac{\partial v_1}{\partial u_3} \\
    \cfrac{\partial v_2}{\partial u_3} \\
    \cfrac{\partial v_3}{\partial u_3}
\end{matrix}\right]
$$

$$
=\begin{bmatrix}
    \cfrac{\partial v_1}{\partial u_1} & \cfrac{\partial v_1}{\partial u_2} & \cfrac{\partial v_1}{\partial u_3} \\
    \cfrac{\partial v_2}{\partial u_1} & \cfrac{\partial v_2}{\partial u_2} & \cfrac{\partial v_2}{\partial u_3} \\
    \cfrac{\partial v_3}{\partial u_1} & \cfrac{\partial v_3}{\partial u_2} & \cfrac{\partial v_3}{\partial u_3}
\end{bmatrix}
\begin{bmatrix}
    du_1 \\ du_2 \\ du_3
\end{bmatrix}
$$

여기에서, 3x3 행렬을 Jacobian 이라고 한다. **Jacobian의 각 열 벡터**는 매개변수 공간의 각 축이 실 공간으로 변환될 때 만들어지는 벡터이다. 이 벡터들이 해당 지점에서 실 공간의 새로운 기준 방향들(기저)을 형성한다.

---

### 2. Scale factor

$$
d\vec{v}=du_1\frac{\partial\vec{v}}{\partial u_1}+du_2\frac{\partial\vec{v}}{\partial u_2}+du_3\frac{\partial\vec{v}}{\partial u_3}
$$

**Jacobian 의 각 열벡터는 실 공간에 유도된 새로운 기저 벡터** 라고 하였다. 
위의 기저를 normalize 하고, 실 공간의 미소길이벡터 $d\vec{v}$ 를 표현해 보자.

$$
d\vec{v}=\hat{e}_1h_1du_1+\hat{e}_2h_2du_2+\hat{e}_3h_3du_3
$$

$$
\vec{h}_{j}=\frac{\partial\vec{v}}{\partial u_{j}},\quad
h_{j}=\left|\vec{h}_{j}\right|,\quad
\hat{e}_{j}=\frac{\vec{h}_{j}}{h_{j}}
$$

이전 챕터에서 학습한 바, scale factor $h_j$ 를 매개변수 공간 $u_j$ 방향의 미소 변화량에 곱하면, 실 공간에서의 미소 길이가 된다.

---

**example1) 원통좌표계 → 데카르트좌표계**

$$
\vec{v}=\hat{x}\rho\cos\phi+\hat{y}\rho\sin\phi+\hat{z}z
$$

$$
{{{{{{{{{{\displaystyle h_{\rho}=\left|\left|\partial_{\rho}v^{i}\vec{}\right|\right|=\left|\left|\left\lbrack\cos\phi,\sin\phi,0\right\rbrack\right|\right|=1}}}}}}}}}}
$$

$$
{{{{{{{\displaystyle h_{\phi}=\left|\left|\partial_{\phi}v^{i}\right|\right|=\left|\left|[-\rho\sin\phi,\rho\cos\phi,0]\right|\right|=\rho}}}}}}}
$$

$$
{{{{{{\displaystyle h_{z}=\left|\left|\partial_{z}v^{i}\right|\right|}}}}}}=1
$$

따라서,

$$
\begin{aligned}d\vec{v}=\left[\begin{matrix}\cos\phi\\ \sin\phi\\ 0\end{matrix}\right]\end{aligned}d\rho+\left[\begin{matrix}-\sin\phi\\ \cos\phi\\ 0\end{matrix}\right]\rho d\phi+\left[\begin{matrix}0\\ 0\\ 1\end{matrix}\right]dz
$$

$$
\begin{aligned}d\vec{v}=\hat{x}\left(\cos\phi d\rho-\rho\sin\phi d\phi\right)+\hat{y}\left(\sin\phi d\rho+\rho\cos\phi d\phi\right)+\hat{z}dz\end{aligned}
$$

여기에서, **회전 변환된 기저임을 알 수 있다.**

$$
\begin{aligned}\hat{e}_1=\hat{\rho}=\left[\begin{matrix}\cos\phi\\ \sin\phi\\ 0\end{matrix}\right]\end{aligned},\quad\hat{e}_2=\hat{\phi}=\left[\begin{matrix}-\sin\phi\\ \cos\phi\\ 0\end{matrix}\right],\quad\hat{e}_3=\hat{z}=\left[\begin{matrix}0\\ 0\\ 1\end{matrix}\right]
$$

$$
\begin{aligned}d\vec{v}=\hat{\rho}\end{aligned}d\rho+\hat{\phi}\rho d\phi+\hat{z}dz
$$

**정리하면,**

$$
\begin{aligned}d\vec{u}\xrightarrow{\text{Transformation:  }\cdot\nabla_{u}}\begin{aligned}d\vec{v}\end{aligned}\end{aligned}
$$

$$
\begin{aligned}d\vec{v}=\left[\begin{matrix}\cos\phi\\ \sin\phi\\ 0\end{matrix}\right]\end{aligned}d\rho+\left[\begin{matrix}-\sin\phi\\ \cos\phi\\ 0\end{matrix}\right]\rho d\phi+\left[\begin{matrix}0\\ 0\\ 1\end{matrix}\right]dz
$$

$$
\begin{aligned}=\hat{x}\left(\cos\phi d\rho-\rho\sin\phi d\phi\right)+\hat{y}\left(\sin\phi d\rho+\rho\cos\phi d\phi\right)+\hat{z}dz\end{aligned}
$$

$$
\begin{aligned}=\hat{\rho}\end{aligned}d\rho+\hat{\phi}\rho d\phi+\hat{z}dz
$$

---

**example2) 구좌표계->데카르트좌표계 @Seungmin Son** 

---

### **~~3. 미소 면적 보정 값~~**

[(b) Determinant](https://www.notion.so/b-Determinant-1cc8bc3f14068159baa1ebeb35504800?pvs=21)  ~~에 의해서,~~

- -uriencoded--\begin%7Baligned%7D미소넓이보정값=\det\left(\left[\begin%7Bmatrix%7D%7B%7B\displaystyle\frac%7B\partial r_1%7D%7B\partial u_1%7D%7D%7D & %7B%7B%7B\displaystyle\frac%7B\partial r_1%7D%7B\partial u_2%7D%7D%7D%7D\\ %7B%7B%7B\displaystyle\frac%7B\partial r_2%7D%7B\partial u_1%7D%7D%7D%7D & %7B%7B%7B\displaystyle\frac%7B\partial r_2%7D%7B\partial u_2%7D%7D%7D%7D\end%7Bmatrix%7D\right]\right)=\frac%7B\partial r_1%7D%7B\partial u_1%7D%7B\displaystyle\frac%7B\partial r_2%7D%7B\partial u_2%7D-\frac%7B\partial r_1%7D%7B\partial u_2%7D\frac%7B\partial r_2%7D%7B\partial u_1%7D%7D\end%7Baligned%7D

~~또한, 미소넓이보정값을 scale factor로 표현할 수 있다.~~

- -uriencoded--\begin%7Baligned%7D미소넓이보정값=h_1h_2 \, 또는 h_1h_3 \, 또는 \, h_2h_3 \end%7Baligned%7D

---

### **~~6. 미소 부피 보정 값~~**

[(b) Determinant](https://www.notion.so/b-Determinant-1cc8bc3f14068159baa1ebeb35504800?pvs=21)  ~~에 의해서,~~

- -uriencoded--\begin%7Baligned%7D미소부피보정값=\det\left(\begin%7Bbmatrix%7D%7B\displaystyle\frac%7B\partial r_1%7D%7B\partial u_1%7D%7D & %7B\displaystyle\frac%7B\partial r_1%7D%7B\partial u_2%7D%7D & %7B%7B\displaystyle\frac%7B\partial r_1%7D%7B\partial u_3%7D%7D%7D\\ %7B\displaystyle\frac%7B\partial r_2%7D%7B\partial u_1%7D%7D & %7B%7B\displaystyle\frac%7B\partial r_2%7D%7B\partial u_2%7D%7D%7D & %7B%7B\displaystyle\frac%7B\partial r_2%7D%7B\partial u_3%7D%7D%7D\\ %7B\displaystyle\frac%7B\partial r_3%7D%7B\partial u_1%7D%7D & %7B%7B\displaystyle\frac%7B\partial r_3%7D%7B\partial u_2%7D%7D%7D & %7B%7B\displaystyle\frac%7B\partial r_3%7D%7B\partial u_3%7D%7D%7D\end%7Bbmatrix%7D\right)\end%7Baligned%7D

~~또한, 부피보정값을 scale factor로 표현할 수 있다.~~

- -uriencoded--\begin%7Baligned%7D미소부피보정값=h_1h_2h_3\end%7Baligned%7D

---