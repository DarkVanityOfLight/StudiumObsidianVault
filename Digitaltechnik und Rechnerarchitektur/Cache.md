
Wie können wir wissen ob ein Speicher Wort im Cache ist. 
Wir betrachten $l$ Speicher Level, wobei $\text{Mem}_l$  der [Hauptspeicher](Speicher.md) ist.
$$\text{Mem}_1[0\dots size_1 - 1], \dots, \text{Mem}_l[0\dots size_l - 1]$$ mit $size_1 < size_2 < \dots size_l$.

$adr_k(a_l)$ ist die Adresse eines Speicherwortes $a_l$ im Cache mit dem Level $k$.
Die Definition von $adr_k(a_l)$ ist unterschiedlich für die Verschiedenen Cache Arten

## Direkte Zuweisung

Wir weisen einem einzelnem Wort $adr_k(a_l) := (a_l \mod size_k)$ zu, wir betrachten also die kleinsten Adress Bits.

![dmmw](dmmw.png)

Dabei werden mehre Adressen auf dem Level $k+1$ auf die selbe Adresse auf dem Level $k$ Abgebildet, deshalb Speichern wir neben den Daten auch noch die übrige Adresse auf dem Level $k$. Verwenden wir also $adr_k (a_l) := (a_l \mod size_k)$, dann müssen wir auch noch einen Tag $tag_k(a_l) := (a_l \div size_k)$. Dann ist im Speicher $\text{Mem}_k[i]$, das Speicherwort mit der Adresse $a_l := tag_k[i] \times size_{k} + i$.

Außerdem Speichern wir Flaggen $\text{Valid}_k[0\dots size_k - 1]$. Diese sagt uns ob $\text{Mem}_k[i]$ ist ein Valider Eintrag. Zu beginn sind alle Einträge Falsch. Zu beginn sind alle Blöcke invalide, deshalb hat unser Cache folgende Architektur:

| $0$   | $\text{Valid}_k[0]$   | $\text{tag}_k[0]$   | $\text{Mem}_k[0]$   |
| ----- | --------------------- | ------------------- | ------------------- |
|       | $\vdots$              |                     |                     |
| $S_k$ | $\text{Valid}_k[S_k]$ | $\text{tag}_k[S_k]$ | $\text{Mem}_k[S_k]$ |

wobei $S_k = \text{size}_k - 1$

```verilog
function FindBlock(k, adr)
	adrk := adr mod sizek;
	tagk := adr div sizek;
	hitk := Validk [adrk ]& (tagk [adrk ] = tagk );
	return (hitk, adrk)
end

function WriteWord(k, adr, m)
	adrk := adr mod sizek;
	tagk := adr div sizek;
	tagk [adrk ] := tagk;
	Validk [adrk ] := 1;
	Memk [adrk ] := m
end

function ReadWord(adr)
	k := 0;
	do k := k + 1;
		(found, ak ) := FindBlock(k, adr)
	while !found;
		m := Memk [ak];
	while k > 1 do 
		k := k − 1;
		WriteWord(k, adr, m)
	end;	
	return m
end
```

## Block Orientiert

Da das laden von [DRAM](DRAM.md) Speicher es erlaubt mehrere Wörter gleichzeitig zu lesen besteht unser Cache besser aus mehreren Wörtern um Lokalität auszunutzen. Dazu werden Blöcke aus $B = 2^b$ Wörtern verwendet und zwischen Block und Speicheradressen unterschieden. Speicheradresse $a_l$ gehört zu Block $a_l \text{ div } B$, die Lade und Speicheroperationen bleiben dieselben, der Cache Controller übersetzt sie in Block Adressen.

Wir nehmen an Adressen $a_l = \langle [x_a, \dots x_b]\rangle^{\mathbb N}_2$ des Hauptspeichers $\text{Mem}_l$ besteht aus $a$ Bits.

Betrachten wir Cache Blöcke der grösse $B = 2^b$, wir erhalten die Blockadresse durch
$$a_l \text{ div } B = \langle[x_a, \dots, x_b]\rangle^{\mathbb N}_2$$
Normalerweise ist $\text{size}_k$ auch Exponenten von $2$. Deshalb gibt es auf Cache Level $k$ aus $\text{size}_k := 2^{s_k}$ Blöcken, dann gilt

$$\begin{align}
&\text{tag}_k([x_1, \dots, x_0]) := (a_l \text{ div } B) \text{ div } \text{size}_k := a_l \text{ div } 2^{s_k + b} := [x_a, \dots, x_{s_k + b}]\\
&\text{adr}_k([x_a, \dots, x_0]) := (a_l \text{ div } B) \mod \text{size}_k := (a_l \text{ div } 2^b) \text{ mod } 2^{s_k} := [x_{s_k} + b-1, \dots x_b]
\end{align}$$


Die Adresse wird also folgendermaßen berechnet:
$$\begin{align}
&\text{block}_k(a_l) := a_l \text{ div } 2^b\\
&\text{tag}_k(a_l) := (a_l \text{ div } 2^b)\text{ div } 2^{s_k}\\
&\text{adr}_k(a_l) := (a_l \text{ div } 2^b) \mod 2^{s_k}
\end{align}$$


