	Jannis Lauterbach, Kilian Lichtner, Gregor Stöbener

## Aufgabe 2

## a)
$a \circ b =e \implies b \circ a = e$

$a \circ e \circ b = e$
$a \circ (b \circ a) \circ b = e$

$(a \circ b) \circ (a\circ b) = e$
$e \circ e = e$

## b)

$$\begin{align}
&a\circ e = a\\
&a \circ (a^{-1} \circ a) = a\\
&(a \circ a^{-1}) \circ a = a\ |\text{Es gilt $a \circ a^{-1} =  e$ siehe a}\\
&e \circ a = a
\end{align}$$
## c)

Nehmen wir an es das Links neutrale Element sei nicht eindeutig dann gibt es ein $e_1 \not = e_2$ sodass:

$e_1 \circ e_2 = e_2$
und 
$e_2 \circ e_1 = e_1$
Wir haben schon gezeigt das $e_1 \circ e_2 = e_2 \circ e_1$ daher gilt:
$e_2 = e_1$ und dies ist ein Widerspruch.

## d)
Nehmen wir an das Links inverse Element sei nicht eindeutig dann gibt es ein $a_1 ^{-1} \not = a_2^{-1}$ sodass:

$a_1^{-1} = a_1^{-1}\circ e = a_1^{-1} \circ a_2^{-1} \circ a$
Wie wir schon gezeigt haben gilt damit auch:
$a_1^{-1} \circ a \circ a_2^{-1}$
$e\circ a_2^{-1}$
$\implies a_2^{-1} = a_1^{-1}$

## e)

$(a\circ b)^{-1} = b^{-1} \circ a^{-1}$

Substituieren wir für $a\circ b = c$ erhalten wir:
$c^{-1}$ und $b^{-1} \circ a^{-1}$
Dann gilt:
$c^{-1}\circ c = e$ und 
$$\begin{align}
&b^{-1} \circ a^{-1} \circ c =e|\text{Resubstitution}\\
&b^{-1} \circ a^{-1} \circ a \circ b = e\\
\end{align}$$
### f)
$(a^{-1})^{-1} = a$
Da gilt:
$a^{-1} \circ a =e$
und wie wir in a) gezeigt haben
$\implies a \circ a^{-1} = e$
Per definition ist dann $a$ das links inverse zu $a^{-1}$
und da das inverse auch eindeutig Bestimmt ist muss gelten
$(a^{-1})^{-1} = a$


## Aufgabe 3

### a)
$$
\sigma^2 = \left(
\begin{matrix}
1 & 2 & 3 & 4 & 5 & 6 & 7\\
2 & 1 & 5 & 6 & 4 & 3 & 7\\
1 & 2 & 4 & 3 & 6 & 5 & 7\\
\end{matrix}
\right)
$$
$$
\tau^2  = \left(
\begin{matrix}
1 & 2 & 3 & 4 & 5 & 6 & 7\\
1 & 3 & 4 & 2 & 5 & 7 & 6\\
1 & 4 & 2 & 3 & 5 & 6 & 7
\end{matrix}
\right)
$$

$$
\sigma \circ \tau = \left(\begin{matrix}
1 & 2 & 3 & 4 & 5 & 6 & 7\\
2 & 1 & 5 & 6 & 4 & 3 & 7\\
3 & 1 & 5 & 7 & 2 & 4 & 6
\end{matrix}\right)
$$
$$
\tau \circ \sigma = \left(\begin{matrix}
1 & 2 & 3 & 4 & 5 & 6 & 7\\
1 & 3 & 4 & 2 & 5 & 7 & 6\\
2 & 5 & 6 & 1 & 4 & 7 & 3
\end{matrix}\right)
$$

### b)
$$\left(
\begin{matrix}
1 & 2 & 3 & 4 \\
2 & 1 & 3 & 4 \\
\end{matrix}
\right)\in S_4$$
$$\left(
\begin{matrix}
1 & 2 & 3 & 4 \\
3 & 2 & 1 & 4 \\
\end{matrix}
\right)\in S_4$$
$$\left(
\begin{matrix}
1 & 2 & 3 & 4 \\
4 & 2 & 3 & 1 \\
\end{matrix}
\right)\in S_4$$
---

$$\left(
\begin{matrix}
1 & 2 & 3 & 4 \\
1 & 3 & 2 & 4 \\
\end{matrix}
\right)\in S_4$$
$$\left(
\begin{matrix}
1 & 2 & 3 & 4 \\
1 & 4 & 3 & 2 \\
\end{matrix}
\right)\in S_4$$
---

$$\left(
\begin{matrix}
1 & 2 & 3 & 4 \\
1 & 2 & 4 & 3 \\
\end{matrix}
\right)\in S_4$$
---


## Aufgabe 4
# a)
```python
def siebDesEratosthenes(n):
    p = 2
    primZahlen = []
    primListe = [True for i in range(n+1)]   
    while (p*p <= n):
        if (primListe[p] == True):
            for i in range(p*2, n+1, p):
                primListe[i] = False
        p=p+1
    for p in range(2, n+1):
        if primListe[p] == True:
            primZahlen.append(p)
    return primZahlen

print(siebDesEratosthenes(100))
print("-----")
```
`[2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, 37, 41, 43, 47, 53, 59, 61, 67, 71, 73, 79, 83, 89, 97]`

# b)
```python
def probedivsion(n):
    for x in siebDesEratosthenes(n):
        if n%x == 0:
            return x

print(probedivsion(21))     
print("-----")      
```
`3`
# c)
```python
def primfaktorzerlegung(n):
    faktoren = []
    while n%2 == 0:
        n = n//2
        faktoren.append(2)
    p=3
    while n != 1:
        while n%p == 0:
            n = n//p
            faktoren.append(p)
        p=p+2
    print(faktoren)

primfaktorzerlegung(116338867864982351)
```
`[1013, 1013, 3119, 6029, 6029]`

