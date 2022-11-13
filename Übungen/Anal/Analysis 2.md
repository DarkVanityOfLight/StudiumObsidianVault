> Jannis Lauterbach, Kilian Lichtner

## Aufgabe 1

$$|2^M| = 2^{|M|}$$

## Aufgabe 2

Sein $n \in \mathbb N$ und seien $n^2 + 1$ beliebige Punkte in dem Quadrat $\{(x, y) | 0 \leq x < n, 0 \leq y < n\}$

Teilt man das Quadrat in ein Gitternetz von $n\times n$ gleich großen Quadraten mit der Seitenlänge 1. Setzen wir $n^2 + 1$ Punkte in diese Quadrate muss einer der Punkte in ein Quadrat gesetzt werden in dem schon ein Punkt liegt, damit ist der Abstand zwischen diesen Punkten $\leq \sqrt{2}$. 

## Aufgabe 3


## Aufgabe 4
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
    
    // Take the last element to not move it 
    var lastElement: Int = 0
    val help = Stack<Int>()
    
    for(i in 0..start.size){
        if(start.size == 1){
            lastElement = start.pop()
            break
        }
        
        help.push(start.pop())
    }
    
    // Move the stack back from the helper stack
    for(i in 1..help.size){
        val e = help.pop()
        start.push(e)
    }
    
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