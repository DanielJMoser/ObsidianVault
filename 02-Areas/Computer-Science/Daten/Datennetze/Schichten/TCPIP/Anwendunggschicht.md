#Datennetze 

Die Anwendungsschicht ist die oberste Schicht im **TCP/IP-Modell** und ermöglicht die Interaktion zwischen **Anwendungen** und dem **Netzwerk**. Sie bietet die Schnittstelle für Benutzerprogramme, um Netzwerkdienste zu nutzen, und definiert die Protokolle, die für die Kommunikation auf Anwendungsebene erforderlich sind.

---

## Hauptaufgaben der Anwendungsschicht

### Bereitstellung von Netzwerkanwendungen

- Die Anwendungsschicht ermöglicht es Anwendungen wie Webbrowsern, E-Mail-Clients, Dateitransfer-Programmen und anderen Netzwerkdiensten, direkt mit dem Netzwerk zu interagieren.
- Sie definiert Protokolle, die von diesen Anwendungen verwendet werden, um Daten zwischen Geräten auszutauschen.

### Datendarstellung und -formatierung

- Die Anwendungsschicht ist dafür verantwortlich, dass Daten in einer für den Empfänger verständlichen Form präsentiert werden. Dies kann die Konvertierung zwischen verschiedenen Datenformaten, Zeichensätzen oder die Komprimierung von Daten umfassen.
  
### Sitzungsmanagement

- Einige Protokolle der Anwendungsschicht unterstützen das **Sitzungsmanagement**, das den Aufbau, die Verwaltung und den Abbau von Sitzungen zwischen Kommunikationspartnern regelt. Eine Sitzung ermöglicht eine länger andauernde, bidirektionale Kommunikation.

---

## Wichtige Protokolle der Anwendungsschicht

### Hypertext Transfer Protocol (HTTP/HTTPS)

- **HTTP** ist das Hauptprotokoll, das für den Abruf von Webseiten und deren Ressourcen verwendet wird.
- **HTTPS** ist die verschlüsselte Version von HTTP, die Sicherheit durch Transport Layer Security (TLS) oder Secure Sockets Layer (SSL) bietet.
  
### File Transfer Protocol (FTP)

- **FTP** ermöglicht den Dateitransfer zwischen einem Client und einem Server. Es unterstützt verschiedene Kommandos zum Hochladen, Herunterladen und Verwalten von Dateien auf entfernten Servern.
- Ein ähnliches Protokoll, **SFTP (Secure File Transfer Protocol)**, stellt sicher, dass der Datenaustausch verschlüsselt und sicher ist.

### Simple Mail TrInternetschichtansfer Protocol (SMTP)

- **SMTP** wird zum Senden von E-Mails verwendet. Es arbeitet oft in Kombination mit anderen Protokollen wie **IMAP** oder **POP3**, die für den Abruf von E-Mails verantwortlich sind.

### Domain Name System (DNS)

- **DNS** ist ein System zur Auflösung von **Domainnamen** in **IP-Adressen**. Es ermöglicht die Übersetzung leicht verständlicher Domainnamen (z.B. www.example.com) in die für Computer verständlichen IP-Adressen.

### Dynamic Host Configuration Protocol (DHCP)

- **DHCP** dient der automatischen Zuweisung von IP-Adressen und anderen Netzwerkkonfigurationsinformationen (wie Subnetzmaske, Standardgateway und DNS-Server) an Geräte in einem Netzwerk.

---

## Zusammenhang mit den unteren Schichten

- Die Anwendungsschicht sendet Daten an die **Transportschicht**, die für die zuverlässige oder unzuverlässige Übertragung der Daten sorgt, abhängig davon, ob **TCP** oder **UDP** verwendet wird.
- Sie ist die Schnittstelle, über die Benutzer und Programme auf die Dienste des Netzwerks zugreifen. Dabei wird sie von den darunterliegenden Schichten unterstützt, die sich um die korrekte Übertragung und Zustellung der Daten kümmern.

siehe: [[Transportschicht]] für die darunterliegende Schicht im TCP/IP-Modell.
