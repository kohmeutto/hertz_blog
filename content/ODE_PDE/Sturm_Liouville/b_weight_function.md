+++
title = "(b) Weight function"
weight = 2
+++

---

임의의 미분 연산자는 아래와 같다.

$$
L=p_0\left(x\right)\frac{d^2}{dx^2}+p_1\left(x\right)\frac{d}{dx}+p_2\left(x\right) 
$$

$$
Lu_{n}=\lambda_{n}u_{n}
$$

이전 챕터의 예제에서 보았듯이. 일반적인 연산자를 스텀-리우빌 형태로 바꾸면, 고유값 문제에, 어떠한 함수가 곱해진다.

$$
L_{p}=\left\lbrack\frac{d}{dx}\left(p\left(x\right)\frac{d}{dx}\right)+q\left(x\right)\right\rbrack u_{n} 
$$

$$
L_{p}u_{n}=-w\left(x\right)\lambda_{n}u_{n}
$$

따라서, 임의의 미분 연산자는 아래와 같이 표현할 수 있다.

$$
L=-\frac{1}{w\left(x\right)}\left\lbrack\frac{d}{dx}\left(p\left(x\right)\frac{d}{dx}\right)+q\left(x\right)\right\rbrack u_{n}=\lambda_{n}u_{n}
$$

여기서의 w(x)는 weight function 이라고 한다.