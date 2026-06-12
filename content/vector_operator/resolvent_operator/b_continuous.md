+++
title = "(b) [C] Continuous"
weight = 6
+++

---

### 1. 결함 연산자의 연속화: 사슬에서 블록으로

이산 챕터(Discrete)에서 결함 연산자는 진성 고유벡터만으로는 공간을 다 채우지 못하는 연산자였고, 모자란 자리는 일반화된 고유벡터로 메웠다. 한 고윳값에 매달린 일반화 고유벡터들은 조르당 사슬을 이루었으며, 그 사슬은 처음부터 끝까지 켓과 연산자의 관계로만 적혔다. 이 챕터는 그 결함 구조를 고윳값이 연속인 경우로 넓힌다. 출발점은 이산 챕터가 세운 사슬 관계 그 자체다.
ss
이산 챕터에는 행렬이 한 번도 나오지 않았다. 이 챕터 중간에 블록과 행렬 표기가 등장하는데, 그 표기는 사슬 관계를 연속으로 옮긴 다음 텐서곱 챕터의 규칙으로 받쳐서 들인다. 어느 단계에서도 이산 챕터에 없던 것을 근거 없이 끌어들이지 않는다.

**1) 이산 사슬 관계를 연속 고윳값으로 옮긴다**

이산 챕터의 사슬 관계를 다시 적는다. 고윳값 $\lambda_m$ 에 매달린 사슬 칸 $k$ 의 일반화 고유벡터는, 연산자가 작용하면 자기 고윳값을 돌려주고 한 칸 아래 상태를 함께 내놓는다.

$$
\hat{A}|\lambda_{m,k}\rangle = \lambda_m|\lambda_{m,k}\rangle + |\lambda_{m,k-1}\rangle \qquad (|\lambda_{m,0}\rangle = 0)
$$

이 관계에는 번호가 둘 붙어 있다. 하나는 고윳값을 가리키는 번호 $m$ 이고, 다른 하나는 사슬에서 몇 번째 칸인지 가리키는 번호 $k$ 다. 연속화는 이 둘 가운데 고윳값 번호 $m$ 하나만 연속 변수 $\nu$ 로 바꾼다. 사슬 칸 번호 $k$ 는 그대로 둔다. 사슬 칸이 왜 정수로 남는지는 §2에서 두 축을 가르며 따로 본다. 여기서는 고윳값만 연속으로 옮긴다.

$$
\hat{A}|\lambda_k(\nu)\rangle = \nu|\lambda_k(\nu)\rangle + |\lambda_{k-1}(\nu)\rangle \qquad (|\lambda_0(\nu)\rangle = 0)
$$

사슬의 첫 칸 $k=1$ 에서는 아래 칸이 없으므로($|\lambda_0(\nu)\rangle = 0$), 자기 고윳값만 돌려주는 진성 고유함수가 된다.

$$
\hat{A}|\lambda_1(\nu)\rangle = \nu|\lambda_1(\nu)\rangle
$$

여기까지 이산 챕터의 켓과 연산자 언어를 그대로 썼다. 행렬은 나오지 않았다.

**2) 사슬 켓을 텐서곱으로 적는다**

사슬 켓 하나에는 두 정보가 들어 있다. 사슬의 몇 번째 칸 $k$ 인가, 그리고 어느 고윳값 $\nu$ 에 속하는가다. 텐서곱 챕터에서 위치와 스핀처럼 성격이 다른 두 자유도를 한 켓에 담았던 것과 같은 상황이다. 두 정보는 서로 독립이다. 같은 고윳값 $\nu$ 위에 사슬 칸이 여러 개 쌓일 수 있고, 같은 칸 번호 $k$ 가 여러 고윳값에 걸쳐 나타난다. 이렇게 독립인 두 자유도를 한 켓에 묶는 연산이 텐서곱이다.

여기서 두 자유도를 어느 자리에 둘지 정한다. 사슬 칸을 왼쪽에, 고윳값을 오른쪽에 둔다. 사슬 칸이 왼쪽에 오는 까닭은, 사슬 칸이 블록의 자리(위 칸인지 아래 칸인지)를 정하고 그 자리에 고윳값 켓 $|\nu\rangle$ 가 들어가기 때문이다. 이 순서가 아래 4번에서 세울 블록 연산자, 그리고 §6의 구체 예제와 맞아떨어진다.

$$
|\lambda_k(\nu)\rangle = |e_k\rangle \otimes |\nu\rangle
$$

왼쪽 인자 $|e_k\rangle$ 는 사슬 축을 맡는다. 사슬 길이가 $K$ 이면 $|e_k\rangle$ 는 $\mathbb{C}^K$ 의 표준기저, 곧 $k$ 번째 자리만 1이고 나머지가 0인 열벡터로, 사슬의 어느 칸인지를 가리킨다. 오른쪽 인자 $|\nu\rangle$ 는 고윳값 축을 맡으며, 위치 고유켓처럼 연속 변수 $\nu$ 로 매겨진다.

구체적으로 사슬 길이 $K=2$ 에서 두 사슬 켓이 어떤 모양인지 본다. 사슬 칸 자유도는 2차원이고, 첫째 칸은 $|e_1\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix}$, 둘째 칸은 $|e_2\rangle = \begin{pmatrix} 0 \\ 1 \end{pmatrix}$ 다.

여기서 사슬 칸 기저를 표준기저로 둔 것은 가장 단순한 좌표를 고른 선택이며, 반드시 이 기저여야 하는 것은 아니다. $|e_k\rangle$ 는 사슬의 $k$ 번째 칸을 가리키는 라벨일 뿐이고, 그 라벨을 어떤 벡터로 나타낼지는 자유다. 사슬 칸 자유도의 어떤 선형독립한 두 벡터(이를테면 $\begin{pmatrix} 1 \\ 1 \end{pmatrix}$, $\begin{pmatrix} 1 \\ -1 \end{pmatrix}$)를 기저로 잡아도 같은 연산자를 표현할 수 있으며, 두 표현은 기저 변환으로 이어진다. 다만 그런 좌표에서는 강하 연산자와 블록의 모양이 복잡해져, 사슬 구조(한 칸 아래를 내놓는다는 관계)가 행렬에서 덜 또렷하게 보인다. $k$ 번째 칸을 $k$ 번째 자리만 1인 표준기저 벡터로 두면 강하 연산자가 가장 단순한 모양이 되고 사슬 구조가 행렬 위에 가장 분명히 드러나므로, 그 좌표를 고른 것이다. 이 챕터 끝의 위장 연산자 예제가 바로 표준기저가 아닌 좌표에서 본 같은 연산자의 경우다.

