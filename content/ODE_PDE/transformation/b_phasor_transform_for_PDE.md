+++
title = "(b) Phasor transform for PDE"
weight = 2
+++

---

**example1) Lossless wave equation**

아래 미분방정식의 해는 단일 주기와 파장을 가진다.

$$
\nabla^2u\left(\vec{r},t\right)=\frac{1}{v^2}\frac{\partial^2}{\partial t^2}u\left(\vec{r},t\right)
$$

{{< details summary="sol" >}}
    
$e^{-i \omega t}$를 기준으로, 페이저 변환을 수행한다.
    
$$
\nabla^2\underline u\left(\vec{r}\right)=-\frac{\omega^2}{v^2}\underline u\left(\vec{r}\right)
$$
    
$$
\left(\nabla^2+\frac{\omega^2}{v^2}\right)\underline u\left(\vec{r}\right)=0
$$
    
$k=\omega/v$ 이면,
    
$$
\left(\nabla^2+k^2\right)\underline u\left(\vec{r}\right)=0
$$
    
따라서,
    
$$
u\left(\vec{r},t\right)=\operatorname{Re}\left\lbrack\underline u\left(\vec{r}\right)e^{-i\omega t}\right\rbrack
$$
    
만약, 1차원의 x방향으로 움직이고, 여러 주파수가 중첩이 되어 있다고 하면,
    
$$
u\left(\vec{r},t\right)=\operatorname{Re}\left\lbrack\int d\omega\left\lbrack c_1\left(\omega\right)e^{i\left(kx-\omega t\right)}+c_2\left(\omega\right)e^{-i\left(kx+\omega t\right)}\right\rbrack\right\rbrack
$$

{{< /details >}}

---

**example2) Lossy wave equation**

아래 미분방정식의 해는 단일 주기와 파장을 가진다.

$$
\nabla^2u\left(\vec{r},t\right)=\mu\epsilon\frac{\partial^2}{\partial t^2}u\left(\vec{r},t\right)+\mu\sigma\frac{\partial}{\partial t}u\left(\vec{r},t\right)
$$

{{< details summary="sol" >}}
    
$e^{-i \omega t}$를 기준으로, 페이저 변환을 수행한다.
    
$$
\nabla^2\underline u\left(\vec{r}\right)=-\omega^2\mu\epsilon\underline u\left(\vec{r}\right)-i\omega\mu\sigma\underline u\left(\vec{r}\right)
$$
    
$$
\left(\nabla^2+\omega^2\mu\epsilon+i\omega\mu\sigma\right)\underline u\left(\vec{r}\right)=0
$$
    
$\displaystyle \underline \epsilon = \epsilon\left(1+i\frac{\sigma}{\omega\epsilon}\right)$ 를 복소 유전율이라고 한다.
    
$$
\left(\nabla^2+\omega^2\mu\underline{\epsilon}\right)\underline u\left(\vec{r}\right)=0
$$

$\underline{k}^2=\omega^2\mu\underline{\epsilon}$, $\underline{k}=k+i\kappa$  라고 하면,
   
$$
\left(\nabla^2+\underline{k}^2\right)\underline u\left(\vec{r}\right)=0
$$
    
$$
k=\omega\sqrt{\frac{\mu\epsilon}{2}}\left(\sqrt{1+\left(\frac{\sigma}{\omega\epsilon}\right)^2}+1\right)^{1/2}
$$
    
$$
\kappa=\omega\sqrt{\frac{\mu\epsilon}{2}}\left(\sqrt{1+\left(\frac{\sigma}{\omega\epsilon}\right)^2}-1\right)^{1/2}
$$
    
만약, 도전율이 매우 크다면(양도체),
    
$$
k=\kappa=\sqrt{\pi f\mu \sigma}
$$
    
따라서,
    
$$
u\left(\vec{r},t\right)=\operatorname{Re}\left\lbrack\underline u\left(\vec{r}\right)e^{-i\omega t}\right\rbrack
$$

 {{< /details >}}