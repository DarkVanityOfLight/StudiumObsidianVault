> Marcel Wirdel, Kilian Lichtner
## Aufgabe 2

### 1
Das Programm gibt eine erfüllende Belegung `[p = False, q = False, r = True]` für die Formel $(r \lor \neg p) \land (p \lor (q \lor r))$ aus.

### 2
Gegeben eine Formel $F$ und einer Belegung, hängen wir die Belegung mit einer " und nicht" Verknüpfung an unsere Formel $F$ an. In unserem Fall also:
$$(r \lor \neg p) \land (p \lor (q \lor r)) \land \neg (\neg p \land \neg q \land r)$$
### 3
- $(r \lor \neg p) \land (p \lor (q \lor r)) \land \neg (\neg p \land \neg q \land r)$ : `[p = True, q = False, r = True]`
- $(r \lor \neg p) \land (p \lor (q \lor r)) \land \neg (\neg p \land \neg q \land r \land \neg(p \land \neg q \land r))$: `[p = False, q = True, r = True]`

## Aufgabe 3

### 1
- Schreibe Implikationen und Äquivalenzen um.
- Schreibe die Formel als NNF(Vorlesung)
- Verwende das Distributivgesetz um $\land$ in die Klammern zu ziehen und $\lor$ nach außen zu drücken $F\land(G \lor H) \equiv (F\land G) \lor (F\land H)$

### 2
$$(A \land B \land \neg C)$$

__Eingabe:__ Eine Formel in DNF

__Algorithmus:__

Wir betrachten jede Subformel einzeln, unsere Formel ist genau dann erfüllbar wenn mindestens eine der Subformeln erfüllbar ist:

Für jede Subformel betrachten wir all ihre Literale:
Jedes Literal das vorkommt setzen wir auf $\top$, oder $\bot$ sollte seine Negation vorkommen,
kommt eine Variable doppelt als Literal und seine Negation vor betrachten wir die nächste Subformel. 
Können wir jedes Literall einer Subformel erfolgreich auf $\top$ oder $\bot$ setzen,  ist die gegebene DNF erfüllbar.

Der Algorithmus läuft maximal in $O(|A|^2)$, da wir uns maximal jeden Term einmal anschauen, und in jedem Term jedes Literal($n\cdot n = n^2$).

### 3
Die Ausgabe des ersten Algorithmus ist im Worstcase $O(2^{|A|})$. Deshalb muss der Zweite Algorithmus im Worstcase auch $2^{|A|}$ Terme überprüfen. Die Laufzeit ist damit:
$$O\left(2^{|A|^2}\right)$$ was nicht Polynomiell ist.

## Aufgabe 4

### 1

$\rightarrow$
Nehmen wir an $\Sigma = \bigcup_i \Sigma_i$   ist erfüllbar.
Nach dem Kompaktheitstheorem gilt für jedes $i\in\mathbb N$:
$$\Sigma_i \subset\Sigma$$ gibt es eine Erfüllende Belegung. Da dies für jedes $i$ gilt ist jedes $\Sigma_i$ erfüllbar

$\leftarrow$

Nehmen wir an alle $\Sigma_i$ sind erfüllbar:
für jedes $i\in\mathbb N$ existiert ein Modell $M_i$ für $\Sigma_i$
Wir konstruieren ein Model $M$ für $\Sigma$ indem wir die Vereinigung aller Modelle $M_i$ nehmen.
Da jedes $\Sigma_i$ erfüllbar ist erhalten wir durch die Kombination aller Modelle ein Modell für $\Sigma$.

## 2
Wenn $\Sigma_i \subseteq \Sigma_{i+1}$ nicht mehr gilt, kann in jedem Schritt neue Variablen eingeführt werden können oder die Struktur der Formel so geändert wird das ein neues Model das $\Sigma_{i}$ erfüllt nicht mehr $\Sigma_{i+1}$ erfüllt. Dies führt dazu das die Kette nicht mehr erfüllbar ist auch wenn jede einzelne Formel erfüllbar ist.

## Aufgabe 5


### 1
$$\begin{align}
&p \rightarrow q, p\rightarrow r, q \leftrightarrow \neg r\\
\iff& \neg p \lor q, \neg p \lor r, p\rightarrow \neg r, p \leftarrow \neg r\\
\iff& \neg p \lor q, \neg p \lor r, \neg p \lor \neg r, \neg \neg r \lor p\\
\iff& \neg p \lor q, \neg p \lor r, \neg p \lor \neg r, \ r \lor p
\end{align}$$


![](Pasted%20image%2020231111154518.png)

Wir können $\neg p$ erzeugen deshalb gilt
$$p \rightarrow q, p\rightarrow r, q \leftrightarrow \neg r \vDash \neg p$$

### 2
![](Pasted%20image%2020231111152233.png)

Da wir keine Leere Menge herleiten können, ist die Formel erfüllbar.