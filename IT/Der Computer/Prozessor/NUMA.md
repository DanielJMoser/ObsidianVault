## Definition

**Non-Uniform Memory Access (NUMA)** ist eine Computerarchitektur, bei der der **Zugriff auf den Speicher** für einen Prozessor von der Entfernung zwischen dem Prozessor und dem Speicher abhängt. 
NUMA wird häufig in **Multiprozessor-Systemen** eingesetzt, um die Skalierbarkeit und Performance zu verbessern, indem jeder Prozessor seine eigene lokale Speichereinheit hat und auf andere Speichereinheiten mit einer höheren Latenz zugreift.

## Prinzipien der NUMA-Architektur

#### Speicherlokalität

In einem NUMA-System hat jeder Prozessor einen **lokalen Speicher**, auf den er schneller zugreifen kann, als auf den **entfernten Speicher** anderer Prozessoren. Dieser Unterschied in der Speicherzugriffszeit führt zu einer **nicht-uniformen Speicherzugriffszeit**. Dies liegt daran, dass jener Zugriff über einen gemeinsamen [[Bus-Systeme|Bus]] oder einen **Interconnect** funktioniert. 

#### NUMA-Nodes

NUMA-Architekturen sind in **Nodes** unterteilt, wobei jeder Node eine eigene Kombination aus **Prozessor(en)** und **Speicher** darstellt. Der Zugriff auf den Speicher innerhalb des gleichen Nodes ist schneller als der Zugriff auf den Speicher eines anderen Nodes.

#### Caching und Speicherverwaltung

Moderne NUMA-Systeme nutzen **Caching-Techniken** und spezialisierte **Speicherverwaltung**, um die Effizienz zu maximieren. Dies erfolgt, indem versucht wird, Daten, die häufig von einem Prozessor verwendet werden, lokal zu halten und dadurch die Zugriffszeiten zu minimieren.

## Vorteile von NUMA

- **Erhöhte Skalierbarkeit:** NUMA ermöglicht die effiziente Skalierung von Systemen mit einer hohen Anzahl an Prozessoren.
- **Optimierter Speicherzugriff:** Durch die Lokalität des Speichers wird der Speicherzugriff optimiert, was die **Gesamtperformance** verbessert.
- **Geringere Speicherbandbreitenengpässe:** Da Prozessoren ihren eigenen lokalen Speicher haben, wird der Druck auf die **gemeinsame Speicherbandbreite** reduziert.

## Herausforderungen von NUMA

- **Komplexe Speicherverwaltung:** Die Verwaltung von Datenlokalität erfordert eine präzise Steuerung durch **Betriebssysteme** und **Anwendungen**, um sicherzustellen, dass die Vorteile von NUMA genutzt werden.
- **Ungleichmäßige Speicherzugriffszeiten:** Ungeeignete Datenlokalisierung kann zu **Performanceeinbußen** führen, wenn ein Prozessor häufig auf entfernten Speicher zugreift.

## NUMA in der Praxis

#### NUMA in Linux

In Linux-Systemen, wie etwa Arch Linux, kann der **NUMA-Support** aktiviert und konfiguriert werden. Über Werkzeuge wie `numactl` lässt sich die Speicherplatzierung steuern, um die Performance von Anwendungen zu optimieren, die auf mehreren Prozessoren ausgeführt werden.

#### NUMA in modernen Prozessoren

Viele moderne **Serverprozessoren** wie **AMD EPYC** und **Intel Xeon** unterstützen NUMA, um eine bessere Nutzung von Multithreading und parallelen Aufgaben zu ermöglichen.

## Beispielkonfiguration mit numactl

```bash
# Zeigt die NUMA-Konfiguration des Systems an
numactl --hardware

# Startet eine Anwendung und weist sie einem spezifischen NUMA-Node zu
numactl --cpunodebind=0 --membind=0 ./anwendung
```

## Zusammenfassung

**NUMA** bietet eine leistungsstarke Architektur für **multiprozessorgebundene Systeme**, indem es Prozessoren ermöglicht, auf lokalen Speicher mit geringerer Latenz zuzugreifen. Trotz der damit verbundenen Komplexität in der Speicherverwaltung kann NUMA die **Systemperformance** erheblich verbessern, insbesondere bei Anwendungen, die von **hoher [[Parallele vs. Verteilte Systeme#Parallele Systeme|Parallelität]]** profitieren.

---

