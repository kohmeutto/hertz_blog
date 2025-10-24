+++
title = "(b) Laplace transform II"
weight = 5
+++

---

### 1. 라플라스 변환

(1) 단방향 라플라스 변환

$$
\langle s^L|f\cdot u\rangle
=\int_0^{\infty}dt\left[e^{-st}f\left(t\right)u(t)\right\rbrack
$$

(2) 양방향 라플라스 변환, causal system

$$
\langle s^L|f\rangle
=\int_{-\infty}^{\infty}dt\left[e^{-st}f\left(t\right)\right\rbrack
$$

---

### 2. 중요 Properties


**1) linearity**

적분연산자 자체가 선형연산자이다.

$$
\langle s^L|af\cdot u+bg\cdot u\rangle
=a\langle s^L|f\cdot u\rangle+b\langle s^L|g\cdot u\rangle
$$

$$
\langle s^L|af+bg\rangle
=a\langle s^L|f\rangle+b\langle s^L|g\rangle
$$

**2) time shifting**

$$
\langle s^L|f(t-\tau)u(t-\tau)\rangle
=\langle s^L|\hat{S}_\tau|f\cdot u\rangle
=e^{-s\tau}\langle s^L|f\cdot u\rangle
$$

$$
\langle s^L|f(t-\tau)\rangle
=\langle s^L|\hat{S}_\tau|f\rangle
=e^{-s\tau}\langle s^L|f\rangle
$$

{{< details summary="proof" >}}

$$
\langle s^L|\hat{S}_\tau
=\langle s^L|\left(\int dt |t\rangle\langle t|\right)\hat{S}_\tau
=\int dt \langle s^L|t\rangle\langle t-\tau|
=\int dt e^{-st}\langle t-\tau|
$$

$$
=\int dt' e^{-s(t'+\tau)}\langle t'|
=e^{-s\tau}\int dt' e^{-st'}\langle t'|
$$

$$
=e^{-s\tau}\langle s^L|
$$

<hr>

{{< /details >}}

**3) amplitude scaling**

$$
\langle s^L|f\left(at\right)u\left(at\right)\rangle
=\frac{1}{|a|}\left\langle \left(\frac{s}{a}\right)^L \middle|f\cdot u\right\rangle
$$

$$
\langle s^L|f\left(at\right)\rangle
=\frac{1}{|a|}\left\langle \left(\frac{s}{a}\right)^L \middle|f\right\rangle
$$

{{< details summary="proof" >}}

$$
\langle s^L|f\left(at\right)u\left(at\right)\rangle
=\int dt e^{-st}f(at)u(at)
=\int dk \frac{1}{a} e^{-\frac{s}{a}k} f(k)u(k)
$$

$$
=\frac{1}{|a|}\left\langle \left(\frac{s}{a}\right)^L \middle|f\cdot u\right\rangle
$$

<hr>

{{< /details >}}

**4) amplitude scaling & time shifting**

$$
\langle s^L|f\left(at-b\right)u\left(at-b\right)\rangle=\frac{1}{|a|} e^{-\frac{b}{a}s}\left\langle \left(\frac{s}{a}\right)^L \middle|f\cdot u\right\rangle
$$

$$
\langle s^L|f\left(at-b\right)\rangle
=\frac{1}{|a|} e^{-\frac{b}{a}s}\left\langle \left(\frac{s}{a}\right)^L \middle|f\right\rangle
$$

{{< details summary="proof" >}}

라플라스 변환은 연산자→괄호→Ket 순이다.

<br><br>

$$
\langle s^L|f\left(at-b\right)u\left(at-b\right)\rangle
=\left\langle
s^L\middle|
f\left(a\left(t-\frac{b}{a}\right)\right)
u\left(a\left(t-\frac{b}{a}\right)\right)
\right\rangle
$$

$$
=e^{-\frac{b}{a}s}\left\langle s^L\middle|f(at)u(at)\right\rangle
=\frac{1}{|a|} e^{-\frac{b}{a}s}\left\langle \left(\frac{s}{a}\right)^L \middle|f\cdot u\right\rangle
$$

<hr>

{{< /details >}}

**5) frequency shifting**

$$
\langle s^L|e^{at}\cdot f\cdot u\rangle
=\langle s|e^{a\hat{t}}|f\cdot u\rangle
=\langle s-a|f\cdot u\rangle
$$

