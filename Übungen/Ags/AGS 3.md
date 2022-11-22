> Kilian Lichtner, Jannis Lauterbach

## Aufgabe 1
Vorgaben: $|N| = |M|$, $|M|, |N| < \infty$, $f: M\to N$
Behauptungen: 
a) f bijektiv 
b) f injektiv
c) f surjektiv

a, b, c äquivalent

b) $\implies$ c) f inj. -> $\forall m \in M \exists n \in N: f(m)=n \land f(m_1) \not = f(m_2)$
$|M| = |N|$, M, N endl $\implies \forall n \in N \exists m\in M : f(m) = n$

c) $\implies$ b) $f surj \implies \forall n \in N \exists m\in M: f(m) = n$
$|M| = |N|$, M, N endl ein El. hat nicht mehrere Bilder
$\implies \forall m \in M \exists n\in N: f(m) = n end f(m_1) \not = f(m_2), m_1\not = m_2 \implies f inj.$

$(c\iff b) \implies a$

## Aufgabe 2
#### a)
Da $f$ injektiv ist gilt für beliebige$\forall m_1, m_2 \in M : f(m_1) = f(m_2) \implies m_1 = m_2$ und da $g$ auch injektiv ist gilt $\forall n_1, n_2 \in N: g(n_1) = g(n_2) \implies n_1  = n_2$. $\forall m_1, m_2 \in M: (g \circ f)(m_1) = (g\circ f)(m_2) \implies h(f(m_1)) = h(f(m_2)) \implies f(m_1) = f(m_2) \implies m_1 = m_2$

#### b) f,h surejektiv $\implies$ $h\circ f$ surjektiv
$\implies f(m) = n$ und $h(n) = l$
$(h\circ f) \implies h(f(m)) = h(m) = l$


## Aufgabe 3
### a)
$g: N \to M$ ist definiert als $n \mapsto f^{-1}(n)$  falls das Urbild von  $n$ definiert ist, ansonsten ein beliebiges Element in $M$. Damit gilt $g(f(m)) = id_M$.

Seien $m_1, m_2 \in M \qquad f(m_1) = f(m_2)$ Anwendung von $g$
$g(f(m_1)) = g(f(m_2)) \implies m_1 = m_2$ da $f \circ g = id_M$

### b)
Da f surjektiv ist gilt:
$\forall n\in N \quad \exists_1 m \in M : f(m) = n$
Wahlen wir ein beliebiges aber festes $n \in N$ erhalten wir:
Da $g: N \to M$
$f(g(n)) = n = f \circ g = id_N$

$f: M \to N$ ist definiert als $m \mapsto g^{-1}(m)$ falls das Urbild von $m$ nach $N$ definiert ist, ansonsten wählen wir ein beliebiges Element in $N$. Damit gilt $f(g(n)) = id_N$



## Aufgabe 4
Wir schreiben für jede Zahl $n \leq 101$ jede mögliche länge($\leq 10$) der ab/aufsteigenden Teilfolge auf, daraus erhalten wir $10^2$ verschiedene mögliche paare aus Teilfolgen. Da wir allerdings $101$ Zahlen haben muss eine dieser Teilfolgen $11$ lang sein.


## Aufgabe 5
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