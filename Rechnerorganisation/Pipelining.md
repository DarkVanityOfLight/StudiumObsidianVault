
## Allgemeines Konzept

Der grundlegende Gedanke hinter Pipelining besteht darin, eine Abfolge von Anweisungen in einer Schleife zu betrachten und anstatt die Schleifkörper sequenziell auszuführen, diese zeitlich zu überlappen.

Für eine Schleife mit $n$ Itereationen und $d$ Anweisungen verbessern wir die Laufzeit von $n\cdot d$ auf $n + d$, das heißt, um einen Faktor von $d$  indem wir $d$ Anweisungen parallel ausführen.

## Beispiel

```verilog
module noPipe (nat ?x, !y) {
	loop {
		y = (5 * (x+x) + 3) * (x+2);
		pause;
	}
}
```

Die Eingabe $x$ wird aus der Umgebung gelesen, und die Ausgabe $y$ wird in jedem Clock Cycle berechnet.
Die `pause` Anweisung wartet auf den nächsten Cycle. Für $x = 0, 1, 2$ erhalten wir die Werte

| x | y   |
|---|-----|
| 0 | 6   |
| 1 | 39  |
| 2 | 92  |
| 3 | 165 |
| 4 | 258 |
| 5 | 371 |
| 6 | 504 |
| 7 | 657 |
| 8 | 830 |
| 9 | 1023|


Betrachten wir die Abhängigkeiten erhalten wir:

![dep](dep.png)

Das Pipelining generiert $d=4$ Stufen die zu den einzelnen Zeilen gehoeren:

```
module correctPipe(nat ?x, !y) {
 nat t1, t2, t3, t4, t5, t6;
 loop {
	 next(t1) = x+x; next(t2) =  x+2;
	 next(t3) = 5 * t1; next(t5) = t2;
	 next(t4) = t3 + 3; next(t6) = t5;
	 next(y) = t4 * t6;
	 pause;
 }
}
```

Die Ausgabe ist um $d$ Schritte verzögert, aber die Clock Frequenz kann um $d$ mal schneller gemacht werden.

| $x$  | $t1$ | $t2$ | $t3$ | $t4$ | $t5$ | $t6$ | $y $  |
|----|-----|-----|-----|-----|-----|-----|-----|
| $0$  | $0$  | $0$  | $0$  | $0$  | $0$  | $0$  | $0$   |
| $1$  | $0$  | $2$  | $0$  | $3$  | $0$  | $0$  | $0$   |
| $2$  | $2$  | $3$  | $0$  | $3$  | $2$  | $0$  | $0$   |
| $3$  | $4$  | $4$  | $10$ | $3$  | $3$  | $2$  | $0$   |
| $4$  | $6$  | $5$  | $20$ | $13$ | $4$  | $3$  | $6$   |
| $5$  | $8$  | $6$  | $30$ | $23$ | $5$  | $4$  | $39$  |
| $6$  | $10$ | $7$  | $40$ | $33$ | $6$  | $5$  | $92$  |
| $7$  | $12$ | $8$  | $50$ | $43$ | $7$  | $6$  | $165$ |
| $8$  | $14$ | $9$  | $60$ | $53$ | $8$  | $7$  | $258$ |
| $9$  | $16$ | $10$ | $70$ | $63$ | $9$  | $8$  | $371$ |
| $10$ | $18$ | $11$ | $80$ | $73$ | $10$ | $9$  | $504$ |


Wir haben  `Copy` Knoten in den Graphen eingeführt, dies werden gebracht da wenn wir `next(y) = t4 * t2` berechnen würden, der Wert  von `t2` schon zwei mal überschrieben worden wäre. Dadurch müssen wir den Wert nach `t5` und dann nach `t6` verschieben sodass, das überschreiben harmlos ist. Dies nennt sich __write-after-read__ Konflikt, wobei das lesen zu spät geschieht, also zuerst eine Schreiboperation stattfindet, welche erst danach passieren sollte.

## Das Problem

Betrachten wir eine Schaltung die eine Tiefe Kombinatorische Funktion $f$ implementiert, in jedem Cycle wird die Ausgabe $y$ für die Eingabe $x$ berechnet.
Das Problem ist, das die Clock Frequenz niedrig ist da $f$ eine Tiefe Schaltung ist.


Um dieses Problem zu lösen Teilen wir $f$: $f(x) = f_p(f_{p-1}(\dots f_1(x)\dots))$.
Wir erhalten $f_i$ indem wir die Schaltungen Partitionieren. Nun ist $f$ und $f_p \circ \dots \circ f_1$ das gleiche, also auch die gleiche Langsame Clock Frequenz.

Nun fügen wir Pipeline Register $R_i$ zwischen den Funktionen $f_i$ ein, dadurch erhalten wir eine Pipeline in der die Stufen in und von Registern schreiben/lesen.
Die Clock Frequenz kann dadurch auf $p$ für $p$ Stufen erhöht werden, wir erhalten eine Verbesserung um den Faktor $p$.  Die Berechnung $y  = f(x)$ benötigt jedoch immer noch $p$ Cycles, jedoch wird in jedem Cycle eine Berechnung beendet.

## Konflikte