$$
\langle s^L|e^{at}\cdot f\rangle
=\langle s^L|e^{a\hat{t}}|f\rangle
=\langle (s-a)^L|f\rangle
$$

{{< details summary="proof" >}}
    
$$
\int_{-\infty}^{\infty}dt\left\lbrack e^{-\left(s-a\right)t}f\left(t\right)\right\rbrack
=\langle (s-a)^L|f\rangle
$$

<hr>

{{< /details >}}

**6) convolution**

$$
\mathcal{L}\left\lbrace h\left(t\right)u(t)\ast f\left(t\right)u(t)\right\rbrace\left(s\right)=\langle s|(h\cdot u)\ast (f\cdot u)\rangle=\langle s|h\cdot u\rangle\langle s|f\cdot u\rangle
$$

$$
\mathcal{L}\left\lbrace h\left(t\right)\ast f\left(t\right)\right\rbrace\left(s\right)=\langle s|h\ast f\rangle=\langle s|h\rangle\langle s|f\rangle
$$

{{< details summary="proof" >}}

$$
\int^{\infty}_{0}dt\left[e^{-st}\int^{\infty}_{0}d\tau\left[h\right(t-\tau\left)f\left(\tau\right)\right]\right]
$$

$$
=\int^{\infty}_{0}dt\left[e^{-s\left(t-\tau+\tau\right)}\int^{\infty}_{0}d\tau\left[h\right(t-\tau\left)f\left(\tau\right)\right]\right]
$$

$$
=\int^{\infty}_{0}dt\left[\int^{\infty}_{0}d\tau\left[h\left(t-\tau\right)e^{-s\left(t-\tau\right)}f\left(\tau\right)e^{-s\tau}\right]\right]
$$

$$
=\int^{\infty}_{0}d\tau\left[ f\left(\tau\right)e^{-s\tau}\int^{\infty}_{0}dt\left[h\left(t-\tau\right)e^{-s\left(t-\tau\right)}\right]\right]
$$

$$
=\int^{\infty}_{0}d\tau\left[ f\left(\tau\right)e^{-s\tau}H\left(s\right)\right]
$$

$$
=H\left(s\right)\int^{\infty}_{0}d\tau\left[ f\left(\tau\right)e^{-s\tau}\right]
$$

$$
=H\left(s\right)F\left(s\right)
$$

<hr>

{{< /details >}}

**7) 시간영역미분**

$$
\left\langle s^L\middle|\frac{d^n}{dt^n}f(t)u(t)\right\rangle=s^{n}\langle s^L|f\cdot u\rangle-s^{n-1}f\left(0\right)-s^{n-2}f^{\left(1\right)}\left(0\right)-s^{n-3}f^{\left(2\right)}\left(0\right)-\cdots
$$

$$
\left\langle s^L\middle|\frac{d^n}{dt^n}f(t)\right\rangle=s^{n}\langle s^L|f\rangle
$$

{{< details summary="proof" >}}

$$
\int^{\infty}_{0}dt\left[e^{-st}\frac{d^{n}}{dt^{n}}f\left(t\right)\right]
=\int^{\infty}_{0}dt\left[\frac{\partial}{\partial t}\left\lbrace e^{-st}\frac{\partial^{n-1}}{\partial t^{n-1}} f\left(t\right)\right\rbrace-\left(-s\right)e^{-st}\frac{\partial^{n-1}}{\partial t^{n-1}} f\left(t\right)\right]
$$

$$
=\left[ e^{-st}\frac{\partial^{n-1}}{\partial t^{n-1}} f\left(t\right)\right]^{\infty}_{0}
+s\int^{\infty}_{0}dt\left[e^{-st}\frac{\partial^{n-1}}{\partial t^{n-1}} f\left(t\right)\right]
$$

$∣f^{(n−1)}(t)∣≤Me^{αt}$, 이면 $\operatorname{Re}\lbrace s\rbrace>α$ 이어야 수렴한다. 

$$
=-f^{\left(n-1\right)}\left(0\right)
+s\left\lbrace-f^{\left(n-2\right)}\left(0\right)+s\int^{\infty}_{0}dt \left[e^{-st}\frac{\partial^{n-2}}{\partial t^{n-2}} f\left(t\right)\right]\right\rbrace
$$

