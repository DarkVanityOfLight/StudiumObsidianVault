
## Aufgabe 1.1

Sei $M$ eine Menge. Zeigen sie für Teilmengen $A, B, C \subset M$ mit Hilfe von Venn-Diagrammen:

1. Für $\cap$ gilt:
	a) Kommutativität $A\cap B = B \cap A$
	b) Identität $A\cap M = A$
	c) Assoziativität $A\cap (B\cap C) = (A\cap B) \cap C$
2. Für $\cap$ gilt:
	a) Kommutativität $A\cup B = B\cup A$
	b) Identität $A\cup \emptyset = A$
	c) Assoziativität $A\cup (B\cup C) = (A\cup B) \cup C$
3. Für $\cap$ und $\cup$ gelten die Distributivgesetze
$$\begin{align*}
A\cap (B\cup C) &= (A\cap B) \cup (A\cap C)\\
A\cup(B\cap C) &= (A\cup) \cap (A\cup C)
\end{align*}$$
4. Vergleichen Sie mit den Rechenregeln für ganze Zahlen


## Aufgabe 1.2

Zeigen sie fuer endliche Mengen $M$ und $N$, dass

$$|M \cup N| = |M| + |N| - |M \cap N|$$
und
$$|M\times M| = |M| \cdot |N|$$

---

$$\begin{align*}
I:& |M \cup N| = |M\setminus N| + |N \setminus M| + |M\cap N|\\
II:& |M| + |N| - |M\cap N| =  |M \setminus N| + |N\setminus M| + |M\cap N|
\end{align*}$$

und
$$\begin{align*}
&|M \times N| = |M| \cdot |N|\\
&(\underbrace{\underbrace{m}_{|M|}, \underbrace{n}_{|N|}}_{\text{Möglichkeiten}}) \in M \times N
\end{align*}$$

Also gibt es $|M| \cdot |N|$ verschiedene paare.

## Aufgabe 1.3

Schreiben Sie ein Programm, das fuer eine Liste $a = (a_{1}, ..., a_{n} \in\mathbb Z^{n})$ die Summe
$$\sum\limits^{n}_{k=1} a_{k}$$
berechnet.

---

```fsharp
let rec sum (l: list<int>): int = 
	match l with
	| [] -> 0
	| head::tail -> (sum tail) + head
```

## Aufgabe 1.4

Zeigen sie mit vollständiger Induktion, dass
$$
\sum\limits^{n}_{k=1} k^{2} = \frac{n\cdot(n+1)(2n+1)}{6}
$$

für alle $n\in\mathbb N$

---


Aussage zu Beweisen:
$$A: \sum\limits^{n}_{k=1} k^{2} = \frac{n\cdot(n+1)(2n+1)}{6}$$

Induktionsanfang:

$$\sum\limits^{1}_{k=1} k^{2} = 1$$
$$\frac{1\cdot (1+1) \cdot (2\cdot 1 + 1)}{6} = 1$$

Induktionsvoraussetzung:

Sei $n$ ein beliebiges aber festes $n \in\mathbb N$. Dann gilt $A(n)$

Induktionsschritt:

$n\to n+1$

$$\begin{align*}
&\frac{(n+1)\cdot((n+1)+1)(2(n+1)+1)}{6}\\
\iff &\frac{(n+1) \cdot (n+2) \cdot (2n + 3)}{6}
\end{align*}$$

$$\begin{align*}
&\sum\limits^{n+1}_{k=1} k^{2}\\
\iff & \underbrace{\sum\limits^{n}_{k=1} k^{2}}_{\text{Induktionsvoraussetzung}} +(n+1)^{2}\\
\iff & \frac{n\cdot (n+1) (2n +1)}{6} + (n+1)^{2}\\
\iff & \frac{n\cdot (n+1) (2n +1)}{6}  + \frac{6(n+1)^{2}}{6}\\
\iff & \frac{n\cdot (n+1) (2n +1) + 6(n+1)^{2}}{6}\\
\iff & {(n+1)(n (2n+1) + 6(n+1)) \over 6}\\
\iff & {(n+1)(2n^2 +3n + 4n +6) \over 6}\\
\iff & {(n+1)(n (2n+3) + 2(2n+3)) \over 6}\\
\iff & {(n+1)(n+2)(2n+3)\over 6} \\
\end{align*}$$



