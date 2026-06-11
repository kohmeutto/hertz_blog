+++
title = "(b) Tensor Product"
weight = 5
+++

---

### 1. 동기: 여러 자유도를 한 공간에 담기

하나의 상태공간(Hilbert space)은 한 종류의 자유도를 기술한다. 예를 들어 한 입자의 위치 자유도는 위치 고유켓 $|x\rangle$ 들이 펼치는 공간으로, 스핀 자유도는 두 스핀 켓 $|\uparrow\rangle, |\downarrow\rangle$ 이 펼치는 공간으로 기술된다. 문제는 한 계가 두 종류 이상의 자유도를 동시에 가질 때다. 위치와 스핀을 함께 가진 입자, 또는 두 개의 입자로 이루어진 계가 그렇다. 이때 두 자유도를 하나의 상태공간으로 묶는 연산이 텐서곱(Tensor product)이다.

핵심 성질은 다음과 같다. 두 자유도가 서로 독립이면, 합쳐진 공간의 차원은 두 공간의 차원의 곱이다. 직관은 단순한 조합 계산이다. 윗옷을 두 종류(흰색, 검은색) 중에서, 바지를 두 종류(청색, 회색) 중에서 고른다면, 가능한 옷차림은 두 선택의 모든 짝이어서 $2 \times 2 = 4$ 가지다. 두 선택이 독립이므로 한쪽 가짓수와 다른 쪽 가짓수가 곱해진다. 텐서곱으로 묶은 상태공간의 차원도 같은 이유로 곱이 된다.

$$
\dim(\mathcal{H}_1 \otimes \mathcal{H}_2) = \dim(\mathcal{H}_1) \cdot \dim(\mathcal{H}_2)
$$

이 챕터의 뒤 내용(연속 일반화 챕터)에서 묶을 두 자유도는 고윳값 축(연속 변수 $\nu$ 가 도는 위치공간)과 사슬 축(조르당 사슬의 칸 번호 $k$ 가 도는 유한 공간)이다. 이때는 한쪽이 무한 차원(연속), 다른 쪽이 유한 차원(이산)이라는 점이 본질적이며, 그 의미는 일반화 챕터에서 다룬다. 본 챕터는 텐서곱 자체의 정의와 규칙을, 가장 작은 유한 차원 예로 먼저 세운다.

---

### 2. 텐서곱의 정의

텐서곱 공간 $V = V_1 \otimes V_2$ 는 다음과 같이 정의된다. $V_1$ 의 임의의 상태 $|\psi\rangle$ 와 $V_2$ 의 임의의 상태 $|\phi\rangle$ 의 각 쌍에 대하여 $V$ 안에 대응하는 상태 $|\psi\rangle \otimes |\phi\rangle$ 가 존재하며, 이 대응이 다음 두 성질을 만족한다. 이 대응은 두 공간의 데카르트 곱(순서쌍의 집합) $V_1 \times V_2$ 에서 $V$ 로 가는 사상으로 적힌다.

$$
\otimes : V_1 \times V_2 \longrightarrow V, \qquad (|\psi\rangle, |\phi\rangle) \longmapsto |\psi\rangle \otimes |\phi\rangle
$$

---

### 3. 텐서곱의 기본 성질

**1) 성질 1: 스칼라 곱에 대한 선형성**

스칼라 $a$ 를 텐서곱에 곱한 것은, 그 스칼라를 어느 한쪽 인자에 곱한 것과 같다.

$$
a\,(|\psi\rangle \otimes |\phi\rangle) = (a|\psi\rangle) \otimes |\phi\rangle = |\psi\rangle \otimes (a|\phi\rangle)
$$

**2) 성질 2: 벡터 덧셈에 대한 분배성**

한쪽 인자가 두 켓의 합이면 텐서곱이 각 항으로 분배된다. 왼쪽 인자에 대하여 다음이 성립한다.

$$
(|\psi_1\rangle + |\psi_2\rangle) \otimes |\phi\rangle = |\psi_1\rangle \otimes |\phi\rangle + |\psi_2\rangle \otimes |\phi\rangle
$$

오른쪽 인자에 대해서도 같다.

$$
|\psi\rangle \otimes (|\phi_1\rangle + |\phi_2\rangle) = |\psi\rangle \otimes |\phi_1\rangle + |\psi\rangle \otimes |\phi_2\rangle
$$

