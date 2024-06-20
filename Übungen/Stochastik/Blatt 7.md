> Kris Grohe, Kilian Lichtner
## Aufgabe 1

_a)_
Der Worst Case fuer Quicksort tritt ein wenn wir immer das kleinste/groesste Element als Pivot waehlen. Dadurch erhalten wir einen Unbalancierten Suchbaum, die Pivots sind dann:

$$[8, 10, 17, 50, 56, 58, 61, 62, 64, 67, 74, 75, 86, 87, 99]$$
und wir erhalten einen rechtsgekrümmten Baum
Was in $\sum^{14}_{i=1} i$ Vergleichen resultiert, also $105 \ge \left(15 \atop 2\right) = 105$.

_b)_
Wählen wir immer den Median haben wir einen Balancierten Suchbaum:

![Drawing 2024-06-09 18.40.16.excalidraw](Drawing%202024-06-09%2018.40.16.excalidraw.md)

Dabei benötigen wir insgesamt $34$ Vergleiche.

Zuerst vergleichen wir das Median Element mit allen anderen ($14$ vergleiche). Dann Vergleichen wir in den 2 Teilbäumen jeweils 6 Elemente mit dem Median, und dann in den letzten $4$ Teilbäumen vergleichen wir jeweils mit $2$ Elementen. Daraus erhalten wir:
$$14 + 2\cdot 6 + 4 \cdot 2 = 34 \le \lceil15 \cdot \ln(15)\rceil = 41$$

## Aufgabe 2

_a)_
Wir haben $n$ Spalten, für jede Spalte berechnen wir eine Summe von $1, \dots n$, in jeder Summe führen wir eine Multiplikation durch also, hat eine Summe $n$ Multiplikationen, dies tuen wir $n$ mal also $n^2$.

_b)_
Wir multiplizieren $n$ Spalten mit $n$ Zeilen, in jeder Multiplikation berechen wir $n$ Multiplikationen, dadurch erhalten wir $n^3$ Multiplikationen.

_c)_
Gegeben sei die resultierende Matrix $C$, sowie $A$ und $B$.
Die Vektor-Matrix Multiplikation läuft in $O(n^2)$ Multiplikationen, außerdem gilt für die $O$ notation:
$$i\cdot n^2\in O(n^2)\quad \text{für ein beliebiges aber festes } i$$

Wir wählen einen zufälligen Vektor $v \in \mathbb R^n$, und multiplizieren 
$$\begin{align}
&v \cdot A = v'\\
&v' \cdot B = v''\\
&\text{genauso gilt bei einer korrekten Matrix-Matrix}\\
&\text{multiplikation}\\
&v \cdot C = v''
\end{align}$$

Wir haben $3$ Matrix-Vektor Multiplikation also 
$3 \cdot n^2 \in O(n^2)$.

## Aufgabe 3

_a)_
```ocaml
let selectPivot l = let n = Random.int (List.length l) in
  (n, List.nth l n)

let rec removenth l n = 
  match l with
  |[] -> []
  |_:: tail when n = 0 -> tail
  |head :: tail -> head :: removenth tail (n-1)

let rec quickSort l =
  match l with
  |[] -> []
  |l -> 
      match selectPivot l with 
      |(n, pivot) ->
        match List.partition
        (fun el -> pivot > el) (removenth l n) 
        with
        |(left, right) -> quickSort left @ [pivot] @ quickSort right 

let l = quickSort [56; 64; 58; 61; 75; 86; 17; 62; 8; 50; 87; 99; 67; 10; 74];;
print_endline ("["^(int_list_to_string l)^"]")
```

> $$[8, 10, 17, 50, 56, 58, 61, 62, 64, 67, 74, 75, 86, 87, 99]$$



_b)_
```ocaml
(*
Not exactly a set but good enough, my implemenation can take numbers that appear double
*)
let rec generate_unsorted_list n =
  match n with
  |n when n=0 -> []
  |n -> Random.int 536870912 ::generate_unsorted_list (n-1) 
(*
Magic number is 2**29, with 2**30 being the largest possible number from Random.int
*)


let l1 = quickSort (generate_unsorted_list 10);;
print_endline ("["^(int_list_to_string l1)^"]");;
let l2 = quickSort (generate_unsorted_list 100);;
print_endline ("["^(int_list_to_string l2)^"]");;
let l3 = quickSort (generate_unsorted_list 1000);;
print_endline ("["^(int_list_to_string l3)^"]");;
let l4 = quickSort (generate_unsorted_list 10000);;
print_endline ("["^(int_list_to_string l4)^"]");;
(*This is the only one that actually takes time,
but ik my implementation is pretty bad*)
let l5 = quickSort (generate_unsorted_list 100000);;
print_endline ("["^(int_list_to_string l5)^"]");;
(* I will spare you the output ChungiXD *)
```


