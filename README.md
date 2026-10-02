# Praxisseite Dr. med. univ. Oana-Raluca Despa

Entwurfsstand 30.09.2026. Basis ist die Farbpalette Mint und Himmelblau (vormals
Farbvariante A). Die übrigen Farbvarianten sind entfallen und stecken in der Git-Historie.
Zur Auswahl stehen acht **Gestaltungsvarianten** derselben Seite in zwei Gruppen:
A bis D unterscheiden sich in Flächen und Anordnung, E bis H zusätzlich in Schrift,
Schriftgrößen, Rhythmus, Navigation, Leistungsdarstellung und Abschnittstrennung.

## Aufbau

```
index.html              Übersicht, alle acht Varianten in zwei Gruppen
seite/stil-a.html       Bänder            (vollflächige Farbwechsel)
seite/stil-b.html       Versetzt          (editoriales Raster, keine Karten)
seite/stil-c.html       Organisch         (weiche Formen, runde Kanten)
seite/stil-d.html       Raster und Kante  (farbige Streifen, Akzentkanten)
seite/stil-e.html       Editorial         (Serif, Haarlinien, Kapitälchen, nummerierte Liste)
seite/stil-f.html       Statement         (Condensed-Versalien, Farbflächen, große Ziffern)
seite/stil-g.html       Reduziert         (kleine Grotesk, nur Haarlinien, Definitionsliste)
seite/stil-h.html       Organisch         (weiche Serif, Verläufe, versetztes Kachelraster)
seite/bilder/           aufbereitete Fotos (JPEG und WebP, je 750 und 1500 px breit)
seite/impressum.html    Platzhalterseite
seite/datenschutz.html  Platzhalterseite
```

Die acht Varianten sind im HTML **zeichengleich identisch** bis auf die Variantenbezeichnung
in der oberen Leiste, das Portrait unter „Über mich“ und, bei E bis H, den Google-Fonts-Link im Kopf. Inhalt,
Abschnittsreihenfolge, Navigationspunkte, Formular und Farbpalette sind überall dieselben.
Unterschiedlich ist ausschließlich ein angehängter Stilblock im Stylesheet. Bei E bis H ist
dieser Block deutlich größer, weil er auch Schrift, Größen und Abstände neu setzt.

| Variante | Schrift | Navigation | Leistungen | Abschnittstrennung |
|---|---|---|---|---|
| E Editorial | Newsreader + Source Sans 3 | Zeitschriftenkopf, zentriert, nicht mitlaufend | nummerierte Liste mit Linien | Haarlinie am Abschnittskopf, Label in der Randspalte |
| F Statement | Barlow Condensed + Barlow | vollflächig grün, Versalien | breite Zeilen mit großer Nummer | Farbwechsel Grün, Weiß, Mint, Dunkel, Himmelblau |
| G Reduziert | IBM Plex Sans | schlichte Textzeile, Kontakt als Textlink | zweispaltige Definitionsliste | Haarlinie über die volle Breite, nummerierte Labels |
| H Organisch | Fraunces + Nunito Sans | offene Kopfzeile, Links in getönter Kapsel | unterschiedlich große Kacheln, versetzt | weiche Farbwaschungen ohne Kante |

Das Grundstylesheet (bis zum Block `GESTALTUNGSVARIANTE`) ist in allen acht Dateien
identisch. E bis H wurden aus `stil-a.html` erzeugt, indem nur Titel, Fontlink,
Variantenbezeichnung und Stilblock ersetzt wurden. Hover-Bewegungen der Buttons sind in
E bis H abgeschaltet.

## Farben und Stil wechseln

Jede Seite enthält zwei klar abgegrenzte Blöcke im `<style>`-Tag:

1. `FARBPALETTE` mit allen Farbwerten. In allen acht Varianten identisch. Außerhalb davon
   steht kein einziger Farbwert im Stylesheet.
2. `GESTALTUNGSVARIANTE` am Ende. Nur dieser Block unterscheidet die Varianten und
   überschreibt Layout, Kartenstil, Typografie und Abschnittsflächen.

Für die finale Seite wird der Stilblock der gewählten Variante behalten und die anderen
Dateien entfallen.

Die Palette ist gegen WCAG AA geprüft, einschließlich der neuen Farbflächen: weiße Schrift
auf dem Petrolband erreicht 5,5:1, der helle Ton darauf 4,7:1, Akzenttext auf dem Mintband
4,7:1. Der Akzent kommt in zwei Abstufungen vor: `--akzent` ist rein dekorativ,
`--akzent-tief` trägt Text.