---

### 4. 중요 따름 성질

아래의 성분 쌓기 규칙과 기저 짝 전개가 정의와 기본 성질로 부터 따라 나온다.


**1) 성분 쌓기 규칙**

정의가 추상적이므로, 가장 작은 경우인 2차원 켓과 2차원 켓의 텐서곱에서 구체적 계산 규칙을 본다. 규칙은 왼쪽 켓의 각 성분에 오른쪽 켓 전체를 곱하여 세로로 쌓는 것이다.

$$
\begin{pmatrix} a \\ b \end{pmatrix} \otimes \begin{pmatrix} c \\ d \end{pmatrix} = \begin{pmatrix} a \begin{pmatrix} c \\ d \end{pmatrix} \\[6pt] b \begin{pmatrix} c \\ d \end{pmatrix} \end{pmatrix} = \begin{pmatrix} ac \\ ad \\ bc \\ bd \end{pmatrix}
$$

구체 수치로 계산한다.

$$
\begin{pmatrix} 1 \\ 2 \end{pmatrix} \otimes \begin{pmatrix} 3 \\ 4 \end{pmatrix} = \begin{pmatrix} 1 \cdot 3 \\ 1 \cdot 4 \\ 2 \cdot 3 \\ 2 \cdot 4 \end{pmatrix} = \begin{pmatrix} 3 \\ 4 \\ 6 \\ 8 \end{pmatrix}
$$

2차원과 2차원을 묶으니 $2 \times 2 = 4$ 차원이 되었다. 차원이 곱해지는 것이 텐서곱의 첫 특징이며, 차원 공식과 일치한다.

**2) 기저 짝 전개: 성분이 뜻하는 것**

위의 결과 $\begin{pmatrix} ac, ad, bc, bd \end{pmatrix}^T$ 의 네 성분이 무엇인지는, 두 켓을 각자의 기저로 펼쳐 텐서곱에 두 공리를 적용하면 드러난다. 먼저 왼쪽 켓을 왼쪽 공간의 표준기저 $|u_1\rangle = \begin{pmatrix} 1, 0 \end{pmatrix}^T$, $|u_2\rangle = \begin{pmatrix} 0, 1 \end{pmatrix}^T$ 로 펼친다.

$$
\begin{pmatrix} a \\ b \end{pmatrix}
=a \begin{pmatrix} 1 \\ 0 \end{pmatrix} + b \begin{pmatrix} 0 \\ 1 \end{pmatrix}
= a|u_1\rangle + b|u_2\rangle
$$

오른쪽 켓을 오른쪽 공간의 표준기저 $|e_1\rangle = \begin{pmatrix} 1, 0 \end{pmatrix}^T$, $|e_2\rangle = \begin{pmatrix} 0, 1 \end{pmatrix}^T$ 로 펼친다.

$$
\begin{pmatrix} c \\ d \end{pmatrix} = c|e_1\rangle + d|e_2\rangle
$$

기저 글자를 $u$ 와 $e$ 로 다르게 쓴 것은 두 켓이 서로 다른 공간에 살기 때문이다. 숫자로는 둘 다 $\begin{pmatrix} 1, 0 \end{pmatrix}^T$, $\begin{pmatrix} 0, 1 \end{pmatrix}^T$ 로 같지만, 서로 독립인 두 자유도이므로 구별된다. 텐서곱은 성질 2(분배성)에 의해 덧셈에 분배되고 성질 1(선형성)에 의해 스칼라가 앞으로 빠져나오므로, 두 전개를 텐서곱하면 네 항이 된다.

$$
\begin{pmatrix} a \\ b \end{pmatrix} \otimes \begin{pmatrix} c \\ d \end{pmatrix} = (a|u_1\rangle + b|u_2\rangle) \otimes (c|e_1\rangle + d|e_2\rangle)
$$
ㄴ
$$
= ac\,(|u_1\rangle \otimes |e_1\rangle) + ad\,(|u_1\rangle \otimes |e_2\rangle) + bc\,(|u_2\rangle \otimes |e_1\rangle) + bd\,(|u_2\rangle \otimes |e_2\rangle)
$$

네 기저 짝이 4차원에서 무엇인지 1)의 규칙으로 계산한다.

