+++
title = "(b) Tensor components transformation I"
weight = 6
+++

---

**중요사항: 동일 [실 공간]** 에 대한 것으로 **텐서 성분 변환** 을 다룬다. 여기서의 텐서는 벡터이며, 변위벡터, 국소벡터를 의미한다. 

---

### 1. 기저의 표현

아래와 같이 u 좌표계의 **orthnormal** 한 기저 벡터를 아래와 같이 놓는다.

$$
|u_{i}\rangle=\left[\begin{matrix}
    u_{i}\left\lbrack1\right\rbrack \\
    u_{i}\left\lbrack2\right\rbrack \\
    u_{i}\left\lbrack3\right\rbrack
\end{matrix}\right]
$$

$$
|u_1\rangle=\left[\begin{matrix}
    u_1\left\lbrack1\right\rbrack \\
    u_1\left\lbrack2\right\rbrack \\
    u_1\left\lbrack3\right\rbrack
\end{matrix}\right], \quad
|u_2\rangle=\left[\begin{matrix}
    u_2\left\lbrack1\right\rbrack \\
    u_2\left\lbrack2\right\rbrack \\
    u_2\left\lbrack3\right\rbrack
\end{matrix}\right], \quad
|u_3\rangle=\left[\begin{matrix}
    u_3\left\lbrack1\right\rbrack \\
    u_3\left\lbrack2\right\rbrack \\
    u_3\left\lbrack3\right\rbrack
\end{matrix}\right]
$$

기저 벡터의 전치행렬, 즉 행벡터는 아래와 같이 표현할 수 있다.

$$
\langle u_{i}|
=\left\lbrack 
    u_{i}\left\lbrack1\right\rbrack \,\,\,
    u_{i}\left\lbrack2\right\rbrack \,\,\,
    u_{i}\left\lbrack3\right\rbrack
\right\rbrack
$$

$$
\langle u_1|
=\left\lbrack
    u_1\left\lbrack1\right\rbrack \,\,\,
    u_1\left\lbrack2\right\rbrack \,\,\,
    u_1\left\lbrack3\right\rbrack
\right\rbrack, \quad
\langle u_2|
=\left\lbrack
    u_2\left\lbrack1\right\rbrack \,\,\, 
    u_2\left\lbrack2\right\rbrack \,\,\,
    u_2\left\lbrack3\right\rbrack
\right\rbrack, \quad
\langle u_3|
=\left\lbrack
    u_3\left\lbrack1\right\rbrack \,\,\,
    u_3\left\lbrack2\right\rbrack \,\,\,
    u_3\left\lbrack3\right\rbrack
\right\rbrack
$$

벡터의 내적은 다음과 같이 표현할 수 있다.

$$
\vec{a}\cdot\vec{b}=[a]^{T}[b]=\langle a|b\rangle
$$

각 기저는 orthonormal 하다. 따라서,

$$
\delta_{ij}=\langle u_{i}|u_{j}\rangle
$$

---

### 2. 항등 연산자

$$
I=\sum_{i=1}^3|u_{i}\rangle\langle u_{i}|
$$

proof)

임의의 벡터 |Ψ⟩는 다음과 같이 표현될 수 있다.

$$
|\Psi\rangle=\sum_{i=1}^3c_{i}|u_{i}\rangle
$$

$$
\langle u_{i}|\Psi\rangle=\sum_{j=1}^3c_{j}\langle u_{i}|u_{j}\rangle=\sum_{j=1}^3c_{j}\delta_{ij}=c_{i}
$$

위 식에 다시 대입하면,

$$
|\Psi\rangle=\sum_{i=1}^3c_{i}|u_{i}\rangle=\sum_{i=1}^3\langle u_{i}|\Psi\rangle|u_{i}\rangle=\sum_{i=1}^3|u_{i}\rangle\langle u_{i}|\Psi\rangle=\left(\sum_{i=1}^3|u_{i}\rangle\langle u_{i}|\right)|\Psi\rangle
$$

따라서,

$$
I=\sum_{i=1}^3|u_{i}\rangle\langle u_{i}|
$$

---

### 3. 다른 기저로의 선형 변환

임의의 벡터 |Ψ⟩는 다음과 같이 표현될 수 있다.

$$
|\Psi\rangle=\sum_{i=1}^3c_{i}|u_{i}\rangle
$$

