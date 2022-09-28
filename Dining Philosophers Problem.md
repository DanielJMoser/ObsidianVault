## Dining Philosophers Problem

1. Man denke über phil. Probleme nach
2. Man warte, bis **linke** Gabel verfügbar und nehme diese
3. Man warte, bis **rechte** Gabel verfügbar und nehme diese
4. Man esse
5. Man gebe **linke** Gabel ab
6. Man gebe **rechte** Gabel ab
7. Man beginne von vorne

Oben beschriebender Ablauf funktioniert, so lange nur **einzelne Philosophen** hungrig werden.

Falls aber *alle gleichzeitig*: 

* Alle Philosophen nehmen **linke** Gabel auf
* Warten dann auf das freiwerden der **rechten** Gabel -> Nicht vorhergesehen!
* Diese Art des Mexican Standoffs nennt man [[Deadlock]]