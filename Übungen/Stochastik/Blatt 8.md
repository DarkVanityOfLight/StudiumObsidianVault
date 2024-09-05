
> Kris Grohe, Kilian Lichtner

## Aufgabe 1

Für die ersten $47$ Würfe gilt der folgende Gewinn im $i$ten Wurf:
$$2^i \cdot \frac{1}{2}^i$$
für die ersten $47$ Würfe insgesamt gilt also 
$$\left(\sum^{47}_{i=1} 2^i \cdot \left(\frac{1}{2}\right)^i\right)$$
Danach erhöht sich unser Gewinn nicht mehr, also im $i$ten Wurf mit $i > 47$:
$$2^{47} \frac{1}{2}^i$$
Da wir keine Maximale Anzahl an Würfen haben bekommen wir folgende Summe:
$$\sum^\infty_{i = 48} 2^{47} \frac{1}{2}^i = 2^{47}\sum^\infty_{i = 48}  \frac{1}{2}^i$$
Nach der Geometrischen Summenformel gilt dann:
$$\begin{align}
&2^{47}\sum^\infty_{i = 48}  \frac{1}{2}^i \\
\iff&2^{47} \left(\sum^\infty_{i = 0}  \frac{1}{2}^i  - \sum^{47}_{i = 1}  \frac{1}{2}^i\right)\\
\iff&2^{47} \left(\frac{1}{1 - \frac{1}{2}}  - \sum^{47}_{i = 1}  \frac{1}{2}^i\right)\\
\iff&2^{47} \left(\frac{1}{\frac{1}{2}}  - \sum^{47}_{i = 1}  \frac{1}{2}^i\right)\\
\iff&2^{47} \left(2  - \sum^{47}_{i = 1}  \frac{1}{2}^i\right) = 1
\end{align}$$

Zusammengesetzt erhalten wir:
$$\begin{align}
&\left(\sum^{47}_{i=1} 2^i \cdot \left(\frac{1}{2}\right)^i\right) + \sum^\infty_{i = 48} 2^{47} \frac{1}{2}^i\\
\iff& 47 + 1 = 48
\end{align}$$


## Aufgabe 2

```ocaml
type gamestate = | Lose | Win

let rec sevenelevensub s = 
  match (Random.int 6) + (Random.int 6) + 2 with
  |sum when sum = 7 -> Lose
  |sum when sum = s -> Win
  |_ -> sevenelevensub s

let seveneleven () = 
  match (Random.int 6) + (Random.int 6) + 2 with
  |sum when sum = 7 || sum = 11 -> Win
  |sum when sum = 2 || sum = 3 || sum = 12 -> Lose
  |sum -> sevenelevensub sum

let rec do_n_times f n =
  match n with
  |0 -> []
  |_ -> f ()::(do_n_times f (n-1))

let div n m = 
  float_of_int m /. float_of_int n

let calc_avg_win wl n =
  List.map (fun e -> match e with | Win -> 1 | Lose -> -1) wl
  |> (List.fold_left (fun acc w -> acc + w) 0) |> div n;;

```


_a)_
```ocaml
print_float(calc_avg_win (do_n_times (seveneleven) 10) 10);;
print_endline ""
```

> $0$

_b)_

```ocaml
print_float(calc_avg_win (do_n_times (seveneleven) 1000) 1000);;
print_endline ""
```

> $0.018$


## Aufgabe 3

_a)_

![Drawing 2024-06-17 11.52.04.excalidraw](Drawing%202024-06-17%2011.52.04.excalidraw.md)

_b)_

$$\frac{2}{9} \cdot 1 + \frac{1}{9} \cdot -1 + \frac{1}{4} \cdot 1 + \frac{1}{3} \cdot -1 +  \frac{1}{3} \cdot 1 + \frac{7}{18} \cdot -1 + \frac{5}{12} \cdot 1 + \frac{4}{9} \cdot -1 = -\frac{1}{18}$$

