# Asta Fantacalcio 2026/27 — deploy su Railway

Web-app per gestire l'asta del fantacalcio. Gira come pagina web: la apri da un link
in Safari (anche sull'iPad), i dati si salvano localmente sul dispositivo.

## Cosa c'è dentro
- `index.html` — la web-app completa (tutto in un file, funziona anche offline una volta caricata)
- `server.js` — micro-server statico Node, nessuna dipendenza
- `package.json` — dice a Railway come avviare (`npm start`)
- `railway.json` — config di deploy

## Deploy su Railway (2 minuti)

### Metodo A — da GitHub (consigliato)
1. Metti questa cartella in un repo GitHub.
2. Su Railway: **New Project → Deploy from GitHub repo** → scegli il repo.
3. Railway rileva Node da solo, builda e avvia. Fine.
4. In **Settings → Networking → Generate Domain** ottieni l'URL pubblico (es. `https://xxx.up.railway.app`).

### Metodo B — da CLI
```bash
npm i -g @railway/cli
railway login
railway init
railway up
railway domain   # genera l'URL pubblico
```

## Usare l'app sull'iPad
1. Apri l'URL Railway in **Safari** (scheda normale, NON navigazione privata).
2. Facoltativo ma comodo: **Condividi → Aggiungi a Home** per averla come un'app con icona.
3. Imposta budget e modificatore, poi durante l'asta scrivi i prezzi pagati.

## Nota importante
Railway qui serve SOLO a ospitare la pagina. I dati dell'asta restano salvati
in locale sul tuo iPad (localStorage), esattamente come nella versione a file.
Non c'è database: se cambi dispositivo, esporta/importa il backup dalle impostazioni.

## Costo
È una pagina statica leggerissima: il consumo su Railway è minimo. Se vuoi, dopo
l'asta puoi mettere in pausa o eliminare il servizio.
