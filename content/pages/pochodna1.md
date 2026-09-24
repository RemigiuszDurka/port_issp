---
title: "Pochodna (1)"
legacy_url: "http://users.ift.uni.wroc.pl/~rdurka/matissp/index.php/pochodna1/"
---

# Pochodna (1)

Pierwsza część materiału o pochodnych.

Pochodna funkcji $f$ w punkcie $x_0$ jest granicą ilorazu różnicowego, jeśli ta granica istnieje:

$$
f'(x_0)=\lim_{x\to x_0}\frac{f(x)-f(x_0)}{x-x_0}.
$$

![Animacja: czym jest pochodna?](https://upload.wikimedia.org/wikipedia/commons/2/21/What_is_derivative_%28animation%29.gif?utm_source=pl.wikipedia.org&utm_campaign=index&utm_content=original)

## Wykład

- Materiały: [Pochodne1.pdf](../site_assets/Pochodne1.pdf)
- [Karta wzorów](../site_assets/karta_wzorow_v2.png)
- [Starsza prezentacja](../site_assets/pochodne_old.pdf)

## Wzory fundamentalne

| Funkcja | Pochodna funkcji | Przykład |
| --- | --- | --- |
| $x^\alpha$ | $\alpha x^{\alpha-1}$ | $(x^{1/2})'=\frac12x^{-1/2}$ |
| $e^x$ | $e^x$ | $(e^{2x})'=2e^{2x}$ |
| $\ln x$ | $\frac{1}{x}$ | $(\ln x)'=\frac{1}{x}$ |
| $\sin x$ | $\cos x$ | $(\sin 3x)'=3\cos 3x$ |
| $\cos x$ | $-\sin x$ | $\left(\cos \frac{x}{2}\right)'=-\frac12\sin\frac{x}{2}$ |

**Tabela 1.** Pochodne funkcji elementarnych.

| Wyrażenie | Pochodna | Przykład |
| --- | --- | --- |
| $\alpha f(x)+\beta g(x)$ | $\alpha f'(x)+\beta g'(x)$ | $(3x-5\sin x)'=3-5\cos x$ |
| $f(x)g(x)$ | $f'(x)g(x)+f(x)g'(x)$ | $(xe^x)'=e^x+xe^x$ |
| $\frac{1}{g(x)}$ | $-\frac{g'(x)}{g^2(x)}$ | $\left(\frac{1}{x^2}\right)'=-\frac{2}{x^3}$ |
| $\frac{f(x)}{g(x)}$ | $\frac{f'(x)g(x)-f(x)g'(x)}{g^2(x)}$ | $\left(\frac{x}{e^x}\right)'=\frac{1-x}{e^x}$ |
| $f(g(x))$ | $f'(g(x))\,g'(x)$ | $(\sin x^2)'=2x\cos x^2$ |
| $f^{-1}(x)$ | $(f^{-1})'(x)=\frac{1}{f'(f^{-1}(x))}$ | Dla $y=x^2$ ograniczamy dziedzinę do $x\ge 0$, więc $x=\sqrt y$ i $\frac{dx}{dy}=\frac{1}{2\sqrt y}$ |

**Tabela 2.** Podstawowe wzory na pochodne funkcji złożonych.

## Zadania do wykonania ręcznie

### **Zadanie 1.** Obliczanie pochodnych

Oblicz pochodne następujących funkcji:

1. $y(x)=-3x+3$
2. $y(x)=\pi x+\sin 1$
3. $y(x)=\sin 2$
4. $y(x)=x^7$
5. $y(x)=2x^3-3x^2+8x-9$
6. $y(x)=ax^2+2ax+a$
7. $y(x)=6x^{1/3}$
8. $y(x)=x^\pi$
9. $y(x)=\sqrt{x}$
10. $y(x)=\cos x+\sin x$
11. $y(x)=e^x$
12. $y(x)=\ln x$
13. $y(x)=2\sin x\cos x$
14. $y(x)=x\sin x$
15. $y(x)=xe^x$
16. $y(x)=\ln x\,e^x$
17. $y(x)=(x+1)(x+1)$
18. $y(x)=(x+1)e^x$
19. $y(x)=\ln(-x)$
20. $y(x)=\sin(-x)$
21. $y(x)=\sin(x^2)$
22. $y(x)=e^{-2x}$
23. $y(x)=e^{-3\sin x}$
24. $y(x)=\frac{1}{x+1}$
25. $y(x)=\frac{x}{x+1}$
26. $y(x)=\frac{1}{\sin x}$
27. $y(x)=\frac{1}{1+\sin x}$
28. $y(x)=\frac{1}{\sin(x^2)}$
29. $y(x)=\frac{1}{\sin(x^2)+1}$
30. $y(x)=\sqrt{x+1}$
31. $y(x)=\log_{10}x$
32. $y(x)=10^x$
33. $y(x)=x^x$
34. $y(x)=\arccos x$

### **Zadanie 2.** Pochodna z definicji

Policz pochodną z definicji ilorazu różnicowego dla:

- $3x+1$,
- $x^2+1$,
- stałej $a$.

### **Zadanie 3.** Położenie, prędkość i przyspieszenie

Policz ręcznie funkcję prędkości i przyspieszenia w zależności od czasu dla podanych poniżej ruchów. Jakie było położenie, prędkość i przyspieszenie w piątej sekundzie?

- $x(t)=150+50t-4.5t^2$,
- $x(t)=\sin t$,
- $x(t)=t-\frac{1}{t+1}$.

### **Zadanie 4.** Weryfikacja komputerowa ruchu

Biorąc funkcje z poprzedniego zadania, narysuj w Octave na jednym wykresie $x(t)$, $v(t)$ i $a(t)$ dla każdego przypadku. Nie zapomnij o legendzie. Czy wartości dla $t=5$ pokrywają się z ręcznymi obliczeniami?

### **Zadanie 5.** Reguła łańcuchowa

O pewnych funkcjach $f$ i $g$ wiadomo, że $g(0)=0$, $g'(0)=2$ oraz $f'(0)=4$. Ile wynosi pochodna funkcji złożonej $f(g(x))$ w punkcie $x=0$?

### **Zadanie 6.** Reguła de l’Hospitala

Korzystając z reguły de l’Hospitala, znajdź granice:

$$
\lim_{x\to 0}\frac{\sin x}{x},
$$

$$
\lim_{x\to 0}\frac{1-\cos x}{x^2},
$$

$$
\lim_{x\to 0}\frac{\sqrt{1+x}-1}{x},
$$

$$
\lim_{x\to\infty}\frac{\ln x}{x},
$$

$$
\lim_{x\to\infty}\frac{e^x}{x},
$$

$$
\lim_{x\to\infty}e^x\frac{1}{x}.
$$

### **Zadanie 7.** Kiedy nie stosować reguły de l’Hospitala?

Dlaczego reguły de l’Hospitala nie można użyć do wyznaczenia granicy

$$
\lim_{x\to 0}\frac{x+1}{x-1}\,?
$$

### **Zadanie 8.** Reguła Leibniza

Uogólnij regułę Leibniza $(fg)'=f'g+fg'$ na przypadek pochodnej iloczynu trzech funkcji: 

$$(fgh)'=\ldots$$
