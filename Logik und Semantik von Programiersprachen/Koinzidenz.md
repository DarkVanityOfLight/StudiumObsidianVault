Sei $\sigma$ eine [Signatur](Logik%20und%20Semantik%20von%20Programiersprachen/Signatur.md), $\mathfrak S$ eine $\sigma$-[Struktur](Struktur.md), und $\varphi \in FO(\sigma)$ eine Formel. Gegeben zwei Bewertungen $\mathcal v_1, \mathcal v_2$, die mit $\mathfrak S$ übereinstimmen, und $\mathfrak v_1(x) = \mathfrak v_2(x)$ für jedes $x\in FREE(\varphi)$, dann ist es der Fall, dass
$$(\mathfrak S, \mathcal v_1) \vDash \varphi \text{ g.dw. } (\mathfrak S, \mathcal v_2) \vDash \varphi$$

Dazu betrachten wir zuerst das Koinzidenslemma für Terme. Sei $\sigma$ eine [Signatur](Logik%20und%20Semantik%20von%20Programiersprachen/Signatur.md), $\mathfrak S = (D, I)$ eine $\sigma$-[Struktur](Struktur.md) und $t$ ein $\sigma$-[Term](Term.md). Gegeben zwei [Bewertungen](Bewertung.md) $\mathcal v_1, \mathcal v_2$, die mit $\mathfrak S$ passen, bei denen $v_1(x) = v_2(x)$ für jede in $t$ vorkommende Variable $x$, ist es der Fall, dass
$$\textbf{val}_{\mathfrak S, \mathcal v_1}(t) = \textbf{val}_{\mathfrak S, \mathcal v_2}(t)$$
Der Beweis verwendet [Strukturelle Induktion](Strukturelle%20Induktion.md) über den Term aufbau.
- Induktionsanfang: $t$ ist entweder ein Konstantensymbol $c$ oder die Variable $x$. In beiden Fällen gilt es,  dass $\textbf{val}_{\mathfrak S, \mathcal v_1}(t) = \textbf(val)_{\mathfrak S, \mathcal v_2}(t)$
- Induktionsschritt: $t$ hat die Form $f(t_1, \dots, t_r)$. Dann 
  $$\begin{align}
  \mathbf{val}_{\mathfrak S, \mathcal v_1}(f(l_1, \dots, l_r)) &= I(f)(\textbf{val}_{\mathfrak S, \mathcal v_1}(l_1), \dots, \mathbf{val}_{\mathfrak S, \mathcal v_1}(l_r))\\
  &= I(f)(\textbf{val}_{\mathfrak S, \mathcal v_2}(t_2), \dots, \textbf{val}_{\mathfrak S, \mathcal v_2}(t_r))\\
  &= \textbf{val}_{\mathfrak S, \mathcal v_2}(f(t_1, \dots, t_r))
  \end{align}$$


Nun zum Beweis des allgemeinen Lemmas:
Wir verwenden wieder [Strukturelle Induktion](Strukturelle%20Induktion.md) über den Formel aufbau.

- Induktionsanfang: $\varphi := R(t_1, \dots, t_r)$. Es gilt nun, dass $FREE(\varphi) = Var(\varphi)$. Aus dem Koinzidenzlemma für Terme folgt, dass $\textbf{val}_{\mathfrak S, \mathcal v_1}(t_i) =  \textbf{val}_{\mathfrak S, \mathcal v_2}(t_i)$  für jedes $i = 1, ... r$. Infolgedessen $$(\textbf{val}_{\mathfrak S, \mathcal v_1}(t_1), \dots, \textbf{val}_{\mathfrak S, \mathcal v_1} (t_r)) \in I(R) \text{ g.d.w } (\textbf{val}_{\mathfrak S, \mathcal v_2}(t_1), \dots , \textbf{val}_{\mathfrak S, \mathcal v_2}(t_r)) \in I(R)$$ Zusammenfassend: $(\mathfrak S, \mathcal v_1) \vDash R(t_1, \dots, t_r) \text{ g.d.w } (\mathfrak S, \mathcal v_2) \vDash R(t_1, \dots, t_r)$
- Induktionsanfang 2: $\varphi$ ist $t_1 = t_2$. Der Beweis ist wie der für den vorhergehenden Fall.
- Induktionsschritt 1: Boolesche Kombination. Der Beweis ist einfach.
- Induktionsschritt 2: $\varphi$ hat die Form $\forall x \psi$ oder $\exists x\psi$. Wir betrachten nur ersteres, weil ein ähnlicher Beweis für den Fall $\varphi := \exists x\psi$ funktioniert. Es gilt nun, dass $(\mathfrak S, \mathcal v_1)$ g.d.w. $(\mathfrak S, v_1[a/x]) \vDash \psi$ für jedes $a\in D$. Da $\mathcal v_1[a/x](y) = \mathcal v_2[a/x](y)$ für jedes $y\in FREE(\psi)$ gilt, folgt aus der Induktionsvoraussetzung, dass $$(\mathfrak S, \mathcal v_1[a/x])\vDash \psi \iff  (\mathfrak S, \mathcal v[a/x]) \vDash \psi$$ Dies bedeutet, dass $(\mathfrak S, \mathcal v_1[a/x]) \vDash \psi$ für jedes $a\in D$ g.d.w $(\mathfrak S, \mathcal v_2[a/x]) \vDash \psi$ für alle $a$ g.d.w. $(\mathfrak S, \mathcal v_2) \vDash \forall x\psi$.

Das Koinzidenzlemma resultiert in vereinfachter Notation.
