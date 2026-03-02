
[Endliche Automaten](Endliche%20Automaten.md) benötigen relativ viel Schreibaufwand und Platz für die Notation. Deshalb verwenden wir reguläre Ausdrücke.

Sei $\Sigma$ ein [Alphabet](Alphabet.md). Die [Menge](Mengen.md) $\text{Reg}(\Sigma)$ der regulären Ausdrücke über $\Sigma$ ist die kleinste Menge mit den folgenden Eigenschaften:

- $\emptyset \in \text{Reg}(\sigma), \varepsilon \in \text{Reg}(\Sigma), \Sigma\subseteq\text{Reg}(\Sigma)$ 
- Wenn $\alpha, \beta \in \text{Reg}(\Sigma)$, dann auch:
	- $\alpha \beta \in\text{Reg}(\Sigma)$,
	- $(\alpha | \beta) \in \text{Reg}(\Sigma)$,
	- $(\alpha)^* \in\text{Reg}(\Sigma)$

Statt $(\alpha | \beta)$ wird oft auch $(\alpha + \beta)$ geschrieben.

## Sprache eines regulären Ausdrucks

- $L(\emptyset) = \emptyset$, $L(\varepsilon) = \lbrace \varepsilon\rbrace$, $L(a) = \lbrace a\rbrace$ für $a\in\Sigma$
- $L(\alpha\beta) = L(\alpha)L(\beta)$
- $L(\alpha | \beta) = L(\alpha) \cup L(\beta)$
- $L(\alpha^*) = L(\alpha)^*$

