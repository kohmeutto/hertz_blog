+++
title = "(b) Direct sum"
weight = 1
+++

---

### 1. 동기: 두 공간을 독립된 블록으로 나란히 두기

두 벡터공간을 하나로 결합하는 방법은 한 가지가 아니다. 그 중, 직합(Direct sum)은 두 공간을 겹치지 않게 이어 붙여 나란히 두는 "또는"의 결합이다. 직합으로 묶은 공간의 원소는 두 부분을 따로 들고 있으며, 한 부분에 일어나는 일이 다른 부분을 건드리지 않는다. 직합은 차원이 더해진다.

$$
\dim(V_1 \oplus V_2) = \dim V_1 + \dim V_2
$$

---

### 2. 직합의 공리와 기저

**1) 공리: 순서쌍과 성분별 연산**

두 벡터공간 $V_1$, $V_2$ 의 직합 $V_1 \oplus V_2$ 의 원소는 순서쌍 $(|v\rangle, |w\rangle)$ 이다. 여기서 $|v\rangle \in V_1$, $|w\rangle \in V_2$ 이다. 텐서곱과 마찬가지로 직합도 두 공간의 데카르트 곱 위에서 정의되지만, 결합 방식이 다르다. 덧셈은 같은 자리끼리 따로 한다. 첫 성분은 $V_1$ 안에서, 둘째 성분은 $V_2$ 안에서 더한다.

$$
(|v_1\rangle, |w_1\rangle) + (|v_2\rangle, |w_2\rangle) = (|v_1\rangle + |v_2\rangle,\ |w_1\rangle + |w_2\rangle)
$$

스칼라 곱도 각 성분에 따로 작용한다.

$$
a\,(|v\rangle, |w\rangle) = (a|v\rangle,\ a|w\rangle)
$$

**2) 열벡터 표현**

직합의 원소는 $V_1$ 성분을 위에, $V_2$ 성분을 아래에 쌓은 열로 적힌다. $V_1$, $V_2$ 가 둘 다 2차원이면 위 두 칸이 $V_1$ 의 몫, 아래 두 칸이 $V_2$ 의 몫이다.

$$
(|v\rangle, |w\rangle) = \left( \begin{pmatrix} v_1 \\ v_2 \end{pmatrix}, \begin{pmatrix} w_1 \\ w_2 \end{pmatrix} \right)=\begin{pmatrix} v_1 \\ v_2 \\ w_1 \\ w_2 \end{pmatrix}
$$

example)

$$
\begin{pmatrix} 1 \\ 2 \end{pmatrix} \oplus \begin{pmatrix} 3 \\ 4 \end{pmatrix} = \begin{pmatrix} 1 \\ 2 \\ 3 \\ 4 \end{pmatrix}
$$

**3) 차원과 기저**

직합의 기저는 두 공간의 기저를 그냥 합친 것이다. $V_1$ 의 기저 $\{|u_i\rangle\}$ 와 $V_2$ 의 기저 $\{|e_j\rangle\}$ 에서, 한쪽 자리를 0으로 채운 순서쌍들이 직합의 기저가 된다.

example)

$V_1$ 이 2차원, $V_2$ 가 2차원인 경우 기저는 네 개다.

$$
(|u_1\rangle, 0) = \begin{pmatrix} 1 \\ 0 \\ 0 \\ 0 \end{pmatrix}, \quad (|u_2\rangle, 0) = \begin{pmatrix} 0 \\ 1 \\ 0 \\ 0 \end{pmatrix}
,\quad (0, |e_1\rangle) = \begin{pmatrix} 0 \\ 0 \\ 1 \\ 0 \end{pmatrix}, \quad (0, |e_2\rangle) = \begin{pmatrix} 0 \\ 0 \\ 0 \\ 1 \end{pmatrix}
$$

---

### 3. 직합 연산자: 블록 대각

직합 공간에 작용하는 연산자 가운데 기본은, 두 공간을 섞지 않고 각 블록에 따로 작용하는 블록 대각(Block-diagonal) 꼴이다. $V_1$ 에 작용하는 연산자 $A$ 와 $V_2$ 에 작용하는 연산자 $B$ 의 직합을 다음으로 적는다.

$$
A \oplus B = \begin{pmatrix} A & 0 \\ 0 & B \end{pmatrix}
$$

작용 규칙은 각 블록이 자기 성분에만 작용하는 것이다. 위 블록 $A$ 는 첫 성분 $|v\rangle$ 에, 아래 블록 $B$ 는 둘째 성분 $|w\rangle$ 에 작용한다.

