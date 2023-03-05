Wir wollen nun Division mit Rest, den Euklidischen Algorithmus  
und die Lösung von simultanen Kongruenzen auf den Polynom-  
ring übertragen. Diese Algorithmen funktionieren völlig analog  
zu denen in $\mathbb Z$. Wir formulieren zunächst das allgemeine Prinzip  
dahinter:

Ein __euklidischer Ring__ ist ein kommutativer [Ring](Ring.md) mit $1\not = 0$ ohne nicht-triviale Nullteiler (d.h. $0$ ist der einzige Nullteiler) einer Abbildung
$$d: R\setminus\lbrace 0 \rbrace \to \mathbb N_{0}$$
sodass für je zwei Elemente $a, b \in R\setminus\lbrace 0\rbrace$ Elemente $g, r \in R$ existieren mit 
1. $a = g\cdot b + r$ 
2. $r= 0$ oder $d(r) < d(b)$

Wir bezeichnen dies als Division von $a$ durch $b$ mit Rest $r$. Die Abbildung $d$ heißt __euklidische Norm__.
