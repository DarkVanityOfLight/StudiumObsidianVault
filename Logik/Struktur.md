---
title: Struktur
aliases:
  - structure
---


> Die __Struktur__ stimmt mit der [[Mathe/Signatur]](siehe auch [Signatur](Mathe/Signatur.md) und [Signatur](Grundlagen%20der%20Programmierung/Signatur.md)) $\sigma$ überein.


Ein Beispiel einer Struktur ist ein [Modell](Modell.md) einer bestimmten mathematischen Theorie. Beispielsweise können [Prädikatenlogische](Logik/Prädikatenlogik.md) Formeln mit der Signatur $\sigma_{\mathbb N}$ mit Bezug auf einem Standardmodell $\mathcal N$ der Zahlentheorie interpretiert werden, wobei $<, +$ und $\times$ als kleiner als, Addition und Multiplikations Operatoen, bzw. $0$ und $1$ als die Zahlen $0$ und $1$ verstanden werden. 

Eine Struktur $\mathfrak S$ gibt Interpretationen von Funktions und Relationssymbolen an. Eine Struktur über der Signatur $\sigma$ (Abgekürzt $\sigma$-Struktur) ist ein Paar $\mathfrak S = (D, I)$, wobei das sogenannte [Domain](Domain.md)(auch Grundmenge genannt)  $D$ eine nicht leere [Menge](Mengen.md) ist, und die sogenannte __Interpretation__ den Symbolen in $\sigma$ gewisse "Bedeutung" zuordnet, d.h. $I$ ordnet einem $r$-stelligem Funktionssymbol $f\in \sigma$ eine Funktion $I(f): D^{r} \to D$ bzw. einem $r$-stelligen Relationssymbol $R\in\sigma$ eine $r$ stellige Relation $I(R) \subseteq D^{r}$. Daraus folgt das einem Konstantensymbol $c$ ein Element $I(c) \in D$ zugeordnet wird. Ferner ist $I(=)$ die Gleichheitsrelation auf $D$. Wir  verwenden die Notation $=$, um diese Gleichheitsrelation $I(=)$ zu bezeichnen.
