+++
title = "(p) 1D Wave equation for free-space"
weight = 2
+++

---

1차원 파동방정식의 해는 아래와 같다.

$$
\frac{\partial^2}{\partial x^2}u\left(x,t\right)=\frac{1}{v^2}\frac{\partial^2}{\partial t^2}u\left(x,t\right)
$$

위 연산은 초기조건이 주어지지 않았으므로, 해는 유일하지 않음을 상기해라. 최종해는 가능한 모든 해를 포괄하는 일반적인 형태라는 것을 알아야 한다. 자유 공간에서, 

- 파수 중첩의 해

$$
u\left(x,t\right)=\int_{-\infty}^{\infty}dk\left\lbrack c_1\left(k\right)e^{i\left(kx-\omega t\right)}+c_2\left(k\right)e^{i\left(kx+\omega t\right)}\right\rbrack
$$

- 주파수 중첩의 해

$$
u\left(x,t\right)=\int_{-\infty}^{\infty}d\omega\left\lbrack c_1\left(\omega\right)e^{i\left(kx-\omega t\right)}+c_2\left(\omega\right)e^{i\left(kx+\omega t\right)}\right\rbrack
$$

---

**proof1) 스텀-리우빌 적용, 엄밀한 풀이**

$$
\frac{\partial^2}{\partial x^2}u\left(x,t\right)=\frac{1}{v^2}\frac{\partial^2}{\partial t^2}u\left(x,t\right)
$$

자유공간에서 라플라시안 연산자에 대해, 고유값과 고유함수를 구한다. 고유값과 고유함수가 연속적임을 이해해야 한다.

$$
L:=\frac{\partial^2}{\partial x^2}
$$

$$
\frac{\partial^2}{\partial x^2}X\left(x\right)T\left(x\right)_{}=-k^2X\left(x\right)T\left(x\right)
$$

$$
\left(\frac{\partial^2}{\partial x^2}+k^2\right)X\left(x\right)=0
$$

(1) $k\ne0$

$$
X\left(x\right)=a_1e^{-ikx}+a_2e^{ikx}
$$

(2) $k=0$

$$
X\left(x\right)=0
$$

"eigen-expansion 을 수행한다. '무한대에서 0으로 수렴해야 하는 조건'하에 미분연산자는 자기 수반(self-adjoint) 연산자이다. **이때 '무한대에서 0으로 수렴해야 하는 조건'은 푸리에 변환이 잘 정의되고 역변환이 가능하기 위해 필요하다. 이는 파동이 국소화(wave packet)되어 계수 함수 c(k)가 잘 정의될 때 충족**된다는 것을 의미한다. 또한 self-adjoint 함은 고유값은 실수이고, 이에 적분 범위는 실수축에서 수행됨을 알아야 한다. 해는 다음과 같다."

$$
u\left(x,t\right)=\int_{-\infty}^{\infty}dk\left\lbrack c\left(k\right)e^{ikx}T\left(t\right)\right\rbrack
$$

위는 파동 방정식의 해 이므로, 파동 방정식에 대입하면, T(t)를 구할 수 있다.

$$
k^2T\left(t\right)=\frac{1}{v^2}\frac{\partial^2}{\partial t^2}T\left(t\right)
$$

$$
\left(\frac{\partial^2}{\partial t^2}+\omega^2\right)T\left(t\right)=0,\quad\omega^2=k^2v^2
$$

$$
T\left(x\right)=b_1e^{-i\omega t}+b_2e^{i\omega t}
$$

따라서, 최종적으로 파동방정식의 해는 다음과 같다.

$$
u\left(x,t\right)=\int_{-\infty}^{\infty}dk\left\lbrack c_1\left(k\right)e^{i\left(kx-\omega t\right)}+c_2\left(k\right)e^{i\left(kx+\omega t\right)}\right\rbrack
$$

주파수 공간에서는 k를 ω로 바꾸기만 하면 된다.

