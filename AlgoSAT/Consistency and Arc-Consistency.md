An encoding is _consistent_ if whenever a partial [assignment](Assignment.md) is inconsistent with respect to $C$ (it cannot be extended to a solution of $C$) [Unit Propagation](Unit%20Propagation.md) results in a conflict


The encoding is _arc-consistent_ if 
1. it is consistent and
2. Unit Propagation discards values that cannot be assigned


Consistency detects impossible partial assignments, and arc-consistency also prunes impossible single values.

