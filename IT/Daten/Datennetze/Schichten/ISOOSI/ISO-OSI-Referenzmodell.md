#Datennetze 

-> Theoretisches Referenzmodell, entwickelt von der **International Standards Organisation** (ISO)

-> Modelliert die Verbindung offener Systeme, daher der Name **Open Systems Interconnection** (OSI)

Es handelt sich dabei um ein **hierarchisches Modell**, welches in **Schichten** aufgeteilt ist. 

Das **vollständige** Schichtenmodell verfügt über 7, das **verkürzte** über 5 Schichten. 

- Jede davon erfüllt genau **eine** Aufgabe. 
- Die Funktionalität ist **gekapselt** und nur durch eine **klar definierte Schnittstelle** zugänglich. 
- Jede Schicht baut auf der darunterliegenden auf und bietet Services für die darüberliegende an.
- Bieten sie die selbe Schnittstelle an, sind die Schichten **austauschbar**

Zum Vergleich: [[Teile-und-Herrsche-Prinzip]] bei Software!


## Schichten des ISO/OSI-Modells

Das ISO/OSI-Modell besteht aus 7 Schichten, die jeweils eine spezifische Aufgabe übernehmen und auf den darunterliegenden Schichten aufbauen. Jede Schicht kommuniziert dabei über klar definierte Schnittstellen mit der darüber- und darunterliegenden Schicht.

### 1. **Bitübertragungsschicht (Physical Layer)**
- Verantwortlich für die **physikalische Übertragung** von Daten.
- Definiert, wie Bits als elektrische, optische oder Funk-Signale über ein Medium übertragen werden.
- Beispiele: Kabeltypen (z. B. Kupferkabel, Glasfaser), elektrische Spannungen, Frequenzen.

### 2. **Sicherungsschicht (Data Link Layer)**
- Zuständig für die **fehlerfreie Übertragung** von Datenrahmen (Frames) zwischen direkt verbundenen Geräten.
- **MAC-Adressen** werden hier verwendet, um einzelne Geräte im Netzwerk zu identifizieren.
- Beispiele: Ethernet, PPP (Point-to-Point Protocol).

### 3. **Vermittlungsschicht (Network Layer)**
- Verantwortlich für die **logische Adressierung** und **Wegewahl (Routing)** von Datenpaketen.
- Nutzt **IP-Adressen** zur Identifikation von Geräten.
- Bestimmt den besten Pfad für die Datenübertragung über das Netzwerk.
- Beispiel: IP (Internet Protocol).

### 4. **Transportschicht (Transport Layer)**
- Stellt eine **Ende-zu-Ende-Kommunikation** zwischen Hosts sicher.
- Garantiert die **Zuverlässigkeit** der Verbindung (z. B. durch Bestätigungen und Neuübertragungen).
- Nutzt Protokolle wie **TCP** (verbindungsorientiert) und **UDP** (verbindungslos).
- Verwendet **Ports**, um Anwendungen auf einem Gerät eindeutig zu identifizieren.

### 5. **Sitzungsschicht (Session Layer)**
- Kontrolliert und verwaltet die **Verbindungen** (Sitzungen) zwischen zwei Geräten.
- Synchronisiert den Datenfluss und stellt sicher, dass Sitzungen nach Unterbrechungen wiederhergestellt werden können.
- Beispiel: NetBIOS, RPC (Remote Procedure Call).

### 6. **Darstellungsschicht (Presentation Layer)**
- Übersetzt Daten in ein **standardisiertes Format**, das von der Anwendung verstanden werden kann.
- Sorgt für **Verschlüsselung**, **Kompression** und **Konvertierung** von Daten.
- Beispiel: JPEG, ASCII, SSL/TLS für Verschlüsselung.

### 7. **Anwendungsschicht (Application Layer)**
- Die höchste Schicht, in der Anwendungen direkt mit dem Netzwerk kommunizieren.
- Stellt **Protokolle** und **Dienste** bereit, die für Anwendungen wie E-Mail, Webbrowser oder Dateitransfers benötigt werden.
- Beispiele: HTTP, FTP, SMTP.

---

Das verkürzte Modell reduziert diese Schichten auf fünf, indem es einige der Funktionen kombiniert, jedoch bleibt das Prinzip der klaren Trennung der Aufgaben bestehen.


