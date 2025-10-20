+++
title = "(b) Laplace transform I"
weight = 4
+++

---

**LSI 연산자 정리**

(1) $\hat{H}|x'\rangle=|h(x-x')\rangle$

(2) $\hat{H}=|h\rangle\ast=\int dx' |h(x-x')\rangle\langle x'|$

(3) $\hat{H}=|h\rangle\ast=\int ds H(s)|s\rangle\langle s|$

---


### 1. Eigenvector & eigenvalue of LSI systems

연산자 $|h\rangle\ast$ 의 고유값과 고유벡터

$$
\text{eigenvalue}: \lambda=H(s)=\int_{-\infty}^{\infty} dt h(t) e^{-st}
$$

$$
\text{eigenvector}: |s\rangle=|e^{st}\rangle
$$

proof)

$$
|h\rangle\ast|e^{st}\rangle
=\int^{\infty}_{-\infty}d\tau h(\tau) |e^{s(t-\tau)}\rangle
=\left(\int^{\infty}_{-\infty}d\tau e^{-s\tau}h(\tau) \right)|e^{st}\rangle
$$

$$
\lambda=H(s)=\int_{-\infty}^{\infty} dt h(t) e^{-st}
$$

---

### 2. State vector & operator

벡터 $|h\rangle$는 **'설계도(DNA)'** 이고, 연산자 $|h\rangle\ast$는 **'설계도대로 작동하는 기계'** 이다.

proof)

연산자는 스팩트럼 분해에 의해서,

$$
|h\rangle\ast = \int ds H(s)|s\rangle\langle s|
$$

시스템 벡터는 고유벡터로 표현할 수 있다.

$$
|h\rangle
= \int ds \langle s^d|h\rangle|s\rangle
= \frac{1}{2\pi i}\int ds H(s)|s\rangle
$$

고유기저에 대한 좌표는

$$
\langle s^d|h\rangle
=\frac{1}{2\pi i}H(s)
$$

위 두 식을 비교하면 연산자 $|h\rangle\ast$의 고유값과 $|h\rangle$의 좌표가 유사함을 알 수 있다.

---

### 3. 라플라스 변환

아래는 동일한 것을 다른 관점으로 설명한 것이다.

(1) 관점1: **라플라스 변환**은 convolution으로 모두 귀결되는 LSI 연산자의 **eigenvalue**(고유값)을 찾아 내는 방법이다.

$$
H(s)=L\left\lbrace h\left(t\right)\right\rbrace\left(s\right)=\int_{-\infty}^{\infty}dt\left[h\left(t\right)e^{-st}\right]
$$

(2) 관점2: **라플라스 변환**은 벡터의 **좌표**를 찾아 내는 방법이다.

$$
H(s)=\langle s|h\rangle=\int_{-\infty}^{\infty}dt\left[h\left(t\right)e^{-st}\right]
$$

---

### 4. 대수방정식

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
\langle s|f_1\rangle+\langle s|f_2\rangle=\langle s|f_3\rangle
$$

$$
\lambda_1+\lambda_2=\lambda_3
$$

---

### 5. 라플라스 역변환

$|s\rangle$에 대한 기저를 $|t\rangle$에 대한 기저로 옮기는 것이다.

$$
\langle t|h\rangle
= \langle t|\left(\int ds H(s)|s\rangle \right)
= \int ds H(s)\langle t|s\rangle
= \int ds H(s)e^{st}
$$

브라연산자는 모두 선형이므로(필수 조건이며, 선택적인 성질이 아님)

$$
\langle s|\left(\int dt |t\rangle\langle t|\right)|h\rangle=\int_{-\infty}^{\infty}dt\left[h\left(t\right)e^{-st}\right]
$$


---

### 6. 주의사항

Laplace transform은 다양한 함수에 적용할 수 있는 강력한 수학적 도구이다. 하지만, 이 변환을 사용하여 시스템의 출력을 전달 함수와의 곱, 즉 $Y(s) = H(s)X(s)$로 간단하게 계산하는 것은 시스템이 반드시 선형 이동 불변(LSI)일 때만 유효하다.

비선형 시스템은 중첩의 원리를 만족하지 않으므로, 임펄스 응답 h(t)와 전달 함수 H(s)라는 개념 자체가 시스템 전체를 대표할 수 없다. 따라서 이 문서에서 다루는 모든 시스템 분석 기법은 LSI 시스템을 전제로 한다.