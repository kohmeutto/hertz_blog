+++
title = "(i) LScI"
weight = 1
+++

---

### 1. LScI

Linear + Scale Invariance

---

### 2. Linearity(선형성)=Superpostion

Superposition은 Linearity 와 동치이다. 따라서, 두가지 용어를 system 에서 혼용해서 사용해도 같은 의미임을 상기하라.

$$
\text{Superposition}=\text{Addictivity}+\text{Scaling}
$$

$$
\hat{M}(a|\psi_1\rangle+b|\psi_2\rangle)
=a\hat{M}|\psi_1\rangle+b\hat{H}|\psi_2\rangle
$$

---

### 3. Scale invariance

- 축척 불변 시스템이란 시스템을 작동시키는 근본적인 규칙이 축척(입력의 확대/축소)에 따라 변하지 않는다는 의미이다.
- **'순수한 축척($a>0$)'** 에 대한 것으로, 양수만 포함한다. 음수를 포함하는 순간, 그것은 '축척' 이론이 아니라 '축척 + 반사'라는 훨씬 더 복잡한 이론이 되어버린다.
- 축척 불변성은 동일한 '형태'의 입력을 어떤 축척으로 넣든지 상관없이, 출력은 항상 똑같은 '형태'로 나온다.
- LScI 연산자 $\hat{M}$은 스케일링(scaling) 연산자 $\hat{Z}_a$와 교환가능함을 의미한다.

$$
[\hat{M},\hat{Z}_{a}]
\implies
\hat{Z}_a\hat{M}=\hat{M}\hat{Z}_a
$$

- '똑같은 형태로 나온다.'의 의미는 단지 출력의 축척이 변할 뿐이다.

$$
h(u, u')
= \frac{1}{u'}h_M(u/u')
$$

proof)

$$
\langle u^d|\hat{Z}_a\hat{M}|u'\rangle
= \langle (au)^d|\hat{M}|u'\rangle
= h(au, u')
$$

$$
\langle u^d|\hat{M}\hat{Z}_a|u'\rangle
= \frac{1}{a}\langle u^d|\hat{M}|u'/a\rangle
= \frac{1}{a}h(u, u'/a)
$$

$a$는 임의의 스케일 상수이므로 $u'$ 값을 대입할 수 있다. 

$$
h(u'u, u')
= \frac{1}{u'}h(u, 1)
$$

$u$에 대한 함수 $h_M(u)$ 를 $h_M(u):=h(u, 1)$ 이라고 새롭게 정의한다. (즉, 입력($u'$)이 1일 때의 시스템 응답을 $h_M$으로 정의)

$$
h(u, u')
= \frac{1}{u'}h_M(u/u')
$$

---

### 4. Mellin Convolution

LSI가 '일반 컨볼루션'으로 귀결되듯이, 모든 LScI 연산자는 **'멜린 컨볼루션'** 으로 귀결된다. 아래 형태는 선형이기만 하면 어떤 변환이든 표현할 수 있다.

$$
\hat{M}=\iint du du' h(u,u')|u\rangle\langle u'^d|
$$

이 일반적인 형태에 **"LScI 시스템"** 이라는 강력한 제약 조건을 걸어본다.

$$
\hat{M}
=\iint du du' \frac{1}{u'}h_M(u/u')|u\rangle\langle u'^d|
$$

임의의 벡터와 연산을 수행해보자.

$$
\langle u^d|\hat{M}|f\rangle
=\iint du'' du' \frac{1}{u'}h_M(u''/u')\langle u^d|u''\rangle\langle u'^d|f\rangle
$$

$$
=\iint du'' du' \frac{1}{u'}h_M(u''/u')\delta(u-u'') f(u')
=\int\frac{du'}{u'}h_M(u/u')f(u')
$$

$$
=:h(u)\circledast f(u)
=\langle u^d|(|h\rangle\circledast|f\rangle)
=\langle u^d|(|h\rangle\circledast)|f\rangle
$$

따라서,

$$
\hat{H} = |h\rangle\circledast
$$

