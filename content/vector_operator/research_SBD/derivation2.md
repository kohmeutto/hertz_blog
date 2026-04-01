+++
title = "Derivation2"
weight = 3
+++

---

## EBIC 기반 소수 캐리어 확산 길이 및 Life time 추출

작성자: 김기범, 윤영준 / 일자: 2026.03.26

---

### 1. 물리적 시스템의 정의 및 지배 방정식

본 모델은 n형 반도체 소자(예: n-type 4H-SiC 에피택셜 층)에 외부에서 전자 빔이 조사되어 전자-정공 쌍(EHP)이 연속적으로 생성되는 정상 상태(Steady-state)를 다룬다. 역방향 바이어스 $V$가 인가된 상태에서 계측되는 생성 전류 $I_{gen}(V)$를 통해 물질의 고유 물성치인 소수 캐리어(정공)의 확산 길이 $L_p$와 재결합 수명 $\tau_p$를 역산하는 것이 목적이다. 소자 내부는 인가 전압 $V$에 의해 두께가 변조되는 공핍층(Depletion Region, $0 \le x \le W(V)$)과, 전기장이 없는 중성 영역(Neutral Region, $W(V) < x \le d_{eff}$)으로 분리된다.

**1) 캐리어 연속 방정식 (Continuity Equation)의 도출**

1차원 공간 내 임의의 미소 체적(단면적 $A$, 두께 $\Delta x$)에서 소수 캐리어(정공 기준)의 질량 보존 법칙은 다음과 같이 기술된다. 단위 시간당 정공 농도 $p$의 변화율은 정공 플럭스(Flux)의 발산, 체적 내 생성률 $G(x)$, 재결합률 $R$의 합으로 정의된다. 정공의 전류 밀도는 $J_p$이다.

$$
\frac{\partial p}{\partial t} = -\frac{1}{q} \frac{\partial J_p}{\partial x} + G(x) - R
$$

정상 상태($\partial p / \partial t = 0$)를 가정하고, 중성 영역 내에서는 전기장 $\mathcal{E} \approx 0$이므로 드리프트 성분이 소거된다. 정공의 순수 확산 전류 밀도는 Fick의 제1법칙에 따라 $J_p = -q D_p \frac{d(\Delta p)}{dx}$ 로 정의된다. 이를 연속 방정식에 대입한다.

$$
0 = -\frac{1}{q} \frac{d}{dx} \left( -q D_p \frac{d\Delta p}{dx} \right) + G_0 - \frac{\Delta p}{\tau_p}
$$

$$
0 = D_p \frac{d^2 \Delta p}{dx^2} + G_0 - \frac{\Delta p}{\tau_p}
$$

양변을 정공 확산 계수 $D_p$로 나누고, $L_p^2 = D_p \tau_p$ 관계를 적용하면, 풀어야 할 2계 선형 비동차 상미분 방정식이 도출된다.

$$
\frac{d^2 \Delta p(x)}{dx^2} - \frac{\Delta p(x)}{L_p^2} = -\frac{G_0}{D_p}
$$

여기서 빔에 의한 생성 함수 $G(x)$는 빔 침투 깊이 내에서 상수 $G_0$로 균일하다고 가정한다.

---

### 2. 중성 영역 확산 방정식의 일반해 유도

미분 방정식의 일반해 $\Delta p(x)$는 우변이 0인 동차해 $\Delta p_h(x)$와, 상수항에 대한 특수해 $\Delta p_p(x)$의 합으로 구성된다.

**1) 특수해 (Particular Solution) 도출**

우변의 항 $-\frac{G_0}{D_p}$가 위치 $x$에 무관한 상수이므로, 미정계수법에 의해 특수해 $\Delta p_p(x) = K$ (상수)로 둔다.

$$
\frac{d^2 (K)}{dx^2} - \frac{K}{L_p^2} = -\frac{G_0}{D_p} \implies -\frac{K}{L_p^2} = -\frac{G_0}{D_p}
$$

$$
K = \frac{G_0 L_p^2}{D_p} = \frac{G_0 (D_p \tau_p)}{D_p} = G_0 \tau_p
$$

$$
\Delta p_p(x) = G_0 \tau_p
$$

**2) 동차해 (Homogeneous Solution) 도출**

