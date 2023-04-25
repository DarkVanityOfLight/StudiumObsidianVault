	Jannis Lauterbach, Kilian Lichtner, Gregor Stöbener

## Aufgabe 1

## a)
euklidischerAlgorithmus (a, b):
    if b = 0 then a
    else euklidischerAlgorithmus (b, a modulo b)


### Tests:

a = 10
b = 0
1. if 0 = 0 then 10 | Trifft zu 
2. Ausgabe 10

a = 4
b = 2
1. if 2 = 0 then 4 | Trifft nicht zu
2. euklidischerAlgorithmus (2, 4 modulo 2)
3. if 0 = 0 then 2 | Trifft zu
4. Ausgabe 2
```python
def euklidischerAlgorithmus (a, b):
    if b == 0:
        return a
    else:
        return euklidischerAlgorithmus(b, a % b)

print(euklidischerAlgorithmus(60, 20))
print(euklidischerAlgorithmus(5, 10))
print(euklidischerAlgorithmus(15, 23))
```

```
Output: 
20
5
1
```

## b)
Den größten gemeinsamen Teiler von Zähler und Nenner bilden, um die größte Zahl zu finden mit welcher gekürzt werden kann. 

ggt von  $90297278063 \text{ und } 18261358091 = 18027007$
$$\begin{align}
{90297278063/18261358091 \over 18261358091/18261358091}={5009\over 1013}
\end{align}$$
## Aufgabe 2

$$\begin{align}
&x \equiv 2 \mod 3\\
&x \equiv 2 \mod 7\\
&x \equiv 3 \mod 10
\end{align}$$
---

$$\begin{align}
&(7 \cdot 10) \cdot x_1 \equiv 1 \mod 3 \implies x_1 = 1\\
&(3 \cdot 10) \cdot x_2 \equiv 1 \mod 7 \implies x_2 = 4\\
&(3 \cdot 7) \cdot x_3 \equiv 1 \mod 10 \implies x_3 = 1
\end{align}$$

---

$$\begin{align}
&x = 2 \cdot 7 \cdot 10 \cdot x_1 + 2 \cdot 3 \cdot 10 \cdot x_2 + 3 \cdot  3 \cdot 7 \cdot x_3\\
&x = 2 \cdot 7 \cdot 10 \cdot 1 + 2 \cdot 3 \cdot 10 \cdot4 + 3 \cdot 3 \cdot 7 \cdot 1 \\
&=443
\end{align}$$

---

$$
 443 \mod 3 \cdot 7 \cdot 10  = 23
$$

---
$$R = \{23 + z \cdot 210| \forall z \in \mathbb Z\}$$ für  $z \in \mathbb Z$

## Aufgabe 3


$$\begin{align}
x + 28 \equiv 1 \mod 35\\
x + 6 \equiv 1 \mod 6\\
x + 4 \equiv 1 \mod 11
\end{align}$$
---

$$\begin{align}
& x \equiv 8 \mod 35\\
& x \equiv 1 \mod 6\\
& x \equiv 8 \mod 11
\end{align}$$

---

$$\begin{align}
&(6 \cdot 11)  \cdot x_1 \equiv 1 \mod 35 \implies x_1 = 26\\
&(35 \cdot 11) \cdot x_2 \equiv 1 \mod 6 \implies x_2 = 1\\
&(6 \cdot 35) \cdot x_3 \equiv 1 \mod 11 \implies x_3 = 1
\end{align}$$

---

$$\begin{align}
&x = 8 \cdot 6 \cdot 11 \cdot x_1 + 1 \cdot 35 \cdot 11 \cdot x_2 + 8 \cdot 6 \cdot 35 \cdot x_3\\
&x = 8 \cdot 6 \cdot 11 \cdot 26+ 1 \cdot 35 \cdot 11 \cdot 1 + 8 \cdot 6 \cdot 35 \cdot 1\\
&x = 13728 + 385 + 1680\\
&x = 15793
\end{align}$$

