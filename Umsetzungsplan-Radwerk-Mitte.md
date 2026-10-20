# Umsetzungsplan – Neue Website Radwerk Mitte

> Grundlage: `PRD – Neue Website Radwerk Mitte.pdf` (maßgeblich) und `Übung_Kundengespräch_Protokoll.pdf` (Herkunft der Anforderungen). Stand: 19.10.2026.
>
> Empfehlungen in diesem Dokument sind Beispiele zur Diskussion mit Radwerk, keine getroffenen Entscheidungen. Sie sollen die offenen Punkte konkret genug machen, um in einem kurzen Abstimmungstermin mit Merle Vogelsang, Dilan Aydın, Amara Osei und Svenja Kowalczyk entschieden zu werden – nicht, um sie vorwegzunehmen.

## 0. Was schon geklärt ist – und was noch offen ist

| Punkt | Status | Befund / Empfehlung |
|---|---|---|
| Farben | Design-Guideline korrigiert | PRD und Protokoll sagen klar: Blau und Orange bleiben, kein Rebranding. `radwerk-mitte-design-guideline.md` wurde entsprechend von Nachtblau+Grün auf Nachtblau+Orange umgestellt. Weiterhin offen: Der exakte Orangeton (`#FF6A00`) ist ein Platzhalter-Beispiel. Empfehlung: Vor der Design-Freigabe ein Foto oder den Pantone-/RAL-Wert der Firmenfahrzeuge von Radwerk einholen und damit abgleichen. |
| Technik | Noch offen, bewusst | PRD sagt ausdrücklich: Technik wird erst nach Analyse der bestehenden WordPress-Seite per Fragebogen festgelegt. WordPress ist nicht gesetzt. Keine Tech-Entscheidung vorab treffen – auch keine beispielhafte, da hier echte Fakten (Plugins, Datenmodell) erst noch fehlen. |

## 1. Offene Fragen an Merle – mit Beispiel-Empfehlung zur Diskussion

Die PRD listet diese Fragen ausdrücklich als ungeklärt (PRD S. 4). Jede Zeile hier ist ein Vorschlag, kein Fakt – zur Abstimmung im Kickoff-Termin.

| Offene Frage (aus PRD) | Beispiel-Empfehlung (zur Diskussion) |
|---|---|
| Woran genau messen wir Erfolg – B2B-Anfragen, weniger Standardmails, oder beides? Gibt es heutige Vergleichswerte? | Beide Metriken parallel tracken (PRD nennt beide als Ziel), da heute ohnehin keine Vergleichswerte existieren. Ab Launch ein einfaches monatliches Dashboard mit B2B-Anfragen pro Monat und Mail-/Anruf-Volumen beim Kundenservice führen, um nach 2–3 Monaten eine Baseline zu haben. |
| Welche Leasing-Konditionen und Partner fließen in den Rechner? | Rechner zunächst mit einer vereinfachten, klar als unverbindlich gekennzeichneten Beispielformel starten (Radpreis + Bruttogehalt → grobe monatliche Belastung über Gehaltsumwandlung), bis Radwerk die echten Leasingraten und Partnerkonditionen liefert. Erst mit echten Daten live schalten. |
| Ab wann soll ein Partnerportal folgen? | Nicht in Version 1 einplanen (siehe Nicht-Ziele). Empfehlung: Datenmodell und Formularstruktur so anlegen, dass eine Partnerportal-Schnittstelle ca. 6–12 Monate nach Launch ergänzt werden kann, ohne die Website neu aufzubauen. |
| Sollen Custom-Räder schon jetzt auf der Seite erscheinen? | Nicht zeigen in Version 1 – passt zum PRD-Nicht-Ziel und dazu, dass Radwerk das Luxussegment laut Protokoll selbst erst im nächsten Jahr testet. Falls gewünscht, höchstens als kurzer Teaser ohne Preis oder Konfigurator. |
| Welche Inhalte der Service Level Agreements dürfen öffentlich gezeigt werden? | Nur allgemeine, nicht kundenspezifische Standards veröffentlichen (z. B. typische Reaktionszeiten, Werkstattservice-Umfang) – keine Vertragsdetails einzelner Kunden. |
| Ist das Budget über 150.000 Euro hinaus erweiterbar, und wofür? | Mit 150.000 Euro planen und eine kurze Nice-to-have-Liste führen (z. B. Partnerportal-Vorbereitung, zusätzliche Sprache), die bei Freigabe eines höheren Budgets zuerst gezogen wird. |
| Wer entscheidet über Entwürfe, und in wie vielen Runden? | Zwei Entwurfsrunden vorschlagen: (1) Wireframe/Informationsarchitektur-Review, (2) High-Fidelity-Design mit Farben/Bildsprache – Freigabe jeweils durch Merle Vogelsang, fachlicher Input vorab von Dilan, Amara und Svenja. |

