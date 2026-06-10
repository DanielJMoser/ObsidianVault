#Date\

Die Netzzugangsschicht (auch als "Network Interface Layer" im TCP/IP-Modell bezeichnet) ist die unterste Schicht im TCP/IP-Referenzmodell. Sie kombiniert die Funktionen der **[[Sicherungsschicht]]** und der **[[Bitübertragungsschicht]]** des [[ISO-OSI-Referenzmodell|OSI-Modells]] und ist für den Zugriff auf das physische Netzwerk verantwortlich, indem sie die Schnittstelle zwischen dem Netzwerkmedium und den höheren Schichten des Modells darstellt.

---

## Hauptaufgaben der qNetzzugangsschicht

### Physikalischer Zugriff auf das Übertragungsmedium

- Diese Schicht definiert, wie Daten auf dem physikalischen Medium (z.B. Kupferkabel, Glasfaser, Funkwellen) übertragen werden, indem sie elektrische, optische oder elektromagnetische Signale verwendet.
- Sie umfasst alle Aspekte des Zugriffs auf das physikalische Netzwerk, wie die Wahl der geeigneten Übertragungstechnologie und die Regelung des Zugriffs auf das Medium (z.B. CSMA/CD bei Ethernet).

### Datenrahmen (Frames) und MAC-Adressen

- Die Netzzugangsschicht kapselt Daten in **Frames** ein, die Metadaten wie die Quell- und Ziel-MAC-Adressen (Media Access Control) enthalten.
- **MAC-Adressen** identifizieren eindeutig Netzwerkschnittstellen und ermöglichen die direkte Kommunikation zwischen Geräten innerhalb desselben Netzwerks.

### Fehlererkennung und -korrektur

- Diese Schicht stellt sicher, dass übertragene Datenrahmen fehlerfrei am Ziel ankommen, indem sie Mechanismen wie **CRC (Cyclic Redundancy Check)** verwendet, um Übertragungsfehler zu erkennen.
- Es gibt in der Regel keine automatische Fehlerkorrektur auf dieser Schicht; stattdessen melden die höheren Schichten einen Fehler und initiieren eine erneute Übertragung, falls nötig.

### Flusskontrolle

- Einige Implementierungen der Netzzugangsschicht bieten eine **Flusskontrolle**, um zu verhindern, dass der Empfänger von Daten überlastet wird. Dies wird in der Regel durch Pausen- und Weitersteuermechanismen (z.B. bei Ethernet) realisiert.

---

## Wichtige Technologien der Netzzugangsschicht

### Ethernet (IEEE 802.3)

- **Ethernet** ist eine weitverbreitete Technologie für kabelgebundene Netzwerke und standardisiert den Zugriff auf das physikalische Medium und die Kommunikation zwischen Geräten in einem LAN (Local Area Network).
- Ethernet verwendet das **CSMA/CD (Carrier Sense Multiple Access with Collision Detection)**-Protokoll, um sicherzustellen, dass nur ein Gerät zu einem bestimmten Zeitpunkt auf das Medium zugreift.

### WLAN (IEEE 802.11)

- **WLAN** ermöglicht drahtlose Netzwerke und arbeitet ebenfalls auf der Netzzugangsschicht. Hier wird statt eines physischen Kabels eine drahtlose Verbindung über Funkwellen genutzt.
- WLAN verwendet **CSMA/CA (Carrier Sense Multiple Access with Collision Avoidance)**, um Kollisionen im Netzwerk zu vermeiden.

### PPP (Point-to-Point Protocol)

- **PPP** ist ein Protokoll zur direkten Kommunikation zwischen zwei Netzwerkgeräten. Es wird häufig bei Verbindungen über Modems, ISDN oder VPNs eingesetzt und bietet zusätzliche Funktionen wie Authentifizierung und Verschlüsselung.

### FDDI (Fiber Distributed Data Interface)

- **FDDI** ist eine Glasfaser-basierte Netzwerktechnologie, die für Hochgeschwindigkeits-Datenübertragungen in Weitverkehrsnetzen (WANs) eingesetzt wird. Sie verwendet einen Dual-Ring-Ansatz, um Daten sicher und effizient zu übertragen.

---

## Zusammenhang mit höheren Schichten

- Die Netzzugangsschicht stellt sicher, dass Daten von der **Internetschicht** (IP) über das physikalische Netzwerk übertragen werden.
- Während die Internetschicht für das Routing und die logische Adressierung (IP-Adressen) verantwortlich ist, kümmert sich die Netzzugangsschicht um die physikalische Adressierung (MAC-Adressen) und den Zugriff auf das Netzwerkmedium.

siehe: [[Vermittlungsschicht]] für die darüberliegende Schicht im TCP/IP-Modell.
