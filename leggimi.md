# OMG TV & OMG+ TV - Stremio Addon

[🇬🇧 Read in english](readme.md)

Un add-on per Stremio per aggiungere al catalogo playlist di canali M3U con EPG (IPTV).
Per la versione PLUS con supporto per playlist personalizzate, visita: https://github.com/mccoy88f/OMG-Plus-TV-Stremio-Addon

⚠️⚠️⚠️ **MOLTO IMPORtANte! LA NUOVA VERSIONE RIBRANDIZZATA E AGGIORNATA FEB 2025 E' ARRIVATA!:**
Questa repo verrà abbandonata e poi chiusa!
https://www.reddit.com/r/Stremio_Italia/comments/1j0h44x/tv_su_stremio_omg_premium_tv_m3u_playlist_addon/
NUOVA REPO: https://github.com/mccoy88f/OMG-Premium-TV

IMPORTANTE: Prima di tutto...

<a href="https://www.buymeacoffee.com/mccoy88f"><img src="https://img.buymeacoffee.com/button-api/?text=Offrimi una birra&emoji=🍺&slug=mccoy88f&button_colour=FFDD00&font_colour=000000&font_family=Bree&outline_colour=000000&coffee_colour=ffffff" /></a>

[Puoi anche offrirmi una birra con PayPal 🍻](https://paypal.me/mccoy88f?country.x=IT&locale.x=it_IT)

## 🌟 Funzionalità Principali

### Core
- Visualizzazione dei canali per categorie
- Ricerca dei canali per nome
- Ordinamento automatico per numero di canale
- Cache dei dati con aggiornamento automatico
- Supporto per playlist multiple
- Gestione automatica degli stream duplicati
- Cache intelligente con aggiornamento automatico ogni 12 ore

### EPG (Electronic Program Guide)
- Supporto EPG con informazioni dettagliate
- Visualizzazione del programma in onda
- Lista dei prossimi programmi
- Supporto per EPG multiple
- Sistema di remapping degli ID canali
- Cache EPG con aggiornamento automatico ogni 12 ore
- Supporto per file EPG compressi (gz)

### Streaming
- Supporto diretto per stream HLS
- Supporto per stream DASH MPD non criptati
- Integrazione con MediaFlow Proxy
- Gestione degli User-Agent personalizzati
- Gestione Header personalizzati per ogni stream

## 🚀 Opzioni di Deployment

### 1. Deploy su Render.com
[![Deploy to Render](https://render.com/images/deploy-to-render-button.svg)](https://render.com/deploy?repo=https://github.com/mccoy88f/OMG-plus-TV-Stremio-Addon)

1. Clicca sul pulsante sopra (richiede un account Render)
2. Seleziona il branch 'main' (usa le altre solo per test)
3. Configura le variabili d'ambiente necessarie

### 2. Deploy su Hugging Face
1. Crea un nuovo Space su Hugging Face
2. Seleziona "Docker" come template
3. Usa il Dockerfile fornito (Dockerfile.hf in questa repo)
4. Configura le variabili d'ambiente nelle impostazioni dello Space

## 🛠️ Configurazione Variabili d'Ambiente

### Configurazione Base
- `M3U_URL`: URL della playlist M3U (solo versione Plus)
  - Supporta sia singola playlist che file con lista di URL
  - Default: URL hardcoded nella versione base
  
- `EPG_URL`: URL della guida EPG (solo versione Plus)
  - Supporta sia singolo file EPG che file con lista di URL
  - Supporta file .gz compressi
  - Default: URL hardcoded nella versione base

- `ID_SUFFIX`: Suffisso per gli ID canali
  - Esempio: 'it' aggiungerà .it agli ID canali senza ID
  - Se non impostata o vuota, non verrà aggiunto alcun suffisso
  - Non ha valore di default

### Configurazione EPG
- `ENABLE_EPG`: Attiva/disattiva EPG 
  - Valori: 'no' per disattivare
  - Default: attivo
  
- `TIMEZONE_OFFSET`: Offset del fuso orario per EPG
  - Formato: '+1:00' o '-2:00'
  - Default: '+1:00'

### Configurazione Proxy
- `PROXY_URL`: URL del MediaFlow Proxy
  - Opzionale
  - Necessario per alcuni dispositivi/browser

- `PROXY_PASSWORD`: Password per il proxy
  - Richiesta se PROXY_URL è impostato

- `FORCE_PROXY`: Forza l'uso del proxy
  - Valori: 'yes' per attivare
  - Rimuove gli stream diretti quando attivo

### Configurazione Deployment
- `PORT`: Porta del server
  - Render.com: Default 10000
  - Hugging Face: Default 7860
  
- `HOST`: Host del server
  - Hugging Face: Default '0.0.0.0'

- `BRANCH`: Branch del repository
  - Valore: main (use le altre solo per test)
  - Usato nel deployment su Hugging Face

## 🔄 Changelog

### v3.3.0
- Migliorato il remapping
- Gestione di categorie/generi multipli per lo stesso canale se definito nella playlist m3u
- Miglior abbinamento dell'epg, ora tutti i confronti sono fatti in minuscolo (ovunque)

### v3.2.0
- Aggiunto supporto per file EPG compressi
- Aggiunta variabile ID_SUFFIX per personalizzare ID canali
- Migliorata gestione timezone EPG
- Ottimizzazione cache e performance
- Supporto per deploy su Hugging Face
- Fix minori e miglioramenti stabilità

### v3.0.0
- Gestione EPG migliorata
- Supporto stream DASH MPD
- Sistema di remapping ID canali
- Supporto per deployment su Hugging Face

### v2.5.0
- Gestione multiplaylist e multi-EPG
- Miglioramento gestione generi/gruppi
- Unificazione canali con stesso ID
- Supporto per EPG di grandi dimensioni

## ⚠️ Note Importanti
- EPG superiori a 5/7 MB potrebbero causare problemi su Render.com
- Su Render.com, usa [uptime robot](https://uptimerobot.com/) per evitare lo standby del server
- Alcuni stream potrebbero richiedere il proxy per funzionare su certi dispositivi
- La cache viene aggiornata automaticamente ogni 12 ore

## 📦 Installazione Locale

1. Clona il repository
```bash
git clone https://github.com/mccoy88f/OMG-TV-Stremio-Addon.git
```

2. Installa le dipendenze
```bash
npm install
```

3. Avvia l'addon
```bash
npm start
```

## 👏 Ringraziamenti
- FuriousCat per l'idea del nome OMG
- Team di [Stremio Italia](https://www.reddit.com/r/Stremio_Italia/)
- Comunità Telegram [Stremio ITA](https://t.me/Stremio_ITA)
- Iconic Panda per l'[icona](https://www.flaticon.com/free-icon/tv_18223703?term=tv&page=1&position=2&origin=tag&related_id=18223703)

## 📜 Licenza
Progetto rilasciato sotto licenza MIT.

## ⚠️ Disclaimer
- Non sono responsabile per l'uso illecito dell'addon
- Contenuti forniti da terze parti
- Nessuna garanzia sulla disponibilità dei canali
