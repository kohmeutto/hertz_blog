+++
title = "(b) Continuous"
weight = 4
+++

---

### 1. 연속 스펙트럼과 복소 평면의 분지절단 (Branch Cut)

이산 공간(Discrete space)에서 연산자의 스펙트럼은 복소 평면 상에 고립된 점 형태의 특이점(Isolated singularity)으로 존재하며, 레졸번트는 이 극점들을 중심으로 로랑 급수(Laurent series) 전개를 이룬다. 이산 챕터에서 보았듯, 고립된 극점 $\lambda_m$ 을 감싸는 코시 닫힌 경로 적분 $\oint_{\Gamma_m}$ 을 통해 사영 연산자 $\hat{P}_m$(1차극)과 멱영 연산자 $\hat{N}_m$(2차 이상 극)을 산출하였다.

반면, 시스템의 차원이 무한대로 확장되거나 경계 조건이 개방(Open boundary)될 경우, 이산적인 고윳값 $\lambda_m$ 은 밀집되어 연속적인 스펙트럼을 형성한다. 이때 레졸번트 연산자 $R(z, \hat{A}) = (z\hat{I} - \hat{A})^{-1}$ 는 더 이상 고립된 극점을 갖지 않으며, 복소 평면 상의 특정 곡선을 따라 특이점이 조밀하게 배열된 분지절단(Branch cut)을 형성한다. 레졸번트는 이 절단선을 경계로 해석적 연속성(Analytic continuation)을 상실하며, 복소수 $z$ 가 절단선의 각기 다른 방향에서 접근할 때 대수적으로 서로 다른 극한값을 가지게 된다.

이 분지절단이 복소 평면 어디에 놓이는지는 연산자의 성질에 따라 갈린다. 본 챕터는 다음의 위계 위에서 전개된다.

- 가장 일반: 연산자 $\hat{A}$ 가 비정규(Non-normal) 특성을 포함하여, 연속 스펙트럼이 복소 평면 내 임의의 유향 곡선(Oriented smooth curve) $\Gamma$ 를 따라 분포한다. 이 경우 곡선을 가로지르는 도약을 복소 소호츠키-플레멜 정리로 산출한다(2·3절).
- 특수: 곡선 $\Gamma$ 가 실수축이고 연산자가 자기수반(Self-adjoint)이면, 고윳값이 실수로 제한되어 분지절단이 실수축 위에 정렬되고, 위 도약이 1차원 소호츠키-플레멜 정리로 환원되어 고전 스톤의 공식이 된다(4절).
- 경계: 스펙트럼이 곡선이 아니라 고립된 점이면(이산 스펙트럼), 곡선 도약이 아니라 그 점을 감싸는 닫힌 경로 적분으로 돌아간다(7절 예제).

그리고 위 어느 경우든, 레졸번트의 1차극은 사영 밀도(Projection density)를, 2차 이상의 극은 멱영 밀도(Nilpotent density)를 산출한다.

---

### 2. 복소 소호츠키-플레멜 정리와 스톤 공식의 일반형 (사영 밀도)

이산 공간에서 코시 닫힌 경로 적분 $\oint_{\Gamma_m}$ 을 통해 단일 사영 연산자 $\hat{P}_m$ 을 유도했던 대수적 과정은, 연속 공간에서 스펙트럼 곡선(분지절단면)을 가로지르는 레졸번트의 도약(Jump) 연산으로 치환된다. 본 절에서는 연산자 $\hat{A}$ 가 복소 평면 내 유향 곡선 $\Gamma$ 상에 연속 스펙트럼을 형성하는 일반적인 경우를 상정하고, 레졸번트의 1차극이 만드는 사영 밀도 $d\hat{P}(z)$ 를 산출한다.

부호 규약을 먼저 고정한다. 곡선 $\Gamma$ 의 진행 방향을 정하고, 그 진행 방향을 기준으로 좌측(왼쪽) 영역을 $+$측, 우측(오른쪽) 영역을 $-$측으로 정의한다. 곡선 위 관측점 $z$ 에 대하여 좌측에서 접근하는 극한점을 $z^+$, 우측에서 접근하는 극한점을 $z^-$ 라 하고, 곡선의 국소적 법선 벡터 $\vec{n}(z)$ 를 이용해 다음과 같이 적는다.

$$
z^\pm = z \pm \epsilon \, \vec{n}(z)
$$

이 규약 아래에서 다음의 사영 밀도가 도출된다.

$$
d\hat{P}(z) = \frac{1}{2\pi i} \left[ R(z^-, \hat{A}) - R(z^+, \hat{A}) \right] dz
$$

![소호츠키-플레멜 정리의 기하학적 적분 경로](image1.svg)

proof)

연속 스펙트럼이 분포하는 복소 평면 상의 곡선 구간 $\Gamma$ 를 둘러싸는 닫힌 적분 경로를 설정하고, 이 경로를 곡선 $\Gamma$ 에 무한히 밀착시키는 극한 흡수 원리(Limiting absorption principle)를 적용한다. 곡선을 수직으로 횡단하는 구간의 적분 기여도는 소멸하고, 곡선 $\Gamma$ 와 평행하게 좌측 경로($z^+$, 역방향 주행)와 우측 경로($z^-$, 순방향 주행)의 선적분만이 남아 다음의 극한 차분식을 형성한다.

$$
\Delta\hat{P}_{\Gamma} = \lim_{\epsilon \to 0^+} \frac{1}{2\pi i} \int_{\Gamma} \left[ R(z^-, \hat{A}) - R(z^+, \hat{A}) \right] dz
$$

적분 구간을 국소적인 미소 복소 척도 $dz$ 로 한정하면, 사영 밀도 $d\hat{P}(z)$ 를 정의하는 대수적 원형이 도출된다.

$$
d\hat{P}(z) = \lim_{\epsilon \to 0^+} \frac{1}{2\pi i} \left[ R(z^-, \hat{A}) - R(z^+, \hat{A}) \right] dz
$$

괄호 내부의 레졸번트 차분을 연산하기 위해, 실수축에 국한되었던 한계를 벗어나 복소 평면 내 유향 곡선에 대하여 성립하는 복소 소호츠키-플레멜 정리(Complex Sokhotski-Plemelj theorem)를 도입한다. 임의의 복소 함수 $f(\tau)$ 와 곡선 $\Gamma$ 상의 관측점 $z$ 에 대하여, 코시형 적분(Cauchy-type integral)의 좌극한($z^+$)과 우극한($z^-$)은 앞서 고정한 부호 규약 아래 다음과 같이 분할된다.

$$
\lim_{z' \to z^\pm} \frac{1}{2\pi i} \int_{\Gamma} \frac{f(\tau)}{\tau - z'} d\tau = \pm \frac{1}{2} f(z) + \frac{1}{2\pi i} \mathcal{P} \int_{\Gamma} \frac{f(\tau)}{\tau - z} d\tau
$$

여기서 $\mathcal{P}$ 는 복소 곡선 $\Gamma$ 상의 코시 주치(Cauchy Principal Value) 적분을 의미하며, $z^+$(좌측)에 $+\frac{1}{2}f(z)$, $z^-$(우측)에 $-\frac{1}{2}f(z)$ 가 대응한다.

이 정리를 레졸번트의 도약 차분에 적용하려면, 먼저 레졸번트가 사영 밀도에 대한 코시형 적분으로 표현됨을 확인해야 한다. 이 표현은 새로 도입하는 가정이 아니라, 이산 챕터에서 증명한 레졸번트의 부분분수 분해를 연속으로 옮긴 것이다.

