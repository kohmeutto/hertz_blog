+++
title = "(i) LSI"
weight = 1
+++

---

### 1. LSI

LSI operator(system) 이 가지는 특성은 아래와 같다.

**(1) Linearity(선형성)=Superpostion**

Superposition은 Linearity 와 동치이다. 따라서, 두가지 용어를 system 에서 혼용해서 사용해도 같은 의미임을 상기하라.

$$
\text{Superposition}=\text{Addictivity}+\text{Scaling}
$$

$$
\hat{H}(a|\psi_1\rangle+b|\psi_2\rangle)
=a\hat{H}|\psi_1\rangle+b\hat{H}|\psi_2\rangle
$$

**(2) Shift invarient**

- 이동 불변 시스템이란 시스템을 작동시키는 근본적인 규칙(rule)이 이동(시간,공간) 등에 따라 변하지 않는다는 의미한다. 
- 따라서 동일한 모양의 입력을 언제 넣든지 상관없이, 출력은 항상 **똑같은 모양으로 나온다.**
- '똑같은 모양으로 나온다.'의 의미는 단지 출력이 나오는 시간만 입력이 들어간 시간에 맞춰 **평행 이동**할 뿐이다.

$$
|\varphi(t-\tau)\rangle=\hat{H}|\psi(t-\tau)\rangle
$$

proof)

$|\varphi(t)\rangle=\hat{H}|\psi(t)\rangle$라고 하자.

$$
\hat{H}|\psi(t-\tau)\rangle
=\hat{H}\hat{S}_\tau|\psi(t)\rangle
$$

이동 불변은 시스템(연산자)과 이동 연산자와 교환 가능을 의미하므로,

$$
\hat{S}_\tau\hat{H}|\psi(t)\rangle
=\hat{S}_\tau\hat{H}|\psi(t)\rangle
=\hat{S}_\tau|\varphi(t)\rangle
=|\varphi(t-\tau)\rangle
$$

만약, $t_0\ne t_1$ 라고 하자.

$$
|\psi'(t-t_1\rangle=\hat{H}|\psi(t-t_0)\rangle
$$

이것은 이동 불변성을 만족하지 않는다.

