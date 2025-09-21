+++
title = "(b) Matrix"
weight = 5
+++

---

'행렬'이라는 용어는 이산적인 시스템을 다루기 위한 수학적 도구이다.

---

### 1. 행렬의 디렉 표기법

**(1) 단위기저(orthonormal basis) 벡터**

$$
\hat{A}=\sum_{i,j}A_{ij}|u_i\rangle\langle u_j|, \quad
\text{where }
A_{ij}=\langle u_i| \hat{A} |u_j\rangle
$$

proof)

$$
\hat{A}
=\hat{I}\hat{A}\hat{I}
=\left(\sum_i|u_i\rangle\langle u_i|\right)\hat{A}\left(\sum_j|u_j\rangle\langle u_j|\right)
=\sum_{i,j}|u_i\rangle\langle u_i|\hat{A}|u_j\rangle\langle u_j|
$$

$$
=\sum_{i,j}A_{ij}|u_i\rangle\langle u_j|
$$

**(2) 듀얼기저(dual basis) 벡터**

$$
\hat{A}=\sum_{i,j}A^i_{.j}|u_i\rangle\langle u^j|, \quad
\text{where }
A^i_{.j}=\langle u^i| \hat{A} |u_j\rangle
$$

proof)

$$
\hat{A}
=\hat{I}\hat{A}\hat{I}
=\left(\sum_i|u_i\rangle\langle u^i|\right)\hat{A}\left(\sum_j|u_j\rangle\langle u^j|\right)
=\sum_{i,j}|u_i\rangle\langle u^i|\hat{A}|u_j\rangle\langle u^j|
$$

$$
=\sum_{i,j}A^i_{.j}|u_i\rangle\langle u^j|
$$