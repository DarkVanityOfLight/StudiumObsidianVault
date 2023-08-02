
Wie wird ein Bit auf eine Sequenz von Signalleveln Kodiert?

Ein Encoding Schema sollte folgende Eigenschaften besitzen:

- Selbsttaktung
- Verringerung des Baseline-Drifts
- Verringerung der benötigten Übertragungsbandbreite

## Bit Rate vs. Symbol Rate(Baud)

Ein Symbol ist ein Signal-level oder eine Veränderung des Signal-levels.

Ein Symbol kann mehrere Bits Darstellen dadurch kann es Passieren das $\frac{bit}{s}> baud$, aber genauso kann es sein das mehrere Symbole für ein Bit benötigt werden.

## Non-Return To Zero

NRZ ist eine einfaches Encoding bei dem eine $1$ einer Hohen Spannung entspricht und $0$ einer geringen, dabei wird die Spannung jedoch niemals wieder $0$. NRZ hat eine gute Verwertung der Bandbreite da ein Symbol einem Bit entspricht. 
Es ist jedoch anfaellig für Baseline-Drift und ist außerdem nicht Selbsttacktend.

![nrz](nrz.png)

## Non-Return To Zero Inverted

Bei NRZ-I wird anstatt durch den Spannungswert, durch eine Spannungsänderung eine $1$ angezeigt. Dadurch wird das Problem mit Aufeinanderfolgenden $1$en geloest, nicht jedoch aufeinanderfolgende $0$en, weiterhin fehlt hier auch die Selbsttacktung.

![nrzi](nrzi.png)

## Manchester Encoding

Beim Manchester-Encoding wird ein Bit durch $2$  Signale dargestellt, dabei ist der erste Teil des Signals das Bit selbst und der zweite Teil das Invertierte Bit. Dadurch wird Selbsttacktung möglich und wir haben maximal zwei aufeinanderfolgende Highs/Lows. Allerdings benötigt man eben 2 Symbole per Bit also pro Baud erhält man nur 0.5 bit.

![manchester](manchester.png)


## 4B4B

Bei 4B-5B wird jede $4$ bit Sequenz auf eine $5$ Bit Sequenz abgebildet und diese dann mit [NRZ-I](#Non-Return%20To%20Zero%20Inverted) auf das Medium uebertragen. Durch die Abbildung auf $5$ Bit gibt es niemals mehr als 3 Konsekutive Nullen und dank [NRZ-I](#Non-Return%20To%20Zero%20Inverted) gibt es keine Konsekutiven Einsen.