이산 챕터의 반단순(멱영이 없는) 연산자는 스펙트럼 분해 $\hat{A} = \sum_m \lambda_m \hat{P}_m$ 으로 적히며, 사영 연산자는 완비성 $\sum_m \hat{P}_m = \hat{I}$ 와 직교성 $\hat{P}_m \hat{P}_n = \delta_{mn}\hat{P}_m$ 을 만족한다. 레졸번트의 분모 $z\hat{I} - \hat{A}$ 를 이 두 성질로 전개한다. 먼저 $z\hat{I}$ 를 완비성으로 풀어 쓴다.

$$
z\hat{I} = z\sum_m \hat{P}_m = \sum_m z\hat{P}_m
$$

이를 스펙트럼 분해와 함께 빼서 분모를 정리한다.

$$
z\hat{I} - \hat{A} = \sum_m z\hat{P}_m - \sum_m \lambda_m \hat{P}_m = \sum_m (z - \lambda_m)\hat{P}_m
$$

이제 $\sum_m \dfrac{1}{z - \lambda_m}\hat{P}_m$ 이 이 분모의 역행렬임을 직교성으로 확인한다. 두 합을 곱한다.

$$
\left( \sum_n (z - \lambda_n)\hat{P}_n \right)\left( \sum_m \frac{1}{z - \lambda_m}\hat{P}_m \right) = \sum_{n,m} \frac{z - \lambda_n}{z - \lambda_m}\hat{P}_n \hat{P}_m
$$

직교성 $\hat{P}_n \hat{P}_m = \delta_{nm}\hat{P}_m$ 을 적용하면 $n = m$ 인 항만 남는다.

$$
= \sum_m \frac{z - \lambda_m}{z - \lambda_m}\hat{P}_m = \sum_m \hat{P}_m = \hat{I}
$$

곱이 항등원이 되므로, 이산 레졸번트는 각 고윳값 $\lambda_m$ 에서 1차극을 가지고 그 잔여가 사영 연산자 $\hat{P}_m$ 인 부분분수 분해를 가진다.

$$
R(z, \hat{A}) = \sum_m \frac{\hat{P}_m}{z - \lambda_m}
$$

연속 스펙트럼에서는 고윳값 $\lambda_m$ 이 밀집되어 연속 변수 $\tau$ 가 되고, 이산 합 $\sum_m$ 은 곡선 적분 $\int_\Gamma$ 로, 낱개의 사영 연산자 $\hat{P}_m$ 은 미소 구간당 사영 연산자인 사영 밀도 $d\hat{P}(\tau)$ 로 바뀐다.

$$
\sum_m \frac{\hat{P}_m}{z - \lambda_m} \quad\longrightarrow\quad \int_{\Gamma} \frac{d\hat{P}(\tau)}{z - \tau}
$$

여기서 밀도 $d\hat{P}(\tau)$ 를 적분 변수 $d\tau$ 로 묶어 밀도 함수 $f(\tau)$ 를 정의한다. 즉 $d\hat{P}(\tau) = f(\tau)\,d\tau$ 로 두면, $f(\tau)$ 는 '단위 스펙트럼 폭당 사영 연산자'라는 연산자값 밀도가 된다. 이로써 1차극 부분의 레졸번트가 사영 밀도에 대한 코시형 적분으로 표현되며, 이는 새 가정이 아니라 위 이산 부분분수의 연속 극한이다.

$$
R(\zeta, \hat{A}) = \int_{\Gamma} \frac{d\hat{P}(\tau)}{\zeta - \tau} = \int_{\Gamma} \frac{f(\tau)}{\zeta - \tau}\,d\tau
$$

이 적분의 분모는 $\zeta - \tau$ 이고 위 정리의 분모는 $\tau - z'$ 이므로, 부호 관계 $\dfrac{1}{\zeta - \tau} = -\dfrac{1}{\tau - \zeta}$ 를 적용하여 레졸번트를 정리와 연결한다.

$$
R(\zeta, \hat{A}) = -\int_{\Gamma} \frac{f(\tau)}{\tau - \zeta} d\tau = -2\pi i \left( \frac{1}{2\pi i} \int_{\Gamma} \frac{f(\tau)}{\tau - \zeta} d\tau \right)
$$

관측점 $z$ 의 좌극한 $z^+$ 와 우극한 $z^-$ 에 대하여 정리를 대입한다. 좌극한($z^+$)의 분해는 다음과 같다.

$$
R(z^+, \hat{A}) = -2\pi i \left[ +\frac{1}{2} f(z) + \frac{1}{2\pi i} \mathcal{P} \int_{\Gamma} \frac{f(\tau)}{\tau - z} d\tau \right] = -\pi i f(z) + \mathcal{P} \int_{\Gamma} \frac{f(\tau)}{z - \tau} d\tau
$$

우극한($z^-$)의 분해는 다음과 같다.

$$
R(z^-, \hat{A}) = -2\pi i \left[ -\frac{1}{2} f(z) + \frac{1}{2\pi i} \mathcal{P} \int_{\Gamma} \frac{f(\tau)}{\tau - z} d\tau \right] = +\pi i f(z) + \mathcal{P} \int_{\Gamma} \frac{f(\tau)}{z - \tau} d\tau
$$

(두 식 모두 $-2\pi i \cdot \frac{1}{2\pi i}\mathcal{P}\int\frac{f(\tau)}{\tau-z}d\tau = -\mathcal{P}\int\frac{f(\tau)}{\tau-z}d\tau = +\mathcal{P}\int\frac{f(\tau)}{z-\tau}d\tau$ 로 정칙부의 분모 부호를 바꾸어 정리하였다.)

분해된 두 식을 도약 차분식에 대입하여 뺄셈을 수행한다.

$$
R(z^-, \hat{A}) - R(z^+, \hat{A}) = \left[ +\pi i f(z) + \mathcal{P} \int_{\Gamma} \frac{f(\tau)}{z - \tau} d\tau \right] - \left[ -\pi i f(z) + \mathcal{P} \int_{\Gamma} \frac{f(\tau)}{z - \tau} d\tau \right]
$$

차분 과정에서 복소 평면 전역으로 뻗어나가는 배경장인 코시 주치($\mathcal{P}\int$) 성분이 대수적으로 완전히 상쇄되어 소멸하며, 특이점에서의 국소 밀도 성분만이 보존된다.

$$
R(z^-, \hat{A}) - R(z^+, \hat{A}) = 2\pi i f(z)
$$

도출된 잔여항의 양변에 계수 $\frac{1}{2\pi i}$ 와 미소 변위 $dz$ 를 곱하여 사영 밀도의 정의($d\hat{P}(z) = f(z) dz$)로 환원한다.

$$
f(z) dz = \frac{1}{2\pi i} \left[ R(z^-, \hat{A}) - R(z^+, \hat{A}) \right] dz
$$

$$
d\hat{P}(z) = \frac{1}{2\pi i} \left[ R(z^-, \hat{A}) - R(z^+, \hat{A}) \right] dz
$$

복소 평면 내 임의의 유향 곡선 상에서 비정규 연산자의 사영 밀도를 레졸번트의 도약 차분으로부터 되살리는 이 결과물을, 실수축에 국한되지 않은 스톤의 공식(Stone's formula)의 일반형이라 명명한다. 단, 이 도약이 산출하는 것은 1차극에 대응하는 사영 밀도뿐이며, 2차 이상 극에 대응하는 멱영 밀도는 3절의 가중 도약으로 별도로 산출해야 한다.

proof) 복소 소호츠키-플레멜 정리의 기하학적 증명

*(1) 적분 경로의 기하학적 분할 및 특이점 우회*

