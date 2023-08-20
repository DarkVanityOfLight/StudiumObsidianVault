
Logische Formeln werden mit folgenden Operatoren gebildet:

![Logische Operationen](Elementare%20Logik.md#Logische%20Operationen)


Weitere Operatoren sind:

- $A\iff B := (A\implies B) \land (B\implies A)$ 
- $A\oplus B := \neg (A\iff B)$ 
- $A \barwedge B := \neg(A \land B)$
- $A\nabla B := \not(A \lor B)$
- $A \implies B | C := (A \implies B) \land (\neg A \implies C)$

## Größe
$\text{Size}(x) := 0$
$\text{Size}(\neg A) := 1 + \text{Size}(A)$
$\text{Size}(A\land B) = 1 + \text{Size}(A) + \text{Size(B)}$
$\text{Size}(A \lor B) := 1 + \text{Size}(A) + \text{Size}(B)$

## Tiefe

$\text{Depth}(x):= 0$
$\text{Depth}(\neg A) := 1 + \text{Depth}(A)$
$\text{Depth}(A \land B) := 1 + \max\lbrace \text{Depth}(A), \text{Depth}(B)\rbrace$
$\text{Depth}(A \lor B) := 1 + \max\lbrace \text{Depth}(A), \text{Depth}(B)\rbrace$


## Ersetzung
Sei $x$ eine Variable und $\alpha$ eine Formel.
Wir definieren das ersetzen $[\varphi]^\alpha_x$ als die Formel die wir erhalten wenn wir alle $x$ durch $\alpha$ in $\phi$ ersetzen.

$[y]^\alpha_{x} = \begin{cases} \alpha : x \equiv y\\ y: \text{sonst}\end{cases}\text{for Variables } y$

$[\neg \varphi]^\alpha_x = \neg[\varphi]^\alpha_x$
$[\varphi \land \uppsi]^\alpha_x = [\varphi]^\alpha_x \land [\uppsi]^\alpha_x$ 
$[\varphi \lor \uppsi]^\alpha_x = [\varphi]^\alpha_x \lor [\uppsi]^\alpha_x$ 

## Erfüllbarkeit
($\text{SAT}(\varphi)$)
$\varphi$ ist Erfüllbar wenn es eine Belegung $L$ der Variablen mit $\textlbrackdbl\varphi\textrbrackdbl_L = true$ gibt

Eine Formel ist Erfüllbar wenn sie nicht als $0$ darstellbar ist.

$\text{SAT}(\varphi) \iff NF(\varphi) \not = 0$


$\text{SAT}(\varphi) \iff \neg \text{VALID}(\neg \varphi)$
$\text{SAT}(\varphi) \iff \neg (\varphi \iff 0)$

## Validität
($\text{VALID}(\varphi)$)
$\varphi$ ist Valide wenn es keine Belegung $L$ der Variablen mit $\textlbrackdbl\varphi\textrbrackdbl_L = false$ gibt.

Eine Formel ist Valide wenn sie als $1$ dargestellt werden kann.

$\text{VALID}(\varphi) \iff NF(\varphi) = NF(1)$


$\text{VALID}(\varphi) \iff \neg \text{SAT}(\neg\varphi)$
$VALID(\varphi) \iff (\varphi \iff 1)$

## Äquivalent

Zwei Formeln $\varphi, \uppsi$ sind Äquivalent wenn gilt:
$\textlbrackdbl\varphi\textrbrackdbl_L = \textlbrackdbl\uppsi\textrbrackdbl_L$ für jede Belegung $L$

Eine Formel $\varphi$ ist Äquivalent zu $\uppsi$ wenn sie als $\uppsi$ umgeschrieben werden kann.

$(\varphi \iff \uppsi) \iff NF(\varphi) = NF(\uppsi)$

$(\varphi \iff \uppsi) \iff \text{VALID}(\varphi \iff \uppsi)$
$(\varphi \iff \uppsi) \iff \neg \text{SAT}(\neg(\varphi \iff \uppsi))$



