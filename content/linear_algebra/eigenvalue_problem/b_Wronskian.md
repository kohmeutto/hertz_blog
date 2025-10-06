+++
title = "(b) Wronskian"
weight = 2
+++

---

### 1. 론스키안(Wronskian) 행렬 & 행렬식

이산 유한 벡터(기저)의 경우, 독립과 종속을 판별하기 위해, 일반적인 행렬을 구성하여, 행렬식(determinent)를 사용하였다. **연속 무한 기저로 표현되는** 경우 ($|f_1\rangle$, $|f_2\rangle$, $\cdots$)독립과 종속을 판별하기 위해, **론스키안 행렬** 을 구성한다.

$$
W
=\begin{bmatrix}
\langle x|f_1\rangle & \langle x|f_2\rangle & \langle x|f_3\rangle & \cdots \\
\langle x|\hat{D}|f_1\rangle & \langle x|\hat{D}|f_2\rangle & \langle x|\hat{D}|f_3\rangle & \cdots \\
\langle x|\hat{D}^2|f_1\rangle & \langle x|\hat{D}^2|f_2\rangle & \langle x|\hat{D}^2|f_3\rangle & \cdots \\
\vdots & \vdots & \vdots & \ddots \\
\end{bmatrix}
=\begin{bmatrix}
f_1(x) & f_2(x) & f_3(x) & \cdots \\
f'_1(x) & f'_2(x) & f'_3(x) & \cdots \\
f''_1(x) & f''_2(x) & f''_3(x) & \cdots \\
\vdots & \vdots & \vdots & \ddots \\
\end{bmatrix}
$$

- 독립: $|W|\ne 0$
- 종속: $|W|= 0$

proof)

론스키안(Wronskian)은 함수들의 선형 독립성을 판별하는 강력한 도구이며, 디락 표기법을 사용하면 그 구조를 더 근본적인 수준에서 이해할 수 있다.

아래와 같이 연속 무한 기저를 가지는 상태벡터가 2개 있다.

$$
|f_1\rangle=\int dx f_1(x) |x\rangle
$$

$$
|f_2\rangle=\int dx f_2(x) |x\rangle
$$

이 두 벡터의 독립 종속 여부를 판단하기 위해 아래의 식을 만든다.

$$
c_1|f_1\rangle+c_2|f_2\rangle=0
$$

연속 무한 기저이므로 행벡터로 표현할 수 없다. 따라서, 연산이 가능한 형태로 표현해야 한다.

$$
c_1\langle x|f_1\rangle+c_2\langle x|f_2\rangle=0
\implies
c_1f_1(x)+c_2f_2(x)=0
$$

미지수가 2개 이므로 하나의 방정식이 더 필요하다. 위 식을 미분하면, 

$$
c_1f'_1(x)+c_2f'_2(x)=0
$$

따라서, 다음과 같은 론스키안 행렬을 만들 수 있다.

$$
W=
\begin{bmatrix}
f_1(x) & f_2(x) \\
f'_1(x) & f'_2(x) \\
\end{bmatrix}
$$

위 행렬을 bra-ket 으로 표기하면, 본질적 의미를 파악할 수 있다.

$$
W
=\begin{bmatrix}
\langle x|f_1\rangle & \langle x|f_2\rangle \\
\langle x|\hat{D}|f_1\rangle & \langle x|\hat{D}|f_2\rangle  \\
\end{bmatrix}
$$

위 행렬의 열벡터를 살펴보자.

$$
\begin{bmatrix}
\langle x|f_n\rangle \\ \langle x|\hat{D}|f_n\rangle
\end{bmatrix}
$$

**상태 벡터 $|f_n\rangle$는 '값' 정보와 함께 '어떻게 움직이는가'에 대한 '변화율(미분)' 정보도 잠재적으로 포함하고 있다.** 서로 다른 두 벡터의 관계를 정확히 알려면, 이 두 가지 정보를 모두 캐내야 한다. 

---
