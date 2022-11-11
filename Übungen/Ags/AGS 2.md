> Jannis Lauterbach, Kilian Lichtner
## Aufgabe 1
$\alpha$. $(A \land \neg C) \implies \neg B$ : Wenn der Herbst Sonnig ist und der Ertrag nicht gering ist, dann ist der Wein nicht teuer.

$\beta$. $(\neg A \lor B) \implies \neg C$ : Wenn der Herbst nicht Sonnig ist oder der Wein teuer ist dann ist der Ertrag nicht gering.

$\gamma$. $\neg(\neg A) \implies \neg C \land \neg B$: Wenn der Herbst (nicht nicht)sonnig ist dann  ist der Ertrag nicht gering und der Wein ist nicht teuer.

Da der Ertrag hoch ist wenn die Weinreben genug Sonne bekommen, dadurch kann dann der Preis gesenkt werden und somit ist der Wein nicht teuer.

---

## Aufgabe 2
IB:
$$A:
\sum^{n}_{k=1}(6k -1) = 6\cdot\left({n(n+1) \over2}\right) -n
$$
IA:
$$\begin{align}
A(1) &= 6*1 -1 &=& 6\left({1(1+1) \over 2}\right) -1\\
&=  5 &=& 5
\end{align}$$

IV:
Für ein $n \in \mathbb N$ gelte $A(n)$

IS: $n \to n+1$
$$\begin{align}
&\sum^{n+1}_{k=1} (6k -1)\\
=& \underbrace{\sum^{n}_{k=1} (6k-1)}_{IV} + (6(n+1)-1)\\
=& {6n(n+1) \over 2} - n + (6(n+1) -1)\\
=& n(6n+6) -2n+2(6(n+1)-1) \over 2\\
=&n(6n+6) -2n + 2(6n +6 -1)\over 2 \\
=& 6n^2 + 6n -2n +12n + 12-2 \over 2\\
=& {6n^2 +6n-2n+12+12n-2 \over 2}\\
=&6n^2 + 6n +12n +12 -2n -2 \over 2\\
=& {6n^2 + 6n+12n +12 \over 2} - {2(n+1)\over 2}\\
=&{6(n^2 +n + 2n + 2) \over 2} - (n+1)\\
=&{6(n+1)(n+2) \over 2} - (n+1)\\
\square
\end{align}$$
---

## Aufgabe 3
$$\begin{align}
&\prod_{k=1}^{n}2^k  \\
=& 2^1 \cdot ... \cdot2^n\\
=&2^{1+...+n}\\
=&2^{n(n+1) \over 2}
\end{align}$$

---

## Aufgabe 4

Turm verschieben(Zielplatz, Hilfsplatz, Startplatz):
    Wenn wir nur 1 Scheibe auf dem Startplatz haben verschiebe sie auf den Zielplatz, Zurückgeben
    Turm mit -1 Scheiben verschieben (Hilfsplatz, Zielplatz, Startplatz)
    Bewegung von letzter Scheibe von Startplatz auf Zielplatz
    Turm mit -1 Scheiben verschieben(Zielplatz, Startplatz, Hilfsplatz)


Die optimale Anzahl an Zügen ist $2^n -1$

$A: 2^n -1 = 2\cdot A(n-1) + 1$
IA: $A(1) = 2^1 -1 = 1 = 2\cdot 0 +1$
IV: Für $n\in \mathbb N$ gelte $A(n)$
IB: $A(n+1) = 2^{(n+1)} -1$
IS: 
$$\begin{align}
&A(n+1)=2 \cdot A(n) + 1\\
&=2\cdot (2^n -1) +1\\
&=2\cdot 2^n -2+1\\
&=2^{(n+1)} -1 \\
&\square
\end{align}$$

---


## Aufgabe 5
### a)

```python
def summe(a):

    # return sum(a)
    s = 0
    for i in a:
        s+= i
    
    return s

def prod(a):

    s = 1

    for i in a:
        s *= i

    return s
# Errechne das Ergebniss der Summe mit der Formel aus Aufgabe 2
def sum_form(n):
    return ((6*n*(n+1))/2) - n
# Errechne das Ergebniss des Produkts mit der Formel aus Aufgabe2
def prod_form(n):
    return 2 ** ((n*(n+1))/2)

# Vergleiche das Ergebniss von 2 Funktion in einer Markdown
# Tabelle
def compareTill(n, f1, f2):\
    res = ["|n|Programm|Formel|", "|----|----|----|"]
    template = "|{}|{}|{}|"
    for i in range(1, n):
        program = f1(range(1, i))
        form = f2(i)
        res.append(template.format(i, int(program), int(form)))

    return res

```

### b)

#### Summe
|n|Programm|Formel|
|----|----|----|
|1|0|5|
|2|1|16|
|3|3|33|
|4|6|56|
|5|10|85|
|6|15|120|
|7|21|161|
|8|28|208|
|9|36|261|

#### Produkt
|n|Programm|Formel|
|----|----|----|
|1|1|2|
|2|1|8|
|3|2|64|
|4|6|1024|
|5|24|32768|
|6|120|2097152|
|7|720|268435456|
|8|5040|68719476736|
|9|40320|35184372088832|
