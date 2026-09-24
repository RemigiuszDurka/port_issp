---
title: "Funkcje"
legacy_url: "http://users.ift.uni.wroc.pl/~rdurka/matissp/index.php/funkcje/"
---

# Funkcje

Funkcją nazywamy przyporządkowanie każdemu elementowi z pewnego zbioru $A$ dokładnie jednego elementu ze zbioru $B$. Zbiór $A$ nazywamy dziedziną funkcji, a zbiór $B$ przeciwdziedziną funkcji. Funkcję oznaczamy symbolem $f:A\to B$, a jej wartość w punkcie $x\in A$ zapisujemy jako $f(x)\in B$. **Zbiorem wartości** funkcji nazywamy zbiór wszystkich wartości $f(x)$ rzeczywiście przyjmowanych przez funkcję dla $x\in A$; jest on podzbiorem przeciwdziedziny $B$.

## Wykład

- Materiały: [Funkcje.pdf](../site_assets/Funkcje.pdf)
- [Starsza prezentacja](../site_assets/funkcje_old.pdf)

## Quiz

1. Na typowym wykresie $y$–$x$ (współrzędne kartezjańskie) zmienną niezależną umieszcza się zwyczajowo na osi poziomej czy pionowej?
2. Jeżeli $f:A\to B$ jest funkcją bijektywną, to $f^{-1}$ oznacza $1/f$ czy funkcję odwrotną $f^{-1}:B\to A$?
3. Wykres funkcji odwrotnej do $y(x)$ otrzymujemy, odbijając go względem prostej $y=\ldots$. Jak przy tym zamieniają się dziedzina i zbiór wartości funkcji?
4. Faktoryzacja to przekształcenie wyrażenia do postaci iloczynu czy sumy?
5. Czy różnica dwóch wielomianów stopnia $n$ (np. 2) może być wielomianem niższego stopnia niż $n$?
6. Czy iloczyn dwóch wielomianów, każdy stopnia $n$ (np. 2), może być wielomianem niższego stopnia niż $2n$?
7. Które z poniższych wielomianów na pewno mają co najmniej jeden pierwiastek rzeczywisty: dowolny wielomian 3. stopnia, dowolny wielomian 6. stopnia, czy dowolny wielomian 2015. stopnia?

## Zadania do wykonania ręcznie

**Zadanie 1.** Traktując $f:\mathbb R\to\mathbb R$, $f(x)=x$, znajdź $f^{-1}(x)$ i podaj dziedzinę oraz przeciwdziedzinę funkcji odwrotnej.

**Zadanie 2.** Traktując $f:\mathbb R\to\mathbb R$, $f(x)=-x+1$, znajdź $f^{-1}(x)$ i podaj dziedzinę oraz przeciwdziedzinę funkcji odwrotnej.

**Zadanie 3.** Niech $f:\mathbb R\setminus\{0\}\to\mathbb R\setminus\{0\}$, $f(x)=1/x$. Znajdź $f^{-1}(x)$ i podaj dziedzinę oraz przeciwdziedzinę funkcji odwrotnej.

**Zadanie 4.** Jeżeli $f(x)=x^2$, to superpozycja $f$ z samą sobą, $(f\circ f)(x)=\ldots$

**Zadanie 5.** Niech $f:\mathbb R\to\mathbb R$, $f(x)=x+1$. Wyznacz $f^{-1}$, a następnie oblicz $(f\circ f^{-1})(x)$. Podaj dziedzinę otrzymanej funkcji.

**Zadanie 6.** O wielomianie $w(x)$ wiadomo, że jego wyraz wiodący ma postać $x^5$, a jego pierwiastkami są 1, 2, 3, 4 i 5. Co to za wielomian?

**Zadanie 7.** Niech

$$
w(x)=5x^4-3x^3+2x^2-2x-1.
$$

Wyznacz:

- $w(0)=\ldots$
- $w(1)=\ldots$
- wyraz wolny tego wielomianu,
- stopień tego wielomianu,
- współczynnik liniowy tego wielomianu.

**Zadanie 8.** Niech

$$
f:[1,\infty)\to[0,\infty),
\qquad
f(x)=\sqrt{x-1}.
$$

Znajdź ręcznie funkcję odwrotną $f^{-1}$. Podaj jej dziedzinę i przeciwdziedzinę. Na jednym układzie współrzędnych narysuj obie funkcje oraz prostą $y=x$.

## Zadania do wykonania przy asyście komputera

