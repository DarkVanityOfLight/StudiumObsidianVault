TLS ist ein weit verbreitetes Sicherheitsprotokoll über der [Transport Layer](Transport%20Layer.md).

Die drei Ziele von TLS sind:
__Confidentially__ durch symmetrische Verschlüsselung
__Authentication__ durch public key cryptography
__Integrity__ durch kryptographisches Hashing

## Confidentially

Bob verschlüsselt seine Nachricht mit Alice Public key, Alice kann die Nachricht mit ihrem Private Key wieder entschlüsseln.

![conf](conf.png)
## Integrity

Alice unterschreibt ihre Nachricht indem sie sie mit einem Private key verschlüsselt. Bob kann mit Alice Public Key entschlüsseln und dadurch sichergehen das die nachricht valide ist(Genau umgekehrt zu Confidentially).
Da es relativ Aufwendig ist lange Nachrichten zu verschlüsseln wird ein Hash angewandt um einen "Fingerabdruck" von fester länge zu generieren.

![int](Kommunkikationssysteme/attachments/int.png)


## Authentication

Sogenannte Certification Authorities(CA) ordnen Public Keys zu gewissen Entitys E zu.

Diese Entity registriert ihren Public Key und identifiziert sich mit der CA. Die CA erstellt einen Certificat das die Identität von E mit E's public key identifiziert.

![auth](auth.png)



