+++
title = "(b) Tensor components transformation II"
weight = 7
+++

---

**중요사항: 동일 [실 공간]** 에 대한 것으로 **텐서 성분 변환** 을 다룬다. 여기서의 텐서는 벡터이며, 국소벡터를 의미한다.

---

### 0. 정리

<img src="image1.png" width="40%" height="auto">

- **데카르트 → 원통, 원통 → 구**

$$
M_{CD}=\left[\begin{matrix}
    \cos\phi & \sin\phi & 0 \\
    -\sin\phi & \cos\phi & 0 \\
    0 & 0 & 1
\end{matrix}\right], \quad 
M_{CS}=\left[\begin{matrix}
    \sin\theta & 0 & \cos\theta \\
    \cos\theta & 0 & -\sin\theta \\
    0 & 1 & 0
\end{matrix}\right]
$$

- **원통 → 데카르트, 구 → 원통**

$$
M_{DC}=\left[\begin{matrix}
    \cos\phi & -\sin\phi & 0 \\
    \sin\phi & \cos\phi & 0 \\
    0 & 0 & 1
\end{matrix}\right],\quad
M_{CS}=\left[\begin{matrix}
    \sin\theta & \cos\theta & 0 \\
    0 & 0 & 1 \\
    \cos\theta & -\sin\theta & 0
\end{matrix}\right]
$$

---

### 1. 데카르트 좌표계 ↔︎ 원통 좌표계

<img src="image2.png" width="60%" height="auto">

- 데카르트 좌표계 기준에서, 데카르트 좌표계의 국소 벡터 표현

$$
u_1\left[\begin{matrix}
    1 \\ 0 \\ 0
\end{matrix}\right]
+u_2\left[\begin{matrix}
    0 \\ 1 \\ 0
\end{matrix}\right]
+u_3\left[\begin{matrix}
    0 \\ 0 \\ 1
\end{matrix}\right]
=\left[\begin{matrix}
    1 & 0 & 0 \\
    0 & 1 & 0 \\
    0 & 0 & 1
\end{matrix}\right]
\left[\begin{matrix}
    u_1 \\ u_2 \\ u_3
\end{matrix}\right]
$$

- 데카르트 좌표계 기준에서, 원통 좌표계의 국소 벡터 표현

$$
v_1\left[\begin{matrix}
    \cos\phi \\ \sin\phi \\ 0
\end{matrix}\right]
+v_2\left[\begin{matrix}
    -\sin\phi \\ \cos\phi \\ 0
\end{matrix}\right]
+v_3\left[\begin{matrix}
    0\\ 0\\ 1
\end{matrix}\right]
=\left[\begin{matrix}
    \cos\phi & -\sin\phi & 0 \\
    \sin\phi & \cos\phi & 0 \\
    0 & 0 & 1
\end{matrix}\right]
\left[\begin{matrix}
    v_1 \\ v_2 \\ v_3
\end{matrix}\right]
$$

국소 벡터는 텐서 이므로, 좌표계에 상관없이 동일해야 한다.

$$
\left[\begin{matrix}
    u_1 \\ u_2 \\ u_3
\end{matrix}\right]
=\left[\begin{matrix}
    \cos\phi & -\sin\phi & 0 \\
    \sin\phi & \cos\phi & 0 \\
    0 & 0 & 1
\end{matrix}\right]
\left[\begin{matrix}
    v_1 \\ v_2 \\ v_3
\end{matrix}\right]
$$

또한, **위의 행렬은 회전변환 행렬이므로, 유니타리 연산자** 이다. 따라서, 역행렬은 전치행렬과 같다.

$$
\left[\begin{matrix}
    v_1 \\ v_2 \\ v_3
\end{matrix}\right]
=\left[\begin{matrix}
    \cos\phi & \sin\phi & 0 \\
    -\sin\phi & \cos\phi & 0 \\
    0 & 0 & 1
\end{matrix}\right]
\left[\begin{matrix}
    u_1 \\ u_2 \\ u_3
\end{matrix}\right]
$$

---

### 2. 원통 좌표계 ↔︎ 구 좌표계

<img src="image3.png" width="35%" height="auto">

- 원통 좌표계 기준에서, 원통 좌표계의 국소 벡터 표현

$$
u_1\left[\begin{matrix}
    1 \\ 0\\ 0
\end{matrix}\right]
+u_2\left[\begin{matrix}
    0 \\ 1 \\ 0
\end{matrix}\right]
+u_3\left[\begin{matrix}
    0 \\ 0 \\ 1
\end{matrix}\right]
=\left[\begin{matrix}
    1 & 0 & 0 \\
    0 & 1 & 0 \\
    0 & 0 & 1
\end{matrix}\right]
\left[\begin{matrix}
    u_1 \\ u_2 \\ u_3
\end{matrix}\right]
$$

- 원통 좌표계 기준에서, 구 좌표계의 국소 벡터 표현