## Das Zitat im Ablauf

In A bis D in Cormorant Garamond kursiv als Kontrast zur Plus Jakarta Sans,
jeweils anders gefasst: A über einer kräftigen Linie, B mit hängendem Anführungszeichen,
C zentriert in einer weichen Fläche, D hinter einer Akzentkante.

In E bis H in der Schrift der jeweiligen Variante: E als Pull-Quote in Newsreader kursiv
zwischen zwei Linien, F riesig in Barlow Condensed kursiv über die volle Breite auf dunklem
Grund, G klein und zentriert in Plex Sans kursiv mit viel Abstand, H in Fraunces kursiv auf
einer getönten Verlaufsfläche.

## Fotos

Kopfbereich in allen acht Varianten: IMG_1290 und IMG_1320 (beide Hochformat) nebeneinander,
auch mobil als zwei schmale Spalten. Zweimal 3:4 ergibt genau das 3:2 der früheren
Bildfläche; wo eine Variante die Fläche breiter setzt (E 21:9, F 2:1, G 16:7) oder schmaler
(H 4:5), wird per `object-position` beschnitten. In H tragen beide Fotos einen Bogen wie
ein Altbaufenster.

Portrait unter „Über mich“, je Variante ein anderes, damit die Kundin vergleichen kann:

| A | B | C | D | E | F | G | H |
|---|---|---|---|---|---|---|---|
| 1229 | 1151 | 1123 | 1241 | 1149 | 1248 | 1114 | 1132 |

Bei 1149 und 1151 steht das Gesicht im Original zu tief; beide sind enger auf 3:4
zugeschnitten, damit es im oberen Drittel liegt.

Aufbereitung: von Display P3 nach sRGB gewandelt, lange Seite 2000 px (plus 1000 px für
`srcset`), JPEG und WebP, alle Dateien unter 400 KB, sämtliche Metadaten einschließlich EXIF
und GPS entfernt. Die Originale in `Fotos/` sind per `.gitignore` ausgeschlossen, weil sie
groß sind und Standortdaten enthalten. Alle Bilder außer den beiden im Kopfbereich laden
mit `loading="lazy"`.

Die übrigen ausgewählten Praxisfotos (1300, 1303, 1316) sind nicht eingebaut, weil keine
Variante eine weitere Bildfläche hat.

## Kontaktbereich

Formular und Kontaktangaben liegen in einem gemeinsamen Abschnitt mit der ID `#kontakt`.
Ab 900 px zweispaltig: links die Kontaktangaben samt Anfahrt, rechts das Formular.
Darunter einspaltig in derselben Reihenfolge. Einen separaten
Terminabschnitt gibt es nicht mehr; in der Kopfzeile führt nur noch der hervorgehobene
Button auf `#kontakt`.

Statt einer eingebetteten Karte steht unter der Adresse ein Textlink „In Google Maps
öffnen", der die Adresse als Suchanfrage übergibt und in einem neuen Tab aufgeht. Kein
iframe, kein Kartendienst im Seitenaufbau, damit ohne Einwilligung keine Daten an Dritte
fließen.

Das Terminbuchungs-Widget ist entfallen. An seiner Stelle steht ein Kontaktformular mit
Name, E-Mail, Telefon und Nachricht.

**Keine Auswahlfelder** zu Behandlungen, Beschwerden oder Diagnosen. Gesundheitsdaten
werden also nicht strukturiert erhoben, können aber im Freitextfeld „Nachricht" stehen.

**Pflicht-Einwilligung:** Vor dem Absende-Button steht eine Checkbox, die ausdrücklich
auch Gesundheitsdaten einschließt und auf die Datenschutzerklärung verlinkt. Ohne Haken
lässt sich das Formular nicht absenden.

Daraus folgen Pflichten, die vor dem Livegang erfüllt sein müssen:

- Die Einwilligung muss **dokumentiert** werden (Wortlaut, Zeitpunkt), Art. 7 Abs. 1 DSGVO.
- Der **Widerruf** muss praktisch möglich sein und so einfach wie die Erteilung.
- Die **Übertragung muss verschlüsselt** erfolgen. Ein einfacher unverschlüsselter
  Mailversand an ein web.de-Postfach ist für Gesundheitsdaten nicht ausreichend.
- **Löschfristen** und Empfänger gehören in die Datenschutzerklärung.

