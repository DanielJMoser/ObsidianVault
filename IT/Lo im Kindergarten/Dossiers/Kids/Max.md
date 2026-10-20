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
- [[Valentina]]: Er sagt, das Klettergerüst gehört seinem Papa. Sie sagt: „Kauft hast es du. Obn bin i." Und klettert höher. Er mault. (Vorschlag)

## Intrigen

- [[Der zwölfte Platz]]: **weiß** „Papa hat's Klettergerüst kauft" und das Kuvert. **Verbirgt** nichts. **Will** klettern.
- [[Der versprochene Sitz]]: hat beim Abendessen gehört, dass die Mama „nächstes Jahr" in den Council kommt. Erzählt es weiter.

## Kid-Profile (Vorschlag)

- **birthday:** „Hat am 19. Februar Geburtstag."
- **klettergeruest:** „Sagt, das Klettergerüst gehört seinem Papa." Das schaltet das Thema frei.
- **Eigenes Thema** `hotel`, „Das Hotel": „Bei uns im Hotel gibt's an Pool. Drinnen! Und an Koch, der macht ma Pommes, wann i will."
- **Eigene Aktivität** `gipfel`, „Wer zuerst oben ist": aufs Klettergerüst um die Wette.
- **likedPlaces:** klettergeruest, sandkiste, rutsche, lego (#155). Er bringt jeden Tag etwas Neues mit, und an der Legokiste baut er dem Traktor eine Garage.
- **likedKids:** felix beidseitig, jonas einseitig (#155). Mit Valentina nicht befreundet: Ist sie oben am Klettergerüst, kommt er nicht auf „sein" Gerüst.
- **Sitz:** `tisch_12`, neben Los Stuhl. Bis zu seiner Aufnahme ist er der leere zwölfte Platz (#155, #157).
- **groupActivityDislikes:** `crafts` (#155).
- **Refusal:** „I red heut nit mit dir. Du host nix zum Hergeben."
- **Reaktion auf Essen:** „Bei uns daheim gibt's a Buffet. Do kannst nehmen, so viel du willst." (likes)
- **Storm-in:** „Is des Klo a für Gäst?"

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

## Figur (geplant, #158)

Entschieden mit dem Entwickler am 2026-10-20 (Figuren-Matrix). Gebaut wird aus `kinder.py` und dem Bauplan; der Konzept-Frame ist nur ein Leitbild für den Charakter.

- **Steckbrief:** Blond, eine hoch aufgestellte Tolle. Keine Brille. Gelber Pulli, darüber eine dunkelblaue Steppweste, schwarze Hose. Hervorstechend: Tolle und Weste.
- **Parameter:** `haare` tolle (kräftiger als bisher: steht hoch und nach vorn), `merkmal` keins, `accessoire` steppweste (neu, eigener Slot Marine), `haut` HautHell, `haar` HaarBlond, Pulli ChairYolk, Hose InkBlack, `asymmetrie` rechts. Gesicht: schaut (`make_face`: seed 29, eyes 0.21, eye_size 0.055, brows −2, mouth 0.10, smile 0.1, blush 0.8).
- **Warum:** Die Mama ist „Immer perfekt angezogen" (Evelyn Haidacher, Oberfläche). Der Papa sagt über die Villa „alles neu, was alt aussehen soll" (Hannes Haidacher, Eckdaten). Max selbst, Oberfläche: „Am ersten Tag weint er nicht, er schaut." Was er jeden Tag Neues mitbringt, kann eine starre Figur nicht zeigen.
- **Konzept-Frame:** FLUX `fr158_max_seed15802`.

## Offene Fragen

- **(geteilt, übernommen)** Felix und Max streiten ums Klettergerüst und spielen am Ende trotzdem zusammen. Passt das zu Felix' Dossier? Dort steht der Streit schon als Vorschlag.
- ~~Wann kommt Max genau?~~ Entschieden: Tag 11, Montag 28. September (#157).