---

$$\begin{align}
&15793 \mod (35 \cdot 6 \cdot 11)\\
&15793 \mod 2310 = 1933
\end{align}$$

---

$$\begin{align}
&R = \{1933 + z \cdot 2310\}\\
&1933 + (1 \cdot 2310) = 4243
\end{align}$$

 ## Aufgabe 4
### a)
$$\begin{align}
&x \equiv a_1 \mod n_1\\
&x \equiv a_2 \mod n_2\\
\\

& n_1 | (x- a_1)\\
& n_2 | (x - a_2)\\
\\
&m_1 \cdot n_1 = (x - a_1)\\
&m_2 \cdot n_2 = (x -a_2)\\
\\
&x = m_1\cdot n_1 + a_1\\
&x = m_2 \cdot n_2 + a_2\\
\\
& m_2 \cdot n_2 + a_2 = m_1 \cdot n_1 + a_1\\
&a_1 - a_2 = m_2 \cdot n_2 - m_1 \cdot n_1\\
&ggT(n_1, n_2)| (a_1 - a_2)\qquad ggT(n_1, n_2)|(m_2\cdot n_2 - m_1 \cdot n_1)
\end{align}$$


### b)
$$\begin{align}
&x \equiv 1 \mod 108\\
&x \equiv 25 \mod 80\\
\\
& 1 \equiv 25 \mod 4\\
& 1 \mod 4 = 1\qquad 25 \mod 4 = 1\\
\\
&\text{Primfaktorzerlegung}:\\
&108 = 2^2 \cdot 3^3\\
&80 = 2^4 \cdot 5\\
\\

&\cancel{x \equiv 1\equiv 5 \mod 4}\\
&x \equiv 1\equiv 28 \mod 27\\
\\
&x \equiv 25 \equiv 57 \mod 32\\
&x \equiv 25 \equiv 0 \mod 5\\

\end{align}$$
---
$$\begin{align}
& x \equiv 28 \mod 27\\
&x \equiv 57 \mod 32\\
& x \equiv 0 \mod 5
\end{align}$$
---

$$\begin{align}
&(32 \cdot 5) \cdot x_1 \equiv 1 \mod 27 \implies x_1 = 13\\
&(27 \cdot 5) \cdot x_2 \equiv 1 \mod 32 \implies x_2 = 23\\
&(32 \cdot 27) \cdot x_3 \equiv 1 \mod 5 \implies x_3 = 4
\end{align}$$
---
$$\begin{align}
&x = 28 \cdot 32 \cdot 5 \cdot x_1 + 57 \cdot 27 \cdot 5 \cdot x_2 + 0 \cdot 27 \cdot 32 \cdot x_3\\

&x = 28 \cdot 32 \cdot 5 \cdot 13 + 57 \cdot 27 \cdot 5 \cdot 23 + 0 \cdot 27 \cdot 32 \cdot 4\\
&x = 235 225
\end{align}$$
---
$$
235225 \mod 4320 = 1945
$$
---

$$
L = \{1945 + z\cdot 2160|\forall z\in \mathbb Z\}
$$

## Aufgabe 5

```python
def aPrime (lR, uR):
    primeList = []
    for n in range (lR, uR + 1):
        if n > 1:
            for i in range (2, n):
                if (n % i) == 0:
                    break
            else:
                primeList.append(n)
    return primeList

bPrime = []
def p (sn, n, n2):
    for x in range(sn, n):
        print(x, " = ", len(aPrime(0, x)))
        bPrime.append(len(aPrime(0, x)))
        for a in range(sn, n2):
            print("|", len(aPrime(0, x)), "|", a, "|", 
                  len(aPrime(0, x))/x, "|", 
                  1/(math.log(x) - a), "|")
        print("----------------------------------")
```

![](Pasted%20image%2020221202183111.png)