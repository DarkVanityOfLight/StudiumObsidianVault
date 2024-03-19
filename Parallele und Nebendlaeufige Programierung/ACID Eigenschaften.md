

__Atomicity:__ Eine Aktion wird entweder vollständig oder gar nicht ausgeführt

__Consistency:__ Eine Aktion führt von einem im Sinne der Anwendung konsistenten Zustand in einen konsistenten Folgezustand.

__Isolation:__ Zwischenergebnisse sind für andere Aktionen nicht sichtbar.

__Durability:__ Eine beendete Aktion kann nicht mehr rückgängig gemacht werden


## Gemeinsame Objekte/Variablen

Variablen/Objekte können von mehreren Threads genutzt werden, hier kann es sich entweder um Lese oder Schreibzugriffe handeln.

Zu beachten ist:
- Änderungen in einem Thread sollen im anderen sichtbar sein
- Die Reihenfolge der Operationen muss klar definiert sein
- Zugriffe zur gleichen Zeit sollten im Allgemeinen vermieden werden

durch compiler Optimierungen kann es geschehen dass es nicht bemerkt wird wenn ein anderer Thread einen Wert abändert.


### Volatile

hiermit wird dem Compiler mitgeteilt welche Variablen von mehreren Threads genutzt werden, dann werden Optimierungen für diese Variablen nicht durchgeführt, dazu sollten volatile Variablen unabhängig von anderen Variablen sein.


### Atomare Datentypen

Man kann auch sogenannte atomare Datentypen verwenden, die ohne Locks arbeiten und mehrere atomare Operationen anbieten

## Gemeinsame Objekte und Locks

Wenn ein Objekt geändert wird, soll oft kein andere Thread Änderungen an dem Objekt durchführen, dazu wird ein __Lock__ auf das Objekt gesetzt. Locks können so gesetzt werden, dass sie nur für manche Operationen gelten, die auf dem Objekt ausgeführt werden können.

Objekt und Methoden Locks werden in Java durch `synchronized` realisiert.

Es kann sein, dass sich beim Ausführen von Anweisungen, die ein Lock erzeugen herausstellt, dass erst fortgefahren werden kann, nachdem ein anderer Thread Operationen ausführt. Dann wird das Lock abgegeben und gewartet, die Methoden die zuerst passieren muss, muss dann dem wartenden Thread mitteilen, wann es möglich ist fortzufahren, dazu wird in Java `wait(), notify(), notifyAll()` verwendet

## Semaphor

Eine Semaphor ist ein Konzept zur Verwaltung von Ressourcen, es gibt einen Zähler der nie negativ werden darf, Falls der Zähler $0$ ist, werden Ressourcen nicht mehr zugewiesen und es wird gewartet

