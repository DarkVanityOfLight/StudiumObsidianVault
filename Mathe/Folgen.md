Sei $M$ eine Menge, dann ist eine Folge in $M$  eine Abbildung
$$\begin{align}
&\mathbb N \to M\\&n \mapsto a_n\end{align}$$
Wir schreiben für die Folge kurz $(a_n)_{n\in\mathbb N}$ oder $(a_n)$.

---

Eine [Funktion](Mathe/Funktionen.md) von $N$ nach $R$ heißt (reelle) Folge.
$$\begin{align}
a: N \rightarrow R\\
n \mapsto a(n) = a_n
\end{align}$$kurze Schreibweise: $(a_n)_{n \in N} = (a_n) \subseteq R$

Folgen können [Beschränkt](Schranken.md) sein.
Außerdem können sie [Monotonie](Funktionen.md#Monotonie) verhalten zeigen.


Sei $K$ ein [angeordneter Körper](Angeordneter%20Körper.md) und $(a_n), (b_n)$  [konvergente](Konvergenz.md) Folgen in $K$ mit
$\lim a_n = a \quad \lim b_n = b$
Dann [konvergieren](Konvergenz.md) die Folgen $(a_n + b_n)$ und $(a_n \cdot b_n)$ und es gilt:
$\lim_{n\to\infty} a_n + b_n = a+b$
$\lim_{n\to\infty} a_n \cdot b_n = a \cdot b$

$(a_1) = (a_1 , a_2, a_3, ...)$
$b_n = (b_1, b_2, b_3, ...)$
$(a_n + b_n) := (a_1 + b_1, a_2 + b_2, ...)$

ist außerdem $a \not = 0$, dann gibt es ein $N$ mit $a_{n} \not= 0$ für alle $n\ge N$,
die Folge $\left(\frac{1}{a_{n}}\right)_{n\ge N}$ [konvergiert](Konvergenz.md) und es gilt 
$$\lim_{n\to\infty} \frac{1}{a_{n}} = \frac{1}{a}$$



---

Ist $a\not = 0 \implies \exists N : a_n \not = 0 \quad\forall n \geq N$
dann $\left(1\over a_n\right)_{n \geq N}$
konv $\lim_{n \to \infty} {1\over a_n} = {1 \over a}$

## Beispiel

Die Summe von nicht konvergenten Folgen kann konvergent sein.

$(-1)^n + (-1)^{n+1} = 0 \implies$ konvergent

## Beschränkt
$(a_n)$ ist nach oben beschränkt wenn $\exists c \in K : a_n \leq c \forall n$
$(a_n)$ ist nach unten beschränkt wenn $\exists c \in K : a_n \geq c \forall n$

Wenn $(a_n)$ von oben und unten beschränkt ist nennt man es nur beschränkt

### Bemerkung

$(a_n)$ ist beschränkt $\iff \exists c \in k : |a_n| \leq c \quad \forall n$

---

Jede [Konvergente](Konvergenz.md) Folge ist beschränkt

## Beweis

$a := \lim_{n \to \infty} a_n\qquad \exists N : |a_n -a|< 1\quad \forall n \geq N$
$|a_n| = |a_n - a +a| \leq |a_n -a| + |a| < 1+|a| \quad \forall n \geq N$
$c:= max\{|a_1|,..., |a_{N-1}|, 1+|a|\}$
$\implies |a_n| \leq c \quad \forall n$

## Beispiel

$a_n = 2 + {2 \over n} \quad \lim a_n = 2$
$N = 3\qquad |a_n - 2| < 1 \quad \forall n\geq 3$
$c := max\{3, 4, 2 + 1\}=$ 4
$\implies |a_n| \leq 4 \quad\forall n$
---

Gibt es zu jedem $\epsilon\in k$ ein $N \in \mathbb N$ mit $a_n > \epsilon\quad\forall n \geq N$ so heißt $(a_n)$ bestimmt divergent gegen $\infty$

Schreibe $\lim_{n\to\infty} a_n = \infty$


## Grenzwert
Sei $(a_n)_{n\in \mathbb{N}}$ eine Folge.
Eine Zahl $a \in \mathbb{R}$ heißt Grenzwert der Folge $(a_n)_{n \in \mathbb N}$, wenn es zu jeder Zahl $\epsilon \in \mathbb R, \epsilon > 0$, eine [natürliche Zahl](Natürliche%20Zahlen.md) $n_\epsilon \in \mathbb N$ gibt, so dass für alle $n \geq n_\epsilon$ stets gilt, dass $|a_n - a| < \epsilon$. Kurz und knapp:
$a$ heißt Grenzwert von $$\begin{align}
&(a_n)_n \in \mathbb N \\
\iff &\forall \epsilon > 0, \exists n_\epsilon |\ |a_n -a| \epsilon, \forall n \geq n_\epsilon
\end{align}$$
Hat die Folge $(a_n)_n \in \mathbb N$ einen Grenzwert $a$, schreibt man kurz 
$$\lim_{ n \to \infty } a_n = a$$

## Grenzwertbeweisen
Behauptung: $lim_{n\to \infty} {1 \over n}= 0$
Sein $\epsilon > 0$ vorgegeben. Wir müssen $n_\epsilon \in N$ bestimmen, sodass $|a_n -a| < \epsilon$, also $|{1\over n} - 0| < \epsilon \forall n \geq n_\epsilon$
da $1\over n$ stets positiv ist, soll also ${1\over n} < \epsilon$, also $n > {1\over \epsilon} \forall n \geq n_\epsilon$
Also $n_\epsilon$ können wir wählen $n_\epsilon := \lceil {2\over \epsilon}\rceil$
Sei $\epsilon > 0$ beliebig. Sei $n_\epsilon := \lceil {2\over \epsilon}\rceil$. Dann gilt
für alle $n \geq n_\epsilon$
$$\begin{align}
|{1\over n} - 0| = |{1\over n}| = {1\over n} \leq {1\over n_\epsilon} = {1\over \lceil {2\over \epsilon}\rceil} \leq {1 \over {2\over \epsilon}} = {\epsilon \over 2} < \epsilon
\end{align}$$

$\neg B \implies \neg A$ : nicht beschränkt $\implies$ nicht konvergent

Sei $[a,b] \subseteq \mathbb R$ und sei $x_0 \in [a,b]$.
Sei $f$ eine reellwertige Funktion, die auf $[a, b]$ oder $[a,b] \setminus \{x_0\}$ definiert sei.
Man sagt, der Grenzwert von $f$ für $x$ gegen $x_0$ existiert und ist gleich $c$ schreibt $$\lim_{x \to_0} f(x) = c$$
falls für jede Folge $(x_n)_{n \in \mathbb N}$ in $[a, b]$ mit $\lim_{n \to \infty}x_n = x_0$ gilt, dass $\lim_{n\to \infty}f(x_n) = c$

## Grenzwertsätze
Wenn für zwei auf $[a, b]$ oder $[a, b] \setminus {x_0}$ definierte reellwertige Funktionen $f$ und $g$ die Grenzwerte $\lim_{x\to x_0} f(x)$ und  $\lim_{x\to x_0} g(x)$ existieren, dann existieren auch folgende Grenzwerte:
- $\lim_{x\to x_0}(f(x) + g(x)) = \lim_{x\to x_0} f(x) +\lim_{x\to x_0} g(x)$ 
- $\lim_{x\to x_0}(f(x) - g(x)) = \lim_{x\to x_0} f(x) -\lim_{x\to x_0} g(x)$ 
- $\lim_{x\to x_0}(f(x) \cdot g(x)) = \lim_{x\to x_0} f(x) \cdot\lim_{x\to x_0} g(x)$ 
- $\lim_{x \to x_0} = {\lim_{x \to x_0} f(x) \over \lim_{x \to x_0} g(x)}$



## Monotonie
Sei $K$ ein [Angeordneter Körper](Angeordneter%20Körper.md). Eine Folge $(a_n)$ heißt monoton wachsend, wenn $a_{n+1} \ge a_{n}$ für alle $n$.
Sie heißt monoton fallend, wenn $a_{n+1} \le a_{n}$ für alle $n$.

## Konvergent und Divergent
Dann heißt die Folge $(a_n)_n\in \mathbb N$ einen konvergent.
Man sagt auch: Die Folge $(a_n)_n\in \mathbb N$ konvergiert gegen a
> Jede konvergente Folge ist beschränkt
> Beschränktheit ist keine hinreichende Bedingung für Konvergenz.
> Ist eine Folge monoton und beschränkt, dann ist sie konvergent.

Hat die Folge $(a_n)_{n\in \mathbb N}$ keinen Grenzwert, dann heißt sie divergent.

Seien $(a_n)_n{\in \mathbb N}$ und $(b_n)_{n\in\mathbb N}$ zwei Folgen. Dann gilt:
Konvergieren die Folgen $(a_n)_{n \in \mathbb N}$ und $(b_n)_{n \in \mathbb N}$, dann konvergiert auch die Folge $(a_n + b_n)_{n \in \mathbb N}$ und es gilt
$$\lim_{n \to \infty}(a_n + b_n) = \lim_{n \to \infty} a_n + \lim_{n \to \infty} b_n$$
Konvergieren die Folgen $(a_n)_{n \in \mathbb N}$ und $(b_n)_{n \in \mathbb N}$, dann konvergiert auch die Folge $(a_n \cdot b_n)_{n \in \mathbb N}$ und es gilt
$$\lim_{n \to \infty}(a_n \cdot b_n) = \lim_{n \to \infty} a_n \cdot \lim_{n \to \infty} b_n$$
Konvergieren die Folgen $(a_n)_{n \in \mathbb N}$ und $(b_n)_{n \in \mathbb N}$ und gilt $b_n \not = 0 \forall n \in \mathbb N$ und $\lim_{n \to \infty} b_n \not = 0$, dann konvergiert auch die Folge $({a_n \over b_n})_{n\in \mathbb N}$ und es gilt
$$
\lim_{n \to \infty} {a_n \over b_n} = {\lim_{n \to \infty} a_n \over \lim_{n \to \infty} n_n}
$$
Für $c \in \mathbb R$ gilt
$$\lim_{n\to\infty}(c\cdot a_n) = c \cdot \lim_{n\to\infty} a_n$$

## Teilfolgen
Eine Teilfolge einer Folge $(a_{n})= (a_{1}, a_{2}, ...)$ ist eine Folge der Form
$$(a_{n_{i}}) = (a_{n_{1}}, a_{n_{2}}, ...)$$
mit 
$$n_{1} < n_{2} < ...$$

Sei $K$ ein angeordneter [Körper](Körper.md). Jede Folge in $K$ hat eine monotone Teilfolge.
Jede Teilfolge $(a_{n_{i}})$ einer [konvergenten](Konvergenz.md) Folge $(a_n)$ hat denselben [Grenzwert](Folgen.md#Grenzwertsätze)
$$\lim_{i\to\infty} a_{n_{i}} = \lim_{n\to\infty} a_{n}$$
