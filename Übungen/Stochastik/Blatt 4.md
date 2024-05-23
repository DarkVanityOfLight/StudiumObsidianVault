
> Kris Grohe, Kilian Lichtner

## Aufgabe 1

_a)_
Zuerst hänge das zusätzlich Paket an jeder Partition an jeder möglichen Stelle an. Dann berechnen wir alle Partitionen von $4$ in $2$ und hängen das zusätzliche Paket als einzelnes Päckchen an jede Partition.

Wir erhalten $S(4, 3) \cdot 3 + S(4, 2)$ unterschiedliche Partitionen.

_b)_

$$S(n+1, m+1) = S(n, m) + \left((m+1)\cdot S(n, m+1)\right) $$

Sei $S_m (N_{+1}, m+1)$ die Menge der Partitionen einer Menge $N_{+1}$ mit $|N_{+1}| = n+1$ in $m+1$ nicht leere Teilmengen.

Wir bestimmen die Menge aller Partitionen von $N_{+1}$ in $m$ nicht leere Teilmengen, indem wir alle Partitionen von $N$ mit $N = n$ in $m$ nichtleere Teilmengen bestimmen und an jede ein neues Element hinzufügen, also $S_m(N, m)$. Dazu bestimmen wir alle Partitionen von $N$ in $m+1$ Teilmengen($S_m(N, m+1)$) und fügen das neue Element an allen möglichen Teilmengen hinzu, wir haben $m+1$ Teilmengen, dadurch erhalten wir $(m+1) \cdot |S_m(N, m+1)|$ neue Partitionen.

Wir erhalten also:
$$S(n+1, m+1) = |S_m(N_{+1}, m+1)| = |S_m(N, m)| + (m+1) \cdot |S_{m}(N, m+1)|$$
Die generierten Teilmengen sind disjunkt, da wir im ersten Fall das neue Element als eigene Menge hinzufügen, und im zweiten Fall in jede bestehende Menge einfügen.

$\square$

_c)_

$$\begin{align}
&S(5, 3) = S(4, 2) + 3\cdot S(4, 3)\\
&S(5, 3) = (S(3, 1) + 2 \cdot S(3, 2)) + 3\cdot (S(3, 2) + 3 \cdot S(3, 3))\\
&S(5, 3) = (S(3, 1) + 2 \cdot (S(2, 1) + 2 \cdot S(2, 2))) + 3\cdot ((S(2, 1) + 2 \cdot S(2, 2)) + 3 \cdot S(3, 3))\\
&S(5, 3) = (1 + 2 \cdot (1 + 2 \cdot 1)) + 3\cdot ((1 + 2 \cdot 1) + 3 \cdot 1)\\
&S(5, 3) = 25
\end{align}$$

## Aufgabe 2

Partition $S$:
Wenn $S = \emptyset$ return $\emptyset$
$x = S.pop()$
$S' = \text{Partition}(S\setminus \lbrace x \rbrace)$
Für jede Partition von $S'$, füge $x$ entweder als Einzelmenge hinzu oder füge $x$ zu jeder bestehenden Teilmenge in der Partition hinzu.

---
R1
Partition $\lbrace 1, 2, 3, 4\rbrace$
$x = 1$
Partition $\lbrace 2, 3, 4\rbrace$

---
R2
Partition $\lbrace 2, 3, 4\rbrace$
$x = 2$
Partition $\lbrace 3, 4\rbrace$

---
R3
Partition $\lbrace 3, 4\rbrace$
$x = 3$
Partition $\lbrace 4\rbrace$

---
R4
Partition $\lbrace 4 \rbrace$
$x=4$
Partition $\emptyset$

---
R5
Partition $\emptyset$ returns $\emptyset$

---
R4
Partition $\lbrace 4 \rbrace$ returns
$$\lbrace \lbrace 4\rbrace\rbrace$$

---
R3
Partition $\lbrace 3, 4\rbrace$ returns
$$ \lbrace\lbrace\lbrace 4\rbrace, \lbrace 3\rbrace\rbrace, \lbrace\lbrace 4, 3\rbrace\rbrace\rbrace$$

---
R2
Partition $\lbrace 2, 3, 4\rbrace$ returns
$$\lbrace \lbrace\lbrace 4, 2\rbrace,\lbrace 3 \rbrace\rbrace, \lbrace\lbrace 4 \rbrace,\lbrace 3, 2 \rbrace\rbrace, \lbrace\lbrace 4 \rbrace,\lbrace 3\rbrace, \lbrace 2\rbrace\rbrace, \lbrace \lbrace 4, 3, 2 \rbrace\rbrace, \lbrace \lbrace 4, 3 \rbrace,\lbrace 2\rbrace\rbrace\rbrace $$

---
R1
Partition $\lbrace 1, 2, 3, 4\rbrace$ returns

