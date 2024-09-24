#Datennetze 

-> auch: **Internetschicht**

Die Netzwerkschicht (3. Schicht im [[ISO-OSI-Referenzmodell]]) ist verantwortlich für das Routing und die logische Adressierung von Datenpaketen. Sie ermöglicht die Übertragung von Daten zwischen verschiedenen Netzwerken und sorgt dafür, dass die Daten an den richtigen Zielknoten gelangen.

---

## Hauptaufgaben der Netzwerkschicht

### Routing

- **Routing** ist der Prozess, bei dem die Netzwerkschicht den optimalen Weg für Datenpakete durch das Netzwerk bestimmt. Router übernehmen diese Aufgabe, indem sie anhand von Routing-Tabellen entscheiden, wie ein Paket weitergeleitet wird.
- Das Routing kann statisch (vordefinierte Routen) oder dynamisch (durch Protokolle wie OSPF oder BGP) erfolgen.

### Logische Adressierung

- Die Netzwerkschicht verwendet **logische Adressen**, um Geräte eindeutig zu identifizieren. Die bekannteste Form dieser Adressen sind **IP-Adressen** (IPv4/IPv6).
- Jede Netzwerkschnittstelle in einem Netzwerk hat eine eindeutige IP-Adresse, die zur Identifizierung des Geräts dient.

### Fragmentierung

- Wenn die Größe eines Pakets die maximale Übertragungsgröße (MTU) des Mediums überschreitet, wird es aufgeteilt. Diese **Fragmentierung** wird in der Netzwerkschicht durchgeführt.
- Die Pakete werden bei Fragmentierung mit den entsprechenden Feldern versehen, um beim Empfänger wieder korrekt zusammengesetzt zu werden. Dies geschieht durch das **Identification**, **Fragment Offset** und **MF**-Flag, wie bereits in [[IP-Header]] beschrieben.

---

## Wichtige Protokolle der Netzwerkschicht

### Internet Protocol (IP)

- **IPv4**: Verwendet eine 32-Bit-Adresse, was rund 4 Milliarden eindeutige Adressen ermöglicht. Trotz der Adressknappheit wird IPv4 immer noch weitverbreitet genutzt.
- **IPv6**: Die Nachfolgeversion von IPv4, die eine 128-Bit-Adresse nutzt und eine praktisch unbegrenzte Anzahl von IP-Adressen bereitstellt.

### ICMP (Internet Control Message Protocol)

- Verwendet zur Fehler- und Statusmeldung in Netzwerken.
- Bekannt durch Tools wie **ping**, welches die Erreichbarkeit eines Hosts überprüft, oder **traceroute**, welches den Pfad von Paketen durch das Netzwerk anzeigt.

---

## Paketweiterleitung

- Die Netzwerkschicht sorgt dafür, dass Pakete vom Sendernetzwerk zum Zielnetzwerk transportiert werden.
- Jedes Datenpaket enthält eine Quell- und Zieladresse, die in der Netzwerkschicht verarbeitet wird, um den nächsten Schritt im Übertragungsweg zu bestimmen.

---

## ARP (Address Resolution Protocol)

- **ARP** wird genutzt, um die MAC-Adresse (physikalische Adresse) eines Geräts anhand seiner IP-Adresse zu bestimmen.
- Wenn ein Gerät ein Datenpaket senden möchte, aber nur die IP-Adresse des Empfängers kennt, verwendet es ARP, um die entsprechende MAC-Adresse zu ermitteln und so die Daten auf der Sicherungsschicht weiterzuleiten.

---

## NAT (Network Address Translation)

- **NAT** ermöglicht es, mehrere Geräte in einem lokalen Netzwerk mit einer einzigen öffentlichen IP-Adresse zu verbinden. Es ersetzt die Quell-IP-Adresse eines Datenpakets durch die öffentliche IP-Adresse des Routers, um die Privatsphäre im lokalen Netzwerk zu schützen.

siehe: [[Transportschicht]] für die darüberliegende Schicht im OSI-Modell.