$$
v_1\left[\begin{matrix}
    \sin\theta \\ 0 \\ \cos\theta
\end{matrix}\right]
+v_2\left[\begin{matrix}
    \cos\theta \\ 0 \\ -\sin\theta
\end{matrix}\right]
+v_3\left[\begin{matrix}
    0 \\ 1 \\ 0
\end{matrix}\right]
=\left[\begin{matrix}
    \sin\theta & \cos\theta & 0 \\
    0 & 0 & 1 \\
    \cos\theta & -\sin\theta & 0
\end{matrix}\right]
\left[\begin{matrix}
    v_1 \\ v_2 \\ v_3
\end{matrix}\right]
$$

국소 벡터는 텐서 이므로, 좌표계에 상관없이 동일해야 한다.

$$
\left[\begin{matrix}
    u_1 \\ u_2 \\ u_3
\end{matrix}\right]
=\left[\begin{matrix}
    \sin\theta & \cos\theta & 0 \\
    0 & 0 & 1 \\
    \cos\theta & -\sin\theta & 0
\end{matrix}\right]
\left[\begin{matrix}
    v_1 \\ v_2 \\ v_3
\end{matrix}\right]
$$

또한, **위의 행렬은 회전변환 행렬이므로, 유니타리 연산자** 이다. 따라서, 역행렬은 전치행렬과 같다.

$$
\left[\begin{matrix}
    v_1 \\ v_2 \\ v_3
\end{matrix}\right]
=\left[\begin{matrix}
    \sin\theta & 0 & \cos\theta \\
    \cos\theta & 0 & -\sin\theta \\
    0 & 1 & 0
\end{matrix}\right]
\left[\begin{matrix}
    u_1 \\ u_2 \\ u_3
\end{matrix}\right]
$$

---

### 3. 데카르트 좌표계(D) → 구좌표계(S)

데카르트 좌표계에서 구좌표계로의 **좌표 변환 행렬** $M_{SD}$ 는

$$
M_{SD}=M_{SC}M_{CD}
$$

$$
M_{SD}=\left[\begin{matrix}
    \sin\theta & 0 & \cos\theta \\
    \cos\theta & 0 & -\sin\theta \\
    0 & 1 & 0
\end{matrix}\right]
\left[\begin{matrix}
    \cos\phi & \sin\phi & 0 \\
    -\sin\phi & \cos\phi & 0 \\
    0 & 0 & 1
\end{matrix}\right]
$$

구좌표계에서 데카르트 좌표계로의 **좌표 변환 행렬** $M_{DS}$ 는

$$
M_{DS}=M_{DC}M_{CS}
$$

$$
M_{DS}=\left[\begin{matrix}
    \sin\theta & \cos\theta & 0 \\
    0 & 0 & 1 \\
    \cos\theta & -\sin\theta & 0
\end{matrix}\right]
\left[\begin{matrix}
    \cos\phi & -\sin\phi & 0 \\
    \sin\phi & \cos\phi & 0 \\
    0 & 0 & 1
\end{matrix}\right]
$$


---

**example1)**

Express vector $\vec{A}=\hat{x}\left(x+y\right)+\hat{y}\left(y-x\right)+\hat{z}z$ in spherical coordinates.

{{< details summary="sol" >}}
    
$$
M_{SD}=\left[\begin{matrix}
    \sin\theta & 0 & \cos\theta \\
    \cos\theta & 0 & -\sin\theta \\
    0 & 1 & 0
\end{matrix}\right]
\left[\begin{matrix}
    \cos\phi & \sin\phi & 0 \\
    -\sin\phi & \cos\phi & 0 \\
    0 & 0 & 1
\end{matrix}\right]
=\left[\begin{matrix}
    \sin\theta\cos\phi & \sin\theta\sin\phi & \cos\theta \\
    \cos\theta\cos\phi & \cos\theta\sin\phi & -\sin\theta \\
    -\sin\phi & \cos\phi & 0
\end{matrix}\right]
$$

좌표변환을 수행한다.

$$
\left[\begin{matrix}
    A_{R} \\ A_{\theta} \\ A_{\phi}
\end{matrix}\right]
=\left[\begin{matrix}
    \sin\theta\cos\phi & \sin\theta\sin\phi & \cos\theta \\
    \cos\theta\cos\phi & \cos\theta\sin\phi & -\sin\theta \\
    -\sin\phi & \cos\phi & 0
\end{matrix}\right]
\left[\begin{matrix}
    x+y \\ y-x \\ z
\end{matrix}\right]
$$

$$
=\left[\begin{matrix}
    \left(x+y\right)\sin\theta\cos\phi+\left(y-x\right)\sin\theta\sin\phi+z\cos\theta \\
    \left(x+y\right)\cos\theta\cos\phi+\left(y-x\right)\cos\theta\sin\phi-z\sin\theta \\
    -\left(x+y\right)\sin\phi+\left(y-x\right)\cos\phi
\end{matrix}\right]
$$
    
x,y,z 는 아래와 같다.
    
$$
x=r\sin\theta\cos\phi
$$
    
$$
y=r\sin\theta\sin\phi
$$
    
$$
z=r\cos\theta
$$

대입하면,

$$
\left[\begin{matrix}
    A_{R} \\ A_{\theta} \\ A_{\phi}
\end{matrix}\right]
=\left[\begin{matrix}
    R \\ 0 \\ r\sin\theta
\end{matrix}\right]
$$

{{< /details >}}

---