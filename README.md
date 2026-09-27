# Cambia Sfondo

Web app (PWA) con tre pulsanti che cambiano il colore dello sfondo.
Ricorda l'ultimo colore scelto, colora la barra del browser, si installa sulla schermata Home e funziona offline.

## File

| File | A cosa serve |
|---|---|
| `index.html` | L'app (HTML, CSS e JS in un unico file) |
| `manifest.json` | Nome, colori e icone per l'installazione |
| `service-worker.js` | Cache dei file per il funzionamento offline |
| `icons/` | Icone dell'app (favicon, 192, 512, maskable, Apple) |

## Pubblicazione

### Opzione A: Netlify Drop (la più veloce)
1. Vai su https://app.netlify.com/drop
2. Trascina l'intera cartella `cambia-sfondo`.
3. Ottieni subito un link `https://….netlify.app`.

### Opzione B: GitHub Pages
1. Crea un repository su GitHub (es. `cambia-sfondo`).
2. Carica **il contenuto** della cartella (`index.html` deve stare nella radice del repository).
3. Apri **Settings → Pages**, poi imposta *Source: Deploy from a branch*, branch `main` e cartella `/ (root)`.
4. Dopo circa un minuto l'app è su `https://<tuo-utente>.github.io/cambia-sfondo/`.

## Installazione sul telefono
- **Android (Chrome)**: apri il link, poi menu ⋮ → *Installa app* (o *Aggiungi a schermata Home*).
- **iPhone (Safari)**: apri il link, poi *Condividi* → *Aggiungi a Home*.

## Prova in locale
Il service worker non funziona aprendo il file con doppio clic (`file://`). Serve un piccolo server:

```bash
cd cambia-sfondo
python3 -m http.server 8000
# poi apri http://localhost:8000
```

## Aggiornare l'app
Dopo ogni modifica, cambia `CACHE = 'cambia-sfondo-v1'` in `service-worker.js`
(es. `v2`): così chi l'ha installata riceve la nuova versione.
