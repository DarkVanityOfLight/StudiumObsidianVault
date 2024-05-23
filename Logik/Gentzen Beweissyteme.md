
Die Korrektheit und Vollständigkeit des Beweissystems ist ähnlich zu [Hilbert Beweissysteme](Hilbert%20Beweissysteme.md). Im Vergleich zu $\mathfrak F_0$ hat das sogenannte Natural Deduction System nur wenige Axiomen muster, aber dafür viele Inferenzregeln. Die Gentzen Beweissysteme sind typischerweise einfach in der Benutzung, jedoch eignen sich [Hilbert Beweissysteme](Hilbert%20Beweissysteme.md) besser dafür Metatheoreme zu beweisen.

Die Basisaussage in Natural Deduction Beweisen ist ein __sequent__.

$$(S, \alpha) \text{ wobei } S \subset PROP, \alpha \in PROP$$

## Interferenzregeln

Wir definieren die Relation $\vdash \subseteq 2^{PROP} \times PROP$ mit den Basisregeln:

- IS: $$\frac{}{\alpha\vdash \alpha}$$
- C1: $$\frac{S\vdash \alpha, \beta}{S\vdash \alpha \land \beta}$$
- D1: $$\frac{S\vdash \alpha}{S\vdash \alpha \lor \beta, \beta \lor \alpha}$$
- N1: $$\frac{S\vdash \alpha,\neg \alpha}{S\vdash \beta}$$
- MR: $$\frac{S\vdash\alpha}{S' \vdash \alpha} (S\subseteq S')$$
- C2: $$\frac{S\vdash \alpha \land \beta}{S\vdash \alpha, \beta}$$
- D1: $$\frac{S, \alpha \vdash \gamma | S, \beta\vdash \gamma}{S, \alpha\lor \beta \vdash \gamma}$$
- N2: $$\frac{S, \alpha \vdash \beta | S, \neg a \vdash \beta}{S\vdash \beta}$$
## Notation

| Notation | Bedeutung |
| ---- | ---- |
| $S\vdash \alpha, \beta$ | $S\vdash \alpha \text{ und } S\vdash \beta$ |
| $S_1 \vdash \alpha_1\|S_2 \vdash \alpha_2$ | $S_1 \vdash \alpha \text{ und } S_2 \vdash a_2$ |
| $S, \alpha_1, \dots, \alpha_n \beta$ | $S\cup \lbrace \alpha_1, \dots, \alpha_n \rbrace \vdash \beta$ |
| $\vdash \beta$ | $\emptyset \vdash \beta$ |


## Notation für Inferenzregeln

Eine Natural  Regel ist von der Form:
$$\frac{S_1 \vdash \alpha |\dots| S_n \vdash \alpha_n}{S\vdash \beta}$$

Dabei nennen wir $S_1\vdash \alpha |\dots|S_n\vdash\alpha$ die Annahmen
und $S\vdash \beta$ die Schlussfolgerung.
Die Interpretation einer solchen Regel ist das $S\vdash \beta$ aus dieser Regel aus den Annahmen hergeleitet werden kann.

## Axiom

Die Initial sequents Regel ist:
$$\frac{}{\alpha \vdash \alpha}$$

Dabei gibt es keine Annahmen.

## Beweise
Ein Beweis $S\vdash\alpha$ ist eine Sequenz von Sequents 
$$(S_1 \vdash \alpha_1), \dots, (S_n \vdash a_n)$$ mit $S_n = S$ und $\alpha_n = \alpha$.
Sodass jedes Sequent $S_i \vdash \alpha_i$ entweder 
1. das initiale Sequent ist, oder
2. durch eine Basisregel hergeleitet werden kann, wobei die Annahmen bereits in dem Beweis früher vorhanden sind

Gegeben ein Sequent $(S, \alpha)$, schreiben wir $S\vdash \alpha$ falls es ein Beweis gibt. So ein Sequent nennt man auch __Satz__

## Monotonie Regel
(MR) $$\frac{S\vdash \alpha}{S'\vdash \alpha} (S\subseteq S')$$

Intuitiv: Eine Aussage kann immer noch bewiesen werden, wenn man mehr Annahmen macht.

## Konjunktion Regel

(C1) $$\frac{S\vdash \alpha, \beta}{S\vdash \alpha \land \beta}$$
(C2)

$$\frac{S\vdash \alpha \land \beta}{S\vdash\beta}$$

C2 besteht aus zwei Regeln
$$\frac{S\vdash \alpha\land\beta}{S\vdash \alpha}$$

$$\frac{S\vdash \alpha\land\beta}{S\vdash \beta}$$

## Disjunktions Regeln

(D1) $$\frac{S\vdash \alpha}{S\vdash \alpha\lor\beta, \beta\lor \alpha}$$
(D2) $$\frac{S, \alpha \vdash \gamma | S,\beta \vdash \gamma}{S, \alpha \lor  \beta \vdash \gamma}$$
## Regeln für die Negation

(N1) $$\frac{S \vdash \alpha, \neg \alpha}{S\vdash \beta}$$
(Wiederspruch)

(N2) $$\frac{S, \alpha \vdash \beta | S, \neg \alpha \vdash \beta}{S\vdash \beta}$$
(Proof by cases)


## Hergeleitete Regel

Eine hergeleitete Regel ist eine Regel der Form 
$$\frac{S_1 \vdash \alpha_1 | \dots | S_n \vdash \alpha_n}{S\vdash \beta}$$
sodass $S\vdash \beta$ gilt falls die Annahmen gelten.

## Beweis einer hergeleiteten Regel

Ein __Beweis__ $$\frac{H_1 \vdash \beta_1 | \dots H_m \vdash \beta_m}{S\vdash \beta}$$
ist eine Sequenz $(S_1 \vdash \alpha_1), \dots, (S_n \vdash \alpha_n)$ von Sequenten sodass jedes Sequent $S_i \vdash \alpha_i$ entweder:
1. Ein Initialsequent oder ein von den $H_j \vdash \beta_j$ Sequents ist, oder:
2. kann durch eine Basisregel hergeleitet werden, wobei die Annahmen früher in dem Beweis vorkommen.


## Mehr hergeleitete Regeln

### Reductio ad absurdum
$$\frac{S, \neg \alpha\vdash \beta\neg \beta}{S\vdash \alpha}$$

### Implication elimination
$$\frac{S\vdash \alpha \to \beta}{S,\alpha \vdash \beta}$$
### Cut rule
$$\frac{S\vdash\alpha | S, \alpha \vdash\beta}{S\vdash \beta}$$

### Implication introduction
$$\frac{S, \alpha \vdash \beta}{S\vdash \alpha\to\beta}$$

