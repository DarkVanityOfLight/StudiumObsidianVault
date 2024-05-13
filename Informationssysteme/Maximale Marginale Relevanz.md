
Das nächste zurückgegebene Dokument $d_i$ soll relevant zur Anfrage $q$ sein, aber auch verschieden zu den bislang zurückgegebenen Dokumenten $d_1\dots d_{i-1}$

$$argmax_{d_i \in D} (\lambda sim(q, d_i) - (1-\lambda)\max_{d_j : 1\leq j<i} sim(d_i, d_j))$$
mit dem Tuning Parameter $\lambda$ und ähnlichkeitsmass $sim$

