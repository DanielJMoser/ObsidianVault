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
- **Stimme:** breites Tirolerisch, laut, direkt. „Muggen", „Bua", „isch".
  - „I kimm höher auffi als du."

## Kanon
- — noch nicht im Spiel. Quelle: [[Besetzung]].

### Kid-Profile (Vorschlag)
- **summary:** Valentina ist als Erste oben am Klettergerüst und als Letzte wieder unten. Wer ihr sagt, dass das zu hoch ist, kriegt zu hören, dass das eh nicht hoch ist.
- **facts:** `birthday` (18. Februar), `brueder` („Hat zwei große Brüder, die schon in die Schule gehen."), `werkstatt` („Darf in Papas Werkstatt die Schrauben sortieren.").
- **topic** `werkstatt` „Papas Werkstatt", unlocked by `werkstatt`.
- **likedPlaces:** klettergeruest, rutsche, schaukel, basteltisch (#155). Drinnen der Basteltisch, weil sie in Papas Werkstatt die Schrauben sortieren darf; die Sandkiste fällt weg, sie ist immer oben.
- **likedKids:** felix und hannah beidseitig; jonas einseitig, weil er sie verpetzt hat und sie ihm trotzdem nicht lange böse sein kann (#155). Mit Max nicht befreundet: Wer zuerst am Klettergerüst ist, hält den anderen fern.
- **Sitz:** `tisch_08`, neben Hannah, gegenüber Jonas (#155).
- **groupActivityDislikes:** `read_aloud` (#155).

## Oberfläche
- Immer oben: Klettergerüst, Rutschenturm, Fensterbank, wenn keiner schaut.
- Tirolerisch, laut, ohne Umweg. Sagt Erwachsenen, was sie denkt.
- Kommt im Firmenbus und darf vorne sitzen, wenn Papa holt.

## Entdeckbar
- **Gstudierte.** „Mei Papa sagt, Gstudierte kennen sich bei nix aus." Beim Talk über Arbeit oder Eltern.
- **Der Baron zahlt nicht.** „Mei Papa hat beim Herrn Baron die Heizung gmacht. Und jetzt wart ma." Bei höherem Vertrauen: „Mei Papa sagt, der Baron zahlt nia." (Vorschlag) Siehe [[Die Villa]].
- **Die Jassi-Mama.** „Die Jassi-Mama hat mein Papa einmal in den Council haben wollen. Der hat nur glacht." (Vorschlag)
- **Jonas petzt.** „Lo! Das Vogelhaus hat die Valentina kaputt gemacht." Das sagt Jonas, nicht sie. Siehe [[Jonas]].

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

## Figur (geplant, #158)

Entschieden mit dem Entwickler am 2026-10-20 (Figuren-Matrix). Gebaut wird aus `kinder.py` und dem Bauplan; der Konzept-Frame ist nur ein Leitbild für den Charakter.

- **Steckbrief:** Schwarzes Haar, ein Dutt oben auf dem Kopf. Keine Brille. Gelber Pulli, blaue Latzhose. Hervorstechend: der Dutt.
- **Parameter:** `haare` dutt (neu), `merkmal` keins, `accessoire` latzhose (neu, in der Familie der Hose, kein eigener Slot), `haut` HautMittel, `haar` HaarSchwarz, Pulli ChairYolk, Hose BookBlue, `asymmetrie` links. Gesicht: trotzig (`make_face`: seed 28, brows 10, lift −0.03, mouth 0.16, smile 0.4).
- **Warum:** Oberfläche: „Immer oben: Klettergerüst, Rutschenturm, Fensterbank, wenn keiner schaut." Der Papa trägt die Arbeitshose (Sepp Kirchmair, Oberfläche), und sie ist sein Ebenbild (Sepp Kirchmair, Beziehungen).
- **Konzept-Frame:** FLUX `fr158_valentina_seed15801`.

## Offene Fragen
- **(entschieden)** Valentina kommt auf den Roster, ab Tag 1 (Map #152); ihr Kid-Profil ist #164. Sitz und Places stehen seit #155 oben.
- **(geteilt, entschieden)** Max und das Klettergerüst: Streitet Valentina mit ihm, oder ist das nur Felix' Streit? Max' Dossier entscheidet.
