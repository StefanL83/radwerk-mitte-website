# Projekt-Zusammenfassung – Radwerk Mitte Website

> Zusammengeführte Fassung aus: (a) dieser Arbeitsumgebung (VS Code / Claude Code) und (b) einer Zusammenfassung von drei weiteren Chats im selben Claude-Project (`radwerk-mitte-projektzusammenfassung.md`, vom Nutzer bereitgestellt). Stand: 19.10.2026.

## 0. Wichtiger Kontext-Hinweis

Laut der aus dem Claude-Project stammenden Zusammenfassung handelt es sich um ein **Übungsprojekt im Kurs "Agentic / Vibe Engineering"** (Aimée Experience Design · BTA). Radwerk Mitte ist demnach eine **fiktive** Firma für Übungszwecke, keine reale Kundenbeziehung. Das deckt sich mit der Kursfolie `image (3).png` in diesem Ordner ("Agentic Engineering · Tag 1", Thema "PRD mit Claude"), die ebenfalls als Kursmaterial erkannt wurde. Diese Einordnung stammt aus einer anderen Chat-Sitzung, nicht aus eigener Prüfung in dieser Sitzung – wird hier aber als plausibel übernommen, da sie zum vorgefundenen Material passt.

## 1. Firmensteckbrief und Ausgangslage

Radwerk Mitte: Fahrradhändler mit Werkstatt, Sitz Kassel, Filialen in Kassel und Göttingen, ca. 120 Beschäftigte, ca. 28 Mio. € Umsatz, laut Firmensteckbrief gegründet 1989 (diese Jahreszahl stammt aus einem in dieser Sitzung nicht eingesehenen Dokument, hier nur übernommen, nicht verifiziert). Wachstumsziel ca. 15 % im nächsten Jahr, vor allem über B2B-Dienstrad-Leasing; B2C bleibt bestehen. Die heutige WordPress-Website wirkt veraltet, zeigt das B2B-Angebot kaum und bietet nur Anfragen per E-Mail.

### Gesicherte Fakten aus dem Kundengespräch (Merle Vogelsang)

- Beispiel-Großauftrag: Klinikum möchte 80 Beschäftigte ausstatten
- Custom-Räder (Luxussegment) werden im nächsten Jahr getestet, Strategie offen
- Risiken: große Online-Händler (z. B. Upway), Engpass im Kundenservice (nur 1 Person), Werkstatt-Engpass bei Spitzenlast, Lieferkettenrisiko bei chinesischen Komponenten (Backups aus Polen/Tschechien)
- Gewünschte neue Funktionen: Leasing-Rechner, FAQ, bessere Vorsortierung von Anfragen
- Kein Partnerportal vorhanden; keine Statistik zur Absprungrate (Problem nur aus Gesprächen bekannt, nicht belegt)
- Blau und Orange bleiben, der Auftritt soll aber weniger altbacken wirken, kein Rebranding
- Budget: zunächst ca. 150.000 €, ggf. mehr nach Rücksprache mit dem Team

## 2. Arbeit im Project, chronologisch über alle Chats

### Chat 1 (anderer Chat im Project) – PRD in einseitige Übersicht umwandeln

Ergebnis laut bereitgestellter Zusammenfassung: ein Dokument "PRD auf einer Seite – Neue Website Radwerk Mitte" (Kernaussage, Ziel mit Messgröße, Zielgruppe, Nicht-Ziele, Annahmen, Akzeptanzkriterien, offene Fragen an Merle) sowie eine 16:9-PRD-Folie als Artifact (bearbeitbar, als PowerPoint/PDF exportierbar).

### Chat 2 (anderer Chat im Project) – Claude-Projekt initialisieren

Ergebnis: eine `CLAUDE.md` mit Projektkontext, belegten Fakten, Dateiübersicht und Arbeitsregeln (Deutsch, Ton sachlich/hilfsbereit/per Sie, belegen statt erfinden, Gesagtes von Vermutetem trennen, offene Fragen statt Lücken füllen) – entspricht im Kern der `CLAUDE.md`, die in diesem Ordner als Projektanweisung vorliegt.

Wichtiger Befund aus diesem Chat: **Abweichungen zwischen verschiedenen PRD-Entwürfen**, die im Kundengespräch nicht belegt sind:

- Werkstatt-Terminbuchung, Statusabfrage, Chat-Funktion und ein Livegang-Termin Frühjahr 2027 wurden im Kundengespräch nie genannt.
- Der externe Onlineshop wird in einem Entwurf nur verlinkt, in einem anderen soll er die Verfügbarkeit je Filiale anzeigen – ein Widerspruch.
- Eine Annahme, die Werkstatt solle einen Großteil des 15-%-Wachstums tragen, widerspricht Merles eigener Aussage zum Werkstatt-Engpass bei Spitzenlast.

Diese Diskrepanzen betreffen andere PRD-Fassungen im Project (PRD-Kurzfassung, PRD als Markdown) – nicht zwingend die `PRD – Neue Website Radwerk Mitte.pdf`, die in dieser Sitzung als maßgeblich verwendet wurde und keine dieser drei Zusatzpunkte enthält. Das bestätigt indirekt, dass mehrere, teils widersprüchliche PRD-Versionen im Umlauf sind und vor der weiteren Umsetzung auf eine gemeinsame Fassung geeinigt werden muss (siehe PRD-Raster-Ziel "Eine Seite" aus dem Kurskontext).

