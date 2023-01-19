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


