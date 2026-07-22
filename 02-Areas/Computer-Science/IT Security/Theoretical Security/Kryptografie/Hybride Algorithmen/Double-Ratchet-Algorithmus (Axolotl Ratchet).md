-> Entwickelt zur **E2EE** in Instantmessengern, urspruenglich fuer **Signal**.

Nach einem ersten Key-Exchange kuemmert sich der Algorithmus um **kurzlebige Session-keys**, die immer wieder erneuert und gewartet werden muessen. Dabei kommen zwei sog. kryptografische "Ratchets" zum Einsatz: Einerseits eine [[Schlüsselableitung]] (Englisch: **Key Derivation Function**, oder **KDF**) wie etwa eine [[Kryptografische Hashfunktionen|Hashfunktion]] (symmetrisch), andererseits ein [[Diffie-Hellman Key Exchange]] (asymmetrisch).

Die urspruengliche Namensgebung (Axolotl-Protokoll u.Ae.) stammt daher, dass man mit dem Protokoll eine OTR-Implementierung mit **Perfect Forward Secrecy** bei Kompromittierung eines der Kommunikationspartner haben wollte und 