Betrachten wir Programm Ausführung, dann sind die Eingaben für die Pipeline $\mathcal J = \lbrace addiu, \dots\rbrace$, betrachten wir einen Anweisungsstrom $\mathcal I : \mathbb N \to \mathcal J$. Die Pipeline
 berechnet $p$ unterschiedliche Teile $f_1, \dots, f_p$ von $p$ verschiedenen Anweisungen $\mathcal I^{(t+p)}, \dots, \mathcal I^{(t+1)}$ in einer Zeit $t\in\mathbb N$. 
 Jedoch sollte die Semantik die selbe sein als ob alle Teile einer Anweisung $\mathcal I^{(t)}$ ausgeführt wurden bevor die nächste Anweisung $\mathcal I^{t+1}$ startet. Deshalb müssen wir Pipeline Konflikte vermeiden.

| Stage     | $i-1$                    | $i$                      | $i+1$                    | $\dots$ | $p-1$                    | $p$                      |
|-----------|------------------------|------------------------|------------------------|-----|------------------------|------------------------|
| $\mathcal I^{(t+i-1)}$ | $\mathcal I^{(t+1)}$ | $\mathcal I^{(t)}$ | $\mathcal I^{(t-1)}$ | $\dots$ | $\mathcal I^{(t+i-p+1)}$ | $\mathcal I^{(t+i-p)}$ |

### RAW

> read-after-write auch genannt echte Abhängigkeit

$\mathcal I^{(t)}$ liest eine Variable die von einer der $\mathcal I^{(t-1)}, \dots \mathcal I^{(t+i-p)}$ in einer der nächsten Stufe geschrieben wird.

$\mathcal I^{(t)}$  liest in Stufe $i$ eine Variable die später von einer Vorangehenden Anweisung $\mathcal I^{(t-j)}$ geschrieben wird. $\mathcal I^{(t)}$ liest zu früh, es sollte nur gelesen werden wenn alle vorangehenden Anweisungen geschrieben haben.