$$
|u_1\rangle \otimes |e_1\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix} \otimes \begin{pmatrix} 1 \\ 0 \end{pmatrix} = \begin{pmatrix} 1 \\ 0 \\ 0 \\ 0 \end{pmatrix}, \qquad |u_1\rangle \otimes |e_2\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix} \otimes \begin{pmatrix} 0 \\ 1 \end{pmatrix} = \begin{pmatrix} 0 \\ 1 \\ 0 \\ 0 \end{pmatrix}
$$

$$
|u_2\rangle \otimes |e_1\rangle = \begin{pmatrix} 0 \\ 1 \end{pmatrix} \otimes \begin{pmatrix} 1 \\ 0 \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \\ 1 \\ 0 \end{pmatrix}, \qquad |u_2\rangle \otimes |e_2\rangle = \begin{pmatrix} 0 \\ 1 \end{pmatrix} \otimes \begin{pmatrix} 0 \\ 1 \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \\ 0 \\ 1 \end{pmatrix}
$$

네 짝이 4차원의 네 표준기저(첫째·둘째·셋째·넷째 자리에 1)이다. 위 전개식에 대입한다.

$$
ac\begin{pmatrix} 1 \\ 0 \\ 0 \\ 0 \end{pmatrix} + ad\begin{pmatrix} 0 \\ 1 \\ 0 \\ 0 \end{pmatrix} + bc\begin{pmatrix} 0 \\ 0 \\ 1 \\ 0 \end{pmatrix} + bd\begin{pmatrix} 0 \\ 0 \\ 0 \\ 1 \end{pmatrix} = \begin{pmatrix} ac \\ ad \\ bc \\ bd \end{pmatrix}
$$

1)에서 규칙으로 곧장 얻은 결과와 같다. 따라서 1)의 "각 성분에 곱하여 쌓는다"는 규칙은 이 분배 전개를 압축한 것이며, 네 성분 $ac, ad, bc, bd$ 는 네 기저 짝 $|u_i\rangle \otimes |e_j\rangle$ 앞에 붙는 계수다. 곧, 텐서곱 공간의 기저는 왼쪽 공간의 기저와 오른쪽 공간의 기저의 모든 짝이다.

$$
|u_1\rangle \otimes |e_1\rangle, \quad |u_1\rangle \otimes |e_2\rangle, \quad |u_2\rangle \otimes |e_1\rangle, \quad |u_2\rangle \otimes |e_2\rangle
$$

---

### 5. 줄임 표기

텐서곱 기호 $\otimes$ 를 생략하고 두 켓을 붙여 쓰는 관습이 흔하다. 다음은 모두 같은 대상을 가리킨다.

$$
|u_i\rangle \otimes |e_j\rangle \;=\; |u_i\rangle|e_j\rangle \;=\; |u_i, e_j\rangle \;=\; |u_i e_j\rangle
$$

켓이 어느 상태공간에 속하는지를 켓에 하위 첨자로 적기도 한다. 예를 들어 첫째 공간의 켓에는 첨자 1을, 둘째 공간의 켓에는 첨자 2를 붙여 $|\psi\rangle_1 \otimes |\phi\rangle_2$ 로 쓴다. 이 첨자가 소속 공간을 식별하므로, 첨자를 적는 한 두 켓을 쓰는 순서는 의미를 바꾸지 않는다. 반대로 첨자를 생략하면 쓰는 순서가 소속 공간을 결정하며, 첫 자리가 첫째 공간, 둘째 자리가 둘째 공간을 뜻한다고 약속한다.

이 줄임 표기에서 한 가지를 주의해야 한다. 두 켓을 붙인 $|u_i\rangle|e_j\rangle$ 는 텐서곱이지만, 두 연산자를 붙인 $\hat{A}\hat{B}$ 는 텐서곱이 아니라 같은 공간 안의 합성(보통의 행렬곱)이다.

---

### 6. 연산자의 텐서곱

연산자도 같은 규칙으로 묶는다. 왼쪽 행렬의 각 성분에 오른쪽 행렬 전체를 곱하여 블록으로 배치한다.

$$
\hat{A} \otimes \hat{B} = \begin{pmatrix} a_{11} & a_{12} \\ a_{21} & a_{22} \end{pmatrix} \otimes \hat{B} = \begin{pmatrix} a_{11} \hat{B} & a_{12} \hat{B} \\ a_{21} \hat{B} & a_{22} \hat{B} \end{pmatrix}
$$

