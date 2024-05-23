
> Kris Grohe, Kilian Lichtner

## Aufgabe 1


_a)_

> [!Behauptung]
> $$\sum^n_{j=0} \left( n \atop j \right) = 2^n$$

__Beweis__:
Sei $M$ eine Menge mit $|M| = n$. $P(M)$ ist die Potenzmenge von $M$, das heißt die Menge aller Teilmengen von $M$. Wir wissen außerdem $|P(M)| = 2^{|M|} = 2^n$.

Wir schreiben $\left( M \atop j \right)$ für die Menge an $j$ Elementigen Teilmengen von $M$. Die Potenzmenge enthält alle $j$ Elementigen Teilmengen, für alle $0 \le j \le n$. Die Anzahl an Elementen in der Potenzmenge ist also

$$\left|\bigcup^n_{j=0}  \left( M \atop j\right) \right| = |P(M)| = 2^{|M|} = 2^n$$
Die einzelnen Mengen $\left( M \atop j\right)$ sind offensichtlich disjunkt, da die Elemente unterschiedliche grössen haben
$\square$

_b)_



> [!Behauptung]
> $$\sum^n_{j=0} \left( n \atop j\right)^2 = \left(2n \atop n\right)$$

__Beweis__

$$\begin{align}
&\sum^n_{j=0} \left( n \atop j\right)^2 \\
\iff&\sum^n_{j=0} \left( n \atop j\right) \cdot \left( n \atop j\right) & |\text{Proposition 1.2.5}\\
\iff& \sum^n_{j=0} \left( n \atop j\right) \cdot \left( n \atop n-j\right) &|\text{Proposition 1.2.12}\\
\iff&\left( n + n \atop n\right)\\
\iff&\left( 2n \atop n\right)\\
\end{align}$$
$\square$
## Aufgabe 2

_a)_

Sei $(p_0) \wedge (p_1,\dots, p_n) = (p_0, p_1,\dots, p_n)$
und $p_0 \wedge (p_1,\dots, p_n) = (p_0, p_1,\dots, p_n)$

$\text{partition}\;n\; m$
if $m > n$ then
	$\lbrace\rbrace$
if $m=1$ then
	{(n)}
else
	$\bigcup_{1\le c < n-(m-1)} \lbrace c \wedge p |p\in \text{partition}\; (n-c)\; (m-1)\rbrace$
	
(Sortiere die Einzellisten(lösche Duplikate))

_b)_

$\text{partition}\;7\;3$
$$\begin{align}
&\lbrace 1\wedge\text{partition}\;6\;2 \rbrace\\
\cup &\lbrace 2\wedge\text{partition}\;5\;2 \rbrace\\
\cup &\lbrace 3\wedge\text{partition}\;4\;2 \rbrace\\
\cup &\lbrace 4\wedge\text{partition}\;3\;2 \rbrace\\
\cup &\lbrace 5\wedge\text{partition}\;2\;2 \rbrace\\
\end{align}$$

---

$\text{partition}\;6\;2$
$$\begin{align}
&\lbrace 1 \wedge\text{partition}\; 5\;1\rbrace\\
\cup &\lbrace 2 \wedge\text{partition}\; 4\;1\rbrace\\
\cup &\lbrace 3 \wedge\text{partition}\; 3\;1\rbrace\\
\cup &\lbrace 4 \wedge\text{partition}\; 2\;1\rbrace\\
\cup &\lbrace 5 \wedge\text{partition}\; 1\;1\rbrace\\
=&\lbrace (1, 5), (2,4), (3, 3), (4, 2), (5, 1)\rbrace
\end{align}$$
$\text{partition}\; 5\; 2$
$$\begin{align}
&\lbrace 1 \wedge \text{partition}\; 4\; 1\rbrace\\
\cup&\lbrace 2 \wedge \text{partition}\; 3\; 1\rbrace\\
\cup&\lbrace 3 \wedge \text{partition}\; 2\; 1\rbrace\\
\cup&\lbrace 4 \wedge \text{partition}\; 1\; 1\rbrace\\
=&\lbrace (1, 4), (2, 3), (3, 2), (4, 1)\rbrace
\end{align}$$
$\text{partition}\;4\; 2$
$$\begin{align}
&\lbrace 1\wedge\text{partition}\;3\;1 \rbrace\\
\cup&\lbrace 2\wedge\text{partition}\;2\;1 \rbrace\\
\cup&\lbrace 3\wedge\text{partition}\;1\;1 \rbrace\\
=& \lbrace (1, 3), (2, 2), (3, 1) \rbrace
\end{align}$$

