---
typ: kind
familie: ["[[Manni Plattner]]"]
im_spiel: false
---
# Hannah
> Fünf, fröhlich, an der Kasse im Kaufladen zu Hause. Sagt beim Mittagessen, was der Papa beim Abendessen gesagt hat. Wort für Wort.

## Eckdaten
- **Alter:** 5, geboren am 11. April 2021. Vorschuljahr. (Vorschlag)
- **Familie:** Manni und Sandra Plattner. Einzelkind.
- **Wohnen:** Pradl. (Vorschlag)
- **Herkunft:** Tirol.
- **Allergien:** keine.
- **Stimme:** Tirolerisch, schnell, mit Papas Sätzen dazwischen, die nicht zu einer Fünfjährigen passen.
  - „Der Papa sagt, im Council sitzen lauter Gauner. Was ist ein Gauner?"

## Kanon
- — noch nicht im Spiel. Quelle: [[Besetzung]], [[Das Loch in der Kassa]].
- **Vorschlag für ein Kid-Profil:**
  - Fact `kasse`: „Ist im Kaufladen immer die Kassiererin. Zählt das Wechselgeld zweimal."
  - Topic `bank`: „Papas Bank"
  - likedPlaces: kaufladen, maltisch, schaukel.
  - likedKids: jassi, valentina. Im Kaufladen ist sie die Kassiererin, Jassi die Köchin.
  - **Entschieden (#155):** die Places wie oben; jassi und valentina beide beidseitig; Sitz `tisch_07`, weit weg von Nici; groupActivityDislikes keine. Mit Nici nicht befreundet: Am Maltisch, den beide mögen, sperrt jede die andere aus.

## Oberfläche
- Fröhlich, redet viel, lacht laut.
- Will im Kaufladen immer die Kasse. Zählt jedes Spielgeld zweimal, „wie der Papa".
- Kommt mit Jassis Restaurant gut aus: Jassi kocht, Hannah kassiert.

## Entdeckbar
- **Papas Sätze.** Talk über Familie oder Wochenende, sonst einfach so beim Essen:
  - „Der Papa sagt, der Herr Baron hat ihm das Geld gestohlen."
  - „Der Papa sagt, im Council sitzen lauter Gauner."
  - „Die Mama sagt, der Papa soll's endlich gut sein lassen."
- Sie versteht es nicht. Sie weiß nur, dass es wichtig klingt, wenn der Papa so redet. Im Kern stimmt es trotzdem. Siehe [[Das Loch in der Kassa]].
- **Wer der Herr Baron ist,** weiß sie: „Der Papa von der Nici." (Vorschlag)

## Verborgen
- Sie wiederholt es, weil der Papa dann immer so ernst ist und es ihr wichtig vorkommt. Ein Geheimnis ist es für sie nicht.
- Dass ihre Familie einmal im Council war, weiß sie nicht.

## Motive
- **Will:** die Kasse. Dass der Papa wieder lacht beim Abendessen.
- **Fürchtet:** wenn die Eltern streiten, leise, damit sie es nicht hört.
- **Würde nie:** beim Wechselgeld schummeln.

## Beziehungen
- [[Manni Plattner]]: Papa. Sie liebt ihn und plappert ihn nach.
- Sandra: Mama. Sagt „Hannah, das sagt man nicht", und Hannah sagt es trotzdem.
- [[Jassi]]: Restaurant-Partnerin. Jassi kocht, Hannah kassiert. Freundinnen, beidseitig (#155).
- [[Valentina]]: Freundin zum Schaukeln. Beidseitig (#155).
- [[Nici]]: Der „Herr Baron" ist Nicis Papa. Hannah hat es Nici einmal gesagt, seitdem gehen sie sich aus dem Weg. (Vorschlag)

## Intrigen
- [[Das Loch in der Kassa]]: **weiß**, was der Papa sagt. **Verbirgt** nichts. **Will** nichts davon, sie ist fünf.

## Figur (geplant, #158)

Entschieden mit dem Entwickler am 2026-10-20 (Figuren-Matrix). Gebaut wird aus `kinder.py` und dem Bauplan; der Konzept-Frame ist nur ein Leitbild für den Charakter.

- **Steckbrief:** Blond, zwei kurze Schwänzchen hoch über den Ohren, kurze Fransen. Keine Brille. Himbeerfarbener Pulli, Jeans. Trägt ein rotes Geldtascherl am Riemen quer über der Brust. Hervorstechend: die abstehenden Schwänzchen.
- **Parameter:** `haare` schwaenzchen (neu), `merkmal` keins, `accessoire` taschl (neu, eigener Slot KidRed), `haut` HautHell, `haar` HaarBlond, Pulli Himbeer (neue Familie), Hose BookBlue, `asymmetrie` rechts. Gesicht: lacht (`make_face`: seed 27, eyes 0.20, brows −6, mouth 0.26, smile 1.0).
- **Warum:** Oberfläche: „Fröhlich, redet viel, lacht laut." und „Will im Kaufladen immer die Kasse. Zählt jedes Spielgeld zweimal, ‚wie der Papa'."
- **Konzept-Frame:** FLUX `fr158_hannah_seed15802`.

## Offene Fragen
- (geteilt, übernommen) Hannah hat Nici gesagt, ihr Papa sei ein Dieb, und seitdem meiden sich die beiden. Das gehört auch in Nicis Dossier.
- **(entschieden)** Hannah kommt ins Spiel, ab Tag 1 (Map #152); ihr Kid-Profil ist #163.
