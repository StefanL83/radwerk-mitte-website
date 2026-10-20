# Testplan – Neue Website Radwerk Mitte

> Grundlage: `PRD – Neue Website Radwerk Mitte.pdf` (maßgeblich, insbesondere Abschnitt „Akzeptanzkriterien" auf S. 3), `Übung_Kundengespräch_Protokoll.pdf`, `Tech-Spec-Radwerk-Mitte.md` und `Umsetzungsplan-Radwerk-Mitte.md`. Stand: 20.10.2026.
>
> Hinweis zum aktuellen Stand: `index.html` und `pflegedienste.html` sind ein statischer HTML-Entwurf (Design-/Funktionsprototyp für GitHub Pages, siehe Badge „Entwurf" im Header). Es gibt noch kein CMS, keinen echten E-Mail-Versand und keine von Radwerk bestätigten Leasingkonditionen oder Kontaktdaten – das ist laut PRD und Umsetzungsplan auch so beabsichtigt, da die Technikentscheidung erst nach Auswertung des WordPress-Fragebogens fällt. Dieser Testplan unterscheidet deshalb explizit zwischen Testfällen, die **am aktuellen Entwurf** schon prüfbar sind, und solchen, die erst **nach der Technik-/Backend-Entscheidung** (Phase 3 im Umsetzungsplan) ausführbar sind.

## 1. Ziel und Geltungsbereich

Dieser Testplan prüft, ob Version 1 der Website die acht im PRD festgelegten Akzeptanzkriterien erfüllt, sowie die daraus abgeleiteten funktionalen und nicht-funktionalen Anforderungen aus der Tech Spec. Freigabekriterium laut PRD: *„Die Seite ist fertig, wenn alle Punkte erfüllt sind und Merle Vogelsang sie freigibt."*

## 2. Teststufen

| Teststufe | Zweck | Wann |
|---|---|---|
| Entwurfs-/Prototyp-Test | Struktur, Interaktion und Inhalte des statischen HTML-Entwurfs prüfen | Laufend, schon heute möglich |
| Funktionstest (Backend) | Formular-Versand, Kategorie-Routing, Rechner mit echten Konditionen | Nach Technikentscheidung (Phase 3) |
| Abnahmetest (UAT) | Abgleich mit der PRD-Akzeptanzkriterien-Checkliste durch Radwerk | Vor Launch (Phase 6) |
| Freigabetest | Finale Freigabe durch Merle Vogelsang | Launch-Gate |

Da im Projekt kein Test-Framework vorliegt, erfolgen alle Tests manuell (Browser/Gerät) nach den Schritten unten.

## 3. Testfälle je PRD-Akzeptanzkriterium

| ID | Akzeptanzkriterium (PRD) | Testschritte | Erwartetes Ergebnis | Am Entwurf testbar? |
|---|---|---|---|---|
| TC-01 | Dienstrad-Leasing für Unternehmen ist von der Startseite mit einem Klick erreichbar | Startseite öffnen, Hauptnavigation/„Für Unternehmen" prüfen | Ein Klick führt zum B2B-Bereich (`#fuer-unternehmen`) | Ja – vorhanden |
| TC-02 | Leasing-Rechner gibt nach Eingabe von Radpreis und Bruttogehalt die monatliche Belastung aus, mit Hinweis „unverbindlich" | Regler „Radpreis" und „Monatliches Bruttogehalt" in verschiedene Positionen bewegen (Min, Max, Mitte) | Monatliche Rate aktualisiert sich live; Text „Unverbindlich …" ist sichtbar | Teilweise – Rechenformel ist laut Entwurf-Badge „Beispiel"/Platzhalter, keine von Radwerk bestätigten Konditionen (siehe Tech Spec Abschnitt 7). Formel-Logik selbst ist aber testbar. |
| TC-03 | Anfrageformular verlangt eine Kategorie und leitet an die zuständige Person weiter | Formular ohne Kategorie absenden; danach mit jeder Kategorie (B2B-Angebot, Werkstatt, Bestellung, Sonstiges) absenden | Pflichtfeld-Validierung greift; nach Absenden erscheint Bestätigung | Teilweise – UI-Validierung und Bestätigungsanzeige sind im Entwurf vorhanden (`contact-form`/`contact-thanks`), es erfolgt aber **kein echter Versand/Routing per E-Mail** (kein Backend). Weiterleitung an die „zuständige Person" ist erst nach Technikentscheidung testbar. |
| TC-04 | FAQ deckt häufigste Standardfragen ab, abgestimmt mit dem Kundenservice | FAQ-Bereich öffnen, jede Frage per Klick auf-/zuklappen | Akkordion öffnet/schließt korrekt, Icon wechselt +/− | Ja (Technik) – **Inhaltliche Abstimmung mit Amara Osei (Kundenservice) ist laut Entwurf-Hinweis noch offen**, aktuelle FAQ sind als „Beispiel" markiert |
| TC-05 | Mindestens eine Referenz eines Geschäftskunden ist sichtbar | Abschnitt „Referenzen" prüfen | Mindestens eine Referenz (aktuell Klinikums-Beispiel, 80 Beschäftigte) ist sichtbar | Ja – vorhanden, aber als Beispiel/Platzhalter markiert; echte Referenzfreigabe durch Radwerk steht laut PRD noch aus |
| TC-06 | Telefonnummer und beide Standorte (Kassel, Göttingen) stehen auf jeder Seite | Footer auf `index.html` und `pflegedienste.html` prüfen | Kassel und Göttingen mit Adresse/Telefon erscheinen auf jeder Seite | Teilweise – Platzierung ist vorhanden, Inhalte sind aktuell „[Adresse/Telefon – Platzhalter]" und müssen durch echte Daten von Radwerk ersetzt werden |
| TC-07 | Link zum externen Onlineshop funktioniert | Footer-Link „Zum Onlineshop" anklicken | Link öffnet den externen Shop | Nein – aktuell nur Platzhalter-URL (`example.com`); echter Shop-Link von Radwerk steht noch aus |
| TC-08 | Design nutzt Blau und Orange, wirkt modern, freigegeben durch Merle | Visuelle Prüfung gegen `radwerk-mitte-design-guideline.md` | Farben entsprechen der Guideline; Freigabe-Vermerk von Merle liegt vor | Design visuell testbar; **Freigabe durch Merle steht noch aus** (Gate laut Umsetzungsplan Phase 2). Exakter Orangeton ist laut Umsetzungsplan Abschnitt 0 noch ein Platzhalter-Beispiel. |
| TC-09 | Alle Seiten funktionieren auf dem Smartphone | `index.html` und `pflegedienste.html` auf mobilen Breakpoints testen (siehe Abschnitt 5) | Layout, Navigation, Rechner, FAQ und Formular sind auf Smartphone nutzbar, kein horizontales Scrollen | Ja |
| TC-10 | Absprungrate und Anzahl der Anfragen sind ab Launch messbar | Prüfen, ob Tracking/Analytics eingebunden ist | Tracking-Code erfasst Formularabschlüsse, Rechnernutzung, Seitenaufrufe | Nein – laut Tech Spec Abschnitt 9 muss Analytics vor Launch eingerichtet werden; im aktuellen Entwurf ist kein Tracking vorhanden |

## 4. Ergänzende funktionale Testfälle (nicht wörtlich im PRD, aber aus Umsetzung ableitbar)

| ID | Testfall | Schritte | Erwartetes Ergebnis |
|---|---|---|---|
| TC-11 | Dropdown „Für Unternehmen" → Pflegedienste | Auf Desktop über den Pfeil klicken bzw. per Hover öffnen; per Tastatur (Tab/Enter) bedienen; Escape drücken | Dropdown öffnet/schließt per Klick, Hover und Tastatur; schließt bei Klick außerhalb oder Escape |
| TC-12 | Navigation zwischen `index.html` und `pflegedienste.html` | Von Pflegedienste-Seite zurück zu Startseite, Anker-Links (`index.html#kontakt` etc.) von der Unterseite aus prüfen | Alle internen Anker-Links springen zur richtigen Sektion auf der Zielseite |
| TC-13 | Rechner – Grenzwerte | Radpreis auf Minimum (500 €) und Maximum (6.000 €) setzen; Bruttogehalt auf Minimum (1.500 €) und Maximum (8.000 €) setzen | Berechnung bleibt plausibel (keine negativen/NaN-Werte), Anzeige bleibt lesbar |
| TC-14 | Formular – Pflichtfelder und E-Mail-Format | Formular mit leerem Namen/ungültiger E-Mail-Adresse absenden | Browser-native Validierung verhindert Absenden bzw. zeigt Fehlermeldung |
| TC-15 | FAQ – Mehrfachbedienung | Mehrere FAQ-Einträge nacheinander und gleichzeitig öffnen | Jeder Eintrag lässt sich unabhängig öffnen/schließen, `aria-expanded` wird korrekt gesetzt |

## 5. Nicht-funktionale Testfälle

| Bereich | Testfall | Referenz |
|---|---|---|
| Responsive/Mobile | Seiten bei typischen Breakpoints testen: 360 px, 390 px, 768 px, 1024 px, 1440 px (Chrome DevTools + mindestens ein reales Smartphone) | PRD-Akzeptanzkriterium TC-09, Tech Spec Abschnitt 8 |
| Barrierefreiheit | Kontraste (Blau/Orange auf Weiß/Navy), Fokus-Zustände bei Tab-Navigation, Alt-Texte für Bilder, Formularlabels, FAQ-Buttons mit Screenreader (z. B. NVDA) testen | Tech Spec Abschnitt 8 (WCAG 2.2 AA), `radwerk-mitte-design-guideline.md` |
| Performance | Core Web Vitals (LCP, CLS, INP) auf Startseite messen (z. B. Lighthouse) | Tech Spec Abschnitt 8 – noch keine konkrete PRD-Kennzahl, als Richtwert vorgeschlagen |
| Datenschutz/DSGVO | Prüfen, ob Datenschutzerklärung und Einwilligung beim Formular vorhanden sind, sobald personenbezogene Daten real verarbeitet werden | Tech Spec Abschnitt 8 – aktuell nur Platzhalter-Link „Datenschutz" im Footer |
| Sicherheit | Formular auf Spam-Schutz und serverseitige Validierung prüfen | Tech Spec Abschnitt 8 – erst nach Backend-Entscheidung umsetzbar |
| Cross-Browser | Chrome, Firefox, Safari, Edge (aktuelle Versionen) auf Desktop und Safari/Chrome auf iOS/Android | Ergänzend zu TC-09 |

## 6. Testumgebungen (Vorschlag)

| Gerätetyp | Beispiel | Browser |
|---|---|---|
| Smartphone (klein) | 360–390 px Breite | Safari (iOS), Chrome (Android) |
| Tablet | 768–834 px Breite | Safari (iPadOS) |
| Desktop | ≥1280 px Breite | Chrome, Firefox, Edge |

## 7. Aktuell nicht testbar / abhängig von offenen Punkten

Diese Punkte lassen sich erst prüfen, sobald die zugehörigen offenen Fragen (siehe PRD S. 4 und Umsetzungsplan Abschnitt 1) mit Radwerk geklärt sind:

- **E-Mail-Versand und Kategorie-Routing (TC-03):** abhängig von der Technikentscheidung (Umsetzungsplan Phase 3).
- **Echte Leasing-Rechner-Formel (TC-02):** abhängig von den finalen Leasingkonditionen und Partnern.
- **Echte Kontaktdaten (TC-06) und Shop-Link (TC-07):** abhängig von Zulieferung durch Radwerk (PRD-Annahme „Zulieferung").
- **Design-Freigabe (TC-08):** abhängig von Freigabe durch Merle Vogelsang und vom finalen Orangeton (Fahrzeug-Referenzmaterial).
- **FAQ-Inhalte (TC-04):** abhängig von Abstimmung mit Amara Osei.
- **Analytics/Messbarkeit (TC-10):** abhängig von der Wahl eines Analytics-Tools (Tech Spec Abschnitt 9, bisher offen).

## 8. Freigabeprozess

1. Testfälle TC-01 bis TC-15 sowie Abschnitt 5 am jeweils aktuellen Stand durchführen und Ergebnisse dokumentieren (bestanden/nicht bestanden/nicht anwendbar mit Begründung).
2. Offene Punkte aus Abschnitt 7 mit Radwerk klären, danach betroffene Testfälle erneut ausführen.
3. Finaler Abgleich mit der Akzeptanzkriterien-Checkliste in `Umsetzungsplan-Radwerk-Mitte.md` (Abschnitt 5).
4. Freigabe durch Merle Vogelsang (PRD-Gate), fachliche Vorabnahme durch Dilan Aydın, Amara Osei und Svenja Kowalczyk für ihre jeweiligen Bereiche.
