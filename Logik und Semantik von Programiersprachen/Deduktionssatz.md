## Semantisch
>[!PROPOSITION] 
>$$\Sigma \vDash \varphi \to \psi \text{ gdw } \Sigma, \varphi \vDash \psi$$

## Syntaktisch
>[!Proposition]
> $$\Sigma\vDash \varphi \to \psi\;\text{gdw}\; \Sigma \cup \lbrace \varphi \rbrace \vDash \psi$$ 

## Beweis

$\implies$ Angenommen $I\vDash \Sigma \cup \lbrace \varphi \rbrace$. Zu zeigen $I \vDash \psi$. Aus der Annahme folgt $I \vDash \varphi \to \psi$. Aus $I \vDash \varphi$ folgt $I\vDash \psi$ .

$\Longleftarrow$  Angenommen $I \vDash \Sigma$. Unser Ziel ist es $I \vDash \varphi \to \psi$ zu zeigen. Es genuegt zu zeigen, dass wenn $I\vDash \varphi$ gilt, dann $I\vDash \psi$ . Also nehmen wir an dass $I\vDash \varphi$. In diesem Fall haben wir $I\vDash \Sigma \cup \lbrace\varphi\rbrace$ und dies impliziert zusammen mit der Annahme $I\vDash \psi$.
$\blacksquare$ 
