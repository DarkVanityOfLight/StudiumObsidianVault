
Oft will man nicht nur die Wahrscheinlichkeit eines einzelnen Ergebnisses wissen, sondern ist daran interessiert mit welcher Wahrscheinlichkeit das Ergebnis in einer gegebenen [Menge](Mengen.md) von Ergebnissen liegt.

Sei $m: \Omega \to \mathbb R_{\ge 0}$ eine [Wahrscheinlichkeitsfunktion](Wahrscheinlichkeitsfunktionen.md). Jede [Teilmenge](Teilmengen.md) $M\subset \Omega$ bezeichnen wir als Ereignis und ordnen $M$ die Wahrscheinlichkeit
$$P(M) = \sum_{\omega \in M} m(\omega)$$
zu.

Sei $m : \Omega \to \mathbb R_{\ge 0}$ eine Wahrscheinlichkeitsfunktion. Offenbar gilt
$$P(\Omega) = 1$$
und
$$P(M) \ge 0$$
für alle Ereignisse $M\subset \Omega$.
Weiter gilt für die Inklusionsbeziehung zwischen Ereignissen
$$M \subset N\subset \Omega \implies P(M) \le P(N)$$
für das $1$ elementige Ereignis $M = \lbrace \omega\rbrace$ mit $\omega\in\Omega$ gilt
$$P(\lbrace \omega\rbrace) = m(\omega)$$


Ist $M$ ein Ereignis, dann gilt 
$$P(\overline M) = 1 - P(M)$$


---

Ist $m: \Omega \to \mathbb R_{\ge 0}$ eine Wahrscheinlichkeitsfunktion und sind $M_1, \dots, M_n \subset \Omega$ Ereignisse, dann gilt

$$P(M_1 \cup \dots \cup M_n) = \sum^n_{k=1}(-1)^{k-1} \sum_{|T| = k } P(M_T)$$
mit 
$$M_T = \bigcap_{i\in T} M_i$$
für $T \subset \lbrace 1, \dots, n\rbrace$.