한 가지를 더 분명히 해 둔다. 사슬 칸 기저를 다른 기저로 바꾸면 강하 연산자 $N$ 의 모양은 달라지지만, 항등 연산자 $\hat{I}$ 의 모양은 어느 기저에서든 항등 행렬 $\begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}$ 로 똑같이 남는다. 곧 $\hat{I}$ 가 이 형태인 것은 $N$ 과 달리 선택이 아니라 필연이다. 항등 연산자는 모든 벡터를 그대로 두므로, 어떤 기저 $\{|f_k\rangle\}$ 를 잡아도 각 기저 벡터에 작용하면 자기 자신을 돌려주고($\hat{I}|f_k\rangle = |f_k\rangle$), 따라서 그 기저에서 본 행렬의 모든 열이 단위벡터가 되어 언제나 항등 행렬이다. 닮음 변환으로 보아도 $\hat{S}^{-1}\hat{I}\hat{S} = \hat{S}^{-1}\hat{S} = \hat{I}$ 이므로 좌표를 어떻게 바꿔도 불변이다. 따라서 좌표 선택에 따라 모양이 바뀌는 것은 강하 연산자 $N$ 쪽이며, 항등 $\hat{I}$ 는 좌표와 무관하다.

첫째 칸 사슬 켓을 텐서곱으로 적는다. 텐서곱 챕터 4절의 성분 쌓기(왼쪽 켓의 각 성분에 오른쪽 켓 전체를 곱한다)를 쓴다. 왼쪽 $|e_1\rangle$ 의 두 성분 1과 0 각각에 오른쪽 $|\nu\rangle$ 를 곱한다.

$$
|\lambda_1(\nu)\rangle = |e_1\rangle \otimes |\nu\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix} \otimes |\nu\rangle = \begin{pmatrix} 1 \cdot |\nu\rangle \\ 0 \cdot |\nu\rangle \end{pmatrix} = \begin{pmatrix} |\nu\rangle \\ 0 \end{pmatrix}
$$

둘째 칸 사슬 켓도 같은 규칙으로 적는다. 왼쪽 $|e_2\rangle$ 의 두 성분 0과 1 각각에 오른쪽 $|\nu\rangle$ 를 곱한다.

$$
|\lambda_2(\nu)\rangle = |e_2\rangle \otimes |\nu\rangle = \begin{pmatrix} 0 \\ 1 \end{pmatrix} \otimes |\nu\rangle = \begin{pmatrix} 0 \cdot |\nu\rangle \\ 1 \cdot |\nu\rangle \end{pmatrix} = \begin{pmatrix} 0 \\ |\nu\rangle \end{pmatrix}
$$

두 모양이 뜻하는 바는 단순하다. 사슬 칸 $|e_k\rangle$ 가 위 칸과 아래 칸 가운데 어느 자리를 쓸지 고르고, 그 자리에 고윳값 켓 $|\nu\rangle$ 가 들어간다. 첫째 칸이면 위 자리에, 둘째 칸이면 아래 자리에 $|\nu\rangle$ 가 놓이고 나머지 자리는 0이다. 이것이 사슬 켓을 텐서곱으로 적는다는 말의 구체적 의미다.

**3) 사슬 관계를 텐서곱 언어로 옮기면 합 꼴이 나온다**

1)의 사슬 관계 우변에 있는 두 항을, 2)의 텐서곱 표기로 한 항씩 옮긴다.

먼저 첫 항 $\nu|\lambda_k(\nu)\rangle$ 를 옮긴다. 텐서곱 표기로 적으면 $\nu\,(|e_k\rangle \otimes |\nu\rangle)$ 이다. 고윳값 축에 작용하는 연산자 $\hat{X}_\nu$ 를 그 작용 $\hat{X}_\nu|\nu\rangle = \nu|\nu\rangle$ 로 정의한다. 이 정의에서 좌변과 우변을 바꾼 $\nu|\nu\rangle = \hat{X}_\nu|\nu\rangle$ 를 오른쪽 인자 자리에 대입한다.

$$
\nu\,(|e_k\rangle \otimes |\nu\rangle) = |e_k\rangle \otimes (\nu|\nu\rangle) = |e_k\rangle \otimes (\hat{X}_\nu|\nu\rangle)
$$

왼쪽 인자 $|e_k\rangle$ 는 그대로 두었으므로, 항등 $\hat{I}_2$ 를 작용시킨 것($\hat{I}_2|e_k\rangle = |e_k\rangle$)으로 보고 묶는다. 그러면 텐서곱 챕터 6절의 텐서곱 연산자에서 왼쪽이 항등인 꼴이 된다.

$$
|e_k\rangle \otimes (\hat{X}_\nu|\nu\rangle) = (\hat{I}_2|e_k\rangle) \otimes (\hat{X}_\nu|\nu\rangle) = (\hat{I}_2 \otimes \hat{X}_\nu)(|e_k\rangle \otimes |\nu\rangle)
$$

다음으로 둘째 항 $|\lambda_{k-1}(\nu)\rangle$ 를 옮긴다. 텐서곱 표기로 적으면 $|e_{k-1}\rangle \otimes |\nu\rangle$ 이다. 사슬 칸을 한 칸 내리는 강하 연산자 $N$ 을 그 작용으로 정의한다.

$$
N|e_k\rangle = |e_{k-1}\rangle \quad (k \ge 2), \qquad N|e_1\rangle = 0
$$

이 정의에서 좌변과 우변을 바꾼 $|e_{k-1}\rangle = N|e_k\rangle$ 를 왼쪽 인자 자리에 대입한다.

$$
|e_{k-1}\rangle \otimes |\nu\rangle = (N|e_k\rangle) \otimes |\nu\rangle
$$

오른쪽 인자 $|\nu\rangle$ 는 그대로 두었으므로, 항등 $\hat{I}$ 를 작용시킨 것으로 보고 묶는다. 그러면 텐서곱 6절의 텐서곱 연산자에서 오른쪽이 항등인 꼴이 된다.

$$
(N|e_k\rangle) \otimes |\nu\rangle = (N|e_k\rangle) \otimes (\hat{I}|\nu\rangle) = (N \otimes \hat{I})(|e_k\rangle \otimes |\nu\rangle)
$$

두 항을 합치면, 사슬 관계의 우변 전체가 한 덩어리 연산자의 작용으로 적힌다.

$$
\hat{A}(|e_k\rangle \otimes |\nu\rangle) = (\hat{I}_2 \otimes \hat{X}_\nu)(|e_k\rangle \otimes |\nu\rangle) + (N \otimes \hat{I})(|e_k\rangle \otimes |\nu\rangle)
$$

오른쪽의 공통 켓 $(|e_k\rangle \otimes |\nu\rangle)$ 을 두 연산자 묶음 밖으로 묶는다.

$$
\hat{A}(|e_k\rangle \otimes |\nu\rangle) = (\hat{I}_2 \otimes \hat{X}_\nu + N \otimes \hat{I})(|e_k\rangle \otimes |\nu\rangle)
$$

이 식이 모든 사슬 켓 $|e_k\rangle \otimes |\nu\rangle$ 에서 성립하고, 이 켓들이 공간 전체의 기저이므로, 두 연산자가 기저 전체에서 같은 작용을 한다는 것은 연산자 자체가 같다는 뜻이다.

$$
\hat{A} = \hat{I}_2 \otimes \hat{X}_\nu + N \otimes \hat{I}
$$

이 합 꼴은 텐서곱 챕터 8절의 $\hat{A} \otimes \hat{I} + \hat{I} \otimes \hat{B}$ 와 같은 모양이다. 첫 항이 고윳값 축에만 작용하고, 둘째 항이 사슬 축에만 작용한다.

