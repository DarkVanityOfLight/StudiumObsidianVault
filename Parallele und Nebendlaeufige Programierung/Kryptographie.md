Ein Kryptosystem ist eine [Menge](Mengen.md) an Algorithmen, die [sichere Kommunikation](Sichere%20Kommunikation.md) realisieren.
Kryptographie ist die Entwicklung und das Nutzen von Kryptosystemen. Kryptographische Schlüssel entscheiden, welche Variante des Kryptosystems verwendet wird.

## Klassifizierung

Es gibt verschiedene Arten Kryptographie/Kryptosysteme zu klassifizieren:

1. Nach dem Ziel: Vertraulichkeit(Verschlüsselung) oder Integrität
2. Nach der Art der Schlüssel:
	- Symmetrische: Zwei Prozesse haben denselben Schlüssel. Der Schlüssel muss geheim gehalten werden
	- Asymmetrische: Die Prozesse haben verschiedene Schlüssel. Nur manche Schlüssel müssen geheim gehalten werden.


## Symmetrische Verschlüsselung
$p_1$ und $p_2$ einigen sich auf einen geheimen Schlüssel $K$ mit einem Schlüsselgenerierungsalgorithmus. Die Nachricht $M$ wir zu $C = Enc(K, M)$ verschlüsselt beim Empfänger wird $C$ wieder zu $M=Dec(K, C)$ entschlüsselt.

## Message Authentication Codes

$p_1$ und $p_2$ einigen sich auf einen geheimen Schlüssel $K$ mit einem Schlüsselgenerierungsalgorithmus $MAC(K, M)$ erzeugt einen Code, der an die Nachricht angefügt wird.
Dann überprüft der Empfänger ob der erhaltene Code tatsächlich zur Nachricht passt. 

## Asymmetrische Verschlüsselung
Jeder Prozess generiert ein Schlüsselpaar bestehend aus einem public und einem private/secret key durch key generation algorithm KGen Public keys werden veröffentlicht.

## Digitale Signaturen
Jeder Prozess generiert ein Schlüsselpaar $(sk, pk)$, Public keys werden veroeffentlicht. Die Funktion $Sign(sk, M)$ berechnet Signatur fuer $M$, Verify verifiziert die Signatur