$$
(A \oplus B)(|v\rangle, |w\rangle) = (A|v\rangle,\ B|w\rangle)
$$

example)

$A = \begin{pmatrix} 2 & 0 \\ 0 & 3 \end{pmatrix}$, $B = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}$, $|v\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix}$, $|w\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix}$ 에서 위 식을 확인한다.

$$
A \oplus B = \begin{pmatrix} 2 & 0 & 0 & 0 \\ 0 & 3 & 0 & 0 \\ 0 & 0 & 0 & 1 \\ 0 & 0 & 1 & 0 \end{pmatrix},
\quad
A\begin{pmatrix} 1 \\ 0 \end{pmatrix} = \begin{pmatrix} 2 \\ 0 \end{pmatrix},
\quad
B\begin{pmatrix} 1 \\ 0 \end{pmatrix} = \begin{pmatrix} 0 \\ 1 \end{pmatrix}
$$

아래임을 확인할 수 있다.

$$
(A \oplus B)\begin{pmatrix} 1 \\ 0 \\ 1 \\ 0 \end{pmatrix} = \begin{pmatrix} 2 \\ 0 \\ 0 \\ 1 \end{pmatrix}
$$

$4 \times 4$ 행렬로 직접 곱해도 같은 결과가 나온다. 비대각이 0이므로 위 두 성분은 $A$ 만, 아래 두 성분은 $B$ 만 결정하며, 두 블록이 서로 간섭하지 않는다. 이것이 직합 구조의 연산자다.

---

### 4. 직합 공간의 내적

직합 공간의 내적은 두 성분의 내적을 더한 것이다. 첫 성분끼리, 둘째 성분끼리 내적을 취해 합한다.

$$
\big\langle (|v_1\rangle, |w_1\rangle) \,\big|\, (|v_2\rangle, |w_2\rangle) \big\rangle = \langle v_1|v_2\rangle + \langle w_1|w_2\rangle
$$

example)

구체 수치로 4차원 표준 내적과 일치함을 확인한다. $|v_1\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix}$, $|w_1\rangle = \begin{pmatrix} 0 \\ 1 \end{pmatrix}$, $|v_2\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix}$, $|w_2\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix}$ 로 둔다. 성분별 내적의 합을 먼저 계산한다.

$$
\langle v_1|v_2\rangle + \langle w_1|w_2\rangle = (1\cdot 1 + 0\cdot 0) + (0\cdot 1 + 1\cdot 0) = 1 + 0 = 1
$$

이제 4차원 열벡터로 직접 계산한다. 

$$
\big\langle (|v_1\rangle, |w_1\rangle) \,\big|\, (|v_2\rangle, |w_2\rangle) \big\rangle  = \begin{pmatrix} 1 \\ 0 \\ 0 \\ 1 \end{pmatrix} \cdot \begin{pmatrix} 1 \\ 0 \\ 1 \\ 0 \end{pmatrix} = 1
$$

성분별 내적의 합과 4차원 직접 내적이 모두 1로 일치한다. 텐서곱 공간의 내적이 두 내적의 곱 $\langle a_1|a_2\rangle \cdot \langle b_1|b_2\rangle$ 이었던 것과 달리, 직합 공간의 내적은 두 내적의 합이다. 곱과 합의 이 차이가 텐서곱과 직합의 또 하나의 대비다.

---

### 6. (참고) 스펙트럼 분해와 직합

직합은 이 시리즈 본체의 스펙트럼 분해에 직접 등장한다. 연산자의 서로 다른 고윳값에 속하는 고유공간들은 서로 독립이므로, 전체 공간은 그 고유공간들의 직합으로 적힌다.

$$
V = \bigoplus_m V_{\lambda_m}
$$

서로 다른 고윳값 $\lambda_m$ 의 고유공간 $V_{\lambda_m}$ 들은 독립된 블록으로 나란히 놓이며(직합), 이에 대응하여 연산자는 각 고유공간에 따로 작용하는 블록 대각 구조를 가진다. 한편 하나의 고유공간 내부에서는 고윳값 축과 사슬 축이 곱으로 엮인다(텐서곱). 따라서 이 시리즈는 두 결합을 모두 사용한다. 고윳값들 사이는 직합(서로 다른 고윳값은 독립 블록)이고, 한 고윳값 내부의 두 축은 텐서곱(스펙트럼 축과 사슬 축의 동시 결합)이다. 직합과 텐서곱을 모두 이해해야 결함 연산자의 전체 구조가 보이는 까닭이다.

---