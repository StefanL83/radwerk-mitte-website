# Website-Entwurf (Snapshot)

Diese Datei (`Main.dc.html`) ist eine Sicherung des aktuellen Stands des interaktiven Website-Entwurfs für Radwerk Mitte, Stand 20.10.2026.

Live-Version (interaktiv, bearbeitbar): https://claude.ai/artifact/3zsmkVGSzNwf8XwUq1YJmA

## Hinweis zum Format

`Main.dc.html` ist der interne Quellcode des Claude-"Design"-Canvas-Tools, kein eigenständig lauffähiges HTML. Er enthält:

- `{{platzhalter}}`-Templating für dynamische Werte (z. B. Leasing-Rechner, FAQ-Toggles)
- Eine eingebettete Komponenten-Logik (`class Component extends DCLogic`)
- Ein `<script src="./support.js">`, das nur innerhalb des Canvas-Tools existiert

Diese Datei dient als Backup/Versionsstand des Designs (Struktur, Texte, Styles), nicht als einsatzbereiter Code für die technische Umsetzung. Für die echte Implementierung siehe `Tech-Spec-Radwerk-Mitte.md`.
