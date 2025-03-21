## Definition

**Polymorphismus** ist ein grundlegendes Konzept in der [[_Objektorientierte Programmierung|objektorientierten Programmierung (OOP)]], das die Fähigkeit beschreibt, dass Objekte verschiedener Klassen über eine **einheitliche Schnittstelle** interagieren können. Der Begriff stammt aus dem Griechischen und bedeutet **"Vielgestaltigkeit"**. In der Informatik ermöglicht Polymorphismus, dass eine Methode oder Funktion je nach Kontext unterschiedliche Formen oder Implementierungen annehmen kann.

## Arten des Polymorphismus

### 1. Subtyp-Polymorphismus (Inklusionspolymorphismus)

- **[[Vererbung, Spezialisierung, Generalisierung#Vererbung (Inheritance)|Vererbung]]:** Ermöglicht es einer Unterklasse, die Methoden ihrer Oberklasse zu überschreiben oder zu erweitern.
- **Interfaces:** Klassen können gemeinsame Schnittstellen implementieren und dadurch polymorph verwendet werden.

### 2. Ad-hoc-Polymorphismus

- **Methodenüberladung:** Mehrere Methoden im selben Gültigkeitsbereich haben denselben Namen, aber unterschiedliche Parameterlisten.
- **Operatorüberladung:** Operatoren werden für benutzerdefinierte Datentypen neu definiert.

### 3. Parametrischer Polymorphismus

- **Generika:** Ermöglichen es, Klassen und Methoden mit **Typvariablen** zu definieren, die zur **Laufzeit** spezifiziert werden.

## Dynamische vs. Statische Bindung

- **Statische Bindung (Compile-Time Polymorphismus):** Die Methode wird während der **Kompilierungszeit** gebunden. Beispiele: Methodenüberladung.
- **Dynamische Bindung (Run-Time Polymorphismus):** Die Methode wird zur **Laufzeit** basierend auf dem Objekttyp gebunden. Beispiele: Methodenüberschreibung in Vererbungshierarchien.

## Vorteile des Polymorphismus

- **Flexibilität:** Erlaubt es, allgemeine Schnittstellen zu definieren und spezifische Implementierungen bereitzustellen.
- **Erweiterbarkeit:** Neue Klassen können hinzugefügt werden, ohne den vorhandenen Code zu ändern.
- **Wiederverwendbarkeit:** Förderung von Code-Resuability durch Verwendung von allgemeinen Klassen und Methoden.

## Beispiele

### Beispiel 1: Vererbung und Methodenüberschreibung

```java
public class Fahrzeug {
    public void fahren() {
        System.out.println("Das Fahrzeug fährt.");
    }
}

public class Auto extends Fahrzeug {
    @Override
    public void fahren() {
        System.out.println("Das Auto fährt auf der Straße.");
    }
}

public class Boot extends Fahrzeug {
    @Override
    public void fahren() {
        System.out.println("Das Boot fährt auf dem Wasser.");
    }
}
```

#### Verwendung

```java
public class Hauptprogramm {
    public static void main(String[] args) {
        Fahrzeug fahrzeug1 = new Auto();
        Fahrzeug fahrzeug2 = new Boot();

        fahrzeug1.fahren(); // Ausgabe: Das Auto fährt auf der Straße.
        fahrzeug2.fahren(); // Ausgabe: Das Boot fährt auf dem Wasser.
    }
}
```

### Beispiel 2: Generika (Parametrischer Polymorphismus)
```java
public class Box<T> {
    private T inhalt;

    public void setInhalt(T inhalt) {
        this.inhalt = inhalt;
    }

    public T getInhalt() {
        return inhalt;
    }
}
```

#### Verwendung
```java
Box<String> stringBox = new Box<>();
stringBox.setInhalt("Hallo Welt");
System.out.println(stringBox.getInhalt()); // Ausgabe: Hallo Welt

Box<Integer> integerBox = new Box<>();
integerBox.setInhalt(123);
System.out.println(integerBox.getInhalt()); // Ausgabe: 123
```


## Zusammenfassung

**Polymorphismus** ist ein zentrales Prinzip der objektorientierten Programmierung, das es ermöglicht, Objekte und Methoden flexibel und erweiterbar zu gestalten. Durch die Fähigkeit, Methoden und Klassen auf unterschiedliche Weise zu verwenden, fördert Polymorphismus die **Modularität**, **Wartbarkeit** und **Wiederverwendbarkeit** von Code.

---
#OOP