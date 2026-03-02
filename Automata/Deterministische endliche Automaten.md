

Ein deterministischer endlicher Automat $A$ ist ein $5$-Tupel $A = (Q, \Sigma, \delta, q_0, F)$ wobei:
- $Q$ eine endliche Menge von Zuständen ist
- $\Sigma$ ein endliches Eingabealphabet ist
- $\delta: Q \times \Sigma \to Q$ die Transitionsfunktion ist
- $q_0 \in Q$ der Startzustand ist und
- $F\subseteq Q$ die Menge der Endzustände ist

---

Wir erweitern die Transitionsfunktion $\delta$ eines DFA zur Übergangsfunktion $\hat\delta$, die die Übergänge für ganze Wörter ermittelt.

Zu einem DFA $A = (Q, \Sigma,\delta, q_0, F)$ definieren wir eine Funktion $\hat\delta: Q\times \Sigma^* \to Q$ induktiv wie folgt

- $\hat\delta(q, \varepsilon) = q \qquad \forall q \in Q$
- $\hat\delta(q, wa) = \delta(\hat\delta(q, w), a) \qquad \forall q\in Q, w\in\Sigma^*, a\in\Sigma$

---

Die von einem DFA $A = (Q, \Sigma, \delta, q_0, F)$ erkannte Sprache ist
$$L(A) =  \lbrace w\in\Sigma^* | \hat\delta(q_0, w) \in F\rbrace$$

Wir sagen, dass ein Wort $w\in\Sigma^*$ von $A$ akzeptiert wird, wenn $\hat\delta(q_0, w)\in F$.




