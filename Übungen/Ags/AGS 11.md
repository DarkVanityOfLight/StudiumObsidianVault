> Jannis Lauterbach, Kilian Lichtner, Gregor Stöbener

## Aufgabe 1

### a)
Sei $a \in \mathbb R$ ungleich 0  Betrachten wir die Abbildung $x \mapsto a \cdot x$ 

Ist die Abbildung injektiv, so ist sie auch surjektiv (da R endlich ist)
Ist die Abbildung injektiv und surjektiv, dann $\exists \ b \in R$ so dass $a \cdot b = 1$ ($b \cdot a = 1$  Kommutativgesetz). Also ist a eine Einheit 

Ist die Abbildung nicht injektiv, dann $\exists \ y,z \in \mathbb R$ mit $y \neq z$ so dass $a \cdot y = a \cdot z$
dann ist $a \cdot y - a \cdot z = a (y \cdot z) = 0$ (Distributivgesetz). 
Da $y - z \neq 0$ ist a ein Nullteiler

### b)
Gilt $a \cdot c = b \cdot c$ dann gilt auch $c (a - b) = 0$ Wenn jedoch $c \neq 0$ so muss $a - b = 0$ gelten $a - b = 0 \implies a = b$ Damit gilt: $a \cdot c = b \cdot c \implies a = b$

## Aufgabe 2


$$ n= 186444745729857899758373984272541398503249351266417000699738642133172271283265124803102459$$

$$e = 2^{16} + 1$$

---

Da einer der Faktoren relativ klein ist können wir die Pollardfaktorisierung anwenden.

```python
def pollard_p_1(n):
    a = 2
    for k in range(2, int(2*(n**0.25))):
        a = pow(a, k, n)
        d = gcd(a-1, n)
        if d > 1:
            return d
    return n

def gcd(a, b):
    while b:
        a, b = b, a%b
    return a
```


Wir erhalten $p = 2962244945158622279601750283735698362054297$ und damit $q = 62940354083336669282335053470277744418281466547$

Nun können wir $\phi(n)$ errechnen $\phi(n) = 186444745729857899758373984272541398503249288323100672417910737518517050721785008159581616$
Um an den Privaten schlüssel zu kommen lösen wir $e \cdot d = 1 \mod \phi(n)$ mithilfe des Euklidischem Algorithmus.
$d = 144519783985790947216463957780263103956010556583510294319695217448779562333745493606767873$
Als entschlüsselte Nachricht erhalten wir nun $2023$.

---
```maple
ifactor(186444745729857899758373984272541398503249351266417000699738642133172271283265124803102459, 'pollard')
```
führte in unseren Versuchen nicht zu einem Ergebnis.

## Aufgabe 3

Es gilt:
$$
x^{n}= \left\{ \
x(x^{2})^{\frac{n-1}{2}}\text{Falls $n$ ungerade}\atop 
(x^{2})^{\frac{n}{2}}\text{Falls $n$ gerade}\right. \
$$
Der Algorithmus funktioniert wie folgt:

1.  Initialisiere $c = 1$
2.  Solange $b > 0$:
    1.  Falls $b$ ungerade ist, setze $c = (c \cdot a) \mod n$
    2.  Teile $b$ durch 2 (ignoriere das Restwert)
    3.  Setze $a = (a \cdot a) \mod n$
3.  Gib $c$ zurück

```python
def mod_exp(a, b, n):
    c = 1
    while b > 0:
        if b % 2 == 1:
            c = (c * a) % n
        a = (a * a) % n
        b = b // 2
    return c
```

## Aufgabe 4

### a)
#### Additionstabelle 
| +    | 0   | 1   | 2   | 3   | 4   |
| --- | --- | --- | --- | --- | --- |
| 0   | 0   | 1   | 2   | 3   | 4   |
| 1   | 1   | 2   | 3   | 4   | 0   |
| 2   | 2   | 3   | 4   | 0   | 1   |
| 3   | 3   | 4   | 0   | 1   | 2   |
| 4   | 4   | 0   | 1   | 2   | 3   |

#### Multiplikationstabelle

| $\cdot$    | 0   | 1   | 2   | 3   | 4   |
| --- | --- | --- | --- | --- | --- |
| 0   | 0   | 0   | 0   | 0   | 0   |
| 1   | 0   | 1   | 2   | 3   | 4   |
| 2   | 0   | 2   | 4   | 1   | 3   |
| 3   | 0   | 3   | 1   | 4   | 2   |
| 4   | 0   | 4   | 3   | 2   | 1   |

### b)
$$\begin{matrix} &x_1 &+ & \overline 2x_2 &+ & \overline3x_3 &= &0 \\ &\overline2x_1 &+ & \overline3x_2 &+ &\overline4x_3 &= &0 \\ &\overline3x_1 &+ & \overline4x_2 &+ &\overline0x_3 &= &0 \\ \end{matrix}$$ $| I \times 2$ $$\begin{matrix} &I|&\overline2x_1 &+ &\overline 4x_2 &+ &\overline1x_3 &= &0 \\ &II|&\overline2x_1 &+ & \overline3x_2 &+ &\overline4x_3 &= &0 \\ &II|&\overline3x_1 &+ & \overline4x_2 &+ &\overline0x_3 &= &0 \\ \end{matrix}$$ $| I + II$ $$\begin{matrix} &I|&\overline2x_1 &+ &\overline 4x_2 &+ &\overline1x_3 &= &0 \\ &II|&\overline4x_1 &+ & \overline2x_2 &+ &\overline0x_3 &= &0 \\ &II|&\overline3x_1 &+ & \overline4x_2 &+ &\overline0x_3 &= &0 \\ \end{matrix}$$ $| II \times 3$ $$\begin{matrix} &I|&\overline2x_1 &+ &\overline 4x_2 &+ &\overline1x_3 &= &0 \\ &II|&\overline2x_1 &+ & \overline1x_2 &+ &\overline0x_3 &= &0 \\ &II|&\overline3x_1 &+ & \overline4x_2 &+ &\overline0x_3 &= &0 \\ \end{matrix}$$ $| II + III$ $$\begin{matrix} &I|&\overline2x_1 &+ &\overline 4x_2 &+ &\overline1x_3 &= &0 \\ &II|&\overline0x_1 &+ & \overline0x_2 &+ &\overline0x_3 &= &0 \\ &II|&\overline3x_1 &+ & \overline4x_2 &+ &\overline0x_3 &= &0 \\ \end{matrix}$$

$$L = \{\}$$