따라서, 교환 법칙은 성립하지 않는다.

$$
\hat{A} \otimes \hat{B} \ne \hat{B} \otimes \hat{A}
$$

한 자유도에만 작용하는 연산자를 합성계 전체의 연산자로 확장할 때, 아래의 표현의 형태로 쓴다.

$$
I \otimes \hat{A} + \hat{B} \otimes I
$$

example)

두 경우를 계산한다. 먼저 항등 $I_2$ 를 왼쪽에, 어떤 행렬 $\hat{B} = \begin{pmatrix} 5 & 6 \\ 7 & 8 \end{pmatrix}$ 를 오른쪽에 둔다. 왼쪽이 항등이므로 대각 자리에만 $\hat{B}$ 가 깔린다.

$$
I_2 \otimes \hat{B} = \begin{pmatrix} 1 \cdot \hat{B} & 0 \cdot \hat{B} \\ 0 \cdot \hat{B} & 1 \cdot \hat{B} \end{pmatrix} = \begin{pmatrix} 5 & 6 & 0 & 0 \\ 7 & 8 & 0 & 0 \\ 0 & 0 & 5 & 6 \\ 0 & 0 & 7 & 8 \end{pmatrix}
$$

이번에는 순서를 바꾸어, 행렬 $\hat{A} = \begin{pmatrix} 5 & 6 \\ 7 & 8 \end{pmatrix}$ 를 왼쪽에, 항등 $I_2$ 를 오른쪽에 둔다. 왼쪽 성분 하나하나에 $I_2$ 가 곱해진다.

$$
\hat{A} \otimes I_2 = \begin{pmatrix} 5 I_2 & 6 I_2 \\ 7 I_2 & 8 I_2 \end{pmatrix} = \begin{pmatrix} 5 & 0 & 6 & 0 \\ 0 & 5 & 0 & 6 \\ 7 & 0 & 8 & 0 \\ 0 & 7 & 0 & 8 \end{pmatrix}
$$

**같은 재료로 만든 $I_2 \otimes \hat{B}$ 와 $\hat{A} \otimes I_2$ 가 전혀 다른 행렬** 이다. 왼쪽 자리와 오른쪽 자리가 맡는 역할이 다르기 때문이다.

이 두 형태가 특별히 중요하다. $\hat{A} \otimes I$ 는 왼쪽 자유도에만 작용하고 오른쪽 자유도는 건드리지 않는 연산자이며($\hat{A}$ 라는 변환을 첫째 자유도에만 적용), $I \otimes \hat{B}$ 는 오른쪽 자유도에만 작용하는 연산자다. **한 자유도에만 작용하는 연산자를 합성계 전체의 연산자로 확장할 때 이 형태를 쓴다.** 그 정확한 작용 방식이 다음 성분별 작용으로 정해진다.

---

### 7. 성분별 작용

**1) 연산자 & 벡터**

텐서곱에서 가장 중요한 단 하나의 규칙이다. 연산자의 텐서곱이 켓의 텐서곱에 작용하면, 왼쪽은 왼쪽끼리, 오른쪽은 오른쪽끼리 따로 만난다.

$$
(\hat{A} \otimes \hat{B})(|v\rangle \otimes |w\rangle) = (\hat{A}|v\rangle) \otimes (\hat{B}|w\rangle)
$$

$\hat{A}$ 는 왼쪽 자유도의 켓 $|v\rangle$ 에만 작용하고 오른쪽은 건드리지 않으며, $\hat{B}$ 는 오른쪽 자유도의 켓 $|w\rangle$ 에만 작용하고 왼쪽은 건드리지 않는다. 두 자유도가 서로 간섭 없이 각자의 연산자에게만 반응한다. 성분별 작용은 곱 상태 $|v\rangle \otimes |w\rangle$ 에 대한 작용을 정한다. 곱 상태가 아닌 일반 상태(6절에서 다루는 얽힌 상태를 포함)에는 연산자의 선형성으로 확장한다. 일반 켓을 기저 짝으로 펼치고, 연산자가 선형이므로 합 안으로 들어가, 각 기저 짝에 성분별 작용을 적용한다.

