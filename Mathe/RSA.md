Trapdoor-Einwegfunktion

$$\{\text{Klartextnachrichten}\} \rightleftarrows \{Veverschlüsselte Nachricht\}$$
§ Setup $N\in\mathbb N$ Nachrichten $0 \leq m < N$

Jeder Benutzer: 
1) Wähle $p, q$ prim mit $p\cdot q > N$
2) $n:= p \cdot q$
3) $\varphi(n) = (p-1) \cdot (q-1)$
4) $p, q$ löschen
5) Wähle $e\in\mathbb N$ $ggT(e, \varphi(n)) = 1$
6) $0<d<\varphi(n): e \cdot d \equiv 1 \mod \varphi(n)$
7) $\varphi(n)$ löschen

| |privat|öffemtlich|
|-|-|-|
|A| $d_A$ | $(n_{a}, e_{a})$|
|B| $d_b$| $(n_{B}, e_{B})$|

$B \underbrace{\to}_{m} A$

## Verschlüsseln

$c =m^{e_{A}} \mod n_{A}$
$ggT(m, n_{a)}= 1$ d.h. $\overline m \in (\mathbb Z\diagup n_{A})^{\times}$

Entschlüsseln:

$\tilde m = c^{d_{A}} \mod n_{A}$

$\mod n_A$
$\widetilde m \equiv c^{d_{A}}= (m^{e_A})^{d_{A}} = m^{l_{A}\cdot d_{A}} = m^{1 + k \cdot \varphi(n_{A)}}= m \cdot (m^{\varphi(n_{A})}) \equiv m \mod n_{A}$


---

## Setup

Für RSA wählt man eine große Zahl $N\in\mathbb N$ und codiert Nachrichteneinheiten in eine Zahl $0 \ge m < N$ (zum Beispiel $N = 26^k$ und repräsentiert Buchstaben durch Ziffern). In der Praxis verwendet man ein $N$ mit etwa $200$ bis $600$ Dezimalziffern.
Jeder Benutzer führt nun die folgenden Schritte aus:

1. Wähle $2$ Primzahlen mit $p\cdot q > N$. Man beachte, dass es nach dem [Primzahlsatz](Primzahlsatz.md) genügend Primzahlen gibt.
2. Berechne $n:= p\cdot q$ und den Wert der [Eulerischen Phi Funktion](Eulerische%20Phi%20Funktion.md) $$\varphi(n) = (p-1)(q-1)$$Die Zahlen $p$ und $q$ können nun gelöscht werden. Es ist keine effiziente Methode bekannt, um $\varphi(n)$ zu berechnen ohne die Faktorisierung $n = p\cdot q$ zu bestimmen.
3. Wähle eine Zahl $e\in\mathbb N$  mit $ggT(e, \varphi(n)) = 1$
4. Berechne das Inverse $0 < d < \varphi(n)$ von $e$ modulo $\varphi(n)$, also mit $$ed \equiv 1 \mod \varphi(n)$$ Nun kann $\varphi(n)$ gelöscht werden. Der öffentliche Schlüssel ist das Tupel $(n, e)$ und der private Schlüssel $d$.

## Nachrichtenuebertragung

Betrachten wir nun zwei Personen Alice und Bob mit Schlüsseln

$$
\begin{array}{|c|c|c|}
\hline
 & \text{privat} & \text{öffentlich} \\
\hline
\text{Alice} & d_A &(n_A, e_A)  \\
\hline
\text{Bob} & d_B &(n_B, e_B)  \\
\hline
\end{array}
$$

Will Bob an Alice eine Nachricht $m$ senden, berechnet er mit Hilfe des öffentlichen Schlüssels von Alice
$$c:= m^{eA} \mod n_{A}$$
und überträgt $c$ an Alice. Wir nehmen an, dass $ggT(m, n_{A}) = 1$ was mit sehr hoher Wahrscheinlichkeit der Fall ist (anderenfalls hat $B$ einen Teiler von $n_{A}$ gefunden und kann damit den privaten Schlüssel von $A$ berechnen). Somit repräsentiert $m$ ein Element in $(\mathbb Z/n_{A})^{\times}$. Alice berechnet nun zum Entschlüsseln mit Hilfe von ihrem privaten Schlüssel
$$\stackrel{\sim}{m} := c^{d_{A}}\mod n_{A}$$
Dann gilt modulo $n_A$, dass
$$\stackrel{\sim}{m} \equiv c^{d_{A}} \equiv (m^{e_{A}})^{d_{A}} = m^{e_{A}d_{A}} = m^{1+k\cdot\varphi(n_{A})} = m \cdot (m^{\varphi(n_{A})})^{k} \equiv m \mod n_{A}$$
