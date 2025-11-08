+++
title = "(a) Mellin transform I"
weight = 2
+++

---

### 1. Eigenvector & eigenvalue of LScI systems

연산자 $|h\rangle\circledast$ 의 고유값과 고유벡터

$$
\text{eigenvalue}: \langle s^M|=\int_{0}^{\infty} \frac{dx}{x} x^{s} \langle x^d|\implies\langle s^M|m\rangle=\int_{0}^{\infty} \frac{dx}{x}x^{s}m(x),\quad \langle s^M|x\rangle=\frac{1}{x}x^{s}
$$

$$
\text{eigenvector}:
|s\rangle_M=\int_0^\infty dx \, x^{-s} |x\rangle
\implies\langle x^d|s\rangle_M=x^{-s}
$$

proof)

$$
|m\rangle\circledast|s\rangle=M(s)|s\rangle
$$

$$
\langle x^d|(|h\rangle\circledast)|s\rangle
=M(s)\langle x^d|s\rangle
$$

위의 식을 토대로,

$$
\langle x^d|(|h\rangle\circledast)|s\rangle
=\langle x^d|\left\{\int^{\infty}_{0}\frac{dx'}{x'}|h_M(x/x')\rangle\langle x'^d|\right\} |s\rangle_M
=\int^{\infty}_{0}\frac{dx'}{x'}h(x/x')\langle x'^d|s\rangle_M
$$

$\langle x'^d|s\rangle_M=(x')^{-s}$ 라고 하면,

$$
=\int^{\infty}_{0}\frac{dx'}{x'}h_M(x/x')(x')^{-s}
$$

$x/x'=u$ 라고 하면,

$$
=\int^{0}_{\infty}-\frac{x'}{x}duh_M(u)(x/u)^{-s}
=\int^{\infty}_{0}\frac{du}{u}h_M(u)u^{s}x^{-s}
$$

**고유값을 멜린 변환** 이라고 하며, **추출(변환) 연산자** 로 표현해 보자.

$$
\langle s^M|=\int_{0}^{\infty} \frac{dx}{x} x^{s} \langle x^d|
$$

---

### 2. "$|s\rangle_M$" & "$\langle s^M|$" & "$\langle s^{M,d}|$

**(1) $|s\rangle\_M$ 은 비직교 기저**

proof)

$$
\langle s|s'\rangle_M
=\langle s|\hat{I}|s'\rangle_M
=\langle s|\left\{\int dx |x\rangle\langle x^d|\right\}|s'\rangle_M
=\int dx \langle s|x\rangle x^{-s}
$$

$|x\rangle$ 을 표준기저이므로,

$$
=\int dx \langle x|s\rangle^\ast x^{-s}
=\int dx x^{-(s^\ast+s)}
$$

$s^\ast+s$의 실수부가 $\sigma\ne 0$ 라면, 적분값이 존재하지 않음, $|s\rangle\$은 비직교 기저

**(2) $\langle s^M|$ & $\langle s^{M,d}|$**

$$
\langle s^M|s'\rangle=2\pi i\delta(s-s'),\quad
\langle s^{M,d}|=\frac{1}{2\pi i}\langle s^M|
$$

proof)

$$
\langle s^M|s'\rangle
=\int \frac{dx}{x} x^s \langle x^d|s'\rangle
=\int \frac{dx}{x} x^{s-s'}
$$

$x=e^t$로 놓고, 브롬위치 적분을 사용하면,

$$
=2\pi i\delta(s-s')
$$

따라서,

$$
\langle s^{M,d}|=\frac{1}{2\pi i}\langle s^M|
$$

---

### 3. 스팩트럼 분해

벡터 $|h\rangle$는 **'설계도(DNA)'** 이고, 연산자 $|h\rangle\circledast$는 **'설계도대로 작동하는 기계'** 이다.

proof)

연산자는 스팩트럼 분해에 의해서,

$$
|h\rangle\circledast
=\int ds (\langle s^M|h\rangle)|s\rangle\langle s^d|
$$

시스템 벡터는 고유벡터로 표현할 수 있다.

$$
|h\rangle
= \int ds (\langle s^{M,d}|h\rangle)|s\rangle
= \frac{1}{2\pi i}\int ds (\langle s^M|h\rangle)|s\rangle
$$

---

### 4. 멜린 역변환

$|s\rangle$_M에 대한 기저를 $|x\rangle$에 대한 기저로 옮기는 것이다.

$$
h(x)
= \langle x|h\rangle
= \langle x|\left(\int ds \langle s^{M,d}|h\rangle|s\rangle \right)
= \frac{1}{2\pi i}\int ds \langle s^M|h\rangle x^{-s}
$$