$$
u\left(x,t\right)=\int_{-\infty}^{\infty}d\omega\left\lbrack c_1\left(\omega\right)e^{i\left(kx-\omega t\right)}+c_2\left(\omega\right)e^{i\left(kx+\omega t\right)}\right\rbrack
$$

푸리에 (역)변환과 동일한 형태이다. 잘 생각해보면, 파동의 중첩을 만족하기 때문에, 위의 결과는 당연하다.

---

**proof2) 페이저 변환과 중첩을 사용한 쉬운 풀이**

$e^{-i \omega t}$를 기준으로, 페이저 변환을 수행한다.

$$
\nabla^2\underline u\left(x\right)=-\frac{\omega^2}{v^2}\underline u\left(x\right)
$$

$$
\left(\nabla^2+\frac{\omega^2}{v^2}\right)\underline u\left(x\right)=0
$$

$\displaystyle k=\frac{\omega}{v}$이면,

$$
\left(\nabla^2+k^2\right)\underline u\left(x\right)=0
$$

따라서,

$$
u\left(x,t\right)=\underline u\left(x\right)e^{-i\omega t}
$$

1차원의 x방향 & 주파수가 중첩이 되어 있다고 하면,

$$
u\left(x,t\right)=\int d\omega\left\lbrack c_1\left(\omega\right)e^{i\left(kx-\omega t\right)}+c_2\left(\omega\right)e^{-i\left(kx+\omega t\right)}\right\rbrack
$$

proof1) 과 해가 다르다. 그러나, 위 증명에서 계수 c_1과 c_2는 여기에서와는 서로 다른 값이다. 따라서, 표현의 차이일 뿐 동일한 해를 나타낸다.

---

**proof3) 푸리에 변환을 사용한 풀이**

경계조건이 무한대 이므로, 공간에 대해, 푸리에 변환을 수행한다. k는 실수이다.

$$    
-k^2v^2\underline{u}\left(k,t\right)=\frac{\partial^2}{\partial t^2}\underline{u}\left(k,t\right), \quad -\infty < x < \infty, \quad t > 0
$$
 
$$
\underline{u}\left(k,t\right)=a_1e^{-i\omega t}+a_2e^{+i\omega t},\quad\omega^2=k^2v^2
$$
    
변수분리 형태를 적용하면,
    
$$
\underline{u}\left(k,t\right)=\underline{f}\left(k\right)e^{-i\omega t}+\underline{g}\left(k\right)e^{+i\omega t},\quad\omega^2=k^2v^2,
$$
      
해를 구하기 위해 역 푸리에 변환을 수행한다.
    
$$
F^{-1}\left\lbrace\underline{u}\left(k,t\right)\right\rbrace\left(x,t\right)=\frac{1}{2\pi}\int_{-\infty}^{\infty}dk\left\lbrack\underline{f}\left(k\right)e^{-i\omega t}+\underline{g}\left(k\right)e^{+i\omega t}\right\rbrack e^{ikx}
$$
    
$$
u\left(x,t\right)=\frac{1}{2\pi}\int_{-\infty}^{\infty}dk\left\lbrack\underline{f}\left(k\right)e^{-i\left(\omega t-kx\right)}+\underline{g}\left(k\right)e^{+i\left(\omega t+kx\right)}\right\rbrack
$$

---

### Q) 왜 증명 2는 엄밀하지 않은가.

proof2)는 단일 주파수 해를 찾은 후, 이를 '모든 주파수에 대해 중첩한다'는 다음 단계로 넘어간다. 이는 선형 시스템에 대한 중첩 원리에 기반한 유효한 추론이지만, 푸리에 변환의 엄밀한 '존재 정리' 및 '역변환 정리'를 통해 일반해를 명시적으로 유도하는 proof1&3) 만큼 수학적으로 '완전히 유도된(deductive)' 과정은 아니다. 다시 말해, proof2) 는 '이러한 형태의 해가 존재한다면 일반해는 그 중첩일 것이다'라는 직관적이고 구성적인 접근 방식에 가깝다.

---

[ABC for waves](https://www.ibiblio.org/e-notes/webgl/gpu/boundary.htm)