따라서, 반복하면,

$$
\mathcal{L}\left\lbrace\frac{d^{n}}{dt^{n}}f\left(t\right)u(t)\right\rbrace\left(s\right)=s^{n}F\left(s\right)-s^{n-1}f\left(0\right)-s^{n-2}f^{\left(1\right)}\left(0\right)-s^{n-3}f^{\left(2\right)}\left(0\right)-\cdots
$$

양방향 변환에서는 

$$
\left[ e^{-st}\frac{\partial^{n-1}}{\partial t^{n-1}} f\left(t\right)\right]^{\infty}_{0} \to \left[ e^{-st}\frac{\partial^{n-1}}{\partial t^{n-1}} f\left(t\right)\right]^{\infty}_{-\infty} =0
$$

<hr>

{{< /details >}}    

**8) 시간영역적분**

$$
\left\langle s^L\middle|\int_0^{t}dt'\left\lbrack f\left(t'\right)\right\rbrack\right\rangle
=\langle s^L|u\ast f\rangle
=\langle s^L|u\rangle\langle s^L|f\rangle
=\frac{1}{s}\langle s|f\rangle
$$

$$
\left\langle s^L\middle|\int_{-\infty}^{t}dt'\left\lbrack f\left(t'\right)\right\rbrack\right\rangle
=\langle s^L|u\ast f\rangle
=\langle s^L|u\rangle\langle s^L|f\rangle
=\frac{1}{s}\langle s|f\rangle
$$

{{< details summary="proof" >}}

$$
\mathcal{L}\left\lbrace\int_{-\infty}^{t}dt'\left\lbrack u\left(t-t'\right)f\left(t'\right)\right\rbrack\right\rbrace\left(s\right)=\mathcal{L}\left\lbrace u\left(t\right)\ast f\left(t\right)\right\rbrace\left(s\right)=\frac{1}{s}\langle s|f\rangle
$$

<hr>

{{< /details >}}    

**9) s-영역미분**

$$
\langle s^L|t^n\cdot f\cdot u\rangle=\langle s|(\hat{t})^n|f\cdot u\rangle=(-1)^n\frac{d^n}{ds^n}\langle s|f\cdot u\rangle
$$

$$
\mathcal{L}\left\lbrace t^{n}f\left(t\right)\right\rbrace\left(s\right)
=\langle s|t^n\cdot f\rangle=\langle s|(\hat{t})^n|f\rangle=(-1)^n\frac{d^n}{ds^n}\langle s|f\rangle
$$

$$
\mathcal{L}\left\lbrace tu\left(t\right)\right\rbrace\left(s\right)
=\langle s|t\cdot u\rangle=\langle s|\hat{t}|u\rangle=(-1)^1\frac{d}{ds}\langle s|u\rangle
=\frac{1}{s^2}
$$

$$
\mathcal{L}\left\lbrace t^{n}u\left(t\right)\right\rbrace\left(s\right)
=\langle s|t^n\cdot u\rangle=\langle s|(\hat{t})^n|u\rangle=(-1)^n\frac{d^n}{ds^n}\langle s|u\rangle
=\frac{n!}{s^{n+1}}
$$

{{< details summary="proof" >}}

$$
\mathcal{L}\left\lbrace t^{n}f\left(t\right)\right\rbrace\left(\omega\right)
=\int^{\infty}_{-\infty}dt\left[e^{-st}t^n f\left(t\right)\right]
$$

$$
=\int^{\infty}_{-\infty}dt\left[f\left(t\right)\left(\frac{1}{-1}\right)^n\frac{\partial^n}{\partial s^n}e^{-st}\right]
=(-1)^n\frac{\partial^n}{\partial s^n}\int^{\infty}_{-\infty}dt\left[e^{-st}f\left(t\right)\right]
$$

$$
=(-1)^n\frac{d^n}{ds^n}\mathcal{L}\left\lbrace f\left(t\right)\right\rbrace\left(\omega\right)
$$

<hr>

{{< /details >}}

**9) initial value**

$$
f\left(0\right)=\lim_{s\to\infty}s\mathcal{L}\left\lbrace f\left(t\right)u(t)\right\rbrace\left(s\right)
=\lim_{s\to\infty}s \langle s|f\cdot u \rangle
$$

{{< details summary="proof" >}}

