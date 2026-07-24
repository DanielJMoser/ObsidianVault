H1BRwdMmdK
-> Entwickelt zur **E2EE** in Instantmessengern, ursprünglich für **Signal**.

Nach einem ersten Key-Exchange kümmert sich der Algorithmus um **kurzlebige Session-Keys**, die immer wieder erneuert und gewartet werden müssen. Dabei kommen zwei sog. kryptografische "Ratchets" zum Einsatz: Einerseits eine [[Schlüsselableitung]] (Englisch: **Key Derivation Function**, oder **KDF**) wie etwa eine [[Kryptografische Hashfunktionen|Hashfunktion]] (symmetrisch), andererseits ein [[Diffie-Hellman Key Exchange]] (asymmetrisch).

Die ursprüngliche Namensgebung (Axolotl-Protokoll u.Ä.) stammt daher, dass man mit dem Protokoll eine OTR-Implementierung mit [[Perfect Forward Secrecy]] erschaffen wollte, die durch den häufigen Wechsel der **Session-Keys** zur "Selbstheilung" in der Lage war – eben wie der namensgebende **Querzahnmolch** (bzw. Olm -- merken: wird spaeter wichtig!), der sich somehow Gliedmassen nachwachsen lassen kann. Leider dann spaeter umbenannt.

