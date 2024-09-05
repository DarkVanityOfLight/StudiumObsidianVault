
> Marcel Wirdel, Kilian Lichtner
## Aufgabe 1

### a)

1. `CREATE INDEX idx_mitarbeiter_name_abteilung ON mitarbeiter (name, abteilung);` 
   Ein zusammengesetzter Index auf den Spalten `name` und `abteilung` ist optimal, da die Anfrage beide Spalten in der WHERE-Klausel verwendet.
2. `CREATE INDEX idx_kunde_ort_regjahr_guthaben ON kunde (ort, reg_jahr, guthaben);`
   Ein Index, der die Spalten `ort`, `reg_jahr` und `guthaben` kombiniert, ist geeignet, weil die Anfrage eine OR-Bedingung für `ort` und `reg_jahr` sowie eine Bereichsbedingung für `guthaben` enthält.
3. `CREATE INDEX idx_bestellung_status_kid ON bestellung (status, kid);`
   Ein Index auf `status` und `kid` in der Tabelle `bestellung` ist hier am vorteilhaftesten. Der status wird in der WHERE-Klausel verwendet, und der `kid` wird in der JOIN-Bedingung benötigt.

### b)

1. Dieser Index hilft nicht viel, da die Spaltenreihenfolge nicht optimal ist. `nachname` und `adresse` sind in der WHERE-Klausel nicht enthalten. `kragenweite` könnte helfen, aber nur, wenn die ersten Spalten des Indexes auch in der WHERE-Klausel verwendet würden. 
2. Dieser Index ist besser geeignet, weil `kragenweite` und `alter` in der WHERE-Klausel verwendet werden. Der Index kann für die Bedingungen auf `kragenweite` und `alter` genutzt werden.
3. Hash-Indizes sind nicht gut für Bereichsabfragen `(alter < 40)` geeignet, da sie nur für exakte Suchanfragen effizient sind. Diese Art von Index wäre daher nicht optimal. 
4. Hash-Index auf `kragenweite` Verwendung: Dieser Index wäre teilweise nützlich für die Bedingung `kragenweite = 43 OR kragenweite = 45`, aber da es ein Hash-Index ist, würde er nicht für die Bereichsabfrage `alter < 40` helfen. 

## Aufgabe 2
![Drawing 2024-07-07 13.27.18.excalidraw](Drawing%202024-07-07%2013.27.18.excalidraw.md)

## Aufgabe 3
Es gilt $\sigma_{\theta_1}(R) \cap \sigma_{\theta_2}(R) \equiv \sigma_{\theta_1}\sigma_{\theta_2}(R) \equiv \sigma_{\theta_1\land\theta_2}(R)$ 
Dies folgt direkt aus der Distributivitaet von $\sigma$ mit $\cap$.
Wir erhalten nur noch einen Natural Join anstatt zwei Cross Joins/2 Natural Joins.

![250](Drawing%202024-07-07%2014.32.16.excalidraw.md)

  
## Aufgabe 4

### a)
![](Pasted%20image%2020240707160404.png)

![](Pasted%20image%2020240707160351.png)

### b)
Häufigkeit von Zahlen kleiner oder gleich 13
### 1.
$12+17+10+14+12+14+15/2=76.5$
### 2.
$29+24+26+40/4=109$
### 3.
$13\cdot 7.5 =97.5$
### 4. 
$\int_{1}^{13}p(x)dx=157.94$

Häufigkeit von Zahlen im Intervall $[17,20]$
### 1.
$19+12=31$
### 2.
31
### 3.
$4\cdot 7.5=30$
### 4.
$\int_{17}^{20}p(x)dx=34.68$

## Fehler
Für Zahlen $\le 13$ (Tatsächliche Häufigkeit $88$):
- $H_2$ $\frac{76.5-88}{88}=-0.1306$ ($13.06\%$ Fehler)
- $H_{4}$ $\frac{109-88}{88}=0.2386$ ($23.86\%$ Fehler)
- Gleichverteilung $\frac{97.5-88}{88}=0.107$ ($10.7\%$ Fehler)
- Polynom $\frac{157.94-88}{88}=0.794$ ($79.4\%$ Fehler)

Für Zahlen im Intervall $[17,20]$ (Tatsächliche Häufigkeit 31):
-  $H_2$ $\frac{31-31}{31}=0$ ($0\%$ Fehler)
- $H_{4}$ $\frac{31-31}{31}=0$ ($0\%$ Fehler)
- Gleichverteilung $\frac{30-31}{31}=-0.032$ ($3.2\%$ Fehler)
- Polynom $\frac{34.68-31}{31}=0.1187$ ($11.87\%$ Fehler)
### c)
Intervalle: $[1,6],[6,11],[11,16],[16,21]$ 
Häufigkeiten Für Intervalle:
- $[1,6]: 33$
- $[6,15]: 61$
- $[15,19]: 44$
- $[19,21]: 12$

SSE für $H_4$ :
$$\begin{align*}
&(5-7.25)^{2}+(7-7.25)^{2}+(10-7.25)^{2}+(7-7.25)^2\\
&+(4-6)^2+(6-6)^2+(8-6)^2+(6-6)^2+(8-6.5)^2+(4-6.5)^2\\
&+(8-6.5)^2+(6-6.5)^2+(9-10)^2+(12-10)^2+(13-10)^2+(6-10)^2\\
&+(10-7.75)^2+(9-7.75)^2+(4-7.75)^2+(8-7.75)^2\\
&= 82.5
\end{align*}$$
SSE für optimiertes Histogramm:
$$\begin{align*}
&(5-6.6)^{2}+(7-6.6)^{2}+(10-6.6)^{2}+(7-6.6)^2\\
&+(4-6.6)^2+(6-7.625)^2+(8-7.625)^2+(6-7.625)^2+(8-7.625)^2+(4-7.625)^2\\
&+(8-7.625)^2+(6-7.625)^2+(9-7.625)^2+(12-11)^2+(13-11)^2+(6-7.625)^2\\
&+(10-11)^2+(9-11)^2+(4-6)^2+(8-6)^2\\
&= 65.8325
\end{align*}$$