유향 곡선 $\Gamma$ 상의 특이점 $z$ 에 접근하는 코시형 적분 $I(z') = \dfrac{1}{2\pi i} \int_{\Gamma} \dfrac{f(\tau)}{\tau - z'} d\tau$ 의 극한 $\lim_{z' \to z^\pm} I(z')$ 을 규명한다. 관측점 $z$ 를 중심으로 반경이 $\epsilon$ 인 극소 원 $C_\epsilon$ 을 설정하고, 원래의 곡선 $\Gamma$ 를 원의 외부 구간 $\Gamma_\epsilon = \Gamma \setminus (\Gamma \cap C_\epsilon)$ 과 원호 구간 $C_\epsilon^\pm$ 으로 분할한다. 좌측($+$측)에서 접근하는 $z^+$ 극한은 좌측 우회 반원 $C_\epsilon^+$ 를, 우측($-$측)에서 접근하는 $z^-$ 극한은 우측 우회 반원 $C_\epsilon^-$ 를 형성한다.

*(2) 외부 구간의 극한: 코시 주치(Principal Value)의 유도*

특이점 $z$ 를 제외한 곡선 구간 $\Gamma_\epsilon$ 에 대한 적분은 $\epsilon \to 0^+$ 극한에서 특이점이 배제된 유효 면적만을 적분하는 방식이 되며, 이는 복소 평면 상의 코시 주치 적분으로 정의된다.

$$
\lim_{\epsilon \to 0^+} \frac{1}{2\pi i} \int_{\Gamma_\epsilon} \frac{f(\tau)}{\tau - z} d\tau = \frac{1}{2\pi i} \mathcal{P} \int_{\Gamma} \frac{f(\tau)}{\tau - z} d\tau
$$

*(3) 미소 원호 구간의 극한: 극점의 반유수(Half Residue) 산출*

특이점 $z$ 근방의 미소 반원 $C_\epsilon^\pm$ 경로에 대하여, 변수 $\tau$ 를 국소적으로 극좌표 매개변수화하여 $\tau = z + \epsilon e^{i\theta}$ 로 치환한다. 미분 요소는 $d\tau = i\epsilon e^{i\theta} d\theta$ 가 된다. 함수 $f(\tau)$ 가 $z$ 근방에서 횔더 연속(Hölder continuous) 조건을 만족하면, $\epsilon \to 0^+$ 극한에서 $f(\tau) \to f(z)$ 로 근사된다. 반원 적분의 일반형은 다음과 같이 정리된다.

$$
\lim_{\epsilon \to 0^+} \frac{1}{2\pi i} \int_{C_\epsilon^\pm} \frac{f(\tau)}{\tau - z} d\tau = \frac{f(z)}{2\pi i} \int \frac{i\epsilon e^{i\theta}}{\epsilon e^{i\theta}} d\theta = \frac{f(z)}{2\pi} \int d\theta = \frac{f(z)}{2\pi} \Delta\theta
$$

좌측($+$측) 접근 $z^+$ 에 대응하는 반원 $C_\epsilon^+$ 는 각도가 $+\pi$ 만큼 변하는 경로($\Delta\theta = +\pi$)를 형성한다.

$$
\lim_{\epsilon \to 0^+} \frac{1}{2\pi i} \int_{C_\epsilon^+} \frac{f(\tau)}{\tau - z} d\tau = \frac{f(z)}{2\pi} (+\pi) = +\frac{1}{2} f(z)
$$

우측($-$측) 접근 $z^-$ 에 대응하는 반원 $C_\epsilon^-$ 는 각도가 $-\pi$ 만큼 변하는 경로($\Delta\theta = -\pi$)를 형성한다.

$$
\lim_{\epsilon \to 0^+} \frac{1}{2\pi i} \int_{C_\epsilon^-} \frac{f(\tau)}{\tau - z} d\tau = \frac{f(z)}{2\pi} (-\pi) = -\frac{1}{2} f(z)
$$

*(4) 정리의 해석학적 완성*

외부 구간(코시 주치)과 미소 반원(반유수)의 기여를 합산하면, 임의의 복소 유향 곡선에 대한 소호츠키-플레멜 정리가 부호 일관되게 완성된다. $z^+$(좌측)에는 $+\frac{1}{2}f(z)$ 가, $z^-$(우측)에는 $-\frac{1}{2}f(z)$ 가 더해진다.

$$
\lim_{z' \to z^\pm} \frac{1}{2\pi i} \int_{\Gamma} \frac{f(\tau)}{\tau - z'} d\tau = \pm \frac{1}{2} f(z) + \frac{1}{2\pi i} \mathcal{P} \int_{\Gamma} \frac{f(\tau)}{\tau - z} d\tau
$$

이 결과를 본문의 레졸번트 도약 차분에 대입하면, 코시 주치 항이 상쇄되고 $f(z)$ 기원의 사영 밀도 성분만이 보존되어, 연속 공간 사영 밀도의 대수적 분리 정당성이 확립된다.

---

### 3. 복소 스펙트럼의 멱영 밀도 (Nilpotent Density): 고차극 가중 도약

2절의 도약은 레졸번트의 1차극만을 잡아 사영 밀도를 산출하였다. 그러나 연산자 $\hat{A}$ 가 비정규(Non-normal)여서 대각화에 결함이 있으면, 레졸번트는 이산 챕터의 로랑 급수에서 보았듯 2차 이상의 극점을 가진다. 복소 곡선 $\Gamma$ 위에서 레졸번트의 스펙트럼 표현은 사영 밀도 항과 멱영 밀도 항으로 전개된다.

$$
R(z, \hat{A}) = \int_{\Gamma} \frac{d\hat{P}(\tau)}{z - \tau} + \int_{\Gamma} \frac{d\hat{N}(\tau)}{(z - \tau)^2} + \cdots
$$

2절의 1차극 코시형 적분은 우변 첫 항만 표현하므로, 둘째 항인 멱영 밀도 $d\hat{N}(z)$ 는 별도의 가중 도약으로 산출해야 한다. 이산 챕터에서 멱영 연산자를 $(z - \lambda_m)$ 가중 적분 $\hat{N}_m = \frac{1}{2\pi i}\oint_{\Gamma_m}(z-\lambda_m)R(z)dz$ 로 정의했던 논리를 연속 곡선으로 확장한다.

$$
d\hat{N}(z) = \frac{1}{2\pi i} \left[ (z^- - z) R(z^-, \hat{A}) - (z^+ - z) R(z^+, \hat{A}) \right] dz
$$

proof)

이산 공간의 레졸번트 적분에서 규명한 바와 같이, 연산자 항등식 $\hat{A}R(z, \hat{A}) = zR(z, \hat{A}) - \hat{I}$ 가 복소 평면 전체에서 성립한다. 이 항등식의 변수 $z$ 에 곡선 좌극한 $z^+$ 와 우극한 $z^-$ 를 대입하고, 도약 차분을 적용한다.

$$
\frac{1}{2\pi i} \left[ \hat{A}R(z^-) - \hat{A}R(z^+) \right] dz = \frac{1}{2\pi i} \left[ (\zeta R)_- - (\zeta R)_+ \right] dz - \frac{1}{2\pi i} \left[ \hat{I} - \hat{I} \right] dz
$$

여기서 $(\zeta R)_\pm = z^\pm R(z^\pm)$ 이며, 관측점 자체가 복소 변수 $\zeta = z^\pm$ 로 작용한다. 우변의 두 번째 항인 항등 연산자 $\hat{I}$ 는 특이점이 없는 전해석 함수(Entire function)이므로 분지절단에서의 도약 값이 0으로 소멸한다. 좌변은 연산자 $\hat{A}$ 와 사영 밀도 $d\hat{P}(z)$ 의 곱인 $\hat{A}\,d\hat{P}(z)$ 로 치환된다(2절에서 $\frac{1}{2\pi i}[R(z^-) - R(z^+)]dz = d\hat{P}(z)$ 를 유도하였으므로, 양변 좌측에 $\hat{A}$ 를 곱한 것이다).