$$
(\hat{A} \otimes \hat{B})\sum_{i,j} c_{ij}\,(|u_i\rangle \otimes |e_j\rangle) = \sum_{i,j} c_{ij}\,(\hat{A}|u_i\rangle) \otimes (\hat{B}|e_j\rangle)
$$

이렇게 하면 텐서곱 연산자의 작용이 곱 상태를 넘어 임의의 상태로 정의된다.

example)


$\hat{A} = \begin{pmatrix} 2 & 0 \\ 0 & 3 \end{pmatrix}$, $\hat{B} = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}$, $|v\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix}$, $|w\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix}$ 로 둔다.

먼저 우변(각자 작용)을 계산한다.

$$
\hat{A}|v\rangle = \begin{pmatrix} 2 & 0 \\ 0 & 3 \end{pmatrix}\begin{pmatrix} 1 \\ 0 \end{pmatrix} = \begin{pmatrix} 2 \\ 0 \end{pmatrix},\quad
\hat{B}|w\rangle = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}\begin{pmatrix} 1 \\ 0 \end{pmatrix} = \begin{pmatrix} 0 \\ 1 \end{pmatrix}
$$

둘을 텐서곱한다.

$$
(\hat{A}|v\rangle) \otimes (\hat{B}|w\rangle) = \begin{pmatrix} 2 \\ 0 \end{pmatrix} \otimes \begin{pmatrix} 0 \\ 1 \end{pmatrix} = \begin{pmatrix} 2 \cdot 0 \\ 2 \cdot 1 \\ 0 \cdot 0 \\ 0 \cdot 1 \end{pmatrix} = \begin{pmatrix} 0 \\ 2 \\ 0 \\ 0 \end{pmatrix}
$$

이제 좌변(먼저 묶고 작용)을 계산하여 같은 값이 나오는지 본다. $|v\rangle \otimes |w\rangle$ 를 구한다.

$$
|v\rangle \otimes |w\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix} \otimes \begin{pmatrix} 1 \\ 0 \end{pmatrix} = \begin{pmatrix} 1 \\ 0 \\ 0 \\ 0 \end{pmatrix}
$$

$\hat{A} \otimes \hat{B}$ 를 구한다.

$$
\hat{A} \otimes \hat{B} = \begin{pmatrix} 2 \hat{B} & 0 \\ 0 & 3 \hat{B} \end{pmatrix} = \begin{pmatrix} 0 & 2 & 0 & 0 \\ 2 & 0 & 0 & 0 \\ 0 & 0 & 0 & 3 \\ 0 & 0 & 3 & 0 \end{pmatrix}
$$

둘을 곱한다.

$$
(\hat{A} \otimes \hat{B})(|v\rangle \otimes |w\rangle) = \begin{pmatrix} 0 & 2 & 0 & 0 \\ 2 & 0 & 0 & 0 \\ 0 & 0 & 0 & 3 \\ 0 & 0 & 3 & 0 \end{pmatrix}\begin{pmatrix} 1 \\ 0 \\ 0 \\ 0 \end{pmatrix} = \begin{pmatrix} 0 \\ 2 \\ 0 \\ 0 \end{pmatrix}
$$

좌변과 우변이 똑같이 $\begin{pmatrix} 0, 2, 0, 0 \end{pmatrix}^T$ 이다.

**2) 연산자 & 연산자**

연산자끼리의 곱에도 같은 규칙이 적용된다. 두 텐서곱 연산자를 합성하면 같은 자리끼리 합성된다.

$$
(\hat{A} \otimes \hat{B})(C \otimes D) = (\hat{A}C) \otimes (\hat{B}D)
$$

이는 성분별 작용을 켓이 아니라 연산자에 적용한 것으로, 왼쪽 자리에서는 $\hat{A}$ 와 $C$ 가, 오른쪽 자리에서는 $\hat{B}$ 와 $D$ 가 각자 합성됨을 뜻한다.

---

### 5. 합 꼴과 교환성

한 자유도에만 작용하는 두 연산자를 더한 형태 $\hat{A} \otimes I + I \otimes \hat{B}$ 가 자주 등장한다. 이 합 꼴의 의미를 성분별 작용으로 읽는다. 첫 항 $\hat{A} \otimes I$ 는 $(\hat{A}|v\rangle) \otimes (I|w\rangle) = (\hat{A}|v\rangle) \otimes |w\rangle$ 이 되어 왼쪽 자유도에만 $\hat{A}$ 가 작용하고, 둘째 항 $I \otimes \hat{B}$ 는 $|v\rangle \otimes (\hat{B}|w\rangle)$ 이 되어 오른쪽 자유도에만 $\hat{B}$ 가 작용한다.

