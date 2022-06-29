# Eingebettete Software

-> Integraler Bestandteil eines [Technischen Systems](/home/danielm/Dokumente/ObsidianVault/IT/Embedded Systems/Technische Systeme.md). Sie ist oft 
*  **einer Einzigen Aufgabe** dediziert, 
* **auf spezielle Hardware optimiert** (damit auch darauf ausgelegt, auf deren 
  * Fehleranfälligkeiten,
  * (sensorische) Ungenauigkeiten und 
  * Besonderheiten Rücksicht zu nehmen),
* eine **Maßanfertigung**.

---------------------------------------------------------

## Besonderheiten

* Optimale Auslastung der äußerst begenzt vorhandenen Ressourcen
* Oft hardwarenahe, low-level Programmierung
  * Oft sehr schlankes oder kein OS
* Hohe Anforderungen an **Verfügbarkeit, Zuverlässigkeit und Betriebssicherheit**!
  * Reaktion in Echtzeit!
  * Menschenleben (je nach Einsatzgebiet) schnell in Gefahr!
  * Wartung oft nicht einfach möglich!

-----------------------------------------------------

## Ressourcenverbrauch

Niedrige Hardwarekosten durch **Massenproduktion**.
Es gilt:

> *Je höher die Stückzahl, desto weniger wirken sich die Entwicklungskosten auf den Stückpreis aus*.

Kosten für Hardware allerdings **direkt!**
Daher wird ein **höherer Entwicklungsaufwand** in Kauf genommen, um schlankere und hardwareoptimierte Software zu bauen.


#### Energieverbrauch

Dieser soll möglichst niedrig sein, bei Batteriebetriebenen Systemen oft im Milliwattbereich. 

"Verbrauchte" Energie wird als **Wärme** wieder abgeführt.
Hitzeableitsysteme sind bei [[Mikrocontroller#System-on-a-Chip|SoC]]s oft schwierig oder unmöglich zu realisieren. Daher oft **höhere Betriebstemperaturen** als bei anderen Computersystemen.

-----------------------------------------------------------

