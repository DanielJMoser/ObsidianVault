---
typ: kind
familie: ["[[Sepp Kirchmair]]"]
im_spiel: false
---
# Valentina

> Klettert höher, als sie darf, redet wie ihr Papa und hält Gstudierte für Leute, die sich bei nix auskennen.

## Eckdaten
- **Alter:** 5, geboren am 18. Februar 2021. Vorschuljahr.
- **Wohnen:** im Haus „beim Installateur", am Rand vom Saggen.
- **Familie:** Papa Sepp, Mama Martina, zwei große Brüder in der Volksschule.
- **Herkunft:** Tirol, durch und durch.
- **Allergien:** keine.
- **Garderobe (geplant, #171):** Zeichen Stern, grüne Jacke (LeafGreen), grüne Hausschuhe. Haken West 3. Grün statt des Gelbs ihres Pullis, weil sonst drei gelbe Jacken hängen würden (Leni, Ida, sie).
- **Stimme:** breites Tirolerisch, laut, direkt. „Muggen", „Bua", „isch".
  - „I kimm höher auffi als du."

## Kanon
- — noch nicht im Spiel. Quelle: [[Besetzung]]. Das Kid-Profil ist entschieden, siehe unten „Kid-Profile (entschieden, #164)".

## Oberfläche
- Immer oben: Klettergerüst, Rutschenturm, Fensterbank, wenn keiner schaut.
- Tirolerisch, laut, ohne Umweg. Sagt Erwachsenen, was sie denkt.
- Kommt im Firmenbus und darf vorne sitzen, wenn Papa holt.

## Entdeckbar
- **Gstudierte.** „Mei Papa sagt, Gstudierte kennen sich bei nix aus." Beim Talk über Arbeit oder Eltern.
  - **Im Spiel (#164):** ihre Zeile auf `wetter`, ohne Fact. Eine Haltung, kein Hebel.
- **Der Baron zahlt nicht.** „Mei Papa hat beim Herrn Baron die Heizung gmacht. Und jetzt wart ma." Bei höherem Vertrauen: „Mei Papa sagt, der Baron zahlt nia." (Vorschlag) Siehe [[Die Villa]].
  - **Im Spiel (#164):** zwei Stufen auf ihrem Thema `werkstatt`. Die gewöhnliche Zeile erzählt die Heizung (Fact `heizung`), das Anvertrauen zitiert den Papa (Fact `zahlt_nie`).
- **Die Jassi-Mama.** „Die Jassi-Mama hat mein Papa einmal in den Council haben wollen. Der hat nur glacht." (Vorschlag)
  - **Im Spiel (#164):** offen, auf `essen`, über das Grillen (Fact `council`).
- **Jonas petzt.** „Lo! Das Vogelhaus hat die Valentina kaputt gemacht." Das sagt Jonas, nicht sie. Siehe [[Jonas]].
  - **Im Spiel (#164):** Jonas' Anvertrauen auf `tiere`, es deckt ihren Fact `vogelhaus` auf. Sie selbst weicht auf `tiere` aus („A Häusl brauchen die eh koans."), und das Vogelhaus hängt schief in der Rosskastanie (fr-051).

## Verborgen
- Das kaputte Vogelhaus im Garten war sie. Sie ist draufgeklettert. Jonas hat es Lo erzählt. Sie war einen Tag lang beleidigt, länger geht es bei Jonas nicht. (Vorschlag)
- Klettern hat sie von den Brüdern. Sie will nicht die Kleine sein.
- Dass der Papa auf Geld wartet, hat sie am Küchentisch gehört. Was eine Mahnung ist, weiß sie nicht. Sie weiß nur, dass die Mama dabei laut wird.

## Motive
- **Will:** ganz oben sein. Mit den Brüdern mithalten. Einmal in Papas Bus vorne fahren, ganz allein.
- **Fürchtet:** dass man sie für zu klein hält.
- **Würde nie:** zugeben, dass etwas zu hoch ist.

## Beziehungen
- [[Sepp Kirchmair]]: Papa. Ihr Held, ihr Vorbild, ihre Sprache.
- Martina Kirchmair: Mama. Die, die Nein sagt.
- [[Jonas]]: petzt. Böse sein kann sie ihm trotzdem nicht lange. Sie mag ihn, einseitig (#155).
- [[Hannah]]: Freundin zum Schaukeln, beidseitig (#155).
- [[Max]]: kommt mitten im Herbst und sagt, das Klettergerüst gehört seinem Papa. Sie streitet nicht. Wem es gehört, ist ihr wurscht; sie klärt es, indem sie höher klettert: „Kauft hast es du. Obn bin i." Max mault, Felix bewundert sie noch mehr. (Vorschlag)
- [[Felix]]: schaut ihr beim Klettern zu, als wäre sie ein Bergretter. Verliebt, auf seine Art. Sie lässt ihn mitklettern, bis zur Hälfte. Ob sie merkt, was los ist, ist offen. Freunde, beidseitig (#155).

## Intrigen
- [[Die Villa]]: **weiß**, dass der Baron dem Papa Geld schuldet. **Verbirgt** nichts. **Will** nichts davon. Sie sagt es, weil der Papa es sagt.

## Kid-Profile (entschieden, #164)

Gegrillt mit dem Entwickler am 2026-10-20. Das Profil ist `placeholder: true`; jede Zeile ist ein Entwurf für den Durchgang des Entwicklers. *Oberfläche* und *Entdeckbar* kommen über Facts, `reveals` und ein Anvertrauen hinein; *Verborgen* bleibt draußen.

- **Die Regel:** Valentina sagt alles, was der Papa sagt, und gibt nie zu, was sie klein macht. Darum gibt es kein Geständnis-Anvertrauen wie Felix' Höhe (#159). Das Vertrauen hält nur zurück, was sie erst sagt, wenn sie mit Lo warm ist: dass der Baron nie zahlt.
- **name:** Valentina
- **Stimme:** breiter als Felix, aber auf den ersten Blick lesbar: „i", „nit", „isch", „lei", „auffi"/„obi", „koa"; höchstens ein schweres Wort pro Zeile, kurze Sätze ohne Umweg. Summary und Facts hochdeutsch, wie bei den Kanon-Kindern.
- **summary:** „Valentina ist als Erste oben am Klettergerüst und als Letzte wieder unten. Wer ihr sagt, dass das zu hoch ist, kriegt zu hören, dass das eh nicht hoch ist. Sie sagt jedem Erwachsenen, was sie denkt, laut und auf Tirolerisch, und wenn der Papa sie im Firmenbus abholt, darf sie vorne sitzen."
  - Nur *Oberfläche*.
- **refusal:** „Na. Du sagsch eh lei wieder, des isch z'hoch." Valentina verschränkt die Arme und schaut an dir vorbei, nach oben.
  - Lo ist dann die, die Nein sagt, wie die Mama (Beziehungen).
- **Facts:**
  - `birthday`: „Hat am 18. Februar Geburtstag." Von nichts aufgedeckt, wie bei jedem Kanon-Kind.
  - `brueder`: „Hat zwei große Brüder." Ohne Namen; „Schule" fällt weg, weil keine Zeile es sagt.
  - `werkstatt`: „Darf in Papas Werkstatt die Schrauben sortieren."
  - `council`: „Sagt, die Jassi-Mama wollte ihren Papa in den Council holen, und er hat nur gelacht."
  - `heizung`: „Sagt, ihr Papa hat beim Herrn Baron die Heizung gemacht, und jetzt warten sie."
  - `zahlt_nie`: „Sagt, ihr Papa sagt, der Baron zahlt nie."
  - `vogelhaus`: „Jonas sagt, sie ist aufs Vogelhaus im Garten geklettert, und jetzt ist es kaputt." Aufgedeckt von Jonas, steht aber auf ihrer Seite, wie Lenis `guinea_pig`.
  - Was sie erzählt, steht als „Sagt, …", wie Miras `stueck`: Die Notizen halten fest, was gesagt wurde, nicht, was es heißt.
- **Eigenes Topic:** `werkstatt`, „Papas Werkstatt", freigeschaltet über `werkstatt`.
- **Eigene Activity:** `installateur`, „Installateur spielen", freigeschaltet über `werkstatt` (wie Jonas' `grandpa_farm` → Topic und Activity). Keine Kletter-Activity: Max' Dossier schlägt `gipfel` vor.
- **Reaktionen:**

| Topic | Taste | Zeile | reveals |
|---|---|---|---|
| `wetter` | indifferent | „Mei Papa sagt, Gstudierte kennen sich bei nix aus. Die schauen ins Handy, ob's regnet. Mei Papa schaut aufn Berg." | — |
| `tiere` | likes | „Vögel mag i. Die san a immer ganz obn. A Häusl brauchen die eh koans." | — |
| `essen` | likes | „Am liabsten Grillwürstl. Mei Papa geht nirgends hin, lei zum Grillen. Die Jassi-Mama hat ihn amal in den Council haben wollen. Do hat er lei glacht." | `council` |
| `wochenende` | likes | „Am Samstag war i beim Papa in der Werkstatt und hab die Schrauben sortiert, nach der Größe. I woaß, wo jede hinghört." | `werkstatt` |
| `monster` | dislikes | „Monster unterm Bett? Des erzählen mir meine zwoa großen Brüder, damit i mi fürcht. I fürcht mi aber nit." Valentina verdreht die Augen. | `brueder` |
| `werkstatt` | likes | „In der Werkstatt gibt's tausend Schrauben. Mei Papa hat a beim Herrn Baron die Heizung gmacht, a ganz a große. Und jetzt wart ma." | `heizung` |
| ↳ Anvertrauen | indifferent | „Mei Papa sagt, der Baron zahlt nia." Valentina zuckt mit den Schultern. „Aber a Heizung hat er jetzt." | `zahlt_nie` |

  - **Die Kette:** `wochenende` → `werkstatt` → Topic `werkstatt` → `heizung`; ab `confideThreshold`, wenn Lo `heizung` kennt, „der Baron zahlt nia". Das ist ihr größter Hebel (siehe [[Die Villa]], „Was es kippt"), darum liegt er hinter Vertrauen, wie Matteos rotes Auto (#162).
  - **„Mei Papa sagt"** steht nur auf `wetter` und im Anvertrauen. Die Heizung erzählt sie, statt sie zu zitieren, damit sie nicht wie Hannah klingt („Der Papa sagt, der Herr Baron hat ihm das Geld gestohlen"). Wer der Baron ist, erklärt sie nicht; das tun Matteo, Felix und Hannah.
  - **`tiere`:** „A Häusl brauchen die eh koans" ist die Ausrede eines Kindes, das das Vogelhaus kaputt gemacht hat. Sie gesteht nichts, und niemand erklärt es.
  - **`essen`:** führt über Sepps Grillen (seine Oberfläche: „Geht zu keiner Sitzung und zu keinem Fest, außer zum Grillen") zum Council.
  - **`monster` dislikes:** Monster unterm Bett sind was für die Kleinen. Ihre Furcht aus den Motiven, gezeigt, nicht erklärt.
  - **Wen sie nennt:** die Jassi-Mama, keine Kinder. Max nie (vor Tag 11 gibt es ihn nicht), und Felix' Höhe nie, sonst wäre sein Anvertrauen `zweite_sprosse` entwertet.
  - Geschmack: drei likes, ein indifferent, ein dislikes bei den generischen Topics, wie Felix; `werkstatt` likes, das Anvertrauen indifferent wie Miras und Felix'.
- **Jonas' Anvertrauen** (Datenänderung an einem Kanon-Kind, siehe [[Jonas]], „Geplant (#164)"): auf `tiere`, likes, reveals `valentina/vogelhaus`: „Lo! Das Vogelhaus im Garten hat die Valentina kaputt gemacht. Die ist draufgeklettert, bis ganz oben! Ich hab nur zugeschaut. Also fast nur."
- **`loo.storm_in.valentina`:** „Do herinnen isch jo nix zum Klettern." Valentina knallt die Tür wieder zu. (Platzhalter)
- **restrictions:** keine.
- **Parent-Zeile:** `herr_kirchmair`, „Herr Kirchmair", Sway 0,5, kein Patron, kein Titel; Sepp holt sie ab (siehe [[Sepp Kirchmair]]).
- **likedPlaces:** klettergeruest, rutsche, schaukel, basteltisch (#155). Drinnen der Basteltisch, weil sie in Papas Werkstatt die Schrauben sortieren darf; die Sandkiste fällt weg, sie ist immer oben.
- **likedKids:** felix und hannah beidseitig; jonas einseitig, weil er sie verpetzt hat und sie ihm trotzdem nicht lange böse sein kann (#155). Mit Max nicht befreundet: Wer zuerst am Klettergerüst ist, hält den anderen fern.
- **Sitz:** `tisch_08`, neben Hannah, gegenüber Jonas (#155).
- **groupActivityDislikes:** `read_aloud` (#155).
- **Platzhalter:** `placeholder: true` am Profil, keine Endung „(Platzhalter)" an den Profilzeilen; die Klo-Zeile endet darauf wie die der Kanon-Kinder.
- **Nicht im Profil:** Martinas Mahnungen und die Klage (Sepps *Verborgen*); Sepps Bäder in der Pichler-Maisonette (sein *Entdeckbar*); der Streit mit Max ums Klettergerüst (gehört zu #165); „Einmal in Papas Bus vorne fahren, ganz allein" (ein Motiv); Rutschenturm und Fensterbank (die Places bleiben bei #155).

## Figur (geplant, #158)

Entschieden mit dem Entwickler am 2026-10-20 (Figuren-Matrix). Gebaut wird aus `kinder.py` und dem Bauplan; der Konzept-Frame ist nur ein Leitbild für den Charakter.

- **Steckbrief:** Schwarzes Haar, ein Dutt oben auf dem Kopf. Keine Brille. Gelber Pulli, blaue Latzhose. Hervorstechend: der Dutt.
- **Parameter:** `haare` dutt (neu), `merkmal` keins, `accessoire` latzhose (neu, in der Familie der Hose, kein eigener Slot), `haut` HautMittel, `haar` HaarSchwarz, Pulli ChairYolk, Hose BookBlue, `asymmetrie` links. Gesicht: trotzig (`make_face`: seed 28, brows 10, lift −0.03, mouth 0.16, smile 0.4).
- **Warum:** Oberfläche: „Immer oben: Klettergerüst, Rutschenturm, Fensterbank, wenn keiner schaut." Der Papa trägt die Arbeitshose (Sepp Kirchmair, Oberfläche), und sie ist sein Ebenbild (Sepp Kirchmair, Beziehungen).
- **Konzept-Frame:** FLUX `fr158_valentina_seed15801`.

## Offene Fragen
- **(entschieden)** Valentina kommt auf den Roster, ab Tag 1 (Map #152); ihr Kid-Profil ist #164. Sitz und Places stehen seit #155 oben.
- **(geteilt, entschieden)** Max und das Klettergerüst: Streitet Valentina mit ihm, oder ist das nur Felix' Streit? Max' Dossier entscheidet.
  - **(#164)** Keine Zeile von Valentina nennt Max. „Kauft hast es du. Obn bin i." gehört, wenn überhaupt, in Max' Profil (#165).
- **(entschieden, #164)** Das Kid-Profil, siehe oben.
