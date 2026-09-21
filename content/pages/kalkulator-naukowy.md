---
title: "Octave jako kalkulator naukowy"
legacy_url: "http://users.ift.uni.wroc.pl/~rdurka/matissp/index.php/octave/kalkulator-naukowy/"
---

# Octave jako kalkulator naukowy

## Wyświetlanie wyniku obliczeń

Po uruchomieniu Octave w konsoli pojawia się znak zachęty (*prompt*), przy którym wpisujemy polecenia. Najczęściej ma on postać:

```text
>>
```

Octave można wykorzystać jak zaawansowany kalkulator naukowy. Wpisanie:

```octave
1/7
```

daje wynik zapisany w specjalnej zmiennej `ans`:

```text
ans = 0.14286
```

`ans` przechowuje wartość ostatniego wyrażenia, dlatego można od razu użyć jej w następnym obliczeniu:

```octave
1/ans
```

otrzymując:

```text
ans = 7
```

Spróbujmy jednak użyć nie zmiennej `ans`, lecz liczby widocznej na ekranie:

```octave
1/0.14286
```

otrzymując w krótkim formacie:

```text
ans = 6.9999
```

Wynik nie jest dokładnie równy 7. Nie ma tu sprzeczności: liczba `0.14286` jest tylko **skróconym sposobem wyświetlenia** wyniku. Zmienna `ans` przechowuje znacznie dokładniejsze **zmiennoprzecinkowe przybliżenie** liczby $1/7$, ale nie dokładną wartość matematyczną $1/7$. Liczba $1/7$ ma nieskończone rozwinięcie w używanej reprezentacji binarnej, więc komputer zapisuje ją z ograniczoną precyzją.

Aby wyświetlić więcej cyfr, użyj:

```octave
format long
1/7
```

Aby wrócić do krótszego formatu:

```octave
format short
```


To rozróżnienie jest bardzo ważne w obliczeniach numerycznych: **wartość przechowywana w pamięci i liczba cyfr pokazanych na ekranie to nie to samo**.

## Operatory arytmetyczne

| Operacja | Operator | Przykład |
| --- | --- | --- |
| potęgowanie | `**` lub `^` | `2**3`, `2^3` |
| mnożenie | `*` | `2*3` |
| dzielenie prawostronne | `/` | `1/7` |
| dzielenie lewostronne | `\` | `7\1` |
| dodawanie | `+` | `2+2` |
| odejmowanie | `-` | `3-2` |

Dla zwykłych liczb `x/y` i `y\x` są równoważne. Różnica staje się istotna przy operacjach macierzowych.

Priorytet operatorów jest standardowy: najpierw potęgowanie, potem mnożenie i dzielenie, a na końcu dodawanie i odejmowanie.

Przykład:

```octave
2 + 2^3/4
```

jest interpretowany jak:

```text
2 + ((2^3)/4)
```

## Stałe matematyczne

| Stała | Zapis w Octave | Znaczenie |
| --- | --- | --- |
| $\pi$ | `pi` | liczba pi |
| $e$ | `e` | podstawa logarytmów naturalnych |
| $i$ | `i` lub `j` | jednostka urojona |

Przykłady:

```octave
e
i*i
sqrt(-1)
log(-1)
```

Octave obsługuje liczby zespolone, dlatego pierwiastek z liczby ujemnej lub logarytm liczby ujemnej może zwrócić wynik zespolony.

## Funkcje matematyczne

Octave udostępnia m.in. funkcje `sin`, `cos`, `exp`, `sqrt`, `log`, `log10` i `factorial`.

```octave
pi^2
log10(1000)
log10(1e3)
sin(cos(sin(cos(1))))
factorial(6)
factorial(50)
log10(factorial(50))
```

Zapis `1e3` oznacza $1\times10^3$. Analogicznie `3.04e64` oznacza $3.04\times10^{64}$.

Funkcja `factorial(n)` oblicza silnię $n!$. Dla dużych wartości wynik jest zwykle wyświetlany w notacji naukowej. Przykładowo wartość `factorial(50)` jest rzędu $10^{64}$, a więc ma 65 cyfr dziesiętnych. Można to szybko ocenić za pomocą:

```octave
log10(factorial(50))
```

Argumenty funkcji trygonometrycznych podajemy domyślnie w radianach. Aby obliczyć sinus kąta $30^\circ$, można użyć:

```octave
sin(30*pi/180)
```

W kodzie Octave separatorem dziesiętnym jest kropka, np. `0.5`, a nie przecinek.

## Kończenie pracy

Program można zakończyć poleceniem:

```octave
quit
```

## Quiz

1. Co to jest znak zachęty (*prompt*)?
2. Co oznacza zmienna `ans`?
3. Dlaczego `1/ans` może dać dokładnie 7, mimo że na ekranie wcześniej widzieliśmy `ans = 0.14286`?
4. Jaka jest różnica między `format short` i `format long`?
5. Co oznaczają operatory `**`, `^`, `*`, `/`, `\`, `+` i `-`?
6. Jak zapisuje się w Octave liczby w notacji naukowej?
7. W jakich jednostkach Octave interpretuje argumenty funkcji trygonometrycznych?
8. Jak kończy się pracę z programem Octave?

## Zadania do wykonania w Octave

**Zadanie 1.** Oblicz $\sin 20^\circ$.

**Zadanie 2.** Porównaj liczby $10^{11}$ i $11^{10}$.

**Zadanie 3.** Sprawdź, że `sqrt(-1)` daje jednostkę urojoną oraz że $i^2=-1$.

**Zadanie 4.** Sprawdź, że Octave potrafi obliczać logarytmy z liczb ujemnych.
- Ile wynosi numerycznie `log(-1)`?
- Na podstawie wyniku zaproponuj dokładny wzór na $\log(-1)$.

**Zadanie 5.** Oblicz $\pi^\pi$ i wyświetl co najmniej 10 cyfr po przecinku.

**Zadanie 6.** Porównaj liczbowo $\left(1+\frac{1}{100000}\right)^{100000}$ z liczbą $e$. Jak sprawdzić, że liczby te nie są dokładnie równe?

**Zadanie 7.** Ile dokładnie jest różnych wyników losowania Lotto „6 z 49”? Wskazówka: użyj `nchoosek(49,6)`.

**Zadanie 8.** Korzystając z liczb zespolonych, sprawdź:
- ile wynosi `cos(i)`,
- czy $\sin^2(i)+\cos^2(i)=1$,
- czy $\cos(i)=(e+e^{-1})/2$.

**Zadanie 9.** Na podstawie wzoru $\cos x=\frac{e^{ix}+e^{-ix}}{2}$ oraz jedynki trygonometrycznej zaproponuj analogiczny wzór na $\sin x$ zawierający $e$ i $i$. Do ustalenia znaku wykorzystaj Octave.
