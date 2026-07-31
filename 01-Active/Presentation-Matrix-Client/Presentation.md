# myChat
Ein **Matrix-Plugin** fuer die myMCI

---

# Problemstellung

Aktuell fehlt uns ein **niedrigschwelliger, sicherer Kommunikationskanal**:
- In erster Linie fuer Incomings: Keine Kommunikation zwischen Aufnahme und  Studienbeginn -> Absagen von 10-15%
- Auch zur studentischen Vernetzung **vor, waehrend und nach** dem Studium
	- Wohnungssuche
	- Start-Up-Gruendung
	- Buddy-Programm
	- ...etc...
- e.g. Kim Fladda meldete schon Interesse an, diesen Kanal fuer regulaere Studienanfaenger:innen aus dem Ausland zu nutzen.


---
# Fokus
**-> Kommunikationsplattform fuer Incomings**

- "Vertrauenswuerdige" Incomings erhalten schon frueher als bisher Zugriff auf unsere IT-Infrastruktur.
	- "Vertrauenswuerdig" heisst: LA bereits eingereicht (TBD!)
	- Max. 12 Monate vor Ankunft (laut IRO reicht auch 6... wird noch entschieden)
	- Max. 6 Monate nach Abreise
- Aktuell wird von IRO ein **WhatsApp-Chat** bespielt (etwa: Wohnboerse, allgemeine Kurzinfos, Erinnerungen, etc.) -> suboptimal!
- **Von IRO vorgeschlagen**: Plugin von **Studo**, welches diesen Use-Case abdecken soll.
- Wir kontern mit **Matrix**.

---

Mat

# Matrix in a nutshell

-> kein "Produkt" in dem Sinne, sondern ein offenes Protokoll. Vgl. E-Mail!

- Dezentralisiert, MCI betreibt Homeserver via matrix.mci4me.at
- Clients gibt's zuhauf: MCI-eigene Webinstanz von _Element_ auf chat.mci4me.at.
- E2EE per default, implementiert den urspruenglich fuers Signal-Protokoll entwickelten **Double Ratchet Algorithm**

---

# Vorgehensweise
- Klarzustellen: **Ab wann** koennen wir den Incomings einen **mci4me-Account** verpassen?
- **Konfiguration** der existierenden Infrastruktur
	- Erstellen von sog. Spaces bzw. Rooms
	- Permission-Management
	- Lifecycles anpassen
	- Danach: Technisch gesehn ready-to-go?
- **myChat** als integrierten, minimalen Client in die myMCI

---




# myChat -- Architektonische Ueberlegungen

Genau genommen eine separate App:

- Eigener Login (user-facing bis SSO viable wird)
- Eigene secrets (Login-Token und Crypto-Store)
- Calls zu matrix.mci4me.at, nicht zum Designer
- Eigene Content Security Policy
- Push-Notifikationen werden separat gehandled
- ...
- Vor allem aber: Vergleichsweise hohen XSS-Potenzial.

Daher erscheint mir eine separate WebView ziemlich sinnvoll. Es gibt mMn. keinen Grund, warum sich die Beiden eine Origin (und damit Zugriff auf localStorage und den myMCI-Token) teilen sollen.

---
# myChat -- Architektonische Ueberlegungen 2

Eine moeglichst simple Bridge sorgt fuer die Kommunikation zwischen myMCI und myChat. Aktuell:

- unread-count
- close-chat
- Handling von Deep-Links und hardwareBackButton
- secure-storeage-get/set/remove

---

# FAQ
## "Warum nicht einfach Element in einer WebView laufen lassen?"

Gute Frage! Waere die einfache Loesung -> Laeuft schon auf chat.mci4me.at, hoeheres Sicherheitsniveau.

Aber:
- auf Speicherebene des In-App-Browsers beschraenkt
	- kein Hardware-Keychain/Keystore moeglich
	- keine nativen Push-Nachrichten
- kein Branding