## 2. Was ist für die Website empfehlenswert? (Zusammenfassung)

Basierend auf PRD und Gesprächsprotokoll, als Ausgangspunkt für die Abstimmung mit Radwerk:

- Struktur zuerst klären, dann gestalten: B2B, Privatkunden und Werkstatt als drei klar unterscheidbare Einstiege, B2B mit einem Klick von der Startseite erreichbar – das ist die zentrale PRD-Anforderung und sollte die Informationsarchitektur dominieren.
- Rechner früh, aber vorsichtig: Der Leasing-Rechner ist das meistgewünschte Feature (Protokoll + PRD). Lieber mit einer transparent unverbindlichen Beispielrechnung früh live gehen und später mit echten Partnerkonditionen verfeinern, als auf vollständige Daten zu warten.
- Formular vor Mail: Ein kategorisiertes Formular mit Weiterleitung ersetzt den heutigen reinen Mail-Weg – das adressiert sowohl die Absprungrate als auch die Entlastung des einzigen Support-Mitarbeiters.
- Technikentscheidung bewusst spät: Nicht vorab auf WordPress oder eine Alternative festlegen, sondern den im PRD vorgesehenen Fragebogen zur Bestandsseite zuerst auswerten.
- Farben zweistufig lösen: Mit der korrigierten Guideline (Blau+Orange) arbeiten, aber den exakten Orangeton erst mit echtem Fahrzeug-Referenzmaterial von Radwerk fixieren, bevor das Design final eingefroren wird.
- Messbarkeit von Anfang an: Da es keine heutigen Vergleichswerte gibt, Tracking für Absprungrate, Formularabschlüsse und Rechnernutzung vor dem Launch einbauen, nicht danach nachrüsten.

## 3. Scope (laut PRD, Annahme "Umfang")

Enthalten in Version 1: Website mit B2B-Bereich, Leasing-Rechner, FAQ, Anfrageformular mit Kategorien, Referenzen, Standort-/Kontaktinfos, Link zum bestehenden externen Onlineshop.

Bewusst nicht enthalten (Nicht-Ziele): eigener Onlineshop, Partnerportal mit Kunden-Login (nur vorbereiten, z. B. saubere Datenstruktur für API-Anbindung später), Konfigurator für Custom-Räder, Rebranding, neue Support-Software (Formular leitet weiterhin per Mail weiter).

## 4. Phasenplan

### Phase 1 – Discovery & Bestandsaufnahme
- Fragebogen zur bestehenden WordPress-Seite auswerten (Inhalte, Plugins, Datenbestand, SEO-Status) – Grundlage für die spätere Technikentscheidung.
- Offene Fragen aus Abschnitt 1 mit Merle, Dilan, Amara und Svenja klären (inkl. Vorschläge aus dieser Tabelle als Diskussionsgrundlage).
- Fahrzeug-Referenzmaterial für den exakten Orangeton einholen (siehe Abschnitt 0).
- Zulieferung durch Radwerk einsammeln: Texte, Bilder, FAQ-Rohfragen, Referenzfreigaben, Leasing-Konditionen.
- Gate: Technikentscheidung erst nach Auswertung des Fragebogens.

### Phase 2 – Konzept & Design
- Informationsarchitektur: B2B, Privatkunden und Werkstatt als auf den ersten Blick unterscheidbare Bereiche; B2B-Bereich mit einem Klick von der Startseite erreichbar (Akzeptanzkriterium).
- Visuelles Design auf Basis der korrigierten Guideline (Blau+Orange), finaler Orangeton erst nach Abstimmung mit Radwerk einfrieren, Ton: sachlich, hilfsbereit, per Sie.
- Barrierefreiheit und Lesbarkeit auf Smartphone und Desktop als Kriterium, nicht als Nachgedanke.
- Gate: Freigabe des Designs durch Merle Vogelsang (explizites Ziel im PRD).