## Aufgabe 1.5

Stellen Sie eine Formel für 
$$\sum\limits^{n}_{k=1}(2k-1)$$
auf und beweisen sie diese.

---


$$\begin{align*}
\sum\limits^{1}_{k=1}(2\cdot k - 1) &= 1\\
\sum\limits^{2}_{k=1}(2\cdot k - 1) &= 4\\
\sum\limits^{3}_{k=1}(2\cdot k - 1) &= 9\\
\sum\limits^{4}_{k=1}(2\cdot k - 1) &= 16\\
\end{align*}$$
Induktion:
$$
A: \sum\limits^{n}_{k=1}(2k-1) = n^{2}
$$

Induktionsanfang:

$$
\sum\limits^{1}_{k=1}(2\cdot k - 1) = 1
$$
$$1^{2} = 1$$

Induktionsvoraussetzung:

Sei $n$ ein beliebiges aber festes $n\in\mathbb N$. Dann gelte $A(n)$

Induktionsschritt:

$n\to n+1$

$$\begin{align*}
& (n+1)^2\\
\iff &n^{2}+2n +1
\end{align*}$$
$$\begin{align*}
&\sum\limits^{n+1}_{k=1}(2k - 1)\\
\iff & \underbrace{\sum\limits^{n}_{k=1} (2k -1)}_{\text{Induktionsvoraussetzung}} + (2(n+1) -1)\\
\iff & n^{2} + (2(n+1) - 1)\\
\iff & n^{2}+ 2n + 2 - 1\\
\iff  & n^{2} + 2n +1
\end{align*}$$

$\blacksquare$


## Aufgabe 1.6

Stellen Sie eine Formel für
$$\sum\limits^{n}_{k=1} k^{3}$$
auf und beweisen Sie diese.

---

$$\begin{align*}
\left(\frac{n\cdot(n+1)}{2}\right)^{3}\\
\frac{n^{3} \cdot (n+1)^{3}}{8}\\
\frac{n^{3} \cdot (n+1)^{2} \cdot (n+1)}{8}\\
\frac{n^{3} \cdot (n^{2} +2n + 1) \cdot (n+1)}{8}\\
\end{align*}$$



$$A: \frac{n^{3} \cdot (n^{2}+ 2n + 1) \cdot(n+1)}{8}$$

Induktionsanfang:

$$\sum\limits^{1}_{k=1} = k^{3} = 1$$
$$\frac{1\cdot (1 + 2 + 1) \cdot (2)}{8} = 1$$

Induktionsvoraussetzung:
Sei $n$ ein beliebiges aber festes $n\in\mathbb N$. Dann gelte $A(n)$

Induktionsschritt:
$n\to n+1$

$$\begin{align*}
&\frac{(n+1)^{3} \cdot ((n+1)^{2}+ 2(n+1) + 1) \cdot((n+1)+1)}{8}\\
\end{align*}$$
$$\begin{align*}
&\sum\limits^{n+1}_{k=1} k^{3}\\
\iff & \underbrace{\sum\limits^{n}_{k=1} k^{3}}_{\text{Induktionsvoraussetzung}} + (n+1)^3\\
\iff & \frac{n^{3} \cdot (n^{2}+ 2n + 1) \cdot(n+1)}{8} + (n+1)^3\\
\iff &\frac{n^{3} \cdot (n^{2}+ 2n + 1) \cdot(n+1)}{8} + \frac{(8(n+1)^3)}{8}\\
\iff &\frac{n^{3} \cdot (n^{2}+ 2n + 1) \cdot(n+1) + (8(n+1)^3)}{8}\\
\end{align*}$$
$\blacksquare$

## Aufgabe 1.7

Zeigen Sie für $q\in\mathbb R, q\not=1$ mit vollständiger Induktion
$$\sum\limits^{n}_{k=0} q^{k} = \frac{1- q^{n+1}}{1-q}$$

---

$$
A: \sum\limits^{n}_{k=0} q^{k} = \frac{1- q^{n+1}}{1-q}
$$

Induktionsanfang:

$$\sum\limits^{0}_{k=0} = 1$$
$$\frac{1-q^{0+1}}{1-q} = \frac{1-q}{1-q} = 1$$