새로 들인 강하 연산자 $N$ 을 구체 행렬로 본다. 사슬 길이가 $K=2$ 이면 $N$ 은 $2\times2$ 행렬이고, $|e_2\rangle$ 를 $|e_1\rangle$ 로 내리고 $|e_1\rangle$ 을 0으로 보낸다.

$$
N = \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}
$$

작용을 직접 확인한다. $|e_2\rangle = \begin{pmatrix} 0 \\ 1 \end{pmatrix}$ 에 작용시킨다.

$$
N|e_2\rangle = \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}\begin{pmatrix} 0 \\ 1 \end{pmatrix} = \begin{pmatrix} 1 \\ 0 \end{pmatrix} = |e_1\rangle
$$

$|e_1\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix}$ 에 작용시킨다.

$$
N|e_1\rangle = \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}\begin{pmatrix} 1 \\ 0 \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \end{pmatrix} = 0
$$

한 번 더 곱하면 사슬 끝에 닿아 0이 된다.

$$
N^2 = \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}\begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix} = \begin{pmatrix} 0 & 0 \\ 0 & 0 \end{pmatrix}
$$

사슬이 더 길어도 규칙은 같다. 사슬 길이가 $K=3$ 이면 $N$ 은 $3\times3$ 이고, 한 칸씩 내린다.

$$
N = \begin{pmatrix} 0 & 1 & 0 \\ 0 & 0 & 1 \\ 0 & 0 & 0 \end{pmatrix}
$$

제곱하면 두 칸 내리는 연산자가 된다.

$$
N^2 = \begin{pmatrix} 0 & 1 & 0 \\ 0 & 0 & 1 \\ 0 & 0 & 0 \end{pmatrix}\begin{pmatrix} 0 & 1 & 0 \\ 0 & 0 & 1 \\ 0 & 0 & 0 \end{pmatrix} = \begin{pmatrix} 0 & 0 & 1 \\ 0 & 0 & 0 \\ 0 & 0 & 0 \end{pmatrix}
$$

세제곱에서 사슬 길이에 닿아 0이 된다.

$$
N^3 = \begin{pmatrix} 0 & 0 & 1 \\ 0 & 0 & 0 \\ 0 & 0 & 0 \end{pmatrix}\begin{pmatrix} 0 & 1 & 0 \\ 0 & 0 & 1 \\ 0 & 0 & 0 \end{pmatrix} = \begin{pmatrix} 0 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 0 \end{pmatrix}
$$

이 $N$ 은 이산 챕터의 멱영 연산자 $\hat{N}_m = \sum_{k=2}^{k_m}|\lambda_{m,k-1}\rangle\langle\lambda^{m,k}|$ 과 같은 일을 한다. 둘 다 사슬 칸을 한 칸 내리고, 사슬 길이만큼 거듭제곱하면 0이 된다. 이산에서 켓과 쌍대의 외적의 합으로 적었던 그 작용을, 사슬 축만 떼어 행렬로 적은 것이 $N$ 이다.

**4) 합 꼴을 행렬로 적으면 블록 연산자가 된다**

이제 합 꼴 $\hat{I}_2 \otimes \hat{X}_\nu + N \otimes \hat{I}$ 를 행렬로 적는다. 여기서 비로소 블록과 행렬 표기가 처음 나온다. 이 표기는 이산 챕터에서 다룬 적이 없으므로, 텐서곱 챕터 6절의 행렬 텐서곱 규칙(왼쪽 행렬의 각 성분에 오른쪽 행렬 전체를 곱하여 블록으로 배치)으로 받쳐서 적는다.

사슬 길이 $K=2$ 로 둔다. 첫 항 $\hat{I}_2 \otimes \hat{X}_\nu$ 를 텐서곱 6절 규칙으로 적는다. 왼쪽이 $2\times2$ 항등 $\hat{I}_2 = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}$ 이므로, 그 두 대각 성분(1과 1) 자리에 오른쪽 $\hat{X}_\nu$ 가 통째로 들어가고 비대각(0) 자리는 0이 된다.

$$
\hat{I}_2 \otimes \hat{X}_\nu = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} \otimes \hat{X}_\nu = \begin{pmatrix} \hat{X}_\nu & 0 \\ 0 & \hat{X}_\nu \end{pmatrix}
$$

둘째 항 $N \otimes \hat{I}$ 를 같은 규칙으로 적는다. 왼쪽이 $N = \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}$ 이므로, 그 단 하나뿐인 비영 성분(1행 2열의 1) 자리에 오른쪽 $\hat{I}$ 가 들어가고 나머지 자리는 0이 된다.

$$
N \otimes \hat{I} = \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix} \otimes \hat{I} = \begin{pmatrix} 0 & \hat{I} \\ 0 & 0 \end{pmatrix}
$$

두 블록을 더한다.

$$
\hat{I}_2 \otimes \hat{X}_\nu + N \otimes \hat{I} = \begin{pmatrix} \hat{X}_\nu & 0 \\ 0 & \hat{X}_\nu \end{pmatrix} + \begin{pmatrix} 0 & \hat{I} \\ 0 & 0 \end{pmatrix} = \begin{pmatrix} \hat{X}_\nu & \hat{I} \\ 0 & \hat{X}_\nu \end{pmatrix}
$$

이 행렬이 블록 연산자(또는 연산자값 행렬)다. 대각 두 칸에 고윳값 축 연산자 $\hat{X}_\nu$ 가 같이 깔리고, 우상단 한 칸에 항등 $\hat{I}$ 가 얹혀 사슬 강하를 맡는다. 우상단의 $\hat{I}$ 는 새로운 무엇이 아니라, 둘째 항 $N \otimes \hat{I}$ 에서 $N$ 의 단 하나뿐인 비영 성분 자리에 들어간 항등이다. 곧 사슬 켓을 한 칸 내리는 강하 연산자 $N$ 을 블록으로 펼친 결과다.

2번에서 사슬 켓을 $|e_k\rangle \otimes |\nu\rangle$ 로, 곧 사슬 축을 왼쪽에 두어 적었으므로, 블록 연산자에서도 사슬 축이 $2\times2$ 바깥 구조를 이루고 고윳값 축 연산자가 각 블록 안에 들어간다. 켓과 연산자의 텐서곱 순서가 같으니, 2번의 $\begin{pmatrix} |\nu\rangle \\ 0 \end{pmatrix}$, $\begin{pmatrix} 0 \\ |\nu\rangle \end{pmatrix}$ 와 이 블록이 같은 자리 약속을 쓴다.

이제부터 고윳값 축 연산자 $\hat{X}_\nu$ 의 구체 보기로 위치 연산자 $\hat{X}$ 를 쓴다. 위치 연산자는 위치 고유켓에 $\hat{X}|\nu\rangle = \nu|\nu\rangle$ 로 작용하여, $\hat{X}_\nu$ 의 정의와 같은 방식으로 움직인다. 블록 연산자를 다음으로 적는다.

$$
\hat{A} = \begin{pmatrix} \hat{X} & \hat{I} \\ 0 & \hat{X} \end{pmatrix}
$$

이 연산자가 §4 이후 연속 분해의 기본 보기이고, §6에서 구체 예제로 다시 확인한다.

**5) 블록의 위상: 출발 형태가 아니라 사슬 기저가 드러내는 정규형**

