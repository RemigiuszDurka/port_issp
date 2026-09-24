---
title: "ODE"
legacy_url: "http://users.ift.uni.wroc.pl/~rdurka/matissp/index.php/ode/"
---

# ODE

ODE (ang. *ordinary differential equations*) to angielski skrótowiec oznaczający **równania różniczkowe zwyczajne**.

Są to równania, w których występują funkcje jednej zmiennej niezależnej oraz jej pochodne, czyli mamy do czynienia z równaniami postaci

$$
F\left(x,y(x),y'(x),y''(x),\ldots,y^{(n)}(x)\right)=0,
$$

gdzie $y(x)$ jest funkcją zmiennej $x$, a $\frac{dy}{dx}=y'(x),\frac{d^2y}{dx^2},\ldots,\frac{d^ny}{dx^n}$ są jej pochodnymi kolejnych rzędów.

W fizyce często używamy czasu $t$ jako zmiennej niezależnej, a funkcja $x(t)$ może oznaczać np. położenie ciała w funkcji czasu. Wtedy równanie różniczkowe zwyczajne przyjmuje postać

$$
F\left(t,x(t),\frac{dx}{dt},\frac{d^2x}{dt^2},\ldots,\frac{d^nx}{dt^n}\right)=0.
$$

gdzie $\frac{dx}{dt}=\dot{x},\frac{d^2x}{dt^2}=\ddot{x},\ldots,\frac{d^nx}{dt^n}$ są pochodnymi kolejnych rzędów funkcji $x(t)$ względem czasu $t$.

## Wykład

- Materiały: [ODE.pdf](../site_assets/ODE.pdf)
- Klasyfikacja: [równania liniowe](https://en.wikipedia.org/wiki/List_of_linear_ordinary_differential_equations) i [równania nieliniowe](https://en.wikipedia.org/wiki/List_of_nonlinear_ordinary_differential_equations)
- [Starsza prezentacja](../site_assets/ODE_old.pdf)

## Zadania do wykonania ręcznie

**Zadanie A.** Jaki jest rząd następujących równań różniczkowych zwyczajnych?

1. $\displaystyle \frac{dx}{dt}=x^2$
2. $\displaystyle \left(\frac{dx}{dt}\right)^2=x$
3. $\displaystyle \frac{d^2x}{dt^2}=\left(\frac{dx}{dt}\right)^3$
4. $\displaystyle x+\frac{dx}{dt}\frac{d^2x}{dt^2}=0$

**Zadanie B.** Rozwiąż równania różniczkowe pierwszego rzędu metodą rozdzielania zmiennych:

- a) $\displaystyle \frac{dy}{dx}=\frac{x}{y}$
- b) $\displaystyle \frac{dy}{dx}=\frac{y}{x}$
- c) $\displaystyle \frac{dy}{dx}=\frac{1}{x}$
- d) $\displaystyle \frac{dy}{dx}=xy$
- e) $\displaystyle \frac{dy}{dx}=\sqrt{x}$
- f) $\displaystyle y\,dx+x\,dy=0$

**Zadanie C.** Rozwiąż równania różniczkowe drugiego rzędu:

- a) $\displaystyle \frac{d^2x}{dt^2}-a=0$
- b) $\displaystyle \frac{d^2y}{dx^2}-\frac{dy}{dx}=0$
- c) $y''+y'=0$, przy warunkach $y(0)=2$ oraz $y'(0)=-1$
- d) $y''-y=0$, przy warunkach $y(0)=2$ oraz $y'(0)=0$
- e) $y''-4y'+4y=0$, przy warunkach $y(0)=1$ oraz $y'(0)=1$
- f) $\displaystyle \frac{d^2y}{dx^2}=\omega^2y$
- g) $\displaystyle \frac{d^2y}{dx^2}=-\omega^2y$

**Zadanie D.** Zmiana prędkości pewnego samochodu od momentu wyłączenia silnika do chwili, w której samochód się zatrzymuje, opisana jest równaniem

$$
\frac{dv}{dt}=-(b+cv^2),
$$

gdzie $v$ jest prędkością samochodu w metrach na sekundę, a $t$ — czasem wyrażonym w sekundach. Aby jednostki w równaniu były zgodne, parametr $b$ ma jednostkę $\mathrm{m/s^2}$, natomiast $c$ — $\mathrm{m^{-1}}$. Parametry te opisują odpowiednio składnik oporu niezależny od prędkości oraz składnik proporcjonalny do $v^2$.

- Znajdź funkcję $v(t)$ w Wolfram Alpha, przyjmując $b=0.12$, $c=2.4\times10^{-4}$ oraz warunek początkowy $v(0)=100\,\mathrm{km/h}$.
- Znajdź drogę, po której samochód się zatrzyma.
- O ile zmieniłaby się droga do zatrzymania samochodu, gdyby zaniedbać opór powietrza, czyli przyjąć $c=0$?

**Zadanie E.** Przyporządkuj poniższe pola kierunków odpowiednim równaniom.

![Pole kierunków A.](../site_assets/2ode_SF-270x300.png){ width="260" }

![Pole kierunków B.](../site_assets/3ode_SF-265x300.png){ width="260" }

![Pole kierunków C.](../site_assets/1ode_SF-300x300.png){ width="260" }

- $\displaystyle \frac{dx}{dt}=1$
- $\displaystyle \frac{dx}{dt}=t$
- $\displaystyle \frac{dx}{dt}=tx$

**Zadanie F.** Rozwiąż numerycznie w Octave proste równanie pierwszego rzędu

$
\frac{dx}{dt}=-x,
\qquad x(0)=1,
$

korzystając z funkcji `lsode`. Porównaj wynik numeryczny z rozwiązaniem dokładnym $x(t)=e^{-t}$, rysując obie funkcje na jednym wykresie.
