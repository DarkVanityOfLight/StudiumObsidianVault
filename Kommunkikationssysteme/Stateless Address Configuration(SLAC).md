

SLAC wird genutzt um IPv6 Adressen einem Host zuzuordnen

1. Der Host gibt sich selbst eine Link-Local Adresse
2. Er schickt eine Neighbor Solicitation Nachricht mit seiner Link-Local Adresse
3. Falls er eine Neighbor Advertisement Nachricht erhält gibt er sich eine neue Adresse und wiederholt Schritt 2. Falls er keine Antwort erhält geht der Host davon aus das seine Adresse valid ist.
4. Der Host sendet eine Router Solicitation Nachricht mit seiner Link Local Adresse um eine globale IPv6 Adresse zu erhalten(Optional)
5. Wiederhole Schritt 2 und 3(DAD) für die globale IPv6

