
Sei $\Delta$ eine Formelmenge. Man definiere 
$$Th(\Delta) := \lbrace \varphi : \Delta \vDash \varphi \rbrace$$


>[!DEFINITIOn] Axiomatisierung
>Eine _Axiomatisierung_ einer [Theorie](Theorien%20der%20ersten%20Stufe.md) $T$ ist eine [entscheidbare](Entscheidbar.md) [Menge](Mengen.md) $\Delta$, wobei $T = Th(\Delta)$. Eine Theorie ist _axiomatisierbar_ , wenn sie eine Axiomatisierung hat.


>[!SENTENCE] Satz
>Jede axiomatisierbare Theorie ist semi-entscheidbar



## Beweis

Man führt [Gilmores Methode](Gilmores%20Methode.md) für alle mögliche $\psi_{\Theta}$ "parallel" aus.

Sei $\psi_1, \psi_2, \dots$ die Auflistung aller [Saetze](Satz.md) in $\Delta \cup \lbrace \neg \varphi\rbrace$:

für $n=1,2, \dots,$ wiederhole Folgendes:
1. Man führe $n$ Schritte der Methode Gilmores auf $\bigwedge^{n}_{i=1} \psi_i$  aus
2. Ist die Ausgabe "YES"(unerfüllbar), gebe "YES" aus.

Wir schreiben $\Delta \vdash \varphi$, wenn Gilmores Methode "unerfüllbar" auf $E(SNF(\Delta \cup \lbrace \neg \varphi \rbrace))$ ausgibt.

Es gilt, dass 
$$\Delta \vDash \varphi \iff \Delta \vdash \varphi$$

Dieses Theorem ist ein einfaches Korollar des [Satz von Herbrand](Satz%20von%20Herbrand.md), sowie des [Grundresolutionstheorems](Grundresolutionstheorem.md)