$$
(\hat{A} \otimes I + I \otimes \hat{B})(|v\rangle \otimes |w\rangle) = (\hat{A}|v\rangle) \otimes |w\rangle + |v\rangle \otimes (\hat{B}|w\rangle)
$$

이 합 꼴에서 두 항은 서로 교환한다. 4절의 연산자 곱 규칙 $(\hat{A} \otimes \hat{B})(C \otimes D) = (\hat{A}C) \otimes (\hat{B}D)$ 로 직접 확인한다. 먼저 $(\hat{A} \otimes I)(I \otimes \hat{B})$ 를 계산한다.

$$
(\hat{A} \otimes I)(I \otimes \hat{B}) = (\hat{A}I) \otimes (I\hat{B}) = \hat{A} \otimes \hat{B}
$$

순서를 바꾼 $(I \otimes \hat{B})(\hat{A} \otimes I)$ 를 계산한다.

$$
(I \otimes \hat{B})(\hat{A} \otimes I) = (I\hat{A}) \otimes (\hat{B}I) = \hat{A} \otimes \hat{B}
$$

두 결과가 같으므로 교환자가 영이다.

$$
[\hat{A} \otimes I, \; I \otimes \hat{B}] = (\hat{A} \otimes I)(I \otimes \hat{B}) - (I \otimes \hat{B})(\hat{A} \otimes I) = \hat{A} \otimes \hat{B} - \hat{A} \otimes \hat{B} = 0
$$

서로 다른 자유도(서로 다른 자리)에서 작용하는 두 연산자는 항상 교환한다. 이것이 텐서곱으로 묶은 두 자유도가 독립적으로 작동하는 근거이며, 함수·지수·역연산 같은 계산을 두 자유도로 분리해서 처리할 수 있게 한다. 이 분리가 결함 연산자(고윳값 부분과 멱영 부분의 분리)에서 어떻게 쓰이는지는 일반화 챕터에서 다룬다.

(참고) 물리에서 이 합 꼴의 대표적 예가 상호작용 없는 두 입자의 해밀토니안이다. 이는 본 시리즈 본체(결함 연산자)와 직접 관련되지는 않으나, 합 꼴의 표준적 쓰임을 보이기 위해 둔다. 두 자유 입자의 에너지는 각자의 운동에너지의 합이므로, 합성계의 해밀토니안은 첫째 입자에만 작용하는 항과 둘째 입자에만 작용하는 항의 합이다.

$$
\hat{H} = \frac{\hat{p}_1^2}{2m} \otimes \hat{I} + \hat{I} \otimes \frac{\hat{p}_2^2}{2m}
$$

첫 항은 첫째 입자의 운동에너지로 둘째 입자는 건드리지 않는 $\hat{A} \otimes I$ 꼴이고, 둘째 항은 그 반대인 $I \otimes \hat{B}$ 꼴이다. 두 항이 서로 다른 입자에 작용하므로 위에서 본 대로 교환한다. 보통은 텐서곱과 항등을 생략하여 $\dfrac{\hat{p}_1^2}{2m} + \dfrac{\hat{p}_2^2}{2m}$ 로 쓰지만, 각 항이 실제로는 합성계 전체에 작용하는 $\hat{A} \otimes I$ 또는 $I \otimes \hat{B}$ 꼴임을 기억해야 한다.

---

### 6. (참고) 곱 상태와 얽힌 상태

텐서곱 공간의 모든 상태가 $|v\rangle \otimes |w\rangle$ 의 꼴로 적히는 것은 아니다. 이 꼴로 적히는 상태를 곱 상태(Product state), 적히지 않는 상태를 얽힌 상태(Entangled state)라 한다. 이 구별은 텐서곱 공간이 단순히 두 공간을 나열한 것이 아니라 그보다 큰 공간임을 보여 준다.

먼저 곱 상태의 예를 본다. 4차원 상태 $\frac{1}{\sqrt{2}}(|u_1 e_1\rangle + |u_1 e_2\rangle)$ 는 왼쪽 인자를 묶어낼 수 있다.

