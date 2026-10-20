---
typ: kind
familie: ["[[Hannes Haidacher]]", "[[Evelyn Haidacher]]"]
im_spiel: false
---
# Max

> Der Neue von der Warteliste. Kommt mitten im Lauf und sagt jedem, dass das Klettergerüst seinem Papa gehört.

## Eckdaten

- **Alter:** 4, geboren am 19. Februar 2022.
- **Wohnen:** die renovierte Villa im Saggen. Vorher das Hotel im Zillertal, wo immer wer da war, der ihm was gebracht hat.
- **Herkunft:** Zillertal.
- **Allergien:** keine.
- **Ab wann:** Tag 11, Montag 28. September. Seine Aufnahme auf den Notfallplatz (#157).
- **Stimme:** Zillertaler Dialekt, laut, direkt. „Mei Papa hat's Klettergerüst kauft, damit i einidarf."

## Kanon

- Noch nicht im Spiel. Quelle: [[Besetzung]], [[Der zwölfte Platz]].

## Oberfläche

- Kommt, wenn alle anderen sich schon kennen. Am ersten Tag weint er nicht, er schaut.
- Will sofort aufs Klettergerüst, weil es „seins" ist.
- Sagt zu Lo „Bringst ma a Wasser?", so wie im Hotel zum Personal.
- Hat jeden Tag was Neues mit: einen Traktor, eine Taschenlampe, ein Pickerlbuch.

## Entdeckbar

- **Das Klettergerüst:** „Mei Papa hat's Klettergerüst kauft, damit i einidarf." Sagt er gleich am ersten Tag, jedem.
- **Das Kuvert:** bei höherem Vertrauen: „Und d'Mama hat der Jassi-Mama a Kuvert brocht." Er war mit an der Tür. Dass das was bedeutet, weiß er nicht. (Vorschlag)
- **Der Sitz:** „Die Mama kimmt nächstes Jahr in den Council." Hat er beim Abendessen gehört. (Vorschlag)

## Verborgen

- Im Hotel war er nie allein, aber selten mit seinen Eltern. Im Kindergarten muss er zum ersten Mal teilen, was er für seins hält.
- Er weiß nicht, was ein Platz ist und was er gekostet hat. Für ihn hat der Papa einfach ein Klettergerüst gekauft.

## Motive

- **Will:** ganz oben auf dem Klettergerüst sein. Einen Freund.
- **Fürchtet:** dass ihm wer was wegnimmt.
- **Würde nie:** zugeben, dass er sich am ersten Tag nicht ausgekannt hat.

## Beziehungen

- [[Hannes Haidacher]]: Papa. Ist oft im Tal. Wenn er da ist, gibt's was.
- [[Evelyn Haidacher]]: Mama. Holt ihn immer zu früh ab.
- [[Felix]]: Streit ums Klettergerüst. Max sagt, es gehört ihm, weil es sein Papa gekauft hat. Felix sagt, es gehört der Bergrettung. Am Ende spielen sie trotzdem zusammen Bergung. Freunde, beidseitig (#155).
- [[Jonas]]: Max mag ihn, einseitig (#155).
- [[Jassi]]: kennt er vom Kuvert, sie ihn vom Fenster. Sonst nix.
- [[Valentina]]: Er sagt, das Klettergerüst gehört seinem Papa. Sie sagt: „Kauft hast es du. Obn bin i." Und klettert höher. Er mault. Entschieden (#165): Sie streitet nicht, sie klettert höher, und im Spiel hört man ihren Satz nur aus Max' Mund, auf `wetter`.

## Intrigen

- [[Der zwölfte Platz]]: **weiß** „Papa hat's Klettergerüst kauft" und das Kuvert. **Verbirgt** nichts. **Will** klettern.
- [[Der versprochene Sitz]]: hat beim Abendessen gehört, dass die Mama „nächstes Jahr" in den Council kommt. Erzählt es weiter.

## Kid-Profile (entschieden, #165)

Gegrillt mit dem Entwickler am 2026-10-20. Das Profil ist `placeholder: true`; jede Zeile ist ein Entwurf für den Durchgang des Entwicklers. Die Fäden aus *Entdeckbar* kommen über Facts, `reveals` und zwei Anvertrauen hinein; *Verborgen* bleibt draußen.

**Die Leitregel:** Max verbirgt nichts ([[Der zwölfte Platz]], Wer weiß was). Was herauskommt, entscheidet also das Thema, nach dem Lo fragt. Vertrauen hält zwei Zeilen zurück: das Kuvert, weil es das Explosivste ist und im Spiel keinen anderen Weg hat, und den ersten Tag, weil er das Einzige ist, was er wirklich nie zugeben würde (Motive), wie Felix' zweite Sprosse. Max fängt an Tag 11 bei Vertrauen 6 an; kümmert sich Lo jeden Tag ganz um ihn, erreicht er `confideThreshold` (12) um Tag 13 oder 14, mit nur einem Talk am Tag um Tag 23.

- **name:** Max
- **Stimme:** Zillertaler Dialekt, laut, direkt, mit „is" statt „isch" („i", „mei", „nit", „kimmt", „einidarf"), wie die Sprachproben oben. So hört man das Zillertal gegen Innsbruck. Ob „is" passt, entscheidet der Durchgang des Entwicklers. Summary und Facts hochdeutsch, wie bei den Kanon-Kindern.
- **summary:** „Max ist neu und kam, als sich die anderen schon alle kannten. Er weint nicht, er schaut. Das Klettergerüst nennt er ‚meins', und zu Lo sagt er: ‚Bringst ma a Wasser?' Jeden Tag hat er etwas Neues mit: einen Traktor, eine Taschenlampe, ein Pickerlbuch."
  - Nur *Oberfläche*. Das Hotel fehlt mit Absicht, und das Summary erklärt nicht, warum er Lo wie Personal anspricht.
- **refusal:** Max dreht dir den Rücken zu. „I red heut nit mit dir. Du host nix zum Hergeben."
  - Passt zu Hannes' *Entdeckbar*: Im Tal legt hin, wer was will.
- **Facts:**
  - `birthday`: „Hat am 19. Februar Geburtstag." Von nichts aufgedeckt, wie bei jedem Kanon-Kind.
  - `hotel`: „Sein Papa hat ein Hotel im Zillertal. Dort hat Max bis zum Frühjahr gewohnt."
  - `klettergeruest`: „Sagt, sein Papa hat das Klettergerüst gekauft, damit er in den Kindergarten darf."
  - `sitz`: „Sagt, seine Mama kommt nächstes Jahr in den Council. Die Jassi-Mama hat es versprochen."
  - `kuvert`: „Sagt, seine Mama hat der Jassi-Mama ein Kuvert gebracht. Er war dabei."
  - `haken`: „Hat am ersten Tag seinen Haken an der Garderobe nicht gefunden und niemanden gefragt."
  - Was er erzählt, steht als „Sagt, …", wie bei Felix und Hannah: Die Notizen halten fest, was er gesagt hat, nicht, was es heißt.
- **Eigenes Topic:** `hotel`, „Papas Hotel", freigeschaltet über `hotel`. Parallel zu Hannahs „Papas Bank": Bei Max gehört alles dem Papa. Neben Matteos „Die Hotelküche" liest man den Klassenunterschied, ohne dass es wer erklärt. Das Hotel bekommt keinen Namen.
- **Eigene Activity:** `gipfel`, „Wer zuerst oben ist", aufs Klettergerüst um die Wette, freigeschaltet über `klettergeruest`.
- **Reaktionen:**

| Topic | Taste | Zeile | reveals |
|---|---|---|---|
| `wetter` | likes | „Wenn d'Sunn scheint, geh i aufs Klettergerüst. Des is meins! Mei Papa hat's kauft, damit i einidarf." Max verschränkt die Arme. „Der Felix sagt, des ghört der Bergrettung. Und d'Valentina sagt: ‚Kauft hast es du. Obn bin i.'" | `klettergeruest` |
| ↳ Anvertrauen | indifferent | „Des Klettergerüst hat mei Papa kauft. Und d'Mama hat der Jassi-Mama a Kuvert brocht, a ganz a dicks. I war dabei, an der Tür." Max zeigt mit den Händen, wie dick. „Die Jassi war am Fenster." | `kuvert` |
| `tiere` | indifferent | „Tiere? I hab heut an Traktor mit. Mit Anhänger! Den derf nur der Jonas angreifen." | — |
| `essen` | likes | „Beim Abendessen hat d'Mama gsagt, nächstes Jahr kimmt sie in den Council. Des hat ihr d'Jassi-Mama versprochen." Max nickt wichtig. „Dann gibt's a Fest. Mit Buffet, wie im Hotel." | `sitz` |
| `wochenende` | likes | „Am Wochenende fahr ma ins Tal, ins Hotel vom Papa. Do bringt ma jeder was, wenn i will. A Wasser, an Kakao, alles." | `hotel` |
| `monster` | dislikes | „Monster nehmen oam Sachen weg." Max steckt die Hand in die Hosentasche. „Drum nimm i mein Traktor mit ins Bett." | — |
| `hotel` | likes | „Im Hotel vom Papa gibt's an Pool. Drinnen! Und an Koch, der macht ma Pommes, wann i will." Max schaut zur Küche. „Do herin muss ma warten, bis Mittag is." | — |
| ↳ Anvertrauen | indifferent | „Im Hotel hat jede Tür a Nummer. Do herin san lauter Bildln." Max schaut auf seine Schuhe. „Am ersten Tag hab i mein Hakn nit gfunden. Gfragt hab i koan. Des braucht neamd wissen." | `haken` |

  - **Die Klettergerüst-Kette:** `wetter` deckt `klettergeruest` auf, ohne Hürde (*Entdeckbar*: er sagt es am ersten Tag jedem), und schaltet `gipfel` frei. Ab `confideThreshold`, wenn Lo `klettergeruest` kennt, kommt auf `wetter` das Kuvert. Die Spenderplakette am Gerüst (fr-051, eine Bemerkung) sagt schon „Gespendet von Familie Haidacher"; erst „damit i einidarf" macht aus der Spende einen gekauften Platz.
  - **Das Kuvert** steht für sich, weil es statt der gewöhnlichen Zeile kommt. „Die Jassi war am Fenster": Er kennt sie vom Kuvert, sie ihn vom Fenster (Beziehungen).
  - **Der Sitz** ist ein gewöhnliches Reveal auf `essen` („beim Abendessen gehört"), ohne Hürde. Es ist die Mama, nicht der Papa: Evelyn will den Sitz, Hannes will ihn nur für sie. Die Zeile nennt die Jassi-Mama, wie Hannahs (#163) und Idas, damit Lo aus drei Kindern auf dieselbe Frau kommt.
  - **Die Hotel-Kette:** `wochenende` deckt `hotel` auf („Ist oft im Tal. Wenn er da ist, gibt's was.") und schaltet „Papas Hotel" frei. Die gewöhnliche `hotel`-Zeile deckt nichts auf, also zählt für das Anvertrauen dort nur das Vertrauen, wie bei Felix' `bergrettung`.
  - **Der Haken** macht das Motiv konkret. An Tag 11 steht er an seinem Haken (#157), an Tag 1 hat ihn Hannes gebracht (Hannes, *Oberfläche*). Das Klo hat schon die Klo-Zeile.
  - **`monster`** zeigt seine Angst, dass ihm wer was wegnimmt (Motive), ohne sie zu erklären. **`tiere`**: Er mag Jonas, einseitig (#155); der Traktor ist eines seiner täglichen Mitbringsel.
  - **Wen er nennt:** Felix, Valentina, Jonas und die Jassi-Mama; alle sind ab Tag 1 da. Valentina „streitet" nicht, sie klettert höher, und man hört sie nur aus Max' Mund ([[Valentina]], #164). Felix' Höhe nennt er nie, sonst wäre dessen Anvertrauen `zweite_sprosse` entwertet. Kein anderes Kind nennt Max: Vor Tag 11 gibt es ihn im Spiel nicht.
  - Geschmack: drei likes, ein indifferent, ein dislikes bei den generischen Topics; `hotel` likes; beide Anvertrauen indifferent.
- **`loo.storm_in.max`:** „Is des Klo a für Gäst?" Max bleibt in der Tür stehen und wartet auf eine Antwort. (Platzhalter)
- **restrictions:** keine. Allergien keine (Eckdaten), keine Familienregel in der Lore.
- **Parent-Zeile:** `frau_haidacher`, „Frau Haidacher", Kind `max`, Sway 0,5, kein Patron (#156). Evelyn holt ihn ab, immer zu früh; bei Pixner und Plattner bekam die Zeile auch, wer abholt. Kein Titel. Die Zeile gibt es ab Tag 1; bis zur Aufnahme sieht sie nichts (#157).
- **Aufgabe:** `max_eingewoehnung`, Kind `max`, `announcedOn` 11, `dueOn` 13 (Mi 30.9.), `with_kid:max`, nach dem Vorbild von `leni_eingewoehnung`. Sie wird im selben Morgenbericht angekündigt wie die Aufnahme. Versäumt verliert Max 1,5 Vertrauen, und Frau Haidacher sieht es. Die Zahlen darf die Balance (#166) verschieben.
  - `task.max_eingewoehnung`: „Der Council of Parents® legt Wert darauf, dass sich Max rasch eingewöhnt: Er soll bis zum Stichtag einmal ganz für sich allein drankommen. Die Familie Haidacher hat sich um den Kindergarten sehr verdient gemacht."
  - `bericht.task.missed.max_eingewoehnung`: „Um {0} hat sich in seinen ersten Tagen niemand eigens gekümmert."
  - Der letzte Satz der Aufgabe zeigt, dass der Vorstand vor den Zahlern buckelt, ohne Spende oder Platz beim Namen zu nennen. Eine Patron-Aufgabe für Susanne geht nicht: `with_kid:max` in einer Patron-Aufgabe ist ein Ladefehler (#157).
- **Aus #155 und #157, unverändert:** Roster-Zeile `{ "id": "max", "admittedOn": 11 }`; `morgenbericht.aufnahme.max` wie in *Aufnahme* unten; likedPlaces klettergeruest, sandkiste, rutsche, lego; likedKids felix beidseitig, jonas einseitig; Sitz `tisch_12` zur Jause und zum Mittagessen; groupActivityDislikes `crafts`; mit Valentina nicht befreundet.
- **Platzhalter:** `placeholder: true` am Profil, keine Endung „(Platzhalter)" an den Profilzeilen; die Klo-Zeile endet darauf wie die der Kanon-Kinder. Die Parent-Zeile hat kein Flag.
- **Nicht im Profil:** sein *Verborgen* (im Hotel nie allein, selten bei den Eltern; dass er nicht weiß, was ein Platz ist); was er jeden Tag Neues mitbringt, über das Summary und den Traktor hinaus (offen auf der Map, #158); dass er mit Felix am Ende Bergung spielt (steckt in der Freundschaft, #155).

## Aufnahme (#157)

Entschieden mit dem Entwickler am 2026-10-20. Die Regel gilt für jedes Kind; Max ist das einzige, das sie braucht.

- **Config:** Seine Roster-Zeile ist `{ "id": "max", "admittedOn": 11 }`. Alle anderen werden an Tag 1 aufgenommen.
- **Vor Tag 11 ist er nirgends.** Er hat keine Notizbuch-Seite, keine Zeile bei der Abholung, keine Beschäftigung, keine Incidents, kein Petzen. Er steht nicht in der Essensausgabe-Schlange, zählt für keine Vorschrift und macht bei keiner Gruppenaktivität mit. Beim Storm-in kommt er nicht vor. `tisch_12` bleibt leer, und er zieht nichts aus dem Zufall: Die Tage 1–10 laufen wie ohne ihn.
- **Der Morgenbericht an Tag 11** kündigt ihn an, einmal, und die Zeile bleibt in den Notizbuch-Berichten. Entwurf (`morgenbericht.aufnahme.max`, Platzhalter): „Der Council of Parents®: Ab heute besucht Max den Notfallplatz Ihrer Gruppe." Der Notfallplatz ist für den dringendsten Fall gedacht. Dass er an die Familie geht, die bezahlt hat, erklärt die Zeile nicht; das versteht, wer später „Mei Papa hat's Klettergerüst kauft" hört.
- **Vertrauen:** Er startet am Tag 11 mit dem Startwert wie jedes Kind an Tag 1, also „ist zurückhaltend". Der tägliche Verlust beginnt am Abend seines ersten Tages. Das passt zu „Am ersten Tag weint er nicht, er schaut."
- **In der Szene:**
  - Er steht bei der Tageseröffnung an der Garderobe, bei seinem Haken, und läuft von dort in die Bringzeit.
  - Sein Garderobenzeichen klebt ab Tag 1 über dem Haken, weil der Platz seit Juli vergeben ist. Jacke und Hausschuhe hängen erst ab Tag 11 dort (#171).
  - An den Tagen 1–10 sieht Lo also einen zwölften Haken und einen zwölften Stuhl, zu denen kein Kind gehört.
- **Die Haidacher-Zeile** (#156, Sway 0.5) gibt es ab Tag 1. Bis zur Aufnahme sieht sie nichts und zählt nichts.
- **Aufgabe:** #157 verlangt keine. Ob es eine Eingewöhnungsaufgabe für Max gibt, wie die von Leni, entscheidet #165.
  - **Entschieden (#165):** ja, `max_eingewoehnung`, Tage 11–13; siehe *Kid-Profile* oben.

## Figur (geplant, #158)

Entschieden mit dem Entwickler am 2026-10-20 (Figuren-Matrix). Gebaut wird aus `kinder.py` und dem Bauplan; der Konzept-Frame ist nur ein Leitbild für den Charakter.

- **Steckbrief:** Blond, eine hoch aufgestellte Tolle. Keine Brille. Gelber Pulli, darüber eine dunkelblaue Steppweste, schwarze Hose. Hervorstechend: Tolle und Weste.
- **Parameter:** `haare` tolle (kräftiger als bisher: steht hoch und nach vorn), `merkmal` keins, `accessoire` steppweste (neu, eigener Slot Marine), `haut` HautHell, `haar` HaarBlond, Pulli ChairYolk, Hose InkBlack, `asymmetrie` rechts. Gesicht: schaut (`make_face`: seed 29, eyes 0.21, eye_size 0.055, brows −2, mouth 0.10, smile 0.1, blush 0.8).
- **Warum:** Die Mama ist „Immer perfekt angezogen" (Evelyn Haidacher, Oberfläche). Der Papa sagt über die Villa „alles neu, was alt aussehen soll" (Hannes Haidacher, Eckdaten). Max selbst, Oberfläche: „Am ersten Tag weint er nicht, er schaut." Was er jeden Tag Neues mitbringt, kann eine starre Figur nicht zeigen.
- **Konzept-Frame:** FLUX `fr158_max_seed15802`.

## Offene Fragen

- **(geteilt, entschieden)** Felix und Max streiten ums Klettergerüst und spielen am Ende trotzdem zusammen. Passt das zu Felix' Dossier? Dort steht der Streit schon als Vorschlag. Ja (#155, #165): Sie sind Freunde, beidseitig, und den Streit hört man nur aus Max' `wetter`-Zeile („Der Felix sagt, des ghört der Bergrettung."). Felix nennt Max nie (#159).
- ~~Wann kommt Max genau?~~ Entschieden: Tag 11, Montag 28. September (#157).