동차 방정식 $d^2 \Delta p_h/dx^2 - \Delta p_h/L_p^2 = 0$ 의 특성 방정식은 $r^2 - 1/L_p^2 = 0$ 이며, 근은 $r = \pm 1/L_p$ 이다. 공핍층 경계 $x=W$를 기점으로 쌍곡선 함수의 선형 결합으로 표현한다.

$$
\Delta p_h(x) = C_1 \cosh\left(\frac{x-W}{L_p}\right) + C_2 \sinh\left(\frac{x-W}{L_p}\right)
$$

**3) 일반해 (General Solution) 및 경계 조건 적용**

특수해와 동차해를 합산한 일반해는 다음과 같다.

$$
\Delta p(x) = C_1 \cosh\left(\frac{x-W}{L_p}\right) + C_2 \sinh\left(\frac{x-W}{L_p}\right) + G_0 \tau_p
$$

경계조건1-공핍층 경계 ($x = W$): 내부의 강한 전기장에 의해 경계면에 도달한 정공은 즉시 휩쓸려가므로, 이 지점은 완전 흡수체(Perfect Sink)로 작용한다. $\Delta p(W) = 0$ 을 대입하면 $\cosh(0)=1, \sinh(0)=0$ 이므로 다음과 같이 $C_1$이 확정된다.

$$
C_1 (1) + 0 + G_0 \tau_p = 0 \implies C_1 = -G_0 \tau_p
$$

경계조건2-유효 후면 경계 ($x = d_{eff}$): 빔이 멈추는 물리적 침투 한계점에서는 캐리어가 재결합하여 소멸한다고 가정한다 ($\Delta p(d_{eff}) = 0$). 중성 영역의 길이를 $H = d_{eff} - W$ 로 치환하고 대입한다.

$$
-G_0 \tau_p \cosh\left(\frac{H}{L_p}\right) + C_2 \sinh\left(\frac{H}{L_p}\right) + G_0 \tau_p = 0
$$

쌍곡선 함수의 반각 공식($\cosh(2\theta) - 1 = 2\sinh^2(\theta)$ 및 $\sinh(2\theta) = 2\sinh(\theta)\cosh(\theta)$)을 적용하여 $C_2$에 대해 정리한다.

$$
C_2 \sinh\left(\frac{H}{L_p}\right) = G_0 \tau_p \left[ \cosh\left(\frac{H}{L_p}\right) - 1 \right]
$$

$$
C_2 = G_0 \tau_p \frac{2\sinh^2\left(\frac{H}{2L_p}\right)}{2\sinh\left(\frac{H}{2L_p}\right)\cosh\left(\frac{H}{2L_p}\right)} = G_0 \tau_p \tanh\left(\frac{H}{2L_p}\right)
$$

---

### 3. 생성 전류 $I_{gen}(V)$

총 생성 전류는 공핍층 내부의 드리프트 전류($I_{drift}$)와 중성 영역에서 확산해 넘어온 확산 전류($I_{diff}$)의 합이다.

$$
I_{gen}(V) = I_{drift}(V) + I_{diff}(V)
$$

**1) 드리프트 전류 ($I_{drift}$)**

전기장 내($0 \le x \le W$)에서 생성된 정공은 100% 수집되므로, 체적 내 총 생성률을 합산한다. ($A$는 소자의 단면적)

$$
I_{drift}(V) = q A \int_{0}^{W(V)} G_0 dx = q A G_0 W(V)
$$

**2) 확산 전류 ($I_{diff}$)**

$x=W$ 경계면으로 확산되어 들어오는 전류의 크기를 구한다. $I_{diff} = q A D_p \left| d\Delta p/dx \right|_{x=W}$ 이다. 일반해를 미분하여 $x=W$를 대입한다.

$$
\left. \frac{d\Delta p}{dx} \right|_{x=W} = \frac{C_2}{L_p} = \frac{G_0 \tau_p}{L_p} \tanh\left(\frac{d_{eff}-W}{2L_p}\right)
$$

$D_p \tau_p = L_p^2$ 이므로 확산 전류는 다음과 같이 정리된다.

$$
I_{diff}(V) = q A D_p \frac{G_0 \tau_p}{L_p} \tanh\left(\frac{d_{eff}-W}{2L_p}\right) = q A G_0 L_p \tanh\left(\frac{d_{eff}-W}{2L_p}\right)
$$

**3) 총 생성 전류 초월 방정식 결합**

