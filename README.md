# Praxisseite Dr. med. univ. Oana-Raluca Despa

Entwurfsstand 25.09.2026. Basis ist der gewählte Entwurf 3 (modern, weiche Verläufe,
großzügige Typografie). Die früheren Entwürfe 1 und 2 sind entfallen und stecken nur noch
in der Git-Historie.

## Aufbau

```
index.html              Farbvergleich, alle fünf Varianten nebeneinander
seite/farbe-a.html      Mint & Himmel      (die Farbgebung des gewählten Entwurfs)
seite/farbe-b.html      Sand & Salbei      (warm, erdig)
seite/farbe-c.html      Petrol & Perle     (kühl, klar)
seite/farbe-d.html      Taupe & Bronze     (neutral, warm, zurückhaltend)
seite/farbe-e.html      Nachtblau & Leinen (tief, elegant)
seite/impressum.html    Platzhalterseite
seite/datenschutz.html  Platzhalterseite
```

Die fünf Farbvarianten sind **zeichengleich identisch** bis auf den Farbblock und die
Variantenbezeichnung in der oberen Leiste. Aufbau, Texte und Bildflächen sind überall dieselben.

## Farben wechseln

Jede Seite enthält genau einen deutlich markierten Block:

```css
/* ============================================================
   FARBPALETTE: Mint & Himmel
   ...
   ============================================================ */
:root{ ... }
/* ==================== Ende Farbpalette ==================== */
```

Um die Farbigkeit der gesamten Seite zu ändern, wird nur dieser Block durch den einer
anderen Variante ersetzt. Außerhalb davon steht kein einziger Farbwert im Stylesheet.
Ein zweiter, separater `:root`-Block enthält die Strukturwerte (Radius, Schatten, Schrift),
die in allen Varianten gleich bleiben.

Alle fünf Paletten sind gegen WCAG AA geprüft: jede Kombination aus Text- und Flächenfarbe
erreicht mindestens 4,5:1. Der Akzentton kommt in zwei Abstufungen vor, weil der helle Ton
als Textfarbe durchfällt: `--akzent` ist rein dekorativ, `--akzent-tief` trägt Text.

## Kontaktformular

Das Terminbuchungs-Widget ist entfallen. An seiner Stelle steht ein Kontaktformular mit
Name, E-Mail, Telefon (optional) und Nachricht.

**Bewusst nicht enthalten:** Auswahlfelder zu Behandlungen, Beschwerden oder Diagnosen.
Solche Felder würden Gesundheitsdaten im Sinne von Art. 9 DSGVO strukturiert erheben, was
den Aufwand für Rechtsgrundlage, Einwilligung und Verschlüsselung erheblich erhöht. Unter
dem Formular steht der Hinweis, keine sensiblen Gesundheitsdaten anzugeben, mit Link zur
Datenschutzerklärung.

Pflichtfelder sind Name, E-Mail und Nachricht. Die Validierung läuft ohne Framework, zeigt
Fehler direkt am Feld, setzt `aria-invalid`, springt zum ersten fehlerhaften Feld und
räumt die Meldung wieder ab, sobald die Eingabe stimmt. Nach erfolgreichem Absenden
erscheint eine Bestätigung, die den Fokus erhält.

**Offen:** Das Formular versendet noch nichts. Vor dem Livegang muss ein Versandweg
eingerichtet (Mail-Endpunkt oder Formulardienst mit Auftragsverarbeitungsvertrag) und in
der Datenschutzerklärung beschrieben werden. Der Entwurf weist in der Bestätigung darauf hin.

## Platzhalter für Kontaktdaten

`[TELEFON]` und `[EMAIL]` stehen im Kontaktbereich, im Footer und im Impressum, damit sie
an einer Stelle gesucht und ersetzt werden können:

```
grep -rn "\[TELEFON\]\|\[EMAIL\]" seite/
```

Aus dem Text der Kundin liegt bereits die Adresse `privatpraxis-despa@web.de` vor. Sie ist
bewusst nicht eingesetzt, weil für die Praxis vermutlich eine eigene Adresse eingerichtet wird.

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
- Einzige externe Ressource: Google Fonts (Plus Jakarta Sans).
- Mobile-first, geprüft bis 375 px Breite.
- Semantisches HTML, Sprungmarke zum Inhalt, `aria-label` auf allen Bildplatzhaltern.
- Alle Seiten tragen `<meta name="robots" content="noindex, nofollow">`.

## Offene Punkte

- Entscheidung für eine Farbvariante
- Kurzbeschreibungen zu den sechs Leistungen, je ein bis zwei Sätze
- Telefonnummer, E-Mail-Adresse und Sprechzeiten
- Ablauf eines Termins: die drei Schritte sind noch vollständig Platzhalter
- Einleitungstexte für Leistungen, Ablauf und Anfahrt
- Fotos der Praxisräume und ein Portrait
- Versandweg für das Kontaktformular
- Impressum und Datenschutz juristisch befüllen