남은 우변 첫 번째 항 내부의 변수 $\zeta$ 를 $\zeta = (\zeta - z) + z$ 로 분할하여 전개한다.

$$
\hat{A}\,d\hat{P}(z) = z \left( \frac{1}{2\pi i} \left[ R(z^-) - R(z^+) \right] dz \right) + \frac{1}{2\pi i} \left[ (\zeta - z)R(z^-) - (\zeta - z)R(z^+) \right] dz
$$

우변의 첫 번째 항은 사영 밀도의 정의에 의해 $z\,d\hat{P}(z)$ 가 된다. 두 번째 항은 $\zeta - z = z^\pm - z = \pm\epsilon\vec{n}(z)$ 의 가중을 가지는 도약으로, 1차극만 존재할 경우 $\epsilon \to 0$ 극한에서 0이 되지만 2차극이 존재하면 그 잔여가 보존되어 멱영 밀도 $d\hat{N}(z)$ 와 일치한다.

$$
d\hat{N}(z) = \frac{1}{2\pi i} \left[ (z^- - z) R(z^-, \hat{A}) - (z^+ - z) R(z^+, \hat{A}) \right] dz
$$

따라서 이산 공간의 연산자 분해 항등식 $\hat{A}\hat{P}_m = \lambda_m\hat{P}_m + \hat{N}_m$ 은 복소 연속 공간에서도 어떠한 대수적 비약 없이 밀도 항등식으로 동치 변환된다.

$$
\hat{A}\,d\hat{P}(z) = z\,d\hat{P}(z) + d\hat{N}(z)
$$

이로써 Gemini 식 전개에서 누락되었던 2차극 성분, 즉 비정규성의 핵심인 멱영 밀도가 가중 도약을 통해 빠짐없이 복원된다. 사영 밀도(1차극)와 멱영 밀도(2차극)가 함께 갖추어져야 비정규 연산자의 복소 스펙트럼 측도가 온전하게 기술된다.

---

### 4. 특수형: 자기수반 연산자와 실수축 상의 스톤의 공식

연산자 $\hat{A}$ 가 자기수반(Self-adjoint 또는 에르미트) 연산자인 경우, 연산자의 모든 고윳값은 실수로 제한된다(Hermitian 챕터에서 고유방정식 $\hat{A}|\lambda\rangle = \lambda|\lambda\rangle$ 에 $\langle\lambda|$ 를 내적하여 $\lambda = \lambda^\ast$ 를 증명하였다). 따라서 연속 스펙트럼 구간 $\Omega$ 는 복소 평면의 실수축 상에 정렬된 분지절단(Branch cut)을 형성한다. 이 특수한 기하학적 구조에서는 2절의 일반화된 복소 법선 극한이 실수축에 수직으로 밀착하는 고전적 극한 흡수 원리로 환원되고, 곡선 도약은 1차원 분포 이론의 소호츠키-플레멜 정리로 환원된다. 또한 자기수반 연산자는 정규 연산자이므로 멱영 밀도가 $d\hat{N}(\nu) = \hat{0}$ 으로 소멸한다.

$$
d\hat{P}(\nu) = \delta(\nu - \hat{A}) d\nu
$$

proof)

스펙트럼 구간 $[\nu_1, \nu_2] \subset \mathbb{R}$ 을 둘러싸는 복소 평면 상의 직사각형 경로를 실수축에 무한히 밀착시키는 극한 흡수 원리를 적용한다.

수직 경로의 적분 기여도는 $\epsilon \to 0^+$ 극한에서 소멸하며, 실수축과 평행하게 주행하는 상단 경로($z = \nu + i\epsilon$, 역방향 주행)와 하단 경로($z = \nu - i\epsilon$, 순방향 주행)의 선적분만이 보존되어 다음의 극한 차분식을 형성한다. 2절의 곡선 부호 규약에서 실수축의 진행 방향을 $+\nu$ 로 잡으면 좌측($+$측)은 상반평면($z = \nu + i\epsilon$), 우측($-$측)은 하반평면($z = \nu - i\epsilon$)에 대응한다.

$$
\Delta\hat{P}_{[\nu_1, \nu_2]} = \lim_{\epsilon \to 0^+} \frac{1}{2\pi i} \int_{\nu_1}^{\nu_2} \left[ R(\nu - i\epsilon, \hat{A}) - R(\nu + i\epsilon, \hat{A}) \right] d\nu
$$

적분 구간을 국소적인 미소 실수 척도 $d\nu$ 로 한정하면, 사영 밀도 $d\hat{P}(\nu)$ 를 정의하는 대수적 원형이 도출된다.

$$
d\hat{P}(\nu) = \lim_{\epsilon \to 0^+} \frac{1}{2\pi i} d\nu \left[ R(\nu - i\epsilon, \hat{A}) - R(\nu + i\epsilon, \hat{A}) \right]
$$

괄호 내부의 레졸번트 차분을 연산하기 위해 실수 변수 $x$ 에 대하여 특이점을 우회하는 적분 경로의 해석학적 거동을 정의하는 1차원 소호츠키-플레멜 정리(Sokhotski-Plemelj theorem)를 도입한다.

$$
\lim_{\epsilon \to 0^+} \frac{1}{x \pm i\epsilon} = \mathcal{P} \left( \frac{1}{x} \right) \mp i\pi \delta(x)
$$

독립 변수 $x$ 를 연속 스펙트럼의 관측점 $\nu$ 와 자기수반 연산자 $\hat{A}$ 의 대수적 차이인 $(\nu - \hat{A})$ 로 치환하여 레졸번트 연산자에 정리를 전개한다. 좌변의 레졸번트 극한은 발산하지 않는 코시 주치(Cauchy Principal Value, $\mathcal{P}$) 성분과 특이점에서의 붕괴 성분인 디랙 델타 함수(Dirac delta function) 성분으로 분할된다.

$$
R(\nu \pm i\epsilon, \hat{A}) = \mathcal{P} \left( \frac{1}{\nu - \hat{A}} \right) \mp i\pi \delta(\nu - \hat{A})
$$

이 항등식을 도약 연산식에 대입하여 하단 극한($\nu - i\epsilon$)과 상단 극한($\nu + i\epsilon$)의 대수적 차분을 산출한다.

$$
R(\nu - i\epsilon, \hat{A}) - R(\nu + i\epsilon, \hat{A}) = \left[ \mathcal{P} \left( \frac{1}{\nu - \hat{A}} \right) + i\pi \delta(\nu - \hat{A}) \right] - \left[ \mathcal{P} \left( \frac{1}{\nu - \hat{A}} \right) - i\pi \delta(\nu - \hat{A}) \right]
$$

차분 과정에서 배경장을 형성하는 코시 주치 성분은 대수적으로 상쇄되어 소거되며, 상태를 특정하는 델타 함수 성분만이 $2i\pi \delta(\nu - \hat{A})$ 로 보존된다. 이 결과를 본래의 밀도 식에 대입하면 $2\pi i$ 계수가 소거되며 최종 항등식으로 귀결된다.

$$
d\hat{P}(\nu) = \delta(\nu - \hat{A}) d\nu
$$

자기수반성이 보장된 시스템에서 실수축으로의 극한 흡수 원리를 통해 유도되는 이 결과가, 사영 측도를 완벽하게 보존하는 고전적 스톤의 공식이다.

proof) 1차원 소호츠키-플레멜 정리의 대수적 증명

*(1) 복소 분수의 대수적 분리 (실수화)*

극한 대상이 되는 복소 분수 함수 $f_\epsilon(x) = \dfrac{1}{x \pm i\epsilon}$ 에 켤레 복소수 $x \mp i\epsilon$ 를 분모와 분자에 곱하여 실수부와 허수부로 분리한다.

