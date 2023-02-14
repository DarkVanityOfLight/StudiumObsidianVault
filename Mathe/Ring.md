Ein [kommutativer](Kommutativgesetz.md) Ring mit $1$ ist eine Menge $R$ zusammen mit zwei Verknüpfungen
$$\begin{align*}
+:& R\times R \to R, (a, b) \mapsto a+b\\
\cdot:& R\times R \to R, (a, b) \mapsto a\cdot b
\end{align*}$$

für die gilt
- $(R, +)$ ist eine abelsche Gruppe
- $(R, \cdot)$ ist ein [abelsches](Gruppe.md#Abelsch) [Monoid](Gruppe.md#Monoid)
- die Verknüpfungen sind [distributiv](Distributivgesetz.md)

---

Wir schreiben $0$ für das neutrale element  der [[Addition]] und $1$ für das Neutrale der [[Multiplikation]]. Weiter schreiben wir $-a$ für das additive Inverse von $a\in R$ und $a^{-1}$ für das multiplikative Inverse von $a$, falls dieses existiert.

Inverse bezüglich der [Multiplikation](Multiplikation) können in einem Ring $R$ existieren, müssen aber nicht. Klar ist, dass es für $0\in R$ kein multiplikatives Inverses geben kann, da immer
$$0\cdot a = (0+0) \cdot a = 0\cdot a + 0\cdot a$$
also
$$0\cdot a = 0$$
für alle $a\in R$. falls jedes Element außer der $0$ bezüglich der Multiplikation ein Inverses hat, spricht man von einem [Körper](Körper.md)
