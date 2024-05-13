
> Kris Grohe, Kilian Lichtner
## Aufgabe 1

_a)_
Die Anzahl an Möglichkeiten Berechnet sich wie folgt:
$$\frac{1}{n+1} \left( 2n \atop n \right)$$
für $4$ Personen mit $10$ Euro scheinen ergibt sich
$$\frac{1}{4+1}\left( 2\cdot 4 \atop 4\right) = 14$$

_b)_

Da wir wissen das $\left( n+m \atop n\right)$ die Anzahl an kürzesten Wegen von $A$ nach $B$ ist, ist zu zeigen das $\left(n+m \atop n+1\right)$ dieser Wege unterhalb der Winkelhalbierenden verlaufen.

Zuerst machen wir eine Beobachtung

$$\begin{align}
\left(n+m \atop n+1\right) = \left( n+m \atop n+m - (n+1) \right) = \left(\ n+m \atop n+m - n - 1\right) = \left( n+m \atop m-1\right)
\end{align}$$

Nach der Vandermonde Identität gilt:

$$\left(n+m \atop m-1\right) = \sum^{m-1}_{j=0} \left(n \atop j\right) \cdot \left(m \atop m-1-j\right)$$

$$\sum^{m-1}_{j=0} \left(n \atop j\right) \cdot \left(m \atop m-1-j\right)$$
gilt, da jeder Weg nach $j\times j$ sich eindeutig in die zwei Wege aus $\left( n\atop j\right)$ und $\left( m \atop m-1-j \right)$ zerlegen lässt, außerdem diese Wege kreuzen sich nicht.
$\square$

## Aufgabe 2


$$\varphi (id) = \left(\begin{array}{}
1 & 2& 3 & 4 & 5\\
1 & 2 & 3 & 4& 5
\end{array}\right)$$

$$\varphi (s_{1}) = \left(\begin{array}{}
1 & 2& 3 & 4 & 5\\
1 & 5 & 4 & 3& 2
\end{array}\right)$$

$$\varphi (s_{2}) = \left(\begin{array}{}
1 & 2& 3 & 4 & 5\\
3 & 2 & 1 & 5& 4
\end{array}\right)$$

$$\varphi (s_{3}) = \left(\begin{array}{}
1 & 2& 3 & 4 & 5\\
5 & 4 & 3 & 2& 1
\end{array}\right)$$
$$\varphi (s_{4}) = \left(\begin{array}{}
1 & 2& 3 & 4 & 5\\
2 & 1 & 5 & 4& 3
\end{array}\right)$$
$$\varphi (s_{5}) = \left(\begin{array}{}
1 & 2& 3 & 4 & 5\\
4 & 3 & 2 & 1& 5
\end{array}\right)$$

$$\varphi (r) = \left(\begin{array}{}
1 & 2& 3 & 4 & 5\\
2 & 3 & 4 & 5& 1
\end{array}\right)$$

## Aufgabe 3

_a)_
Es gibt insgesamt $4! = 24$ verschiedene Anordnungen der Adressen, $9$ davon sind Adressen bei denen keiner der Briefe eine korrekte Adresse bekommt. Die Wahrscheinlichkeit dass keiner der Empfänger den für ihn bestimmten Brief bekommt ist dann $\frac{9}{24}$.

_b)_

Sei $M_i$ die Menge aller Permutationen mit einem Fixpunkt an der Stelle $i$.

Wir wissen die Menge an Permutationen ist $n!$.

Wir suchen also 
$$n! - \left|\bigcup_{1 \leq i\leq n} M_i\right|$$

Die Siebformel ergibt für

$$\left|\bigcup_{1 \leq i\leq n} M_i\right| = \sum_{I\setminus \emptyset\subseteq\lbrace1, 2, \dots, n\rbrace} (-1)^{|I|+1} \left|\bigcap_{i\in I}  M_i\right|$$

Es gibt genau $(n-k)!$ verschiedene Permutationen mit $k$ Fixierten Elementen. 

$$\begin{align}
&\sum^n_{k=1} \sum_{I\setminus \emptyset\subseteq\lbrace1, 2, \dots, n\rbrace; |I| = k} (-1)^{|I|+1} \left|\bigcap_{i\in I}  M_i\right|\\
\iff&=\sum^n_{k=1}  (-1)^{k+1} \left( n \atop k\right) (n-k)!\\
\square
\end{align}$$

## Aufgabe 4


_a)_
Bei $n<6$ haben wir nicht die Möglichkeit alle Zahlen zu würfeln, daher ist $n$ mindestens $6$:
$6! \cdot \frac{1}{6}^6 = \frac{5}{324}$

_b)_


_c)_

```ocaml
let rec do_throws n = 
  if n = 0 then
    []
  else
    (Random.int 6) + 1 :: do_throws (n-1)

let contains_all_1_to_6 lst =
  let rec contains n = function
    | [] -> false
    | hd :: tl -> if hd = n then true else contains n tl
  in
  let rec check_all_numbers n =
    if n > 6 then true
    else if contains n lst then check_all_numbers (n + 1)
    else false
  in
  check_all_numbers 1

(*No recursion depth to deep :( *)
let do_exp i n =
  let c = ref 0 in
  for _ = 1 to i do  
    c := !c + (if contains_all_1_to_6 (do_throws n) then 1 else 0)
  done;
  (float_of_int !c) /.
  (float_of_int i);;


print_endline (string_of_float (do_exp 100000 12))

```


## Aufgabe 5

```ocaml
let rec paths n m =
  if n = 0 && m = 0 then
    [[]]
  else if n > 0 then
    let paths_down = List.map (fun p -> 1 :: p) (paths (n - 1) m) in
    if m > 0 then
      let paths_right = List.map (fun p -> 0 :: p) (paths n (m - 1)) in
      paths_down @ paths_right
    else
      paths_down
  else if m > 0 then
    List.map (fun p -> 0 :: p) (paths n (m - 1))
  else
    (* This will never happen: *)
    raise Exit

let example_paths = paths 2 3;;
List.iter (fun path -> Printf.printf "Path: %s\n" (String.concat "" (List.map string_of_int path))) example_paths
```

>Path: 11000
>Path: 10100
>Path: 10010
>Path: 10001
>Path: 01100
>Path: 01010
>Path: 01001
>Path: 00110
>Path: 00101
>Path: 00011

