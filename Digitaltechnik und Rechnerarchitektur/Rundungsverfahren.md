

## Runden nach $-\infty$

$f(x) := \lfloor x\rfloor$

## Runden nach $+\infty$

$f(x) := \lceil x \rceil = -\lfloor -x \rfloor$

## Runden nach $0$

$$f(x) := \begin{cases}
\lfloor x\rfloor : x \geq 0\\
\lceil x\rceil :x < 0\\
\end{cases}$$

## Runden zum nächsten in Richtung $-\infty$

$$f(x) := \lceil x-0.5 \rceil$$

## Runden zum nächsten in Richtung $\infty$

$$f(x) := \lfloor x + 0.5\rfloor$$

## Runden zum nächsten in Richtung $0$

$$f(x) := \begin{cases}
\lceil x - 0.5\rceil : x \geq 0\\
\lfloor x+0.5\rfloor : x < 0
\end{cases}$$

## Runden zur nächsten geraden Zahl

$$f(x) := \begin{cases}
\lfloor x\rfloor : x - \lfloor x \rfloor < 0.5\\
\lceil x\rceil : x- \lfloor x\rfloor > 0.5\\
\lfloor x\rfloor : x - \lfloor x \rfloor = 0.5\text{ und $\lfloor x \rfloor$ gerade}\\
\lceil x \rceil: \text{sonst}
\end{cases}$$


