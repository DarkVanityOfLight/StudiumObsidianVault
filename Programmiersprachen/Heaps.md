Ein Heap ist ein [Baum](Baum.md), sodass:

- jedem Knoten ist ein Schlüssel zugeordnet
- für jeden Kindknoten ist der Schlüssel nicht grösser als der des Elternknotens.
- Er links-vollständig ist.

Links-vollständige Heaps können einfach als Array dargestellt werden:

![heap](heap.png)

Für den Knoten mit Index $i$ haben wir:

- `left(i) = 2*i`
- `right(i) = 2*i+1`
- `parent(i) = i//2`

Wir definieren eine Heap Eigenschaft:

$$
A[parent(i)] \geq A[i] \forall 2 \leq i\leq n
$$

Die Knoten eines links-vollständigen Binärbaums bilde ein zusammenhängendes Anfangsstück des Arrays.

