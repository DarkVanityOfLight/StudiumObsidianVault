
Im Gegensatz zu Kombinierenden Schaltungen verwenden Sequentielle Schaltungen auch Flip-Flops.

Flip-Flops Speichern ein bit und können durch Eingaben Manipuliert werden.

## Asynchrone Implementation


![srlatch](srlatch.png)


## Synchrone Schaltungen


Zeit laueft diskret, also wird durch [Natürliche Zahlen](Natürliche%20Zahlen.md) Modelliert. Zu jedem Zeitpunkt gilt, die Schaltung liest neue Inputs, berechnet die Werte des nächsten Internen Knotens und generiert eine Ausgabe abhängig von der Eingabe.

Sequentielle Schaltungen sind also die Implementation von [Endlichen Automaten](Endliche%20Automaten.md)

In diesen Schaltungen verwenden wir Flip-Flops, $c$ ist das Clock Signal was Periodisch zwischen $1$ und $0$ wechselt und $d$ ist der Input. Ein D Flip-Flop Speichert ein Bit zum Zeitpunkt $t\in\mathbb N$ 

$$q^{t+1} := d^{t}$$

Es gibt verschiedene Arten von Flip-Flops.

![flpflp](flpflp.png)

Jeder dieser Flip-Flops kann verwendet um eine beliebigen Sequentielle Schaltung zu bauen. Jeder Flip-Flop speichert einen Datenbit in der Zustandsvariable $q$.


## SR Flip-Flop

$q^(t+1) := \neg r^{t} \land (s^{t} \lor q^{t})$

| $r^{(t)}$ | $s^{(t)}$ | $q^{(t+1)}$ | Aktion                 |               |
| --------- | --------- | ----------- | ---------------------- | ------------- |
| $0$       | $0$       | $q^t$       | $q^{(t+1)} := q^{(t)}$ | Speichern     |
| $0$       | $1$       | $1$         | $q^{(t+1)} := 1$       | Setzen        |
| $1$       | $0$       | $0$         | $q^{(t+1)} := 0$       | Zuruecksetzen |
| $1$       | $1$       | $0$         | -                      | Verboten      |







Reset und Set dürfen nicht gleichzeitig gesetzt werden.

## JK Flip-Flop

| $r^t$ | $s^t$ | $q^{(t+1)}$    | Aktion                    |              |
| ----- | ----- | ------------ | ------------------------- | ------------ |
| $0$   | $0$   | $q^t$        | $q^{t+1} := q^{t}$        | Speichern     |
| $0$   | $1$   | $0$          | $q^{t+1} := 0$            | Zurücksetzen |
| $1$   | $0$   | $1$          | $q^{(t+1)} := 1$          | Setzen       |
| $1$   | $1$   | $\neg q^{t}$ | $q^{(t+1)} := \neg q^{t}$ | Negieren     |




## D Flip-Flop 

Delay Flip-Flop $q^{(t+1)} := d^{t}$

| $d^{(t)}$ | $q^{(t+1)}$ | Aktion           |               |
| --------- | ----------- | ---------------- | ------------- |
| $0$       | $0$         | $q^{(t+1)} := 0$ | Zuruecksetzen |
| $1$       | $1$         | $q^{(t+1)} := 1$ | Setzen        |

## T Flip-Flop

Toggel Flip-Flop
$$q^{(t+1)} := q^{(t)} \oplus e^{(t)}$$

| $e^{(t)}$ | $q^{(t+1)}$    | Aktion                 |           |
| --------- | -------------- | ---------------------- | --------- |
| $0$       | $q^{(t)}$      | $q^{(t+1)} := q^{(t)}$ | Speichern |
| $1$       | $\neg q^{(t)}$ | $q^{(t+1)} := \neg q^{(t)}$                       | Negieren          |

## Analyse

Im Gegensatz zu Kombinatorischen Schaltungen werden Sequentille nicht durch Logik dargestellt sondern durch [Endliche Automaten](Endliche%20Automaten.md).
Dazu suchen wir erst ein Zeit Bedingtes Boolesches Gleichungssystem:

$$\begin{cases}
p^{(t+1)} = i^{(t)}\\
q^{(t+1)} = p^{(t)}\\
o^{(t)} = \neg i^{t} \land p^{(t)} \land q^{(t)}
\end{cases}$$