$$
\frac{1}{\sqrt{2}}(|u_1\rangle \otimes |e_1\rangle + |u_1\rangle \otimes |e_2\rangle) = |u_1\rangle \otimes \frac{1}{\sqrt{2}}(|e_1\rangle + |e_2\rangle)
$$

왼쪽 켓 하나와 오른쪽 켓 하나의 텐서곱으로 적혔으므로 곱 상태다.

이제 얽힌 상태의 예를 본다. 다음 상태가 곱 상태로 적히지 않음을 보인다.

$$
|\Phi\rangle = \frac{1}{\sqrt{2}}(|u_1 e_1\rangle + |u_2 e_2\rangle)
$$

만약 이것이 곱 상태 $\big(a|u_1\rangle + b|u_2\rangle\big) \otimes \big(c|e_1\rangle + d|e_2\rangle\big)$ 로 적힌다고 가정한다. 우변을 2절의 분배로 전개한다.

$$
\big(a|u_1\rangle + b|u_2\rangle\big) \otimes \big(c|e_1\rangle + d|e_2\rangle\big) = ac|u_1 e_1\rangle + ad|u_1 e_2\rangle + bc|u_2 e_1\rangle + bd|u_2 e_2\rangle
$$

$|\Phi\rangle$ 의 계수와 항별로 맞춘다. $|u_1 e_1\rangle$ 의 계수에서 $ac = \frac{1}{\sqrt{2}}$, $|u_2 e_2\rangle$ 의 계수에서 $bd = \frac{1}{\sqrt{2}}$, 그리고 $|u_1 e_2\rangle$ 와 $|u_2 e_1\rangle$ 의 계수에서 $ad = 0$, $bc = 0$ 이다. 네 조건을 함께 본다.

$$
ac = \frac{1}{\sqrt{2}}, \qquad bd = \frac{1}{\sqrt{2}}, \qquad ad = 0, \qquad bc = 0
$$

$ac = \frac{1}{\sqrt{2}} \neq 0$ 에서 $a \neq 0$ 이고 $c \neq 0$ 이다. 그런데 $ad = 0$ 이고 $a \neq 0$ 이므로 $d = 0$ 이어야 한다. 하지만 $bd = \frac{1}{\sqrt{2}} \neq 0$ 에서 $d \neq 0$ 이어야 한다. $d = 0$ 과 $d \neq 0$ 이 모순이다.

따라서 $|\Phi\rangle$ 는 어떤 곱 상태로도 적히지 않는 얽힌 상태다. 텐서곱 공간에는 이렇게 두 자유도가 분리되지 않게 얽힌 상태가 존재하며, 이것이 곱 공간이 두 공간의 단순 나열보다 큰 이유다. 다만 일반화 챕터에서 다루는 사슬 켓 $|\nu\rangle \otimes |e_k\rangle$ 은 곱 상태이고, 얽힘은 본 시리즈의 주제는 아니나 텐서곱 공간의 크기를 이해하기 위해 짚어 둔다.

---

### 7. 텐서곱 공간의 내적

텐서곱 공간에도 내적이 정의되며, 두 자유도의 내적의 곱으로 주어진다. 왼쪽 인자끼리, 오른쪽 인자끼리 내적을 취해 곱한다.

$$
\big(\langle a_1| \otimes \langle b_1|\big)\big(|a_2\rangle \otimes |b_2\rangle\big) = \langle a_1|a_2\rangle \cdot \langle b_1|b_2\rangle
$$

이것이 4차원 벡터의 보통 내적과 일치함을 구체 수치로 확인한다. $|a_1\rangle = |u_1\rangle$, $|b_1\rangle = |e_1\rangle$, $|a_2\rangle = |u_1\rangle$, $|b_2\rangle = |e_2\rangle$ 로 둔다. 인자별 내적의 곱을 먼저 계산한다. 표준기저의 직교 규격화 $\langle u_1|u_1\rangle = 1$, $\langle e_1|e_2\rangle = 0$ 을 쓴다.

$$
\langle u_1|u_1\rangle \cdot \langle e_1|e_2\rangle = 1 \cdot 0 = 0
$$

