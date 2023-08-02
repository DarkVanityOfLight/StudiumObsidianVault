

## Polling

Es gibt eine sogenannte Master Node, die eine Node darüber informiert das sie nun Senden darf, Probleme ergeben sich daraus das es einen einzelnen Fehlerpunkt gibt(Master) und das es extra overhead durch das Polling gibt. Außerdem kann die Latency deutlich höher sein als sonnst.

## Token Passing

Es gibt ein Token, dieses Token wird von Node zu Node gesendet um anzuzeigen wer Senden darf. Auch hier benötigen wir extra overhead um das Token zu senden, auch die Latency und der Single Point of failure(hier das Token) werden nicht verbessert.