$$
\frac{1}{x \pm i\epsilon} = \frac{x \mp i\epsilon}{(x \pm i\epsilon)(x \mp i\epsilon)} = \frac{x \mp i\epsilon}{x^2 + \epsilon^2} = \frac{x}{x^2 + \epsilon^2} \mp i \frac{\epsilon}{x^2 + \epsilon^2}
$$

우변의 첫 번째 항은 정칙부의 기원이 되는 실수부 함수이며, 두 번째 항은 사영 밀도의 기원이 되는 허수부 함수이다. 이 두 함수에 대하여 극한 $\epsilon \to 0^+$ 을 취할 때의 해석학적 거동을 각각 증명한다.

*(2) 허수부의 극한: 디랙 델타 함수의 유도*

허수부 함수 $D_\epsilon(x) = \dfrac{\epsilon}{x^2 + \epsilon^2}$ 는 실수축 상에서 로렌츠 분포(Lorentzian)를 가진다. 이 함수를 임의의 시험 함수 $\phi(x)$ 와 함께 무한 구간에서 적분하고 실수 변수 치환 $x = \epsilon y$, $dx = \epsilon dy$ 를 적용한다.

$$
\lim_{\epsilon \to 0^+} \int_{-\infty}^{\infty} \frac{\epsilon}{x^2 + \epsilon^2} \phi(x) dx = \lim_{\epsilon \to 0^+} \int_{-\infty}^{\infty} \frac{\epsilon}{(\epsilon y)^2 + \epsilon^2} \phi(\epsilon y) (\epsilon dy) = \lim_{\epsilon \to 0^+} \int_{-\infty}^{\infty} \frac{1}{y^2 + 1} \phi(\epsilon y) dy
$$

극한 $\epsilon \to 0^+$ 을 적분 내부로 전개하면 $\phi(\epsilon y) \to \phi(0)$ 이 되며, 남은 적분 $\int_{-\infty}^{\infty} \frac{1}{y^2 + 1} dy$ 은 아크탄젠트(Arctangent) 함수의 특성에 의해 $\pi$ 로 수렴한다.

$$
= \phi(0) \int_{-\infty}^{\infty} \frac{1}{y^2 + 1} dy = \pi \phi(0)
$$

분포 이론의 정의에서, 임의의 함수 $\phi(x)$ 에 곱하여 적분했을 때 그 함숫값 $\phi(0)$ 만을 남기는 대상은 디랙 델타 함수 $\delta(x)$ 이다. 따라서 허수부는 다음의 극한으로 종결된다.

$$
\lim_{\epsilon \to 0^+} \frac{\epsilon}{x^2 + \epsilon^2} = \pi \delta(x)
$$

*(3) 실수부의 극한: 코시 주치(Principal Value)의 유도*

실수부 함수 $P_\epsilon(x) = \dfrac{x}{x^2 + \epsilon^2}$ 는 기함수(Odd function)이다. $x = 0$ 근방에서 발산하는 특이점의 적분을 정의하기 위해 시험 함수 $\phi(x)$ 에 대입하여 극한을 취한다.

$$
\lim_{\epsilon \to 0^+} \int_{-\infty}^{\infty} \frac{x}{x^2 + \epsilon^2} \phi(x) dx
$$

적분을 $x = 0$ 을 중심으로 대칭적인 미소 구간 $[-\delta, \delta]$ 와 그 외부 구간으로 분할한다. 외부 구간에서는 $\epsilon \to 0$ 극한 시 특이점이 없으므로 $\dfrac{x}{x^2} = \dfrac{1}{x}$ 로 자연스럽게 수렴한다. 내부 미소 구간 $[-\delta, \delta]$ 에서는 시험 함수를 $\phi(x) = \phi(0) + x\psi(x)$ 로 테일러 전개하여 대입한다.

$$
\int_{-\delta}^{\delta} \frac{x}{x^2 + \epsilon^2} \left[ \phi(0) + x\psi(x) \right] dx = \phi(0) \int_{-\delta}^{\delta} \frac{x}{x^2 + \epsilon^2} dx + \int_{-\delta}^{\delta} \frac{x^2}{x^2 + \epsilon^2} \psi(x) dx
$$

첫 번째 항의 피적분 함수 $\dfrac{x}{x^2 + \epsilon^2}$ 는 기함수이므로 대칭 구간 $[-\delta, \delta]$ 에 대한 적분은 자명하게 0으로 소멸한다. 두 번째 항은 $\epsilon \to 0$ 극한에서 특이점이 상쇄되어 적분 가능한 값으로 수렴한다. 결과적으로 기함수의 대칭성으로 발산 특이점을 상쇄하고 그 외의 유효 면적만을 적분하는 이 방식이 1차원 코시 주치의 정의와 일치한다.

$$
\lim_{\epsilon \to 0^+} \frac{x}{x^2 + \epsilon^2} = \mathcal{P}\left(\frac{1}{x}\right)
$$

*(4) 정리의 대수적 완성*

실수부와 허수부의 극한 결과를 본래의 분리 식에 대입하면, 실수축 상에서의 소호츠키-플레멜 정리가 완성된다.

$$
\lim_{\epsilon \to 0^+} \frac{1}{x \pm i\epsilon} = \lim_{\epsilon \to 0^+} \left( \frac{x}{x^2 + \epsilon^2} \mp i \frac{\epsilon}{x^2 + \epsilon^2} \right) = \mathcal{P}\left(\frac{1}{x}\right) \mp i\pi \delta(x)
$$

---

<div style="width:100%;max-width:800px;margin:2rem auto;border:1px solid #ddd;border-radius:8px;overflow:hidden;font-family:'Times New Roman',Times,serif;">
<div style="background-color:#f8f9fa;padding:15px;border-bottom:1px solid #ddd;">
<h4 style="margin:0 0 10px 0;color:#333;text-align:center;">소호츠키-플레멜 정리 대수적 분해 시뮬레이터</h4>
<div style="display:flex;align-items:center;justify-content:center;gap:15px;">
<label for="eps-slider" style="font-style:italic;font-size:1.1rem;">ε = <span id="eps-val" style="font-weight:bold;color:#cc0000;">0.50</span></label>
<input type="range" id="eps-slider" min="0.01" max="1.0" step="0.01" value="0.5" style="width:60%;cursor:pointer;">
</div>
</div>
<div style="position:relative;background-color:#ffffff;padding:20px;">
<canvas id="sokhotski-canvas" width="760" height="400" style="width:100%;height:auto;border:1px solid #eee;"></canvas>
<div style="position:absolute;top:30px;left:30px;background:rgba(255,255,255,0.9);padding:10px;border:1px solid #ddd;border-radius:4px;box-shadow:0 2px 4px rgba(0,0,0,0.1);">
<div style="display:flex;align-items:center;margin-bottom:5px;">
<div style="width:20px;height:3px;background-color:#0055cc;margin-right:10px;"></div>
<span style="font-style:italic;">실수부 (코시 주치): <span style="font-family:serif;">x / (x² + ε²)</span></span>
</div>
<div style="display:flex;align-items:center;">
<div style="width:20px;height:3px;background-color:#cc0000;margin-right:10px;"></div>
<span style="font-style:italic;">허수부 (디랙 델타): <span style="font-family:serif;">ε / (x² + ε²)</span></span>
</div>
</div>
</div>
<div style="padding:10px 20px;background-color:#f8f9fa;border-top:1px solid #ddd;font-size:0.9rem;color:#555;text-align:center;">
슬라이더를 왼쪽으로 이동하여 ε → 0 극한에서의 대수적 붕괴 양상을 관찰하십시오.
</div>
</div>
<script>
(function() {
function init() {
const canvas = document.getElementById('sokhotski-canvas');
if(!canvas) return;
const ctx = canvas.getContext('2d');
const slider = document.getElementById('eps-slider');
const valueDisplay = document.getElementById('eps-val');
const width = canvas.width, height = canvas.height;
const xMin = -3, xMax = 3, yMin = -5, yMax = 15;
function mapX(x) { return ((x - xMin) / (xMax - xMin)) * width; }
function mapY(y) { return height - ((y - yMin) / (yMax - yMin)) * height; }
function drawAxes() {
ctx.beginPath(); ctx.strokeStyle = '#999'; ctx.lineWidth = 1;
ctx.moveTo(0, mapY(0)); ctx.lineTo(width, mapY(0));
ctx.moveTo(mapX(0), 0); ctx.lineTo(mapX(0), height); ctx.stroke();
ctx.fillStyle = '#666'; ctx.font = "italic 14px 'Times New Roman'";
ctx.fillText("0", mapX(0) - 15, mapY(0) + 20);
}
function drawFunction(fn, color, lineWidth) {
ctx.beginPath(); ctx.strokeStyle = color; ctx.lineWidth = lineWidth;
const step = (xMax - xMin) / 500; let first = true;
for (let x = xMin; x <= xMax; x += step) {
const y = fn(x);
if (y > yMax + 5 || y < yMin - 5) { first = true; continue; }
if (first) { ctx.moveTo(mapX(x), mapY(y)); first = false; }
else { ctx.lineTo(mapX(x), mapY(y)); }
}
ctx.stroke();
}
function render() {
const eps = parseFloat(slider.value);
valueDisplay.textContent = eps.toFixed(2);
ctx.clearRect(0, 0, width, height); drawAxes();
drawFunction((x) => x / (x * x + eps * eps), '#0055cc', 2.5);
drawFunction((x) => eps / (x * x + eps * eps), '#cc0000', 2.5);
}
slider.addEventListener('input', render);
render();
}
if (document.readyState === 'loading') {
document.addEventListener('DOMContentLoaded', init);
} else {
init();
}
})();
</script>

