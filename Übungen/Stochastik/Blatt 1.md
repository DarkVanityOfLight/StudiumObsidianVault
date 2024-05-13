
> Kris Grohe, Kilian Lichtner
## Aufgabe 1

$$\begin{align}
&\sum^{n}_{j=0} \left( n\atop j \right)^2 \\
\iff&\sum^{n}_{j=0} \left( n\atop j \right) \cdot \left(n \atop j\right) \qquad | \text{Proposition 1.2.5}\\
\iff&\sum^{n}_{j=0} \left( n\atop j \right) \cdot \left(n \atop n - j\right) \qquad |\text{Proposition 1.2.12} \\
\iff&\left(n+n \atop n \right)\\
\iff&\left(2n \atop n\right)
\end{align}$$

## Aufgabe 2

$$
\left( (n-1)+(m-1) \atop (n-1)\right) = \left( (n-1)+(m-1) \atop (n-1)+(m-1) - (n-1)\right) = \left( (n-1)+(m-1) \atop (m-1)\right)
$$

IA: 
$$
\left( 0 + 0 \atop 0\right) = 1
$$

IV: Für ein beliebiges aber festes $m+n$ gelte $\left( (n-1)+(m-1) \atop (n-1)\right)$

IS: $m+n\mapsto m+n+1$

$$\begin{align}
\left( (n-1)+(m-1) + 1 \atop (n-1)\right) 
\end{align}$$

## Aufgabe 3

$$\begin{align}
|M_3 \cup M_5 \cup M_7 \cup M_{11}| =& |M_3| + |M_5| + |M_7|+ |M_{11}|\\
& - |M_3 \cap M_5| - |M_3 \cap M_7| - |M_3 \cap M_{11}|\\
& - |M_5 \cap M_7| - |M_5 \cap M_{11}|\\
& - |M_7 \cap M_{11}|\\
& + |M_3 \cap M_5 \cap M_7| + |M_3 \cap M_5 \cap M_{11}| \\ 
& + |M_3 \cap M_7 \cap M_{11}| + |M_7 \cap M_5 \cap M_{11} |\\
& - |M_3 \cap M_5 \cap M_7 \cap M_{11}|
\end{align}$$

Jede Menge $M_i$ enthält genau $\left\lfloor \frac{100000}{i}\right\rfloor$ Elemente.
Die Schnittmenge der Mengen $M_i\dots M_j$ enthält genau
$\left\lfloor \frac{100000}{i \cdot \dots \cdot j} \right\rfloor$ Elemente.

$|M_3| = \lfloor\frac{100000}{3}\rfloor = 33 333$
$|M_5| = \lfloor\frac{100000}{5}\rfloor = 20 000$
$|M_7| = \lfloor\frac{100000}{7}\rfloor = 14 285$
$|M_{11}| = \lfloor\frac{100000}{11}\rfloor = 9090$
$|M_3 \cap M_5| = \lfloor\frac{100000}{3\cdot 5}\rfloor = 6666$
$|M_3 \cap M_7| = \lfloor\frac{100000}{3\cdot 7}\rfloor = 4761$
$|M_3 \cap M_{11}| = \lfloor\frac{100000}{3\cdot 11}\rfloor = 3030$
$|M_5 \cap M_7| = \lfloor\frac{100000}{5\cdot 7}\rfloor = 2857$
$|M_5 \cap M_{11}| = \lfloor\frac{100000}{5\cdot 11}\rfloor = 1818$
$|M_7 \cap M_{11}| = \lfloor\frac{100000}{7\cdot 11}\rfloor = 1298$
$|M_3 \cap M_5 \cap M_7| = \lfloor\frac{100000}{3 \cdot 5 \cdot 7}\rfloor = 952$ 
$|M_3 \cap M_5 \cap M_{11}| = \lfloor\frac{100000}{3 \cdot 5 \cdot 11}\rfloor = 606$
$|M_3 \cap M_7 \cap M_{11}| = \lfloor\frac{100000}{3 \cdot 7 \cdot 11}\rfloor = 432$ 
$|M_7 \cap M_5 \cap M_{11}| = \lfloor\frac{100000}{7\cdot 5 \cdot 11}\rfloor = 259$
$|M_3 \cap M_5 \cap M_7 \cap M_{11}| = \lfloor\frac{100000}{3\cdot 5\cdot 7\cdot 11}\rfloor = 86$

$$\begin{align}
&|M_3 \cap M_5 \cap M_7 \cap M_{11}| = \\
&33333 + 20000 + 14285 + 9090  - 6666 - 4761 - 3030 -2857 - 1818 - \\
&1298 + 952 + 606 + 432 + 259 - 86\\
&= 58441
\end{align}$$


## Aufgabe 4

_a)_

$$\begin{align}
n=0 :& \lbrace \emptyset \rbrace\\

n=1 :& \lbrace\emptyset \rbrace \cup\lbrace\emptyset \cup \lbrace 1\rbrace\rbrace = \lbrace \emptyset, \lbrace 1\rbrace\rbrace\\

