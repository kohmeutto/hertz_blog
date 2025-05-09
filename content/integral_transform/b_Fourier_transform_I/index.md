+++
title = "(b) Fourier transform I"
weight = 5
+++

---

### 1. 푸리에 변환의 본질

**함수는 여러 주파수 성분들이 중첩** 되어 있다고 볼 수 있다. 푸리에 변환은 각 주파수 성분의 크기를 구하는 것이다. 아래는 cosine과 sine 함수를 나타내며, 빨간색은 주파수 성분의 크기이다.

- cosine 함수
<img src="image1.png" width="60%" height="auto">

- sine 함수
<img src="image2.png" width="60%" height="auto">

---

### 2. 각 주파수 성분들은 orthogonal 하다.

$$
\langle e^{i\omega't}|e^{i\omega t} \rangle=2\pi\delta\left(\omega-\omega'\right)
$$

{{< details summary="proof) 중요" >}}

$$
\int_{-\infty}^{\infty}dt\left\lbrack e^{i\omega t}e^{-i\omega't}\right\rbrack
$$

위 식이 무엇인지 구하는 것이 목적이다. 'Regularization(정칙화) 기법'을 사용하자. 수학이나 물리학에서 다루는 문제 중에는 발산하거나(divergent), 특이점(singularity)을 포함하거나, 또는 해가 유일하게 결정되지 않는(ill-posed problem) 등 수학적으로 잘 정의되지 않거나 다루기 어려운 경우가 있다. 정칙화는 이러한 문제들을 직접 다루는 대신, 하나 이상의 매개변수(ϵ 등)를 도입하여 문제를 약간 변형(정칙화)함으로써 임시적으로 잘 정의되고 다루기 쉬운 형태로 만든 다음, 그 매개변수에 대해 특정 극한을 취하여 원래 문제의 '해석적인(meaningful)' 결과를 얻어내는 기법 이다.

$$
\Omega=\omega-\omega'
$$

$$
f_{\epsilon}(\Omega)=\int_{-\infty}^{\infty}dt\left\lbrack e^{i\Omega t}e^{-\epsilon|t|}\right\rbrack
$$

$$
\int_{-\infty}^{\infty}dt\left\lbrack e^{i\left(\omega-\omega'\right)t}\right\rbrack
=\lim_{\epsilon\to0}f_{\epsilon}(\Omega)
=\lim_{\epsilon\to0}\int_{-\infty}^{\infty}dt\left\lbrack e^{i\Omega t}e^{-\epsilon|t|}\right\rbrack
=\int_{-\infty}^0dt\left\lbrack e^{i\Omega t}e^{\epsilon t}dt\right\rbrack+\int_0^{\infty}dt\left\lbrack e^{i\Omega t}e^{-\epsilon t}\right\rbrack
$$

음수 구간

$$
\int_{-\infty}^0dt\left\lbrack e^{i\Omega t}e^{\epsilon t}dt\right\rbrack=\int_{-\infty}^0dt\left\lbrack e^{(\epsilon+i\Omega)t}\right\rbrack=\left[\frac{1}{\epsilon+ i\Omega}e^{(\epsilon+i\Omega)t}\right]_{-\infty}^0=\frac{1}{\epsilon+ i\Omega}
$$

양수 구간

$$
\int_{0}^{\infty} e^{i\Omega t} e^{-\epsilon t} dt = \int_{0}^{\infty} e^{(-\epsilon + i\Omega)t} dt = \left[ \frac{1}{-\epsilon + i\Omega} e^{(-\epsilon + i\Omega)t} \right]_{0}^{\infty} = \frac{1}{\epsilon - i\Omega}
$$

따라서,

$$
f_{\epsilon}(\Omega)=\int_{-\infty}^{\infty}dt\left\lbrack e^{i\Omega t}e^{-\epsilon|t|}\right\rbrack=\frac{2\epsilon}{\Omega^2 + \epsilon^2}
$$

(1) $\Omega=0$

$$
\lim_{\epsilon\to0}f_{\epsilon}(\Omega)=\lim_{\epsilon\to0}\frac{2}{\epsilon}=\infty
$$

(2) $\Omega\ne0$

$$
\lim_{\epsilon\to0}f_{\epsilon}(\Omega)=\lim_{\epsilon\to0}\frac{0}{\Omega^2}=0
$$


(1) & (2) 의 결과를 사용하면, 다음을 얻을 수 있다.

$$
\lim_{\epsilon\to0}f_{\epsilon}(\Omega)=A\delta\left(\Omega\right)
$$

계수 A가 무엇인지 구해보자. 디렉델타함수의 정의를 사용한다.

$$
A=\int_{-\infty}^{\infty}d\Omega\left\lbrack \frac{2\epsilon}{\Omega^2 + \epsilon^2} \right\rbrack
=2\int_{-\infty}^{\infty}d\left(\frac{\Omega}{\epsilon}\right)\left\lbrack \frac{1}{\left(\frac{\Omega}{\epsilon}\right)^2 + 1} \right\rbrack
=2\left[\operatorname{atan}\left(\frac{\Omega}{\epsilon}\right)\right]^{\infty}_{-\infty}=2\pi
$$

최종적으로,

$$
\langle e^{i\omega't}|e^{i\omega t} \rangle=2\pi\delta\left(\omega-\omega'\right)
$$

만약 orthonormal 한 기저로서 표현하고 싶다면,

$$
\left\langle \frac{e^{i\omega't}}{\sqrt{2\pi}}\middle|\frac{e^{i\omega t}}{\sqrt{2\pi}}\right\rangle=\delta\left(\omega-\omega'\right)
$$

{{< /details >}}

---

### 3. 표준 푸리에 변환, 정규 직교성(orthonormal) or 대칭성 기반의 정의

- **물리학, 특히 양자역학:** 정규 직교성 기반 정의가 압도적으로 많이 사용된다. 에너지 보존과 확률 진폭 해석의 중요성 때문이다.
- 물리학적으로 사용될 때, 해석 공간의 변환보다는 **주파수가 중첩되어 있다는 의미가 강함**

$$
f\left(t\right)=\frac{1}{\sqrt{2\pi}}\int_{-\infty}^{\infty}d\omega\left\lbrack F\left(\omega\right)e^{-i\omega t}\right\rbrack
$$

$$
F\left(\omega\right)=F\left\lbrace f\left(t\right)\right\rbrace\left(\omega\right)=\frac{1}{\sqrt{2\pi}}\int_{-\infty}^{\infty}dt\left\lbrack f\left(t\right)e^{+i\omega t}\right\rbrack
$$

---

### 4. 표준 푸리에 변환, 비대칭성 기반의 정의

- **수학:** 비대칭성 기반 정의가 더 많이 사용되는 경향이 있다. 비대칭적인 형태가 수학적 이론 전개에 편리하기 때문
- **공학, 특히 신호 처리:** 비대칭성 기반 정의가 더 많이 사용되는 경향이 있다.
- 수학, 공학적으로 사용될 때, 주파수 중첩 보다는 **해석 공간의 변환 이라는 의미가 강함**

$$
F\left(\omega\right)=F\left\lbrace f\left(t\right)\right\rbrace\left(\omega\right)=\int_{-\infty}^{\infty}dt\left\lbrack e^{-i\omega t}f\left(t\right)\right\rbrack
$$

$$
f\left(t\right)=\frac{1}{2\pi}\int_{-\infty}^{\infty}dt\left\lbrack e^{+i\omega t}F\left(\omega\right)\right\rbrack
$$

---

### 5. 푸리에 변환의 확장: 분포 푸리에 변환

**(1) 표준 푸리에 변환의 한계**

$$
\int_{-\infty}^{\infty}dt |f\left(t\right)| <\infty
$$

위 식은 표준 푸리에 변환이 가능한 조건(절대 적분)이다. 표준 푸리에 변환의 한계를 극복하고 절대 적분 가능하지 않은 신호들을 포함한 더 넓은 범위의 신호에 대해 푸리에 변환을 정의하기 위해 분포(Distribution) 이론을 기반으로 푸리에 변환 개념을 확장한다.

**(2) 분포 푸리에 변환 (Generalized Fourier Transform)**

- **도입 이유:** 표준 푸리에 변환으로는 다룰 수 없는 디랙 델타 함수($\delta(t)$), 단위 계단 함수($u(t)$), 상수 함수 등의 푸리에 변환을 정의하고, 푸리에 분석을 더 넓은 범위의 신호에 적용하기 위함이다.

- **정의 방식:** 분포의 푸리에 변환은 직접적인 적분으로 정의되기보다는, 푸리에 변환의 성질(선형성, 미분, 이동 등)을 이용하거나 "시험 함수"와의 상호 작용을 통해 간접적으로 정의된다. **정칙화(Regularization)** 는 이러한 분포의 푸리에 변환을 이해하고 도출하는 한 가지 유용한 기법으로, 이상적인 신호를 잘 동작하는 함수의 수열로 근사하고 그 수열의 표준 푸리에 변환의 극한을 취하는 방식이다.

- **결과 형태:** 결과 또한 분포 형태가 될 수 있으며, 주파수 영역에서 델타 함수 $\delta(\omega)$와 같은 특이점을 포함할 수 있다.

**(3) 주요 예시**

- **디랙 델타 함수:** $\mathcal{F}\{\delta(t)\} = 1$

- **단위 계단 함수:** $\mathcal{F}\{u(t)\} = \pi\delta(\omega) + \frac{1}{i\omega}$

- **상수 함수 ($A$):** $\mathcal{F}\{A\} = 2\pi A\delta(\omega)$

---

### 6. 라플라스 변환과의 관계

라플라스 변환의 수렴 영역(ROC, Region of Convergence)이 $i\omega$ 축($\text{Re}\{s\}=0$)을 포함할 때, 라플라스 변환 $F(s)$에 $s=i\omega$를 대입한 결과 $F(i\omega)$가 표준 푸리에 변환과 같다. 즉, 이 경우 표준 푸리에 변환은 라플라스 변환의 특수한 경우로 볼 수 있다.

하지만 라플라스 변환의 ROC가 $i\omega$ 축을 포함하지 않는 신호들도 있다. (예: 단위 계단 함수 $u(t)$, 상수 함수). 이러한 신호의 경우, 표준 푸리에 변환은 존재하지 않지만 **분포의 푸리에 변환**은 존재할 수 있으며, 이는 단순히 라플라스 변환에 $s=i\omega$를 대입하는 것만으로는 얻을 수 없다.

따라서 라플라스 변환에 $s=i\omega$를 대입하여 푸리에 변환을 얻는 방법은 **ROC가 $i\omega$ 축을 포함하는 신호에 대해서만 유효**하다. 즉, 표준 푸리에 변환만 할 수 있다.

---

### 7. 페이저 변환과의 관계

페이저 변환과 수학적 뿌리는 동일하다. **그러나 전혀 다른 변환으로 생각하자.** 페이저 변환은 주파수가 1개 (2개 이상 안됨) 일 때, 적용할 수 있는 방법이다.

---