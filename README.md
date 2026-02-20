# Broken Crown – Website Deployment Guide

## Dateistruktur
```
broken-crown/
├── index.html          ← Landing Page
├── editor/
│   └── index.html      ← Tile Designer
├── CNAME               ← Domain-Config (wird automatisch erstellt)
└── README.md           ← Diese Datei
```

## Schritt 1: GitHub Repository erstellen

1. Geh zu https://github.com/new
2. Repository Name: `broken-crown`
3. Public auswählen
4. "Add a README file" NICHT ankreuzen
5. "Create repository" klicken

## Schritt 2: Dateien hochladen

### Option A: Über die GitHub-Webseite (einfachster Weg)
1. Im neuen Repository auf "uploading an existing file" klicken
2. Beide HTML-Dateien + dieses README hochladen:
   - `index.html` (Landing Page)
   - Ordner `editor/` mit `index.html` (Tile Designer)
3. "Commit changes" klicken

### Option B: Per Git (wenn installiert)
```bash
cd C:/Users/momom/Documents/
git clone https://github.com/DEIN-USERNAME/broken-crown.git
cd broken-crown

# Dateien reinkopieren (index.html + editor/index.html)
# Dann:
git add .
git commit -m "Initial website"
git push origin main
```

## Schritt 3: GitHub Pages aktivieren

1. Im Repository → **Settings** (oben rechts)
2. Links im Menü → **Pages**
3. Source: **Deploy from a branch**
4. Branch: **main** / Ordner: **/ (root)**
5. **Save** klicken
6. Nach 1-2 Minuten ist die Seite live unter:
   `https://DEIN-USERNAME.github.io/broken-crown/`

## Schritt 4: Domain kaufen

### Empfohlene Registrare (günstigste für .gg):
- **Porkbun** (porkbun.com) – ca. $18/Jahr, sehr günstig
- **Namecheap** (namecheap.com) – ca. $20/Jahr
- **Cloudflare** (cloudflare.com) – Zum Einkaufspreis, kein Aufschlag

### Domain-Optionen:
- `brokencrown.gg` – Ideal, Gaming-TLD
- `brokencrown.game` – Alternative
- `brokencrown.io` – Tech/Indie-Vibes
- `playbc.gg` – Kurz und knapp

### So kaufst du (Beispiel Porkbun):
1. Geh zu porkbun.com
2. Suche nach `brokencrown.gg`
3. In den Warenkorb → Checkout
4. Account erstellen, bezahlen (Kreditkarte/PayPal)

## Schritt 5: Domain mit GitHub Pages verbinden

### A) Bei GitHub:
1. Repository → Settings → Pages
2. Unter "Custom domain": `brokencrown.gg` eingeben
3. Save klicken
4. "Enforce HTTPS" aktivieren

### B) Beim Domain-Registrar (DNS-Einstellungen):
Füge diese DNS-Records hinzu:

**Für Apex-Domain (brokencrown.gg):**
```
Type: A
Name: @
Value: 185.199.108.153

Type: A
Name: @
Value: 185.199.109.153

Type: A
Name: @
Value: 185.199.110.153

Type: A
Name: @
Value: 185.199.111.153
```

**Für www-Subdomain:**
```
Type: CNAME
Name: www
Value: DEIN-USERNAME.github.io
```

### C) CNAME-Datei:
GitHub erstellt automatisch eine `CNAME`-Datei im Repository.
Falls nicht, erstelle sie manuell mit dem Inhalt:
```
brokencrown.gg
```

### D) Warten:
DNS-Propagation dauert 5 Minuten bis 24 Stunden.
Danach ist deine Seite unter `https://brokencrown.gg` erreichbar!

## Ergebnis

Nach diesen Schritten hast du:
- ✅ `brokencrown.gg` → Landing Page
- ✅ `brokencrown.gg/editor/` → Tile Designer
- ✅ HTTPS automatisch durch GitHub
- ✅ Kostenlos gehostet (nur Domain-Kosten)
- ✅ Updates durch Git Push

## Nächste Schritte

- Discord Server erstellen → Link in Footer einfügen
- Twitter/X Account: @BrokenCrownGame
- Tile Designer mit Synty-GLBs testen
- Screenshot/Trailer für die Landing Page erstellen
- Devlog/Blog als weitere Unterseite
