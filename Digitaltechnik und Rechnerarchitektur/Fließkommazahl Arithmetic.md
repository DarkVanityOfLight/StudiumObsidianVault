## Reelle Zahlen

Analog zu den $\mathbb N$  und $\mathbb Z$, könnten wir mit Axiomen und Definition starten und  die Korrektheit von Algorithmen beweisen.

Fuer die Reellen Zahlen $\mathbb R$ sollten wir die Folgenden Axiome aufstellen:
- Das [Körper](Körper.md) Axiom
- Die [Totalordnung](Totalordnung.md) zusammen mit:
	- $x + z \geq y + z \iff x \geq y$
	- $\texttt{if } x \geq 0 \texttt{ and } y \geq 0 \texttt{ then } x\cdot y \geq 0$
	- die Dedekind-Komplettheit (jede nicht leere Menge hat ein Supremum)

 Allerdings ist die Herangehensweise über Axiome hier nicht nützlich, da:
 - Wir werden keine Reellen Zahlen im Computer darstellen
 - Wir werden Reelle Zahlen approximativ darstellen

 ## Unendliche Radix-B Darstellung

 Analog zu den [[radix-B]] Zahlen könnten wir für eine unendliche [Folge](Mathe/Folgen.md)$x_{n}, x_{n-1}, ..., x_{1}, x_{0}, x_{-1}, x_{-2},...,$ aus  Zahlen die folgende Reelle Zahl konstruieren:
 $$\left(\sum\limits^{n}_{i=0} x_{i} \cdot B^{i}\right) + \left(\sum\limits^{-\infty}_{i=-1} x_{i}\cdot B^{i}\right)$$
 Allerdings steht uns nur endlich viel Speicherplatz im Computer zu, daher sind die unendlichen radix-B zahlen nicht brauchbar für irrationale Zahlen.
 Fuer [Rationale Zahlen](Rationale%20Zahlen.md) würden zwei endliche [Folgen](Mathe/Folgen.md) genügen, aber auch das wird bei Computern nicht benutzt. Stattdessen benutzt man fixed und floating point arithmetic.

 