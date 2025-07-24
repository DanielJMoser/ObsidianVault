
-> zwei Ansätze zur Verarbeitung von Aufgaben in der Informatik.
Allerdings: Unterschiedliche Ziele, Strukturen und Herausforderungen!

# Parallele Systeme

-> Ziele darauf ab, Aufgaben durch die **gleichzeitige** Nutzung **mehrerer Prozessoren oder Kerne** **innerhalb** eines Systems schneller zu erledigen. Der Hauptfokus liegt auf der Reduktion der Rechenzeit für rechenintensive Anwendung durch **parallele Verarbeitung**.

## Architektur
-> Verfügen über eine **gemeinsame** Speicherarchitektur, in der mehrere Prozessoren auf denselben Speicher zugreifen. Beispiele sind **Mehrkernprozessoren** und **Supercomputer**.

## Kommunikation
Nutzen in der Regel **schnellen**, **direkten** Zugriff auf den gemeinsamen Speicher für die Kommunikation zwischen Prozessoren, was eine hohe Bandbreite und niedrige Latenz bietet.

## Fehlertoleranz
Haben meist eine **geringere** Fehlertoleranz, da ein Fehler in einem zentralen System (z. B. einem Knoten oder Prozessor) das gesamte System beeinträchtigen kann.

## Skalierbarkeit
Skalieren durch Hinzufügen von mehr Prozessoren oder Kernen zu einem einzigen System. Die Skalierbarkeit ist **physisch begrenzt** durch den verfügbaren Platz und die Architektur.

## Programmierbarkeit
Programmierung erfordert parallele Algorithmen und oft **spezielle Programmiersprachen** oder **Bibliotheken**, die parallele Operationen unterstützen (z. B. OpenMP, CUDA).

___
# Verteilte Systeme
-> Zielen darauf ab, Ressourcen über **mehrere**, **geografisch verteilte** Systeme oder Netzwerke hinweg zu nutzen. Der Fokus liegt auf der **Skalierbarkeit**, **Fehlertoleranz** und der gemeinsamen Nutzung von Ressourcen über verschiedene Standorte hinweg

## Architektur
Haben eine verteilte Architektur **ohne** gemeinsamen Speicher. Jedes System hat seinen **eigenen** Speicher und kommuniziert über ein **Netzwerk** (z. B. Cluster, Cloud Computing, verteilte Datenbanken).

## Kommunikation
Kommunizieren über **Netzwerke**, was zu **höheren Latenzen** und geringerer Bandbreite im Vergleich zu parallelen Systemen führt. Die Kommunikation erfolgt oft über **Nachrichten** oder **Remote Procedure** Calls (RPCs).

## Fehlertoleranz
Sind oft so gestaltet, dass sie **hohe** Fehlertoleranz bieten, da der Ausfall eines Knoten nicht unbedingt das gesamte System betrifft. Mechanismen zur Replikation und Redundanz sind häufig integriert.

## Skalierbarkeit
Bieten eine **höhere Skalierbarkeit**, da neue Knoten einfach über das Netzwerk hinzugefügt werden können, **unabhängig** von der physischen Standort.

## Programmierung
Programmierung erfordert oft Techniken für **verteilte Kommunikation, Synchronisation und Konsistenz** (z. B. REST, gRPC, verteilte Transaktionen).