지금 세운 블록 연산자의 위상을 분명히 해 둔다. 이 블록은 "모든 연속 결함 연산자가 이렇게 생겼다"는 주장이 아니다. 이것은 이산 사슬 관계를 연속으로 옮겨 텐서곱으로 묶었을 때 나오는 가장 단순한 보기다. 일반 연산자는 처음부터 이 블록 꼴로 주어지지 않는다. 다만 사슬 구조를 가진 연산자라면, 자기 사슬 켓을 좌표축으로 삼았을 때 이 블록 꼴이 드러난다. 곧 블록은 출발 형태가 아니라 사슬 기저가 드러내는 정규형(Normal form)이며, 그 일반 명제는 §3에서 증명한다. 아래에서는 블록 꼴이 아닌 채 주어진 연산자가 사슬 기저에서 블록으로 돌아오는 구체 보기를 먼저 본다.

#### 예제: 위장된 연산자가 사슬 기저에서 드러내는 블록

다음 연산자를 본다. 네 자리가 모두 비영이라, 겉으로는 블록 꼴도 사슬 구조도 보이지 않는다.

$$
\hat{A}' = \begin{pmatrix} \hat{X}+\hat{I} & \hat{I} \\ -\hat{I} & \hat{X}-\hat{I} \end{pmatrix}
$$

아래 세 단계로, 이 연산자가 사실은 앞서 세운 블록과 같은 사슬 구조를 가지며 사슬 기저에서 같은 블록으로 돌아옴을 보인다.

*(1) 결함을 확인한다*

위치 고유켓 $|\nu\rangle$ 의 고유공간 위에서 각 자리는 숫자가 된다. 정의 $\hat{X}|\nu\rangle = \nu|\nu\rangle$ 에서 $(\hat{X}+\hat{I})|\nu\rangle = (\nu+1)|\nu\rangle$, $(\hat{X}-\hat{I})|\nu\rangle = (\nu-1)|\nu\rangle$ 이므로, 고유공간 성분에서 $\hat{A}'$ 는 숫자 행렬 $M(\nu)$ 가 된다.

$$
M(\nu) = \begin{pmatrix} \nu+1 & 1 \\ -1 & \nu-1 \end{pmatrix}
$$

고윳값을 행렬식으로 찾는다. 행렬식 정의 $\det\begin{pmatrix} a & b \\ c & d \end{pmatrix} = ad - bc$ 에 $a = \nu+1-\lambda$, $b = 1$, $c = -1$, $d = \nu-1-\lambda$ 를 대입한다.

$$
\det(M(\nu) - \lambda \hat{I}_2) = (\nu+1-\lambda)(\nu-1-\lambda) - (1)(-1)
$$

치환 $u = \nu - \lambda$ 를 대입하여 정리한다.

$$
= (u+1)(u-1) + 1 = u^2 - 1 + 1 = u^2 = (\nu-\lambda)^2
$$

이중근 $\lambda = \nu$ 다. 진성 고유벡터가 몇 개인지 보려고 $M(\nu) - \nu\hat{I}_2$ 를 적는다. 대각 성분은 $(\nu+1) - \nu = 1$ 과 $(\nu-1) - \nu = -1$ 이다.

$$
M(\nu) - \nu\hat{I}_2 = \begin{pmatrix} 1 & 1 \\ -1 & -1 \end{pmatrix}
$$

두 행이 비례하므로 랭크가 1이고, 진성 고유벡터가 하나뿐이다. 기하적 중복도 1이 대수적 중복도 2보다 작아 결함이다. 제곱을 네 성분 모두 계산한다. (1,1) 성분은 $1\cdot1 + 1\cdot(-1) = 0$, (1,2) 성분은 $1\cdot1 + 1\cdot(-1) = 0$, (2,1) 성분은 $(-1)\cdot1 + (-1)\cdot(-1) = 0$, (2,2) 성분은 $(-1)\cdot1 + (-1)\cdot(-1) = 0$ 이다.

$$
(M(\nu) - \nu\hat{I}_2)^2 = \begin{pmatrix} 0 & 0 \\ 0 & 0 \end{pmatrix}
$$

모든 $\nu$ 에서 2칸 사슬의 결함이다.

*(2) 사슬 켓을 찾는다*

진성 고유켓(첫째 칸)을 $|\lambda_1(\nu)\rangle = \begin{pmatrix} |\nu\rangle \\ -|\nu\rangle \end{pmatrix}$ 로 둔다. 작용을 성분별로 계산한다. 첫 성분은 $(\hat{X}+\hat{I})|\nu\rangle + \hat{I}(-|\nu\rangle) = (\nu+1)|\nu\rangle - |\nu\rangle = \nu|\nu\rangle$ 이고, 둘째 성분은 $-\hat{I}|\nu\rangle + (\hat{X}-\hat{I})(-|\nu\rangle) = -|\nu\rangle - (\nu-1)|\nu\rangle = -\nu|\nu\rangle$ 이다.

$$
\hat{A}'|\lambda_1(\nu)\rangle = \begin{pmatrix} \nu|\nu\rangle \\ -\nu|\nu\rangle \end{pmatrix} = \nu|\lambda_1(\nu)\rangle
$$

자기 고윳값 $\nu$ 만 돌려주므로 진성 고유켓이 맞다. 둘째 칸을 $|\lambda_2(\nu)\rangle = \begin{pmatrix} |\nu\rangle \\ 0 \end{pmatrix}$ 로 둔다. 작용의 첫 성분은 $(\hat{X}+\hat{I})|\nu\rangle + \hat{I}\cdot 0 = (\nu+1)|\nu\rangle$ 이고, 둘째 성분은 $-\hat{I}|\nu\rangle + (\hat{X}-\hat{I})\cdot 0 = -|\nu\rangle$ 이다.

$$
\hat{A}'|\lambda_2(\nu)\rangle = \begin{pmatrix} (\nu+1)|\nu\rangle \\ -|\nu\rangle \end{pmatrix}
$$

이 결과가 사슬 관계 $\nu|\lambda_2(\nu)\rangle + |\lambda_1(\nu)\rangle$ 와 같은지, 우변을 직접 더해 맞춘다.

$$
\nu|\lambda_2(\nu)\rangle + |\lambda_1(\nu)\rangle = \nu\begin{pmatrix} |\nu\rangle \\ 0 \end{pmatrix} + \begin{pmatrix} |\nu\rangle \\ -|\nu\rangle \end{pmatrix} = \begin{pmatrix} \nu|\nu\rangle + |\nu\rangle \\ -|\nu\rangle \end{pmatrix} = \begin{pmatrix} (\nu+1)|\nu\rangle \\ -|\nu\rangle \end{pmatrix}
$$

좌변과 우변이 같다.

$$
\hat{A}'|\lambda_2(\nu)\rangle = \nu|\lambda_2(\nu)\rangle + |\lambda_1(\nu)\rangle
$$

이산 사슬 관계, 곧 자기 고윳값을 돌려주고 한 칸 아래를 내놓는 관계가 연속 변수 $\nu$ 위에서 그대로 성립한다.

*(3) 사슬 켓을 좌표축으로 삼으면 블록이 드러난다*

