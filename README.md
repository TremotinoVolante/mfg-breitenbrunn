
...work in progress...

---

# MFG Breitenbrunn – Vereinswebsite

link: `https://tremotinovolante.github.io/mfg-breitenbrunn`

Statische Website des Modellflugvereins MFG Breitenbrunn, gehostet auf GitHub Pages.  
Kein WordPress, kein CMS, kein JavaScript, kein PHP. Nur HTML + CSS.

---

## Struktur

```
mfg-breitenbrunn/
├── index.html       ← die gesamte Seite (eine einzige Datei)
├── style.css        ← alle Styles, ausgelagert
├── README.md        ← diese Datei
├── logo.png         ← Vereinslogo (wird als favicon + Header verwendet)
├── gelaende.jpg     ← Hero-Foto oben auf der Seite
├── gelaende2.jpg    ← Foto in der Gelände-Sektion
├── modell.jpg       ← Foto in der Modellflug-Sektion
└── flugtag.jpg      ← Foto in der Termine-Sektion
```

---

## Inhalte ändern

Alle Texte stehen direkt in `index.html` — einfach im Browser oder im GitHub-Editor öffnen und bearbeiten.  
Jede Sektion hat einen Kommentar `id="..."` der anzeigt wo man ist:

| Was | Wo in index.html |
|-----|-----------------|
| Vereinsname, Gründungsjahr | `<header>` ganz oben |
| Über uns, Mitgliederzahl | `<section id="ueber">` |
| Adresse, Piste, Öffnungszeiten | `<section id="gelaende">` |
| Aktivitäten | `<section id="modelle">` |
| Termine | `<section id="termine">` |
| Mitgliedsbeiträge | `<section id="mitglied">` |
| Vorstandsnamen, E-Mails | `<section id="kontakt">` |
| Registernummer, Adresse | `<section id="impressum">` |

---

## Fotos tauschen

1. Neues Foto vorbereiten: **vorher komprimieren** (Ziel: unter 200 KB)
2. Datei umbenennen — gleicher Name wie die alte (z.B. `gelaende.jpg`) **oder** neuen Namen in `index.html` anpassen
3. Datei ins Repo hochladen (GitHub → „Add file" → „Upload files")
4. Alte Datei löschen falls nötig

Empfohlene Bildgröße: **1800 × 900 px**, Format jpeg.

---

## Farben ändern

Alle Farben stehen als Variablen ganz oben in `style.css`:

```css
:root {
  --bg:     #f4f1ec;   /* Seitenhintergrund */
  --accent: #2d5a3d;   /* Grün: Links, Striche, Überschriften */
  --ink:    #1e1c18;   /* Haupttextfarbe */
  --soft:   #7a7570;   /* Gedämpfte Texte */
}
```

Einen Hex-Wert ändern = überall geändert. Nie Farben direkt in den Komponenten unten ändern.

---

## Änderungen online stellen

1. Datei in GitHub bearbeiten (Stift-Symbol) oder lokal ändern + pushen
2. GitHub Pages baut automatisch neu — dauert ca. 1–2 Minuten
3. Seite im Browser mit **Cmd+Shift+R** (Mac) oder **Ctrl+Shift+R** (Windows) neu laden um den Cache zu leeren

Wenn CSS-Änderungen nicht ankommen: in `index.html` den CSS-Link anpassen:
```html
<link rel="stylesheet" href="style.css?v=3">
```
Die Zahl hochzählen (v=2, v=3 …) zwingt den Browser zur Neuladung.

---

## Karte anpassen

Der Kartenausschnitt steht im `<iframe>` in `<section id="gelaende">`.  
Der Marker ist auf die genauen Koordinaten des Geländes gesetzt.  
Koordinaten ändern: `marker=BREITE%2CLAENGE` im iframe-src und im map-hint-Link.

---

## Technische Details

- Gehostet auf **GitHub Pages** (kostenlos, kein Ablaufdatum)
- Keine Cookies, kein Tracking, kein JavaScript
- Schriften: System-Fonts als Fallback, Google Fonts **nicht** eingebunden (Datenschutz)
- Karte: OpenStreetMap (keine API-Keys nötig)
- DSGVO: GitHub Pages loggt IP-Adressen serverseitig — siehe Datenschutz-Sektion auf der Seite

## Domainname

Aktuell läuft die Seite unter:  
`https://tremotinovolante.github.io/mfg-breitenbrunn/`

Wenn der Verein eine eigene Domain kauft (z.B. `mfg-breitenbrunn.de`):
1. Im Repo unter Settings → Pages → Custom domain eintragen
2. Beim Domain-Anbieter einen CNAME-Eintrag auf `tremotinovolante.github.io` setzen
3. Eine Datei `CNAME` (ohne Endung) ins Repo mit dem Inhalt `mfg-breitenbrunn.de` legen

---

*Erstellt und gepflegt von Gia · Bei Fragen: Gia auf dem Flugplatz ansprechen.

---

© 2026 MFG Breitenbrunn e.V. All rights reserved.

The website source code is available under the MIT License.
Club logos, photographs, and content are not covered by that license.

All club logos, photographs, and written content remain the property of the club and may not be reused without permission.
