---
title: "Aproksymacje"
legacy_url: "http://users.ift.uni.wroc.pl/~rdurka/matissp/index.php/aproksymacje/"
---

# Aproksymacje

Aproksymacje to przybliżenia funkcji za pomocą wielomianów lub innych funkcji prostszych niż aproksymowana funkcja.

GNU Octave oferuje narzędzia do aproksymacji danych. W tym rozdziale będziemy używać przede wszystkim funkcji `polyfit(x, y, n)`, która wyznacza współczynniki wielomianu stopnia `n` dopasowanego do danych `(x,y)` metodą najmniejszych kwadratów. Otrzymany wielomian można następnie obliczać poleceniem `polyval` i porównywać z danymi na wykresie.

Warto przypomnieć szereg Taylora, który pozwala aproksymować funkcję w pobliżu pewnego punktu za pomocą wielomianu. W szczególności, dla funkcji $f(x)$ rozwiniętej w szereg Taylora wokół punktu $x_0$ mamy

$$
f(x)=f(x_0)+f'(x_0)(x-x_0)+\frac{f''(x_0)}{2!}(x-x_0)^2+\ldots = \sum_{n=0}^{\infty}\frac{f^{(n)}(x_0)}{n!}(x-x_0)^n.
$$

## Wykład

- [Starsza prezentacja](../site_assets/funkcje2_old.pdf)
- Przykłady dopasowania: [fitowanie-0](../site_assets/fit-0.png), [fitowanie-1](../site_assets/fit-1.png), [fitowanie-2](../site_assets/fit-2.png)

## Quiz

**1.** Znajdź błąd w następującym rozumowaniu:

   - Jeżeli funkcja ciągła przyjmuje w punktach $a$ i $b$ wartości $f(a)$ i $f(b)$, to przyjmuje też wszystkie wartości pomiędzy $f(a)$ i $f(b)$.

   - Funkcja $y(x)=1/x$ jest funkcją elementarną, a więc jest funkcją ciągłą; ponadto $y(-1)=-1$ oraz $y(1)=1$.

   - Łącząc powyższe fakty, dochodzimy do wniosku, że musi istnieć liczba $x_0\in[-1,1]$ taka, że $1/x_0=0$.