이제 (2)에서 찾은 두 사슬 켓 $|\lambda_1(\nu)\rangle$ 과 $|\lambda_2(\nu)\rangle$ 자체를 좌표축으로 삼는다. 어떤 켓이든 자기 자신을 축으로 쓰면 그 축에서는 한 자리만 1인 표준 단위 벡터가 되므로, 이 새 좌표에서 두 사슬 켓은 다음과 같다.

$$
|\lambda_1(\nu)\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix}, \qquad |\lambda_2(\nu)\rangle = \begin{pmatrix} 0 \\ 1 \end{pmatrix}
$$

연산자의 행렬은 각 좌표축에 연산자를 작용시킨 결과를 열에 세워 만든다. 첫째 열은 첫째 축 $|\lambda_1(\nu)\rangle$ 에 작용한 결과를 이 좌표로 적은 것이다. (2)에서 $\hat{A}'|\lambda_1(\nu)\rangle = \nu|\lambda_1(\nu)\rangle$ 였으므로, 새 좌표에서 첫째 축이 $\begin{pmatrix} 1 \\ 0 \end{pmatrix}$ 라는 것을 대입한다.

$$
\hat{A}'|\lambda_1(\nu)\rangle = \nu|\lambda_1(\nu)\rangle = \nu\begin{pmatrix} 1 \\ 0 \end{pmatrix} = \begin{pmatrix} \nu \\ 0 \end{pmatrix} \qquad (\text{첫째 열})
$$

둘째 열은 둘째 축 $|\lambda_2(\nu)\rangle$ 에 작용한 결과를 이 좌표로 적은 것이다. (2)에서 $\hat{A}'|\lambda_2(\nu)\rangle = \nu|\lambda_2(\nu)\rangle + |\lambda_1(\nu)\rangle$ 였으므로, 새 좌표에서 둘째 축이 $\begin{pmatrix} 0 \\ 1 \end{pmatrix}$, 첫째 축이 $\begin{pmatrix} 1 \\ 0 \end{pmatrix}$ 라는 것을 대입한다.

$$
\hat{A}'|\lambda_2(\nu)\rangle = \nu|\lambda_2(\nu)\rangle + |\lambda_1(\nu)\rangle = \nu\begin{pmatrix} 0 \\ 1 \end{pmatrix} + \begin{pmatrix} 1 \\ 0 \end{pmatrix} = \begin{pmatrix} 1 \\ \nu \end{pmatrix} \qquad (\text{둘째 열})
$$

두 열을 세워 사슬 기저에서 본 $\hat{A}'$ 의 행렬을 적는다.

$$
\hat{A}' = \begin{pmatrix} \nu & 1 \\ 0 & \nu \end{pmatrix} \qquad (\text{사슬 기저 좌표})
$$

이것이 4)에서 합 꼴로 세운 블록 $\begin{pmatrix} \hat{X} & \hat{I} \\ 0 & \hat{X} \end{pmatrix}$ 를 고유공간 $|\nu\rangle$ 에서 본 모습($\hat{X} \to \nu$)과 같다. 처음 주어진 좌표에서는 네 자리가 모두 차서 가려져 있던 블록 구조가, 사슬 켓을 좌표축으로 바꾸자 드러났다. 여기서 어떤 변환 행렬도 곱하지 않았다. (2)에서 이미 확인한 사슬 관계를 새 좌표에서 그대로 읽었을 뿐이다. 이 읽기가 §3에서 증명할 정규형 명제, 곧 "사슬 관계는 사슬 기저에서 블록"이라는 일반 명제를 이 예제에 적용한 구체 보기다.

이 예제의 교훈을 적는다. 일반 연산자는 블록 꼴로 주어지지 않으며, 사슬 켓을 찾아야 비로소 블록이 드러난다. 그런데 사슬 켓을 직접 푸는 일은 일반적으로 거의 불가능한 역문제다. 챕터 Resolvent가 레졸번트를 도구로 세우는 까닭이 그것이고, 지금 본 블록 연산자는 그 역문제가 이미 풀린 경우, 곧 사슬 기저가 처음부터 표준 기저인 가장 단순한 보기다.

---

---

### 1. 연산자값 행렬과 블록 구조의 연속화

이산 공간에서의 결함 연산자는 조르당 사슬(Jordan chain)을 따라 일반화된 고유벡터로 분해되며, 그 구조는 유한 차원의 행렬로 표현된다. 연속 스펙트럼으로 확장하기 위해 행렬의 원소에 스칼라가 아닌 연산자를 대입하는 구조를 정의한다. 이 접근은 고윳값이 연속으로 분포하는 과정과 사슬 구조가 유지되는 과정을 대수적으로 분리하여 기술한다.

두 상태 켓을 배열한 열 벡터 $|\Psi\rangle = \begin{pmatrix} |\psi_1\rangle \\ |\psi_2\rangle \end{pmatrix}$ 에 작용하며 대각 원소가 위치 연산자 $\hat{X}$ (위치 고유켓에 대하여 $\hat{X}|\nu\rangle = \nu|\nu\rangle$)인 블록 연산자(Block operator)를 다음과 같이 정의한다.

$$
\hat{A} = \begin{pmatrix} \hat{X} & \hat{I} \\ 0 & \hat{X} \end{pmatrix}
$$

이 블록 연산자는 연속 연산자 $\hat{X}$ 와 $2\times2$ 행렬의 텐서곱의 합으로 분해된다.

$$
\hat{A} = \hat{X} \otimes \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} + \hat{I} \otimes \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}
$$

분해의 타당성을 검증하기 위해 각 항을 전개한다. 첫 번째 항은 대각 성분에 $\hat{X}$ 를 배치한다.

$$
\hat{X} \otimes \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} \hat{X} & 0 \\ 0 & \hat{X} \end{pmatrix}
$$

두 번째 항은 우상단 비대각 성분에 항등 연산자 $\hat{I}$ 를 배치한다.

$$
\hat{I} \otimes \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix} = \begin{pmatrix} 0 & \hat{I} \\ 0 & 0 \end{pmatrix}
$$

두 항을 합산하면 본래의 블록 연산자가 대수적 오차 없이 복원된다.

$$
\begin{pmatrix} \hat{X} & 0 \\ 0 & \hat{X} \end{pmatrix} + \begin{pmatrix} 0 & \hat{I} \\ 0 & 0 \end{pmatrix} = \begin{pmatrix} \hat{X} & \hat{I} \\ 0 & \hat{X} \end{pmatrix}
$$

행렬 원소에 연산자를 대입하는 것은 연속 연산자와 유한 차원 이산 행렬을 텐서곱 공간으로 확장하는 것을 의미한다. 임의의 연속 결함 연산자가 반드시 이 형태로 주어지는 것은 아니지만, 사슬 기저(Chain basis)를 통해 텐서곱 형태의 정규형(Normal form)으로 변환할 수 있다.

---

### 2. 스펙트럼 인덱스의 분리: 연속 고윳값과 이산 멱영 지수

연산자의 텐서곱 분해는 비정규 연산자의 상태를 구성하는 두 종류의 독립적인 인덱스를 대수적으로 분리한다. 연속 특성과 이산 특성은 각기 다른 축을 통해 발현된다.

