#BigData
Ein **Data Product** ist ein wiederverwertbares, aktiv gepflegtes Datenpaket, das einen **konkreten Nutzen** für bestimmte Konsumenten liefert. Daten werden dabei nicht als Nebenprodukt von Systemen betrachtet, sondern **wie ein Produkt** behandelt: mit klarer **Verantwortung**, definierter **Schnittstelle** und zugesicherter **Qualität**.

Das Konzept ist ein zentraler Bestandteil von **Data Mesh**, bei dem die Verantwortung für Daten dezentral bei den jeweiligen **Fachbereichen (Domains)** liegt, statt bei einem zentralen Datenteam.

### Eigenschaften

Ein gutes Data Product ist:

-   **Auffindbar**: Es ist in einem Katalog registriert und mit Metadaten beschrieben.
-   **Adressierbar**: Es ist über eine eindeutige, stabile Schnittstelle erreichbar (z. B. Tabelle, API, Stream).
-   **Vertrauenswürdig**: Qualität, Aktualität und Herkunft (Lineage) sind dokumentiert und überwacht.
-   **Selbstbeschreibend**: Schema, Semantik und Beispiele sind dokumentiert, sodass es ohne Rückfragen nutzbar ist.
-   **Interoperabel**: Es folgt gemeinsamen Standards und lässt sich mit anderen Data Products kombinieren.
-   **Sicher**: Zugriffsrechte und Datenschutzvorgaben sind festgelegt und werden durchgesetzt.

___

### Bestandteile

-   **Daten**: Der eigentliche Inhalt, z. B. aus einem [[Handling Data#Data Warehouse|Data Warehouse]] oder [[Handling Data#Data Lake|Data Lake]].
-   **Code**: Die Pipelines zur Erzeugung und Aufbereitung, etwa per [[ETL und ELT]].
-   **Metadaten & Data Contract**: Verbindliche Vereinbarung über Schema, Qualität und Verfügbarkeit (SLAs).
-   **Infrastruktur**: Speicher, Rechenressourcen und Bereitstellung.
-   **Owner**: Ein **Data Product Owner**, der für Pflege und Weiterentwicklung verantwortlich ist.

___

### Abgrenzung

Im Gegensatz zu einem klassischen [[Handling Data#Data Mart|Data Mart]] steht beim Data Product nicht nur die Speicherung, sondern der **gesamte Lebenszyklus** im Fokus: Ein Data Product hat Nutzer, wird versioniert, weiterentwickelt und irgendwann auch wieder abgekündigt.
