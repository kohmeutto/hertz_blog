+++
title = "(i) Linearity"
weight = 3
+++

---

### 0. 정리

선형성 (Linearity)는 공학/수학에서 가장 핵심적으로 중요한 개념이다.

$$
f\left(au_1+bu_2\right)=af\left(u_1\right)+bf\left(u_2\right)
$$

위 식을 만족하는 시스템은 선형적(**선형변환**)이라고 할 수 있다.

Linear Algebra(선형대수학) 학문은 **선형시스템을 다루기 위한 “도구”** 이다.
 
**다음 챕터에서 행렬이 왜 선형변환이고, 선형대수학에서 배우는지 알 수 있다.**

---

### 1. 성질 - 가산성 (additivity)

위 식의 오른쪽 항에서 “+”로 표현되는 것을 가산성이라고 한다.

해석하려는 시스템 $f\left(u\right)$는 선형적이다.

입력값이 $u_1+u_2$일 때,  $u_1$에 대한 결과와  $u_2$에 대한 결과를 각각 따로  얻은다음 더하기한 하면 된다.

---

### 2. 성질 - 동차성 (Homogenity)

위 식의 오른쪽 항에서 상수와의 곱, 즉, $af\left(u\right)$를 동차성(or scaling)이라고 한다.

해석하려는 시스템 $f\left(u\right)$는 선형적이다.

입력값이 $au_1$일 때,  $u_1$에 대한 결과에 단순히 $a$만 곱하면 된다.

---

### 3. Superposition (중첩) = additivity + Homogenity

---

### 4. 원점을 지나지 않는 직선은 선형적이지 않다.

$$
f\left(x\right)=ax+b
$$

위 직선에 대한 식은 선형적이지 않다.

$$
\left\lbrack f\left(x_1+x_2\right)=a\left(x_1+x_2\right)+b\right\rbrack\neq\left\lbrack ax_1+b+ax_2+b\right\rbrack
$$

---

[Nonlinear system - Wikipedia](https://en.wikipedia.org/wiki/Nonlinear_system)