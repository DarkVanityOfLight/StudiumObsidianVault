
An das Datagram werden die EDC(Error detection and correction bits) angehängt und über den Link versendet. Der Empfänger überprüft mithilfe der EDCs ob die Daten fehlerfrei angekommen sind.


## Parity Checking

Ein Parity Check besteht aus einem einzigem Bit das einen Einzelnen Fehler erkennen kann, dabei wird bei einem Even Parity das Parity Bit so gesetzt das die Anzahl an 1en gerade ist.
Dies ist auch in 2 Dimensionen möglich

## CRC

Cyclic Redundancy Checking ist mächtiger als Parity Bits, dafür werden natürlich die Daten Bits $D$ und ein Generatorpolynom $G$ aus $r+1$ bits benötigt. Dann werden $r$ nullen an die Daten angehängt und die Daten Bits $D'$ durch das Generatorpolynom $G$ geteilt(in Binär entspricht das XOR), die ersten $r$ Bits(von Links) des Rests werden dann anstatt der Nullen an die Daten gehängt, zum überprüfen werden nun einfach die Daten durch das Generatorpolynom geteilt, sollte es keine Fehler geben ist der Rest $0$.

CRC wird sowohl in Ethernet als auch in 802.11 WiFi verwendet.


