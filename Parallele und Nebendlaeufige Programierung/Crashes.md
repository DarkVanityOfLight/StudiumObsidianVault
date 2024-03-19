[Prozesse](Prozess.md) können komplett ausfallen, bzw. die Nachrichten eines Prozesses kommen nicht mehr an. Falls der Prozess Teil eines Gesamtprozesses ist, kann da heißen, dass der Gesamtprozess nicht (wie erwartet) terminiert.

Ein Prozess der seine Ereignisse wie erwartet ausführt heißt _korrekt_.

## Redundanz

Es muss mehr als einen Prozess geben, der eine Teilaufgabe im System ausführen kann.

Ein Prozess ist der Primary, der die Aufgabe ausfuehrt und die anderen Prozesse ueber Fortschritte informiert. Falls der Primary nicht mehr reagiert, uebernimmt ein anderer Prozess die Rolle des Primary. Ein solcher Wechsel wird als view change bezeichnet.


### Replikation von Zustandsautomaten
Replikation von Zustandsautomaten bedeutet, dass eine Menge an Prozessen $p_1, \dots, p_r$ dieselben Operationen in identischer Reihenfolge ausführt.

