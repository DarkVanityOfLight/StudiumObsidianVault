
$200.23.16.0/21$
In binary:
$11001000 00010111 0010000 00000000$

Die letzten $21$ Bit können als Host Addressen genutzt werden.
Das heißt wir haben
$2^{11} - 2$ Adressen da die niedrigste als Router Adresse und die Höchste als Broadcast Adresse verwendet wird.

Allgemein gilt für die Anzahl an Adressen:
$2^{32-x} - 2$ wobei $x$ die Subnetzmaske ist.

---

Gebe die Routingadresse in Binär an

Interface A:
$200.23.16.0/21$
$x.x.00010$

Interface B:
$200.23.24.0/24$
$x.x.00011000$

Interface C:
200.23.24.0/21
$x.x.00011$

Longest Prefix matching:

$200.23.24.1$ ist in Subnetz $B$ da der längste Prefix(hier die ersten $24$ Bit) übereinstimmen.

Einfach gesagt, die größere Subnetzmaske bekommt die IP-Adresse

---

Adressbereich Interface A
$x.x.00010|000 00000001 - x.x.00010|111 11111110$
$200.23.16.1 - 200.23.23.254$

Adressbereich Interface B
$x.x.000 11000|0000001 - x.x.000 11000|11111110$
$200.23.24.1-200.23.23.254$

Adressbereich Interface C:
$x.x.00011|001 00000001 - x.x.00011|111 11111110$
$200.23.25.1 - 200.23.31.254$

---


