+++
title = "Outline"
weight = 1
+++

---

### [Derivation 1 적용] 다크 커런트 (Dark Current) 분석

(1) 측정 조건: 전자 빔 OFF (방사선 소스가 없는 상태에서 $V$만 스윕)

(2) 데이터 비교: 양성자 조사 전(Before) vs 후(After) 의 전류($J_{dark}$) 증가량

(3) 추출하는 물리량: 양자역학적 결함 포획률($\eta_0$) 및 SRH 재결합 수명($\tau_{SRH}$)

(4) 논문에서의 역할 (미시적 원인 규명)

- 양성자를 맞았더니 i-layer 내부에 결함(Vacancy)이 늘어났다.
- 계측된 다크 전류에 양자 포획 모델을 대입해 보니, 결함이 캐리어를 잡아먹는 덫의 성능($\eta_0$)이 급증했고, 그 결과 캐리어의 생존 수명($\tau_{SRH}$)이 줄어든다.

(5) 논문의 규명

"In addition, the voltage at which the current begins to increase sharply (turn-on voltage, $V_{on}$) tends to shift toward a lower value as the irradiation fluence increases."

턴온 전압($V_{on}$)이 낮아졌다는 것은, "동일한 순방향 전압을 인가했을 때, 양성자를 맞은 후의 전류가 맞기 전보다 더 많이 흐른다(증가한다)"는 뜻과 같다.

Derivation 1을 적용할 경우,

$$
J_{dark, fwd}(V) = \frac{q n_i W(V) \eta_0}{\hbar} \exp\left(\frac{qV}{2k_B T}\right)
$$

양성자를 맞으면 결함의 포획률($\eta_0$)이 늘어난다. 분자에 있는 $\eta_0$가 커지므로, 수식적으로 순방향 다크 전류($J_{dark, fwd}$)가 증가한다. 즉, 결함을 징검다리 삼아 넘어가는 재결합 전류가 늘어나기 때문에, 논문의 기술대로 "더 낮은 전압에서도 전류가 흐르기 시작하는(V_on 강하)" 현상이 수학적으로 증명된다.

---

### [Derivation 2 적용] EBIC / 빔 조사 전류 (Beam-on Current) 분석

(1) 측정 조건: 전자 빔 ON (전자 빔을 쏘면서 역방향 $V$ 스윕)

(2) 데이터 비교: 양성자 조사 전(Before) vs 후(After) 의 순수 광전류($I_{photo}$) 감소량

(3) 추출하는 물리량: 소수 캐리어 확산 길이($L_p$)

(4) 논문에서의 역할 (거시적 결과 증명)

빔을 맞아 생성된 소수 캐리어(정공)가 전극까지 살아서 걸어가는 거리($L_p$)가 선형 회귀 결과 이만큼 짧아졌다. 따라서 베타전지의 최종 출력($P_{max}$)이 떨어지는 것은 당연한 물리적 결과이다" 라는 현상적 결과를 증명