이제 4차원 벡터로 직접 계산한다. $|u_1 e_1\rangle = \begin{pmatrix} 1 \\ 0 \\ 0 \\ 0 \end{pmatrix}$, $|u_1 e_2\rangle = \begin{pmatrix} 0 \\ 1 \\ 0 \\ 0 \end{pmatrix}$ 이므로 둘의 내적은 성분별 곱의 합이다.

$$
\langle u_1 e_1 | u_1 e_2\rangle = 1\cdot 0 + 0\cdot 1 + 0\cdot 0 + 0\cdot 0 = 0
$$

인자별 내적의 곱과 4차원 직접 내적이 모두 0으로 일치한다. 일반적으로 텐서곱 기저 짝들은 서로 직교하며, 그 직교 규격화는 두 축의 델타의 곱으로 적힌다.

$$
\langle u_i e_j | u_k e_l \rangle = \langle u_i|u_k\rangle \cdot \langle e_j|e_l\rangle = \delta_{ik}\,\delta_{jl}
$$

유한 차원에서는 두 축 모두 크로네커 델타다. 일반화 챕터에서 왼쪽 축이 연속(위치공간)이 되면, 그 축의 크로네커 델타가 디랙 델타로 바뀌고 오른쪽 사슬 축은 크로네커 델타로 남는다. 두 축의 델타 성격이 갈리는 이 차이가 연속에서 두 자유도를 분리해 다루어야 하는 이유이며, 그 상세는 일반화 챕터에서 다룬다.

---

### 8. 붙여 쓴 표기의 구별: 텐서곱 · 합성 · 내적 · 외적

두 대상을 기호 없이 붙여 쓰는 표기는 맥락에 따라 뜻이 다르다. 판별 기준은 결과의 차원이다. 네 가지를 가른다.

**1) 두 켓의 병치 $|a\rangle|b\rangle$ — 텐서곱이다.** 2절 4)에서 보았듯 $|a\rangle \otimes |b\rangle$ 의 줄임이며, 차원이 곱해진다(2차원과 2차원이면 4차원).

**2) 두 연산자의 병치 $\hat{A}\hat{B}$ — 텐서곱이 아니라 합성(행렬곱)이다.** 같은 공간 위의 두 변환을 잇따라 적용하는 것으로, 차원이 곱해지지 않고 그대로다. $2 \times 2$ 두 행렬의 곱은 여전히 $2 \times 2$ 다.

$$
\begin{pmatrix} 1 & 2 \\ 3 & 4 \end{pmatrix}\begin{pmatrix} 5 & 6 \\ 7 & 8 \end{pmatrix} = \begin{pmatrix} 1\cdot 5 + 2\cdot 7 & 1\cdot 6 + 2\cdot 8 \\ 3\cdot 5 + 4\cdot 7 & 3\cdot 6 + 4\cdot 8 \end{pmatrix} = \begin{pmatrix} 19 & 22 \\ 43 & 50 \end{pmatrix}
$$

같은 두 행렬의 텐서곱은 3절에서 보았듯 $4 \times 4$ 가 되어 전혀 다른 대상이다. 곱은 차원 유지, 텐서곱은 차원 곱이다.

**3) 브라와 켓의 병치 $\langle a|b\rangle$ — 내적이며 스칼라(수)다.** 7절에서 다룬 내적으로, 결과가 하나의 복소수여서 차원이 1로 줄어든다.

**4) 켓과 브라의 병치 $|a\rangle\langle b|$ — 외적이며 같은 공간 위의 연산자다.** $n$ 차원 공간이면 $n \times n$ 연산자가 된다. 형식적으로 켓과 브라의 텐서곱 $|a\rangle \otimes \langle b|$ 로 볼 수 있으나, 결과가 곱 공간의 벡터가 아니라 원래 공간 위에 작용하는 연산자라는 점에서 1)과 쓰임이 다르다.

정리하면, 붙여 쓴 표기가 (왼쪽 차원) × (오른쪽 차원)의 더 큰 공간으로 가면 텐서곱이고, 같은 공간에 머물거나(합성·외적) 수로 줄어들면(내적) 텐서곱이 아니다. 본질적 구별은 텐서곱이 서로 다른 두 공간을 곱 공간으로 묶는 연산인 반면, 합성은 같은 한 공간 안에서 두 변환을 잇는 연산이라는 점이다.

---