$$\begin{align}\lbrace
&\lbrace\lbrace 4, 2\rbrace,\lbrace 3 \rbrace, \lbrace 1\rbrace\rbrace, \lbrace\lbrace 4, 2, 1\rbrace,\lbrace 3 \rbrace\rbrace,\\
&\lbrace\lbrace 4, 2\rbrace,\lbrace 3, 1 \rbrace\rbrace,
\lbrace\lbrace 4 \rbrace,\lbrace 3, 2 \rbrace, \lbrace 1\rbrace\rbrace,\\
&\lbrace\lbrace 4 \rbrace,\lbrace 3, 2, 1 \rbrace\rbrace,
\lbrace\lbrace 4, 1 \rbrace,\lbrace 3, 2 \rbrace\rbrace,\\
&\lbrace\lbrace 4 \rbrace,\lbrace 3\rbrace, \lbrace 2\rbrace, \lbrace 1\rbrace \rbrace,
\lbrace\lbrace 4,1 \rbrace,\lbrace 3\rbrace, \lbrace 2\rbrace\rbrace,\\
&\lbrace\lbrace 4 \rbrace,\lbrace 3, 1\rbrace, \lbrace 2\rbrace\rbrace,
\lbrace\lbrace 4 \rbrace,\lbrace 3\rbrace, \lbrace 2, 1\rbrace\rbrace,\\
&\lbrace \lbrace 4, 3, 2 \rbrace, \lbrace 1\rbrace\rbrace,
\lbrace \lbrace 4, 3, 2, 1 \rbrace\rbrace,\\
&\lbrace \lbrace 4, 3 \rbrace,\lbrace 2\rbrace, \lbrace 1\rbrace\rbrace,
\lbrace \lbrace 4, 3 \rbrace,\lbrace 2, 1\rbrace \rbrace,\\
&\lbrace \lbrace 4, 3, 1 \rbrace,\lbrace 2\rbrace \rbrace,\\
\rbrace\end{align}$$

## Aufgabe 3

_a)_

Jede der drei Kanten kann einen von drei Zuständen haben:
- Pfeil im Uhrzeigersinn
- Pfeil gegen den Uhrzeigersinn
- Kein Pfeil
Die Gesamtzahl der möglichen Konfigurationen ist $3^3=27$.

Der Spieler verliert, wenn:
- Alle drei Pfeile im Uhrzeigersinn: 1 Möglichkeit
- Alle drei Pfeile gegen den Uhrzeigersinn: 1 Möglichkeit
- Zwei Pfeile im Uhrzeigersinn und einer ohne Pfeil: $\left(3 \atop 2\right) = 3$ Möglichkeiten
- Zwei Pfeile gegen den Uhrzeigersinn und einer ohne Pfeil:$\left(3 \atop  2\right) = 2$ Möglichkeiten

Insgesamt haben wir $1 + 1 + 3 + 3 = 8$ verlierende Konfigurationen.
$27 - 8 = 19$ gewinnende Konfigurationen.
Der Spieler gewinnt also mit einer Wahrscheinlichkeit von
$$\frac{19}{27}$$

_b)_

Wir schreiben das Symbol $\le$ um zwei Elemente in Relation zu setzen:

Alle Halbordnungen auf $\lbrace1,2,3\rbrace$:

1. Triviale Halbordnung: $1\le1,2\le2,3\le3$
3. $1\le2$
4. $1≤3$
5. $2\le3$
6. $1\le 2\le 3$
7. $1\le 3\le 2$
8. $2\le 1\le 3$
9. $2\le 3\le 1$
10. $3\le 1\le 2$
11. $3\le 2\le 1$
12. $1\le 2$ und $1\le 3$
13. $2\le 1$ und $2\le 3$
14. $3\le 1$ und $3\le 2$

Totalordnungen:
1. $1≤2≤3$
2. $1\le 3\le 2$
3. $2\le 1\le 3$
4. $2\le 3\le 1$
5. $3\le 1\le 2$
6. $3\le2\le 1$

## Aufgabe 4
_a)_
$$\begin{align}
&R_1 = \lbrace (1, 1), (2, 2)\rbrace\\
&R_2 = \lbrace (1,1), (2, 2), (1, 2)\rbrace\\
&R_3 = \lbrace (1, 1), (2, 2), (2, 1)\rbrace\\
&R_4 = \lbrace (1, 1), (2, 2), (1, 2), (2, 1)\rbrace
\end{align}$$

_b)_

Eine reflexive Relation auf einer $n$-elementigen Menge $M = \lbrace1, \dots, n\rbrace$, muss alle Paare $(i, i)| i\in M$ enthalten.

Die anderen Paare sind der Form $(i, j) | i, j\in M \land i\not = j$, es gibt genau $n\cdot (n-1)$ solcher Paare, da es $n$ Elemente gibt und jedes Elementen mit $n-1$ anderen in Relation gesetzt wird. Jedes dieser $n\cdot(n-1)$ Paare hat zwei Möglichkeiten, in der Relation enthalten zu sein oder nicht.
Daher gibt es $2^{n \cdot (n-1)}$ verschiedene reflexive Relationen. 
$\square$

_c)_

