##  ...modulo $p$

Eine **primitive Wurzel** modulo $p$ ist eine Zahl $g$, die alle Elemente der Menge $\mathbb{Z}_p^*$ (die multiplikative Gruppe der nicht-nullen Elemente modulo $p$) durch Potenzen von $g$ erzeugen kann.

Das bedeutet, dass für jede Zahl $x$ in $\mathbb{Z}_p^*$, es ein $k$ gibt, sodass:

$$ g^k \mod p = x $$

Die Anzahl der Elemente in $\mathbb{Z}_p^*$ beträgt $p-1$, und eine primitive Wurzel $g$ erzeugt alle diese Elemente, wenn $g^k \mod p$ für $k = 0, 1, 2, \dots, p-2$ unterschiedliche Werte annimmt.

### Beispiel

Wenn $p = 7$, dann sind die Elemente in $\mathbb{Z}_7^*$: $\{1, 2, 3, 4, 5, 6\}$. Eine primitive Wurzel $g = 3$ erzeugt alle Elemente dieser Menge:

- $3^1 \mod 7 = 3$
- $3^2 \mod 7 = 9 \mod 7 = 2$
- $3^3 \mod 7 = 27 \mod 7 = 6$
- $3^4 \mod 7 = 81 \mod 7 = 4$
- $3^5 \mod 7 = 243 \mod 7 = 5$
- $3^6 \mod 7 = 729 \mod 7 = 1$

Da $3$ alle Elemente der Gruppe $\mathbb{Z}_7^*$ erzeugt, ist es eine primitive Wurzel modulo $7$.
