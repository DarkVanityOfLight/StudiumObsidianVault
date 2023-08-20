Huffman-Encoding generiert Optimale Encodings für Bitvektor Wörter.


Gegeben ist ein Alphabet $\Sigma = \lbrace \sigma_{1}, \dots, \sigma_{n} \rbrace$ mit den Wahrscheinlichkeiten $P(\sigma_{i})$. Wir sortieren das Alphabet und fügen die beiden kleinsten Wahrscheinlichkeiten zusammen in einen Baum. Diesen Schritt wiederholen wir bis es nur noch einen Baum gibt.