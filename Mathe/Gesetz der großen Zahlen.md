Seien $X_1,\dots, X_n: \Omega \to \mathbb R$ [Zufallsvariablen](Zufallsvariablen.md) auf dem diskreten Wahrscheinlichkeitsraum $\Omega$, die [unabhängig und identisch verteilt](Zufallsvariablen.md#Unabhängig%20und%20identisch%20verteilt)
sind und fuer die $E(X^2_i)$ existiere. Wir schreiben
$$\begin{align}
&\mu = E(X_i)\\
&\sigma = \sigma(X_i)
\end{align}$$
Dann gilt für alle $\epsilon > 0$, dass
$$P\left(\left|\frac{X_1 + \dots + X_n}{n} - \mu\right| \ge \epsilon\right) \le \frac{\sigma^2}{n\cdot \epsilon^2}$$
insbesondere ist für eine Folge von Zufallsvariablen $X_i$ wie oben
$$\lim_{n\to\infty}P\left(\left|\frac{X_1 + \dots + X_n}{n} - \mu\right| \ge \epsilon\right) = 0$$
Ebenso gilt 
$$\lim_{n\to\infty}P\left(\left|\frac{X_1 + \dots + X_n}{n} - \mu\right| < \epsilon\right) = 1$$

