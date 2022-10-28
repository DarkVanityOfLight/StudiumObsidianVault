0 13 11 46
21% 23% 18% 13%Die Objekte in einer Menge nennt man Element der Menge M.

## Definition
> Eine Menge ist die Zusammenfassung von wohl unterschiedenen Objekten unserer Anschauung oder unseres Denkens zu einem Ganzen.
---

Ist x ein Element der Menge M, so schreibt man:
$$x \in M$$
andernfalls schreibt man:
$$x \notin M$$
Um eine Menge zu beschreiben benutzt man die Mengenschreibweise:
$$B = \{a;b;c\}$$
Bei Mengen spielt es keine Rolle, wie oft ein Element aufgezählt wird. Sie werden insbesondere nicht größer, wenn ihre Elemente mehrfach aufgezählt werden.
$$\{1;1;2;2;2;2\} = \{1;2\}$$ Auch auf die Reihenfolge der Elemente kommt es nicht an: 
$$\{1;2;3\} = \{3;2;1\}$$
Es erweist sich als zweckmäßig, eine Menge zur Verfügung zu haben, die keine Elemente besitzt. Diese heißt die leere Menge und wird mit  $\emptyset$ oder $\{\}$ bezeichnet. 
## Teilmengen
Wir schreiben $A \subseteq B$ und sagen, dass $A$ eine Teilmenge von $B$ ist wenn gilt:
$$x \in A \implies x\in B$$
d.h wenn jedes Element aus $A$ auch in $B$ liegt. Die Menge $B$ heißt dann auch eine Obermenge von A.
$$A \subseteq B: \iff (x \in A \implies x\in B)\iff (\forall x \in A| x\in B )$$
Der Fall $A=B$ ist in der obigen Definition erlaubt, insbesondere gilt $A \subseteq A$. Außerdem gilt $A=B$ genau dann, wenn $A \subseteq B$ und $B \subseteq A$ gilt.
Wenn man ausdrücken möchte, dass $A$ eine Teilmenge von $B$ und nicht gleich $B$ ist, schreibt man $A \subsetneq B$ und sag, dass A eine echte Teilmenge von $B$ ist.
$$\begin{align}
A \not \subseteq B &\iff\neg(A\subseteq B) \\
& \iff\neg(\forall x \in A: x\in B)\\
&\iff(\exists x\in A: x \not\in B)
\end{align}$$

## Kardinalität
Die Kardinalität einer Menge $A$ ist die Anzahl der Elemente von $A$. Sie wird mit $|A|$ bezeichnet
