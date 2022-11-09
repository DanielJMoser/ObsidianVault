
-> Teil einer **netzwerk-Adresse**, der die Zuordnung von [[TCP]]- bzw. [[UDP]]-Verbindungen zu [[Socket|Sockets]] durch das Betriebssystem ermöglicht.

Gültige Portnummern sind **0 - 65535**!
Sie müssen **eindeutig** in dem jeweiligen Adressraum sein (TCP und UDP respektive).

Eine TCP- bzw. UDP-Verbindung wird durch das **Quadrupel** <mark style="background: #FFB8EBA6;">(Quell-IP, Quell-Port, Ziel-IP, Ziel-Port)</mark> **eindeutig** bestimmt.

Traditionell sind bestimmten Netzwerkdiensten bestimmte Portnummern zugewiesen. So ist **Port 80** etwa für Webserver und **Port 25** für SMTP-Server reserviert.

![[Sock.png]]

