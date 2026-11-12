
# Overfitting

-> die Produktion einer Analyse, welche **zu genau** oder **zu exakt** auf ein bestimmtes Datenset passt und dadurch zu ungenauen Zukunftsanalysen führen kann oder nicht mit neuen Daten kompatibel ist.

Das Modell lernt die Trainingsdaten **auswendig**, inklusive **Rauschen** und **Ausreißern**, anstatt das zugrunde liegende **Muster** zu erkennen. Es **generalisiert** daher schlecht.

**Erkennbar an:**
- **niedrigem** Fehler auf dem Trainingsset
- **hohem** Fehler auf dem Validations- bzw. Testset

**Ursachen:**
- Modell ist **zu komplex** (zu viele Parameter, z.B. zu hoher Grad bei der [[Polynomiale Regression|polynomialen Regression]])
- **zu wenige** Trainingsdaten
- **zu langes** Training

# Underfitting

-> die Produktion einer Analyse, welche **zu einfach** ist, um die Struktur der Daten zu erfassen. Das Modell passt weder auf die Trainingsdaten noch auf neue Daten.

Das Modell hat die zugrunde liegenden **Muster nicht gelernt**.

**Erkennbar an:**
- **hohem** Fehler auf dem Trainingsset
- **hohem** Fehler auf dem Validations- bzw. Testset

**Ursachen:**
- Modell ist **zu einfach** (z.B. eine [[(Unvariante) Lineare Regression|lineare Regression]] für nichtlineare Daten)
- **zu wenige** oder ungeeignete **Features**
- **zu kurzes** Training

**Beispiel**: Wir wollen Punkte vorhersagen, die einer Parabel folgen.
- Eine **Gerade** (Grad 1) trifft die Kurve kaum -> **Underfitting**
- Ein Polynom vom **Grad 2** trifft die Form -> **gute Generalisierung**
- Ein Polynom vom **Grad 15** geht durch jeden Trainingspunkt, schwingt dazwischen aber wild hin und her -> **Overfitting**

## Bias-Variance-Tradeoff

Beide Probleme lassen sich über zwei Fehlerquellen beschreiben:

$$Fehler = Bias^2 + Varianz + Rauschen$$

- $Bias$ -> Fehler durch **zu einfache Annahmen** des Modells. Hoher Bias führt zu **Underfitting**
- $Varianz$ -> wie stark das Modell auf **kleine Änderungen** in den Trainingsdaten reagiert. Hohe Varianz führt zu **Overfitting**
- $Rauschen$ -> der **nicht reduzierbare** Fehler in den Daten selbst

Steigt die **Modellkomplexität**, so sinkt der Bias, aber die Varianz steigt. Gesucht ist der **Mittelweg** mit dem geringsten Gesamtfehler.

## Gegenmaßnahmen

**Gegen Overfitting:**
- **mehr Trainingsdaten** sammeln oder künstlich erzeugen (*Data Augmentation*)
- Modell **vereinfachen** (weniger Parameter, weniger Features)
- **Regularisierung** -> bestraft große Gewichte in der Verlustfunktion (L1 / L2)
- **Dropout** -> schaltet beim Training zufällig Neuronen ab (z.B. in einem [[Convolutional Neural Network]])
- **Early Stopping** -> Training abbrechen, sobald der Fehler auf dem Validationsset wieder steigt

**Gegen Underfitting:**
- Modell **komplexer** machen (mehr Parameter, mehr Schichten, höherer Polynomgrad)
- **bessere Features** verwenden
- **länger** trainieren
- **Regularisierung reduzieren**

# Bedeutung

Ziel im Machine Learning ist nicht, die Trainingsdaten perfekt zu treffen, sondern auf **neuen, unbekannten Daten** gut zu funktionieren (**Generalisierung**).
Deshalb wird das Modell auf dem **Trainingsset** trainiert, mit dem **Validationsset** auf Over- und Underfitting geprüft und erst am Ende mit dem **Testset** bewertet (siehe [[_Machine Learning]]).
Vergleicht man den Fehler, z.B. den [[Mean-squared Error]], auf Trainings- und Validationsset, so erkennt man, in welche Richtung das Modell angepasst werden muss.
