## Aufgabe 1

## Aufgabe 2

## Aufgabe 3



## Aufgabe 4

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