$$
\mathcal{L}\left\lbrace \frac{d}{dt} f\left(t\right)u(t)\right\rbrace\left(s\right)=s\mathcal{L}\left\lbrace f\left(t\right)u(t)\right\rbrace\left(s\right)-f\left(0\right)
$$

$$
\int^{\infty}_{0}dt\left[e^{-st}f'\right(t\left)\right]=s\mathcal{L}\left\lbrace f\left(t\right)u(t)\right\rbrace\left(s\right)-f\left(0\right)\quad
$$

<hr>

$$
\lim_{s\to\infty}\int^{\infty}_{0}dt\left[e^{-st}f'\right(t\left)\right]=\lim_{s\to\infty}\left[s\mathcal{L}\left\lbrace f\left(t\right)u(t)\right\rbrace\left(s\right)-f\left(0\right)\right]
$$

만약, $f'(t)$ 가 $e^{-st}$의 감소보다 증가량이 크지 않다면, (에너지 보존 법칙으로 인해, 물리 시스템의 응답, 공학적인 신호 등의 대부분 이 조건을 만족하는 함수들임)

$$
0=\lim_{s\to\infty}\left[s\mathcal{L}\left\lbrace f\left(t\right)u(t)\right\rbrace\left(s\right)-f\left(0\right)\right]
$$

$$
f\left(0\right)=\lim_{s\to\infty}s\mathcal{L}\left\lbrace f\left(t\right)u(t)\right\rbrace\left(s\right)
$$

<hr>

{{< /details >}}    

**10) final value**

- 단방향 라플라스 변환

$$
f\left(\infty\right)=\lim_{s\to0}s\mathcal{L}\left\lbrace f\left(t\right)u(t)\right\rbrace\left(s\right)
=\lim_{s\to 0}s \langle s|f\cdot u \rangle
$$

- 양방향 라플라스 변환

$$
f\left(\infty\right)=\lim_{s\to0}s\mathcal{L}\left\lbrace f\left(t\right)\right\rbrace\left(s\right)
=\lim_{s\to 0}s \langle s|f \rangle
=\langle s|\hat{D}_t|f\rangle
$$

$$
f\left(-\infty\right)=\lim_{s\to0}s\mathcal{L}\left\lbrace f\left(t\right)\right\rbrace\left(s\right)
=-\lim_{s\to 0}s \langle s|f\rangle
$$

{{< details summary="proof" >}}

<b>단방향 라플라스 변환.</b>

단, sF(s)의 모든 극점이 복소 평면의 좌반부(Re{s}<0)에 위치

$$
\mathcal{L}\left\lbrace \frac{d}{dt} f\left(t\right)u(t)\right\rbrace\left(s\right)=s\mathcal{L}\left\lbrace f\left(t\right)u(t)\right\rbrace\left(s\right)-f\left(0\right)
$$

$$
\int^{\infty}_{0}dt\left[e^{-st}f'\right(t\left)\right]=s\mathcal{L}\left\lbrace f\left(t\right)u(t)\right\rbrace\left(s\right)-f\left(0\right)\quad
$$

$$
\lim_{s\to 0}\int^{\infty}_{0}dt\left[e^{-st}f'\right(t\left)\right]=\lim_{s\to 0}\left[s\mathcal{L}\left\lbrace f\left(t\right)u(t)\right\rbrace\left(s\right)-f\left(0\right)\right]
$$

$$
f\left(\infty\right)-f\left(0\right)=\lim_{s\to 0}\left[s\mathcal{L}\left\lbrace f\left(t\right)u(t)\right\rbrace\left(s\right)-f\left(0\right)\right]
$$

$$
f\left(\infty\right)=\lim_{s\to0}s\mathcal{L}\left\lbrace f\left(t\right)u(t)\right\rbrace\left(s\right)
$$

<hr>

<b>양방향 라플라스 변환</b>

$$
\mathcal{L}\left\lbrace \frac{d}{dt} f\left(t\right)\right\rbrace\left(s\right)
=\langle s|\hat{D}_t|f\rangle
=s\langle s|f\rangle
$$

$$
\lim_{s\to 0}\int^{\infty}_{-\infty}dt\left[e^{-st}f'\right(t\left)\right]
=\lim_{s\to 0}\left\lbrace\int^{\infty}_{0}dt\left[e^{-st}f'\right(t\left)\right]+\int^{0}_{-\infty}dt\left[e^{-st}f'\right(t\left)\right]\right\rbrace
$$

$$
f\left(\infty\right)-f\left(-\infty\right)
=\lim_{s\to 0}s\langle s|f\rangle
$$

<b>$f(\infty)$ 최종값</b>, 우측신호일 경우, $f(-\infty)=0$ 이고. ROC는 허수축을 포함해야 함

$$
f\left(\infty\right)
=\lim_{s\to 0}s\langle s|f\rangle
$$

<b>$f(-\infty)$ 최종값</b>, 죄측신호일 경우, $f(\infty)=0$ 이고, ROC는 허수축을 포함해야 함

$$
f\left(-\infty\right)
=-\lim_{s\to 0}s\langle s|f\rangle
$$

{{< /details >}}

---

### 4. 라플라스 변환, 분포 라플라스 변환, ROC 관계 요약

**1) ROC (수렴 영역)**

-   **가장 중요:** 라플라스 변환 적분 $\int_{-\infty}^{\infty} dt [e^{-st}f(t)]$ 가 **수렴하는 복소 평면의 $s$ 값들의 집합**.
-   여기서 수렴은 **표준적인 수렴**일 수도, **분포적인 수렴**일 수도 있다.

**2) 표준 라플라스 변환**

-   정의: 적분이 **표준적인 의미로 수렴**할 때의 변환.
-   대상: 주로 시간 무한대에서 지수적으로 감쇠하는 신호.
-   **ROC 형태: 항상 열린 영역 (띠 또는 반평면).**

**3) 분포 라플라스 변환**

-   정의: 표준 적분이 어떤 열린 영역에서도 수렴하지 않는 신호들을 다루기 위해 **분포 개념을 확장하여 정의된 변환**.
-   대상: 표준 LT가 어려운 신호 (상수, 진동, 임펄스, 성장 신호 등) 포함.
-   **존재:** 표준 LT보다 넓은 범위의 신호에 대해 존재함이 보장됨.

**4) 핵심 관계: 신호, ROC, 변환 형태**