Eine Totalordnung auf einer Menge $M$ mit $n$ Elementen ist eine Permutation der $n$ Elemente, da in einer Totalordnung jedes Paar von Elementen vergleichbar ist

Deshalb gibt es auf einer $n$-elementigen Menge genau $n!$ Totalordnungen.

## Aufgabe 5


```ocaml
let add_all (p: 'a list list list) (e: 'a) : 'a list list list = 
  List.map (fun p -> [e]::p) p

(*Add e at all possible lists*)
let rec insert_at_all_lists (lst : 'a list list) (e : 'a) : ('a list list list) =
  match lst with
  |[] -> []
  |(hd:'a list) :: (tl:'a list list) ->
      [(e::hd) :: tl] @ List.map (fun l -> hd::l) (insert_at_all_lists tl e)

let rec partition2 n m : int list list list =
  match (n, m) with
  |(n, m) when m > n -> []
  |(n, m) when m = n -> [List.fold_left (fun acc i -> [i]::acc ) [] (range 1 n)] (* Partition m elements in m subsets *)
  |(n, m) when m = 1 -> [[range 1 n]] (* Partition n numbers into one subset *)
  |(n, m) -> let p1 = partition2 (n-1) (m-1) in let p2 = partition2 (n-1) m in
  (add_all p1 n) @ List.flatten (List.map (fun p -> insert_at_all_lists p n) p2);;

print_string "{";
List.iter (fun l -> print_string ("{"^(set_list_to_string l)^"}\n")) (partition2 5 3);;
print_endline "}"
```

$$\begin{align}\lbrace
\lbrace\lbrace5\rbrace, \lbrace4\rbrace, \lbrace1, 2, 3\rbrace\rbrace\\
\lbrace\lbrace5\rbrace, \lbrace4, 3\rbrace, \lbrace1, 2\rbrace\rbrace\\
\lbrace\lbrace5\rbrace, \lbrace3\rbrace, \lbrace4, 1, 2\rbrace\rbrace\\
\lbrace\lbrace5\rbrace, \lbrace4, 3, 2\rbrace, \lbrace1\rbrace\rbrace\\
\lbrace\lbrace5\rbrace, \lbrace3, 2\rbrace, \lbrace4, 1\rbrace\rbrace\\
\lbrace\lbrace5\rbrace, \lbrace4, 2\rbrace, \lbrace3, 1\rbrace\rbrace\\
\lbrace\lbrace5\rbrace, \lbrace2\rbrace, \lbrace4, 3, 1\rbrace\rbrace\\
\lbrace\lbrace5, 4\rbrace, \lbrace3\rbrace, \lbrace1, 2\rbrace\rbrace\\
\lbrace\lbrace4\rbrace, \lbrace5, 3\rbrace, \lbrace1, 2\rbrace\rbrace\\
\lbrace\lbrace4\rbrace, \lbrace3\rbrace, \lbrace5, 1, 2\rbrace\rbrace\\
\lbrace\lbrace5, 4\rbrace, \lbrace3, 2\rbrace, \lbrace1\rbrace\rbrace\\
\lbrace\lbrace4\rbrace, \lbrace5, 3, 2\rbrace, \lbrace1\rbrace\rbrace\\
\lbrace\lbrace4\rbrace, \lbrace3, 2\rbrace, \lbrace5, 1\rbrace\rbrace\\
\lbrace\lbrace5, 4\rbrace, \lbrace2\rbrace, \lbrace3, 1\rbrace\rbrace\\
\lbrace\lbrace4\rbrace, \lbrace5, 2\rbrace, \lbrace3, 1\rbrace\rbrace\\
\lbrace\lbrace4\rbrace, \lbrace2\rbrace, \lbrace5, 3, 1\rbrace\rbrace\\
\lbrace\lbrace5, 4, 3\rbrace, \lbrace2\rbrace, \lbrace1\rbrace\rbrace\\
\lbrace\lbrace4, 3\rbrace, \lbrace5, 2\rbrace, \lbrace1\rbrace\rbrace\\
\lbrace\lbrace4, 3\rbrace, \lbrace2\rbrace, \lbrace5, 1\rbrace\rbrace\\
\lbrace\lbrace5, 3\rbrace, \lbrace4, 2\rbrace, \lbrace1\rbrace\rbrace\\
\lbrace\lbrace3\rbrace, \lbrace5, 4, 2\rbrace, \lbrace1\rbrace\rbrace\\
\lbrace\lbrace3\rbrace, \lbrace4, 2\rbrace, \lbrace5, 1\rbrace\rbrace\\
\lbrace\lbrace5, 3\rbrace, \lbrace2\rbrace, \lbrace4, 1\rbrace\rbrace\\
\lbrace\lbrace3\rbrace, \lbrace5, 2\rbrace, \lbrace4, 1\rbrace\rbrace\\
\lbrace\lbrace3\rbrace, \lbrace2\rbrace, \lbrace5, 4, 1\rbrace\rbrace\\\rbrace
\end{align}$$
