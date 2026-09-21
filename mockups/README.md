# Startseiten-Entwürfe – Privatpraxis für Gefäßchirurgie Dr. med. univ. Oana-Raluca Despa

Drei Design-Richtungen für die Startseite, Stand 21.09.2026. Übersicht: [`../index.html`](../index.html).
Jede Datei läuft per Doppelklick im Browser, kein Build-Schritt. Einzige externe Ressource sind
Google Fonts – für Screenshots bitte kurz online sein, sonst greifen die Fallback-Schriften.

| Datei | Richtung |
|---|---|
| `variante-a.html` | Ruhe & Wärme – erdige Töne, Serifenschrift, viel Weißraum |
| `variante-b.html` | Klar & Präzise – Petrol/Türkis mit Goldakzenten, striktes Raster |
| `variante-c.html` | Weich & Modern – sanfte Verläufe, große Typografie, runde Formen |

Dazu je zwei Platzhalter-Unterseiten pro Variante: `variante-x-impressum.html` und
`variante-x-datenschutz.html`, im Footer verlinkt.

## Damit der Vergleich fair bleibt

Alle drei Entwürfe enthalten **denselben Inhalt**, dieselben sechs Leistungen und dieselben
Bildseitenverhältnisse: Hero 3:2, Portrait 4:5, Lageplan 16:9. Auch die sieben Abschnitte sind
identisch aufgebaut. Es variiert nur das Design – kein Entwurf gewinnt, weil er mehr Inhalt
oder ein größeres Bild hat.

---

## Variante A – „Ruhe & Wärme"

Warmes Off-White, Sand und ein sehr leises Salbei-Petrol statt eines lauten Akzents; Gold kommt
nur als Haarlinie vor. Die Cormorant Garamond in leichtem Schnitt und großem Grad gibt der Seite
etwas Editorial-Haftes und nimmt dem Thema die Nervosität. Die großen vertikalen Abstände und die
bewusst asymmetrische Bildplatzierung schaffen Ruhe – das passt zur „ruhigen Atmosphäre klassischer
Altbauräumlichkeiten", die Frau Dr. Despa in ihrem Text selbst beschreibt. Diese Variante bedient
den Türkis-Gold-Wunsch am leisesten; sie ist als echte Alternative gedacht, nicht als Kompromiss.

## Variante B – „Klar & Präzise"

Das ist die direkte Umsetzung der Türkis-Gold-Idee: tiefes Petrol als Vollflächen-Band, Türkis für
Linien und Verlinkungen, Gold ausschließlich als 1-px-Kante, Ziffernring und Rahmen – nie flächig,
damit es nicht ins Protzige kippt. Outfit und Inter sind zwei sachliche Grotesken, sehr gut lesbar
über das ganze Altersspektrum und auf dem Handy. Das enge Raster mit sichtbaren Kartenkanten und
die Kontaktdaten als Tabelle übersetzen Gefäßdiagnostik in Gestaltung: hier arbeitet jemand präzise.
Von den dreien sieht diese Variante am deutlichsten nach Facharztpraxis aus.

## Variante C – „Weich & Modern"

Sanfte Verläufe aus Mint und Himmelblau mit einem Champagner-Ton als drittem Klang – frisch und
freundlich, ohne je in Richtung Rosa zu gehen. Plus Jakarta Sans in sehr großem Grad für die
Überschriften erzeugt einen hohen Größenkontrast, der modern wirkt. Große Radien, Pill-Buttons und
weiche Schatten sind die Formensprache, die eine jüngere Zielgruppe von Apps kennt – der Entwurf
für die Patientinnen, die in einigen Jahren die Hauptgruppe sein werden.

---

## Rechtliche Hinweise

### Zu prüfen: „Botox-Behandlung"

Botox ist der Markenname eines **verschreibungspflichtigen** Arzneimittels (Botulinumtoxin Typ A).
Publikumswerbung für verschreibungspflichtige Arzneimittel ist nach **§ 10 Abs. 1 HWG** unzulässig –
die Nennung des Markennamens als Leistung auf einer Praxiswebsite ist ein bekanntes Abmahnrisiko.
Die Leistung steht aktuell so in den Entwürfen, weil sie so in ihrem Text stand. Vor Veröffentlichung
sollte das anwaltlich geprüft und gegebenenfalls in eine wirkstoff- oder indikationsbezogene
Formulierung geändert werden.

### Weitere Formulierungen zur Abstimmung

Diese Stellen stammen wörtlich aus ihrem Text. Sie sind nicht offensichtlich unzulässig, gelten aber
als anpreisend im Sinne von § 27 MBO-Ä und sollten mitgeprüft werden:

- „an der **renommierten** Medizin-Universität Wien"
- „Venenbehandlungen **nach dem neuesten Standard**"
- „Realisierung einer **optimalen**, individuell angepassten phlebologischen Patiententherapie"

### Bewusst nicht enthalten

- **Keine Vorher-Nachher-Darstellungen**, auch nicht als Bildplatzhalter (§ 11 Abs. 1 Nr. 5 HWG).
- **Keine Heilversprechen, keine Erfolgs- oder Zufriedenheitsgarantien.**
- **Keine Patientenbewertungen oder Testimonials.**
- Keine erfundenen Angaben. Alles, was nicht aus ihrem Text stammt, steht in eckigen Klammern.
- Diese Hinweise stehen zusätzlich als Kommentar im Kopf jeder HTML-Datei, sind aber auf der Seite
  nicht sichtbar, damit die Screenshots sauber bleiben.

## Terminbuchung

Der Button „Termin vereinbaren" ist ein Platzhalter ohne Funktion und springt auf den Abschnitt
`#termin`. Dort ist eine abgegrenzte, gestrichelt umrandete Fläche „Reservierter Bereich"
vorgesehen, in die später das externe Widget (Dr. Flex o. Ä.) eingebunden wird. Die Fläche ist in
allen drei Varianten gleich positioniert.

## Technischer Stand

- Je eine einzelne HTML-Datei, CSS im `<style>`-Tag, kein Framework, kein JavaScript.
- Mobile-first, geprüft bis 375 px Breite.
- Semantisches HTML, Sprungmarke zum Inhalt, `aria-label` auf allen Bildplatzhaltern.
- Textkontraste nach WCAG AA (mindestens 4,5:1 für Fließtext). Gold wird auf hellem Grund nur
  dekorativ eingesetzt, nie als Schriftfarbe.
- Alle Seiten tragen `<meta name="robots" content="noindex, nofollow">`.

## Offene Punkte

- Kurzbeschreibungen zu den sechs Leistungen (je 1–2 Sätze)
- Telefonnummer und Sprechzeiten
- Ablauf eines Termins: die drei Schritte sind noch vollständig Platzhalter
- Einleitungstexte für Leistungen, Ablauf und Anfahrt
- Fotos der Praxisräume und ein Portrait – bei allen drei Entwürfen tragen die Bilder viel
- Impressum und Datenschutz: derzeit reine Strukturseiten, juristisch zu befüllen
