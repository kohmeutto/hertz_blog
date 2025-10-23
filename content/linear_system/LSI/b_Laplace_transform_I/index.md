+++
title = "(b) Laplace transform I"
weight = 4
+++

---

<img src="image1.png" width="90%" height="auto">

---

### 1. Eigenvector & eigenvalue of LSI systems

연산자 $|h\rangle\ast$ 의 고유값과 고유벡터

$$
\text{eigenvalue}: H(s)=\int_{-\infty}^{\infty} dt h(t) e^{-st}
$$

$$
\text{eigenvector}: |s\rangle, \langle t|s\rangle=e^{st}
$$

proof)

$$
|h\rangle\ast|s\rangle=H(s)|s\rangle
$$

위의 식을 토대로,

$$
\langle t|(|h\rangle\ast)|s\rangle
=\int^{\infty}_{-\infty}d\tau h(\tau) s(t-\tau)
$$

$$
\langle t|H(s)|s\rangle
=H(s)\langle t|s\rangle
=H(s) s(t)
$$


$\langle t|s\rangle=s(t)=e^{st}$ 라고 하면,

$$
\int^{\infty}_{-\infty}d\tau h(\tau) s(t-\tau)
=\int^{\infty}_{-\infty}d\tau h(\tau) e^{s(t-\tau)}
=\left(\int^{\infty}_{-\infty}d\tau e^{-s\tau}h(\tau) \right)e^{st}
$$

따라서,

$$
H(s)=\int_{-\infty}^{\infty} dt e^{-st} h(t) 
$$

---

### 2. Dual vector & dual basis for $|s\rangle$

**(1) Dual vector**

$$
\langle s|s'\rangle=2\pi \delta(s-s'),\quad \text{if }\operatorname{Re}[s]=\operatorname{Re}[s']=0
$$

proof)

$$
\langle s|s'\rangle
=\langle s|\left(\int dt |t\rangle\langle t| \right)|s'\rangle
=\int dt \langle s|t\rangle\langle t|s'\rangle
=\int dt e^{s^\ast t}e^{s't}
=\int dt e^{(s^\ast+s')t}
$$

if $\operatorname{Re}[s]\ne\operatorname{Re}[s']=0$, 
발산하기 때문에 정의할 수 없다.

if $\operatorname{Re}[s]=\operatorname{Re}[s']=0$

위 조건하에, 아래의 형태를 생각해 본다.

$$
\int dt e^{i(\omega-\omega')t}=2\pi\delta(\omega-\omega')
$$

$$
\langle s|s'\rangle=2\pi\delta(s-s')
$$

**(2) Dual basis, 푸리에 변환 기저**

$$
\langle s^d|=\frac{1}{2\pi} \langle s|,\quad
\text{if }\operatorname{Re}[s]=0
$$

proof)

$$
\langle s^d|s'\rangle=\delta(s-s')
$$

$\operatorname{Re}[s]=0$ 일 때, 직교기저이다.

$$
\langle s|s'\rangle=2\pi\delta(s-s')
$$

따라서,

$$
\langle s^d|=\frac{1}{2\pi} \langle s|
$$

**(3) Dual basis, 라플라스 변환 기저**

$$
\langle s^d|t\rangle=\frac{1}{2\pi i}e^{-st},\quad
\langle s^d|h\rangle=\frac{1}{2\pi i}H(s),\quad
\text{if }\operatorname{Re}[s]\ne0
$$

proof)

$\operatorname{Re}[s]\ne 0$ 일 때, 비직교기저이다. 따라서, $\langle s|s'\rangle=2\pi\delta(s-s')$ 관계는 더 이상 성립하지 않는다.

$$
\langle s^d|s'\rangle=\delta(s-s')
$$

