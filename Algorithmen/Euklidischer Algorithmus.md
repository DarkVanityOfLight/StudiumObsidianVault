# Der euklidische Algorithmus
Um den grössten gemeinsamen Teiler zweier Zahlen $a$ und $b$, also den $ggT(a, b)$ zu berechnen führt man nacheinander mehrere Divisionen mit Rest aus. Dabei werden Divisor und Rest im 1. Schritt zu Dividend und Divisor im 2. Schritt. Weiter werden Divisor und Rest im 2. Schritt zu Dividend und Divisor im 3. Schritt usw. Dieses Verfahren führt man solange durch bis die Division ohne Rest aufgeht. Der Divisor im letzten Schritt ist der grösste gemeinsame Teiler.

## Beispiel
> Der groesste gemeinsame Teiler von 2160 und 2592 ist 432, denn

$$1. Schritt: \ 2160 : 2592 = 0\ Rest\ 2160$$
$$2. Schritt:\ 2592:2160 = 1\ Rest\ 432$$
$$3. Schritt:\ 2160 : 432 =  5 \ \ Rest\ \ 0$$
Der letzte Divisor - und das ist nach dem Euklidischen Algorithmus der $ggT$ - ist 432. Damit können nun die beiden Brüche $2592 \over 2160$ und $2160 \over 2592$ so gekürzt werden, dass Nenner und Zähler ganzzahlig bleiben: $${2592 \over 2160} = {6 \cdot \cancel{432} \over 5 \cdot \cancel{432}} = {6 \over 5}$$
$${2160 \over 2592} = {5 \cdot \cancel{432} \over 6 \cdot \cancel{432}} = {5 \over 6}$$