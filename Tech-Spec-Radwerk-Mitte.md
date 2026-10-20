# Tech Spec – Neue Website Radwerk Mitte

> Grundlage: `PRD – Neue Website Radwerk Mitte.pdf` (maßgeblich), `Übung_Kundengespräch_Protokoll.pdf` und `Umsetzungsplan-Radwerk-Mitte.md`. Stand: 19.10.2026.
>
> Wichtig: Das PRD legt ausdrücklich fest, dass die Technik erst nach Auswertung eines Fragebogens zur bestehenden WordPress-Seite festgelegt wird – WordPress ist nicht gesetzt. Diese Spec legt sich deshalb bewusst nicht auf eine konkrete Plattform fest, sondern beschreibt Anforderungen, Architektur-Optionen und eine Beispiel-Logik für den Rechner. Alles, was als Beispiel oder Vorschlag markiert ist, ist zur Diskussion mit Radwerk gedacht, keine Entscheidung.

## 1. Zweck und Geltungsbereich

Diese Spec beschreibt die technischen Anforderungen für Version 1 der neuen Radwerk-Mitte-Website, wie im PRD als Umfang definiert: Website mit B2B-Bereich, Leasing-Rechner, FAQ, Anfrageformular mit Kategorien, Referenzen, Standort-/Kontaktinfos und Link zum bestehenden externen Onlineshop. Sie ist Grundlage für die Technologieauswahl in Phase 1/3 des Umsetzungsplans, nicht deren Ersatz.

## 2. Bindende Vorgaben aus dem PRD (nicht verhandelbar)

- Keine Technikentscheidung vor Auswertung des WordPress-Fragebogens (Phase-1-Gate im Umsetzungsplan).
- Das CMS muss so einfach sein, dass Svenja Kowalczyk Inhalte ohne Entwicklerhilfe pflegen kann.
- Keine neue Support-Software: Das Anfrageformular leitet weiterhin per E-Mail an die zuständige Person weiter.
- Der bestehende externe Onlineshop bleibt unverändert und wird nur verlinkt, keine Integration.
- Kein Partnerportal mit Kunden-Login in Version 1 – nur so vorbereiten, dass eine spätere Schnittstelle nicht blockiert wird.
- Kein Konfigurator für Custom-Räder, kein Rebranding.
- Alle Seiten müssen auf dem Smartphone funktionieren (Akzeptanzkriterium).

## 3. Funktionale Anforderungen (Version 1)

| Funktion | Anforderung (aus PRD) |
|---|---|
| B2B-Bereich | Von der Startseite mit einem Klick erreichbar |
| Leasing-Rechner | Eingabe Radpreis + Bruttogehalt → Ausgabe monatliche Belastung, mit Pflichthinweis "unverbindlich" |
| Anfrageformular | Pflichtfeld Kategorie (z. B. B2B-Angebot, Werkstatt, Bestellung, Sonstiges), Weiterleitung per E-Mail an zuständige Person |
| FAQ | Deckt häufigste Standardfragen ab, mit Kundenservice abgestimmt |
| Referenzen | Mindestens eine B2B-Referenz sichtbar (Beispiel: Klinikums-Auftrag) |
| Standort/Kontakt | Telefonnummer und beide Standorte (Kassel, Göttingen) auf jeder Seite |
| Externer Shop | Link zum bestehenden Onlineshop, keine tiefere Integration |

## 4. Architektur-Optionen (zu bewerten nach dem Fragebogen – keine Festlegung)

Diese drei Richtungen sind Beispiele zur Diskussion, keine Vorentscheidung. Die tatsächliche Wahl hängt vom Ergebnis des WordPress-Fragebogens ab (Inhalte, Datenmenge, SEO-Historie, laufende Integrationen).

- **Option A – Modernisiertes WordPress:** Theme-Neubau auf bestehender WordPress-Basis. Vorteil: Content-Historie und SEO-Werte bleiben erhalten, Team kennt das System bereits. Risiko: Laut Gesprächsprotokoll arbeitet die heutige Seite mit vielen Plugins – vor Wiederverwendung prüfen, welche davon noch nötig sind.
- **Option B – Headless CMS mit eigenem Frontend:** Trennung von Inhalt und Darstellung. Vorteil: Flexibler für den Leasing-Rechner und Performance. Risiko: Höherer Entwicklungsaufwand, Einfachheit für Svenja muss im Auswahlprozess explizit geprüft werden.
- **Option C – Website-Baukasten mit integriertem CMS:** Schnell umsetzbar, in der Regel sehr einfach zu pflegen. Risiko: Individuelle Rechner-Logik und Formular-Routing können eingeschränkter sein als bei A/B – vorab mit einem Proof of Concept prüfen.

**Entscheidungskriterien (Vorschlag):** einfache Content-Pflege ohne Entwicklerhilfe, Platz für eine interaktive Rechner-Komponente, kategorisiertes Formular mit E-Mail-Routing, mobile Performance, Umsetzbarkeit innerhalb des 150.000-€-Budgets inklusive Content-Migration.

## 5. Komponentenübersicht (technologieneutral)

