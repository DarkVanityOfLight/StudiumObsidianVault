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

Teilt man das Quadrat in ein Netz von $n\times n$ gleich großen Quadraten mit der Seitenlänge 1 und setzen wir $n^2 + 1$ Punkte in diese Quadrate muss einer der Punkte in ein Quadrat gesetzt werden in dem schon ein Punkt liegt, da es nur $n^2$ Felder gibt aber $n^2 + 1$ Punkte, damit ist der Abstand zwischen diesen Punkten maximal $\sqrt{1^2 + 1^2}\leq \sqrt{2}$. 


## Aufgabe 3

Ich kann maximal $n-1$ Freunde haben und da es entweder jemanden gibt der mit allen bekannt ist, oder jemanden der keine Bekanntschaft hat gibt es $n-1$ unterschiedliche "Schubfächer" an Bekanntschaften. Daher gibt es mehr "Schubfächer" als Personen($n-1 < n$) und mindestens zwei Personen müssen im selben "Fach" landen(selbe anzahl an Freundschaften).



## Aufgabe 4

### 1.
$|M| = |N|$ und $f: M\to N$

$f$ ist bijektiv, wenn für alle $m \in M$ genau ein $n\in N$ mit $f(m) = n$ existiert, $\forall n\in N: \exists_1 m \in N: f(m) = n$


Da $M$ und $N$ gleich mächtig sind und $f$ surjektiv ist, muss jedes $m\in M$ auf ein unterschiedliches $n \in N$ abgebildet werden, damit ist unsere Abbildung injektiv und da aus der surjektiv die Injektivität folgt ist sie auch bijektiv.

Da jedes $m \in M$ auf ein unterschiedliches $n \in N$ abgebildet werden muss(injektiv) und die Mächtigkeit der Zielmenge gleich der Mächtigkeit der Quelle ist muss jedes $n$ angenommen werden. Da aus der Injektivität die surjektiv folgt, ist die Abbildung bijektiv.

### 2.

$x\in \mathbb N$
Injektiv aber nicht surjektiv $f(x) = {2\over x}$
Surjektiv aber nicht Injektiv $f(x) = x^2$


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