첫째, 고윳값 축이다. 텐서곱의 첫 번째 인자로 부여된 위치 연산자 $\hat{X}$ 가 이 축을 구성한다. 고윳값은 임의의 실수 $\nu$ (또는 복소 공간의 측도를 따르는 연속 변수)로 주어지며, 스펙트럼의 연속성을 결정한다.

둘째, 사슬 축이다. 텐서곱의 두 번째 인자로 부여된 유한 행렬이 이 축을 구성한다. 사슬 축은 특정 고윳값에 종속된 조르당 사슬 내에서 상태의 랭크 인덱스 $k$ 를 지시한다. 대수적 결핍에 의해 발생하는 사슬의 길이는 본질적으로 유한한 정수이므로 고윳값의 연속성과 무관하게 항상 이산적인 특성을 유지한다.

이산 스펙트럼에서는 두 인덱스가 모두 이산 변수 $m, k$ 로 주어졌다.

$$
|\lambda_{m,k}\rangle \quad (m: \text{이산 고윳값},\ k: \text{이산 사슬 칸})
$$

연속 공간에서는 고윳값 인덱스가 연속 변수 $\nu$ 로 치환되며 사슬 인덱스 $k$ 는 유지된다.

$$
|\lambda_k(\nu)\rangle \quad (\nu: \text{연속 고윳값},\ k: \text{이산 사슬 칸})
$$

이에 따라 고윳값 축에 대한 합산은 적분 $\int d\nu$ 로 변환되는 반면, 사슬 축에 대한 합산 $\sum_k$ 는 이산 공간의 형태를 동일하게 유지한다.

---

### 3. 연속 공간의 일반화된 고유함수 사슬

연속 변수 $\nu$ 에 종속된 일반화된 고유함수 사슬의 지배 방정식은 이산 공간에서의 랭크 강하 원리를 따른다. 사슬 인덱스 $k$ 의 상태에 연산자가 작용할 경우 고윳값 $\nu$ 를 반환함과 동시에 랭크가 1만큼 강하된 상태 $|\lambda_{k-1}(\nu)\rangle$ 를 유발한다.

$$
\hat{A}|\lambda_k(\nu)\rangle = \nu|\lambda_k(\nu)\rangle + |\lambda_{k-1}(\nu)\rangle \quad (\text{단, } |\lambda_0(\nu)\rangle = 0,\ 1 \le k \le k(\nu))
$$

첫 번째 랭크 $k=1$ 에서는 강하할 하위 상태가 존재하지 않으므로 진성 고유함수(True eigenfunction)로 작용한다.

$$
\hat{A}|\lambda_1(\nu)\rangle = \nu|\lambda_1(\nu)\rangle
$$

결함 연산자의 사슬 기저는 자기 수반성을 가지지 않아 스스로 직교하지 않는다. 대수적 분해를 성립시키기 위해 표준 수반 벡터(Standard adjoint vector)와 구별되는 쌍대 기저(Bi-dual basis)를 도입한다. 복소 공간의 측도를 반영한 이중-브라(Dual-bra) 표기법 $\langle \lambda^{d,k}(\nu)|$ 를 적용하여 직교 규격화 조건을 다음과 같이 정의한다.

$$
\langle \lambda^{d,j}(\nu')|\lambda_k(\nu)\rangle = \delta^j_k\,\delta(\nu - \nu')
$$

사슬 축에 대해서는 크로네커 델타 $\delta^j_k$ 가 적용되고 고윳값 축에 대해서는 디랙 델타 $\delta(\nu - \nu')$ 가 적용되어 두 축의 직교성이 단일 수식으로 기술된다.

**명제: 사슬 기저에서의 정규형 구조**

다음 두 가지 가정을 전제로 한다.
1. 완전성(Completeness): 사슬 켓 $\{|\lambda_k(\nu)\rangle\}$ 과 쌍대 브라 $\{\langle\lambda^{d,k}(\nu)|\}$ 가 힐베르트 공간 전체를 포괄하는 완전계를 이룬다.
2. 균일성(Uniformity): 사슬 길이 $k(\nu) = K$ 가 전체 연속 스펙트럼 구간에서 일정하다.

위 가정 하에 연산자 $\hat{A}$ 의 사슬 기저 좌표 표현은 텐서곱 기반의 블록 행렬 정규형과 일치한다.

$$
\hat{A} = \hat{X}_\nu \otimes I_K + \hat{I} \otimes N
$$

여기서 $\hat{X}_\nu$ 는 연속 라벨 연산자($\hat{X}_\nu|\nu\rangle = \nu|\nu\rangle$)이며, $N$ 은 $K \times K$ 차원의 단일 강하 행렬($N|e_k\rangle = |e_{k-1}\rangle$, $N|e_1\rangle = 0$)이다.

proof)

사슬 켓을 보조 라벨 켓 $|\nu\rangle$ 과 $\mathbb{C}^K$ 의 표준기저 $|e_k\rangle$ 의 텐서곱 공간에 대응시킨다.

$$
|\lambda_k(\nu)\rangle \;\leftrightarrow\; |\nu\rangle \otimes |e_k\rangle
$$

지배 방정식의 우변 첫 번째 항에서 스칼라 $\nu$ 의 곱은 라벨 연산자 $\hat{X}_\nu$ 의 작용으로 치환된다.

$$
\nu\,(|\nu\rangle \otimes |e_k\rangle) = (\hat{X}_\nu|\nu\rangle) \otimes |e_k\rangle = (\hat{X}_\nu \otimes I_K)\,(|\nu\rangle \otimes |e_k\rangle)
$$

우변 두 번째 항에서 상태의 랭크 강하는 단일 강하 행렬 $N$ 의 작용으로 치환된다.

$$
|\nu\rangle \otimes |e_{k-1}\rangle = |\nu\rangle \otimes (N|e_k\rangle) = (\hat{I} \otimes N)\,(|\nu\rangle \otimes |e_k\rangle)
$$

두 항을 합산하여 텐서곱 공간에서의 연산자 작용을 도출한다.

$$
\hat{A}\,(|\nu\rangle \otimes |e_k\rangle) = \left(\hat{X}_\nu \otimes I_K + \hat{I} \otimes N\right)(|\nu\rangle \otimes |e_k\rangle)
$$

가정된 기저의 완전성에 의해 기저 전체에서의 작용 일치는 연산자 동등성으로 귀결된다. 사슬 기저가 직교 기저가 아니므로 이 동등성은 유니터리 동치가 아닌 닮음(Similarity) 동치이다.

---

### 4. 연속 스펙트럼 연산자 분해

연속 공간에서는 개별 상태가 아닌 측도 $d\nu$ 를 포함한 밀도(Density) 연산자가 기본 대수 단위로 기능한다. 이산 공간의 사영 연산자와 멱영 연산자에 대응하는 연속 밀도를 다음과 같이 정의한다.

$$
d\hat{P}(\nu) = d\nu \sum_{k=1}^{k(\nu)} |\lambda_k(\nu)\rangle\langle \lambda^{d,k}(\nu)|
$$

$$
d\hat{N}(\nu) = d\nu \sum_{k=2}^{k(\nu)} |\lambda_{k-1}(\nu)\rangle\langle \lambda^{d,k}(\nu)|
$$

**1) 분해 항등식**