Induktionsvoraussetzung:

Sei $n$ ein beliebiges aber festes $n \in\mathbb N_{0}$ und $q\in\mathbb R, q\not=1$ dann gelte $A(n)$.

Induktionsschritt:
$n\to n+1$

$$\frac{1-q^{n+2}}{ 1-q}$$

$$\begin{align*}
&\sum\limits^{n+1}_{k=0} q^{k}\\
\iff & \underbrace{\sum\limits^{n}_{k=0} q^{k}}_{Induktionsvoraussetzung} + q^{n+1}\\
\iff & \frac{1-q^{n+1}}{1-q} + q^{n+1}\\
\iff & \frac{1-q^{n+1}}{1-q} + \frac{(1-q) \cdot q^{n+1}}{1-q}\\
\iff & \frac{1-q^{n+1} + (1-q) \cdot q^{n+1}}{ 1-q}\\
\iff & \frac{1-q^{n+1} + q^{n+1} - q^{n+2}}{1-q}\\
\iff &\frac{1-q^{n+2}}{1-q}
\end{align*}$$
$\blacksquare$

## Aufgabe 1.8

Schreiben Sie eine Funktion, die rekursiv alle Teilmengen von $\lbrace{1, ..., n}\rbrace$ bestimmt.

---

```fsharp
let rec addToAll <'a>(l: List<List<'a>>) (e: 'a):List<List<'a>> =
    match l with
    | [] -> [[e]]
    | head::tail -> (e::head) :: (addToAll tail e)

let rec subsets (l: List<Nat>): List<List<Nat>> =
    match l with
    | [] -> [[]]
    | head::tail ->
        let subsetsOfTail = subsets tail
        subsetsOfTail @ (addToAll subsetsOfTail head)

```

## Aufgabe 1.9

Sei $0 < k \le n$. Zeigen Sie: Für die Anzahl $\left({n \atop k}\right)$ der k-elementigen Teilmengen einer n-elementigen Menge gilt
$$\left(n\atop k\right) = \frac{n!}{k!(n-k)!}$$
wobei $n! = 1\cdot 2\cdot ... \cdot n$

---

Zunächst zählt man alle $k$-Tupel mit paarweise verschiedenen Elementen, die sich aus der $n$-elementigen Ausgangsmenge zusammenstellen lassen. Es gibt $n$ Möglichkeiten der Wahl des ersten Tupel-Elements. Nach jeder beliebigen Wahl dieses ersten gibt es nur noch $n-1$ Wahlmöglichkeiten für das zweite Element, dach dessen Wahl nur noch $n-2$ fier das dritte usw..., bis hin zu $n-k+1$ Wahlmöglichkeiten für das $k$-te und letzte Tupel-Element. Die Anzahl aller so zusammengestellten $k$-Tupel ist als das Produkt $n\cdot(n-1) \cdot (n-2) ... (n-k +2) \cdot (n-k+1)$ von $k$ Faktoren, das sich mit Hilfe der Fakultät auch als $\frac{n!}{(n-k)!}$ notieren lässt. Nun sind aber genau je $k!$ der gezählten $k$-Tupel Permutationen voneinander und entsprechen daher ein und derselben $k$-elementigen Teilmenge. Nach Division durch diese Mehrfach Zählungen ergibt sich also tatsächlich $\frac{n!}{k!\cdot (n-k)!} = \left(n\atop k\right)$ als die gesuchte Teilmengen zahl.

## Aufgabe 1.10

Das Spiel "Die Türme von Hanoi" besteht aus $3$ Spielfeldern, auf denen $n$ Scheiben paarweise verschiedener Größe gestapelt werden können. Zu Beginn des Spiels sind alle Scheiben auf einem der Spielfelder der Größe nach zu einem Turm gestapelt. Ziel des Spiels ist, den Anfangs stapel auf ein andere Feld zu versetzen. Dazu darf in jedem Spielzug die oberste Scheibe eines beliebigen Turms auf einen anderen Turm, der keine kleinere Scheibe enthält, gelegt werden.
Geben Sie einen Algorithmus an, der dieses Spiel löst, stellen Sie eine Formel für die Anzahl der notwendigen Züge auf, und beweisen Sie diese mit vollständiger Induktion.

---



