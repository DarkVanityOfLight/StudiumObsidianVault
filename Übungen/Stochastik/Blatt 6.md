
> Kris Grohe, Kilian Lichtner

## Aufgabe 1
_a)_
Es gibt insgesamt $n!$ viele Möglichkeiten $n$ Personen zu arrangieren. Es gibt außerdem $n$ Verschiedenen Drehungen, dadurch erhalten wir
$$\frac{n!}{n} = (n-1)!$$
_b)_

Wir können die Verschiedenen Anordnungen als Zykel betrachten

- $(1, 2, 3, 4)$
- $(2, 1, 3, 4)$
- $(3, 2, 1, 4)$
- $(4, 2, 3, 1)$
- $(1, 3, 2, 4)$
- $(1, 2, 4, 3)$

## Aufgabe 2

_a)_

Sei $c$ der Proportionalitätsfaktor dann:

$$\begin{align}
&P(1) = 1 \cdot c\\
&P(2) = 2 \cdot c\\
&P(3) = 3 \cdot c\\
&P(4) = 4 \cdot c\\
&P(5) = 5 \cdot c\\
&P(6) = 6 \cdot c
\end{align}$$

Außerdem muss gelten
$$\begin{align}
&c \cdot \sum^6_{n=1} n = 1\\
&\text{Daraus folgt}\\
&c \cdot 21 = 1\\
\iff& c = \frac{1}{21}
\end{align}$$

Damit lässt sich Berechnen
$$\begin{align}
&P(1) = 1 \cdot \frac{1}{21} = \frac{1}{21}\\
&P(2) = 2 \cdot \frac{1}{21} =  \frac{2}{21}\\
&P(3) = 3 \cdot \frac{1}{21} = \frac{3}{21}\\
&P(4) = 4 \cdot \frac{1}{21} = \frac{4}{21}\\
&P(5) = 5 \cdot \frac{1}{21} = \frac{5}{21}\\
&P(6) = 6 \cdot \frac{1}{21} = \frac{6}{21}
\end{align}$$

_b)_
Die ungeraden Zahlen von $1$ bis $6$ sind $1, 3, 5$. Dann ist die Wahrscheinlichkeit eine Ungerade Zahl zu Würfeln
$$P(1) + P(3) + P(5) = \frac{1}{21} + \frac{3}{21} + \frac{5}{21} = \frac{3}{7}$$

## Aufgabe 3

_a)_

Die Wahrscheinlichkeit in einem Wurf $1$ zu Würfeln ist $\frac{1}{n}$, die Wahrscheinlichkeit keine $1$ zu Würfeln ist dann genau die Gegenwahrscheinlichkeit also $1-\frac{1}{n}$, wir Würfeln $m$ mal also
$$\left( 1-\frac{1}{n} \right)^m$$
ist die Wahrscheinlichkeit in $m$ Würfen mit einem Würfel mit $n$ Seiten keine $1$ zu Würfeln.

_b)_

$$\begin{align}
&\lim_{n\to\infty} \left( 1 - \frac{1}{n} \right)^{n\cdot \ln(2)}\\
\iff&\lim_{n\to\infty} \exp\left(n\cdot \ln(2) \cdot \ln\left( 1 - \frac{1}{n} \right)\right)\\
\iff& \exp\left(\lim_{n\to\infty} n\cdot \ln(2) \cdot \ln\left( 1 - \frac{1}{n} \right)\right)\\
\iff& \exp\left(\ln(2) \cdot \lim_{n\to\infty} n  \cdot \ln\left( 1 - \frac{1}{n} \right)\right)\\
\iff& \exp\left(\ln(2) \cdot \lim_{n\to\infty} \frac{1}{\frac{1}{n}}  \cdot \ln\left( 1 - \frac{1}{n} \right)\right)\\
\iff& \exp\left(\ln(2) \cdot \lim_{n\to\infty} \frac{\ln\left( 1 - \frac{1}{n} \right)}{\frac{1}{n}} \right) &|\text{L'Hopital}\\
\iff& \exp\left(\ln(2) \cdot \lim_{n\to\infty} \frac{\frac{1}{(n-1) n}}{\frac{1}{n^2}} \right)\\
\iff& \exp\left(\ln(2) \cdot \lim_{n\to\infty} \frac{n^2}{ (n-1) n} \right)\\
\iff& \exp\left(\ln(2) \cdot \lim_{n\to\infty} \frac{n^2}{ n^2 - n} \right)\\
\iff& \exp\left(\ln(2) \cdot \lim_{n\to\infty} \frac{1}{ - \frac{n}{n}} \right)\\
\iff& \exp\left(\ln(2) \cdot \frac{1}{ - 1} \right)\\
\iff& \exp\left(\ln(2) \cdot -1 \right)\\
\iff& 2^{-1}\\
\iff& \frac{1}{2}
\end{align}$$




## Aufgabe 4

```ocaml
let rec all_elements (m:'a) : 'a list list  = 
  match m with
  |0 -> []
  |m -> [m]::all_elements (m-1)

let rec append_all_elements (m: int) (ms: int list list) : int list list = 
  match m with
  |0 -> []
  |m -> List.filter_map (fun sl -> if m <= (List.nth sl 0) then Some (m::sl) else None) ms @ append_all_elements (m-1) ms 


let rec multiset m n : int list list=
  match (m , n) with
  |(_, n) when n = 0 -> []
  |(m, _) when m = 0 -> raise Exit
  |(m , n) when n = 1 -> all_elements m
  |(m, n) -> append_all_elements m (multiset m (n-1));;


let m = multiset 3 3;;
print_endline (set_list_to_string m);

```

> $$\lbrace3, 3, 3\rbrace, \lbrace2, 3, 3\rbrace, \lbrace2, 2, 3\rbrace, \lbrace2, 2, 2\rbrace, \lbrace1, 3, 3\rbrace, \lbrace1, 2, 3\rbrace, \lbrace1, 2, 2\rbrace, \lbrace1, 1, 3\rbrace, \lbrace1, 1, 2\rbrace, \lbrace1, 1, 1\rbrace$$


