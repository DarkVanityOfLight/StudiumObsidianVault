
Eine [Gruppe](Gruppe.md) ist eine [Struktur](Struktur.md) mit der [Signatur](Logik/Signatur.md), die ein binäres Funktionssymbol $\circ$ und das Identitätssymbol $e$ enthält, wobei die folgenden Anforderungen erfüllt sind:
1. $\circ$ ist [assoziativ](Assoziativgesetz.md)
2. Es existiert ein neutrales Element $e$
3. Jedes Element hat ein inverses Element $a^{-1}$, sodass $a\circ a^{-1} = e$

Diese Anforderungen sind FO-beschreibbar:

1. $$\forall a,b,c (a\circ (b \circ c) = (a\circ b) \circ c)$$
2. $\exists e \forall a(a\circ e = a)$
3. $\forall a\exists a^{-1}(a\circ a^-1 = e)$