Turm verschieben(Ziel, Hilfsplatz, Startplatz)  
	Wenn wir nur 1 Scheibe auf dem Startplatz haben:
		Verschiebe sie auf den Zielplatz, Zurückgeben  
	Sonst:
		Turm mit -1 Scheiben verschieben (Hilfsplatz, Zielplatz, Startplatz)
		Bewegung von letzter Scheibe von Startplatz auf Zielplatz  
		Turm mit -1 Scheiben verschieben(Zielplatz, Startplatz, Hilfsplatz)

Die optimale Anzahl an Zügen ist $2^{n}- 1$

$$A: 2^{n} - 1 = 2\cdot A(n-1) + 1$$
Induktionsanfang:
$2^{1} - 1 = 1$
$2 \cdot 0 + 1 = 1$

Induktionsvoraussetzung:

Sei $n$ ein beliebiges aber festes $n\in\mathbb N$, dann gelte $A(n)$

Induktionsschritt:
$n\to n+1$

$2^{n+1}- 1$

$$\begin{align*}
&A(n+1) = 2 \cdot (2^{n} - 1) + 1\\
\iff & 2\cdot 2^{n} - 2+1\\
\iff & 2^{n+1} - 1
\end{align*}$$
$\blacksquare$


## Aufgabe 1.11

Schreiben Sie ein rekursives Programm, das das Spiel "Die Türme von Hanoi löst"

```fsharp
open System

let hanoi (start: Stack<int>) (hilfs: Stack<int>) (ziel: Stack<int>) =
    printfn "%A" start
    printfn "%A" hilfs
    printfn "%A" ziel
    printfn "-----------"

    if start.Count = 1 then
        ziel.Push(start.Pop())
        ()
    else
        let lastElement: int = start.Pop()
        let help = new Stack<int>()

        while start.Count > 0 do
            help.Push(start.Pop())

        while help.Count > 0 do
            start.Push(help.Pop())

        hanoi start ziel hilfs
        ziel.Push(lastElement)
        hanoi hilfs start ziel

[<EntryPoint>]
let main (argv: string[]) : int =
    let start = new Stack<int>()
    let hilfs = new Stack<int>()
    let ziel  = new Stack<int>()

    start.Push(1)
    start.Push(2)
    start.Push(3)

    hanoi start hilfs ziel

    0

```

## Aufgabe 1.12

In einem amerikanischen Stadtplan mit $n$ Avenues und $m$ Streets wollen wir von Punkt $A$ nach Punkt $B$ gehen Wie viele kürzeste Wege gibt es?
Beweisen Sie die Formel mit vollständiger Induktion nach $n+m$.

---

Induktionsbehauptung:
$$
\left(m+n \atop n\right)
$$


## Aufgabe 1.13

Geben Sie je ein Beispiel für eine Abbildung $\mathbb N \to\mathbb N$, die

1. Injektiv aber nicht surjektiv ist.
2. Surjektiv aber nicht injektiv ist.


---

1. $f(x) = x+1$
2. $f(x) = (x-1)^{2}$

## Aufgabe 1.14

Auf einem Fest treffen sich $n$ Personen. Zeigen Sie, dass zwei von diesen mit derselben Anzahl von Anwesenden bekannt sind.

---

Es gibt $n-1$ unterschiedliche "Bekanntschaftsklassen"(Schubfächer), da es entweder jemanden gibt der mit allen befreundet ist, oder jemanden der mit niemanden befreundet ist. Da es $n$ Personen gibt aber nur $n-1$ verschiedene Schubfächer müssen mindestens $2$ Personen die selbe anzahl an Personen haben

## Aufgabe 1.15

Die Komposition von Abbildungen ist assoziativ, das heißt für Abbildungen
$$M \xrightarrow{f} N \xrightarrow{g} L \xrightarrow{h} K$$
gilt
$$h\circ(g\circ f) = (h\circ g) \circ f$$

---

Falls die Aufgabenstellung ist dies zu Beweisen:



$$\begin{align*}
&h\circ (g\circ f)\\
\iff& h(g(f(x)))
\end{align*}$$
$$\begin{align*}
&(h \circ g) \circ f\\
\iff& h(g) \circ f\\
\iff& h(g(f(x)))
\end{align*}$$

---

## Aufgabe 1.16

Sei $f: M\to N$ eine Abbildung. Zeigen Sie:

1. $f$ ist injektiv genau dann, wenn es eine Abbildung $g: f(M) \to M$ gibt mit $g\circ f = id_{M}$
2. $f$ ist surjektiv genau dann, wenn es eine Abbildung $g: N\to M$ gibt mit $f\circ g = id_N$
3. $f$ ist bijektiv genau dann, wenn es eine Abbildung $g: N\to M$ gibt mit $g\circ f = id_{M}$ und $f\circ g = id_{N}$

---

1. Eine Abbildung ist genau dann injektiv wenn jedem Element in der Zielmenge genau ein Element in der Quelle zugeordnet ist. Daher muss es eine sogenannt Umkehrabbildung geben, in unserem Fall $g$ die eine Abbildung eindeutig Umkehrt(zurückführt) also insgesamt $id_{M}$ bildet
2. Eine Abbildung ist genau dann surjektiv wenn jedes Element in der Zielmenge angenommen wird. Daher muss es eine Funktion geben in unserem Fall $f$ die die Funktion $g$ wieder umkehrt also $g$ führt aus der Zielmenge eindeutig in die Quell menge und $f$ führt eindeutig zurück in die Zielmenge und wir erhalten das selbe Eingabe Element aus $N$(also $id_{N}$)
3. Aus 1. und 2. Folgt 3.

## Aufgabe 1.17

Seien $M, N$ endliche Mengen mit $|M| = |N|$ und $f: M\to N$ eine Abbildung. Zeigen Sie, dass folgende Aussagen äquivalent sind:

---

Aus Surjektiv folgt Injektiv:

Eine Abbildung ist genau dann surjektiv wenn jedes Element in der Zielmenge angenommen wird. Da die Zielmenge gleichgroß der Quell menge ist muss also jedes Element aus der Zielmenge genau einem Element der Quell Menge zugeordnet werden(injektiv).


Aus Injektiv folgt Surjektiv:

Eine Abbildung ist genau dann injektiv wenn jedem Element in der Zielmenge genau ein Element der Quell Menge zugeordnet wird. Da die Ziel und Quell menge gleich groß sind muss daher jedes Element der Zielmenge angenommen werden(injektiv)

Bijektiv:

Aus 1, 2 Folgt 3
Aus 3 Folgt und/oder 1,2

## Aufgabe 1.18

Seien die Zahlen $1, ..., 101$ in irgendeiner Reihenfolge gegeben. Zeigen Sie, dass $11$ davon aufsteigend oder absteigend sortiert sind.

Hinweis: Betrachten Sie eine geeignete Menge von Paaren und verwenden Sie das Schubfachprinzip.

---

Wir schreiben für jede Zahl $n \le 101$ jede mögliche länge ($\le 10$) der ab/aufsteigenden Teilfolge auf, daraus erhalten wir $10^{2}$ verschiedene mögliche paare aus Teilfolgen. Haben zwei Teilfolgen die gleiche länge  
können wir zwei Teilfolgen mit unterschiedlichen längen aus ihnen Bilden. Da wir allerdings $101$ Zahlen haben muss eine dieser Teilfolgen $11$ lang sein.

## Aufgabe 1.19

Sei $n \in\mathbb N$  und seien $n^{2} +1$ viele Punkte in dem Quadrat
$$\lbrace(x, y) | 0 \le x < n, 0 \le y < n\rbrace$$
gegeben. Zeigen Sie, dass es unter diesen zwei Punkte gibt, die Abstand $\le \sqrt 2$ haben.

---

Teilt man das Quadrat in ein Netz von $n\times n$ gleich großen Quadraten mit der Seitenlänge $1$ und setzen wir $n^{2} + 1$ Punkte in dieses Quadrat muss einer dieser Punkte in ein Quadrat gesetzt werden in dem schon ein Punkt liegt, da es nur $n^{2}$ Felder gibt aber $n^{2}+1$ Punkte(Schubfachprinzip). Nach Pythagoras ist der Abstand zwischen diesen Punkten maximal $\sqrt{1^{2} + 1^{2}} \le \sqrt{2}$.

## Aufgabe 1.20

Sei $M$ eine __unendliche__ Menge. Zeigen Sie:

1. Es gibt keine surjektive Abbildung $\varphi: M \to 2^{M}$
2. Es gibt keine injektive Abbildung $\psi: 2^{M} \to M$ 

---

## Aufgabe 1.21

1. Bestimmen Sie für $n=1222$ die Binärdarstellung $\phi^{-1}_{2,16}(n)$ in 16 Stellen.
2. Schreiben Sie ein Programm, das für eine beliebige natürliche Zahl $n \in\mathbb N$ die Binärdarstellung $\phi^{-1}_{2,r}(n)$ für geeignetes $r\in\mathbb N$ bestimmt.
3. Berechnen Sie in Binärdarstellung mit $8$ Stellen $101 + 88$

---

1. 
$$\begin{align*}
1222 &= 2\cdot 611 + 0\\
611 &= 2 \cdot 305 + 1\\
305 &= 2 \cdot 152 + 1\\
152 &= 2 \cdot 76 + 0\\
76 &= 2 \cdot 38 + 0\\
38 &= 2 \cdot 19 + 0\\
19 &= 2\cdot 9 + 1\\
9 &= 2 \cdot 4 + 1\\
4 &= 2 \cdot 2 +0\\
2 &= 2 \cdot 1 + 0\\
1 &= 0 \cdot 1 + 1
\end{align*}$$


$$\phi^{-1}_{2,16} = (0, 0, 0, 0, 0, 1, 0, 0, 1, 1, 0, 0, 0, 1, 1, 0)$$

2. 
```fsharp
let binaryRepresentation (n: int) : string =
    let rec binaryRepresentationHelper (n: int) (acc: string) : string =
        match n with
        | 0 -> acc
        | _ -> binaryRepresentationHelper (n / 2) (string (n % 2) + acc)
    binaryRepresentationHelper n ""

printfn "%s" (binaryRepresentation 10)

```

3. 
$101_{10} = 1\cdot 2^6 + 0\cdot 2^5 + 1\cdot 2^2$ = $1100100_2$

$88_{10} = 1\cdot 2^7 + 0\cdot 2^6 + 0\cdot 2^5 + 1\cdot 2^3 + 0\cdot 2^2 + 0\cdot 2^1 + 0\cdot 2^0$ = $01011000_2$


$1100100_2 + 01011000_2 = 100101000_2$

$$\begin{array}{}
& & 1 & 0 & 0 & 1 & 0 & 1 \\
+ & & 0 & 1 & 0 & 1 & 1 & 0 \\
\hline \\
& 1 & 0 & 0 & 1 & 0 & 1 & 0 \\ 
\end{array}$$

## Aufgabe 1.22

Seien $a, b \in \lbrace 0, 1\rbrace^{r}$ Binärzahlen in $r$ Bits.

1. Beschreiben Sie ein Verfahren, das aus $a$ und $b$ die Summe bestimmt, d.h. für minimal mögliches $s$ ein $c\in\lbrace 0, 1\rbrace^{s}$  mit 
   $$\phi_{2,s} (c) = \phi_{2,r}(a) + \phi_{2,r}(b)$$
2. Implementieren Sie ihren Algorithmus und erproben Sie ihn an Beispielen.

---
1. 
Starte von Rechts und wiederhole bis keine Stelle mehr übrig ist:
	Falls Beide Zahlen $1$ an der stelle haben:
		setze die stelle auf $0$
		Falls das carry bit gesetzt ist setze die stelle auf 1
		Setze das carry bit
	Falls eine der beiden Zahlen $0$ ist:
		Falls das carry bit gesetzt ist:
			Setze die Stelle auf $0$
			Setze das carry bit
		Sonst:
			Setze die Stelle auf 1
   Falls beide stellen $0$ sind:
	   Falls das carry bit gesetzt ist:
		   Setze die Stelle auf $1$
		Sonst:
			Setze die Stelle auf $0$
	
Starte von links:
	Falls die Stelle $0$ ist entferne sie
	Falls die Stelle $1$ ist breche ab