합산하여 초기 모델을 완성한다.

$$
I_{gen}(V) = q A G_0 \left[ W(V) + L_p \tanh\left(\frac{d_{eff}-W(V)}{2L_p}\right) \right]
$$

---

### 4. 물리적 파라미터 캘리브레이션 및 수식 적용

빔의 물리량($25 \text{ keV}, 9.2 \text{ nA}$)과 타겟 물질(4H-SiC)의 물성을 통해 선행 계수 $q A G_0$를 확정한다.

**1) 빔 침투 깊이 ($R_e$) 도출 (ref: 10.1088/0022-3727/5/1/308)**

$$
R_e = \frac{0.0276 \cdot A_{eff} \cdot E_b^{1.67}}{\rho \cdot Z_{eff}^{0.89}}
$$

- $E_b = 25 \text{ keV}$
- 4H-SiC 유효 원자량 $A_{eff} = 20.05 \text{ g/mol}$ (Si-28.085, C-12.011)
- 4H-SiC 유효 원자 번호 $Z_{eff} = 10$ (Si-14, C-6)
- 4H-SiC 밀도 $\rho = 3.21 \text{ g/cm}^3$ (ref: http://www.yeeyoung.co.kr/spec/SiC_Ceramic.htm)

$$
R_e = \frac{0.0276 \cdot 20.05 \cdot (25)^{1.67}}{3.21 \cdot (10)^{0.89}} \approx 4.8 \text{ }\mu\text{m}
$$

**2) 단위 길이당 최대 생성 전류 상수 계산**

4H-SiC의 전자-정공 쌍 생성 에너지 $E_{ehp} \approx 7.8 \text{ eV}$ (ref: 10.1109/TNS.2003.807855) 를 적용하여 입사 전자 1개당 생성되는 증폭 계수 $M$을 구한다.

$$
M = \frac{25,000 \text{ eV}}{7.8 \text{ eV}} \approx 3205.13
$$

최대 생성 총 전류 $I_{max}$는 다음과 같다.

$$
I_{max} = 9.2 \text{ nA} \times 3205.13 = 29.487 \text{ }\mu\text{A}
$$

총 전류가 빔 침투 깊이 내에서 균일하게 생성될 때, 1차원 선행 계수($\mu\text{A}/\mu\text{m}$)는 대수적으로 상수화된다.

$$
q A G_0 = \frac{I_{max}}{d_{eff}} = \frac{29.487 \text{ }\mu\text{A}}{4.8 \text{ }\mu\text{m}} = 6.143 \text{ }\mu\text{A}/\mu\text{m}
$$

파라미터가 확정된 최종 모델 방정식은 아래와 같다.

$$
I_{gen}(V) = 6.143 \left[ W(V) + L_p \tanh\left( \frac{4.8 - W(V)}{2L_p} \right) \right], \quad W(V) = \sqrt{\frac{2\varepsilon_s}{q N_D}(V_{bi} - V)}
$$

---

### 5. $L_p$ 추출을 위한 점근적 극한 처리 및 닫힌 형태 도출

위 방정식은 $\tanh$ 인자 내부에 소수 캐리어 확산 길이 $L_p$가 분모로 포함되어 있어 완전한 해석적 역함수가 존재하지 않는다. 명시적 추출을 위해 물리적 기하 극한 조건을 적용한다. 공핍층 두께 $W(V)$를 제어하여 중성 영역의 길이 $H = 4.8 - W(V)$ 가 확산 거리 $L_p$에 비해 충분히 길게 확보된다면($H \ge 5L_p$), 수학적으로 다음의 점근적 극한이 성립한다.

$$
\lim_{x \to \infty} \tanh(x) = 1 \implies \tanh\left( \frac{4.8 - W(V)}{2L_p} \right) \approx 1
$$

위 극한 조건을 만족하는 특정 데이터 포인트 $\left(V, I_{gen}\right)$에 대하여, 초월 항이 상수 $1$로 붕괴하며 수식은 $L_p$를 완벽하게 독립시킬 수 있는 1차 선형 방정식으로 표현된다.

$$
I_{gen}(V) = 6.143 \left[ W(V) + L_p \cdot 1 \right]
$$

이를 $L_p$에 대해 이항하여 정리하면, 계측된 데이터로부터 즉각적으로 물성을 분리해 낼 수 있는 대수적 컴팩트 식(Compact formula)이 도출된다.