$\text{partition}\;3\;2$
$$\begin{align}
&\lbrace 1 \wedge\text{partition}\;2\;1\rbrace\\
&\lbrace 2 \wedge\text{partition}\; 1\; 1\\
=&\lbrace (1, 2)(2, 1) \rbrace
\end{align}$$

$\text{partition}\;2\;2$
$$\begin{align}
&\lbrace 1\wedge\text{partition}\; 1\;1 \rbrace\\
=&\lbrace(1, 1)\rbrace
\end{align}$$

---

$\text{partition}\;7\;3$

$$\begin{align}
\lbrace
&(1, 1, 5), (1, 2,4), (1, 3, 3), (1, 4, 2), (1, 5, 1)\\
&(2, 1, 4), (2, 2, 3), (2, 3, 2), (2, 4, 1)\\
&(3, 1, 3), (3, 2, 2), (3, 3, 1)\\
&(4, 1, 2)(4, 2, 1) \\
&(5, 1, 1)
\rbrace
\end{align}$$

$$\begin{align}
\lbrace
&(5, 1, 1), (4, 2, 1), (3, 3, 1)(3, 2, 2)\rbrace
\end{align}$$




## Aufgabe 3

> [!Behauptung]
> Für $n, m\in\mathbb N$ gibt es genau
> $$\left( n-1 \atop m-1\right)$$
> geordnete Zahlpartitionen von $n$ in $m$ positive Summanden.

__Beweis:__
Zuerst einige Beobachtungen:
Es gilt $m \le n$ denn, ansonsten gibt es keine Summanden in $\mathbb N$ die zu $n$ aufaddieren.

Weiterhin können wir $m < n$ betrachten, da wenn $m = n$ dann gibt es genau eine Zahlpartition und zwar $n\cdot 1$.


Sei also ohne Bedingung der Annahme $m < n$:
Es soll gelten:
$$s_1 + \dots + s_{m} = n$$

> [!Behauptung] 
> Wir wählen $s_{n-1}$ Summanden aus $\lbrace 1, \dots, n-1\rbrace$.

Wir beweisen beide Behauptungen durch Widerspruch:

- Wir wählen $s_n$ Summanden, $s_1 + \dots + s_m = n$, es gibt $n-2$ Summanden die diese Gleichung nicht erfüllen, wir wählen aus $n-1$ Summanden also gibt es genau einen Summanden $s_m = n - s_1 - \dots - s_{m - 1}$ sodass unsere Voraussetzung gilt.
- Wir wählen aus $\lbrace 1,\dots, n\rbrace$, dann könnten wir $n$ wählen und in $\mathbb N$(ohne $0$) ist $s_1 + \dots s_{m-1} + n = n$ nicht erfüllbar.

Also wählen wir aus $\lbrace  1, \dots, (n-1)\rbrace$ genau $m - 1$ Summanden aus. Was genau 
$$\left( n-1 \atop m-1\right)$$
entspricht.
$\square$
## Aufgabe 4

_a)_
$$\begin{align}
&\lbrace \lbrace 1, 2, 3,  4\rbrace\rbrace\\
&\lbrace \lbrace 1, 2, 3 \rbrace, \lbrace 4\rbrace\rbrace\\
&\lbrace \lbrace 1, 2, 4 \rbrace, \lbrace 3\rbrace\rbrace\\
&\lbrace \lbrace 1, 3, 4 \rbrace, \lbrace 2\rbrace\rbrace\\
&\lbrace \lbrace 2, 3, 4 \rbrace, \lbrace 1\rbrace\rbrace\\
&\lbrace \lbrace 1, 2 \rbrace, \lbrace 3, 4\rbrace\rbrace\\
&\lbrace \lbrace 1, 3 \rbrace, \lbrace 2, 4\rbrace\rbrace\\
&\lbrace \lbrace 1, 4 \rbrace, \lbrace 3, 2\rbrace\rbrace\\
&\lbrace\lbrace 1, 2\rbrace,\lbrace 3\rbrace,\lbrace4\rbrace\rbrace\\
&\lbrace\lbrace 1,3\rbrace, \lbrace2\rbrace,\lbrace4\rbrace\rbrace\\
&\lbrace\lbrace 1, 4\rbrace,\lbrace 2\rbrace, \lbrace 3\rbrace\rbrace\\
&\lbrace\lbrace 2, 3\rbrace,\lbrace 1\rbrace,\lbrace 4\rbrace\rbrace\\
&\lbrace\lbrace 2, 4\rbrace, \lbrace 1\rbrace,\lbrace3\rbrace\rbrace\\
&\lbrace\lbrace 3, 4\rbrace,\lbrace 1 \rbrace,\lbrace 2\rbrace\rbrace\\
&\lbrace\lbrace 1\rbrace,\lbrace 2\rbrace, \lbrace 3\rbrace,\lbrace 4\rbrace\rbrace
\end{align}$$