**Spamschutz:** Ein Honeypot-Feld, das per CSS aus dem sichtbaren Bereich geschoben wird,
`tabindex="-1"` und `autocomplete="off"` trägt und mit `aria-hidden` aus der
Sprachausgabe genommen ist. Ist es beim Absenden ausgefüllt, wird die Anfrage verworfen.
Die Bestätigung erscheint trotzdem, damit ein Bot nicht erkennt, dass er aufgefallen ist.
Kein reCAPTCHA, keine externen Dienste. Die Prüfung muss später zusätzlich serverseitig
erfolgen, weil clientseitiges JavaScript umgangen werden kann.

Pflichtfelder sind Name, E-Mail, Telefon, Nachricht und die Einwilligung. Die Validierung läuft ohne Framework, zeigt
Fehler direkt am Feld, setzt `aria-invalid`, springt zum ersten fehlerhaften Feld und
räumt die Meldung wieder ab, sobald die Eingabe stimmt. Nach erfolgreichem Absenden
erscheint eine Bestätigung, die den Fokus erhält.

**Offen:** Das Formular versendet noch nichts. Vor dem Livegang muss ein Versandweg
eingerichtet (Mail-Endpunkt oder Formulardienst mit Auftragsverarbeitungsvertrag) und in
der Datenschutzerklärung beschrieben werden. Der Entwurf weist in der Bestätigung darauf hin.

## Platzhalter für Kontaktdaten

Die E-Mail-Adresse `privatpraxis-despa@web.de` ist eingesetzt und überall als
`mailto:`-Link ausgeführt: im Kontaktbereich, im Footer und im Impressum.

Die Telefonnummer ist weiterhin Platzhalter:

```
grep -rn "\[TELEFON\]" seite/
```

## Rechtliche Hinweise

### Zu prüfen: „Botox-Behandlung"

Botox ist der Markenname eines verschreibungspflichtigen Arzneimittels. Publikumswerbung
dafür ist nach **§ 10 Abs. 1 HWG** unzulässig; die Nennung als Leistung auf einer
Praxiswebsite ist ein bekanntes Abmahnrisiko. Die Leistung steht so in den Entwürfen, weil
sie so im Text der Kundin stand. Vor Veröffentlichung anwaltlich prüfen lassen.

### Weitere Formulierungen zur Abstimmung

Wörtlich aus ihrem Text, nicht offensichtlich unzulässig, aber als anpreisend im Sinne von
§ 27 MBO-Ä diskutabel:

- „an der **renommierten** Medizin-Universität Wien"
- „Venenbehandlungen **nach dem neuesten Standard**"
- „Realisierung einer **optimalen**, individuell angepassten phlebologischen Patiententherapie"

### Bewusst nicht enthalten

- Keine Vorher-Nachher-Darstellungen, auch nicht als Bildplatzhalter (§ 11 Abs. 1 Nr. 5 HWG)
- Keine Heilversprechen, keine Erfolgs- oder Zufriedenheitsgarantien
- Keine Patientenbewertungen oder Testimonials
- Keine erfundenen Angaben. Alles, was nicht aus ihrem Text stammt, steht in eckigen Klammern.

## Technischer Stand

- Je eine einzelne HTML-Datei, CSS im `<style>`-Tag, kein Framework, kein Build-Schritt.
- JavaScript nur für die Formularvalidierung, rund 50 Zeilen, ohne Abhängigkeiten.
- Externe Ressourcen: Google Fonts. A bis D: Plus Jakarta Sans, Cormorant Garamond.
  E: Newsreader, Source Sans 3. F: Barlow Condensed, Barlow. G: IBM Plex Sans.
  H: Fraunces, Nunito Sans. Vor dem Livegang lokal einbinden, damit beim Seitenaufruf keine
  Daten an Google fließen.
- Mobile-first. Überlauf geprüft bei 750, 900, 1100 und 1280 px sowie im
  Mobil-Zweig (E bis H bei 500, 900 und 1280 px); Chrome headless lässt sich nicht unter 500 px Fensterbreite zwingen.
- Semantisches HTML, Sprungmarke zum Inhalt, beschreibende `alt`-Texte an allen Fotos.
- Alle Seiten tragen `<meta name="robots" content="noindex, nofollow">`.

## Offene Punkte

- Entscheidung für eine Gestaltungsvariante
- Telefonnummer
- Ablauf eines Termins: die drei Schritte sind noch vollständig Platzhalter
- Einleitungstext für den Leistungsbereich
- Auswahl eines der acht Portraits
- Serverseitige Honeypot-Prüfung zusätzlich zur clientseitigen
- Verschlüsselter Übertragungsweg und Dokumentation der Einwilligung
- Versandweg für das Kontaktformular
- Impressum und Datenschutz juristisch befüllen