$$
L_p = \frac{I_{gen}(V)}{6.143} - W(V) \quad (\text{단위: }\mu\text{m})
$$

---

### 6. 대수적 한계 극복 및 실효 물성 추출

앞선 5절에서 유도된 닫힌 형태의 수식 $L_p = I_{gen}/G_{ideal} - W(V)$는 소자 내부의 생성 캐리어가 100% 수집된다는 이상적 가정을 전제로 한다. 그러나 실제 4H-SiC 시료의 측정 데이터를 이 모델에 포인트별로 직접 대입할 경우, 확산 길이 $L_p$가 물리적으로 불가능한 음수($< 0$)로 발산하는 모순이 관측된다. 본 절에서는 이러한 대수적 발산의 물리적 원인을 규명하고, 고정된 이론적 상수($G_{ideal}$)의 맹점을 해결하기 위해 자유 변수 선형 회귀(Free-parameter Linear Regression) 모델과 신호 복원(Robust Signal Restoration) 알고리즘을 도입한다.

**1) 실효 생성율($G_{eff}$)의 도입**

$L_p$가 음수로 산출되는 근본적인 원인은, 계측된 순수 광전류($I_{photo}$)가 이론적으로 공핍층 내부에서만 생성되어야 할 최소 기대 전류($G_{ideal} \times W$)에도 미치지 못하기 때문이다. 이는 시료 표면의 데드 레이어(Dead Layer) 및 공핍층 내부의 극심한 재결합 센터(Recombination Centers)로 인해 실제 캐리어 수집 효율($\eta$)이 이론치 대비 현저히 낮음을 의미한다. 따라서 이론적 최대 생성 상수 $G_{ideal} = 6.143 \text{ }\mu\text{A}/\mu\text{m}$를 사용하는 로직을 개선해야 한다. 대신, 실제 수집 기울기인 유효 생성율($G_{eff}$) 을 도입하여 지배 방정식을 다음과 같은 1차 선형 방정식으로 재구성한다.

$$
I_{photo}(W) = G_{eff} \cdot W(V) + G_{eff} \cdot L_p
$$

이 수식에서 측정된 데이터 집합에 대한 선형 회귀(Least Squares Fit, $y = mx + c$)를 수행하면, 두 가지의 미지수를 동시에 독립시킬 수 있다.

- 기울기($m$): 시료의 실제 유효 생성율 $G_{eff}$
- x-절편($-c/m$): 물리적으로 타당한 양수(+)의 소수 캐리어 확산 길이 $L_p$

**2) 암전류 대수적 소거 및 신호 복원**

미소 전압 변조 구간($-1.0\text{V} \sim 0\text{V}$)에서 공핍층 두께 $W$의 변화량은 극히 미미하다. 이 좁은 스케일에서 $\text{pA}$ 단위의 계측기 스파이크 노이즈는 회귀 분석의 기울기($G_{eff}$)를 물리적 궤도에서 이탈시키는 원인이 된다. 순수 물리적 DC 트렌드만을 추출하기 위해 다음의 3단계 신호 처리를 수행한다.

- 암전류 소거 (Dark Subtraction): 동일 전압에서 계측된 암전류(OFF)를 선형 보간(Linear Interpolation)하여 총 전류에서 소거함으로써, 다이오드 누설 성분을 배제한 순수 $I_{photo}$를 산출한다.
- 이동 중앙값 필터 (movmedian): 절댓값을 취하기 전의 부호가 있는 원시 전류 도메인에서 스파이크 노이즈를 1차적으로 제거한다. 평균이 아닌 중앙값을 사용하여 원본 신호의 스케일 훼손을 막는다.
- 국소 회귀 (rlowess): 스파이크가 제거된 데이터에 LOWESS 평활화를 적용하여, 노이즈에 가려진 물리적 선형 기울기만을 부드럽게 복원한다. 

---

### 6. 결과

