## Aufgabe 1

_a)_
Der Worst Case fuer Quicksort tritt ein wenn wir immer das kleinste/groesste Element als Pivot waehlen. Dadurch erhalten wir einen Unbalancierten Suchbaum, die Pivots sind dann:

$$[8, 10, 17, 50, 56, 58, 61, 62, 64, 67, 74, 75, 86, 87, 99]$$
Was in $O(n^2)$ Vergleichen resultiert, also $15^2 = 225 > \left(15 \atop 2\right) = 105$.

_b)_
Waehlen wir immer den Median haben wir einen Balancierten Suchbaum:

![Drawing 2024-06-09 18.40.16.excalidraw](Drawing%202024-06-09%2018.40.16.excalidraw.md)


## Aufgabe 2

_a)_

Wir haben $n$ Spalten, fuer jede Spalte berechnen wir eine Summe von $1, \dots n$, in jeder Summe fuehren wir eine Multiplikation durch also, hat eine Summe eine Laufzeit von $n$, dies tuen wir $n$ mal also $n^2$.

_b)_

F