$$
\hat{A}\,d\hat{P}(\nu) = \nu\, d\hat{P}(\nu) + d\hat{N}(\nu)
$$

proof)

임의의 랭크 $k$ 의 지배 방정식 우측에 이중-브라 쌍대 기저 $\langle \lambda^{d,k}(\nu)|$ 를 외적(Outer product)한다.

$$
\hat{A}|\lambda_k(\nu)\rangle\langle \lambda^{d,k}(\nu)| = \nu|\lambda_k(\nu)\rangle\langle \lambda^{d,k}(\nu)| + |\lambda_{k-1}(\nu)\rangle\langle \lambda^{d,k}(\nu)|
$$

고윳값 $\nu$ 에 대응하는 전체 랭크에 대하여 합산($\sum_{k=1}^{k(\nu)}$)한다. 하위 랭크 상태가 존재하지 않는 $|\lambda_0(\nu)\rangle = 0$ 조건을 반영하여 우변 두 번째 항의 시작 인덱스를 $k=2$ 로 조정한다.

$$
\hat{A}\sum_{k=1}^{k(\nu)}|\lambda_k(\nu)\rangle\langle \lambda^{d,k}(\nu)| = \nu \sum_{k=1}^{k(\nu)}|\lambda_k(\nu)\rangle\langle \lambda^{d,k}(\nu)| + \sum_{k=2}^{k(\nu)}|\lambda_{k-1}(\nu)\rangle\langle \lambda^{d,k}(\nu)|
$$

양변에 측도 $d\nu$ 를 곱한다.

$$
\hat{A}\,d\nu\sum_{k=1}^{k(\nu)}|\lambda_k(\nu)\rangle\langle \lambda^{d,k}(\nu)| = \nu\, d\nu \sum_{k=1}^{k(\nu)}|\lambda_k(\nu)\rangle\langle \lambda^{d,k}(\nu)| + d\nu\sum_{k=2}^{k(\nu)}|\lambda_{k-1}(\nu)\rangle\langle \lambda^{d,k}(\nu)|
$$

각 합산 항을 기정의된 사영 밀도 $d\hat{P}(\nu)$ 와 멱영 밀도 $d\hat{N}(\nu)$ 로 치환하여 항등식을 완성한다.

$$
\hat{A}\,d\hat{P}(\nu) = \nu\, d\hat{P}(\nu) + d\hat{N}(\nu)
$$

**2) 연산자의 복원**

$$
\hat{A} = \int_{\Omega} \big[ \nu\, d\hat{P}(\nu) + d\hat{N}(\nu) \big]
$$

proof)

사영 밀도를 전체 스펙트럼 구간 $\Omega$ 에 대하여 적분하면 완비성 조건에 의해 항등 연산자가 도출된다.

$$
\int_{\Omega} d\hat{P}(\nu) = \hat{I}
$$

대상 연산자 $\hat{A}$ 에 항등 연산자를 곱하고 적분식으로 치환한다.

$$
\hat{A} = \hat{A}\,\hat{I} = \hat{A}\int_{\Omega} d\hat{P}(\nu) = \int_{\Omega} \hat{A}\,d\hat{P}(\nu)
$$

적분 내부 항에 앞서 증명한 분해 항등식을 대입한다.

$$
\hat{A} = \int_{\Omega} \big[ \nu\, d\hat{P}(\nu) + d\hat{N}(\nu) \big]
$$

**3) 고차 멱영 밀도 정의**

레졸번트 전개에 요구되는 고차극 항에 대응하기 위해, 거듭제곱된 멱영 연산자의 연속 확장인 $j$ 칸 강하 밀도 $d\hat{N}_j(\nu)$ 를 정의한다.

$$
d\hat{N}_j(\nu) = d\nu \sum_{k=j+1}^{k(\nu)} |\lambda_{k-j}(\nu)\rangle\langle \lambda^{d,k}(\nu)| \qquad (j = 0, 1, 2, \ldots)
$$

$j=0$ 인 경우 사영 밀도 $d\hat{P}(\nu)$ 와 일치하며, $j=1$ 인 경우 멱영 밀도 $d\hat{N}(\nu)$ 와 일치한다. 강하 횟수 $j$ 가 사슬 길이 $k(\nu)$ 에 도달하면 합산의 초기 조건이 상한을 초과하여 영연산자로 소멸한다.

$$
d\hat{N}_j(\nu) = \hat{0} \quad (j \geq k(\nu))
$$

**4) 밀도 직교성 및 합성 규칙**

$$
d\hat{N}_i(\nu)\, d\hat{N}_j(\nu') = \delta(\nu - \nu')\, d\hat{N}_{i+j}(\nu)\, d\nu' \qquad (i, j \geq 0)
$$

proof)

서로 다른 관측점 $\nu, \nu'$ 에 대한 두 밀도의 곱을 전개한다.

$$
d\hat{N}_i(\nu)\, d\hat{N}_j(\nu') = d\nu\, d\nu' \sum_{k=i+1}^{k(\nu)}\sum_{k'=j+1}^{k(\nu')} |\lambda_{k-i}(\nu)\rangle\,\langle \lambda^{d,k}(\nu)|\lambda_{k'-j}(\nu')\rangle\,\langle \lambda^{d,k'}(\nu')|
$$

내적 항에 쌍대 직교 규격화 조건 $\langle \lambda^{d,k}(\nu)|\lambda_{k'-j}(\nu')\rangle = \delta^{k}_{k'-j}\,\delta(\nu - \nu')$ 를 적용한다. 크로네커 델타에 의해 $k = k' - j$ 조건을 만족하는 항만 잔존한다. 이 과정에서 $k$ 의 범위 $k \geq i+1$ 은 $k' \geq i+j+1$ 로 변환된다.

$$
d\hat{N}_i(\nu)\, d\hat{N}_j(\nu') = \delta(\nu - \nu')\, d\nu\, d\nu' \sum_{k'=i+j+1}^{k(\nu)} |\lambda_{k'-(i+j)}(\nu)\rangle\langle \lambda^{d,k'}(\nu')|
$$

디랙 델타 $\delta(\nu - \nu')$ 가 적분 하에서 $\nu' = \nu$ 를 강제하므로 측도와 델타 함수를 분리하여 재결합한다.

$$
d\hat{N}_i(\nu)\, d\hat{N}_j(\nu') = \delta(\nu - \nu')\, d\nu' \left[ d\nu \sum_{k'=i+j+1}^{k(\nu)} |\lambda_{k'-(i+j)}(\nu)\rangle\langle \lambda^{d,k'}(\nu)| \right]
$$

대괄호 내부의 수식은 정의에 따라 강하 수가 $i+j$ 인 밀도 $d\hat{N}_{i+j}(\nu)$ 와 정확히 일치한다.

---

### 5. 대수적 특성에 따른 연속 스펙트럼 분류

텐서곱으로 분리된 행렬 성분의 대수적 구조에 따라 연속 스펙트럼은 세 가지 형태로 분류된다.

**1) 비축퇴 (Non-degenerate)**

행렬 성분이 $1\times1$ 스칼라이거나 부재하는 경우이다. 랭크 강하 항이 존재하지 않으며 각 고윳값에 단일 진성 고유함수만이 대응된다.

$$
\hat{A}|\nu\rangle = \nu|\nu\rangle
$$