![Definition](RAW.md#Definition)
### WAR
> write-after-read auch genannt gegen Abhängigkeit

$\mathcal I^{(t)}$ schreibt eine Variable die von einem der $\mathcal I^{t-1}, \dots, \mathcal I^{(t+i-p)}$ Anweisungen in einer der nächsten Stufe gelesen wird.

$\mathcal I^{(t)}$ überschreibt  in Stufe $i$ den Wert der später von einer vorherigen Operation $\mathcal I^{(t-j)}$  gelesen werden werden soll. $\mathcal I^{(t)}$ schreibt zu früh, es sollte erst geschrieben werden wenn alle vorherigen Operationen stattgefunden haben.


### WAW
> write-after-write auch genannt Ausgabe Abhängigkeit

$\mathcal I^{(t)}$ schreibt eine Variable die von einer $\mathcal I^{(t-1)},\dots,\mathcal I^{(t+i-p)}$ Anweisungen in einer der nächsten Stufe geschrieben wird.


$\mathcal I^{(t)}$ schreibt in Stufe $i$ den Wert der später von einer Vorangehenden Anweisung $\mathcal I^{(t-j)}$ überschrieben wirt soll. $\mathcal I^{(t)}$ schreibt zu früh, es sollte erst schreiben wenn all vorherigen Anweisung ausgeführt wurden.

---

Wir müssen das Folgenden über $\mathcal I \in \mathcal J$ und $k\in\lbrace 1, \dots, p\rbrace$ wissen.

- $Read(\mathcal I, k)$ Die Variablen die von der Anweisung $\mathcal I$ in Stufe $k$ gelesen werden
- $IWrite(\mathcal I, k)$ Die Variablen $x$ die von der Anweisung $\mathcal I$ durch eine Zuweisung $x=\tau$  in der Stufe $k$ geschrieben werden
- $DWrite(\mathcal I, k)$ Die Variablen $x$ die von der Anweisung $\mathcal I$ in der Stufe $k$ durch eine verzögerte Zuweisung $next(x) = \tau$ geschrieben wird.
- $Write(\mathcal I, k) = IWrite(\mathcal I, k) \cup DWrite(\mathcal I, k-1)$ 

Normalerweise können nur Pessimistische Näherungen erlangt werden, da Lese und Schreiboperationen auf die Eingabe ankommen.


![Formale Definition von RAW Konflikten](RAW.md#Formale%20Definition%20von%20RAW%20Konflikten)
## Formale Definition von WAW Konflikten

|Zeit/Stufe|$i$|$\dots$|$i+k$|$i+k+2$|$\dots$|$p$|
|----------|-|-|-|-|-|-|
|$t$|$\mathcal I: next(x) = \tau$|$\dots$|$\mathcal J: x = \tau;\; next(x) = \tau$||||
|$t+1$||$\dots$||$\mathcal J x = \tau;\;next(x) = \tau$|||
|$\vdots$|$\vdots$|$\dots$|$\vdots$|$\vdots$||$\vdots$|
|$t_p$||$\dots$||||$\mathcal J x=\tau;next(x) = \tau$|

Betrachte zwei Anweisungen $\mathcal I$ und $\mathcal J$. In einer Sequentiellen Ausführung, werden erst alle Schritte von $\mathcal J$ ausgeführt bevor ein Schritt von $\mathcal I$ ausgeführt wird, dadurch gibt es keine Schreiboperation von $\mathcal J$ die im Konflikt mit einer Leseoperation von $\mathcal I$ steht.
In einer Pipeline starten wir früher mit $\mathcal I$ müssen aber Konflikte vermeiden.

Nur eine direkte Zuweisung von $\mathcal J$ zum Zeitpunkt $t$ wird $x$ verändern, bevor die verspätete Zuweisung von $\mathcal I$ zum Zeitpunk $t$ stattgefunden hat, alle anderen Zuweisungen von $\mathcal J$ sind zu spät.

Nehmen wir an das:
- $t_r$ der erste Zeitpunkt ist an dem $\mathcal I$ eine verspätete Zuweisung von $x$ vornimmt.
- $t_{w, i}$ der letzte Zeitpunkt ist an dem $\mathcal J$ eine direkte Zuweisung von $x=\tau$ vornimmt
- $t_{w, d}$ der letzte Zeitpunkt ist an dem $\mathcal J$ eine verspätete Zuweisung $next(x) = \tau$ vornimmt

Wir merken das $t_r \ge t_{w, i}$ und $t_r > t_{w, d}$ gelten muss.

Wenn $\mathcal I$ eine direkte Zuweisung ausführt, dann wären alle Zuweisungen von $\mathcal J$ im Konflikt.
Deshalb definieren wir einen $WAW(\mathcal I,\mathcal J)$ wenn eine der folgenden [Mengen](Mengen.md) nicht leer ist:
- $DWrite(\mathcal I, i)\cap\bigcup^{p}_{j=i+1} DWrite(\mathcal J, j)$
- $DWrite(\mathcal I, i)\cap\bigcup^{p}_{j=i+1} IWrite(\mathcal J, j)$
- $IWrite(\mathcal I, i)\cap \bigcup^{p}_{j=i+1} DWrite(\mathcal J, j)$
- $IWrite(\mathcal I, i)\cap\bigcup^p_{j=i+1} IWrite(\mathcal  J, j)$

## Formale Definition von WAR Konflikten

|Zeit/Stufe|$i$|$\dots$|$i+k$|$i+k+2$|$\dots$|$p$|
|----------|-|-|-|-|-|-|
|$t$|$\mathcal I: next(x) = \tau$|$\dots$|$\mathcal J: read(x)$||||
|$t+1$||$\dots$||$\mathcal J: read(x)$|||
|$\vdots$|$\vdots$|$\dots$|$\vdots$|$\vdots$||$\vdots$|
|$t_p$||$\dots$||||$read(x)$|

Wir betrachten die zwei Operationen $\mathcal I$ und $\mathcal J$. Bei einer Sequentiellen Ausführung würden erst all schritte von $\mathcal J$ ausgeführt werden bevor ein Schritt von $\mathcal I$ ausgeführt wird. Deshalb kann keine Leseoperation von $\mathcal J$ im Konflikt mit einer Schreiboperation von $\mathcal I$ sein. In einer Pipeline wird $\mathcal I$ früher gestartet, aber wir müssen auf Konflikte achten.

Nur die Leseoperation von $\mathcal J$ zum Zeitpunkt $t$ wird den Richtigen Wert $x$ lesen. Alle anderen Leseoperationen von $\mathcal J$ sind zu spät wenn $x$ schon überschrieben ist.

Nehmen wir an das:
- $t_{w}$ ist der erste Zeitpunkt an dem $\mathcal I$ eine verspätete Zuweisung $x$ vornimmt.
- $t_r$ ist der letzte Zeitpunkt an dem $\mathcal J$ eine Leseoperation $read(x)$ ausführt.

Wir merken, dass $t_w \geq t_r$ gelten muss.
Wenn $\mathcal I$ eine direkte Zuweisung ausführt, wären alle Leseopertationen von $\mathcal J$ im Konflikt.

Wir definieren $WAR(\mathcal I, \mathcal J)$, wenn eine der Folgenden [Mengen](Mengen.md) nicht leer ist:
- $DWrite(\mathcal I, i)\cap\bigcup^p_{j=i+2} Read(\mathcal J, j)$
- $IWrite(\mathcal I, i)\cap\bigcup^p_{j=i+1} Read(\mathcal J, j)$

## Do Writes Late

Stufen in denen Variablen geschrieben werden sind oft spät, der Extremfall wäre das nur in der letzten Stufe $p$ geschrieben werden darf. In diesem Fall haben wir $Write(\mathcal I^{(t)}, i) = \lbrace\rbrace$ mit $p\not = i$, und deshalb:
- $RAW(i, j) : \iff \exists \mathcal I_1, \mathcal I_2 \in\mathcal J$. $Read(\mathcal I_1, i) \cap Write(I_2, p)\not = \lbrace\rbrace$
- $WAR(i, j) :\iff false$
- $WAW(i, j):\iff false$

Wenn nur die Stufe $p$ schreiben darf, gibt es keine WAR oder WAW Konflikte
#klausur_rosy

--- 

Bisher haben wir nur Daten Konflikte betrachtet, generell können wir zwischen diesen Konflikten unterscheiden:
- Strukturelle Konflikte: Mehrere Stufen wollen eine gemeinsame Ressource benutzen
- Daten Konflikte: (RAW, WAR, WAW) führt zu einem falschen update von $Reg[i]$
- Kontroll Konflikte: Ein falsches Update des $pc$ Registers

Betrachten wir das $pc$ Register als ein normales Register, können Kontroll Konflikte als Daten Konflikte betrachtet werden.
Strukturelle Konflikte werden durch das duplizieren von Daten behoben.

---

Wir könne [Tabellen](RAW.md#Tabelle) verwenden um potentielle Daten Konflikte zu erkennen, es verbleibt diese zu lösen. Dafuer gibt es mehrere Optionen:
- Pipeline stalling
- Result forwarding
- Speculative execution
- reordering program instructions

## Pipeline Stalling
Eine Pipeline zum Zeitpunkt $t$

|Stufe|$1$|$2$|$\dots$|$p-1$|$p$|
|-----|-|-|-|-|-|
||$\mathcal I_1$|$\mathcal I_2$|$\dots$|$\mathcal I_{p-1}$|$\mathcal I_p$|

Wir erhalten Konflikte wenn eine schreibe oder lese Operation zu früh ausgeführt wird, nehmen wir nun an das es einen Konflikt zwischen den Stufen $i$ und $i+j$ gibt, die einfachste Lösung ist es die Stufen $1, \dots, j$ anzuhalten.
Der Konflikt löst sich dann nach einiger Zeit auf, dann können die Stufen $1, \dots, j$ weitermachen, der Vorteil ist die Einfachheit der Lösung, allerdings wird die Pipeline Performance verringert.

## Result Forwarding
Eine Pipeline zum Zeitpunkt $t$

|Stufe|$1$|$2$|$\dots$|$p-1$|$p$|
|-----|-|-|-|-|-|
||$\mathcal I_1$|$\mathcal I_2$|$\dots$|$\mathcal I_{p-1}$|$\mathcal I_p$|

Betrachten wir eine RAW Konflikt zwischen den Stufen $i$ und $i+j$.
$\mathcal I_i$ liest in Stufe $i$ eine Adresse die von $\mathcal I_{i+j}$ entweder jetzt oder später in der Pipeline geschrieben wird, jedoch hat $\mathcal I_{i+j}$ den Wert schon berechnet, dann kann dieser Wert direkt nach $\mathcal I_i$ gegeben werden. Dadurch erhalten wir keine verschlechterte Performance, jedoch funktioniert dies nur wenn das Ergebnis schon berechnet wurde.
## Spekculative Execution

Eine Pipeline zum Zeitpunkt $t$

|Stufe|$1$|$2$|$\dots$|$p-1$|$p$|
|-----|-|-|-|-|-|
||$\mathcal I_1$|$\mathcal I_2$|$\dots$|$\mathcal I_{p-1}$|$\mathcal I_p$|

Betrachten wir einen RAW Konflikt zwischen den Stufen $i$ und $i+j$. 
Wenn $\mathcal I_{i+j}$ den Wert noch nicht berechnet haben, der geschrieben werden soll, dann kann [Result Forwarding](#Result%20Forwarding) nicht verwendet werden. Mit einer Richtigen Strategie können wir das Ergebnis jedoch den Wert voraussagen. Wenn ein falscher Wert geraten wurde muss die Pipeline geflushed werden:
Alle Anweisungen bis $\mathcal I_i$  müssen aus der Pipeline gelöscht werden und die Anweisung müssen von $\mathcal I_i$ aus neu gelesen werden. Desto besser die Voraussage desto besser ist die Performance, jedoch werden falsche Voraussagen die Performance der Pipeline  verschlechtern.

## Neuordnung des Programmes

Wir können Programme generieren die niemals zu einem Konflikt führen, gute Compiler schaffen dies oft und höherwertige Prozessoren tuen dies von selbst, dies führt zu Dynamischen scheduling oder out of order Ausführung.

## Pipeline des Abacus

Aehnlich zu der klassischen MIPS Pipeline haben wir eine Pipeline mit 5 Stufen:
- __IF__ Instruction fetch
- __ID__ Instruction decode
- __EX__ execute
- __MA__ Memory Access
- __WB__ Write back

Wir werden diese Stufen zuerst beschreiben und [Pipeline Stalling](#Pipeline%20Stalling) verwenden um Konflikte zu beheben.

## Externer Speicher

```verilog
module Abacus(
	bv{16} ?instr, // Instruction to be performed now
	nat pc, // Program Counter
	event nat !adrBus, // Address for memory Access
	event bv{DataWidth} dataBus, // Data for Memory Access
	event readMem, writeMem //Whether read or write Memory
)
```

$pc$ wird auf den Adressbus zum Anweisungsspeicher gelegt. Dann wird $instr$ aus dem Anweisungsspeicher gelesen, $adrBus$ wird auf den Adressbus des Datenspeicher gelegt und $dataBus$ kann gelesen oder geschrieben werden, je nachdem ob $readMem$ oder $writeMem$.

## Locale Variable mit Pipeline Variablen

Wir müssen Ergebnisse zu den weiteren Stufen übergeben, da diese sonst überschrieben werden.

```verilog
[8]bv{ DataWidth } Reg ; // scalar registers 
bv{ DataWidth } ovrflw ; // overflow register
bv{16} instr ; // instruction register
bv{6} opc_ID , opc_EX , opc_MA , opc_WB ;// opcodes of instructions 
bv{7} fnc_EX , fnc_MA , fnc_WB ; // function codes or 7 - bit constant 
bv{10} adr_EX , adr_MA , adr_WB ; // addresses of J - type instruction 
nat{8} rd_EX , rd_MA , rd_WB ;// destination registers 
bv{ DataWidth } opS_EX , opS_MA ; // values to be stored 
bv{ DataWidth } opL_ID , opR_ID ; // preparing ALU operands bv{ DataWidth } opL_EX , opR_EX ; // ALU operands 
bv{2* DataWidth } alu_EX , alu_MA , alu_WB ; // ALU result bool cnd_EX , cnd_MA , cnd_WB ; // branch condition result 
bv{ DataWidth } ld_MA , ld_WB ; // load result
```

Pipeline Stufen schreiben in die folgenden Variablen `opc_ID`, `alu_EX`, `cnd_EX`, `ld_MA` und werden später zum forwarding genutzt.

|IF|ID|EX|MA|WB|
|--|--|--|--|--|
|`instr`| `opc_ID`, `opc_EX`|`opc_MA`|`opc_WB`|`ovrflw`|
|`fnc_EX`|`fnc_MA`|`fnc_WB`|`Reg`
|`adr_EX`|`adr_MA`|` adr_WB`|`pc`
| `rd_EX`|` rd_MA`|` rd_WB `
| `opL_ID`|`opS_MA`|
|`opR_ID`|` alu_MA`,`alu_EX`|`alu_WB`
| `opL_EX`|`cnd_MA`,`cnd_EX`|`cnd_WB`
| `opR_EX` || `ld_MA`,`ld_WB`
|`opS_EX`||`adrBus`
|||`dataBus`|
|||`readMem`|
|||`writeMem`|


## Instruction Fetch

```verilog
module Fetch(nat ?pc, bv{16} !instr) {
	next(instr) = Prog[pc]
}
```

Wir lesen einfach die die Anweisung aus dem Programm Memmory

## Instruction Decode

```verilog
module Decode ( 
bv{16} ? instr , // instruction to be performed now 
[8]bv{ DataWidth } ? Reg , // scalar registers 
bv{ DataWidth } ? ovrflw , // overflow register 
bv{6} opc_ID , opc_EX , // opcodes of instr 
bv{7} fnc_EX , // 7 - bit constant (S - type instr .) 
bv{10} adr_EX , // 10 - bit address (J - type instr .) 
nat{8} rd_EX , // register destination index 
bv{ DataWidth } opL_ID , opR_ID , // prepare ALU operands 
bv{ DataWidth } ! opL_EX ,! opR_EX , // ALU operands 
bv{ DataWidth } ! opS_EX // value for store instr . ) { 
// local variables 
nat{8} rd , rs1 , rs2 ; 
// register indices 
bv{4} cst ; // 4 - bit constant (I - type instr .) 
bv{7} fnc ; // 7 - bit constant (S - type instr .) 
bv{10} adr ; // 10 - bit constant (J - type instr .)

// extract parts of instruction word 
opc_ID = instr {15:10};
rd = bv2nat( instr {9:7}) ; 
rs1 = bv2nat( instr {6:4}) ; 
rs2 = bv2nat( instr {3:1}) ; 
cst = instr {3:0}; 
fnc = instr {6:0}; 
adr = instr {9:0}; // propagate to EX stage 
next( opc_EX ) = opc_ID ; 
next( rd_EX ) = rd ; 
next( fnc_EX ) = fnc ; 
next( adr_EX ) = adr ;

// determine store value for store instruction
next( opS_EX ) = Reg [ rd ]; // determine ALU operand opL_ID case 
	( opc_ID == MOV | opc_ID == OVF ) 
		do opL_ID = {false:: DataWidth };
	( opc_EX == BEZ | opc_EX == BNZ | opc_EX == JMP | opc_EX == J) 
		do opL_ID = nat2bv( pc , DataWidth );
	default 
		opL_ID = Reg [ rs1 ]; 
		
// forward to EX stage 
next( opL_EX ) = opL_ID ;

case
    // signed arithmetic instruction with immediate operand
    (opc_ID{5:4} == 0b00 & opc_ID{1:0} == 0b10) do opR_ID = sext4(cst);
    // unsigned arithmetic instruction with immediate operand
    (opc_ID{5:4} == 0b00 & opc_ID{1:0} == 0b11) do opR_ID = zext4(cst);
    // load / store instructions
    (opc_ID == LDI | opc_ID == LL | opc_ID == STI | opc_ID == SC) do opR_ID = zext4(cst);
    // control flow and moves
    (opc_ID == BEZ or opc_ID == BNZ or opc_ID == MOV) do opR_ID = sext7(fnc);
    (opc_ID == JMP) do opR_ID = Reg[rd];
    (opc_ID == J) do opR_ID = sext10(adr);
    (opc_ID == NEG) do opR_ID = {false::DataWidth};
    (opc_ID == OVF) do opR_ID = ovrflw;
    default opR_ID = Reg[rs2];
    // forward to EX stage
    next(opR_EX) = opR_ID;

```

![iddo](iddo.png)


ID extrahiert die Teile des Anweisung Wortes, z.b.
- Operation Codes `opc_ID`, `opc_EX`
- Register Indices `rd`, `rs1`, `rs2`, `rd_EX`
- Direkte Konstanten `cst`, `fnc`, `adr`, `cst_EX`, `fnc_EX`, `adr_EX`
ID definiert außerdem:
- ALU Operationen `opL_EX` und $opR_EX$
- Den zu speichernden Wert in `opS_EX` für Speicher Operationen

## Instruction Execute

```verilog
module Execute ( 
bv{6} ? opc_EX , // opcode of instruction 
bv{7} ? fnc_EX , // 7 - bit constant (S - type instr .) 
bv{10} ? adr_EX , // 10 - bit constant (J - type instr .) nat{8} ? rd_EX , // register destination index 
bv{ DataWidth } ? opS_EX , // value for store instr . 
bv{ DataWidth } ? opL_EX ,? opR_EX , // ALU operands 
bv{6} ! opc_MA , // opcode of instruction 
bv{7} ! fnc_MA , // 7 - bit constant (S - type instr .) 
bv{10} ! adr_MA , // 10 - bit constant (J - type instr .) nat{8} ! rd_MA , // register destination index 
bv{ DataWidth } ! opS_MA , // value for store instr . 
bv{2* DataWidth } alu_EX , alu_MA , // ALU results 
bool cnd_EX , cnd_MA // result of branch condition )

// note: immediate writes to alu_EX and its double width
case
    // ALU instr: alu_EX = AluOp(opL_EX, opR_EX)
    (opc_EX == ADD) do alu_EX = ...;
    // load / store: address calculation using opL_EX and opR_EX
    (opc_EX == LDI | opc_EX == LL | opc_EX == STI | opc_EX == SC) do alu_EX = ALUADDU(opL_EX, opR_EX);
    // branch / jump: calculate potential next pc
    (opc_EX == BEZ | opc_EX == BNZ | opc_EX == JMP | opc_EX == J) do {
        alu_EX = ALUADDS(opL_EX, opR_EX);
        if (opc_EX == BEZ) cnd_EX = opS_EX == Zero;
        if (opc_EX == BNZ) cnd_EX = opS_EX != Zero;
    }
    default alu_EX = ALUADDU(opL_EX, opR_EX);
    
// propagate to the memory access stage
next(opc_MA) = opc_EX;
next(fnc_MA) = fnc_EX;
next(adr_MA) = adr_EX;
next(rd_MA) = rd_EX;
next(opS_MA) = opS_EX;
next(alu_MA) = alu_EX;
next(cnd_MA) = cnd_EX;
)
```

Die Execute Stufe bestimmt `alu_EX` indem sie die benötigten ALU Operationen mit den Operatoren `opL_EX` und `opR_EX` ausfuehrt. Die Operation wird durch `opc_EX` und `fnc_EX` bestimmt. `alu_EX` wird durch eine direkte Zuweisung gesetzt und wird mit doppelter Bitbreite berechnet. EX berechnet auch die Branch Condition `cnd_EX`.  Die Werte `opc_MA`, `fnc_MA`, `adr_MA`, `rd_MA`, `opS_MA`, `alu_MA`, `cnd_MA` werden zur MA Stufe weitergegeben.

## Memory Access

```verilog
module MemAccess (
    bv{6} ? opc_MA,     // opcode of instr
    bv{7} ? fnc_MA,     // 7-bit constant (S-type instr.)
    bv{10} ? adr_MA,    // 10-bit constant (J-type instr.)
    nat{8} ? rd_MA,     // register destination index
    bv{DataWidth} ? opS_MA,    // value to be stored for stores
    bv{2*DataWidth} ? alu_MA,  // ALU results (immediate and delayed)
    bool ? cnd_MA,      // result of branch condition
    bv{6} ! opc_WB,     // opcode of instr
    bv{7} ! fnc_WB,     // function code
    bv{10} ! adr_WB,    // 10-bit constant (J-type instr.)
    nat{8} ! rd_WB,     // register destination index
    bv{2*DataWidth} ! alu_WB,   // ALU result (contains memory address)
    bool ! cnd_WB,      // result of branch condition
    bv{DataWidth} ld_MA, ! ld_WB,   // load result
    event nat ! adrBus,   // address for memory access
    event bv{DataWidth} dataBus,   // data for memory access
    event readMem, writeMem  // whether data is read or written
);
```

```verilog
if (opc_MA == LD | opc_MA == LL |
    opc_MA == ST | opc_MA == SC |
    (opc_MA == SYNC & fnc_MA == fn_SYNC)) {
    adrBus = bv2nat(alu_MA);
    case
        (opc_MA == LD | opc_MA == LDI | opc_MA == LL) do
            emit(readMem);
            ld_MA = dataBus;
        (opc_MA == ST | opc_MA == STI | opc_MA == SC) do {
            emit(writeMem);
            dataBus = opS_MA;
        }
        (opc_MA == SYNC) do {
            emit(readMem);
            emit(writeMem);
        }
        default nothing;
    }
}

// propagate to the write back stage
next(opc_WB) = opc_MA;
next(fnc_WB) = fnc_MA;
next(adr_WB) = adr_MA;
next(rd_WB) = rd_MA;
next(alu_WB) = alu_MA;
next(cnd_WB) = cnd_MA;
next(ld_WB) = ld_MA;
```

Memory Access wird nur für lade und speicher Anweisungen verwendet.

Fuer Lade Anweisungen
- Lade die Adresse `alu_MA` auf den `adrBus`
- Setze das Signal `readMem`
- Lade die Daten `dataBus` vom Daten Bus und Speicher sie in `ld_MA`, auch hier wird direkte Zuweisung verwendet

Fuer Speicher Anweisungen:
- Lade die Adresse `alu_MA` auf den `adrBus`
- Setze das `writeMem` Signal
- Lege die Daten `opS_MA` auf den `dataBus` um sie in `Mem[adrBus]` zu speichern

## Write Back

```verilog
module WriteBack (
    nat pc,                 // program counter
    bv{6} ? opc_WB,         // opcode of instr
    bv{7} ? fnc_WB,         // 7-bit constant (S-type instr.)
    bv{10} ? adr_WB,        // 10-bit constant (J-type instr.)
    nat{8} ? rd_WB,         // register destination
    bv{2*DataWidth} ? alu_WB,   // ALU result (contains memory address)
    bool ? cnd_WB,          // result of branch condition
    bv{DataWidth} ? ld_WB,  // Load result
    [8]bv{DataWidth} ! Reg,   // scalar registers
    bv{DataWidth} ! ovrflw   // overflow register (completing result)
);
```

```verilog
case
    // load instructions
    (opc_WB == LD | opc_WB == LDI | opc_WB == LL) do {
        Reg[rd_WB] = ld_WB;
        next(pc) = pc + 1;
    }
    // branch and jump instructions
    (opc_WB == BEZ | opc_WB == BNZ) do
        next(pc) = (cnd_WB ? bv2int(alu_WB) : pc + 1);
    (opc_WB == JMP | opc_WB == J) do
        next(pc) = bv2int(alu_WB);
    default {
        ovrflw = UpperWord(alu_WB);
        Reg[rd_WB] = LowerWord(alu_WB);
        next(pc) = pc + 1;
    }
```

Write Back ist dafür verantwortlich die Register `Reg[rd_WB]`, `ovrflw` und `pc`, für die ALU Anweisungen verwendet `ovrflw` und `alu_WB` solange `Reg[rd_WB]` verwendet die untere hälfte. Um zu laden updaten wir `Reg[rd_WB] = ld_WB`.  Fuer spruenge wird das `pc` Register upgedatet mit `cnd_WB` und `alu_WB`, für die anderen Anweisungen haben wir einfach `next(pc) = pc + 1`.

## Konflikte in der Abakus Pipeline

### Struktureller Konflikt bei Speicherzugriff

- **Lesen im Befehlsabruf (IF):**
  - Kein Problem, da verschiedene Programm- und Daten-Speicher (Harvard-Architektur).

- **Lesen/Schreiben im Befehlsausführungsschritt (MA):**
  - Kein Problem, da verschiedene Programm- und Daten-Speicher (Harvard-Architektur).

### Pipeline-Konflikte

- **RAW(ID,WB):**
  - Konflikt aufgrund von Registerabhängigkeit.

- **RAW(IF,WB):**
  - Konflikt aufgrund des Programmzählers (pc).

- **RAW(IF,MA):**
  - Konflikt aufgrund von Datenabhängigkeit im Speicher.

## Verzögerung von Pipeline-Stufen

Jede Pipeline-Stufe muss Eingaben von der vorherigen Stufe lesen und Ausgaben an die nächste Stufe schreiben. Über ein Ausgabebit (valid) signalisiert sie, ob ihre Ausgaben bereit zum Lesen sind. Andernfalls muss die nächste Stufe auf das Lesen ihrer Eingaben warten. Über ein weiteres Ausgabebit (get) signalisiert sie, ob sie die Ausgaben der vorherigen Stufe gelesen hat. Andernfalls muss die vorherige Stufe warten, bis ihre Ausgaben gelesen wurden.

### Konzept der Pipeline

- Abakus-Pipeline mit Verzögerung
- Lösung durch Weiterleitung (Forwarding)
- Variationen von Pipelines
- Abakus-Pipeline
- Weiterleitung von ALU-Anweisungen
- Weiterleitung von LOAD-Anweisungen
- Konflikte durch Branch-Anweisungen
- Verzögerung von Pipeline-Stufen

### Verwendung von valid/get-Signalen zwischen den Pipeline-Stufen

Die Verwendung von Signalen wie valid/get zwischen den Pipeline-Stufen ist eine Lösung.

Es gibt jedoch eine weitere, sehr einfache Lösung: das Einfügen von "nop"-Operationen in IF.

Die "nop"-Operation sollte keine Auswirkungen haben, wenn sie von den Pipeline-Stufen verarbeitet wird. Wir können "nop" als `j 1` definieren, vorausgesetzt, dass die Zieladresse für $j$-Anweisungen sofort in ID anstelle von EX berechnet wird. Andernfalls würde das Einfügen von $j 1$-Anweisungen eine weitere Verzögerung auslösen, was zu einer Endlosschleife des Einfügens von $j 1$-Anweisungen führen würde.

## Konfliktauflösung durch Weiterleitung
- Alle RAW-Konflikte von ALU-Anweisungen werden durch Ergebnisweiterleitung gelöst. - Eine der beiden RAW-Konflikte von LOAD-Anweisungen wird durch Weiterleitung gelöst. - Zwei der drei RAW-Konflikte von BRANCH-Anweisungen werden durch Weiterleitung gelöst. 
## Implementierung der Weiterleitung:
- Weiterleitung für RAW-Konflikte von ALU in Stufe ID. - Weiterleitung für RAW-Konflikt von LOAD in Stufe ID. - Weiterleitung für RAW-Konflikte von BRANCH in Stufe IF. - Weiterleitung für JUMP-Anweisungen in Stufe IF.

## Befehlskodierung mit Weiterleitung

ID liest die Register `Reg[rs1]`, `Reg[rs2]`, `Reg[rd]` und `ovrflw`, wegen RAW Konflikten müssen die korrekten Werte aus den EX oder MA Stufen genommen werden.
Wir führen neue Variablen in ID ein `Rrs1`, `Rrs2`, `Rrd`, `Rov` diese werden wie folgt definiert, im Restlichen Code von ID müssen wir `Reg[rs1]`, `Reg[rs2]`, `Reg[rd]`, `ovrflw` mit `Rrs1`, `Rrs2`, `Rrd`, `Rov`.

```verilog
case
  (isAluOp(opc_EX) & rd_EX == rs1) do
    Rrs1 = LowerWord(alu_EX);
  (isAluOp(opc_MA) & rd_MA == rs1) do
    Rrs1 = LowerWord(alu_MA);
  (isLoadOp(opc_MA) & rd_MA == rs1) do
    Rrs1 = ld_MA;
  default
    Rrs1 = Reg[rs1];
case
  (isAluOp(opc_EX) & rd_EX == rs2) do
    Rrs2 = LowerWord(alu_EX);
  (isAluOp(opc_MA) & rd_MA == rs2) do
    Rrs2 = LowerWord(alu_MA);
  (isLoadOp(opc_MA) & rd_MA == rs2) do
    Rrs2 = ld_MA;
  default
    Rrs2 = Reg[rs2];
case
  (isAluOp(opc_EX) & rd_EX == rd) do
    Rrd = LowerWord(alu_EX);
  (isAluOp(opc_MA) & rd_MA == rd) do
    Rrd = LowerWord(alu_MA);
  (isLoadOp(opc_MA) & rd_MA == rd) do
    Rrd = ld_MA;
  default
    Rrd = Reg[rd];
case
  isAluOp(opc_EX) do
    Rov = UpperWord(alu_EX);
  isAluOp(opc_MA) do
    Rov = UpperWord(alu_MA);
  default
    Rov = ovrflw;
```

Außerdem müssen wir das `pc` Register so schnell wie möglich updaten. Für Sprünge verwenden wir einen zusätzlichen Addierer in `ID` um `pc_ID = nat2bv(bv2nat(opL_ID) + bv2nat(opR_ID), DataWidth)` zu berechnen. Dies berechnet den Korrekten `pc` für IF zum momentanen Zeitpunkt.
Um den `pc` des nächsten Cycles zu bestimmen:
```verilog
case
	(isJumpOp(opc_ID)) do next(pc) = pc_ID;
	(isBranch(opc_EX) & cnd_EX) do next(pc) = bv2nat(alu_EX);
default
	next(pc) = pc + 1;
```

Sollte die vorherige Operation eine Lade oder Sprung Operation gewesen sein halten wir die Pipeline an. Ausserdem schauen wir ob der Sprung in ID oder eine Branch in EX ist:

```verilog
module Fetch(nat ?pc, bv{16} !instr){
	if(isLoadOp(opc_ID) | isBranchOp(opc_ID))
		next(instr) = nop;
	else
		case
			(isJumpOp(opc_ID))
				do next(instr) = Prog[bv2nat(pc_ID)];
			(isBranchOp(opc_EX) & cnd_EX)
				do next(instr) = Prog[bv2nat(alu_EX)];
		default
			next(instr) = Prog[pc];
}
```

Sei:

- $p_{IF}$ die Stufe in der Anweisungen gefetched werden
- $p_{ID}$ die Stufe in der Operanten Register gelesen werden
- $p_{EX}$ die Stufe in der ALU Ergebnisse verfuegbar sind
- $p_{MA}$ die Stufe in der Speicher geladen wird
- $p_{WB}$ die Stufe in der Register geschrieben werden
Dan berechnen wir die Anzahl an verzoegerungen:

| |no forward, no bypass | no forward + bypass|forward+bypass|
|-|-|-|-|
|after ALU|$p_{WB} - p_{ID}$|$(p_{WB} - p_{ID}) - 1$|$(p_{EX} - p_{ID}) - 1$|
|after load|$(p_{WB} - p_{ID}$|$(p_{WB} - p_{ID}) - 1$|$(p_{MA} - p_{ID}) - 1$|
|after branch|$p_{WB} - p_{IF}$|$(p_{WB} - p_{IF}) - 1$|$(p_{EX} - p_{IF}) - 1$|

