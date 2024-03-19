

## Preimage-Resistant

Eine Hash Funktion $h: \lbrace 0, 1 \rbrace^* \to \lbrace 0, 1\rbrace^b$ ist preimage resistent wenn es schwer ist für einen gegebenen Hash $h$ eine Nachricht $x$ mit $H(x) = h$ zu finden.

## Second Preimage-Resistant

Eine Hash Funktion ist second preimage resistent wenn es schwer ist für eine gegebene Nachricht $x_1$ eine zweite Nachricht $x_2 \not = x_1$ mit $H(x_1) = H(x_2)$ zu finden.


## Passwörter

Ein Server speichert den Hash eines Passworts, wobei der Hash preimage und second-preimage resistant ist. Falls Informationen des Servers öffentlich geteilt werden, bleiben die Passwörter geheim. Wenn der Client das Passwort $p$ sendet, wird $H(p)$ berechnet, $H(p)$ wird mit dem gespeicherten Hash verglichen, bei Gleichheit wurde das korrekte Passwort angegeben da $H$ second-image Resistant ist.

## Salted

Da die Hashfunktion $H$ deterministisch ist, passiert es wenn der User dasselbe Passwort bei zwei Servern benutzt, das sie auch den selben Hash speichern. Dies kann vermieden werden, indem  der Server zusätzlich noch zu jedem Passwort $p$ eine Zufallszahl(Salt) $r$ speichert. Der Hash ist dann $H(P\, XOR\, r)$. Da die Server wahrscheinlich verschieden Zufallszahlen verwenden, sehen die gespeicherten Werte komplett verschieden aus.