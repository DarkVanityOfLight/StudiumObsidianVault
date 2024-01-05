
## Negationsnormalform (NNF)

Eine Formel ist in der Negationsnormalform(NNF), wenn jede Negation direkt vor einer [Relation](Relation.md) vorkommt. Als Beispiel sind die Formeln $\neg \exists (x = x+1)$ und $\forall x\neg\neg R(x, y)$ nicht in NNF. Die erste Formel ist nicht in NNF, weil der Quantor $\exists$  zwischen $\neg$ und der Relation steht. Die zweite Formeln ist nicht in NNF, denn eine Negation steht direkt rechts neben der ersten Negation $\neg$.

>[!DEFINTION] Theorem
>Eine FO-Formel lässt sich automatisch in eine Formel in NNF mit linearer Größe umwandeln. Das Verfahren läuft in Polynomialzeit


## Pränexnormalform(PNF)

Eine Formel ist in Pränexnormalform(PNF), wenn sie der folgenden Art ist:
$$\mathcal Q_1 x_1 \dots \mathcal Q_n x_n\psi$$
wobei $\mathcal Q_i\in\lbrace \forall, \exists \rbrace$ und jedes $\psi$ quantorenfrei ist.

## Skolemnormalform(SNF)

Eine Formel ist in Skolemnormalform, wenn es kein Vorkommen von Existenzquantoren gibt. So eine Formel wird auch eine __universelle__ Formel genannt. Im Allgemeinen ist es nicht immer möglich, eine äquivalente Formel in SNF umzuwandeln. Allerdings lässt sich eine Formel in eine [Erfüllbarkeitsäquivalente](Erfüllbarkeitsäquivalent.md) Formel in SNF umwandeln. Dazu ist die resultierende Formel mit zusätzlichen Funktionssymbolen bereichert. 

### Beispiel

$$\forall x\exists y E(x, y)$$

Eine Erfüllbarkeitsäquivalente Formel in SNF ist $\forall x E(x, f(x))$, bei der $f$ ein neues Funktionssymbol ist, das nicht in der ursprünglichen Signatur ist. Grob gesagt hat $f$ die Bedeutung einer "Auswahlfunktion", die ein Element im Universum je nach $x$ auswählt. Infolgedessen erhält die resultierende Formel die Bedeutung der originellen Formel modulo Erfüllbarkeit.

>[!DEFINTION] Theorem
> Die Formel 
> $$\varphi := \forall x_1, \dots, x_n\exists y \psi$$
> ist Erfuellbarkeitsaequivalent zur Formel
> $$\varphi' := \forall x_1, \dots, x_n \psi[f(x_1, \dots, x_n)/y]$$

bei der $f$ ein $n$-stelliges Funktionssymbol ist, das nicht in $\varphi$ vorkommt.

