+++
title = "(b) Decomposition of spectrum"
weight = 4
+++

---

앞서 스펙트럼 정리는 '정규 행렬'이 완벽한 정규직교 고유벡터 기저 $\{|e_i\rangle\}$를 가짐을 보장했다. 이제 우리는 이 기저를 사용하여 연산자 $\hat{A}$ 자체를 그 가장 본질적인 구성요소들인 **고유값**과 **고유벡터**만으로 분해하고 재조립할 수 있다. 이것이 바로 **스펙트럼 분해(Spectral Decomposition)**이다.

### 스펙트럼 분해와 대각화

결론부터 말하면, **'스펙트럼 분해'와 '대각화'는 본질적으로 같은 개념**을 서로 다른 표기법으로 나타낸 것이다.

* **스펙트럼 분해**: $\hat{A} = \sum_i \lambda_i |e_i\rangle\langle e_i|$
    * **관점**: 연산자 $\hat{A}$의 **본질**을 설명한다. "$\hat{A}$라는 변환은, 각 고유 방향으로 투영하여 그 방향의 고유값만큼 크기를 조절하는 행위들의 총합이다."
* **대각화**: $A = PDP^{-1}$
    * **관점**: 연산자 $\hat{A}$의 **계산 절차**를 설명한다. "A 변환은, P⁻¹로 좌표를 바꾸고(고유 기저로), D로 스케일링한 뒤, P로 원래 좌표로 되돌리는 것이다."

---
### 1.5.1 증명

1.  **시작점**: 어떤 연산자 $\hat{A}$는 항등 연산자 $\hat{I}$를 곱해도 변하지 않는다.
    $$
    \hat{A} = \hat{A}\hat{I}
    $$
2.  **완비성 관계 삽입**: $\hat{I}$ 자리에 완비성 관계식 $\hat{I} = \sum_i |e_i\rangle\langle e_i|$를 대입한다. 여기서 $\{|e_i\rangle\}$는 $\hat{A}$의 정규직교 고유벡터 기저이다.
    $$
    \hat{A} = \hat{A} \left( \sum_i |e_i\rangle\langle e_i| \right)
    $$
3.  **연산자 분배**: $\hat{A}$를 합산 기호 안으로 넣는다.
    $$
    \hat{A} = \sum_i \hat{A}|e_i\rangle\langle e_i|
    $$
4.  **고유값 방정식 적용**: $|e_i\rangle$는 $\hat{A}$의 고유벡터이므로, $\hat{A}|e_i\rangle = \lambda_i|e_i\rangle$ 이다.
    $$
    \hat{A} = \sum_i (\lambda_i|e_i\rangle)\langle e_i|
    $$
5.  **최종 공식**: 스칼라인 고유값 $\lambda_i$를 밖으로 빼내면, 최종적인 스펙트럼 분해 공식을 얻는다.
    > $$
    \hat{A} = \sum_i \lambda_i |e_i\rangle\langle e_i|
    $$

---
### 1.5.2 예제

에르미트 행렬 $A = \begin{pmatrix} 2 & 1 \\ 1 & 2 \end{pmatrix}$를 스펙트럼 분해하시오.

* **재료 (1.2절에서 계산)**:
    * $\lambda_1 = 1$, $|e_1\rangle = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ -1 \end{pmatrix}$
    * $\lambda_2 = 3$, $|e_2\rangle = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ 1 \end{pmatrix}$
* **투영 연산자 계산**:
    * $|e_1\rangle\langle e_1| = \frac{1}{2}\begin{pmatrix} 1 & -1 \\ -1 & 1 \end{pmatrix}$
    * $|e_2\rangle\langle e_2| = \frac{1}{2}\begin{pmatrix} 1 & 1 \\ 1 & 1 \end{pmatrix}$
* **스펙트럼 분해**:
    $$
    \hat{A} = \lambda_1 |e_1\rangle\langle e_1| + \lambda_2 |e_2\rangle\langle e_2|
    $$
    $$
    = (1) \cdot \frac{1}{2}\begin{pmatrix} 1 & -1 \\ -1 & 1 \end{pmatrix} + (3) \cdot \frac{1}{2}\begin{pmatrix} 1 & 1 \\ 1 & 1 \end{pmatrix}
    $$
    $$
    = \begin{pmatrix} 1/2 & -1/2 \\ -1/2 & 1/2 \end{pmatrix} + \begin{pmatrix} 3/2 & 3/2 \\ 3/2 & 3/2 \end{pmatrix} = \begin{pmatrix} 2 & 1 \\ 1 & 2 \end{pmatrix} = A
    $$
    원래 행렬이 정확하게 재구성됨을 확인할 수 있다.

---
### 1.5.3 물리적 의미



스펙트럼 분해는 복잡한 연산자(백색광)를, 그 연산자의 가장 본질적인 성분인 **순수한 고유 상태(무지개 색깔)**들과 그 **측정값(각 색깔의 파장)**의 조합으로 나누어 이해하는 과정이다.

> 연산자 $\hat{A}$의 작용은, 사실 각 **고유 상태 방향으로 투영($|e_i\rangle\langle e_i|$)**한 다음, 그 방향의 **고유값($\lambda_i$)**만큼 크기를 조절해주는 행위를 모든 고유 방향에 대해 합산한 것과 같다.