_b)_

>[!Behauptung]
> fuer die Anzahl $B_n$ aller Partitionen einer $n$-elementigen Menge gilt $B_0 = 1$ un
> $$B_{n+1} = \sum^{n}_{k=0} \left(n\atop k\right) B_k$$

__Beweis__
Für eine Menge mit $0$ Elementen gibt es genau eine Partition, die leere, also gilt $B_0 = 1$.

Nehmen wir also an das $B_k$ die Anzahl an Partitionen aller 
$k$-elementigen Menge beschreibt. Dann ist zu zeigen

$$B_{n+1} = \sum^{n}_{k=0} \left( n\atop k\right) B_k$$

Betrachten wir diese Formel als Mengen, $BM_k$ beschreibt nun also die Menge aller Partitionierungen mit $k$ Elementen. Sei $M$ eine
$n$-elementige Menge.

$$
B_{n+1} = \left|BM_{n+1}\right| = \left|\bigcup^n_{k=0} \left(M \atop k\right) \times BM_k\right|
$$
Wir erhalten alle möglichen Teilmengen von $M$ mit größe $k$ und fügen diese an jede Partitionierung an, dadurch erhalten wir per Konstruktion alle neuen möglichen Partitionierung.

Nun ist noch zu zeigen das die generierten Mengen disjunkt sind:
Da die von $\left( M \atop k\right)$ generierten Mengen disjunkt sind und die in $B_k$ enthaltenen Mengen disjunkt sind ist auch $\left(M\atop k\right) \times BM_k$ disjunkt. Da wir in jedem Schritt größere Mengen generieren sind auch diese disjunkt.
$\square$


_c)_

$$\begin{align}
&B_{0} = 1\\
&B_{0 + 1} = 1\cdot \left( 0\atop 0\right) = 1\\
&B_{1 + 1} = 1\cdot \left(1\atop 0\right) + 1\cdot\left( 1 \atop 1\right)  = 2\\
&B_{2 + 1} = 1\cdot \left( 2 \atop 0 \right) + 1\cdot \left( 2 \atop 1 \right) + 2\cdot\left( 2 \atop 2 \right) = 5\\
&B_{3 + 1} = 1\cdot \left( 3 \atop 0 \right) + 1\cdot \left( 3 \atop 1 \right) + 2\cdot\left( 3 \atop 2 \right) + 5 \cdot \left( 3 \atop 3\right)= 15\\

\end{align}$$



## Aufgabe 5

```ocaml

let append_all (l: 'a list list) (e: 'a) = List.map (fun l -> e::l) l

let rec range i j = 
  if i = j then
    [i]
  else
    i :: range (i+1) j

let rec partition (n:int) (m: int) = 
  match (n, m) with
  |(n, m) when m > n -> []
  |(n, m) when m = 1 -> [[n]]
  |(n, m) ->  List.flatten 
    (List.map (
        fun c -> append_all (partition (n-c) (m-1)) c )
        (range 1 (n-(m-1))))
;;

(* Modify our to string function from the first sheet*)
let rec partition_list_to_string l =
  match l with
  |[] -> "()"
  |[x] -> "("^int_list_to_string x^")"
  |h::t -> "("^int_list_to_string h^")"^ ", "^ partition_list_to_string t
;;

let partitions = partition 7 3;;
print_string "{";
print_string (partition_list_to_string partitions);
print_endline "}"
```

> Output:
> $$\begin{align}
&\lbrace
(1, 1, 5), (1, 2, 4), (1, 3, 3), (1, 4, 2), (1, 5, 1),\\
&(2, 1, 4), (2, 2, 3), (2, 3, 2), (2, 4, 1), (3, 1, 3),\\
&(3, 2, 2), (3, 3, 1), (4, 1, 2), (4, 2, 1), (5, 1, 1)
 \rbrace\end{align}$$

