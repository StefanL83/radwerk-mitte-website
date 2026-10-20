# Zusammenfassung – Project „Radwerk Mitte“

Stand: 19.10.2026 · Grundlage: die 3 bisherigen Chats im Project und die Project-Dateien

## 1. Kontext

Übungsprojekt im Kurs **Agentic / Vibe Engineering** (Aimée Experience Design · BTA). Kunde ist die **fiktive** Radwerk Mitte GmbH, ein Fahrradhändler mit Werkstatt aus Kassel (Filialen Kassel und Göttingen, ca. 120 Beschäftigte, ca. 28 Mio. € Umsatz, gegründet 1989). Der am schnellsten wachsende Bereich ist das **Dienstrad-Leasing** für Firmen, Kliniken und Kommunen.

Aufgabe: aus dem Kundengespräch mit Merle Vogelsang ein **PRD für die neue Website** ableiten (Kursschritt 2), Entwürfe in Paaren vergleichen und als Gruppe auf **eine einseitige Fassung** einigen.

PRD-Raster: Ziel · Zielgruppe · Nicht-Ziele · Annahmen · Akzeptanzkriterien · Eine Seite.

### Project-Dateien
- Protokoll des Kundengesprächs (PDF)
- Firmensteckbrief Radwerk Mitte (PDF)
- PRD (Langfassung, PDF) und PRD-Kurzfassung (PDF)
- PRD als Markdown (1 Seite, Jonas Wittwer)
- Zwei Kursfolien/Entwürfe als Bild (PRD-Raster, „PRD · Website Radwerk · Entwurf v1“)

## 2. Gesicherte Fakten aus dem Kundengespräch

- Wachstumsziel ca. **15 %** im nächsten Jahr, vor allem über **B2B-Dienstrad-Leasing**; B2C bleibt bestehen
- Beispiel: Klinikum möchte **80 Beschäftigte** ausstatten
- Custom-Räder (Luxussegment) werden nächstes Jahr getestet, Strategie offen
- Risiken: große Online-Händler (z. B. Upway), Engpass im Kundenservice (1 Person) und in der Werkstatt bei Spitzenlast, Lieferkette (China; Backups aus Polen/Tschechien)
- Aktuelle WordPress-Website wirkt veraltet, B2B-Angebot kaum sichtbar, Anfragen nur per E-Mail
- Gewünscht: Leasing-Rechner, FAQ, bessere Vorsortierung von Anfragen
- Kein Partnerportal vorhanden; keine Statistik zur Absprungrate (Problem nur aus Gesprächen bekannt)
- Blau und Orange bleiben, der Auftritt soll aber weniger altbacken wirken
- Budget: zunächst ca. **150.000 €**, ggf. mehr nach Rücksprache mit dem Team

## 3. Chats im Project

### Chat 1 – „PRD in einseitige Übersicht umwandeln“
- Auftrag: aus dem PRD eine einseitige Übersicht erstellen.
- Ergebnis: ein Doc „PRD auf einer Seite – Neue Website Radwerk Mitte“ mit Kernaussage, Ziel (mit Messgröße), Zielgruppe, Nicht-Zielen, Annahmen, Akzeptanzkriterien und offenen Fragen an Merle.
- Zusätzlich eine **PRD-Folie** (16:9, Radwerk-Designvorgaben) mit sechs Karten; die offenen Fragen sind dunkel hervorgehoben. Die Folie ist als Artifact veröffentlicht, bearbeitbar und als PowerPoint/PDF exportierbar.

### Chat 2 – „Claude-Projekt initialisieren“
- Auftrag: Claude im Project initiieren und eine `CLAUDE.md` anlegen.
- Ergebnis: `CLAUDE.md` mit Projektkontext, belegten Fakten, Dateiübersicht, Arbeitsregeln (Deutsch, Ton sachlich/hilfsbereit/per Sie, belegen statt erfinden, Gesagtes von Vermutetem trennen, offene Fragen statt Lücken füllen).
- Hinweis: Damit die Datei in jedem Chat wirkt, muss sie als Projektdatei hochgeladen oder in die Project-Anweisungen kopiert werden (Letzteres ist verlässlicher).
- Festgestellte **Abweichungen zwischen den PRD-Entwürfen**:
  - Werkstatt-Terminbuchung, Statusabfrage, Chat und Livegang Frühjahr 2027 wurden im Kundengespräch nie genannt.
  - Shop: einmal nur verlinken, einmal Verfügbarkeit je Filiale anzeigen.
  - Annahme „Werkstatt schafft das Mehr bei 15 %“ widerspricht Merles Aussage zum Werkstatt-Engpass.

### Chat 3 – „Design Guideline für Radwerk Mitte“
- Auftrag: Design Guideline im Stil von JobRad (vertraute Benutzerführung, Fahrrad-Assoziation) für Präsentationen, Websites, Apps.
- Ergebnis: ein Design-System als Artifact sowie die Datei `radwerk-mitte-design-guideline.md` mit Haltung, Farben, Typografie, Abständen, Logo, Präsentationen, Web & Apps, Komponenten, Bildsprache und Tonalität.
- Enthalten sind direkt nutzbare Code-Blöcke: `tokens.css` (Farben, Abstände, Radien, Schatten, Hell-/Dunkelmodus), `components.css` (Button, Badge, Eingabefeld, Karte, Schrittfolge) sowie SVG für Bildmarke und fünf Icons.
- Tipp: Die Datei eignet sich auch als `DESIGN.md` für Claude Code.

## 4. Offene Punkte

- Einigung der Gruppe auf **eine** PRD-Fassung (Umfang Stufe 1: Termin-Buchung, Status, Chat ja/nein?)
- Shop: nur verlinken oder Filial-Verfügbarkeit anzeigen
- Erfolgsmessung: B2B-Anfragen, weniger Standardmails oder beides; es gibt keine Vergleichswerte
- Leasing-Konditionen und Partner für den Rechner
- Technik: WordPress weiter nutzen oder neu aufsetzen
- Wann ein Partnerportal folgt; ob Custom-Räder schon auf die Seite kommen
- Welche SLA-Inhalte öffentlich gezeigt werden dürfen
- Budget über 150.000 € hinaus und wofür
- Design: Auffrischung mit Blau/Orange oder grundlegend neu gestalten; Entscheider und Anzahl der Entwurfsrunden
