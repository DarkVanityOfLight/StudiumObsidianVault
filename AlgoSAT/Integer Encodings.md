Sometimes we might encode a [Variable](Variable.md) $x$ which can take a set of integer values $I$.

- _One hot encoding_
	- Each number is represented by a boolean variable $d_i$
	- At least one number is true
	- At most one number is true
- _Order Encoding_
	- Variables represent that a number is larger or equal $o_{\ge i}$
	- This requires a linear number of binary clauses $o_{\ge i} \lor \overline o_{\ge i+1}$
- _Binary encoding_