2. 
   ```fsharp
let binaryAddition (a: string) (b: string) : string =
    let rev a = List.rev (List.map int a)
    let padLeft l n c = List.init (n - List.length l) (fun _ -> c) @ l
    let padRight l n c = l @ List.init (n - List.length l) (fun _ -> c)
    let rec add a b carry =
        match (a, b, carry) with
        | [], [], 0 -> []
        | [], [], 1 -> [1]
        | [], b, carry -> add [0] b carry
        | a, [], carry -> add a [0] carry
        | a::at, b::bt, carry ->
            let s = a + b + carry
            s % 2 :: add at bt (s / 2)
    let len = max (String.length a) (String.length b)
    let a = padLeft (rev a) len '0'
    let b = padLeft (rev b) len '0'
    String.concat "" (List.map string (List.rev (add (rev a) (rev b) 0)))

   ```

## Aufgabe 1.23

Beschreiben Sie ein Verfahren das aus zwei Binärzahlen $a, b \in \lbrace 0, 1\rbrace^{r}$ das Produkt bestimmt, d.h. für minimal mögliches $s \in \mathbb N_{0}$ ein $c\in\lbrace 0, 1\rbrace^{s}$ mit
$$\phi_{2,s}(c) = \phi_{2,r}(a) \cdot \phi_{2,r} (b)$$
Implementieren Sie Ihren Algorithmus.

---

Starte von Rechts und wiederhole bis keine Stelle mehr übrig ist:
	Multipliziere alle zahlen der anderen Zahl mit der ersten Stelle
	Setze einen Platzhalte bevor mit der nächsten Stelle multipliziert wir

Addiere alle Listen die wir so erhalten haben mit der binär Addition aus 1.22

```fsharp
let binaryMultiplication (a: string) (b: string) : string = 
    let rec binaryMultiplicationHelper (x: string) (y: string) (z: string) : string = 
        match y with
        | "" -> z
        | _ -> 
            let a = if y.[y.Length - 1] = '1' then binaryAddition x z else ""
            binaryMultiplicationHelper (x + "0") (y.Substring(0, y.Length - 1)) a
    binaryMultiplicationHelper a b "0"

```

## Aufgabe 1.24

Sei $M := \mathbb R^{2}\setminus \lbrace 0,0\rbrace$ die Menge der Punkte der reellen Ebene ohne den $0$-Punkt. Auf $M$ definiere $(x, y) \sim (x', y')$ genau dann, wenn es eine Gerade durch $(0,0) \in\mathbb R^{2}$ gibt auf der sowohl der Punkt $(x, y)$ als auch der Punkt $(x', y')$ liegen.

1. Zeigen Sie, dass durch $\sim$   eine Äquivalenzrelation gegeben ist.
2. Finden Sie eine geometrische Darstellung der Menge der Äquivalenzklasse $M \setminus \sim$ indem Sie in jeder Äquivalenzklasse einen geeigneten Repräsentanten wählen.

---


Reflexiv:

Zu zeigen:
Für alle $(x, y) \in M$
$(x, y)\sim (x, y)$

Da  die Gerade von $(x, y)$ für ein beliebiges $(x, y) \in M$ zu $(0, 0)$ durch den Punkt $(x, y)$ geht ist die Relation reflexiv.

Transitiv:

Zu zeigen:
Für alle $(x, y), (x', y'), (a, b) \in M$
$(x, y) \sim (x', y')$ und $(x, y) \sim (a, b) \implies (x', y') \sim (a, b)$

Es existiert eine Gerade die durch $(x, y), (0, 0)$ und $(x', y')$ geht.
Außerdem existiert eine Gerade die durch $(x, y), (0, 0)$ und $(a, b)$ geht.
Da beide dieser Geraden durch den Punkt $(0, 0)$ gehen und eine Gerade durch zwei Punkte genau bestimmt werden kann, geht die Gerade $(0, 0), (x', y')$ auch durch $(a, b)$.

Symmetrisch:
Zu zeigen:
Für alle $(x, y), (x', y') \in M$
$(x, y) \sim (x', y') \implies (x', y') \sim (x, y)$
Da eine Gerade durch zwei Punkte eindeutig bestimmt ist gilt:
Die Gerade durch $(x, y), (x', y')$ ist dieselbe wie $(x', y') (x, y)$ 


Wir wählen als Repräsentanten der Äquivalenzklassen die Punkte die ein Positives $x$ haben und den Abstand $2$ zum $0$ Punkt haben also: $\sqrt{x^2 + y^2} = 2$. Damit erhalten wir einen Halbkreis um $(0,0)$ mit einem Radius von $2$

