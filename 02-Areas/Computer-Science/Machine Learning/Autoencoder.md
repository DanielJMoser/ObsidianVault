-> (von griech. *autós* = „selbst“). Ein neuronales Netzwerk, das lernt, seine **eigene Eingabe** zu rekonstruieren.

Ein Autoencoder ist eine Art von **künstlichem neuronalen Netzwerk**, das Daten zuerst in eine **komprimierte Darstellung** übersetzt und daraus anschließend wieder die **ursprünglichen Daten** herstellt.
Da die Eingabe gleichzeitig das Ziel ist, werden **keine Labels** benötigt. Autoencoder gehören daher zum [[Unsupervised Learning]] (genauer: *Self-Supervised Learning*).

## Aufbau

Ein Autoencoder besteht aus **zwei Teilen**, die in einer **Sanduhr-Form** angeordnet sind:

- **Encoder** -> komprimiert die Eingabe $x$ in einen niedrigdimensionalen **Code** $z$
- **Decoder** -> rekonstruiert aus dem Code $z$ die Ausgabe $\hat{x}$

Die schmale Schicht in der Mitte heißt **Bottleneck** (Flaschenhals) bzw. **Latent Space**. Weil sie **weniger Neuronen** als die Eingabe hat, kann das Netz die Daten nicht einfach kopieren, sondern muss die **wichtigsten Merkmale** lernen.

![[Large-Langstrumpf-Model.png]]

*Im Bild: 7 Wörter (One-Hot) -> 2 Neuronen -> 7 Ausgaben. Die 2 mittleren Neuronen bilden den Bottleneck, die Werte dort sind die **Embeddings**.*
*Achtung: Dieses Modell sagt das **nächste Wort** voraus und nicht dasselbe Wort. Streng genommen ist es also ein Encoder-Decoder-Sprachmodell, kein echter Autoencoder. Die Sanduhr-Form ist aber dieselbe.*

#### Formel

$$z = f(W_e \cdot x + b_e)$$
$$\hat{x} = g(W_d \cdot z + b_d)$$

- $x$ -> Der Eingabevektor
- $z$ -> Der Code im Bottleneck (Latent-Vektor)
- $\hat{x}$ -> Die Rekonstruktion der Eingabe
- $W_e, b_e$ -> Gewichte und Bias-Werte des Encoders
- $W_d, b_d$ -> Gewichte und Bias-Werte des Decoders
- $f, g$ -> Aktivierungsfunktionen

#### Verlustfunktion

Trainiert wird, indem der Unterschied zwischen Eingabe und Rekonstruktion minimiert wird, z.B. mit dem [[Mean-squared Error]]:

$$Loss = \frac{1}{n} \Sigma_i (x_i - \hat{x}_i)^2$$

Die Gewichte werden wie gewohnt über [[Forward Propagation]] und [[Backpropagation]] angepasst.

## Varianten

- **Undercomplete Autoencoder** -> der klassische Fall: Bottleneck ist kleiner als die Eingabe
- **Denoising Autoencoder** -> bekommt eine **verrauschte** Eingabe und soll die **saubere** Version rekonstruieren
- **Sparse Autoencoder** -> erzwingt, dass nur **wenige Neuronen** im Code gleichzeitig aktiv sind
- **Variational Autoencoder (VAE)** -> lernt eine **Wahrscheinlichkeitsverteilung** im Latent Space; daraus können **neue Daten generiert** werden

## Anwendungen

- **Dimensionsreduktion** -> ähnlich wie die [[Principal Component Analysis]], aber durch nichtlineare Aktivierungsfunktionen auch für **nichtlineare** Zusammenhänge geeignet (ein linearer Autoencoder mit MSE lernt denselben Unterraum wie die PCA)
- **Anomalieerkennung** -> ungewöhnliche Daten werden **schlecht rekonstruiert** und haben daher einen hohen Loss
- **Entrauschen** von Bildern oder Audio
- **Feature Learning** -> der Encoder wird als Vorverarbeitung für andere Modelle verwendet
- **Generative Modelle** (VAE)

# Bedeutung

Der **Encoder** lernt, die Eingabe auf ihre **wesentlichen Merkmale** zu reduzieren, der **Decoder** lernt, daraus wieder die Eingabe herzustellen.
Ist der Bottleneck **zu groß**, lernt das Netz nur eine Kopie der Eingabe und nichts Nützliches (vgl. [[Overfitting und Underfitting]]). Ist er **zu klein**, geht zu viel Information verloren.