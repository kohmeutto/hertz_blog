+++
title = "(a) Derivative"
weight = 4
+++

---

### 1. 스칼라에 대한 미분

$$
\frac{\partial}{\partial \bar{\bar{A}}} f
=\frac{\partial}{\partial A_{ij}} f\hat{u}_i\hat{u}_j
$$

$$
\left[\frac{\partial}{\partial \bar{\bar{A}}} f\right]_{ij}
=\frac{\partial f}{\partial A_{ij}}
$$

---

### 2. Chain rule

$\bar{\bar{\sigma}}(\bar{\bar{\epsilon}})$ 는 $\bar{\bar{\epsilon}}$에 대한 함수이다. $\bar{\bar{\epsilon}}$은 시간에 대한 함수이다. $\bar{\bar{\sigma}}$의 시간 변화율을 구하려고 한다. 체인룰로 표현하면, 다음과 같다.

$$
\frac{\partial\bar{\bar{\sigma}}}{\partial t}
=\frac{\partial\bar{\bar{\sigma}}}{\partial \bar{\bar{\epsilon}}}:\frac{\partial\bar{\bar{\epsilon}}}{\partial t}
$$

이를 벡터 성분 표기로 표현해 보자. 여기서 기존과 다른 주의해야할 사항은, 2차 텐서에 대한 2차 텐서의 편미분은 분자인덱스를 먼저 쓴다는 것이다(그렇게 해야 성분이 일치한다).

$$
\frac{\partial\bar{\bar{\sigma}}}{\partial t}
=\frac{\partial\sigma_{ij}}{\partial \epsilon_{kl}}\hat{u}_i\hat{u}_j\hat{u}_k\hat{u}_l:\frac{\partial\epsilon_{mn}}{\partial t}\hat{u}_m\hat{u}_n
=\frac{\partial\sigma_{ij}}{\partial \epsilon_{kl}}\frac{\partial\epsilon_{mn}}{\partial t}\hat{u}_i\hat{u}_j(\hat{u}_k\hat{u}_l:\hat{u}_m\hat{u}_n)
$$

$$
=\frac{\partial\sigma_{ij}}{\partial \epsilon_{kl}}\frac{\partial\epsilon_{mn}}{\partial t}\hat{u}_i\hat{u}_j(\hat{u}_k\cdot\hat{u}_m)(\hat{u}_l\cdot\hat{u}_n)
=\frac{\partial\sigma_{ij}}{\partial \epsilon_{kl}}\frac{\partial\epsilon_{mn}}{\partial t}\hat{u}_i\hat{u}_j\delta_{km}\delta_{ln}
$$

$$
=\frac{\partial\sigma_{ij}}{\partial \epsilon_{mn}}\frac{\partial\epsilon_{mn}}{\partial t}\hat{u}_i\hat{u}_j
$$

또는 지수 표기법을 사용하면,

$$
\left[\frac{\partial\bar{\bar{\sigma}}}{\partial t}\right]_{ij}
=\frac{\partial\sigma_{ij}}{\partial \epsilon_{mn}}\frac{\partial\epsilon_{mn}}{\partial t}
$$