-   **ROC의 의미:** 근본적으로는 **원래 라플라스 변환 적분이 수렴하는 영역** (표준적 수렴이든 분포적 수렴이든)
-   ROC 형태가 신호와 변환 성질을 알려준다.
-   **(A) 신호가 지수적으로 감쇠 (또는 유한 길이)**
    -   **ROC:** **열린 영역** (표준 수렴).
    -   변환: 표준 LT 존재 (ROC에서 해석 함수). 분포 LT도 존재.
    -   FT: ROC에 허수축 포함 시 존재.

-   **(B) 신호가 진동 또는 상수 (성장 안함)**
    -   **ROC:** **특정 선 (예: $\operatorname{Re}\lbrace s\rbrace=0$)** (분포적 수렴).
    -   변환: 표준 LT는 열린 ROC 없음. **분포 LT는 존재**. 결과는 선 위 함수 또는 $s$ 영역 분포.
    -   FT: ROC가 $\operatorname{Re}\lbrace s\rbrace=0$ 인 것 **<=> 분포 푸리에 변환 존재**.

-   **(C) 신호가 지수적으로 성장**
    -   **ROC:** **열린 영역 (허수축 미포함)** (표준 수렴) **또는 공집합** (양쪽 성장).
    -   변환: 단방향 성장은 표준 LT 존재. 양방향 성장(실수 cosh/sinh)은 표준 LT 없음. **분포 LT는 존재**하나, ROC는 그대로 (허수축 미포함 또는 공집합).
    -   **FT:** **존재 안 함**.

**5) 결론**

-   ROC는 **라플라스 변환 적분(표준 또는 분포적)이 유효한 영역**
-   분포 LT에서도 ROC는 중요하며, **ROC 형태는 신호 시간 특성 및 FT 존재/형태의 핵심 정보**
-   분포 LT는 표준 LT가 안 되는 신호까지 다루게 해주는 도구이며, ROC는 그 이해의 열쇠

---

### 5. Practice

연구실 구성원들에게만 허용된 자료 입니다. [연습문제](https://hertz2hnu.atlassian.net/wiki/spaces/AJpAH3tcG9Jk/pages/53608611/b+LTI+System)

---