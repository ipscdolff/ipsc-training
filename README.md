# IPSC Træning (PWA) – Underviser-udgave

Multi-skytte IPSC PWA til træningslog: tid, A/C/D, NS, Miss, automatisk **Hit Factor (HF)** og **A%**.  
Denne version har **tema-toggle (☀️/🌙)** og **filtre for skytte, øvelse og dato-interval** i Historik og Statistik.

## Hurtig opsætning på GitHub Pages
1. Opret repo: `ipsc-training` under brugeren **ipscdolff**.
2. Upload **alle filer i roden** (index.html, sw.js, manifest.webmanifest, assets/, CNAME, .nojekyll).
3. Gå til **Settings → Pages** → *Deploy from a branch* → **Branch:** `main`, **Folder:** `/ (root)` → Save.
4. Vent lidt → siden er live.

## Custom domæne: ipsc.dolff.dk
- Filen **CNAME** indeholder allerede: `ipsc.dolff.dk`
- Opret en **CNAME DNS-record** hos din udbyder:
  - **Host/Name:** `ipsc`
  - **Type:** CNAME
  - **Target:** `ipscdolff.github.io`
  - **TTL:** 1h (fx)
- I GitHub repoet → **Settings → Pages**: Angiv `ipsc.dolff.dk` som custom domain.
- Når DNS er slået igennem, vil din app være på `https://ipsc.dolff.dk`.

## Lokal udvikling (valgfrit)
Start en simpel http-server i mappen:
```bash
python -m http.server 8080
# eller
npx http-server -p 8080
```
Åbn `http://localhost:8080` og test. Installer som PWA via browser-menuen.

## Funktioner
- Offline PWA (service worker + cache)
- Gemmer lokalt i **IndexedDB**
- **Skytter**: opret/omdøb/slet (kan ikke slette hvis der er sessions tilknyttet)
- **Filtrér** historik og statistik på: skytte, øvelse, dato-interval
- **Eksport/Import** (JSON) og **CSV-eksport**
- **Backup** inkluderer både sessions og skytte-liste

## Struktur
- `index.html` – UI og logik
- `sw.js` – service worker (offline)
- `manifest.webmanifest` – PWA manifest
- `assets/` – Ikoner
- `CNAME` – Custom domæne (ipsc.dolff.dk)
- `.nojekyll` – Deaktivér Jekyll på GitHub Pages

**GitHub-brugernavn: ipscdolff**