$$
\langle s^d|\hat{I}|s'\rangle
=\langle s^d|\left(\int dt |t\rangle\langle t|\right)|s'\rangle
=\int dt \langle s^d|t\rangle\langle t|s'\rangle
=\int^{\infty}_{-\infty} dt \langle s^d|t\rangle e^{s't}
=\delta(s-s')
$$

브롬 위치 적분을 사용하여,

$$
\langle s^d|t\rangle
=\frac{1}{2\pi i}e^{-st}
$$

이번에는 $\langle s^d|h\rangle$ 을 구해보자.

$$
\langle s^d|h\rangle
=\langle s^d|\hat{I}|h\rangle
=\langle s^d|\left(\int dt |t\rangle\langle t|\right)|h\rangle
=\int dt \langle s^d|t\rangle\langle t|h\rangle
=\frac{1}{2\pi i}\int dt e^{-st}h(t)
$$

따라서,

$$
\langle s^d|h\rangle
=\frac{1}{2\pi i}H(s)
$$ 

---

### 3. State vector & operator

벡터 $|h\rangle$는 **'설계도(DNA)'** 이고, 연산자 $|h\rangle\ast$는 **'설계도대로 작동하는 기계'** 이다.

proof)

연산자는 스팩트럼 분해에 의해서,

$$
|h\rangle\ast = \int ds H(s)|s\rangle\langle s^d|
$$

시스템 벡터는 고유벡터로 표현할 수 있다.

$$
|h\rangle
= \int ds \langle s^d|h\rangle|s\rangle
= \frac{1}{2\pi i}\int ds H(s)|s\rangle
$$

고유기저 $|s\rangle$ 에 대한 좌표는

$$
\langle s^d|h\rangle
=\frac{1}{2\pi i}H(s)
$$

위 두 식을 비교하면 연산자 $|h\rangle\ast$의 고유값과 $|h\rangle$의 좌표가 통일됨을 알 수 있다.

---

### 4. 라플라스 변환

아래는 동일한 것을 다른 관점으로 설명한 것이다.

(1) 관점1: **라플라스 변환**은 convolution으로 모두 귀결되는 LSI 연산자의 **eigenvalue**(고유값)을 찾아 내는 방법이다.

$$
H(s)
=\int_{-\infty}^{\infty}dt\left[h\left(t\right)e^{-st}\right]
$$

(2) 관점2: **라플라스 변환**은 벡터의 **좌표**를 찾아 내는 방법이다. 직관적으로 표현하기 위해, 아래와 같이 사용한다.

$$
H(s)
=2\pi i\langle s^d|h\rangle
=\langle s^L|h\rangle
$$

---

### 5. 대수방정식

$$
y''-7y'=7e^{t}\implies
|f_1\rangle+|f_2\rangle=|f_3\rangle
$$

(1) 관점1: **라플라스 변환**은 convolution으로 모두 귀결되는 LSI 연산자의 **eigenvalue**(고유값)을 찾아 내는 방법이다.

$$
|f_1\rangle\ast|s\rangle+|f_2\rangle\ast|s\rangle=|f_3\rangle\ast|s\rangle
$$

$$
\lambda_1|s\rangle+\lambda_2|s\rangle=\lambda_3|s\rangle
$$

$$
\lambda_1+\lambda_2=\lambda_3
$$

(2) 관점2: **라플라스 변환**은 벡터의 **좌표**를 찾아 내는 방법이다.

$$
\langle s^L|f_1\rangle+\langle s^L|f_2\rangle=\langle s^L|f_3\rangle
$$

$$
\lambda_1+\lambda_2=\lambda_3
$$

---

### 6. 라플라스 역변환

$|s\rangle$에 대한 기저를 $|t\rangle$에 대한 기저로 옮기는 것이다.

$$
\langle t|h\rangle
= \langle t|\left(\int ds \langle s^d|h\rangle|s\rangle \right)
= \int ds \frac{1}{2\pi i}H(s)\langle t|s\rangle
= \frac{1}{2\pi i}\int ds H(s)e^{st}
$$

---

### 7. 주의사항

Laplace transform은 다양한 함수에 적용할 수 있는 강력한 수학적 도구이다. 하지만, 이 변환을 사용하여 시스템의 출력을 전달 함수와의 곱, 즉 $Y(s) = H(s)X(s)$로 간단하게 계산하는 것은 시스템이 반드시 선형 이동 불변(LSI)일 때만 유효하다.

비선형 시스템은 중첩의 원리를 만족하지 않으므로, 임펄스 응답 h(t)와 전달 함수 H(s)라는 개념 자체가 시스템 전체를 대표할 수 없다. 따라서 이 문서에서 다루는 모든 시스템 분석 기법은 LSI 시스템을 전제로 한다.