**2.** Czy funkcja, której wykres przedstawia poniższy rysunek,

   ![Przykład funkcji z nieciągłością.](https://upload.wikimedia.org/wikipedia/commons/d/d2/Lower_semi.png){ width="420" }

   - ma granicę lewostronną w $x_0$?

   - ma granicę prawostronną w $x_0$?

   - jest ciągła lewostronnie w $x_0$?

   - jest ciągła prawostronnie w $x_0$?

   - jest ciągła w $x_0$?

**3.** Czy funkcja

   $$
   y(x)=\frac{2x-1}{x+2},
   $$

   której wykres przedstawia poniższy rysunek,

   [![Wykres funkcji homograficznej.](https://upload.wikimedia.org/wikipedia/commons/c/c4/Homografia.svg){ width="500" }](https://upload.wikimedia.org/wikipedia/commons/c/c4/Homografia.svg)

   - ma w punkcie $x=-2$ granicę prawostronną, właściwą lub nie?

   - ma w punkcie $x=-2$ granicę lewostronną, właściwą lub nie?

   - jest w punkcie $x=-2$ lewostronnie lub prawostronnie ciągła?

   - jest w punkcie $x=-2$ ciągła?

   - jest ciągła na odcinku $[1,2]$?

   - jest ciągła na odcinku $[-3,0]$?

**4.** Na podstawie wykresu funkcji z poprzedniego pytania odpowiedz na następujące pytania:

   - Czy funkcja ta ma funkcję odwrotną?

   - Jeśli tak, to jaka jest jej dziedzina?

## Zadania do wykonania ręcznie

**Zadanie 1.** O pewnym wielomianie $W$ wiadomo, że $W(0)=4$ i $W(2)=-3$. Czy ten wielomian musi mieć pierwiastek?

**Zadanie 2.** Skoro

$$
\sin x=x-\frac{x^3}{3!}+\frac{x^5}{5!}-\ldots,
$$

to ile wynosi

$$
\lim_{x\to 0}\frac{\sin x}{x}\,?
$$

**Zadanie 3.** Skoro

$$
\cos x=1-\frac{x^2}{2!}+\frac{x^4}{4!}-\ldots,
$$

to ile wynosi

$$
\lim_{x\to 0}\frac{1-\cos x}{x^2}\,?
$$

**Zadanie 4.** Skoro

$$
\ln(1+x)=x-\frac{x^2}{2}+\frac{x^3}{3}-\ldots,
$$

to ile wynosi

$$
\lim_{x\to 0}\frac{\ln(1+x)}{x}\,?
$$

**Zadanie 5.** Przypomnij, ile wynosi rozwinięcie funkcji $e^x$. Zapisz rozwinięcie aż do piątej potęgi.

**Zadanie 6.** Podaj analogiczne rozwinięcie $e^{-x}$.

**Zadanie 7.** Podaj analogiczne rozwinięcie $e^{ix}$.

**Zadanie 8.** Wyraź $e^{ix}$ jako kombinację $\sin x$ oraz $\cos x$.

**Zadanie 9.** Podaj rozwinięcie cosinusa hiperbolicznego, wiedząc, że

$$
\cosh x=\frac{e^x+e^{-x}}{2}.
$$

**Zadanie 10.** Biorąc zadania powyżej, udowodnij poprawność słynnego wzoru Eulera:

 $$
 e^{i\pi}+1=0.
 $$

## Zadania do wykonania w asyście komputera

**Zadanie 1.** **Octave:** Jak już wiesz,

$$
\sin x=x-\frac{x^3}{3!}+\frac{x^5}{5!}-\ldots,
\qquad
\cos x=1-\frac{x^2}{2!}+\frac{x^4}{4!}-\ldots.
$$

Niech $s(x)$ będzie wielomianem, który powstaje z powyższego szeregu dla $\sin x$ po odrzuceniu wyrazów w potędze wyższej niż 5. Podobnie niech $c(x)$ będzie wielomianem, który powstaje z szeregu dla $\cos x$ po odrzuceniu wyrazów wyższego stopnia niż 5.

- Utwórz iloczyn

  $$
  w(x)=s(x)\cdot s(x)+c(x)\cdot c(x),
  $$

  który powinien w przybliżeniu równać się $\sin^2 x+\cos^2 x$, czyli mieć wartość 1. Jeżeli używasz Octave i polecenia `conv`, wielomiany **nie muszą mieć tego samego stopnia** — `conv` potrafi mnożyć wektory współczynników o różnej długości. Subtelność pojawia się dopiero wtedy, gdy chcemy później **dodać** otrzymane wielomiany, np. `conv(s,s)` i `conv(c,c)`: ich wektory współczynników muszą odnosić się do tych samych potęg i mieć zgodną długość. Krótszy wektor trzeba więc odpowiednio dopełnić zerami od strony najwyższych potęg.
- Sprawdź, że wyraz wolny $w(x)$ faktycznie równa się 1, a wszystkie pozostałe jego wyrazy stopnia $\leq 5$ równe są 0.
- Sprawdź, jakie wartości ma $w(x)-1$ dla `x = linspace(0, pi, 100)`.

**Zadanie 2.** **Ważne zadanie:** Niech w Octave

```octave
x = 0:0.1:3;
y = exp(x);
```

- Za pomocą polecenia `polyfit` dopasuj do `(x, y)` wielomiany stopnia od 1 do 5. Czy współczynniki tych wielomianów w wyrazach o potędze $\leq 3$ dążą do współczynników wielomianu uzyskanego z rozwinięcia $\exp x$ względem $x$ wokół 0, tj.

  $$
  \exp x=1+x+\frac{x^2}{2}+\frac{x^3}{6}+\ldots\,?
  $$

  Wskazówka — szybka komenda do wyświetlenia jednego z tych wielomianów:

  ```octave
  polyout(polyfit(x, y, 1));
  ```

- Wyświetl $y(x)$ oraz kolejne wielomiany aproksymacyjne otrzymane w poprzednim punkcie. Czy wykresy wielomianów wyższych stopni coraz lepiej odpowiadają aproksymowanej funkcji na zadanym przedziale?

  Wskazówka:

  ```octave
  plot(x, polyval(polyfit(x, y, 1), x), "+", x, y);
  ```

**Zadanie 3.** **Bardzo ważne zadanie:** Dany jest ciąg

```text
[9, 4, 11, 36, 85, 164, 279, 436, 641, 900]
```

Wyrazy tego ciągu zostały wygenerowane za pomocą pewnego wielomianu niewielkiego stopnia, tj. $a_n=f(n)$ dla $n=1,2,\ldots,10$, przy czym $f(n)$ jest wielomianem zmiennej $n$. Pytanie brzmi: jaki to wielomian?

- Zapoznaj się z dokumentacją funkcji `polyfit`: wpisz w Octave `help polyfit` lub zajrzyj do [dokumentacji GNU Octave](https://docs.octave.org/latest/Polynomial-Interpolation.html), a potem wykonaj odpowiednie obliczenia, używając `polyfit`.