n=2 :& \lbrace \emptyset, \lbrace 1\rbrace\rbrace \cup \lbrace\emptyset\cup\lbrace 2\rbrace\rbrace\cup \lbrace \lbrace 1\rbrace \cup \lbrace 2\rbrace\rbrace = \lbrace \emptyset, \lbrace 1\rbrace,\lbrace 2\rbrace,\lbrace 1, 2\rbrace\rbrace\\

n=3 :&\lbrace \emptyset, \lbrace 1\rbrace,\lbrace 2\rbrace,\lbrace 1, 2\rbrace\rbrace \cup \lbrace\emptyset \cup \lbrace 3\rbrace\rbrace \cup \lbrace \lbrace 1\rbrace\cup \lbrace3\rbrace\rbrace \cup \lbrace\lbrace 2\rbrace \cup \lbrace 3\rbrace\rbrace\cup \lbrace \lbrace1, 2\rbrace\cup \lbrace 3 \rbrace\rbrace =\\& \lbrace \emptyset, \lbrace 1\rbrace, \lbrace 2\rbrace, \lbrace 3\rbrace, \lbrace 1, 2\rbrace, \lbrace  1, 3\rbrace, \lbrace 2, 3\rbrace, \lbrace 1, 2, 3 \rbrace\\

n=4 :&\lbrace\lbrace \emptyset, \lbrace 1\rbrace, \lbrace 2\rbrace, \lbrace 3\rbrace\lbrace 1, 2\rbrace, \lbrace  1, 3\rbrace, \lbrace 2, 3\rbrace, \lbrace 1, 2, 3 \rbrace\rbrace \cup \lbrace \emptyset \cup \lbrace 4 \rbrace\rbrace \cup \lbrace \lbrace 1\rbrace \cup \lbrace 4\rbrace\rbrace\\& \cup \lbrace \lbrace 2\rbrace \cup \lbrace 4\rbrace\rbrace \cup \lbrace \lbrace 3\rbrace \cup \lbrace4\rbrace\rbrace \cup \lbrace \lbrace 1, 2\rbrace \cup \lbrace 4 \rbrace\rbrace \cup \lbrace \lbrace 1, 3 \rbrace \cup \lbrace 4 \rbrace\rbrace \cup \lbrace  \lbrace 2, 3\rbrace \cup \lbrace 4 \rbrace\rbrace \\& \cup \lbrace \lbrace 1, 2, 3\rbrace \cup \lbrace 4 \rbrace\rbrace \\&= 
\lbrace\lbrace \emptyset, \lbrace 1\rbrace, \lbrace 2\rbrace, \lbrace 3\rbrace, \lbrace 4\rbrace, \lbrace 1, 2\rbrace, \lbrace  1, 3\rbrace, \lbrace 1, 4\rbrace, \lbrace 2, 3\rbrace, \lbrace 2, 4\rbrace, \lbrace 3, 4\rbrace,  \lbrace 1, 2, 3 \rbrace,\\& \lbrace 1, 2, 4\rbrace, \lbrace 2, 3, 4\rbrace, \lbrace 1, 2, 3, 4\rbrace\rbrace
\end{align}$$


_b)_

```ocaml
(* Generate all subsets from 1 to n *)
let rec subsets n =
  if n == 0 then
    [[]] (* If n is 0, return a list containing an empty list as the only subset *)
  else
    let s = subsets (n-1) in (* Recursively generate subsets for n-1 *)
    List.append s (List.map (fun l -> n::l) s) (* Append subsets of n-1 with subsets of n by adding n to each subset *)


let s = subsets 4;;


(* Make it pretty *)
let rec int_list_to_string l =
  match l with
  |[] -> ""
  |[x] -> string_of_int x
  |h::t -> string_of_int h ^ ", " ^ int_list_to_string t
;;


let rec set_list_to_string l =
  match l with
  |[] -> "{}"
  |[x] -> "{"^int_list_to_string x^"}"
  |h::t -> "{"^int_list_to_string h^"}"^ ", "^ set_list_to_string t
;;

print_string "{";
print_string (set_list_to_string s);
print_endline "}"
```

> Output
> $$\begin{align}
\{&\{\}, \{1\}, \{2\}, \{2, 1\}, \{3\}, \{3, 1\}, \{3, 2\}, \{3, 2, 1\}, \{4\}, \{4, 1\}, \{4, 2\},\\& \{4, 2, 1\}, \{4, 3\}, \{4, 3, 1\}, \{4, 3, 2\}, \{4, 3, 2, 1\}\}
\end{align}$$


## Aufgabe 5

```ocaml
let rec count_div n =
  if n = 1 then
    0
  else
    if (n mod 3 = 0) || (n mod 5 = 0) || (n mod 7 = 0) || (n mod 11 = 0)
    then  count_div (n-1) + 1 else count_div (n-1)
;;

print_endline ((string_of_int (count_div 100000)))
```

> Output
> $$58441$$

