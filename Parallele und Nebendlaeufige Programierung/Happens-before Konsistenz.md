
fuer eine [Programmordnung](Programmordnung.md) $\text{P}\atop\rightarrow$ und eine [Synchronizes-with-Ordnung](Synchronizes-with-Ordnung.md) $\text{SW}\atop\rightarrow$ ist die __Happens-before-Ordnung__ $\text{HB}\atop\rightarrow$ die [reflexiv-transitive Hülle](Transitive%20Hülle.md) von ${\text{P}\atop\rightarrow}\cup{\text{SW}\atop\rightarrow}$. 

Ein Speichermodell erreicht __Happens-before-Konsistenz__ wenn es eine __Happens-before-Ordnung__ $\text{HB}\atop\rightarrow$ gibt, sodass für alle Lesezugriffe $r$ auf eine Variable $v$ einen Schreibzugriff $w$ auf $v$ beobachten darf, sofern gilt:
- $r$ ist nicht durch $\text{HB}\atop\rightarrow$ vor $w$ geordnet, also es gilt nicht $r{\text{HB}\atop\rightarrow}w$
- Es gibt keinen durch $\text{HB} \rightarrow$ geordneten zwischenzeitlichen Schreibzugriff $w'$, also es gilt nicht $w{\text{HB}\atop\rightarrow} w'{\text{HB}\atop\rightarrow} r$ 


Happens-before Konsistenz respektiert die Thread-lokale [Programmordnung](Programmordnung.md) im Bezug auf Lese und Schreibzugriffe auf dieselbe Variable.
Änderungen der Ausführungsreihenfolge ist erlaubt, solange dadurch keine lokalen Date- oder Kontrollabhängigkeit verletzt werden. Weitere Einschränkungen können durch Synchronisation erfolgen.


## Happens-before Speichermodell

Das Happens-before Speichermodell erfüllt:
- Synchronisations-Konsistenz
- Happens-before-Konsistenz

Das heißt, Lesezugriffe
- sehen den letzten Schreibzugriff auf eine volatile Variable 
- sehen keine zukünftigen Schreibzugriffe
- verpassen keine zwischenzeitlichen Schreibzugriffe