---
typ: kind
familie: ["[[Monika Pixner]]"]
im_spiel: false
---
# Matteo

> Der Bub aus dem Souterrain der Gruber-Villa: Er weiß, wann der Mann mit den Pickerln kommt, und sagt es jedem, der fragt.

## Eckdaten

- **Alter:** 4, geboren am 11. Februar 2022. (Vorschlag)
- **Wohnen:** im Souterrain der Gruber-Villa. Nici wohnt über ihm, Leni noch weiter oben.
- **Herkunft:** Mama aus dem Passeier, Papa Stefano aus dem Trentino.
- **Allergien:** keine.
- **Garderobe (geplant, #171):** Zeichen Apfel, terrakottafarbene Jacke (RoofTile), terrakottafarbene Hausschuhe. Haken West 1. Südtirol ist Apfelland, aber das sagt niemand. Die Kochmütze ist Jassis Zeichen (#162).
- **Stimme:** Deutsch mit italienischen Brocken: „dai", „basta", „ecco", „Mamma mia".
  - „Ecco, schau. Der Mann mit den Pickerln war wieder da."
  - **Im Spiel (#162):** höchstens ein Brocken pro Zeile, nicht in jeder. Am liebsten ein deutsches Wort, das ihm fehlt und für das das italienische einspringt („den großen … den armadio"), sonst „ecco", „dai", „basta", „scusa". Kein „Mamma mia", das ist Klischee. Zur Mama sagt er „Mama", weil Monika mit ihm Deutsch redet. Südtiroler Wörter: Muggen, Marende.
  - **Flüche (#162):** „Dio cane!" (vom Papa aus dem Trentino) und „Putaner!" (Südtirol). Er plappert sie nach, ohne zu wissen, was sie heißen. Nur an zwei Stellen: „Dio cane" beim Topic Hotelküche, „Putaner" in der Refusal.

## Kanon

— noch nicht im Spiel. Quelle: die Besetzung.

## Oberfläche

- Kennt jedes Küchenwort, weil der Papa Koch ist.
- Spielt mit Nici, als wären sie Geschwister. Sie ist die Große.
- Erzählt gern und viel, auf Deutsch, bis ihm ein Wort fehlt. Dann auf Italienisch.
- Ist immer in der Sandkiste oder beim Kaufladen.

## Entdeckbar

- **Der Mann mit den Pickerln.** Talk Wochenende: „Heut war wieder der Mann mit den Pickerln beim Herrn Baron. Der hat auf den großen Kasten ein Pickerl gepickt." Daraus erfährt Lo vom Exekutor. (Vorschlag)
  - **Im Spiel (#162):** nicht beim Wochenende, denn der Exekutor kommt an Werktagen. Stattdessen Talk Villa, das eigene Topic, das Talk Monster freischaltet. Fact `pickerl`.
- **Das rote Auto.** „Die Frau mit dem roten Auto kommt immer am Abend zum Herrn Baron." Siehe [[Onkel Timo]]. (Vorschlag)
  - **Im Spiel (#162):** sein einziges Anvertrauen, auf Talk Villa. Fact `rotes_auto`. Er versteckt nichts. Er kommt nur erst darauf, wenn er mit Lo warm ist und länger erzählt.
- **Die Samstage.** „Der Herr vom Büro geht am Samstag immer hinauf." Siehe [[Samstage]]. (Vorschlag)
  - **Im Spiel (#162):** Talk Wochenende. Fact `samstag`. Neben Jonas' Kanon-Zeile („Am Samstag war ich bei der Leni") kann der Spieler selbst darauf kommen, wer da hinaufgeht.
- **Die Bilder.** „Bei der Nici sind die Wände jetzt leer. Die Bilder sind nach Wien gefahren." (Vorschlag)
  - **Im Spiel (#162):** nur eine Zeile, kein Fact. Talk Wetter, wenn er abschweift. Den Fact dazu hätte erst Nicis „Herbert ist ein Bild".

## Verborgen

- Er weiß nicht, was ein Exekutor ist. Er weiß nur, dass Nici traurig ist, wenn er kommt.
- Er erzählt es Nici trotzdem jedes Mal, weil sie fragt.
- Den Papa sieht er unter der Woche fast nur beim Frühstück. Am Sonntag kocht der Papa für alle, auch für Nici.

## Motive

- **Will:** einmal mit dem Papa in der großen Hotelküche stehen. In Jassis Restaurant der Koch sein.
- **Fürchtet:** dass die Nici weggeht.
- **Würde nie:** ein Geheimnis behalten, wenn jemand fragt. Er weiß gar nicht, dass es Geheimnisse sind.

## Kid-Profile (entschieden, #162)

Gegrillt mit dem Entwickler am 2026-10-20. Das Profil ist `placeholder: true`; jede Zeile ist ein Entwurf für den Durchgang des Entwicklers. Die Fäden aus *Entdeckbar* kommen über Facts, `reveals` und ein Anvertrauen hinein; *Verborgen* bleibt draußen.

- **name:** Matteo
- **summary:** „Matteo kennt jedes Küchenwort und erzählt gern und viel, auf Deutsch, bis ihm ein Wort fehlt. Dann geht es auf Italienisch weiter. Meistens steht er in der Sandkiste oder beim Kaufladen. Mit Nici spielt er, als wären sie Geschwister. Sie ist die Große."
  - Kein „weil der Papa Koch ist": keine erklärten Eigenheiten, und sonst wäre `papa_koch` ab Tag 1 verraten.
- **refusal:** „Putaner!" Matteo dreht dir den Rücken zu und erzählt den Rest der Sandkiste, auf Italienisch.
- **Facts:**
  - `birthday`: „Hat am 11. Februar Geburtstag."
  - `papa_koch`: „Sein Papa ist Koch in einem Hotel."
  - `keller`: „Wohnt ganz unten in der Villa von den Grubers, unter der Nici."
  - `pickerl`: „Sagt, beim Herrn Baron war wieder der Mann mit den Pickerln und hat ein Pickerl auf den großen Kasten gepickt."
  - `samstag`: „Sagt, der Herr vom Büro geht am Samstag immer hinauf."
  - `rotes_auto`: „Sagt, die Frau mit dem roten Auto kommt immer am Abend zum Herrn Baron ins Büro."
  - Die drei Fäden stehen als „Sagt, …", wie Miras `stueck`: Die Notizen halten fest, was er gesagt hat, nicht, was es heißt. Das Wort „Exekutor" steht nirgends.
  - Die Bilder bekommen keinen Fact.
- **Eigene Topics:**
  - `kochen`, „Die Hotelküche", freigeschaltet über `papa_koch`. Statt „Wie der Papa kocht": passt zu den Kanon-Labels und zu seinem Motiv.
  - `villa`, „Die Villa", freigeschaltet über `keller`.
- **Eigene Activity:** `sandrisotto`, „Sandrisotto kochen", freigeschaltet über `papa_koch` (wie Jassis `kochbuch` → `restaurant`).
- **Reaktionen:**

| Topic | Taste | Zeile | reveals |
|---|---|---|---|
| `wetter` | likes | „Wenn's regnet, spiel ich mit der Nici oben im Gang. Da hängen jetzt keine Bilder mehr, nur die Nägel. Die Bilder sind nach Wien gefahren." | — |
| `tiere` | dislikes | „Bei uns unten gibt's nur Muggen. Der Papa sagt zanzare, die Mama sagt Muggen, und ich sag: basta!" Matteo haut nach einer, die gar nicht da ist. | — |
| `essen` | likes | „Mein Papa kocht Risotto. Für hundert Leute! Und am Sonntag für uns." | `papa_koch` |
| `wochenende` | indifferent | „Am Samstag hab ich mit der Mama die Post geholt. Der Herr vom Büro ist wieder hinaufgegangen, ganz hinauf. Ecco, am Samstag geht der immer hinauf." | `samstag` |
| `monster` | likes | „Monster wohnen im Keller. Wir wohnen auch im Keller, und ich hab noch nie eins gesehen. Nur die Waschmaschine." | `keller` |
| `kochen` | likes | „In der Hotelküche ist der Topf so groß wie ich, sagt der Papa. Einmal darf ich mit. Und wenn beim Papa was anbrennt, sagt er: ‚Dio cane!'" Matteo schaut, ob du jetzt schimpfst. | — |
| `villa` | indifferent | „Beim Herrn Baron war wieder der Mann mit den Pickerln. Der hat ein Pickerl auf den großen … den armadio gepickt. Mir hat er keins gegeben." Matteo ist ein bisschen beleidigt. | `pickerl` |
| ↳ Anvertrauen | likes | „Weißt du was? Am Abend kommt immer die Frau mit dem roten Auto zum Herrn Baron. Ins Büro, wenn alle anderen schon heim sind. Die Mama sagt, sie sieht nie was." | `rotes_auto` |

  - **Die Kette:** `monster` → `keller` → Topic `villa` → `pickerl`; ab `confideThreshold`, wenn Lo `pickerl` kennt, das rote Auto.
  - **„Keller"** steht nur in der Monster-Zeile; bei `tiere` sagt er „unten".
  - **„Am Sonntag für uns"** bleibt: harmlose Oberfläche. Dass er den Papa unter der Woche kaum sieht, kommt in keine Zeile.
  - **„Die Mama sagt, sie sieht nie was"** zitiert Monikas Spruch („I sich nia wos"). Die Ironie liest der Spieler; ihr *Verborgen* wird nicht ausgesprochen.
  - Geschmack: vier likes, zwei indifferent, ein dislikes, dazu das Anvertrauen likes.
- **`loo.storm_in.matteo`:** „Scusa!" Matteo macht die Tür zu und gleich wieder auf. „Bist du bald fertig? Die Marende ist schon da." (Platzhalter)
- **restrictions:** keine.
- **Parent-Zeile:** `frau_pixner`, „Frau Pixner", Sway 0,5, kein Patron. Monika holt ihn ab; siehe [[Monika Pixner]].
- **likedPlaces:** sandkiste, kaufladen (#155). „garten" ist kein Place, und zwei reichen: „Ist immer in der Sandkiste oder beim Kaufladen."
- **likedKids:** nici, jassi, beide beidseitig (#155).
- **Sitz:** `tisch_06`, neben Nici (#155).
- **groupActivityDislikes:** keine (#155).
- **Platzhalter:** `placeholder: true` am Profil, keine Endung „(Platzhalter)" an den Profilzeilen; die Klo-Zeile endet darauf wie die der Kanon-Kinder.

## Beziehungen

- **[[Monika Pixner]]:** Mama. Hat alle Schlüssel.
- **Stefano:** Papa. Koch, kommt heim, wenn Matteo schläft.
- **[[Nici]]:** Fast eine Schwester. Isst oft bei ihnen unten. Freunde, beidseitig (#155).
- **[[Jassi]]:** Ihr Restaurant braucht einen Koch. Er wäre gern der Koch. Freunde, beidseitig (#155). Im Kaufladen ist nur Platz für zwei, also kommt er nur hinein, wenn Hannah nicht an der Kasse steht.
- **[[Leni]]:** Wohnt ganz oben. Er hört sie singen.
- **[[Timotheus von Gruber]]:** Der Herr Baron. Redet nie mit ihm.

## Intrigen

- **[[Die Villa]]:** **Weiß**, wann der Mann mit den Pickerln kommt. **Verbirgt** nichts. **Will**, dass Nici dableibt.
- **[[Onkel Timo]]:** **Weiß** vom roten Auto. Plaudert es aus, ohne es zu verstehen.
- **[[Samstage]]:** **Weiß**, dass der Herr vom Büro hinaufgeht. Plaudert es aus.

## Figur (geplant, #158)

Entschieden mit dem Entwickler am 2026-10-20 (Figuren-Matrix). Gebaut wird aus `kinder.py` und dem Bauplan; der Konzept-Frame ist nur ein Leitbild für den Charakter.

- **Steckbrief:** Ein Mopp aus schwarzen Locken. Keine Brille. Terrakottafarbener Pulli, Jeans. Trägt eine weiße Küchenschürze. Hervorstechend: die Locken.
- **Parameter:** `haare` locken (kräftiger als bisher: breiter als der Kopf, bis zu den Ohren), `merkmal` keins, `accessoire` schuerze (neu, eigener Slot FrameChalk), `haut` HautMittel, `haar` HaarSchwarz, Pulli RoofTile, Hose BookBlue, `asymmetrie` links. Gesicht: warm (`make_face`: seed 26, eyes 0.20, brows −2, mouth 0.20, smile 0.8, blush 1.2).
- **Warum:** Oberfläche: „Kennt jedes Küchenwort, weil der Papa Koch ist." Die Mama trägt die Arbeitsschürze (Monika Pixner, Oberfläche). Keine Kochmütze: Sie wäre ein Kostüm, und sie ist Jassis Garderobe-Zeichen.
- **Konzept-Frame:** FLUX `fr158_matteo_seed15802`. FLUX malt seine Haut dunkler als HautMittel; gebaut wird HautMittel.

## Offene Fragen

- **(geteilt, übernommen)** Ist Matteo der Koch in Jassis Restaurant? Das gehört auch in Jassis Dossier. (Vorschlag)
- ~~Sein Geburtstag ist ein Vorschlag.~~ Entschieden: 11. Februar (#162).
