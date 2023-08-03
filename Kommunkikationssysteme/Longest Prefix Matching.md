

Wenn ein Router in seine Forwading Table für eine bestimmte Adresse schaut, benutzt er das Laengste Adress Prefix das die Adresse beinhaelt.



| Destination Address Range       | Link Interface |
|---------------------------------|----------------|
| 11001000 00010111 00010\*\*\* \*\*\*\*\*\*\*\*         | 0              |
| 11001000 00010111 00011000 \*\*\*\*\*\*\*\*     | 1              |
| 11001000 00010111 00011 \*\*\* \*\*\*\*\*\*\*\*        | 2              |
| Otherwise                       | 3              |

11001000 00010111 00010|110 10100001 -> 0