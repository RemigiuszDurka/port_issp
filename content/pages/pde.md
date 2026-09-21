---
title: "PDE"
legacy_url: "http://users.ift.uni.wroc.pl/~rdurka/matissp/index.php/pde/"
---

# PDE

PDE (ang. *partial differential equations*) to angielski skrótowiec oznaczający **równania różniczkowe cząstkowe**.

Są to równania, w których występuje funkcja co najmniej dwóch zmiennych niezależnych oraz jej pochodne cząstkowe, czyli mamy do czynienia z równaniami postaci

$$
F\left(x,t,u,u_x,u_t,u_{xx},u_{xt},u_{tt},\ldots\right)=0,
$$

gdzie $u=u(x,t)$ jest funkcją zmiennych niezależnych $x$ i $t$, natomiast $u_x$, $u_t$, $u_{xx}$, $u_{xt}$, $u_{tt}$ itd. oznaczają jej pochodne cząstkowe kolejnych rzędów.

Uwaga: w fizyce jedną ze zmiennych niezależnych jest często czas $t$, a pozostałe opisują położenie, np. $x$. Funkcja $u(x,t)$ może wtedy oznaczać np. temperaturę, wychylenie struny lub gęstość w punkcie $x$ i w chwili $t$. 

## Wykład

- Materiały: [PDE.pdf](../site_assets/PDE.pdf)
- Lista nieliniowych [równań różniczkowych cząstkowych](https://en.wikipedia.org/wiki/List_of_nonlinear_partial_differential_equations)
- [Starsza prezentacja](../site_assets/PDE_old.pdf)

## Quiz

Przyporządkuj równaniom odpowiedni opis.

### Postać równań

1. $\displaystyle \vec\nabla\times\vec E=-\frac{\partial\vec B}{\partial t}$
2. $\displaystyle \vec\nabla\times\vec B=\mu\vec j+\mu\varepsilon\frac{\partial\vec E}{\partial t}$
3. $\displaystyle \varepsilon\vec\nabla\cdot\vec E=\rho$
4. $\displaystyle \vec\nabla\cdot\vec B=0$
5. $\displaystyle \frac{\partial T}{\partial t}=\kappa\nabla^2T$
6. $\displaystyle \vec\nabla\cdot\vec u=0$
7. $\displaystyle \frac{\partial\rho}{\partial t}=-\vec\nabla\cdot(\rho\vec u)$

### Opisy równań

- **A)** Prawo zachowania masy — dynamika płynów.
- **B)** Źródłem pola elektrycznego są ładunki elektryczne.
- **C)** Przepływający prąd oraz zmienne pole elektryczne wytwarzają pole magnetyczne.
- **D)** Nie istnieją ładunki magnetyczne.
- **E)** Prędkość zmiany temperatury jest proporcjonalna do nadwyżki średniej temperatury w otoczeniu danego punktu względem temperatury w tym punkcie.
- **F)** Zmienne w czasie pole magnetyczne wytwarza pole elektryczne.
- **G)** Przepływ jest nieściśliwy.

## Zadania do wykonania ręcznie

**Zadanie A.** Oblicz możliwe pochodne cząstkowe dla:

1. $f(x,y,z)=x^2+yz$,
2. $f(x,y,z)=z\ln(xy)$,
3. $f(x,y)=\dfrac{x}{y}$,
4. $R(t,s)=s^2\sqrt{t}$.

**Zadanie B.** Oblicz różniczkę $df$ dla:

1. $f(x,y,z)=x^2+yz$,
2. $f(x,y,z)=z\ln(xy)$,
3. $f(x,y)=\dfrac{x}{y}$,
4. $R(t,s)=s^2\sqrt{t}$.

**Zadanie C.** Przepisz równania, używając $u=u(x,t)$ oraz pochodnych w jawnej postaci, czyli

$$
\frac{\partial u}{\partial t}=u_t,
\qquad
\frac{\partial u}{\partial x}=u_x,
\qquad
\frac{\partial^2u}{\partial t^2}=u_{tt},
\qquad
\frac{\partial^2u}{\partial t\,\partial x}=u_{tx},
$$

itd.

1. $\displaystyle u_t+u_x+uu_x-u_{xxt}=0$
2. $\displaystyle u_t=u^3u_{xxx}$
3. $\displaystyle (1-u_t^2)u_{xx}+2u_xu_tu_{xt}-(1+u_x^2)u_{tt}=0$

**Zadanie D.** Sprawdź, czy funkcja

$$
\psi(t,x)=A\cos(\omega t+kx)
$$

jest rozwiązaniem równania różniczkowego cząstkowego — tzw. równania falowego:

$$
\frac{\partial^2\psi(t,x)}{\partial t^2}
-V^2\frac{\partial^2\psi(t,x)}{\partial x^2}=0,
$$

gdzie

$$
V=\frac{\omega}{k}
=\frac{2\pi/T}{2\pi/\lambda}.
$$
