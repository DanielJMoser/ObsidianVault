
**Regression** -> Eine Methode zur Vorhersage eines **Zielwerts** (einer abhängigen Variable) anhand von **unabhängigen Beobachtungen**.

-> Trotz des Namens ist die logistische Regression ein Verfahren zur **Klassifikation**. Sie sagt keinen beliebigen Zahlenwert vorher, sondern die **Wahrscheinlichkeit**, dass eine Beobachtung zu einer bestimmten **Klasse** gehört (z.B. *Spam* / *kein Spam*).

Sie gehört zum [[Supervised Learning]], da die Trainingsdaten **Labels** benötigen (meist $y \in \{0, 1\}$).

## Warum nicht einfach lineare Regression?

Die [[(Unvariante) Lineare Regression|lineare Regression]] liefert Werte von $-\infty$ bis $+\infty$. Eine Wahrscheinlichkeit muss aber **zwischen 0 und 1** liegen.
Außerdem verschieben einzelne **Ausreißer** die Gerade stark, wodurch sich die Klassengrenze verschiebt.

Die Lösung: Das Ergebnis der linearen Funktion wird durch die **Sigmoid-Funktion** geschickt.

## Sigmoid-Funktion

$$\sigma(z) = \frac{1}{1 + e^{-z}}$$

- $z$ -> Eine beliebige reelle Zahl (hier: das Ergebnis der linearen Funktion)
- $\sigma(z)$ -> Ein Wert **zwischen 0 und 1**

Eigenschaften:
- $z$ sehr groß -> $\sigma(z) \approx 1$
- $z$ sehr klein (negativ) -> $\sigma(z) \approx 0$
- $z = 0$ -> $\sigma(z) = 0.5$

Die Kurve hat eine **S-Form**.

#### Vorhersagefunktion

$$h_\theta(x) = \sigma(\theta_0 + \theta_1 * x) = \frac{1}{1 + e^{-(\theta_0 + \theta_1 * x)}}$$

- $h_\theta(x)$ -> Die **Wahrscheinlichkeit**, dass $y = 1$ ist, gegeben $x$: $P(y = 1 \mid x)$
- $\theta_0$ -> Der **Bias** (wie bei der linearen Regression)
- $\theta_1$ -> Das **Gewicht** von $x$; bestimmt, wie **steil** die S-Kurve ist

Bei mehreren Features wird $\theta_0 + \theta_1 * x$ zu $\theta^T x$.

## Entscheidungsgrenze

Um aus der Wahrscheinlichkeit eine **Klasse** zu machen, wird ein **Schwellenwert** (Threshold), meist $0.5$, verwendet:

- $h_\theta(x) \geq 0.5$ -> Klasse **1**
- $h_\theta(x) < 0.5$ -> Klasse **0**

Da $\sigma(z) = 0.5$ genau bei $z = 0$ gilt, liegt die **Entscheidungsgrenze** (Decision Boundary) dort, wo $\theta^T x = 0$ ist. Diese Grenze ist eine **Gerade** (bzw. Ebene), die logistische Regression ist also ein **linearer Klassifikator**.
Für nichtlineare Grenzen können, wie bei der [[Polynomiale Regression|polynomialen Regression]], **Potenzen** der Features hinzugefügt werden.

## Verlustfunktion

Der [[Mean-squared Error]] eignet sich hier **nicht**: Durch die Sigmoid-Funktion wäre die Verlustfunktion **nicht konvex** und hätte viele lokale Minima.
Stattdessen wird die **Log-Loss** (Binary Cross-Entropy) verwendet:

$$Loss = -\frac{1}{n} \Sigma_i \left[ y_i \cdot \log(h_\theta(x_i)) + (1 - y_i) \cdot \log(1 - h_\theta(x_i)) \right]$$

- $y_i$ -> Das tatsächliche Label (0 oder 1)
- $h_\theta(x_i)$ -> Die vorhergesagte Wahrscheinlichkeit
- Ist $y_i = 1$, zählt nur der linke Term -> Loss ist groß, wenn $h_\theta(x_i)$ nahe **0** liegt
- Ist $y_i = 0$, zählt nur der rechte Term -> Loss ist groß, wenn $h_\theta(x_i)$ nahe **1** liegt

Eine **sichere, aber falsche** Vorhersage wird also **sehr stark** bestraft.
Die Parameter $\theta$ werden mit dem **Gradientenabstieg** angepasst. Da es keine geschlossene Formel gibt, geschieht das **iterativ**.

**Beispiel**: Wir sagen anhand der Lernstunden $x$ vorher, ob jemand die Prüfung besteht.
Mit $\theta_0 = -4$ und $\theta_1 = 1$ ergibt sich für $x = 6$ Stunden:
$z = -4 + 1 * 6 = 2$ -> $h_\theta(6) = \sigma(2) \approx 0.88$ -> **88 %** Wahrscheinlichkeit zu bestehen -> Klasse **1**.
Die Entscheidungsgrenze liegt bei $x = 4$ Stunden.

## Mehr als zwei Klassen

- **One-vs-All** (One-vs-Rest) -> für jede Klasse wird ein eigenes Modell trainiert („Klasse A oder nicht?“). Die Klasse mit der höchsten Wahrscheinlichkeit gewinnt
- **Softmax-Regression** (Multinomiale logistische Regression) -> die Sigmoid-Funktion wird durch die **Softmax-Funktion** ersetzt, welche Wahrscheinlichkeiten für alle Klassen gleichzeitig liefert, die sich zu **1** summieren

# Bedeutung

Die logistische Regression ist eines der **einfachsten** und **am besten interpretierbaren** Klassifikationsverfahren: Die Gewichte $\theta$ zeigen direkt, **wie stark** und **in welche Richtung** ein Feature die Wahrscheinlichkeit beeinflusst.
Ein einzelnes **Neuron** mit Sigmoid-Aktivierungsfunktion (siehe [[Forward Propagation]]) ist mathematisch genau eine logistische Regression. Sie ist damit ein Grundbaustein **neuronaler Netzwerke**.
Wie jedes Modell kann sie bei zu vielen Features zu [[Overfitting und Underfitting|Overfitting]] neigen, wogegen **Regularisierung** hilft.