## Aufgabe 4

Sei $x\in M_1 \cup \dots\cup M_n$. Wir wollen zeigen, dass $x$ zu der rechten Seite genau mit $P(x)$ beiträgt. Angenommen $x$ liegt in genau $r$ der Mengen $M_i$, ohne Einschränkung $x\in M_1 \cap \dots \cap M_r$. Dann wird $x$ in $\sum_{|T|=k} P(M_T)$ genau $m(x) \cdot \left(r \atop k\right)$ mal gezählt, in jedem Durchschnitt von $k$ der $M_1,\dots, M_r$ genau $m(x)$ mal. Insgesamt trägt $x$ also zu der rechten Seite mit 
$$a = m(x) \cdot \sum^r_{k=1} (-1)^{k-1} \left( r\atop k\right)$$
bei. Da mit Corollar 1.2.26
$$0 = m(x) \cdot\sum^r_{k=1} (-1)^k \left(r \atop k\right) = m(x) - a$$
gilt ist $a = m(x)$.
$\blacksquare$

## Aufgabe 5

Sei $\Omega$ ein diskreter Wahrscheinlichkeitsraum mit Wahrscheinlichkeitsfunktion $m: \Omega \to \mathbb R_{\ge 0}$ und $X: \Omega \to \mathbb R$ eine Abbildung für die
$$\sum_{\omega \in \Omega} X(\omega)^2 \cdot m(\omega)$$
absolut konvergiert.

_Claim:_ $$\sum_{\omega\in\Omega} X(\omega) \cdot m(\omega)$$
absolut konvergiert.

_Beweis:_
Wir spalten die Summe in die Teile mit $|X(\omega)| \le 1$ und $|X(\omega)| > 1$ auf:

$$\begin{align}
\sum_{\omega\in\Omega \atop |X(\omega)| \le 1} X(\omega) \cdot m(\omega) +
\sum_{\omega\in\Omega \atop |X(\omega)| > 1} X(\omega) \cdot m(\omega) 
\end{align}$$


Es gilt, da $|X(\omega)| \le 1$
$$\sum_{\omega\in\Omega \atop |X(\omega)| \le 1} X(\omega) \cdot m(\omega) \le \sum_{\omega\in\Omega \atop |X(\omega)| \le 1} 1 \cdot m(\omega) = \sum_{\omega\in\Omega \atop |X(\omega)| \le 1} m(\omega)$$
 Da $m$ eine Wahrscheinlichkeitsfunktion ist gilt $\sum_{\omega\in \Omega} m(\omega) = 1$ und damit
$$\sum_{\omega\in\Omega \atop |X(\omega)| \le 1} X(\omega) \cdot m(\omega) \le \sum_{\omega\in\Omega \atop |X(\omega)| \le 1} 1 \cdot m(\omega) = \sum_{\omega\in\Omega \atop |X(\omega)| \le 1} m(\omega) \le 1$$

In der zweiten Summe gilt da $|X(\omega)| > 1$,
$$X(\omega) \le X(\omega^2)$$
Also
$$
\sum_{\omega\in\Omega \atop |X(\omega)| > 1} X(\omega) \cdot m(\omega) \le \sum_{\omega\in\Omega \atop |X(\omega)| > 1} X(\omega)^2 \cdot m(\omega) $$
Nach unserer Annahme konvergiert 
$$\sum_{\omega \in \Omega} X(\omega)^2 \cdot m(\omega)$$ und damit auch 
$$\sum_{\omega\in\Omega \atop |X(\omega)| > 1} X(\omega)^2 \cdot m(\omega)$$
nach dem Majorantenkriterium konvergiert dann auch
$$\sum_{\omega\in\Omega \atop |X(\omega)| > 1} X(\omega) \cdot m(\omega) $$

und damit, da beide Summen konvergieren auch die Gesamte Summe
$$\sum_{\omega\in\Omega} X(\omega) \cdot m(\omega)$$
$\blacksquare$
