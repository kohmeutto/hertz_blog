+++
title = "(b) Riesz representation theorem"
weight = 4
+++

---

### 1. 디렉 표기법과의 연결 고리

- Bra의 작용: 쌍대공간 $V^\ast$의 원소 $\langle f|$ 가 원래 공간 V의 원소 $|v\rangle$ 에 작용하는 것, $\langle f|v\rangle$
- 내적: 원래 공간 V의 두 원소 $|f\rangle$와 $|v\rangle$ 사이의 기하학적 관계, $\langle f,v\rangle$.

두 표기법이 너무나 비슷하게 생겼다는 것은 우연이 아니다. 힐베르트 공간에서는 이 둘을 하나로 묶어주는 운명적인 연결고리가 있으며, 그 연결고리의 이름이 바로 **리즈 표현 정리(Riesz Representation Theorem)** 이다.

---

### 2. 리즈 표현 정리(Riesz Representation Theorem)

**(1) Bra 연산자 $\langle f|$은 내적연산자와 동일**

$$
\langle f|v\rangle=(|f\rangle,|v\rangle)
$$

proof)

우리는 아직 $\langle f|v\rangle$라는 함수의 작용과 내적 $\langle f,v\rangle$ 사이에 아무 관계도 모른다. 범함수 $\langle f|$가 0을 출력하게 만드는 모든 벡터들의 집합(영공간) $\text{Ker}(f)$를 생각한다.

$$
\text{Ker}(f)=\{|k\rangle,\langle f|k\rangle=0\}
$$

따라서, 힐버트 공간은 아래와 같이 표현할 수 있다.

$$
H=\text{Ker}(f)\oplus\text{Ker}(f)^\perp
$$

여기서 $\perp$은 공간이 원래 가지고 있던 **내적 $(,)$** 에 대한 수직을 의미한다. $\langle f|$가 영범함수가 아니라면, $\text{Ker}(f)^\perp$ 공간안에 0벡터가 아닌 벡터가 존재한다. 그 중 하나의 벡터를 $|g\rangle$ 라고 하자. 따라서, $H$공간안에 임의의 벡터 $|v\rangle$는 $|k\rangle$의 벡터와 $\alpha|g\rangle$의 벡터의 합성으로 표현할 수 있다.

$$
|v\rangle=\alpha|g\rangle+|k\rangle
$$

범함수와 영공간의 관계를 사용하여,

$$
\langle f|v\rangle = \alpha\langle f|g\rangle\implies
\alpha=\frac{\langle f|g\rangle}{\langle f|v\rangle}
$$

$|g\rangle$와 $|k\rangle$의 수직임을 사용하여,

$$
(|g\rangle,|v\rangle)=\alpha(|g\rangle,|g\rangle)\implies
\alpha=\frac{(|g\rangle,|v\rangle)}{(|g\rangle,|g\rangle)}
$$

두 식은 같아야 하므로,

$$
\langle f|v\rangle
= \frac{\langle f|g\rangle}{(|g\rangle,|g\rangle)} \langle g,v\rangle
$$

$\langle f|g\rangle/(|g\rangle,|g\rangle)$는 상수이며 이를 $\beta$라고 하자.

$$
\langle f|v\rangle
=\beta(|g\rangle,|v\rangle)
=(|\beta^\ast g\rangle,|g\rangle)
$$

위 식은 범함수의 연산이 내적으로 표현될 수 있음을 보여준다.

**(2) 쌍대(파트너) 벡터의 유일성**

ket 벡터 $|f\rangle$의 **쌍대(파트너) 벡터**는 Bra 벡터 $\langle f|$이며, 유일하다. **이 역 또한 성립** 한다.

proof)

ket 벡터 $|f\rangle$ 의 파트너가 $\langle f_1|$과 $\langle f_2|$ 가 있다. 파트너의 정의에 의해,

$$
\langle f_1|v \rangle = (|f\rangle,|v\rangle) 
$$

$$
\langle f_2|v \rangle = (|f\rangle,|v\rangle)  
$$

두 식의 우변이 완전히 같으므로, 좌변도 당연히 같아야 한다.

$$
\langle f_1-f_2|v \rangle = 0 
$$

모든 $v$에 대해 만족하려면, $\langle f_1-f_2|$은 영함수 벡터가 되야 한다. 따라서,

$$
\langle f_1|=\langle  f_2|
$$