**Zadanie 1.** Podaj funkcję odwrotną, jej dziedzinę i przeciwdziedzinę dla:

1. $f:[-3,-1]\to[-\pi,\pi]$, $f(x)=2\arcsin(x+2)$ — narysuj obie funkcje w Wolfram Alpha,
2. $f:\mathbb R\setminus\{2\}\to\mathbb R\setminus\{1\}$, $f(x)=\dfrac{x-1}{x-2}$ — narysuj obie funkcje w Octave.

**Zadanie 2.** Jaki wielomian definiuje w Octave instrukcja poniżej?

```octave
w = [3, -2, 0, 1];
```

**Zadanie 3.** Zdefiniuj w Octave dwa wielomiany,

$$
w(x)=x^2-3x+1,
\qquad
y(x)=x^3+x-1.
$$

Następnie:

1. znajdź wszystkie pierwiastki rzeczywiste $w(x)$,
2. znajdź wszystkie pierwiastki rzeczywiste $y(x)$,
3. wyznacz iloczyn $u(x)=w(x)\cdot y(x)$,
4. sprawdź, czy $w(x)\cdot y(x)=y(x)\cdot w(x)$,
5. porównaj stopień $u(x)$ ze stopniami $w(x)$ i $y(x)$,
6. znajdź wszystkie pierwiastki rzeczywiste $u(x)$ i porównaj je z pierwiastkami rzeczywistymi $w(x)$ oraz $y(x)$,
7. zastanów się, czy odpowiedzi na pytania zadane powyżej mają charakter uniwersalny,
8. narysuj wykres $y(x)$ dla $-1\le x\le 2$,
9. wykonaj ciąg powiększeń wykresu w pobliżu jego miejsca zerowego. Czy w kolejnych powiększeniach wykres zaczyna przypominać fragment linii prostej?

**Zadanie 4.** Wykres funkcji $y=x^2$ dla $-2\le x\le 2$ można w Octave utworzyć następująco:

```octave
N = 100;
x = linspace(-2, 2, N);
y = x .* x;
plot(x, y);
```

Mając wektory `x` i `y`, zamień współrzędne punktów i narysuj relację odwrotną. Dlaczego dla funkcji $y=x^2$ na przedziale $[-2,2]$ otrzymany wykres nie jest wykresem funkcji $y=f^{-1}(x)$? Jak należałoby ograniczyć dziedzinę funkcji wyjściowej, aby funkcja odwrotna istniała?

**Zadanie 5.** Za pomocą metody z poprzedniego zadania:

- narysuj wykres funkcji oraz funkcji odwrotnej do $y(x)=10^x$ i sprawdź, czy pokrywa się on z wykresem funkcji logarytmicznej $y(x)=\log_{10}x$ (`log10(x)` w Octave),
- narysuj wykres funkcji odwrotnej do $y(x)=e^x$ i sprawdź, czy pokrywa się on z wykresem funkcji logarytmicznej $y(x)=\ln x$ (`log(x)` w Octave),
- narysuj wykres funkcji odwrotnej do $y(x)=3^x$ i sprawdź, czy pokrywa się on z wykresem funkcji $y(x)=\log_3 x$ (`log(x)/log(3)` w Octave).

Dla każdej pary podaj dziedzinę i zbiór wartości funkcji wyjściowej oraz dziedzinę i zbiór wartości funkcji odwrotnej.

Przypomnienie: [wzór na zamianę podstawy logarytmów](https://en.wikipedia.org/wiki/Logarithm#Change_of_base).

**Zadanie 6.** Sprawdź działanie komend **`f(g(2))`**, **`g(f(2))`** oraz **`f(f(2))`**.

### Funkcje anonimowe w Octave

W Octave istnieje możliwość definiowania funkcji anonimowych — w pojedynczym wierszu, bez użycia słów kluczowych `function` i `endfunction` (zobacz: <http://dydmat.mimuw.edu.pl/matematyka-obliczeniowa/octave-podstawy>). Służy do tego operator `@`.

Na przykład, aby zdefiniować funkcje $f(x)=2x+1$ oraz $g(x)=x^2-1$, można użyć dwóch instrukcji:

```octave
f = @(x) 2 * x + 1;
g = @(x) x .* x - 1;
```

**Zadanie 7.** Wyświetl na jednym rysunku wykresy funkcji $f\circ f$, $f\circ g$, $g\circ f$ i $g\circ g$ dla $-2\le x\le 2$. Do wykresu trzeba zdefiniować argumenty i użyć polecenia typu:

```octave
plot(x, f(g(x)));
```
