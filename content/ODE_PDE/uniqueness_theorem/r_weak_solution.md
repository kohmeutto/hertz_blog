+++
title = "(r) Weak solution"
weight = 1
+++

---

### 0. 정리

$$
\int_{\Omega}d^3V\left\lbrack v\nabla^2u\right\rbrack=\int_{\Omega}d^2\vec{s}\cdot\left\lbrack v\nabla u\right\rbrack-\int_{\Omega}d^3V\left\lbrack\nabla v\cdot\nabla u\right\rbrack
$$

---

### 1. Weak solution

약한해와 강한해의 이론은 미분 방정식과 편미분 방정식에서 중요한 개념이다. 약한해는 미분 방정식의 해가 반드시 미분 가능하지 않아도 되는 경우를 말한다. 약한해는 함수가 미분 가능하지 않더라도 적분 방정식을 만족하는 경우를 의미한다.

라플라스 방정식 $\nabla^2u=-f$을 고려해보자. 함수의 내적연산을 사용하여 적분 방정식을 만든다. v 테스트 함수이다.

$$
\int_{\Omega}d^3V\left\lbrack v\nabla^2u\right\rbrack=-\int_{\Omega}d^3V\left\lbrack vf\right\rbrack
$$

$$
\nabla\cdot v\nabla u=\nabla v\cdot\nabla u+v\nabla^2u
$$

$$
\int_{\Omega}d^3V\left\lbrack\nabla\cdot v\nabla u-\nabla v\cdot\nabla u\right\rbrack=\int_{\Omega}d^2\vec{s}\cdot\left\lbrack v\nabla u\right\rbrack-\int_{\Omega}d^3V\left\lbrack\nabla v\cdot\nabla u\right\rbrack
$$

**아래 식은 암기하라. (**$\nabla^2$**에 대한 일반적인 weak form 표현)**

$$
\int_{\Omega}d^3V\left\lbrack v\nabla^2u\right\rbrack=\int_{\Omega}d^2\vec{s}\cdot\left\lbrack v\nabla u\right\rbrack-\int_{\Omega}d^3V\left\lbrack\nabla v\cdot\nabla u\right\rbrack
$$

어떤 특정 경계면에서 0이 된다고 가정하자.

$$
\int_{\Omega}d^3V\left\lbrack v\nabla^2u\right\rbrack=-\int_{\Omega}d^3V\left\lbrack\nabla v\cdot\nabla u\right\rbrack
$$

따라서, 다음과 같은 적분 방정식을 만들 수 있다.

$$
\int_{\Omega}d^3V\left\lbrack\nabla v\cdot\nabla u\right\rbrack=\int_{\Omega}d^3V\left\lbrack vf\right\rbrack
$$

**이 적분 방정식을 만족하는 함수 v가 약한 해이다.**

---

### 2. 쉬운 이해

강한 해는 마치 깔끔하고 반듯하게 모든 규칙을 정확히 지키면서 살아가는 모범생과 같다. 수학 문제(PDE)가 주어지면, 그 문제에 나오는 모든 조건(미분 가능성 등)을 완벽하게 만족시키면서 정답을 딱 떨어지게 내는 것이다.

약한 해는 약간 덜 엄격하지만, 넓은 마음으로 규칙을 이해하고 따르려고 노력하는 친구 같다. 수학 문제의 모든 조건을 완벽하게 지키지는 못할 수도 있지만, 문제의 핵심 내용을 다른 방식으로 (적분이라는 도구를 써서) 이해하고 비슷한 해답을 내놓는 것이다. 때로는 모범생(강한 해)처럼 깔끔하지 않을 수도 있고, 어쩌면 좀 이상한 형태일 수도 있다.

유일성의 정리는 "이 수학 문제의 정답은 딱 하나밖에 없어!"라고 외치는 선생님의 말씀과 같다. 어떤 조건을 만족하는 해가 있다면, 그 해가 강한 해든 약한 해든 간에 오직 하나뿐이라는 것을 보장해 주는 것이다.

만약 우리가 찾은 약한 해가 알고 보니 **엄청나게 착하고 공부도 잘해서 모범생(강한 해)** 과 똑같다면, 그리고 선생님(유일성의 정리)이 "이 문제의 모범생 해답은 딱 하나야!"라고 이미 말씀하셨다면, 당연히 우리가 찾은 그 착한 약한 해 (이자 강한 해)는 유일한 정답이 되는 것이다.

하지만 중요한 건, 약한 해가 강한 해와 똑같다고 해서 자동으로 "정답은 하나뿐이야!"라고 말할 수는 없다는 것이다.

선생님이 "이 문제의 모범생 해답은 딱 하나야!"라고 말씀하셨는데, 우리가 찾은 해가 모범생처럼 행동한다면 그 해가 유일한 모범생 해답이 되는 건 맞다.

비유하자면:

- PDE: 수학 문제
- 강한 해: 모범생 해답 (모든 규칙 완벽 준수)
- 약한 해: 덜 엄격하지만 핵심을 이해하는 해답
- 유일성의 정리: "이 문제의 정답은 딱 하나!"라는 선생님의 말씀
- 약한 해 = 강한 해: 우리가 찾은 덜 엄격한 해답이 알고 보니 모범생 해답과 똑같음

핵심은, "약한 해 = 강한 해"라는 사실 자체가 유일성을 보장하는 것이 아니라, 그 해가 만족하는 해 공간에 대한 유일성 정리가 이미 존재해야 한다는 것이다. 우리가 찾은 해가 그 유일성 정리가 적용되는 종류의 해(강한 해)라면, 유일성이 보장되는 것이다.