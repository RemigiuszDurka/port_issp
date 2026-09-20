---
marp: true
theme: default
paginate: true
header: "Remigiusz Durka: MatISSP2, Wektory i pola wektorowe"
style: |
  section {
    font-size: 26px;
    text-align: left;
  }
  h1 {
    color: #027cfe;
  }
  h2 {
    color: rgba(34, 142, 230, 1);
  }
  strong {
    color: #be0791;
  }
------

# Pola wektorowe 

# Równania różniczkowe cząstkowe 
## Partial Differential Equations (PDE)

Remigiusz Durka  
2026

---

# Pole skalarne

**Pole skalarne** to funkcja, która każdemu punktowi przestrzeni przyporządkowuje jedną liczbę rzeczywistą.

W 2D i 3D odpowiednio: $f(x,y)$  oraz $f(x,y,z)$.

Innymi słowy:

- punktowi przypisujemy **skalarną wartość**, która może zależeć od położenia w przestrzeni.

**Przykłady pól skalarnych:**

- temperatura $T(x,y,z)$,
- ciśnienie $p(x,y,z)$,
- gęstość $\rho(x,y,z)$,
- potencjał elektryczny $\phi(x,y,z)$.

---

# Promień wodzący

Punkt przestrzeni możemy opisać za pomocą **promienia wodzącego**, czyli wektora poprowadzonego od początku układu współrzędnych do danego punktu.

W 2D:
$$
\vec{r} = [x,y]
$$

W 3D:
$$
\vec{r} = [x,y,z]
$$

Promień wodzący nie opisuje jeszcze pola - wskazuje jedynie, **w którym punkcie przestrzeni** się znajdujemy.

W fizyce bardzo bardzo często spotykamy się z funkcjami, które zależą od położenia w przestrzeni, czyli mają postać $f(\vec{r})$. Również promień wodzący często zależy od czasu, czyli 

$$
\vec{r} = \vec{r}(t)=[x(t),y(t),z(t)]
$$

---

# Pole wektorowe

**Pole wektorowe** to funkcja, która każdemu punktowi przestrzeni przyporządkowuje wektor. Możemy więc zapisać:

$$
\vec{u}(\vec{r})
$$

albo w 2D i 3D odpowiednio:

$$
\vec{u}(x,y), \qquad \vec{u}(x,y,z)
$$

Innymi słowy:

- punkt przestrzeni jest dany przez **promień wodzący** $\vec{r}$,
- pole wektorowe przypisuje mu **wektor** $\vec{u}(\vec{r})$, który jest „przyczepiony” do tego punktu.

**Przykłady pól wektorowych:**

- pole prędkości w ruchu płynu, pole sił w mechanice i elektrodynamice,
- natężenie pola grawitacyjnego, natężenie pola elektrycznego.

---

# Przykład: pole prędkości

Rozważmy ruch płynu. Każdemu punktowi przestrzeni o promieniu wodzącym

$$
\vec{r} = [x,y,z]
$$

przypisujemy wektor prędkości płynu:

$$
\vec{v}(\vec{r}) = \vec{v}(x,y,z).
$$

Oznacza to, że w każdym punkcie przestrzeni płyn może poruszać się:

- w innym kierunku,
- z inną szybkością.

Zatem **pole prędkości** jest przykładem pola wektorowego. To samo będzie z siłą $\vec{F}(\vec{r})$ czy natężeniem pola elektrycznego $\vec{E}(\vec{r})$.

---

# Przykład pola wektorowego w 2D

Rozważmy pole

$$
\vec{u}(x,y) = [-y,x].
$$

Dla dwóch punktów o promieniach wodzących

$$
\vec{r}_1 = (1,2), \quad \vec{r}_2 = (3,4)
$$

otrzymujemy wektor pola (o różnych długościach i kierunkach):

$$
\vec{u}(1,2) = [-2,1] \quad \text{oraz} \quad \vec{u}(3,4) = [-4,3].
$$

Interpretacja:

- do punktu przestrzeni $\vec{r}_1$ przypisujemy wektor $\vec{u} = [-2,1]$ zaczepiony w punkcie $(1,2)$
- do punktu przestrzeni $\vec{r}_2$ przypisujemy wektor $\vec{u} = [-4,3]$ zaczepiony w punkcie $(3,4)$.

**Przykłady pola 2D i 3D**: [https://teaching.smp.uq.edu.au/scims/Adv_calculus/Vector_field.html](https://teaching.smp.uq.edu.au/scims/Adv_calculus/Vector_field.html)

---

## Zanim przejdziemy dalej

Przypomnijmy pochodne cząstkowe funkcji wielu zmiennych.

Dla funkcji $f(x, y, z)$ pochodne cząstkowe definiujemy jako:

- **Pochodna cząstkowa po $x$**: $\frac{\partial f}{\partial x} = \lim_{h \to 0} \frac{f(x + h, y, z) - f(x, y, z)}{h}$,
- **Pochodna cząstkowa po $y$**: $\frac{\partial f}{\partial y} = \lim_{h \to 0} \frac{f(x, y + h, z) - f(x, y, z)}{h}$,
- **Pochodna cząstkowa po $z$**: $\frac{\partial f}{\partial z} = \lim_{h \to 0} \frac{f(x, y, z + h) - f(x, y, z)}{h}$.

Różniczka zupełna funkcji $f(x, y, z)$ to:
$$
df = \frac{\partial f}{\partial x} dx + \frac{\partial f}{\partial y} dy + \frac{\partial f}{\partial z} dz.
$$

---

## Gradient

Gradient funkcji skalarnej $f$ to wektor zawierający jej pochodne cząstkowe względem wszystkich zmiennych. Intuicyjnie gradient wskazuje kierunek najszybszego wzrostu funkcji.

$$
\nabla f = \left( \frac{\partial f}{\partial x_1}, \frac{\partial f}{\partial x_2}, \dots, \frac{\partial f}{\partial x_N} \right)
$$

---

## Gradient w przestrzeni 3D

Dla funkcji $f(x,y,z)$ gradient ma postać:
$$
\nabla f = \left( \frac{\partial f}{\partial x}, \frac{\partial f}{\partial y}, \frac{\partial f}{\partial z} \right).
$$

Gradient w 3D jest **wektorem**, którego współrzędne to pochodne cząstkowe funkcji $f$ względem $x, y, z$.

## Gradient w przestrzeni 2D

Dla funkcji $f(x,y)$ gradient ma postać:
$$
\nabla f = \left( \frac{\partial f}{\partial x}, \frac{\partial f}{\partial y} \right).
$$

---

## Interpretacja gradientu

- Kierunek gradientu wskazuje najszybszy wzrost wartości funkcji.
- Długość gradientu określa tempo tej zmiany.
- Jeśli gradient jest równy zeru, to jesteśmy w punkcie stacjonarnym (np. minimum, maksimum lub siodło).

## Zastosowania gradientu

Gradient jest szeroko stosowany w:
- optymalizacji matematycznej,
- analizie pól skalarowych (np. temperatura, ciśnienie),
- fizyce (np. siły w polach potencjalnych).

---

## Przykład gradientu

Rozważmy funkcję $f(x, y) = x^2 + y^2$. Obliczmy jej gradient:
$$
\nabla f = \left( \frac{\partial f}{\partial x}, \frac{\partial f}{\partial y} \right) = \left( 2x, 2y \right).
$$

- Gradient to wektor $\nabla f = (2x, 2y)$.
- W punkcie $(1, 2)$ gradient wynosi $\nabla f = (2, 4)$.

---

# Dywergencja

Dywergencja to operator różniczkowy stosowany do pól wektorowych. Mierzy stopień, w jakim pole „źródłowe” rozszerza się lub kurczy w danym punkcie.

Matematycznie dywergencję pola wektorowego $\vec{u}=(u_x, u_y, u_z)$ definiujemy jako:
$$
\operatorname{div}\,\vec{u} \equiv \nabla \cdot \vec{u} = \frac{\partial u_x}{\partial x} + \frac{\partial u_y}{\partial y} + \frac{\partial u_z}{\partial z}.
$$

---

## Interpretacja dywergencji

- Jeśli $\operatorname{div}\,\vec{u} > 0$, pole „rozszerza się” w punkcie (źródło strumienia).
- Jeśli $\operatorname{div}\,\vec{u} < 0$, pole „kurczy się” (ujście strumienia).
- Jeśli $\operatorname{div}\,\vec{u} = 0$, pole jest bezźródłowe (brak źródeł i ujść).

## Zastosowania dywergencji

- **Fizyka płynów** – opis zmian gęstości/przepływu.
- **Elektrodynamika** – równania Maxwella (prawo Gaussa).
- **Mechanika ośrodków ciągłych** – pola deformacji i naprężeń.

---

## Przykład

Rozważmy pole wektorowe $\vec{u} = (x, y^2, z^3)$. Obliczmy dywergencję:
$$
\operatorname{div}\,\vec{u} = \nabla \cdot \vec{u}
= \frac{\partial}{\partial x}x + \frac{\partial}{\partial y} y^2 + \frac{\partial}{\partial z} z^3
= 1 + 2y + 3z^2.
$$

- W punkcie $(1, 2, 3)$: 

$$
\operatorname{div}\,\vec{u}(1, 2, 3) = 1 + 2\cdot 2 + 3\cdot 3^2 = 32
$$

---

# Rotacja

Rotacja (wir, curl) to operator różniczkowy stosowany do pól wektorowych. Mierzy stopień wirowości pola, czyli tendencję do obrotu „wokół punktu”.

Definicja rotacji pola wektorowego $\vec{u} = (u_x, u_y, u_z)$:
$$
\nabla \times \vec{u} =
\left(
\frac{\partial u_z}{\partial y} - \frac{\partial u_y}{\partial z},
\frac{\partial u_x}{\partial z} - \frac{\partial u_z}{\partial x},
\frac{\partial u_y}{\partial x} - \frac{\partial u_x}{\partial y}
\right).
$$

---

## Interpretacja rotacji

- Jeśli $\nabla \times \vec{u} \neq 0$, pole ma **wirowość**.
- Jeśli $\nabla \times \vec{u} = 0$, pole jest **bezwirowe**.

## Oznaczenia

- $\nabla \times \vec{u}$,
- $\operatorname{rot}\,\vec{u}$,
- $\operatorname{curl}\,\vec{u}$.

---

## Źródłowość i wirowość pola wektorowego

Kiedy mamy niezerowe wartości dywergencji, pole jest źródłowe (rozszerza się lub kurczy). Kiedy mamy niezerowe wartości rotacji, pole jest wirowe (ma tendencję do obrotu).

![](image-4.png)

---

# Pola wektorowe na wykresach kolejno

$$
[1,0],\qquad \qquad \qquad [x,y]
$$

$$
[-y,x],\qquad [x-y,x+y]
$$

![width:95% bg right:50%](10_div_curl_2d.png)

## Jak to pogodzić z tym, że rotacja działa w 3D?

Trzeba przyjmować, że wektor $\vec{u}$ jest rozpięty na trzech wymiarach, ale jego składowa wzdłuż osi $z$ jest równa zero. Wtedy rotacja będzie miała tylko składową wzdłuż osi $z$, a jej wartość będzie równa różnicy pochodnych cząstkowych względem $x$ i $y$.

---

## Zastosowania rotacji

- **Hydrodynamika** – wiry w płynach.
- **Elektrodynamika** – równania Maxwella (np. prawo Faradaya).
- **Mechanika płynów** – turbulencje.

---

## Przykład rotacji

Rozważmy pole $\vec{u} = (x y, y z, z x)$.

$$
\nabla \times \vec{u} =
\begin{vmatrix}
\hat{\mathbf{i}} & \hat{\mathbf{j}} & \hat{\mathbf{k}} \\
\frac{\partial}{\partial x} & \frac{\partial}{\partial y} & \frac{\partial}{\partial z} \\
xy & yz & zx
\end{vmatrix}.
$$

Jeszcze raz:
$$
\nabla \times \vec{u} = \left( \frac{\partial (zx)}{\partial y} - \frac{\partial (yz)}{\partial z}, \frac{\partial (xy)}{\partial z} - \frac{\partial (zx)}{\partial x}, \frac{\partial (yz)}{\partial x} - \frac{\partial (xy)}{\partial y} \right).
$$

Ostatecznie:
$$
\nabla \times \vec{u} = (0 - y,\ 0 - z,\ 0 - x) = (-y, -z, -x).
$$

---

# Laplasjan

## Definicja Laplasjanu

Laplasjan (operator Laplace'a) to operator różniczkowy drugiego rzędu:
$$
\Delta u = \nabla^2 u = \frac{\partial^2 u}{\partial x^2} + \frac{\partial^2 u}{\partial y^2} + \frac{\partial^2 u}{\partial z^2}.
$$

---

## Interpretacja Laplasjanu

- Opisuje, na ile wartość „średnia” funkcji $u$ w otoczeniu punktu różni się od $u$ w tym punkcie.
- Wskazuje, czy funkcja ma w punkcie tendencję do minimum/maksimum (intuicyjnie: „wypukłość/wklęsłość”).

## Alternatywne zapisy

- $\Delta u$,
- $\operatorname{div}\operatorname{grad} u$.

---

## Zastosowania Laplasjanu

- **Fizyka matematyczna** – równania Laplace’a i Poissona.
- **Teoria ciepła** – $\frac{\partial u}{\partial t} = \alpha \Delta u$.
- **Równanie Schrödingera** – $-\frac{\hbar^2}{2m} \Delta \psi + V \psi = E \psi$.
- **Przetwarzanie obrazów** – filtry krawędzi.

---

## Przykład Laplasjanu

Rozważmy $u(x, y) = x^2 + y^3$. Liczymy:
$$
\Delta u = \frac{\partial^2 u}{\partial x^2} + \frac{\partial^2 u}{\partial y^2} = 2 + 6y.
$$

- W punkcie $(1, 2)$: 

$$
\Delta u(1, 2) = \left(\frac{\partial^2 u}{\partial x^2}+ \frac{\partial^2 u}{\partial y^2}\right)\Big|_{x=1,y=2} = 2 + 6\cdot 2 = 14
 2 + 6\cdot 2 = 14
$$

---


# Operatory różniczkowe: Klasyfikacja

Operator nabla $\nabla = (\partial_x, \partial_y, \partial_z)$ stanowi trzon analizy wektorowej:

| Operator | Działa na | Wynik | Schemat przekształcenia |
| :--- | :--- | :--- | :--- |
| **Gradient ($\nabla f$)** | pole skalarne | pole wektorowe | $\text{skalar} \to \text{wektor}$ |
| **Dywergencja ($\nabla \cdot \vec{u}$)** | pole wektorowe | pole skalarne | $\text{wektor} \to \text{skalar}$ |
| **Rotacja ($\nabla \times \vec{u}$)** | pole wektorowe | pole wektorowe | $\text{wektor} \to \text{wektor}$ |
| **Laplasjan ($\Delta f = \nabla^2 f$)** | pole skalarne | pole skalarne | $\text{skalar} \to \text{skalar}$ |

---

# Analityczna postać operatorów w $\mathbb{R}^3$

| Operator | Definicja we współrzędnych kartezjańskich |
| :--- | :--- |
| **Gradient** | $\nabla f = \left( \frac{\partial f}{\partial x}, \frac{\partial f}{\partial y}, \frac{\partial f}{\partial z} \right)$ |
| **Dywergencja** | $\nabla \cdot \vec{u} = \frac{\partial u_x}{\partial x} + \frac{\partial u_y}{\partial y} + \frac{\partial u_z}{\partial z}$ |
| **Rotacja** | $\nabla \times \vec{u} = \left( \frac{\partial u_z}{\partial y} - \frac{\partial u_y}{\partial z}, \, \frac{\partial u_x}{\partial z} - \frac{\partial u_z}{\partial x}, \, \frac{\partial u_y}{\partial x} - \frac{\partial u_x}{\partial y} \right)$ |
| **Laplasjan** | $\Delta u = \nabla^2 u = \frac{\partial^2 u}{\partial x^2} + \frac{\partial^2 u}{\partial y^2} + \frac{\partial^2 u}{\partial z^2}$ |

<div class="card">
<b>Różniczka zupełna funkcji:</b> 
$$df = \frac{\partial f}{\partial x}dx + \frac{\partial f}{\partial y}dy + \frac{\partial f}{\partial z}dz = \nabla f \cdot d\vec{r}$$
</div>

---

<div class="grid-2">
<div>

### Twierdzenie Stokesa
Cyrkulacja wektora a strumień rotacji:
$$\oint_C \vec{F} \cdot d\vec{r} = \iint_S (\nabla \times \vec{F}) \cdot d\vec{S}$$

### Twierdzenie Gaussa
Strumień pola a całka dywergencji:
$$\iint_S \vec{F} \cdot d\vec{S} = \iiint_V (\nabla \cdot \vec{F})\, dV$$

</div>
<div>

### Równanie ciągłości
Zachowanie masy lub ładunku w ośrodku:
$$\frac{\partial \rho}{\partial t} + \nabla \cdot (\rho \vec{v}) = 0$$

</div>
</div>

---

# Równania Maxwella w postaci różniczkowej

<div class="grid-2">
<div class="card">

**Prawo Gaussa (elektryczność):**
$$\nabla \cdot \vec{E} = \frac{\rho}{\varepsilon_0}$$

**Prawo Gaussa (magnetyzm):**
$$\nabla \cdot \vec{B} = 0$$

</div>
<div class="card">

**Prawo Faradaya (indukcja):**
$$\nabla \times \vec{E} = -\frac{\partial \vec{B}}{\partial t}$$

**Prawo Ampère'a-Maxwella:**
$$\nabla \times \vec{B} = \mu_0 \vec{J} + \mu_0 \varepsilon_0 \frac{\partial \vec{E}}{\partial t}$$

</div>
</div>

---

# Równania Różniczkowe Cząstkowe i Równanie Falowe

## Od podstaw mechaniki i elektrodynamiki do pełnego wyprowadzenia

---

# Czym są równania różniczkowe cząstkowe (PDE)?

<div class="card">
<b>Równanie różniczkowe cząstkowe (PDE)</b> to równanie, w którym poszukiwana jest funkcja wielu zmiennych, a w równaniu występują jej pochodne cząstkowe.
</div>

- **Porównanie:** W badanych wcześniej równaniach różniczkowych zwyczajnych (ODE) funkcje zależały wyłącznie od **jednej zmiennej**.
- **Warunki jednoznaczności:** Do znalezienia konkretnego rozwiązania fizycznego niezbędne są **warunki brzegowe** i/lub **początkowe**.
- **Fundamentalne przykłady PDE w fizyce:**
  - Równanie falowe
  - Równanie Laplace'a i Poissona
  - Równanie przewodnictwa ciepła (dyfuzji)
  - Równanie Schrödingera

---

# Rys historyczny: Narodziny PDE

* **Badania nad drganiami:** PDE narodziły się z analizy procesów falowych i mechanicznych (drgania strun, prętów, membran) oraz akustyki i hydromechaniki.
* **J. d'Alembert (połowa XVIII w.):** Sformułował pierwsze w historii równanie różniczkowe cząstkowe opisujące strunę drgającą — prototyp równań typu <span class="badge">hiperbolicznego</span>.
* **L. Euler (1707–1783):** Doprecyzował warunki określające jednoznaczność rozwiązań równania struny.
* **D. Bernoulli:** Zauważył, że rozwiązanie można przedstawić jako superpozycję drgań harmonicznych (szereg trygonometryczny).
* **J. Fourier (1750–1830):** Usystematyzował i rozwinął teorię szeregów trygonometrycznych na potrzeby przepływu ciepła.

---

# Ewolucja i klasyfikacja równań

- **A.L. Cauchy:** Sformułował fundamentalne pojęcie zagadnienia początkowego (*zagadnienie Cauchy'ego*).
- **Klasa eliptyczna:**
  - **P. Laplace:** Równanie potencjału sił grawitacyjnych ($\Delta \phi = 0$).
  - **S.D. Poisson:** Rozwinięcie teorii przyciągania mas ($\Delta \phi = f$).
  - Powiązane bezpośrednio z mechaniką nieba i grawimetrią.
- **G. Green (początek XIX w.):** Podstawy teorii potencjału w elektryczności i magnetyzmie.
- **Klasa paraboliczna:**
  - Powstała na bazie badań nad zjawiskiem **przewodnictwa cieplnego** oraz **dyfuzji gazów i cieczy**.

---

# 1. Ruch harmoniczny prosty (Oscylator)

Opisuje drgania punktu materialnego pod wpływem siły sprężystej:

<div class="card">

$$x(t) = A \cos(\omega t + \varphi)$$
</div>

- **$x(t)$** — chwilowe wychylenie z położenia równowagi
- **$A$** — amplituda drgań (maksymalne wychylenie)
- **$\omega$** — częstość kołowa drgań: $\omega = \sqrt{\frac{k_{spr}}{m}} \implies \omega^2 = \frac{k_{spr}}{m}$
- **$\varphi$** — faza początkowa drgań (dla $t = 0$)
- **$\omega t + \varphi$** — całkowita faza ruchu w chwili $t$

*Zależność dotyczy wyłącznie upływu czasu: funkcja $x = x(t)$.*

---

# 2. Ruch falowy (Fala biegnąca)

Opisuje rozchodzenie się zaburzenia jednocześnie w **czasie** i **przestrzeni**:

<div class="card">
$$\xi(x,t) = A \cos(\omega t - kx + \varphi)$$
</div>

- **$\xi(x,t)$** — wychylenie cząstki ośrodka w punkcie $x$ w chwili $t$
- **$A$** — amplituda fali
- **$\omega$** — częstość kołowa: $\omega = \frac{2\pi}{T} = 2\pi f$
- **$k$** — liczba falowa: $k = \frac{2\pi}{\lambda}$ ($\lambda$ to długość fali)
- **$(\omega t - kx + \varphi)$** — faza fali biegnącej w kierunku $+x$

---

# Zestawienie porównawcze: Oscylator vs Fala

| Cecha / Parametr | Ruch harmoniczny (Oscylator) | Ruch falowy (Fala płaska) |
| :--- | :--- | :--- |
| **Dziedzina funkcji** | Tylko czas: $t$ | Czas i przestrzeń: $(x, t)$ |
| **Postać kinematyczna** | $x(t) = A \cos(\omega t + \varphi)$ | $\xi(x,t) = A \cos(\omega t - kx + \varphi)$ |
| **Faza zależy od** | $\omega t$ | $\omega t - kx$ |
| **Częstość kołowa** | $\omega^2 = \frac{k_{spr}}{m}$ | $\omega = \frac{2\pi}{T} = 2\pi f$ |
| **Przestrzeń** | Punkt zlokalizowany | Liczba falowa: $k = \frac{2\pi}{\lambda}$ |
| **Prędkość propagacji** | Brak (drgania w miejscu) | Prędkość fazowa: $v = \frac{\omega}{k}$ |

---

# Wyprowadzenie równania falowego: Krok 1

Różniczkujemy równanie fali $\xi(x,t) = A \cos(\omega t - kx + \varphi)$ względem czasu $t$:

**Pierwsza pochodna cząstkowa po czasie:**
$$\frac{\partial \xi}{\partial t} = -\omega A \sin(\omega t - kx + \varphi)$$

**Druga pochodna cząstkowa po czasie:**
$$\frac{\partial^2 \xi}{\partial t^2} = -\omega^2 \underbrace{A \cos(\omega t - kx + \varphi)}_{\xi(x,t)} = -\omega^2 \xi$$

Dzieląc obie strony przez $-\omega^2$, otrzymujemy:
$$-\frac{1}{\omega^2} \frac{\partial^2 \xi}{\partial t^2} = \xi$$

---

# Wyprowadzenie równania falowego: Krok 2

Różniczkujemy to samo równanie względem współrzędnej przestrzennej $x$:

**Pierwsza pochodna cząstkowa po przestrzeni:**
$$\frac{\partial \xi}{\partial x} = -(-k) A \sin(\omega t - kx + \varphi) = k A \sin(\omega t - kx + \varphi)$$

**Druga pochodna cząstkowa po przestrzeni:**
$$\frac{\partial^2 \xi}{\partial x^2} = -k^2 \underbrace{A \cos(\omega t - kx + \varphi)}_{\xi(x,t)} = -k^2 \xi$$

Dzieląc obie strony przez $-k^2$, otrzymujemy:
$$-\frac{1}{k^2} \frac{\partial^2 \xi}{\partial x^2} = \xi$$

---

# Złożenie równań i prędkość fali

Ponieważ prawe strony obu zależności są równe tej samej funkcji $\xi(x,t)$:

$$-\frac{1}{k^2} \frac{\partial^2 \xi}{\partial x^2} = -\frac{1}{\omega^2} \frac{\partial^2 \xi}{\partial t^2} \implies \frac{\partial^2 \xi}{\partial x^2} = \frac{k^2}{\omega^2} \frac{\partial^2 \xi}{\partial t^2}$$

<div class="card">
<b>Związek dyspersyjny dla fali:</b>

$$v = \frac{\omega}{k} \iff k = \frac{\omega}{v} \iff \frac{k}{\omega} = \frac{1}{v} \iff \frac{k^2}{\omega^2} = \frac{1}{v^2}$$
</div>

Podstawiając stosunek $\frac{k^2}{\omega^2} = \frac{1}{v^2}$, uzyskujemy **równanie falowe 1D**:
$$\frac{\partial^2 \xi}{\partial x^2} = \frac{1}{v^2} \frac{\partial^2 \xi}{\partial t^2}$$

---

# Dowód tożsamości ($L = P$)

Sprawdźmy tożsamość dla funkcji fali $\xi(t, x) = \cos(\omega t - kx)$ w równaniu $\frac{\partial^2 \xi}{\partial x^2} = \frac{1}{v^2} \frac{\partial^2 \xi}{\partial t^2}$:

- **Lewa strona ($L$):**
  $$\frac{\partial^2 \xi}{\partial x^2} = \frac{\partial^2}{\partial x^2}[\cos(\omega t - kx)] = -(-k)^2 \cos(\omega t - kx) = -k^2 \xi$$

- **Prawa strona ($P$):**
  $$\frac{1}{v^2}\frac{\partial^2 \xi}{\partial t^2} = \frac{1}{v^2} [-\omega^2 \cos(\omega t - kx)] = -\frac{\omega^2}{v^2}\xi$$

Ponieważ $v = \frac{\omega}{k}$, to $\frac{\omega^2}{v^2} = \frac{\omega^2}{\omega^2 / k^2} = k^2$. 
Stąd:
$$-k^2 \xi = -k^2 \xi \implies L = P \quad \blacksquare$$

---

<!-- _class: lead -->

# Podsumowanie

- Równania różniczkowe cząstkowe stanowią wspólny język zjawisk transportu, fal i pól w czasoprzestrzeni.
- Przejście od opisu punktu (ODE) do ośrodka ciągłego (PDE) wprowadza przestrzenną zależność fazy: $(\omega t \to \omega t - kx)$.
- Zależność prędkości fazowej fali $v = \frac{\omega}{k}$ bezpośrednio unifikuje drugie pochodne cząstkowe w uniwersalne **równanie falowe**.