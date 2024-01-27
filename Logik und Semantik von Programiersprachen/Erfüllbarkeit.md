
## Erfüllbarkeit in der Aussagenlogik
Eine Formel $\varphi$ ist genau dann erfüllbar (satisfiable), wenn sie ein [Modell](Modell.md) hat.


Um die Erfüllbarkeit einer aussagenlogischen Formel festzustellen gibt es mehrere Algorithmen.

1. Wahrheitstabelle. $O(n^2)$
2. Resolutionsbeweissystem: Die Grundlage schnellster Algorithmen zur Erfüllbarkeit
3.  Auf Resolution basierte Algorithmen: DP Algorithmus, DPLL Algorithmus und CDCL Algorithmus
4. Andere Beweissysteme: Hilbert-Kalkül, Sequenzenkalkuel, etc.
5. PTIME Algorithmen für Spezialfälle: Horn-Formeln, 2-SAT


## Erfüllbarkeit in der Prädikatenlogik

Gegeben eine [Struktur](Struktur.md) $\mathfrak S = (D, I)$ mit der [Signatur](Logik%20und%20Semantik%20von%20Programiersprachen/Signatur.md) $\sigma$, eine Bewertung $\nu$ auf $\mathfrak S$, und eine $FO(\sigma)$-Formel $\varphi$, wir definieren jetzt durch Induktion das Konzept der Erfülbarkeit. d.h. die Bedeutung davon dass $\varphi$ wahr mit Bezug auf $\mathfrak S$ ist (auch so genannt $\mathfrak S, \nu$ erfüllt $\varphi$), was auch als $(\mathfrak S, \nu) \vDash \varphi$ geschrieben wird.

1. Falls $\varphi := R(t_1, \dots t_n)$, dann $(\mathfrak S, \nu) \vDash \varphi$ genau dann wenn $(\textbf(val)(t_1), \dots, \textbf{val}(t_r)) \in I(R)$
2. Falls $\varphi := t_1 = t_2$, dann $(\mathfrak S, \nu) \vDash t_1 = t_2$ genau dann wenn $\textbf(val)(t_1) =  \textbf{val}(t_2)$. Beachten Sie, dass das letzte Vorkommen von $=$ die Gleichheitsrelation auf $D$ bedeutet.
3. Falls $\varphi := \psi_1 \land \psi_2$, wobei $\psi_1, \psi_2 \in FO(\sigma)$, dann $(\mathfrak S, \nu) \vDash \psi_1 \land \psi 2$ genau dann wenn $(\mathfrak S, \nu) \vDash \psi_1$ und $(\mathfrak S, \nu) \vDash \psi_2$
4. Falls $\varphi := \psi_1 \lor \psi_2$, wobei $\psi_1, \psi_2 \in FO(\sigma)$, dann $(\mathfrak S, \nu) \vDash \psi_1 \lor \psi 2$ genau dann wenn $(\mathfrak S, \nu) \vDash \psi_1$ oder $(\mathfrak S, \nu) \vDash \psi_2$
5. Falls $\varphi := \neg \psi$, wobei $\psi \in FO(\sigma)$, dann $(\mathfrak S, \nu) \vDash \neg \psi$ genau dann wenn es nicht der Fall ist, dass $(\mathfrak S, \nu) \vDash \psi$. Letzteres wird auch als $(\mathfrak S, \nu) \not \vDash \psi$ geschrieben
6. Falls $\varphi:= \forall x\psi$, wobei $\psi \in FO(\sigma)$, dann $(\mathfrak S, \nu) \vDash \forall x\psi$ genau dann wenn es für jedes $s\in D$ der Fall ist, dass $\mathfrak S, \nu' \vDash \psi$, wobei $\nu' :=\nu{[s/x]}$. (Gegeben eine Funktion $f : S_1 \to S_2$ und Elemente $s_1 \in S_1$ und $s_2 \in S_2$, schreiben wir $f[s_2/s_1]$, um die Funktion $f'$ zu bezeichnen, bei der $f'(s_1) = s_2$ und $f'(s'_1) =f(s'_{1})$ für jedes $s'_1 \not = s_1$ gilt) 
7. Falls $\varphi := \exists x\psi$, wobei $\psi \in FO(\sigma)$, dann $\mathfrak S \vDash \exists x \psi$ genau dann wenn es ein Element $s\in D$ gibt, wobei $(\mathfrak S, \nu') \vDash \psi$. Hier wird $\nu'$ wie im letzten Punkt der Liste definiert.

Eine Formel $\varphi$ ist erfüllbar, wenn es eine [Struktur](Struktur.md) $\mathfrak S$ und eine [Bewertung](Bewertung.md) $\nu$ gibt, sodass $(\mathfrak S, \nu) \vDash \varphi$ gilt. 