| 측정 조건 (mm) | 유효 생성율 ($G_{eff}$) | 수집 효율 ($\eta$) (%) | 확산 거리 ($L_p$) ($\mu\text{m}$) | 정공 수명 ($\tau_{p0}$) (ns) |
| :---: | :---: | :---: | :---: | :---: |
| 1.900 | 0.2031 | 3.31 | 1.627 | 8.901 |
| 1.958 | 0.0704 | 1.15 | 5.986 | 120.507 |
| 2.021 | 0.1341 | 2.18 | 2.837 | 27.065 |
| 2.080 | 0.1913 | 3.11 | 1.820 | 11.141 |
| 2.139 | 0.5806 | 9.45 | 0.175 | 0.103 |
| 2.206 | 0.0513 | 0.84 | 8.318 | 232.704 |
| 2.264 | 0.1629 | 2.65 | 2.171 | 15.855 |
| 2.320 | 0.4743 | 7.72 | 0.353 | 0.418 |
| 2.382 | 0.0457 | 0.74 | 9.492 | 303.060 |
| 2.539 | 0.2406 | 3.92 | 1.296 | 5.653 |

---

### 7. MATLAB 전압별 계산 스크립트

```matlab
% =========================================================================
% [최종 완성형] 노이즈 필터링 기반 G_eff, L_p 동시 추출 및 Symlog 검증
% - Figure 1: W vs I_photo 선형 회귀 분석 (물성치 추출)
% - Figure 2: V vs I_photo (Raw vs Filtered) 대칭 로그 스케일 검증
% =========================================================================
clear; clc; close all;

%% 1. 절대 물리 상수 및 4H-SiC 표준 물성 세팅
q = 1.60217663e-19;
kB = 1.380649e-23;
T = 300;
eps_s = 9.7 * 8.85418781e-14; 
V_bi = 2.04; % Built-in Potential (4H-SiC)
N_D = 7.38e15; 
G_ideal = 6.143; % 이론적 최대 생성 상수 (uA/um)

% 정공 확산 계수 도출 (Einstein Relation)
mu_p = 115; 
D_p = (kB * T / q) * mu_p; 

%% 2. 데이터 로드 및 암전류(OFF) 전처리
try
    data = readmatrix('EBIC_IV.csv');
catch
    error('EBIC_IV.csv 파일을 찾을 수 없습니다.');
end

V_dark_raw = data(:, 1); I_dark_raw = data(:, 2);
valid_dark = ~isnan(V_dark_raw) & ~isnan(I_dark_raw);
[V_dark_uni, ~, idx_u] = unique(V_dark_raw(valid_dark));
I_dark_uni = accumarray(idx_u, I_dark_raw(valid_dark), [], @mean);

%% 3. 분석 구간 및 루프 변수 설정
V_start = -1.0; 
V_end = 0.0; 

widths_mm = [0, 1.900, 1.958, 2.021, 2.080, 2.139, 2.206, 2.264, 2.320, 2.382, 2.539];
num_conditions = length(widths_mm); 

% Symlog 변환 함수 적용: y = sign(x)*log10(1+|x|/I_th)
I_th = 1e-11; % Threshold Current (10 pA)
symlog_tf = @(x) sign(x) .* log10(1 + abs(x) / I_th);

% Symlog y축 눈금 세팅
ticks_A = [-1e-5, -1e-7, -1e-9, -1e-11, 0, 1e-11, 1e-9, 1e-7, 1e-5];
ticks_trans = symlog_tf(ticks_A);
tick_labels = {'-10^{-5}', '-10^{-7}', '-10^{-9}', '-10^{-11}', '0', '10^{-11}', '10^{-9}', '10^{-7}', '10^{-5}'};

%% 4. 메인 분석 루프 및 시각화 준비
fig1 = figure('Name', 'Regression: I_photo vs W', 'Color', 'w', 'Position', [50 50 1400 800]);
fig2 = figure('Name', 'Signal Restoration (Symlog)', 'Color', 'w', 'Position', [100 100 1400 800]);

fprintf('\n=========================================================================================\n');
fprintf(' [최종 보고서] 필터링 기반 선형 회귀 물성 추출 (Symlog 검증 포함)\n');
fprintf(' (해석 구간: %.2fV ~ %.2fV)\n', V_start, V_end);
fprintf('-----------------------------------------------------------------------------------------\n');
fprintf(' 측정 조건   | 유효 생성율(G_eff) | 수집 효율(eta) | 확산 거리(L_p) | 정공 수명(tau_p0) \n');
fprintf('-----------------------------------------------------------------------------------------\n');

for i = 2:num_conditions
    col_V = 2*i-1; col_I = 2*i;
    V_raw = data(:, col_V); I_raw = data(:, col_I);
    
    idx = (V_raw >= V_start) & (V_raw <= V_end) & ~isnan(V_raw) & ~isnan(I_raw);
    V_v = V_raw(idx); I_on = I_raw(idx);
    
    if length(V_v) < 5, continue; end
    
    % 1. 순수 광전류 산출 (암전류 선형 보간 및 소거, 부호 유지)
    I_dark_interp = interp1(V_dark_uni, I_dark_uni, V_v, 'linear', 'extrap');
    I_photo_raw_A = I_on - I_dark_interp; % 암페어(A) 단위의 부호 있는 원시 데이터
    
    % 2. 정확한 신호 복원 (Signal Restoration)
    % 노이즈에 의한 평균 왜곡을 막기 위해 '절댓값을 취하기 전' 원본 도메인에서 필터링 수행
    I_photo_med_A = smoothdata(I_photo_raw_A, 'movmedian', floor(length(I_photo_raw_A)*0.05));
    I_photo_clean_A = smoothdata(I_photo_med_A, 'rlowess', floor(length(I_photo_raw_A)*0.15));
    
    % 3. 물성 추출을 위한 단위 변환 (절댓값 및 uA 변환)
    I_photo_clean_uA = abs(I_photo_clean_A) * 1e6;
    W_um = sqrt((2 * eps_s / (q * N_D)) .* (V_bi - V_v)) * 1e4;
    
    % 4. 선형 회귀 (Least Squares Fit: y = mx + c)
    p = polyfit(W_um, I_photo_clean_uA, 1);
    G_eff = p(1);       
    Intercept = p(2);   
    
    % 5. 물성치 역산
    L_p = Intercept / G_eff;  
    eta = (G_eff / G_ideal) * 100;
    tau_p0_ns = sign(L_p) * (((L_p * 1e-4)^2) / D_p * 1e9); % 수학적 궤적 보존
    
    % 6. 결과 출력
    fprintf(' %8.3f mm | %14.4f     | %10.2f %%   | %10.3f um   | %10.3f ns \n', ...
            widths_mm(i), G_eff, eta, L_p, tau_p0_ns);
    
    % =========================================================================
    % [시각화 1] 물성 추출 선형 회귀 플롯 (W vs I_photo)
    % =========================================================================
    figure(fig1);
    subplot(3, 4, i);
    plot(W_um, I_photo_clean_uA, 'k.', 'MarkerSize', 8); hold on;
    W_fit = linspace(min(W_um), max(W_um), 100);
    plot(W_fit, polyval(p, W_fit), 'r-', 'LineWidth', 2);
    xlabel('Depletion Width W (\mum)'); ylabel('Filtered |I_{photo}| (\muA)');
    R_sq = corr(W_um, I_photo_clean_uA)^2;
    title(sprintf('%.3f mm (R^2=%.3f)\nL_p=%.2f um', widths_mm(i), R_sq, L_p), 'FontSize', 10);
    grid on;
    
    % =========================================================================
    % [시각화 2] Symlog 기반 신호 복원 검증 플롯 (V vs I_photo)
    % =========================================================================
    figure(fig2);
    subplot(3, 4, i);
    % 원시 데이터 (회색) vs 필터링 데이터 (빨간색)
    plot(V_v, symlog_tf(I_photo_raw_A), 'Color', [0.7 0.7 0.7], 'DisplayName', 'Raw'); hold on;
    plot(V_v, symlog_tf(I_photo_clean_A), 'r-', 'LineWidth', 2, 'DisplayName', 'Filtered');
    
    % Symlog 축 설정
    yticks(ticks_trans);
    yticklabels(tick_labels);
    yline(0, 'k--', 'HandleVisibility', 'off'); % 0 기준선
    
    xlabel('Voltage (V)'); ylabel('I_{photo} (A) [Symlog]');
    title(sprintf('%.3f mm', widths_mm(i)), 'FontSize', 10);
    grid on;
    if i == 2, legend('Location', 'best'); end
    ylim([min(ticks_trans), max(ticks_trans)]);
    xlim([V_start, V_end]);
end

fprintf('=========================================================================================\n');
figure(fig1); sgtitle('Linear Regression: G_{eff} and L_p Extraction', 'FontSize', 16, 'FontWeight', 'bold');
figure(fig2); sgtitle('Signal Restoration Verification (Symmetric Logarithmic Scale)', 'FontSize', 16, 'FontWeight', 'bold');
```
