+++
title = "(b) Riesz representation theorem"
weight = 5
+++

---

### 1. 리즈의 표현 정리, 디렉 표기법과의 연결 고리

- Bra의 작용: 쌍대공간 $V^\ast$의 원소 $\langle f|$ 가 원래 공간 V의 원소 $|v\rangle$ 에 작용하는 것, $\langle f|v\rangle$
- 내적: 원래 공간 V의 두 원소 $|f\rangle$와 $|v\rangle$ 사이의 기하학적 관계, $\langle f,v\rangle$.

두 표기법이 너무나 비슷하게 생겼다는 것은 우연이 아니다. 힐베르트 공간에서는 이 둘을 하나로 묶어주는 운명적인 연결고리가 있으며, 그 연결고리의 이름이 바로 **리즈 표현 정리(Riesz Representation Theorem)** 이다.

이 정리의 수학적 증명은 복잡하지만, 그 결론은 아주 명확하고 강력하다.

- 힐베르트 공간 $V$에서는, 어떤 (연속적인) 선형 범함수(Bra) $\langle f|$ 를 가져오더라도, 그 Bra에 유일하게 대응하는 단 하나의 파트너 Ket 벡터 $|f\rangle$가 $V$ 안에 반드시 존재한다.
- Bra $\langle f|$가 어떤 벡터 $|v\rangle$에 작용하여 얻는 결과값은, 파트너 Ket $|f\rangle$와 벡터 $|v\rangle$의 내적 결과값과 완벽하게 동일하다.

**이를 수식으로 표현하면 다음과 같다.**

$$
\langle f|v\rangle
=\langle f,v\rangle
$$

**(1) 왼쪽 항** : $\langle f|v\rangle$

- 선형 범함수(Bra) $\langle f|$ 가 벡터 $|v\rangle$에 작용하는 것을 나타낸다.
- 이것의 역할은 추상적인 '기계'가 벡터를 받아 숫자를 내놓는 것이다.
- 이 단계에서 이 기계가 '어떻게' 작동하는지 그 내부 구조를 모른다.

**(2) 오른쪽 항** : $\langle f,v\rangle$

- 이것은 벡터 $|f\rangle$와 벡터 $|v\rangle$의 **내적(inner product)** 을 나타낸다.
- 이것의 역할은 두 벡터 사이의 기하학적 관계(겹침)를 계산하여 숫자를 내놓는 것이다.
- 이것은 '켤레 전치를 해서 곱하고 더한다'는 구체적인 계산 규칙을 가지고 있다.

**(3) 등호** : (=)
- 이 등호(=)는, 왼쪽의 추상적인 범함수 $\langle f|$의 작동 방식이, 오른쪽의 구체적인 내적 $\langle f,v\rangle$ 계산 방식과 모든 벡터 $|v\rangle$에 대해 완벽하게 동일하다는 것을 의미한다.
- **즉, Bra $\langle f|$는, 그 작용이 'Ket $|f\rangle$와의 내적'이라는 연산과 모든 면에서 동일한, 유일한 선형 범함수이다.**

---

**Bra-Ket의 더 자세한 내용과 사용법은 'Dirac notation for QM'를 참고한다.**