### Phase 3 – Technik-Entscheidung & Aufbau
- Technologieauswahl basierend auf Fragebogen-Ergebnissen aus Phase 1.
- CMS so wählen/konfigurieren, dass Svenja Kowalczyk Inhalte ohne Entwicklerhilfe pflegen kann (explizite Anforderung).
- Umsetzung: B2B-Bereich, Leasing-Rechner (Eingabe Radpreis + Bruttogehalt → monatliche Belastung, mit Hinweis „unverbindlich"), Anfrageformular mit Pflichtfeld Kategorie (z. B. B2B-Angebot, Werkstatt, Bestellung, Sonstiges) inkl. Weiterleitung per Mail an zuständige Person, FAQ-Bereich, Referenzbereich (mind. 1 B2B-Referenz, z. B. Klinikums-Beispiel), Standort-/Telefoninfo auf jeder Seite, Link zum externen Onlineshop.
- Rechner-Logik erst final spezifizieren, wenn Leasing-Konditionen/Partner (offene Frage) vorliegen; bis dahin Beispielformel aus Abschnitt 1 nutzen.

### Phase 4 – Content & Qualitätssicherung
- Texte, Bilder und FAQ mit Amara Osei (Kundenservice) und Svenja Kowalczyk abstimmen.
- Formular-Routing mit Dilan Aydın (B2B-Vertrieb) und Amara Osei testen (korrekte Kategorie → korrekte Person).
- Responsive-Test aller Seiten auf Smartphone und Desktop (Akzeptanzkriterium).
- Prüfen, ob Link zum externen Onlineshop funktioniert.

### Phase 5 – Messbarkeit einrichten
- Da es laut PRD aktuell keine Vergleichszahlen gibt, Tracking für Absprungrate, Formularabschlüsse, Rechnernutzung und B2B-Anfragen pro Monat vor Launch einrichten, damit die Vergleichsbasis ab Launch entsteht (PRD-Annahme "Messung").
- Festlegen, welche der im PRD genannten Metriken primär berichtet werden (siehe Empfehlung in Abschnitt 1).

### Phase 6 – Freigabe & Launch
- Abgleich mit allen Akzeptanzkriterien aus dem PRD (Checkliste unten).
- Finale Freigabe durch Merle Vogelsang.
- Launch, danach Monitoring der KPI-Baseline.

## 5. Akzeptanzkriterien-Checkliste (wörtlich aus PRD übernommen)

- [ ] Dienstrad-Leasing für Unternehmen von der Startseite mit einem Klick erreichbar
- [ ] Leasing-Rechner: Radpreis + Bruttogehalt → monatliche Belastung, mit Hinweis „unverbindlich"
- [ ] Anfrageformular mit Kategorie, Weiterleitung an zuständige Person
- [ ] FAQ deckt häufigste Standardfragen ab, abgestimmt mit Kundenservice
- [ ] Mindestens eine B2B-Referenz sichtbar
- [ ] Telefonnummer und beide Standorte (Kassel, Göttingen) auf jeder Seite
- [ ] Link zum externen Onlineshop funktioniert
- [ ] Design nutzt die freigegebene Farbdefinition (Blau+Orange, finaler Ton bestätigt) und wirkt modern, von Merle freigegeben
- [ ] Alle Seiten funktionieren auf dem Smartphone
- [ ] Absprungrate und Anzahl der Anfragen sind ab Launch messbar

## 6. Verantwortlichkeiten (laut PRD)

| Rolle | Person | Funktion im Projekt |
|---|---|---|
| Entscheidung/Freigabe | Merle Vogelsang | Gesamtfreigabe, Design-Freigabe |
| B2B-Vertrieb | Dilan Aydın | Anforderungen an Formular/Lead-Qualifizierung |
| Kundenservice | Amara Osei | FAQ-Inhalte, Formular-Kategorien |
| Content/Marketing | Svenja Kowalczyk | Laufende Pflege, CMS-Anforderungen |

## 7. Budget

Geplant: 150.000 Euro. Erweiterung nur nach Rücksprache von Merle mit ihrem Team – im Plan nicht als gesichert verbucht (siehe Empfehlung in Abschnitt 1).

## 8. Nicht Teil dieses Plans

Entsprechend den PRD-Nicht-Zielen: kein eigener Onlineshop, kein Partnerportal mit Login, kein Custom-Rad-Konfigurator, kein Rebranding, keine neue Support-Software. Für das Partnerportal nur so vorbereiten, dass eine spätere Schnittstellenanbindung nicht blockiert wird – nicht mehr.