멱영 밀도는 소멸하고 사영 밀도만 잔존한다.

$$
d\hat{P}(\nu) = d\nu\,|\nu\rangle\langle \nu^d|, \qquad d\hat{N}(\nu) = \hat{0}
$$

**2) 축퇴 (Degenerate)**

행렬 성분이 2차원 이상이나 대각화가 가능한 경우이다. 동일한 고윳값 $\nu$ 를 공유하는 다수의 진성 고유함수가 존재하며 이들은 상호 독립적이다. 랭크 강하 항은 존재하지 않는다.

$$
\hat{A}|\lambda_k(\nu)\rangle = \nu|\lambda_k(\nu)\rangle \quad (\text{모든 } k)
$$

사영 밀도는 여러 항의 합으로 구성되나 멱영 밀도는 0이다.

$$
d\hat{P}(\nu) = d\nu \sum_{k=1}^{k(\nu)} |\lambda_k(\nu)\rangle\langle \lambda^{d,k}(\nu)|, \qquad d\hat{N}(\nu) = \hat{0}
$$

**3) 결함 (Defective)**

행렬 성분이 대각화 불가능한 조르당 결함을 포함하는 경우이다. 비로소 하위 랭크 상태를 유발하는 사슬 구조가 형성되며 멱영 밀도가 비자명 연산자로 발현된다.

$$
d\hat{N}(\nu) = d\nu \sum_{k=2}^{k(\nu)} |\lambda_{k-1}(\nu)\rangle\langle \lambda^{d,k}(\nu)| \neq \hat{0}
$$

자기 수반(에르미트) 연산자는 결함 구조를 취할 수 없으므로 항상 멱영 밀도가 0으로 수렴한다. 결함과 멱영 밀도의 발현은 비자기 수반 연산자의 고유한 특성이다.

---

### 6. 대수적 구조의 교차 검증 (예제)

스펙트럼의 세 가지 분류를 구체적인 연산자를 통해 해석적으로 검증한다.

#### 6-1. 위치 연산자 (비축퇴)

무한 차원 힐베르트 공간 $L^2(\mathbb{R})$ 에 작용하는 위치 연산자 $\hat{X}$ 에 대하여 고유 방정식은 $\hat{X}|\nu\rangle = \nu|\nu\rangle$ 로 주어진다. 직교 관계는 $\langle \nu'|\nu\rangle = \delta(\nu - \nu')$ 이다. 사슬 인덱스가 단일하므로 사영 밀도는 단일 외적이다.

$$
d\hat{P}(\nu) = d\nu\,|\nu\rangle\langle \nu|
$$

멱영 밀도는 $\hat{0}$ 이며, 연산자 복원은 대수적 오차 없이 성립한다.

$$
\int_{-\infty}^{\infty} \nu\, d\hat{P}(\nu) = \int_{-\infty}^{\infty} \nu\,|\nu\rangle\langle \nu|\, d\nu = \hat{X}
$$

#### 6-2. 대각 블록 연산자 (축퇴)

두 성분에 동일하게 작용하는 대각 연산자를 구성한다.

$$
\hat{A} = \begin{pmatrix} \hat{X} & 0 \\ 0 & \hat{X} \end{pmatrix}
$$

텐서곱 기반의 두 상태 $|\lambda_1(\nu)\rangle = \begin{pmatrix} |\nu\rangle \\ 0 \end{pmatrix}$, $|\lambda_2(\nu)\rangle = \begin{pmatrix} 0 \\ |\nu\rangle \end{pmatrix}$ 를 각기 작용시킨 결과는 다음과 같다.

$$
\hat{A}|\lambda_1(\nu)\rangle = \begin{pmatrix} \hat{X}|\nu\rangle \\ 0 \end{pmatrix} = \nu|\lambda_1(\nu)\rangle, \qquad \hat{A}|\lambda_2(\nu)\rangle = \begin{pmatrix} 0 \\ \hat{X}|\nu\rangle \end{pmatrix} = \nu|\lambda_2(\nu)\rangle
$$

랭크 강하 항이 부재하며 독립적인 2겹 축퇴 공간을 형성한다.

$$
d\hat{P}(\nu) = d\nu\left( |\lambda_1(\nu)\rangle\langle \lambda^{d,1}(\nu)| + |\lambda_2(\nu)\rangle\langle \lambda^{d,2}(\nu)| \right), \qquad d\hat{N}(\nu) = \hat{0}
$$

#### 6-3. 비대각 결함 연산자 좌표 변환 (결함)

비대각 성분에 항등 연산자가 위치한 연산자를 구성한다.

$$
\hat{A} = \begin{pmatrix} \hat{X} & \hat{I} \\ 0 & \hat{X} \end{pmatrix}
$$

동일한 상태 $|\lambda_1(\nu)\rangle$, $|\lambda_2(\nu)\rangle$ 를 적용한다. 첫 번째 상태는 진성 고유함수이다.

$$
\hat{A}|\lambda_1(\nu)\rangle = \begin{pmatrix} \hat{X}|\nu\rangle \\ 0 \end{pmatrix} = \nu|\lambda_1(\nu)\rangle
$$

두 번째 상태에 작용할 경우 비대각 $\hat{I}$ 성분에 의해 랭크 강하가 발생한다.

$$
\hat{A}|\lambda_2(\nu)\rangle = \begin{pmatrix} \hat{X} & \hat{I} \\ 0 & \hat{X} \end{pmatrix}\begin{pmatrix} 0 \\ |\nu\rangle \end{pmatrix} = \begin{pmatrix} |\nu\rangle \\ \nu|\nu\rangle \end{pmatrix} = \nu|\lambda_2(\nu)\rangle + |\lambda_1(\nu)\rangle
$$

이 연산자는 자기 고윳값과 더불어 하위 상태를 유발하는 결함 구조를 지닌다. 사영 밀도와 멱영 밀도는 다음과 같이 확정된다.

$$
d\hat{P}(\nu) = d\nu\left( |\lambda_1(\nu)\rangle\langle \lambda^{d,1}(\nu)| + |\lambda_2(\nu)\rangle\langle \lambda^{d,2}(\nu)| \right)
$$

$$
d\hat{N}(\nu) = d\nu\,|\lambda_1(\nu)\rangle\langle \lambda^{d,2}(\nu)|
$$

멱영 밀도의 작용을 단일 상태에 적용하여 규명한다.

$$
d\hat{N}(\nu)\,|\lambda_2(\nu')\rangle = d\nu\,|\lambda_1(\nu)\rangle\langle \lambda^{d,2}(\nu)|\lambda_2(\nu')\rangle = d\nu\,|\lambda_1(\nu)\rangle\,\delta(\nu - \nu')
$$

이산 조르당 블록에서의 멱영 특성이 연속 공간 상의 모든 $\nu$ 좌표에서 구조적으로 발현됨이 증명된다. 일반적인 좌표계에서 대각과 멱영부의 분리가 가시적이지 않은 형태(예: 네 원소가 모두 비영인 행렬)로 주어지는 결함 연산자라 할지라도, 그 사슬 구조에 대한 역행렬 닮음 변환(Similarity transform)을 거치면 필연적으로 상기 서술된 블록 텐서곱 정규형으로 환원된다.