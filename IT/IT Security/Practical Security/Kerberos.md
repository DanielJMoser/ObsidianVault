## Definition

**Kerberos** ist ein **Netzwerk-Authentifizierungsprotokoll**, das darauf abzielt, sichere Authentifizierung in unsicheren Netzwerken zu ermöglichen. Es wurde ursprünglich am **MIT** entwickelt und basiert auf [[Symmetrische Verschlüsselung|Symmetrischer Kryprographie]] sowie dem Konzept eines **Trusted Third Party** (TTP), um die Identitäten von Benutzern und Diensten zu verifizieren. 
Kerberos ermöglicht es, dass sich Benutzer sicher gegenüber Diensten ausweisen können, ohne dass Passwörter über das Netzwerk übertragen werden.

## Funktionsweise

Kerberos verwendet ein System von **Tickets** und **Sitzungsschlüsseln**, um die Authentifizierung und Autorisierung durchzuführen:

1. **Anmeldung beim Authentication Service (AS):**

   - Der Benutzer gibt seinen Benutzernamen ein.
   - Der **Authentication Server (AS)** überprüft die Identität des Benutzers und erstellt ein **Ticket Granting Ticket (TGT)**, das mit dem Passwort des Benutzers verschlüsselt wird.

2. **Erhalt des TGT:**

   - Der Benutzer entschlüsselt das TGT mit seinem Passwort.
   - Das TGT enthält einen **Sitzungsschlüssel** für die Kommunikation mit dem **Ticket Granting Server (TGS)**.

3. **Anforderung eines Service-Tickets vom TGS:**

   - Mit dem TGT fordert der Benutzer ein **Service-Ticket** für einen bestimmten Dienst an.
   - Der TGS überprüft das TGT und erstellt ein Service-Ticket, das für die Authentifizierung beim gewünschten Dienst verwendet wird.

4. **Zugriff auf den Dienst:**

   - Der Benutzer präsentiert das Service-Ticket dem Ziel-Dienst.
   - Der Dienst überprüft das Ticket und gewährt Zugriff, wenn die Authentifizierung erfolgreich ist.

## Komponenten

- **Client:** Der Benutzer oder Prozess, der auf einen Dienst zugreifen möchte.
- **Authentication Server (AS):** Überprüft die Identität des Clients und stellt das Ticket Granting Ticket aus.
- **Ticket Granting Server (TGS):** Stellt Service-Tickets für den Zugriff auf spezifische Dienste aus.
- **Key Distribution Center (KDC):** Kombination aus AS und TGS; zentraler Bestandteil des Kerberos-Systems.
- **Service Server:** Der Server, der den angeforderten Dienst bereitstellt.

## Vorteile

- **Starke Authentifizierung:** Durch den Einsatz von Tickets und Verschlüsselung wird eine sichere Authentifizierung gewährleistet.
- **Einmalanmeldung (Single Sign-On):** Benutzer müssen sich nur einmal authentifizieren, um auf mehrere Dienste zuzugreifen.
- **Keine Übertragung von Passwörtern:** Passwörter werden nicht im Klartext über das Netzwerk gesendet, was das Risiko von Abhörangriffen reduziert.
- **Zeitbeschränkte Tickets:** Tickets haben eine begrenzte Gültigkeitsdauer, was die Sicherheit erhöht.

## Nachteile

- **Abhängigkeit vom KDC:** Der **Single Point of Failure**; wenn der KDC ausfällt, können keine Authentifizierungen mehr durchgeführt werden.
- **Zeit-Synchronisation erforderlich:** Kerberos erfordert, dass alle Systeme synchronisierte Uhren haben, um die Gültigkeit von Tickets zu überprüfen.
- **Komplexität:** Die Einrichtung und Verwaltung von Kerberos kann komplex sein und erfordert spezialisiertes Wissen.
- **Begrenzung auf symmetrische Kryptographie:** Setzt voraus, dass sowohl der Client als auch der Server einen gemeinsamen geheimen Schlüssel mit dem KDC teilen.

## Anwendungsgebiete

- **Unternehmensnetzwerke:** Häufig in **Windows-Domänen** und **Active Directory** für die Authentifizierung von Benutzern und Diensten eingesetzt.
- **UNIX/Linux-Systeme:** Integration von Kerberos zur Authentifizierung von Diensten wie SSH, NFS oder E-Mail.
- **Verteilte Systeme:** Anwendungen, die eine sichere Authentifizierung in verteilten Umgebungen benötigen.

## Zusammenfassung

**Kerberos** ist ein bewährtes Protokoll für die sichere Authentifizierung in Netzwerken. Durch die Verwendung von Tickets und verschlüsselten Sitzungen ermöglicht es eine **sichere Kommunikation** zwischen Clients und Diensten ohne die Notwendigkeit, Passwörter über das Netzwerk zu senden. Trotz einiger Herausforderungen wie der Komplexität und der Abhängigkeit von synchronisierten Systemzeiten bleibt Kerberos ein wichtiger Bestandteil moderner **IT-Security**-Infrastrukturen.

---

#ITsecurity
