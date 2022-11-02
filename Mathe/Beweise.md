# Beweismethoden
Ein mathematischer Satz enthält meist Voraussetzung und Behauptung, verbunden durch [Implikation](Aussagen.md).

Aus [Aussage](Elementare%20Logik.md#Aussageform) $A$ folgt Aussage $B$ dh. $A\implies B$
-> Satz ([Lemma](Elementare%20Logik.md), [Proposition](Elementare%20Logik.md), [Corollar](Elementare%20Logik.md))
Allg Aussagen $A(x), x\in M$
## Beispiel
$\forall x \in \mathbb Q$ist
$x^2 \geq 0$


## Der direkte Beweis
Zeige $A \implies B$ zeige dazu $A\implies C\implies B$
Aus der Voraussetzung A wird die Behauptung B direkt gefolgert, wir beweisen folgenden Satz als Beispiel:
![Gerade natürliche Zahlen](Gerade%20natürliche%20Zahlen.md)

---

## Der indirekte Beweis(Widerspruchsbeweis)
Ist der zu beweisende Satz eine Aussage A, so zeigen wir äquivalent, dass $\neg A$ falsch ist, also dass die negierte Aussage zu einem Widerspruch führt.
![Gerade Potenzen](Gerade%20Potenzen.md)

---

## Beweis durch Gegenbeispiel
Dies ist möglich in dem Fall, dass man eine [Universalaussage](Quantoren.md#Allquantor)  $A(\forall)$ widerlegen möchte. Um zu zeigen, dass $A$ falsch ist, zeigt man dass $\neg A (\exists)$ wahr ist, indem man die Existenz von einem solchen Element zeigt.

---
## Beweis durch Ringschluss
Ist die Äquivalenz mehrer Aussagen zu zeigen, so erspart einem der Beweis durch RIngschluss viel Arbeit