---

### 5. 연속 공간 연산자의 대수적 스펙트럼 분해

2절의 사영 밀도 $d\hat{P}(z)$ 와 3절의 멱영 밀도 $d\hat{N}(z)$ 를 전체 연속 스펙트럼 곡선 $\Gamma$ 에 대하여 적분함으로써, 일반화 챕터에서 구축한 대수적 분해 구조를 해석학적으로 복원한다.

$$
\hat{A} = \int_{\Gamma} \big[ z \, d\hat{P}(z) + d\hat{N}(z) \big]
$$

연속 공간 상호 기저의 직교 규격화 조건은 미소 구간 밀도 간의 곱을 통해 델타 함수 형태의 사영 측도로 보장된다. 제1 레졸번트 항등식을 도약 연산에 대입하여 밀도의 직교성을 증명한다.

$$
d\hat{P}(z) d\hat{P}(z') = \delta(z - z') d\hat{P}(z) dz'
$$

proof)

서로 다른 관측점 $z$ 와 $z'$ 에 대하여 도약 연산의 곱을 전개하면 $R(z^\pm) R(z'^\pm)$ 항들이 생성된다. 제1 레졸번트 항등식 $R(z)R(w) = \dfrac{R(z) - R(w)}{w - z}$ 에 의해 이들의 곱은 $\dfrac{1}{z' - z}$ 형태의 차분으로 분리된다.

극한 $\epsilon \to 0$ 조건에서 $z \neq z'$ 일 경우, 분모가 0이 되지 않으므로 도약의 차분은 상쇄되어 영연산자 $\hat{0}$ 으로 소멸한다. 오직 $z = z'$ 인 국소 지점에서만 $\epsilon$ 에 의한 극점 발산이 발생하며, 이는 분포 이론에 의해 델타 함수 $\delta(z - z')$ 로 수렴한다. 따라서 연속 공간 내 이종 특이점 간의 대수적 직교성이 성립한다.

---

### 6. (정칙부의 확장) 코시 주치 적분과 환원 레졸번트 밀도

이산 공간의 정칙부(Regular part) 상수항이었던 환원 레졸번트 $\hat{S}_m$ 은 관측 공간을 제외한 모든 타 공간들의 배경장 역작용소 합($\sum_{l \neq m}$)으로 규정되었다. 연속 스펙트럼 공간에서는 이산적인 합산 기호 $\sum$ 이 적분 기호 $\int$ 로 대체되며, 관측 특이점 $z$ 를 제외한 나머지 연속 구간에 대한 기여도를 계산해야 한다.

2절의 복소 소호츠키-플레멜 정리 전개 과정에서 확인하였듯, 특이점을 포함하는 적분 구간은 델타 함수(사영 밀도) 성분과 코시 주치 성분으로 분리된다. 스톤의 공식 도출 과정에서 델타 함수 성분을 차감으로 상쇄시키고 남았던 바로 그 코시 주치(Cauchy Principal Value, $\mathcal{P}$) 성분이 연속 공간의 환원 레졸번트 $\hat{S}(z)$ 를 대수적으로 정의한다.

$$
\hat{S}(z) = \mathcal{P} \int_{\Gamma} \frac{d\hat{P}(z')}{z - z'}
$$

이산 공간에서 증명된 직교성 $\hat{P}_m \hat{S}_m = \hat{0}$ 과 대칭적으로, 연속 공간에서도 국소 사영 밀도 $d\hat{P}(z)$ 와 환원 레졸번트 $\hat{S}(z)$ 간의 대수적 직교성이 보존된다.

$$
d\hat{P}(z) \hat{S}(z) = d\hat{P}(z) \left( \mathcal{P} \int_{\Gamma} \frac{d\hat{P}(z')}{z - z'} \right) = \mathcal{P} \int_{\Gamma} \frac{\delta(z - z') d\hat{P}(z)}{z - z'} = \hat{0}
$$

(특이점 $z = z'$ 지점은 주치 적분의 정의에 의해 사전 배제되므로 델타 함수와의 내적은 항상 0으로 소멸한다.)

---

### 7. 예제

본 절은 세 가지 사례로 위계를 교차 검증한다. 7-1은 곡선이 실수축이고 멱영이 0인 자기수반 연속 스펙트럼(4절의 특수형), 7-2는 곡선이 아니라 고립된 복소 점에 스펙트럼이 있어 닫힌 경로 적분으로 돌아가는 경우, 7-3은 고립된 복소 점에 멱영까지 살아 있어 사영 밀도와 멱영 밀도를 모두 산출해야 하는 경우이다.

#### 7-1. 위치 연산자 (Position Operator): 자기수반·실수축·멱영 0

무한 차원 힐베르트 공간 $L^2(\mathbb{R})$ 상에서 작용하는 자기수반 연속 연산자인 위치 연산자 $\hat{X}$ 를 통해, 4절의 실수축 스톤 공식이 어떻게 연속 사영 밀도 $d\hat{P}(\nu)$ 를 산출하는지 검증한다.

$$
\hat{X} |x\rangle = x |x\rangle
$$

**1) 특성 방정식의 붕괴와 연속 스펙트럼**

위치 연산자 $\hat{X}$ 는 임의의 실수 $x \in \mathbb{R}$ 전체 구간에 대하여 연속적인 고윳값을 가진다. 무한 차원 공간이므로 $\det(\hat{X} - \lambda\hat{I}) = 0$ 이라는 행렬식 기반의 특성 방정식은 성립하지 않으며, 고윳값들은 실수축 전체를 덮는 분지절단 $\Omega = (-\infty, \infty)$ 을 형성한다. 위치 연산자는 자기수반이므로 고윳값이 실수임이 보장되고, 분지절단이 실수축 위에 놓여 4절의 실수축 스톤 공식이 적용 가능하다.

**2) 레졸번트 전개 및 도약 연산의 적용**

위치 연산자의 레졸번트 $R(z, \hat{X}) = (z\hat{I} - \hat{X})^{-1}$ 의 대각 성분은 위치 기저 표상(Position representation)에서 다음과 같이 기술된다.

$$
\langle x | R(z, \hat{X}) | x' \rangle = \frac{1}{z - x} \delta(x - x')
$$

이 대각 성분이 2절의 코시형 적분 표현 $R(\zeta, \hat{A}) = \int_\Gamma f(\tau)/(\zeta - \tau)\,d\tau$ 와 일치함을 확인한다. 위치 연산자의 사영 밀도 함수는 위치 고유상태 사영 $f(\nu) = |\nu\rangle\langle\nu|$ 이며, 이를 코시형 적분에 대입한다.

$$
R(z, \hat{X}) = \int_{-\infty}^{\infty} \frac{|\nu\rangle\langle\nu|}{z - \nu}\,d\nu
$$

이 연산자의 위치 기저 행렬 성분을 계산한다.

$$
\langle x | R(z, \hat{X}) | x' \rangle = \int_{-\infty}^{\infty} \frac{\langle x | \nu \rangle \langle \nu | x' \rangle}{z - \nu}\,d\nu
$$

위치 고유상태의 정규직교 관계 $\langle x | \nu \rangle = \delta(x - \nu)$ 를 대입한다.

$$
= \int_{-\infty}^{\infty} \frac{\delta(x - \nu)\,\delta(\nu - x')}{z - \nu}\,d\nu
$$

델타 함수의 필터링 성질로 $\nu = x$ 를 대입하면 적분이 풀려, 위에서 적은 대각 성분과 정확히 일치한다.

$$
= \frac{\delta(x - x')}{z - x}
$$

따라서 2절의 코시형 적분 표현이 위치 연산자에서 사영 밀도 함수 $f(\nu) = |\nu\rangle\langle\nu|$ 로 구체적으로 실현됨이 확인된다. 이제 분지절단 상의 관측점 $\nu$ 에 대하여 레졸번트 극한 차분을 전개한다. 두 분수를 통분한다.

$$
R(\nu - i\epsilon, \hat{X}) - R(\nu + i\epsilon, \hat{X}) = \frac{1}{\nu - i\epsilon - \hat{X}} - \frac{1}{\nu + i\epsilon - \hat{X}}
$$

분자를 정리한다.

$$
(\nu + i\epsilon - \hat{X}) - (\nu - i\epsilon - \hat{X}) = 2i\epsilon
$$

분모를 정리한다.

$$
(\nu - i\epsilon - \hat{X})(\nu + i\epsilon - \hat{X}) = (\nu - \hat{X})^2 + \epsilon^2
$$

분자와 분모를 결합한다.

$$
R(\nu - i\epsilon, \hat{X}) - R(\nu + i\epsilon, \hat{X}) = \frac{2i\epsilon}{(\nu - \hat{X})^2 + \epsilon^2}
$$

**3) 디랙 델타 함수의 유도**

차분 결과에 $\frac{1}{2\pi i}$ 를 곱한다. 계수 $\frac{2i\epsilon}{2\pi i}$ 에서 $i$ 가 약분되어 $\frac{\epsilon}{\pi}$ 가 된다.

$$
\lim_{\epsilon \to 0^+} \frac{1}{2\pi i} \left[ \frac{2i\epsilon}{(\nu - \hat{X})^2 + \epsilon^2} \right] d\nu = \lim_{\epsilon \to 0^+} \frac{1}{\pi} \frac{\epsilon}{(\nu - \hat{X})^2 + \epsilon^2} d\nu
$$

위치 연산자는 실수 고윳값을 가지므로, 관측점 $\nu$ 가 고윳값 $x$ 와 같아지는 지점에서 분모가 $\epsilon^2$ 으로 0에 수렴하고, 4절의 1차원 소호츠키-플레멜 전개에 따라 우변은 디랙 델타 함수 $\delta(\nu - \hat{X})$ 로 수렴한다.

$$
d\hat{P}(\nu) = \delta(\nu - \hat{X}) d\nu
$$

**4) 분해 항등식 교차 검증**

유도된 사영 밀도로 대상 연산자를 전체 스펙트럼 구간 $\Omega$ 에 대하여 적분한다.

$$
\int_{-\infty}^{\infty} \nu \, d\hat{P}(\nu) = \int_{-\infty}^{\infty} \nu \, \delta(\nu - \hat{X}) d\nu
$$

델타 함수의 적분 필터링(Sifting) 성질에서, 적분 변수 $\nu$ 가 연산자 $\hat{X}$ 로 치환되어 식이 항등원으로 환원된다.

$$
= \hat{X}
$$

#### 7-2. 복소 고윳값 대각행렬: 고립점과 닫힌 경로 적분

연속 스펙트럼이 아니라 고립된 복소 점에 스펙트럼이 있는 경우, 2절의 곡선 도약이 아니라 그 점을 감싸는 닫힌 경로 적분으로 돌아가야 함을 보인다.

$$
\hat{A} = \begin{pmatrix} 2+i & 0 \\ 0 & 2-i \end{pmatrix}
$$

고윳값은 $\lambda_1 = 2+i$, $\lambda_2 = 2-i$ 이다. 이 행렬은 대각이므로 $\hat{A}^\dagger$ 역시 대각이고 둘이 교환하여 정규 연산자($[\hat{A}, \hat{A}^\dagger] = 0$)이지만, $\hat{A} \neq \hat{A}^\dagger$ 이므로 에르미트는 아니다. 레졸번트는 대각 성분의 역수로 구성된다.

$$
R(z, \hat{A}) = (z\hat{I} - \hat{A})^{-1} = \begin{pmatrix} \dfrac{1}{z - (2+i)} & 0 \\ 0 & \dfrac{1}{z - (2-i)} \end{pmatrix}
$$

**1) 실수축 도약이 0이 됨 (스톤 공식의 무력화)**

먼저 4절의 실수축 도약을 시도하면 0이 됨을 확인한다. $(1,1)$ 성분에 대해 실수축 $\nu$ 를 따라 통분한다.

$$
\frac{1}{\nu - i\epsilon - \lambda_1} - \frac{1}{\nu + i\epsilon - \lambda_1} = \frac{2i\epsilon}{(\nu - \lambda_1)^2 + \epsilon^2}
$$

$\lambda_1 = 2+i$ 는 허수부 $+1$ 이고 $\nu$ 는 실수이므로, $\nu - \lambda_1 = (\nu - 2) - i$ 의 허수부 $-1$ 이 사라지지 않아 $\nu = \lambda_1$ 이 불가능하다. 따라서 분모의 극한값 $(\nu - \lambda_1)^2$ 은 0이 아닌 유한한 복소수에 머문다.

$$
\lim_{\epsilon \to 0^+} \frac{2i\epsilon}{(\nu - \lambda_1)^2 + \epsilon^2} = \frac{0}{(\nu - \lambda_1)^2} = 0
$$

극점의 실수부와 같은 $\nu = 2$ 를 직접 대입하여 확인한다. $\nu - \lambda_1 = 2 - (2+i) = -i$ 이므로 다음과 같다.

$$
(\nu - \lambda_1)^2 + \epsilon^2 = (-i)^2 + \epsilon^2 = -1 + \epsilon^2, \qquad \lim_{\epsilon \to 0^+} \frac{2i\epsilon}{-1 + \epsilon^2} = \frac{0}{-1} = 0
$$

실수축 도약은 복소 고윳값에 대해 어떤 사영 밀도도 산출하지 못한다. 고윳값이 실수축에서 떨어져 있어 상·하단 경로를 밀착시켜도 극점에 닿지 못하기 때문이다.

**2) 닫힌 경로 적분에 의한 사영 연산자의 산출**

이산 챕터의 정의 $\hat{P}_1 = \dfrac{1}{2\pi i}\oint_{\Gamma_1} R(z)\,dz$ 를 적용한다. 경로 $\Gamma_1$ 은 복소 극점 $\lambda_1 = 2+i$ 를 감싸는 작은 원으로 잡되, 다른 극점 $\lambda_2 = 2-i$ 를 포함하지 않도록 반지름을 정한다. 두 극점 사이 거리는 다음과 같다.

$$
|\lambda_1 - \lambda_2| = |(2+i) - (2-i)| = |2i| = 2
$$

반지름 $r < 2$ 이면 $\Gamma_1$ 내부에는 $\lambda_1$ 만 존재한다. 성분별로 적분한다. $(1,1)$ 성분에 대하여 코시 적분 공식 $\dfrac{1}{2\pi i}\oint_{\Gamma}\dfrac{f(z)}{z-z_0}dz = f(z_0)$ 에서 $f(z) = 1$, $z_0 = \lambda_1 = 2+i$ 를 대입한다.

$$
\frac{1}{2\pi i}\oint_{\Gamma_1} \frac{dz}{z - (2+i)} = 1
$$

$(2,2)$ 성분에 대하여, 극점 $\lambda_2 = 2-i$ 는 $\Gamma_1$ 외부에 있다. 닫힌 경로 내부에 특이점이 없으면 적분이 0이라는 코시 적분 정리에서, 경로 안에 극점이 없으므로 다음이 성립한다.

$$
\frac{1}{2\pi i}\oint_{\Gamma_1} \frac{dz}{z - (2-i)} = 0
$$

비대각 성분 $(1,2), (2,1)$ 은 레졸번트가 대각이므로 0이다. 네 성분을 결합한다.

$$
\hat{P}_1 = \begin{pmatrix} 1 & 0 \\ 0 & 0 \end{pmatrix}
$$

분해 항등식 $\hat{A}\hat{P}_m = \lambda_m \hat{P}_m + \hat{N}_m$ 으로 검증한다. 좌변을 계산한다.

$$
\hat{A}\hat{P}_1 = \begin{pmatrix} 2+i & 0 \\ 0 & 2-i \end{pmatrix}\begin{pmatrix} 1 & 0 \\ 0 & 0 \end{pmatrix} = \begin{pmatrix} 2+i & 0 \\ 0 & 0 \end{pmatrix}
$$

우변에서 $\lambda_1\hat{P}_1$ 을 계산한다.

$$
\lambda_1 \hat{P}_1 = (2+i)\begin{pmatrix} 1 & 0 \\ 0 & 0 \end{pmatrix} = \begin{pmatrix} 2+i & 0 \\ 0 & 0 \end{pmatrix}
$$

좌우가 일치하므로 멱영 성분은 $\hat{N}_1 = \hat{0}$(대각행렬이라 결함 없음)이며, $\hat{A}\hat{P}_1 = \lambda_1\hat{P}_1$ 이 성립한다. 실수축 도약은 0을 주었으나 닫힌 경로 적분은 사영 연산자를 오차 없이 산출한다.

#### 7-3. 복소 고윳값 조르당 블록: 고립점과 멱영 밀도

고립된 복소 점에 멱영부까지 살아 있어, 사영 밀도(1차극)와 멱영 밀도(2차극)를 모두 산출해야 하는 경우이다. 3절의 가중 도약 논리가 닫힌 경로 형태로 어떻게 작동하는지 검증한다.

$$
\hat{A} = \begin{pmatrix} 2+i & 1 \\ 0 & 2+i \end{pmatrix}
$$

고윳값은 $\det(z\hat{I} - \hat{A}) = (z - (2+i))^2 = 0$ 에서 $\lambda = 2+i$ 의 중복근이다. 레졸번트를 구성한다. $z\hat{I} - \hat{A} = \begin{pmatrix} z-(2+i) & -1 \\ 0 & z-(2+i) \end{pmatrix}$ 의 역행렬은 다음과 같다.

$$
R(z, \hat{A}) = \frac{1}{(z-(2+i))^2}\begin{pmatrix} z-(2+i) & 1 \\ 0 & z-(2+i) \end{pmatrix} = \begin{pmatrix} \dfrac{1}{z-\lambda} & \dfrac{1}{(z-\lambda)^2} \\ 0 & \dfrac{1}{z-\lambda} \end{pmatrix}
$$

비대각 성분 $(1,2)$ 에 2차극 $\dfrac{1}{(z-\lambda)^2}$ 이 존재하며, 이것이 멱영부의 표식이다.

**1) 사영 밀도(1차극)의 산출**

$\hat{P} = \dfrac{1}{2\pi i}\oint_{\Gamma} R(z)\,dz$ 를 성분별로 계산한다. $(1,1)$ 과 $(2,2)$ 성분은 1차극이므로 잔여 1을 준다.

$$
\frac{1}{2\pi i}\oint_{\Gamma} \frac{dz}{z - \lambda} = 1
$$

$(1,2)$ 성분은 2차극이며, 2차극의 잔여는 0이다.

$$
\frac{1}{2\pi i}\oint_{\Gamma} \frac{dz}{(z - \lambda)^2} = 0
$$

따라서 1차극 적분이 산출하는 것은 사영 연산자뿐이다.

$$
\hat{P} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}
$$

