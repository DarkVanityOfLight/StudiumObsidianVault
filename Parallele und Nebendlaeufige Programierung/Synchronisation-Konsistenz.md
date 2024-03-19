Wir bezeichnen Zugriffe auf Locks sowie auf als `volatile` deklarierte Variablen als Synchronisationsereignisse.

Sei $E_s$ die [Menge](Mengen.md) an Synchronisationsereignissen.


## Synchronisationsordnung

Eine __Synchronisationsordnung__ $\text{S} \atop\rightarrow$ ist eine [Totalordnung](Totalordnung.md) auf der [Menge](Mengen.md) der Synchronsiationsereignissen.


## Synchronsiations-Konsistenz

Synchronisations-Konsistenz bedeutet, dass für eine [Programmordnung](Programmordnung.md) $\text{P} \atop\rightarrow$ und eine Synchronisationsordnung $\text{S}\atop\rightarrow$
gilt:
- für $e, e'$ aus dem gleichen Thread, $e, e'\in E_s : e{\text{P}\atop\rightarrow} e' \implies e {\text{S}\atop\rightarrow} e'$($\text{S}\atop\rightarrow$ konsistent mit $\text{P}\atop\rightarrow$)
- Ein Lesezugriff auf eine als `volatile` deklarierte Variable liefert den laut $\text{S}\atop\rightarrow$ letzten geschriebenen Wert zurück

