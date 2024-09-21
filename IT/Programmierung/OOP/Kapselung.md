# Kapselung in der Objektorientierten Programmierung (OOP)

## Definition

**Kapselung** ist ein fundamentales Konzept der *[[_Objektorientierte Programmierung|Objektorientierten Programmierung]]* (OOP), das darauf abzielt, die **Daten** und die **Methoden**, die auf diese Daten operieren, innerhalb einer Klasse zu bündeln. Durch Kapselung werden die internen Zustände eines Objekts vor dem direkten Zugriff von außen geschützt, was zu einer besseren **Datenintegrität** und **Modularität** führt.

## Prinzipien der Kapselung

#### Datenabstraktion

Die **Datenabstraktion** verbirgt die komplexen Details der Implementierung und präsentiert nur die notwendigen Schnittstellen für den Benutzer. Dies erleichtert die Nutzung der Klasse, ohne die internen Funktionsweisen kennen zu müssen.

#### Zugriffskontrolle

Durch **Zugriffsspezifikatoren** wie *private*, *protected* und *public* wird geregelt, welche Teile des Codes auf bestimmte Klassenmitglieder zugreifen können. Dies verhindert unautorisierte oder unbeabsichtigte Manipulationen der Daten.

#### Trennung von Schnittstelle und Implementierung

Die **Schnittstelle** definiert, wie mit dem Objekt interagiert werden kann, während die **Implementierung** die internen Details verbirgt. Dies ermöglicht es, die Implementierung zu ändern, ohne die Benutzer der Klasse zu beeinträchtigen.

## Vorteile der Kapselung

- **Sicherheit der Daten:** Schützt vor unautorisiertem Zugriff und Modifikationen.
- **Wartbarkeit:** Erleichtert die Pflege und Aktualisierung des Codes.
- **Wiederverwendbarkeit:** Ermöglicht die Nutzung von Klassen in verschiedenen Kontexten ohne Anpassungen.
- **Flexibilität:** Änderungen in der Implementierung erfordern keine Änderungen im restlichen Code.

## Umsetzung in Programmiersprachen

Die meisten objektorientierten Programmiersprachen bieten Mechanismen zur Unterstützung der Kapselung.

#### Beispiel in Java:

```java
public class Konto {
    private double saldo;

    public double getSaldo() {
        return saldo;
    }

    public void einzahlen(double betrag) {
        if (betrag > 0) {
            saldo += betrag;
        }
    }
}
```

#### Beispiel in C++:

```java
class Konto {
private:
    double saldo;
public:
    double getSaldo() {
        return saldo;
    }
    void einzahlen(double betrag) {
        if (betrag > 0) {
            saldo += betrag;
        }
    }
};
```

## Zusammenfassung

Die **Kapselung** ist ein wesentliches Prinzip der OOP, das zur Erstellung von robusten, sicheren und modularen Software-Systemen beiträgt. Durch die Beschränkung des Zugriffs auf die internen Zustände von Objekten und die Bereitstellung klar definierter Schnittstellen fördert sie **guten Programmierstil** und **Softwarequalität**.

---

#OOP