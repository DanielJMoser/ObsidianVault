---
typ: kind
familie: ["[[Friederike Behrens]]", "[[Jan-Hendrik Behrens]]"]
im_spiel: false
---
# Ida

> Das Mädchen aus Hamburg, das „Mücken" sagt, jeden Tag als Letzte abgeholt wird und Lo am Abend die längsten Geschichten erzählt.

## Eckdaten

- **Alter:** 5, geboren am 30. April 2021. Vorschuljahr. (Vorschlag)
- **Wohnen:** Altbauwohnung im Saggen.
- **Herkunft:** Hamburg. Mit einem Jahr nach Innsbruck gekommen.
- **Allergien:** keine.
- **Garderobe (geplant, #171):** Zeichen Schiff, ein gelber Friesennerz mit Kapuze und Kordel (ChairYolk), gelbe Hausschuhe. Haken West 5. Der Friesennerz zeigt, dass sie nicht von hier ist, wie „Mücken" und „Tüte". Gesagt wird es nie.
- **Stimme:** Hochdeutsch, deutlich, ein bisschen erwachsen. Sagt Mücken, Tüte, lecker, Brötchen, „Tschüss".
  - „Das ist eine Tüte, keine Sackerl." Die anderen lachen.

## Kanon

- Noch nicht im Spiel. Quelle: [[Besetzung]].

## Oberfläche

- Wird jeden Tag als Letzte abgeholt, jede Woche von einer anderen jungen Frau.
- Hilft am Ende des Tages ungefragt beim Aufräumen. Weiß, wo alles hingehört.
- Erzählt gern und lang, mit vielen „und dann".
- Die anderen Kinder verbessern sie: „Des hoaßt Muggen!" Seit Kurzem sagt sie es manchmal selbst, ganz vorsichtig.

## Entdeckbar

- **Wer heute kommt.** „Diese Woche holt mich die Neue. Die heißt Lucía. Glaub ich." Im Spiel: Fact `die_neue`, über `essen` (#161).
- **Mama und Papa.** „Die Mama hat Dienst. Der Papa hat Vorlesung." Fast jeden Tag. Im Spiel: Fact `dienst`, über `wochenende` (#161).
- **Das Versprechen.** „Die Jassi-Mama hat gesagt, wir dürfen bald mitmachen. Im Council." Siehe [[Der versprochene Sitz]]. Im Spiel: Fact `versprechen`, als Anvertrauen auf `wochenende` (#161).
- **Was der Papa sagt.** „Der Papa sagt, das Council ist eine Olli… Olligarchie." Im Spiel: nur eine Zeile, auf `monster` (#161).

## Verborgen

⚠ Der eine schwere Faden der Lore. Leise und glaubwürdig gespielt, ohne Drama.

- Daheim fragt keiner, wie ihr Tag war. Es fehlt ihr an nichts außer an jemandem, der zuhört.
- Darum erzählt sie es Lo, am Abend, wenn alle anderen weg sind. Hört Lo zu, erzählt sie mehr. Hört Lo nicht zu, wird sie still.
- Am Ende einer Geschichte fragt sie oft etwas, um zu prüfen, ob noch wer zuhört: „Und was glaubst du, was dann passiert ist?"
- Ihre Zeichnungen nimmt sie mit heim. Dort bleiben sie in der Tasche.

## Motive

- **Will:** dass ihr wer zuhört. Dazugehören, wie die Eltern, nur weiß sie das nicht.
- **Fürchtet:** dass heute keiner kommt. Es ist noch nie passiert, aber einmal war die Neue eine halbe Stunde zu spät.
- **Würde nie:** sich beschweren.

## Beziehungen

- [[Friederike Behrens]]: Mama. Meistens im Dienst.
- [[Jan-Hendrik Behrens]]: Papa. Meistens in der Vorlesung.
- [[Leni]]: auch neu, auch nicht von hier. Leni sagt Gelsen, Ida sagt Mücken, die anderen sagen Muggen. Das verbindet. Freundinnen, beidseitig (#155).
- [[Leopold]]: redet so, dass sie ihn gut versteht. Hört ihm als Einzige bis zum Ende zu. Freunde, beidseitig (#155). Sie mag ihn, weil er immer etwas Interessantes zu erzählen weiß und ihr alles nett und geduldig erklärt; das kann Lo von ihr erfahren (#155, Q14). Er hält es für Interesse an Geschichte.
- [[Jassi]]: In Jassis Restaurant bestellt Ida immer „ein Brötchen". Jassi hat es auf die Karte geschrieben.
- **Die Oma in Hamburg** (Vorschlag, #161): Bei ihr war Ida zu Besuch; an Hamburg selbst kann sie sich nicht erinnern, sie kam mit einem Jahr nach Innsbruck. Die Oma faltet mit ihr Schiffe aus Zeitung. Daher kennt Ida den Hafen und die Papierschiffe.

## Intrigen

- [[Der versprochene Sitz]]: **Weiß**, dass „wir bald mitmachen dürfen". **Verbirgt** nichts. **Will**, dass die Mama dann öfter da ist. Sie glaubt, das hängt zusammen.
  - Im Spiel (#161): Beides sagt sie erst als Anvertrauen auf `wochenende`, wenn Lo lange zugehört hat. Hannah sagt es früher und als „zurück" (#163).

## Kid-Profile (entschieden, #161)

Gegrillt mit dem Entwickler am 2026-10-20. Das Profil ist `placeholder: true`; jeder Text ist ein Platzhalter für den Durchgang des Entwicklers. Die Fäden aus *Entdeckbar* kommen über Facts, `reveals` und ein Anvertrauen hinein; *Verborgen* bleibt draußen.

**Der Gedanke dahinter:** *Verborgen* sagt: „Hört Lo zu, erzählt sie mehr. Hört Lo nicht zu, wird sie still." Das tut die Mechanik schon. Talk hebt das Vertrauen, ab `confideThreshold` (12) kommt das Anvertrauen, es verblasst wieder mit dem Vertrauen, und unter `refusalThreshold` (3) kommt die Refusal. Der Faden wird gespielt, ohne dass eine Zeile ihn ausspricht.

- **name:** Ida
- **summary:** „Ida kommt aus Hamburg und sagt Mücken, Tüte und lecker. Wenn die anderen ‚Muggen!' rufen, sagt sie es seit Kurzem manchmal nach, ganz vorsichtig. Sie erzählt gern und lang, mit vielen ‚und dann', und hilft am Ende des Tages ungefragt beim Aufräumen. Abgeholt wird sie als Letzte."
  - Nur Oberfläche. Das Spiel zeigt keine Reihenfolge beim Abholen; ohne den letzten Satz fehlte diese Oberfläche ganz. Die wechselnden jungen Frauen hört Lo erst über `die_neue`.
- **refusal:** „Heute erzähl ich nichts." Ida räumt Stifte ein, einen nach dem anderen.
  - Zeigt das „wird still" als Verhalten, ohne es zu erklären.
- **Facts:**
  - `birthday`: „Hat am 30. April Geburtstag." Wird nicht verraten, wie bei allen; der Tag fällt nach den Lauf.
  - `hafen`: „War bei der Oma in Hamburg. Dort sind die Schiffe im Hafen so groß wie ein Berg." Ohne „Kommt aus Hamburg", das sagt schon die Summary.
  - `die_neue`: „Wird von ‚der Neuen' abgeholt. Jede Woche kommt eine andere."
  - `dienst`: „Sagt fast jeden Tag: ‚Die Mama hat Dienst. Der Papa hat Vorlesung.'"
  - `versprechen`: „Sagt, die Jassi-Mama hat versprochen, dass sie bald im Council mitmachen dürfen."
  - Die Olligarchie ist nur eine Zeile, kein Fact (wie Matteos Bilder, #162).
- **Eigenes Topic:** `hafen`, „Der Hafen", freigeschaltet über `hafen`.
- **Eigene Activity:** `schiffe`, „Papierschiffe falten", freigeschaltet über `hafen` (ein Fact für Topic und Activity, wie Jassis `kochbuch`). Damit gilt das Papierschiff an der Figur (#158).
- **Reaktionen:**

| Topic | Taste | Zeile | reveals |
|---|---|---|---|
| `wetter` | likes | „Bei der Oma in Hamburg regnet es von der Seite. Und dann gehen wir trotzdem zum Hafen. Die Schiffe dort sind so groß wie ein Berg. Wirklich!" | `hafen` |
| `tiere` | likes | „Leopold sagt, Mücken heißen eigentlich Culex pipiens. Und hier heißen sie Muggen." Das letzte Wort sagt Ida ganz vorsichtig. „Leopold weiß immer was Interessantes. Und dann erklärt er es mir, ganz geduldig." | `leopold`/`erklaert_gern` |
| `essen` | likes | „Diese Woche holt mich die Neue ab. Die heißt Lucía. Glaub ich. Die letzte Neue hat immer Nudeln gekocht. Lecker!" | `die_neue` |
| `wochenende` | dislikes | „Am Wochenende hatte die Mama Dienst. Und der Papa hatte Vorlesung." Mehr sagt Ida dazu nicht. | `dienst` |
| ↳ Anvertrauen | likes | „Die Jassi-Mama hat gesagt, wir dürfen bald mitmachen. Im Council. Und dann ist die Mama bestimmt öfter da." | `versprechen` |
| `monster` | indifferent | „Monster gibt es nicht. Hat der Papa erklärt. Ausführlich. Der Papa erklärt alles ausführlich. Gestern die Olli… Olligarchie. Das ist das Council." | — |
| `hafen` | likes | „Die Oma faltet Schiffe aus Zeitung. Und dann setzen wir sie aufs Wasser, und dann schwimmen sie weg. Die Oma sagt, die fahren bis nach Amerika." | — |

  - **Die Ketten:** `wetter` → `hafen` → Topic `hafen` und Activity `schiffe`. `wochenende` → `dienst`; ab `confideThreshold`, wenn Lo `dienst` kennt, das Anvertrauen mit dem Versprechen.
  - **Das Wochenende ist ihr einziges dislikes.** Sie beschwert sich nie (*Motive*). Darum zeigt es sich als Fehlen: Überall erzählt sie mit „und dann", beim Wochenende sagt sie zwei kurze Sätze und dann nichts mehr. Unter Vertrauen 12 kostet das Thema Vertrauen; darüber ist es genau das Thema, auf dem sie sich öffnet. Vorbild im Kanon: Miras `essen`.
  - **Das Anvertrauen trägt das Versprechen und die Hoffnung.** Die Hoffnung („dann ist die Mama bestimmt öfter da") steht in der Intrige unter **Will**, nicht in *Verborgen*. Das Versprechen kommt ohnehin über drei Kinder heraus; Hannah trägt es als gewöhnliches Reveal („zurück", #163), bei Ida darf es spät kommen. Wer Ida vernachlässigt, hört es von ihr nie. Gebaut wie Matteos rotes Auto (#162).
  - **Die Olligarchie auf `monster`:** Der Papa erklärt alles ausführlich, Monster wie den Council. Dass er erklärt statt zuhört, sagt keine Zeile.
  - **`tiere`** nimmt Leopolds „Auf Tirolerisch: Muggen" (#160) auf: Sie spricht nach, was er ihr erklärt hat. Das ist das eine vorsichtige „Muggen" der Oberfläche.
  - **Lucía** passt zu den Au-pairs „aus Spanien, Dänemark, Polen" ([[Friederike Behrens]]).
  - Geschmack: drei likes, ein indifferent, ein dislikes (wie Leni), dazu das Anvertrauen likes.
- **Stimme:** Hochdeutsch, höchstens ein norddeutsches Wort pro Zeile, „und dann" höchstens zwei- bis dreimal, die Zeilen weit kürzer als Leopolds Haufen. „Und was glaubst du, was dann passiert ist?" bleibt draußen (*Verborgen*).
- **`loo.storm_in.ida`:** „Oh. Tschüss!" Die Tür geht so schnell zu, wie sie aufgegangen ist. (Platzhalter)
- **restrictions:** keine.
- **Parent-Zeile:** `frau_behrens`, „Frau Dr. Behrens", Sway 0,5, kein Patron. Friederike meldet sich (Mails an Lo) und wartet am meisten auf den Sitz; „Frau Dr." trennt sie von den Council-Zeilen mit Vornamen. Siehe [[Friederike Behrens]].
- **likedPlaces:** maltisch, buecherregal, puppenecke, schaukel (#155). Puppenspiel ist Geschichtenerzählen, mit Leni als Partnerin; auf der Schaukel ist sie mit Leni. Der Kaufladen fällt weg: Mit Jassi ist sie nicht befreundet, also käme sie nie ins Restaurant, solange Jassi dort ist.
- **likedKids:** leni, leopold, beide beidseitig (#155).
- **Sitz:** `tisch_09`, gegenüber Leni, neben Leopold (#155).
- **groupActivityDislikes:** keine (#155).
- **Roster:** ab Tag 1.
- **Für den Durchgang des Entwicklers:** „das" oder „der Council"; das „Glaub ich" steht bei Ida (Lucía) und bei Leopold (`weltkrieg`-Anvertrauen); der Name Lucía.

## Figur (geplant, #158)

Entschieden mit dem Entwickler am 2026-10-20 (Figuren-Matrix). Gebaut wird aus `kinder.py` und dem Bauplan; der Konzept-Frame ist nur ein Leitbild für den Charakter.

- **Steckbrief:** Zwei lange blonde Zöpfe. Keine Brille. Weißer Pulli, dunkelblaue Hose. Hält ein gefaltetes Papierschiff. Hervorstechend: die Zöpfe.
- **Parameter:** `haare` zoepfe (kräftiger als bisher: bis auf die Schultern, etwas nach außen), `merkmal` keins, `accessoire` papierschiff (neu, eigener Slot FrameChalk), `haut` HautHell, `haar` HaarBlond, Pulli FrameChalk, Hose Marine (neue Familie), `asymmetrie` rechts. Gesicht: aufmerksam (`make_face`: seed 25, brows 0, mouth 0.13, smile 0.35).
- **Bedingung:** Das Papierschiff gilt nur, solange #161 die Aktivität `schiffe` behält; sonst `accessoire` nichts. **Erfüllt (#161):** `schiffe` bleibt.
- **Warum:** Zum Aussehen sagt das Dossier nichts. Weiß und Dunkelblau sind ein leiser Gruß an Hamburg (Eckdaten). Sie ist ordentlich angezogen; nichts an der Figur deutet ihren Faden an.
- **Konzept-Frame:** FLUX `fr158_ida_seed15801`.

## Offene Fragen
- Idas Faden ist zuerst leise. Später kann er lauter werden. Wann und wie, entscheidet die Geschichte.

- **(geteilt, entschieden, #155)** Ida und Leni als die zwei „Zugereisten": beidseitige Freundinnen, in beiden Dossiers.
- Soll Lo am Abend eine eigene Gelegenheit haben, Ida zuzuhören, etwa als Abholung, die spät kommt?
