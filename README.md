# Eichfelder Eisbären - Website

Willkommen zur offiziellen Website des Vereins Eichfelder Eisbären! Diese Website ist statisch und verwendet HTML, CSS, Bootstrap und JavaScript für ein responsives Design.

## Überblick

Die Website umfasst folgende Seiten:
- **Startseite** (`index.html`): Willkommensnachricht und dynamisch geladene News.
- **Verein** (`verein.html`): Vorstellung des Vereins und Mitglieder mit Fotos.
- **Impressum** (`impressum.html`): Rechtliche Informationen.
- **Unterstützer** (`unterstuetzer.html`): Liste der Sponsoren.
- **Kontakt** (`kontakt.html`): Kontaktdaten.

## Farbschema

Die Vereinsfarben sind Türkis, Schwarz und Weiß:
- Navbar: Türkis
- Footer: Schwarz
- Text: Weiß auf dunklen Hintergründen
 
## Lokale Entwicklung

### Server starten
Um die Website lokal zu testen, starten Sie einen HTTP-Server im Projektverzeichnis:

```bash
cd /Users/christophhodl/Documents/eichfelderEisbären
python3 -m http.server 8000
```

Öffnen Sie dann http://localhost:8000 in Ihrem Browser.

### Dateistruktur
```
/Users/christophhodl/Documents/eichfelderEisbären/
├── index.html          # Startseite
├── verein.html         # Vereinsseite
├── impressum.html      # Impressum
├── unterstuetzer.html  # Unterstützer
├── kontakt.html        # Kontakt
├── style.css           # Zusätzliche Styles
├── news/               # News-Ordner
│   ├── index.json      # Liste der News-Dateien mit Metadaten
│   └── *.md            # Markdown-News-Dateien
└── bilder/             # Bilder-Ordner
    └── *.png/jpg       # Bilder für News und Mitglieder
```

## News hinzufügen

News werden als Markdown-Dateien im `news/` Ordner gespeichert und dynamisch geladen.

### Schritte:
1. **Markdown-Datei erstellen**: Erstellen Sie eine neue `.md`-Datei im `news/` Ordner, z.B. `260108_NeueNews.md`. Verwenden Sie das Format:
   ```
   # Titel der News
   ## Untertitel
   Text hier.

   [bild.png]  # Für Bilder
   ```
2. **index.json aktualisieren**: Fügen Sie ein neues Objekt zur `news/index.json` hinzu:
   ```json
   {
     "file": "260108_NeueNews.md",
     "created": "2026-01-08T12:00:00",
     "author": "Ihr Name"
   }
   ```
   Sortieren Sie die Liste nach Bedarf (z.B. neueste zuerst).
3. **Bilder hinzufügen**: Platzieren Sie Bilder im `bilder/` Ordner und referenzieren Sie sie in Markdown mit `[bildname.png]`.

### Beispiel-News
Siehe `news/260106_Erstellen.md` und `news/260107_NeueMitglieder.md`.

## Mitglieder bearbeiten

Auf der Vereinsseite (`verein.html`) werden Mitglieder als Bootstrap-Karten angezeigt.

### Schritte:
- Bearbeiten Sie den HTML-Code in `verein.html` im Abschnitt "Unsere Mitglieder".
- Fügen Sie neue `<div class="col-md-4 mb-4">`-Blöcke mit Karten hinzu.
- Beispiel:
  ```html
  <div class="col-md-4 mb-4">
      <div class="card">
          <img src="bilder/mitglied.jpg" class="card-img-top" alt="Name">
          <div class="card-body">
              <h5 class="card-title">Name</h5>
              <p class="card-text">Rolle</p>
              <p>Beschreibung</p>
          </div>
      </div>
  </div>
  ```

## Styles anpassen

- **CSS**: Bearbeiten Sie `style.css` für Farben, Schriftarten usw.
- **Bootstrap**: Die Website verwendet Bootstrap 5. Ändern Sie Klassen in den HTML-Dateien für Layout-Änderungen.
- **Farben**: Die CSS-Variablen in `:root` können angepasst werden.

## Deployment

Da es eine statische Website ist, können Sie sie auf jedem Webserver hosten (z.B. GitHub Pages, Netlify). Laden Sie einfach alle Dateien hoch.

## Pflege-Tipps

- **Regelmäßige Updates**: Aktualisieren Sie News und Mitglieder regelmäßig.
- **Bilder optimieren**: Verwenden Sie komprimierte Bilder für bessere Ladezeiten.
- **Backup**: Sichern Sie den gesamten Ordner regelmäßig.
- **Browser-Test**: Testen Sie auf verschiedenen Geräten und Browsern.

Bei Fragen oder Problemen wenden Sie sich an den Entwickler oder den Vereinsvorstand.