- **Content-Seiten:** Startseite, B2B-Bereich, Privatkunden, Werkstatt, Über uns/Standorte.
- **Leasing-Rechner:** Interaktive Komponente, Berechnung kann clientseitig erfolgen; Nutzung sollte anonym für das Tracking erfasst werden (siehe Abschnitt 9).
- **Anfrageformular:** Serverseitige Verarbeitung – Validierung, Kategorie-Routing, E-Mail-Versand. Kein Ticketsystem, kein Login.
- **FAQ:** Über das CMS gepflegte Liste, optional nach Kategorie filterbar.
- **Referenzen:** Eigener Content-Typ im CMS, damit Svenja neue Referenzen selbst ergänzen kann.
- **Footer/Standorte:** Global eingebunden (Telefonnummer, Kassel, Göttingen), auf jeder Seite sichtbar.

## 6. Datenmodell (Entwurf, erweiterbar für ein künftiges Partnerportal)

| Objekt | Felder (Beispiel) |
|---|---|
| Anfrage/Lead | Kategorie, Firma, Ansprechpartner, Kontakt, Nachricht, Zeitstempel, Quelle (Formular/Rechner) |
| FAQ-Eintrag | Frage, Antwort, Kategorie |
| Referenz | Kundenname, Branche, Kurzbeschreibung, Freigabestatus |
| Rechner-Nutzung | Radpreis, Bruttogehalt-Spanne, Zeitstempel (anonymisiert, nur für Tracking) |

Das Datenmodell ist bewusst so einfach gehalten, dass eine spätere Partnerportal-Schnittstelle (Login, Bestandsabfrage) ergänzt werden kann, ohne die Website neu aufzubauen – das PRD verlangt ausdrücklich "vorbereiten, nicht bauen".

## 7. Leasing-Rechner – Logik (Platzhalter-Beispiel, mit Radwerk zu bestätigen)

Die echten Leasingkonditionen und Partner liegen laut Umsetzungsplan noch nicht vor. Vorschlag für eine erste, klar als unverbindlich gekennzeichnete Beispiel-Logik:

- **Eingaben:** Radpreis (€), monatliches Bruttogehalt (€).
- **Beispielrechnung:** Monatliche Rate = Radpreis geteilt durch eine angenommene Laufzeit (z. B. 36 Monate) zuzüglich einer pauschalen Versicherungs-/Servicegebühr; ein Hinweistext erklärt, dass die tatsächliche Entlastung durch Gehaltsumwandlung vom individuellen Steuersatz abhängt.
- **Ausgabe:** geschätzte monatliche Belastung, mit dem im PRD geforderten Pflichthinweis "unverbindlich".
- **Empfehlung:** Mit dieser Platzhalterformel starten und sie austauschen, sobald Radwerk echte Leasingraten, Partner und Konditionen liefert – nicht auf vollständige Daten warten, um den Rechner-Launch zu verzögern.

## 8. Nicht-funktionale Anforderungen

- **Responsive/Mobile:** Alle Seiten müssen auf dem Smartphone funktionieren (PRD-Akzeptanzkriterium) – mobile-first umsetzen.
- **Barrierefreiheit:** WCAG 2.2 AA, wie in `radwerk-mitte-design-guideline.md` festgelegt (Kontraste, Fokus-Zustände, Alternativtexte).
- **Performance:** Vom PRD keine konkrete Kennzahl vorgegeben. Vorschlag: Core Web Vitals als Richtwert verwenden und mit Radwerk bestätigen.
- **Datenschutz/DSGVO:** Das Anfrageformular erfasst personenbezogene Daten (Name, Firma, Kontakt). Es braucht eine Datenschutzerklärung, eine Einwilligung und einen sicheren E-Mail-Versand. Wer als Verantwortlicher/Auftragsverarbeiter gilt, ist mit Radwerk zu klären – nicht vorwegnehmen.
- **Sicherheit:** Standard-Absicherung des Formulars (Spam-Schutz, serverseitige Validierung). Kein Login-System in Version 1.

## 9. Analytics und Messbarkeit

Direkt aus Phase 5 des Umsetzungsplans: Tracking für Absprungrate, Formularabschlüsse, Rechnernutzung und B2B-Anfragen pro Monat muss **vor** dem Launch eingerichtet sein, da es heute keine Vergleichswerte gibt.

**Offen:** Welches Analytics-Tool zum Einsatz kommt. Empfehlung als Diskussionsgrundlage: ein datenschutzfreundliches Tool wählen, das ohne aufwändigen Cookie-Consent-Prozess DSGVO-konform läuft – passt zum Ton "zuverlässiger Partner" und reduziert Pflegeaufwand für den einzigen Support-Mitarbeiter.

## 10. Hosting und Betrieb

Bewusst offen bis zum Technik-Gate in Phase 1/3 des Umsetzungsplans. Einzige fixe Anforderung: Svenja Kowalczyk muss Inhalte ohne Entwicklerhilfe pflegen können, und es wird keine neue Support-Software eingeführt (E-Mail-Routing reicht aus).

## 11. Abhängigkeit von offenen Fragen

Diese Spec hängt von denselben offenen Punkten ab, die in `Umsetzungsplan-Radwerk-Mitte.md` (Abschnitt 0 und 1) aufgeführt sind:

- Ergebnis des WordPress-Fragebogens → bestimmt die Technologiewahl (Abschnitt 4).
- Echte Leasing-Konditionen und Partner → bestimmen die finale Rechner-Formel (Abschnitt 7).
- Zeitpunkt eines künftigen Partnerportals → bestimmt, wie generisch das Datenmodell (Abschnitt 6) von Anfang an sein muss.

## 12. Nicht Teil dieser Spec

Entsprechend den PRD-Nicht-Zielen: kein eigener Onlineshop, kein Partnerportal mit Login, kein Custom-Rad-Konfigurator, kein Rebranding, keine neue Support-Software.