**2) 멱영 밀도(2차극)의 산출**

멱영 성분은 3절의 가중 도약에 대응하는 이산 정의 $\hat{N} = \dfrac{1}{2\pi i}\oint_{\Gamma}(z-\lambda)R(z)\,dz$ 로 잡힌다. 가중 항 $(z-\lambda)R(z)$ 를 계산한다.

$$
(z-\lambda)R(z) = (z-\lambda)\begin{pmatrix} \dfrac{1}{z-\lambda} & \dfrac{1}{(z-\lambda)^2} \\ 0 & \dfrac{1}{z-\lambda} \end{pmatrix} = \begin{pmatrix} 1 & \dfrac{1}{z-\lambda} \\ 0 & 1 \end{pmatrix}
$$

성분별로 적분한다. 대각 성분 $(1,1), (2,2)$ 는 상수 1이므로 닫힌 경로 적분이 0이다.

$$
\frac{1}{2\pi i}\oint_{\Gamma} 1 \, dz = 0
$$

비대각 성분 $(1,2)$ 는 1차극이 되어 잔여 1을 준다.

$$
\frac{1}{2\pi i}\oint_{\Gamma} \frac{dz}{z - \lambda} = 1
$$

따라서 멱영 연산자가 산출된다.

$$
\hat{N} = \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}
$$

**3) 분해 항등식 교차 검증**

분해 항등식 $\hat{A}\hat{P} = \lambda\hat{P} + \hat{N}$ 으로 검증한다. 좌변은 $\hat{P} = \hat{I}$ 이므로 다음과 같다.

$$
\hat{A}\hat{P} = \hat{A} = \begin{pmatrix} 2+i & 1 \\ 0 & 2+i \end{pmatrix}
$$

우변을 계산한다.

$$
\lambda\hat{P} + \hat{N} = (2+i)\begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} + \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix} = \begin{pmatrix} 2+i & 1 \\ 0 & 2+i \end{pmatrix}
$$

좌우가 일치하여 $\hat{A}\hat{P} = \lambda\hat{P} + \hat{N}$ 이 성립한다. 1차극 도약(사영 밀도)만으로는 $\hat{P} = \hat{I}$ 밖에 얻지 못하고 비대각 결함 $\hat{N} = \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}$ 을 놓치므로, 2차극을 잡는 $(z-\lambda)R$ 가중 도약이 반드시 함께 필요함이 확인된다. 이것이 3절에서 사영 밀도와 멱영 밀도를 모두 갖추어야 한다고 강조한 이유이다.

---