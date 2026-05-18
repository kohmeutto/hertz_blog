+++
title = "(b) Existence and properties"
weight = 4
+++

---

### 1. 그린함수의 존재 조건

그린함수 $G(u,u') = \langle u^d|\hat{A}^{-1}|u'\rangle$ 가 존재하려면, 무엇보다 **$\hat{A}^{-1}$ 자체가 존재해야 한다**. 이 조건은 스펙트럼으로 명확히 표현된다.

**1) 이산 스펙트럼**

b_eigenvalue.md §5에서 정립한 대로, 유한 차원에서 $\hat{A}$ 의 역행렬은

$$
\hat{A}^{-1} \text{ 존재} \iff \det(\hat{A}) \neq 0 \iff \forall i,\ \lambda_i \neq 0
$$

이다. 이산 스펙트럼이면 모든 고유값이 0이 아니어야 그린함수가 존재한다.

**2) 연속 스펙트럼**

연속 스펙트럼의 경우 문서 2 §3에서 본 적분

$$
G(u,u') = \int d\lambda\,\frac{\psi_\lambda(u)\,\psi^\lambda(u')}{\lambda}
$$

가 수렴해야 한다. **$0$ 이 $\hat{A}$ 의 연속 스펙트럼에 포함되지 않을 때** ($0 \notin \sigma_c(\hat{A})$) 적분이 정규(regular) 의미로 수렴한다.

**3) 통합 조건**

이산과 연속을 통합하면

$$
G \text{ 존재} \iff 0 \notin \sigma(\hat{A})
$$

즉, **0이 $\hat{A}$ 의 전체 스펙트럼에 포함되지 않아야 한다**. 영공간 관점에서는 $\ker \hat{A} = \{0\}$ 이다 (b_eigenvalue.md §5).

---

### 2. 존재가 실패할 때

$0 \in \sigma(\hat{A})$ 이면 $\hat{A}^{-1}$ 이 존재하지 않으므로, 그린함수 역시 정규 의미로는 존재하지 않는다. 두 가지 대안적 접근이 있다.

**1) 일반화된 그린함수 (영공간 사영 제거)**

$\hat{A}|v\rangle = |f\rangle$ 의 해가 존재하려면 (Fredholm 대안):

$$
|f\rangle \perp \ker(\hat{A}^\dagger)
$$

이어야 한다. 이 조건이 만족될 때, 영공간을 제외한 직교 보충 공간 위에서 $\hat{A}$ 를 역으로 돌려 **일반화된 그린함수** 를 정의할 수 있다. 이산 차원에서의 Moore-Penrose 유사역행렬에 해당한다.

**2) Resolvent 접근**

더 체계적 접근은 매개변수 $z$ 를 도입하여 $\hat{A}$ 를 $\hat{A} - z\hat{I}$ 로 살짝 옮기는 것이다. $z$ 가 스펙트럼을 피하면 역연산자가 항상 존재한다.

$$
\hat{R}(z) = (\hat{A} - z\hat{I})^{-1}, \quad z \notin \sigma(\hat{A})
$$

Resolvent는 본질적으로 시간 영역 인과율 ($z = E \pm i\eta$ 의 retarded/advanced 분기) 과 결합된 객체이므로, **다음 챕터인 NEGF 에서 본격적으로 다룬다**. 평형 그린함수의 관점에서는 "스펙트럼을 매개변수 $z$ 로 피한다" 라는 아이디어 정도로 충분하다.

---

### 3. 자기수반 연산자에서의 대칭성

$\hat{A}$ 가 자기수반(self-adjoint, $\hat{A} = \hat{A}^\dagger$) 이면, 그린함수는 다음의 대칭성을 가진다.

**1) 일반 형태**

$$
G(u,u') = G^*(u',u) \quad (\text{허미션 대칭, 위치 기저})
$$

proof)

자기수반성 $\hat{A} = \hat{A}^\dagger$ 으로부터 $\hat{A}^{-1}$ 도 자기수반이다.

$$
(\hat{A}^{-1})^\dagger = (\hat{A}^\dagger)^{-1} = \hat{A}^{-1}
$$

b_adjoint.md §2 의 수반 관계 $\langle v|\hat{A}w\rangle = \langle \hat{A}^\dagger v|w\rangle$ 와 내적의 sesquilinear성 $\overline{\langle a|b\rangle} = \langle b|a\rangle$ 을 결합하면 다음 항등식이 성립한다.

$$
\langle v|\hat{B}|w\rangle = \langle w|\hat{B}^\dagger|v\rangle^*
$$

이를 위치 기저에서 $\hat{B} = \hat{A}^{-1}$ (허미션) 에 적용:

$$
G(x,x') = \langle x|\hat{A}^{-1}|x'\rangle = \langle x'|(\hat{A}^{-1})^\dagger|x\rangle^* = \langle x'|\hat{A}^{-1}|x\rangle^* = G^*(x',x)
$$

**주의**: 무한 차원에서 이 결과는 b_adjoint.md §3 의 의미에서 경계항 $\mathcal{R}_{\hat{A}}[\phi,\psi]$ 가 사라질 때 (즉, **연산자가 실제로 자기수반일 때**, 경계 조건 포함) 성립한다. 형식적 자기수반 ($\hat{A}$ 의 미분식이 대칭) 만으로는 충분하지 않다. **자기수반성을 보장하는 경계 조건의 분류는 §4 와 doc 5 에서 다룬다.**

**2) 실수 자기수반 연산자**

$\hat{A}$ 가 실수 자기수반 ($\hat{A}$ 가 실수 표현을 가짐, 예: $-d^2/dx^2 + V(x)$ with real $V$) 이면, $G$ 도 실수가 되어

$$
G(x,x') = G(x',x) \quad (\text{완전 대칭})
$$

이는 **상호성 정리(reciprocity)**: $x'$ 자리의 점원이 $x$ 자리에 만드는 응답은, $x$ 자리의 점원이 $x'$ 자리에 만드는 응답과 같다.

---

### 4. 경계 조건의 역할

지금까지의 논의는 추상 연산자 $\hat{A}$ 에 대한 것이었다. 그러나 **미분 연산자의 경우, 경계 조건이 본질적이다**.

**1) 같은 미분식, 다른 연산자**

$\hat{A} = -d^2/dx^2$ on $[0,L]$ 이라는 미분 식만으로는 연산자가 완전히 결정되지 않는다. 경계 조건에 따라 다른 연산자가 된다.

| 경계 조건 | 고유값 | 고유함수 | 그린함수 |
|---|---|---|---|
| Dirichlet ($\psi(0)=\psi(L)=0$) | $(n\pi/L)^2$, $n=1,2,\ldots$ | $\sin(n\pi x/L)$ | $x_<(L-x_>)/L$ |
| Neumann ($\psi'(0)=\psi'(L)=0$) | $(n\pi/L)^2$, $n=0,1,\ldots$ | $\cos(n\pi x/L)$ | **존재하지 않음** ($\lambda_0=0$) |
| Periodic ($\psi(0)=\psi(L)$, $\psi'(0)=\psi'(L)$) | $(2n\pi/L)^2$, $n=0,1,\ldots$ | $e^{i2n\pi x/L}$ | **존재하지 않음** ($\lambda_0=0$) |
| Robin (혼합) | 일반적으로 다름 | 다름 | 다름 |

**같은 미분식이지만, 경계 조건이 다르면 완전히 다른 연산자**이다.

**2) 영공간과 경계 조건**

Neumann과 Periodic 경계에서 $\lambda_0 = 0$ 이 스펙트럼에 포함되는 이유는 명확하다: **상수 함수 $\psi_0 = $ const 가 미분 방정식 $-\psi_0''=0$ 과 경계 조건을 동시에 만족하기 때문이다**. 따라서 $\hat{A}\psi_0 = 0$, 즉 $\psi_0 \in \ker \hat{A}$ 이며, §1의 존재 조건이 깨진다.

물리적 직관: Neumann (양 끝 자유) 경계에서는 시스템에 단위 힘을 가해도 전체 구조가 그저 떠다닐 수 있어 정상상태 응답이 존재하지 않는다. 반면 Dirichlet (양 끝 고정) 에서는 끝점이 고정되어 정상상태가 자연스럽게 정의된다.

이때는 §2의 일반화된 그린함수가 필요하며, 상수 영공간 사영을 제거한 후 역연산자를 구성한다.

**3) 체계적 처리: Sturm-Liouville**

자기수반 1차원 미분 연산자의 일반적 구조와 자기수반을 보장하는 경계 조건의 분류는 **Sturm-Liouville 이론** 에서 체계적으로 다룬다. 본 챕터의 다음 문서들에서 이를 본격적으로 다룬다.

- **doc 5 (SL form)**: 일반 2계 미분 연산자의 SL 표현, 자기수반 조건 (b_adjoint.md 의 경계항 프레임워크 적용)
- **doc 6 (SL Green's function)**: Wronskian 기반 G 의 일반 구성 공식
- **doc 7 (Singular SL)**: 표준 SL 조건이 깨지는 특수 사례 (Bessel, Legendre, Hermite 등)

§3 의 자기수반 대칭성도 결국 "어떤 경계 조건이 자기수반을 보장하는가" 에 의존하므로, doc 5 에서 그 답이 명확해진다.
