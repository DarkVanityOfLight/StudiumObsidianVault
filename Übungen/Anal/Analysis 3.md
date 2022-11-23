## Aufgabe 1

### a)

$$\begin{align}
&M = \{1, 2, 3, 4, 5, 6, 7, 8\}\\
&N = \{a, b, c, d, e, f, g, h\}\\

&\phi_{2, |M \times N|}^{-1}(\underbrace{1, 1, 1, 1, ..., 1}_{|M \times N|}) = 1\cdot2^0 +1\cdot 2^1 + ... + 2^{|M\times N|-1}\\
&\sum^n_{k=0} 2^k = 2^{n} -1\\
&= 2^{|M\times N|} -1\\
&= 2^{64} - 1\\
&= 18446744073709551616 -1\\
&= 18446744073709551615\\
\end{align}$$

### b)
$$\begin{align}
n \in \mathbb N_0\qquad 1 \not = \lambda \in \mathbb R\\
A(n) = \sum^{n}_{k=0} \lambda^k = {1-\lambda^{n+1} \over 1 -\lambda}
\end{align}$$
IA:
$$\begin{align}
&n = 0\\
&1 \not = \lambda \in \mathbb R\\
&\sum^{0}_{k=0} \lambda^0 = {1 - \lambda^{1} \over 1 -\lambda} \\
&1 = {1 - \lambda \over 1 - \lambda}\\
& 1 = 1
\end{align}$$

IV: Für ein beliebiges aber festes $n \in \mathbb N_0$ und ein beliebiges aber festes $1 \not = \lambda \in \mathbb R$gelte $A(n)$
IB: $A(n+1) = {1 - \lambda^{n+2} \over 1 - \lambda}$
IS: 
$$\begin{align}
&n \to n+1 \\
&\sum^{n+1}_{k=0} \lambda^{k}\\
=&\underbrace{\sum^{n}_{k=0} \lambda^{k}}_{IV} + \lambda^{n+1}\\
=& {1 - \lambda^{n+1} \over 1 -\lambda} + \lambda^{n+1}\\
=& {1-\lambda^{n+1} \over 1 - \lambda} + {\lambda^{n+1} \cdot (1 - \lambda) \over 1-\lambda}\\
=& {1 - \lambda^{n+1} \over 1-\lambda} + {\lambda^{n+1} - \lambda^{n+2} \over1 - \lambda}\\
=& 1 - \lambda^{n+2}\over 1 - \lambda\\
\blacksquare
\end{align}$$

## Aufgabe 2
### a)

#### Reflexiv:

Zu zeigen:
Für alle $(x, y) \in M$
$(x, y)\sim (x, y)$

Da  die Gerade von $(x, y)$ für ein beliebiges $(x, y) \in M$ zu $(0, 0)$ durch den Punkt $(x, y)$ geht ist die Relation reflexiv.

#### Transitiv:

Zu zeigen:
Für alle $(x, y), (x', y'), (a, b) \in M$
$(x, y) \sim (x', y')$ und $(x, y) \sim (a, b) \implies (x', y') \sim (a, b)$

Es existiert eine Gerade die durch $(x, y), (0, 0)$ und $(x', y')$ geht.
Ausserdem existiert eine Gerade die durch $(x, y), (0, 0)$ und $(a, b)$ geht.
Da beide dieser Geraden durch den Punkt $(0, 0)$ gehen und eine Gerade durch zwei Punkte genau bestimmt werden kann, geht die Gerade $(0, 0), (x', y')$ auch durch $(a, b)$.

#### Symmetrisch:
Zu zeigen:
Für alle $(x, y), (x', y') \in M$
$(x, y) \sim (x', y') \implies (x', y') \sim (x, y)$
Da eine Gerade durch zwei Punkte eindeutig bestimmt ist gilt:
Die Gerade durch $(x, y), (x', y')$ ist dieselbe wie $(x', y') (x, y)$ 

### b)
![2022-11-22-201431_317x280_scrot](2022-11-22-201431_317x280_scrot.png)

Wir wählen als Represäsentanten der Äquivalenzklassen die Punkte die ein Positives $x$ haben und den Abstand $2$ zum $0$ Punkt haben also: $\sqrt{x^2 + y^2} = 2$

## Aufgabe 3

### a)
$g: N \to M$ ist definiert als $n \mapsto f^{-1}(n)$  falls das Urbild von  $n$ definiert ist, ansonsten ein beliebiges Element in $M$. Damit gilt $g(f(m)) = id_M$.

Seien $m_1, m_2 \in M \qquad f(m_1) = f(m_2)$ Anwendung von $g$
$g(f(m_1)) = g(f(m_2)) \implies m_1 = m_2$ da $f \circ g = id_M$

### b)
Definiere $g$ als $g(n) = m_n$ wobei $m_n$ definiert durch $f(m_n) = n$
Dann gilt $f \circ g(n) = f(m_n) = n \implies f \circ g = id_N$

Sei $g: N \to M$ mit $f\circ g = id_N$ 
Dann gilt $f \circ g(N) = N \implies f(M) = N$

## Aufgabe 4
### a)
$$\begin{align}
\phi^{-1}_{2, 16}(1009)= (0000001111110001)
\end{align}$$

### b)
Fülle beide Zahlen mit 0 auf die Gleiche länge

Setze carry auf 0
Gehe von Rechts nach Links durch beide Zahlen
Sind beide Stellen 1 und das carry bit 0 setze die momentane stelle auf 0 und setze das carry bit auf 1
Sind beide Stellen 1 und das carry bit 1 setze die momentane stelle auf 1
Sind beide Stellen 0 und das carry bit 1 setze die Stelle auf 1 und das carry bit auf 0
Ist eine Stelle 1 und das carry 1 setze die Stelle auf 1
Ist eine Stelle 1 und das carry 0 setze die Stelle auf 1

Falls das carry bit gesetzt ist füge eine Stelle hinzu und setze sie auf 1

Gehe von Links nach Rechts bis wir auf eine 1 treffen
Kürze die Zahl von links um 1

## Aufgabe 5
```python
# a)
dec = 12 # Eingabe von der Dezimalzahl
binNum = [] # List für die Binärzahl
def toBinary(n): # Rekursive Funktion für Dezimal- zu Binärzahl
    if n >= 1: # Ausführen solang n (Deziamlzahl) nicht >= 1 ist
        toBinary(n // 2) # Erneutes Aufrufen der Funktion mit der 
    binNum.append(n % 2) # Auflistungen der "Zwischenergebnisse"

toBinary(dec) # Funktionsaufruf mit der Dezimalzahl als Eingabe
print("".join(str(e) for e in binNum)) # Ausgabe der Binärzahl

def addBinary(bin1,bin2):

    maxLength = max(len(bin1), len(bin2))
    bin1 = bin1.zfill(maxLength)
    bin2 = bin2.zfill(maxLength)

    extra = 0
    summe = ""

    for i in range(maxLength - 1, -1, -1):
        n = extra
        if bin1[i] == "1":
            n += 1
        else:
            0
        if bin2[i] == "1":
            n += 1
        else:
            0
        summe = ("1" if n % 2 == 1 else "0") + summe
        extra = 0 if n < 2 else 1
    
    if extra != 0:
        summe = "1" + summe

    summe.zfill(maxLength)
    
    for x in range(1, len(summe), 1):
        if summe[x] == "1":
            summe = summe[x:]
            break
            
    return summe

print(addBinary("00001111", "0101"))
```