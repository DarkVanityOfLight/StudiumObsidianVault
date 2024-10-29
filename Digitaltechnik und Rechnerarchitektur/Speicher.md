
Wörter in unserem Speicher und in den Registern haben keine Daten Typen und können unterschiedlich interpretiert werden.
Die Interpretation erfolgt allein durch die Befehle.

Außerdem haben alle Bitvektoren die selbe länge, die Unterschiedlichen längen haben unterschiedliche Namen:

|Name|Bitlaenge|Bytes|
|------|----------|------|
|Byte | 8 |1
|Halbes Wort| 16 | 2|
|Wort|32|4|
|Doppeltes Wort|64|8|


Moderne Architekturen verwenden Register der groesse $64$.

## Ordnung von Bytes

Viele Prozessoren können beides.

### Little Endian

|$Mem[4i + 3]$|$Mem[4i + 2]$|$Mem[4i + 2]$|$Mem[4i + 1]$ | $Mem[4i]$|
|-|-|-|-|
|$x_{31} ... x_{24}$ | $x_{23} ... x_{16}$| $x_{15} ... x_{8}$| $x_7 ... x_0$|

### Big Endian

|$Mem[4i]$|$Mem[4i + 1]$|$Mem[4i+2]$| $Mem[4i + 3]$|
|-|-|-|-|
|$x_{31} ... x_{24}$| $x_{23} ... x_{16}$| $x_{15}...x_{8}$| $x_7 ... x_0$|

---

Speicherzugriff ist insgesamt relativ kompliziert.

Die Adressierung alleine benötigt fast genauso viel Zeit wie das liefern der Daten selbst. Um die Laufzeit zu Armotisieren, wird der Speicher in Blöcke Organisiert, die mehrere Speicherwörter enthalten. Der Datenzugriff auf Blöcke kann auch als Paralleler Zugriff auf mehrere Speicherwörter betrachtet werden. 


## Adressierungsmodelle

Bisher haben wir nur die Direkte Adressierung betrachtet, es gibt jedoch viele weitere Möglichkeiten zu Adressieren, eine der wichtigsten ist die Indirekte Adressierung. Dabei ist die Speicheradresse der Inhalt eines Registers. Eine Verallgemeinerung dieser Adressierung ist die  Displacement Adressierung. Dabei ist die Adresse die Summe aus einem Register und einem durch das Befehlswort angegebenen Operator.

Diese Adressierungsmodelle existieren aus dem Grund, angenommen wir wollen auf einen Hauptspeicher mit 32 Bit Adressen zugreifen. Bei der direkten Adressierung müssen 32 Bit breite Adressen in Befehlswörtern untergebracht werden. Wenn Befehle aber ebenfalls nur 32 Bit sein sollen haben wir keinen Platz mehr für den Befehl Opcodes.

Deswegen müssen die Adressen mit der Hilfe von Registern berechnet werden.


---

Speicher kann auf verschiedene Arten Organisiert werden, [Stacks](Stacks.md), [Queues](Queue.md) oder [[RAM]]. Die Momentanen Implementierungen bevorzugen [[RAM]], wobei Speicher Zellen durch ihre eindeutige Adresse identifiziert werden.

