> Jannis Lauterbach, Kilian Lichtner

## Aufgabe 1




$$|2^M| = 2^{|M|}$$

## Aufgabe 2

Sein $n \in \mathbb N$ und seien $n^2 + 1$ beliebige Punkte in dem Quadrat $\{(x, y) | 0 \leq x < n, 0 \leq y < n\}$

Teilt man das Quadrat in ein Netz von $n\times n$ gleich großen Quadraten mit der Seitenlänge 1. Setzen wir $n^2 + 1$ Punkte in diese Quadrate muss einer der Punkte in ein Quadrat gesetzt werden in dem schon ein Punkt liegt, damit ist der Abstand zwischen diesen Punkten $\leq \sqrt{2}$. 

## Aufgabe 3

Wie viele unterschiedlich Freundschaften sind möglich ? Weniger Freundschaften sind Möglich als es Personen gibt, also müssen mindestens 2 in der selben Kategorie landen. Da die Beziehung Symmetrisch ist fällt entweder die Kategorie keine Freunde oder n-1 Freunde weg, denn entweder ist jemand mit allen befreundet, dann gibt es niemanden der keine Freunde hat, oder es gibt nur Personen die nicht mit jedem Befreundet sind.

Kategorien:
 - Keine Freunde
 - 1 Freund
 - 2 Freunde
 - 3 Freunde


## Aufgabe 4

$|M| = |N|$ und $f: M\to N$

$f$ ist bijektiv, wenn für alle $m \in M$ genau ein $n\in N$ mit $f(m) = n$ existiert, $\forall n\in N: \exists_1 m \in N: f(m) = n$

$f$ ist injektiv wenn $m_1, m_2 \in M$ $f(m_1) = f(m_2) \implies m_1 = m_2$

$f$ ist surjektiv wenn $\forall n \in N\, \exists m \in M: f(m) = n$


## Aufgabe 5


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