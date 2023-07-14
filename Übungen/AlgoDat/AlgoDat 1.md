

> Marcel Wirdel, Jannis Lauterbach, Maurice Marhöfer, Eric Schneider, Kilian Lichtner

---

## Aufgabe 1.1
1. **Algorithmische Idee:** Wir versuchen, die letzten Ziffern von x und y voneinander zu subtrahieren. Wenn das nicht möglich ist, addieren wir den Übertrag zum Subtrahenden.
2. **Algorithmus:**
```python
sub(x_{n-1}...x_0, y_{n-1}...y_0) {
    c_0 = 0
    
    for i = 0 to n-1:
        # elementar Operation
        (c_{i+1}, z_i) = x_i - (y_i + c_i)
    
    z_n = c_n
    
    return z_n...z_0
}
```

3.  **Laufzeit:** Da wir nur eine Elementaroperation haben und diese für jede Ziffer 1-mal aufgerufen wird, benötigen wir für n Ziffern n elementare Operationen.

## Aufgabe 1.2

$$\sum_{i=1}^{\infty} \left(\frac{3}{2} - \sum_{j=0}^{i} \left(\frac{1}{3}\right)^j\right) \\
= \sum_{i=1}^{\infty} \left(\frac{3}{2} - \left(\frac{3}{2} - \frac{3^{-i}}{2}\right)\right) \\
= \sum_{i=1}^{\infty} \left(\frac{3^{-i}}{2}\right) \\
= \frac{1}{2} \sum_{i=1}^{\infty} \left(\frac{1}{3}\right)^i \\
= \frac{1}{2} \cdot \frac{1/3}{1-1/3} \\
= \frac{1}{4}$$

## Aufgabe 1.3

### a)

**Zeilen:** [1,2,3,4,5,6,7,8,9,10,3,4,5,6,7,8,9,10,3,4,5,6,11,12]  
**Akkumulator:** 6

### b)

Das Programm berechnet die Fakultät einer Zahl in Register 1. Dabei verwendet es
$$\begin{align*}
2 + 8 * (n-1) + 4 + 2\\
8 + 8 * (n-1)
\end{align*}$$

Operationen. In unserem Fall also
$$8 + 8 * (3-1) = 8 + 8 * 2 = 24$$
Operationen.

### c)

Mit Hilfe des Zweierkomplements können wir auch negative Zahlen in unserem RAM-Modell darstellen. Dabei können wir die Subtraktion auf die Addition zurückführen, indem wir beispielsweise $1 + (-2)$ berechnen. Dies beschränkt allerdings den positiven Wertebereich, den wir mit n Bits darstellen können, und wir müssen bei der Addition beachten, dass der letzte Übertrag wegfällt.

---

## Aufgabe 1.4

### a)

Da nach Lemma 30.6 aus Kapitel 2 der Vorlesung gilt:
$$O(f) + O(g) = O(f + g) = O(max{f, g})$$

Also gilt: 
$$O(f_1) + O(f_2) = O(max{f_1, f_2})$$
Und da $f_1(n)$, $f_2(n)$ in $O(g(n))$ liegen, muss auch $f_1(n) + f_2(n)$ in $O(g(n))$ liegen.

### b)

$$\begin{align*}
&({n \atop 2})\\
=& n! / (2! * (n-2)!)\\
=& n! / (2! * n! / ((n-2) * (n-1)))\\
=& n! * (n-2) * (n-1) / (2! * n!)\\
=& (n^2 - 3n + 2) / 2\\
\end{align*}
$$
Also liegt es in $\Theta(n^2)$.

### c)

Da nach Lemma 30.6 aus Kapitel 2 der Vorlesung gilt:
$$O(f_1) + O(f_2) = O(max{f_1, f_2})$$
Und $O, \Theta$$ nach Lemma 30.1 reflexiv sind, muss gelten:
$$\max{f(n), g(n)} \in \Theta(f(n) + g(n))$$
### d)

Da Funktionen in $o(f)$ strikt langsamer wachsen als $f$ und Funktionen in $Omega(f)$ mindestens genauso schnell wachsen wie $f$, kann es keine gemeinsame Schnittmenge geben. Damit gilt:

$$o(f) \cap \Omega(f) = \lbrace\rbrace$$
### e)

$$\begin{align*}
&\Omega(f) \cup O(f) \subseteq \Theta(f)\\
&O(f) \cup \Omega(f) \subseteq \Theta(f)\\
&O(f) \cup \Theta(f) \subseteq \Theta(f)\\
&\Theta(f) \subseteq O(f) \cup \Omega(f)\\
&\Theta(f) \subseteq O(f) \cup \Theta(f)\\
&\Theta(f) \subseteq \Omega(f) \cup \Theta(f)\\
&\Theta(f) \subseteq O(f) \cup \Omega(f) \cup \Theta(f)\\
&\Theta(f) \subseteq O(f) \cup \Omega(f) \cup \Theta(f) \subseteq O(f) + \Omega(f) + \Theta(f)\\
&\Theta(f) = O(f) \cup \Omega(f) \cup \Theta(f)
\end{align*}$$
