

Gegeben ist ein Alphabet $\Sigma = \lbrace \sigma_{1}, \dots, \sigma_{n} \rbrace$ mit den Wahrscheinlichkeiten $P(\sigma_{i})$.
Wir sortieren das Alphabet nach den Wahrscheinlichkeiten, dann teilen wir das Alphabet sodass die Wahrscheinlichkeit auf beiden Seiten ungefähr gleich ist. Diesen Vorgang wiederholen wir und übertragen ihn in eine Baumstruktur.

![](shannon_fano.png)

Dies ergibt nicht das Optimale Encoding deswegen verwendet mann meist [Huffman-Encoding](Huffman-Encoding.md).