u 로 표현된 기저를 v 로 바꿔보자.

$$
|\Psi\rangle=I|\Psi\rangle=\sum_{i=1}^3\left(\sum_{j=1}^3|v_{j}\rangle\langle v_{j}|\right)c_{i}|u_{i}\rangle=\sum_{i=1}^3\sum_{j=1}^3c_{i}\langle v_{j}|u_{i}\rangle|v_{j}\rangle
$$

여기에서, $\sum_{i=1}^3c_{i}\langle v_{j}|u_{i}\rangle$ 는 기저 $|v_{j}\rangle$ 의 **성분 값** 이다.

---

### 4. 성분 값 변환 행렬

$$
\sum_{i=1}^3\sum_{j=1}^3c_{i}\langle v_{j}|u_{i}\rangle=\sum_{j=1}^3\langle v_{j}|\left(\sum_{i=1}^3c_{i}|u_{i}\rangle\right)
$$

$$
=\left[\begin{matrix}
    v_1\left\lbrack1\right\rbrack & v_2\left\lbrack1\right\rbrack & v_3\left\lbrack1\right\rbrack \\ v_1\left\lbrack2\right\rbrack & v_2\left\lbrack2\right\rbrack & v_3\left\lbrack2\right\rbrack \\ v_1\left\lbrack3\right\rbrack & v_2\left\lbrack3\right\rbrack & v_3\left\lbrack3\right\rbrack
\end{matrix}\right]^{T}
\left[\begin{matrix}
    u_1\left\lbrack1\right\rbrack & u_2\left\lbrack1\right\rbrack & u_3\left\lbrack1\right\rbrack \\ u_1\left\lbrack2\right\rbrack & u_2\left\lbrack2\right\rbrack & u_3\left\lbrack2\right\rbrack \\ u_1\left\lbrack3\right\rbrack & u_2\left\lbrack3\right\rbrack & u_3\left\lbrack3\right\rbrack
\end{matrix}\right]
\left[\begin{matrix}
    c_1 \\ c_2 \\ c_3
\end{matrix}\right] 
$$

$$
=\left[\begin{matrix}
    v_1\left\lbrack1\right\rbrack & v_1\left\lbrack2\right\rbrack & v_1\left\lbrack3\right\rbrack \\ v_2\left\lbrack1\right\rbrack & v_2\left\lbrack2\right\rbrack & v_2\left\lbrack3\right\rbrack \\ v_3\left\lbrack1\right\rbrack & v_3\left\lbrack2\right\rbrack & v_3\left\lbrack3\right\rbrack
\end{matrix}\right]
\left[\begin{matrix}
    u_1\left\lbrack1\right\rbrack & u_2\left\lbrack1\right\rbrack & u_3\left\lbrack1\right\rbrack \\ u_1\left\lbrack2\right\rbrack & u_2\left\lbrack2\right\rbrack & u_3\left\lbrack2\right\rbrack \\ u_1\left\lbrack3\right\rbrack & u_2\left\lbrack3\right\rbrack & u_3\left\lbrack3\right\rbrack
\end{matrix}\right]
\left[\begin{matrix}
    c_1 \\ c_2 \\ c_3
\end{matrix}\right]
$$

만약 u좌표계의 기저가 표준기저라고 하면,

$$
\sum_{i=1}^3\sum_{j=1}^3c_{i}\langle v_{j}|u_{i}\rangle]
=\left[\begin{matrix}
    v_1\left\lbrack1\right\rbrack & v_1\left\lbrack2\right\rbrack & v_1\left\lbrack3\right\rbrack \\ v_2\left\lbrack1\right\rbrack & v_2\left\lbrack2\right\rbrack & v_2\left\lbrack3\right\rbrack \\ v_3\left\lbrack1\right\rbrack & v_3\left\lbrack2\right\rbrack & v_3\left\lbrack3\right\rbrack
\end{matrix}\right]
\left[\begin{matrix}
    c_1 \\ c_2 \\ c_3
\end{matrix}\right]
$$

위 내용을 정리하면, **u좌표계의 기저가 표준기저라고 하면, u→v의 성분변환행렬은 u→v의 기저행렬(u 표준기저를 기준으로 새로운 v 기저 벡터들을 열로 나열하여 만든 행렬)의 전치행렬과 같다.**

---