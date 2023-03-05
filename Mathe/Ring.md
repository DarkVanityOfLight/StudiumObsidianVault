


Ein [kommutativer](Kommutativgesetz.md) Ring mit $1$ ist eine Menge $R$ zusammen mit zwei Verknüpfungen
$$\begin{align*}
+:& R\times R \to R, (a, b) \mapsto a+b\\
\cdot:& R\times R \to R, (a, b) \mapsto a\cdot b
\end{align*}$$

für die gilt
- $(R, +)$ ist eine [abelsche](Gruppe.md#Abelsch) [Gruppe](Gruppe.md)
- $(R, \cdot)$ ist ein [abelsches](Gruppe.md#Abelsch) [Monoid](Gruppe.md#Monoid)
- die Verknüpfungen sind [distributiv](Distributivgesetz.md)
- die Multiplikation $\cdot$ ist [assoziativ](Assoziativgesetz.md)

Existiert darüber hinaus ein __Einselement__, d.h. es gibt ein Element $1\in R$ mit
$$a\cdot 1 = 1\cdot a = a$$
für alle $a\in R$, so spricht man von einem __Ring mit 1__ (als neutrales Element des [Monoids](Gruppe.md#Monoid) $(R, \cdot)$ ist die $1$ eindeutig) und ist
die Multiplikation $\cdot$ [kommutativ](Kommutativgesetz.md), d.h 
$$a\cdot b = b\cdot a$$
für alle $a, b \in R$, so nennt man $R$ einen kommutativen Ring.

---

Wir schreiben $0$ für das neutrale Element  der [[Addition]] und $1$ für das Neutrale der [[Multiplikation]]. Weiter schreiben wir $-a$ für das additive Inverse von $a\in R$ und $a^{-1}$ für das multiplikative Inverse von $a$, falls dieses existiert.

Inverse bezüglich der [Multiplikation](Multiplikation) können in einem Ring $R$ existieren, müssen aber nicht. Klar ist, dass es für $0\in R$ kein multiplikatives Inverses geben kann, da immer
$$0\cdot a = (0+0) \cdot a = 0\cdot a + 0\cdot a$$
also
$$0\cdot a = 0$$
für alle $a\in R$. falls jedes Element außer der $0$ bezüglich der Multiplikation ein Inverses hat, spricht man von einem [Körper](Körper.md)

## Nullteiler

$a\in R$ heißt Nullteiler von $R$, wenn $a$ die Null teilt, d.h. ein $0 \not= b\in R$ existiert mit $$a\cdot b = 0$$
## Einheit

Man bezeichnet ein Element $a\in R$ als Einheit, wenn $a$ die $1$ teilt, d.h. ein $b\in R$ existiert mit 
$$a\cdot b = 1$$
Die Menge der Einheiten $R^{\times}$ bildet bezüglich $\cdot$ eine Gruppe, die __Einheitengruppe__

---

Ein Element kann nicht sowohl Einheit als auch Nullteiler sein, denn ist $a$ eine Einheit und $a\cdot b = 0$, dann ist $a^{-1} ab =0$

## Unterring

Ist $\emptyset \not = U \subset R$ mit $+$ und $\cdot$ ein Ring, dann bezeichnen wir $U$ als __Unterring__ von $R$. Ist $R$ ein Ring mit $1$, so verlangen wir (in der Regel) außerdem $1\in U$.