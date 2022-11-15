> Jannis Lauterbach, Kilian Lichtner

## Aufgabe 1

Starte mit der leeren Menge $\emptyset$
Nehme ein Element aus M: $\{1\}$
Vereinige die Bisherigen Teilmengen mit dem Element:
$\emptyset \cap {1} =\{1\}$
$\emptyset, \{1\}$

---

Nehme das nächste Element aus M: $\{2\}$
Vereinige die bisherigen Teilmengen mit dem Element: 
$\emptyset \cap 2$, $\{1\} \cap {2}$
$\emptyset, \{1\}, \{2\}, \{1, 2\}$

---

Nehme das nächste Element aus M: $\{3\}$
Vereinige die bisherigen mit dem Element: 
$\emptyset \cap 3, \{1\} \cap \{3\}, \{2\} \cap 3, \{1, 2\} \cap 3$

$\emptyset, \{1\}, \{2\}, \{3\}, \{1, 2\}, \{1, 3\}, \{2, 3\}, \{1, 2 ,3\}$

---

Nehme das letzte Element aus M: $\{4\}$
Vereinige die bisherigen Teilmengen mit dem Element: $\emptyset \cap \{4\}, \{1\} \cap \{4\}, \{2\} \cap 4, \{3\} \cap \{4\}, \{1, 2\} \cap \{4\}, \{1, 3\} \cap \{4\}, \{2, 3\} \cap \{4\}, \{1, 2, 3\} \cap \{4\}$
$\emptyset, \{1\}, \{2\}, \{3\}, \{4\}, \{1, 2\}, \{1, 3\}, \{1, 4\},\{2, 3\}, \{2, 4\}, \{3, 4\}, \{1, 2 ,3\},    \{1, 2, 4\}, \{1, 3, 4\}, \{2, 3, 4\}, \{1, 2, 3, 4\}$


## Aufgabe 2

Sein $n \in \mathbb N$ und seien $n^2 + 1$ beliebige Punkte in dem Quadrat $\{(x, y) | 0 \leq x < n, 0 \leq y < n\}$

Teilt man das Quadrat in ein Netz von $n\times n$ gleich großen Quadraten mit der Seitenlänge 1 und setzen wir $n^2 + 1$ Punkte in diese Quadrate muss einer der Punkte in ein Quadrat gesetzt werden in dem schon ein Punkt liegt, da es nur $n^2$ Felder gibt aber $n^2 + 1$ Punkte, damit ist der Abstand zwischen diesen Punkten $\leq \sqrt{2}$. 


## Aufgabe 3

Es sind maximal ${n^2 \over 2} - n - 1$ verschiedene Freundschaften möglich.


Wie viele unterschiedlich Freundschaften sind möglich ? Weniger Freundschaften sind Möglich als es Personen gibt, also müssen mindestens 2 in der selben Kategorie landen. Da die Beziehung Symmetrisch ist fällt entweder die Kategorie keine Freunde oder n-1 Freunde weg, denn entweder ist jemand mit allen befreundet, dann gibt es niemanden der keine Freunde hat, oder es gibt nur Personen die nicht mit jedem Befreundet sind.

Kategorien:
 - Keine Freunde
 - 1 Freund
 - 2 Freunde
 - 3 Freunde
 - n-1 Freunde




## Aufgabe 4

$|M| = |N|$ und $f: M\to N$

$f$ ist bijektiv, wenn für alle $m \in M$ genau ein $n\in N$ mit $f(m) = n$ existiert, $\forall n\in N: \exists_1 m \in N: f(m) = n$


Wenn eine Abbildung injektiv ist darf jeder Wert in der Ziel menge nur einmal angenommen werden da die beiden Mengen gleich Mächtig sind,
muss jeder Wert in der Ziel menge einmal angenommen werden. Damit ist die Funktion surjektiv. Da aus der Injektivität die Surjektivität folgt ist die Abbildung Bijektiv. Aeqivalent dazu muss die Abbildung injektiv sein wenn  sie surjektiv ist da alle Werte in der Zielmenge angenommen werden müssen und die Mächtigkeit der beiden Mengen gleich ist darf kein Zielwert zwei mal angenommen werden.


## Aufgabe 5

#### a)
Da $f$ injektiv ist gilt für beliebige$m_1, m_2 \in M : m_1 \not = m_2$
$f(m_1) \not = f(m_2) \implies n_1 \not = n_2$ und da $g$ auch injektiv ist gilt $g(n_1) \not = g(n_2) \implies l_1 \not = l_2$. Damit muss $h$ injektiv sein.

#### b)
Da $f$ surjektiv ist existiert ein $m \in M$ für das $f(m) = n$ mit einem beliebigem $n \in N$, und da $g$ auch surjektiv ist existiert ein $n\in N$ für das $g(n) = l$ mit beliebigem $l\in L$.

$$
\forall n \in N \exists m\in M : f(m) = n
$$
$$
\forall l\in L \exists n\in N : g(n) = l 
$$
$$
\implies \forall l \in L \exists m \in M : g(f(m)) = l
$$



## Aufgabe 6
```kotlin
import java.util.Stack

fun hanoi(start: Stack<Int>, hilfs: Stack<Int>, ziel: Stack<Int>){
    print(start)
    print(hilfs)
    println(ziel)
    println("-----------")
    
    if(start.size == 1) {
    	ziel.push(start.pop())
        return
    }
    
    // Wir nehmen die letzte Scheibe(die groesste aus dem Stack)
    // damit wir n-1 Scheiben verschieben koennen
    // dazu benutzen wir einen extra Hilfs stapel
    var lastElement: Int = 0
    val help = Stack<Int>()
    // 
    for(i in 0..start.size){
        // Falls wir beim letzten Element angekommen sind
        if(start.size == 1){
            // Speicher das letzte Element
            lastElement = start.pop()
            break
        }
        // Ansonsten lege die Scheibe auf unseren hilfs stack
        help.push(start.pop())
    }
    
    // Verschiebe den Stapel zurueck von unserem Hilfs stapel
    // ohne das letzte Element(die groesste Scheibe)
    for(i in 1..help.size){
        val e = help.pop()
        start.push(e)
    }
    // Da wir immer die letzte (groesste Scheibe) "liege" lassen
    // bzw aus dem stapel nehmen duerfen wir den Platz trotzdem
    // so behandeln als ob die Scheibe dort liegt(auch) wenn
    // sie im Stack nicht mehr vorhanden ist.
    
    hanoi(start, ziel, hilfs)
    ziel.push(lastElement)
    hanoi(hilfs, start, ziel)
}


fun main() {
    
    val start = Stack<Int>()
    val hilfs = Stack<Int>()
    val ziel  = Stack<Int>()
    
    
    start.push(1)
    start.push(2)
    start.push(3)
    
    
    hanoi(start, hilfs, ziel)
}
```