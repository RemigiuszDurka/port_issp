---
title: "MATLAB"
---

# MATLAB i Octave

**MATLAB** jest komercyjnym środowiskiem obliczeniowym i językiem programowania rozwijanym przez firmę MathWorks. Jest szeroko wykorzystywany w nauce, technice i zastosowaniach inżynierskich. Jest jednak oprogramowaniem komercyjnym i płatnym, choć studentom często oferowany jest bezpłatny lub ograniczony dostęp w ramach licencji uczelnianych i wersji online. 

[MATLAB](https://www.mathworks.com/products/matlab.html){ .md-button .md-button--primary }

Na tym kursie będziemy korzystać przede wszystkim z **GNU Octave** — darmowego i otwartoźródłowego środowiska do obliczeń numerycznych, którego składnia jest w dużej mierze zgodna z MATLAB-em. Dzięki temu większość podstawowych umiejętności zdobytych w Octave można później bez trudu przenieść do MATLAB-a.

[GNU Octave](https://www.gnu.org/software/octave/){ .md-button .md-button--primary }

## Związek z GNU Octave

GNU Octave jest osobnym, wolnym projektem przeznaczonym do obliczeń numerycznych. Jego składnia została zaprojektowana tak, aby duża część podstawowego kodu numerycznego była zgodna z MATLAB-em.  Na tej stronie porównujemy oba środowiska, wskazując co jest wspólne, gdzie pojawiają się różnice i jak sprawdzać przenośność kodu.

W obu środowiskach bardzo podobnie definiujemy liczby, wektory i macierze:

```matlab
x = 2;
v = [1, 2, 3, 4];
A = [1, 2; 3, 4];
```

Tak samo zapisujemy podstawowe działania macierzowe:

```matlab
A + A
A * A
A^2
```

oraz działania element po elemencie:

```matlab
v.^2
v .* v
1 ./ v
```

Wspólny jest również podstawowy sposób tworzenia zakresów, funkcji anonimowych i wykresów:

```matlab
x = linspace(0, 2*pi, 200);
f = @(x) exp(-0.1*x) .* sin(3*x);
y = f(x);

plot(x, y);
grid on;
xlabel('x');
ylabel('f(x)');
```

Podobnie działają często używane funkcje takie jak `sin`, `cos`, `exp`, `log`, `sqrt`, `sum`, `mean`, `roots`, `polyfit`, `polyval`, `plot`, `semilogx`, `semilogy` i `loglog`.

**Podobieństwo składni nie oznacza jednak pełnej zgodności.** Kod korzystający wyłącznie z podstawowych konstrukcji numerycznych bardzo często działa w obu środowiskach bez zmian, natomiast wraz ze wzrostem złożoności programu rośnie liczba miejsc, w których trzeba sprawdzić dokumentację.

## Najważniejsze różnice

| Cecha | GNU Octave | MATLAB |
| --- | --- | --- |
| Model licencyjny | wolne oprogramowanie, GNU GPL | oprogramowanie komercyjne |
| Podstawowy kurs | główne środowisko używane na tych zajęciach | środowisko dodatkowe |
| Rozszerzenia | pakiety Octave i zewnętrzne biblioteki | rozbudowany ekosystem toolboxów MathWorks |
| Składnia | obsługuje wspólną składnię oraz własne rozszerzenia | wymaga składni obsługiwanej przez MATLAB |
| Kończenie bloków | można używać m.in. `end`, ale także `endfor`, `endif`, `endfunction` | typowo używa się `end` |
| Komentarze | `%` oraz również `#` | `%` |
| Funkcje specjalistyczne | dostępność zależy od Octave i zainstalowanych pakietów | dostępność zależy od MATLAB-a i zainstalowanych toolboxów |
| Grafika i GUI | własny interfejs i system grafiki | własny interfejs, grafika i narzędzia integracyjne |

Jeżeli kod ma działać w obu środowiskach, najbezpieczniej używać **wspólnego podzbioru składni**, np. komentarzy `%` oraz zwykłego `end`, i sprawdzać dostępność bardziej specjalistycznych funkcji.

W praktyce **większość podstawowego kodu używanego na tym kursie będzie wyglądała tak samo w Octave i MATLAB-ie**. Różnice pojawiają się przede wszystkim w rozszerzeniach składni i bardziej specjalistycznych funkcjach. Kilka prostych przykładów:

| GNU Octave | MATLAB | Uwagi |
| --- | --- | --- |
| `# komentarz` | `% komentarz` | `%` działa w obu środowiskach |
| `endfor`, `endif`, `endfunction` | `end` | zwykłe `end` działa również w Octave |
| `2**3` | `2^3` | zapis z `^` działa w obu środowiskach |
| `a != b` | `a ~= b` | zapis `~=` działa również w Octave |

Dlatego podczas kursu będziemy na ogół używać takiej składni, która jest poprawna w obu programach. Pozwoli to później przenieść większość prostych skryptów z Octave do MATLAB-a bez przepisywania kodu.

## Macierzowo czy element po elemencie?

Jedna z najważniejszych wspólnych cech MATLAB-a i Octave to rozróżnienie pomiędzy algebrą macierzową a operacjami wykonywanymi element po elemencie.

```matlab
A * A      % mnożenie macierzowe
A .* A     % mnożenie element po elemencie

A^2        % potęga macierzowa
A.^2       % potęgowanie element po elemencie
```

Analogicznie rozróżniamy `/` i `./` oraz `\` i `.\`. Jest to jedna z tych części składni, które warto opanować niezależnie od tego, którego z dwóch środowisk używamy.

## Gdzie zgodność najczęściej się kończy?

Różnice stają się szczególnie istotne, gdy kod korzysta z:

- specjalistycznych toolboxów MATLAB-a lub pakietów Octave,
- bardziej zaawansowanych funkcji graficznych,
- interfejsów do sprzętu i zewnętrznego oprogramowania,
- obiektów, klas i rozbudowanych aplikacji,
- szczegółów składni specyficznych dla jednego środowiska.

## Obliczenia online

### Octave Online

**Octave Online** udostępnia GNU Octave bezpośrednio w przeglądarce. Można wpisywać polecenia w konsoli, wykonywać obliczenia i rysować wykresy.

[Uruchom Octave Online](https://octave-online.net/){ .md-button .md-button--primary }

Najprostszy test:

```octave
x = linspace(0, 2*pi, 200);
y = sin(x);
plot(x, y);
grid on;
```

### MATLAB Online

MathWorks udostępnia **MATLAB Online**. Zakres dostępu zależy od posiadanej licencji lub aktualnej oferty wersji podstawowej, dlatego bieżące limity najlepiej sprawdzać bezpośrednio na stronie MathWorks.

[Uruchom MATLAB Online](https://matlab.mathworks.com/){ .md-button .md-button--primary }
[Porównaj wersje MATLAB Online](https://www.mathworks.com/products/matlab-online/matlab-online-versions.html){ .md-button }