### Chat 3 (anderer Chat im Project) – Design Guideline erstellen

Ergebnis: ein Design-System-Artifact sowie `radwerk-mitte-design-guideline.md` (Haltung, Farben, Typografie, Abstände, Logo, Präsentationen, Web & Apps, Komponenten, Bildsprache, Tonalität), bewusst an die Seh- und Bedienmuster von JobRad angelehnt, inklusive `tokens.css`, `components.css` und SVG-Dateien für Bildmarke und Icons. In dieser ursprünglichen Fassung waren die Markenfarben **Nachtblau + Grün**.

### Diese Sitzung (VS Code / Claude Code) – Umsetzungsplan, Tech Spec, Farbkorrektur, Website-Entwurf, Git

- **Farbkonflikt entdeckt und korrigiert:** Die in Chat 3 erstellte Guideline (Blau+Grün) widersprach der PRD-Vorgabe "Blau und Orange bleiben, kein Rebranding". `radwerk-mitte-design-guideline.md` wurde in dieser Sitzung lokal auf Nachtblau+Orange korrigiert; der exakte Orangeton (`#FF6A00`) ist als Platzhalter-Beispiel markiert. Die Korrektur im geteilten Design-System-Artifact aus Chat 3 wurde vom Berechtigungssystem blockiert ("Unrequested Commit in a Connected App") und steht noch aus.
- **Umsetzungsplan** (`Umsetzungsplan-Radwerk-Mitte.md`): Phasenplan, Akzeptanzkriterien-Checkliste, Verantwortlichkeiten, und für jede offene PRD-Frage eine als Beispiel gekennzeichnete Empfehlung zur Diskussion mit Radwerk.
- **Tech Spec** (`Tech-Spec-Radwerk-Mitte.md`): technologieneutrale Anforderungsspezifikation, da das PRD die Technikentscheidung ausdrücklich erst nach einem WordPress-Fragebogen vorsieht; mit Architektur-Optionen, Datenmodell-Entwurf und Platzhalter-Rechnerlogik.
- **Website-Entwurf** (Claude-Artifact, Design-Typ, nicht im Repo): interaktive Startseite im korrigierten Markendesign mit B2B-Bereich, Leasing-Rechner (Platzhalterformel), FAQ, Referenzen, kategorisiertem Kontaktformular und Footer mit als Platzhalter markierten Kontaktdaten.
- **Git-Repository**: initialisiert, ein Commit (`1b09782`, Autor Stefan) mit den sieben Ausgangsdateien.

## 3. Konsolidierte offene Punkte (aus allen Chats zusammengeführt)

1. **Eine gemeinsame PRD-Fassung:** Die Gruppe muss sich auf eine einseitige Fassung einigen und dabei die in Chat 2 gefundenen Widersprüche auflösen (Werkstatt-Terminbuchung/Status/Chat/Livegang-Termin nicht belegt; Shop nur verlinken vs. Filial-Verfügbarkeit zeigen; Werkstatt-Engpass vs. Werkstatt als Wachstumsträger).
2. **Farben:** Exakter Orangeton und ggf. weitere Auffrischung vs. grundlegende Neugestaltung – mit Radwerk zu klären; Design-System-Artifact aus Chat 3 noch nicht korrigiert.
3. **Technik:** WordPress weiter nutzen oder neu aufsetzen – abhängig vom im PRD vorgesehenen Fragebogen.
4. **Erfolgsmessung:** B2B-Anfragen, weniger Standardmails oder beides; keine heutigen Vergleichswerte vorhanden.
5. **Leasing-Rechner:** echte Konditionen und Partner stehen noch aus; Entwurf nutzt eine klar gekennzeichnete Platzhalterformel.
6. **Partnerportal:** Zeitpunkt offen, für Version 1 nicht vorgesehen, Datenmodell aber vorbereitet.
7. **Custom-Räder:** ob sie schon auf der Seite erscheinen sollen, ist offen.
8. **SLA-Inhalte:** welche Inhalte öffentlich gezeigt werden dürfen, ist offen.
9. **Budget:** Erweiterbarkeit über 150.000 € hinaus und wofür, ist offen.
10. **Design-Entscheidungsprozess:** wer entscheidet und in wie vielen Runden, ist offen.

## 4. Einordnung der Dateien in diesem Ordner

| Datei | Herkunft |
|---|---|
| `PRD – Neue Website Radwerk Mitte.pdf` | Projektunterlage, als maßgeblich behandelt |
| `Übung_Kundengespräch_Protokoll.pdf` | Projektunterlage, Quelle der PRD-Anforderungen |
| `image (3).png` | Kursfolie, kein Radwerk-Material |
| `CLAUDE.md` | Projektanweisungen (entspricht sinngemäß der in Chat 2 erstellten Datei) |
| `radwerk-mitte-design-guideline.md` | Ursprünglich aus Chat 3, in dieser Sitzung farblich korrigiert (Blau+Orange) |
| `Umsetzungsplan-Radwerk-Mitte.md` | In dieser Sitzung erstellt |
| `Tech-Spec-Radwerk-Mitte.md` | In dieser Sitzung erstellt |
| `Projekt-Zusammenfassung.md` | Diese Datei – zusammengeführte Gesamtübersicht |

Der Website-Entwurf selbst liegt nur als Claude-Artifact vor, nicht als Datei in diesem Ordner.
