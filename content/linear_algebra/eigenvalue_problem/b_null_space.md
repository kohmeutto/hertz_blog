+++
title = "(b) Null space"
weight = 1
+++

---

### 1. 영공간

행렬 $A$의 **영공간(Null Space)** 이란, 행렬 $A$와의 곱셈을 통해 0벡터가 되는 모든 벡터 $|v\rangle$ 들의 집합이다. 이는 $A|v\rangle=0$ 이라는 **제차 선형 방정식(Homogeneous Linear Equation)** 의 **해공간(Solution Space)** 과 같다.

$$
\text{Null}(\hat{A})
=\{|v\rangle, \hat{A}|v\rangle=0\}
$$

---
### 2. 영공간은 부분공간이다

영공간은 단순한 집합을 넘어, 그 자체로 벡터 공간의 조건을 만족하는 '부분 공간(subspace)'이다.

- **덧셈에 대한 닫힘**: $|v_1\rangle$과 $|v_2\rangle$가 영공간에 속하면, $\hat{A}(|v_1\rangle+|v_2\rangle) = \hat{A}|v_1\rangle+\hat{A}_2\rangle = 0+0=0$ 이므로, 그 합 $|v_1\rangle+|v_2\rangle$도 영공간에 속한다.
- **스칼라 곱에 대한 닫힘**: $|v\rangle$가 영공간에 속하고 $c$가 스칼라일 때, $\hat{A}(c|v\rangle) = c(\hat{A}|v\rangle) = c(0)=0$ 이므로, 그 스칼라 곱 $c|v\rangle$도 영공간에 속한다.

---

### 3. 물리적 의미

영공간은 어떤 연산자(변환)에 의해 '소멸(annihilate)'되거나 '무시'되는 상태들의 집합이다. 이는 시스템의 **평형 상태, 보존 법칙, 대칭성, 정보 손실** 등 근본적인 특성을 나타내는 매우 중요한 공간이다. 이 때문에 **소멸 공간(Annihilation Space)** 이라는 직관적인 이름으로도 이해할 수 있다.

---

**example1)** 1차원 영공간(직선), 행렬 A의 영공간을 구하시오.

$$
A
=\begin{bmatrix} 1 & 2 \\ 3 & 6 \end{bmatrix}
$$

{{< details summary="sol" >}}

sol)

$$
A\vec{v}=\vec{0}
$$
    
$$
\begin{bmatrix} 1 & 2 \\ 3 & 6 \end{bmatrix}
\begin{bmatrix} x \\ y \end{bmatrix}
=\begin{bmatrix} 0 \\ 0 \end{bmatrix}
$$

$$
\vec{v}
=\begin{bmatrix}
x \\ y
\end{bmatrix}
=\begin{bmatrix}
-2y \\ y
\end{bmatrix}
= y \begin{bmatrix} -2 \\ 1 \end{bmatrix}
$$

따라서, 영공간은

$$
\text{span}\left\{\begin{bmatrix} -2 \\ 1 \end{bmatrix}\right\}
$$

<hr>

{{< /details >}}

**example2)** 2차원 영공간 (평면), 행렬 B의 영공간을 구하시오.

$$
B
=\begin{bmatrix}
1 & 2 & 3 \\
0 & 0 & 0 \\
0 & 0 & 0
\end{bmatrix}
$$

{{< details summary="sol" >}}

$$
B\vec{v} = \vec{0}
$$

$$
\begin{bmatrix}
1 & 2 & 3 \\
0 & 0 & 0 \\
0 & 0 & 0
\end{bmatrix}
\begin{bmatrix} x \\ y \\ z \end{bmatrix}
=\begin{bmatrix} 0 \\ 0 \\ 0 \end{bmatrix}
$$

$$
\vec{v}
=\begin{bmatrix} -2y - 3z \\ y \\ z \end{bmatrix}
=y\begin{bmatrix} -2 \\ 1 \\ 0 \end{bmatrix}
+z\begin{bmatrix} -3 \\ 0 \\ 1 \end{bmatrix}
$$

따라서, 영공간은

$$\text{span}\left\{\begin{bmatrix}
-2 \\ 1 \\ 0
\end{bmatrix},
\begin{bmatrix}
-3 \\ 0 \\ 1
\end{bmatrix}\right\}
$$

{{< /details >}}