# Sito ODOARDO

Sito personale di Odoardo Vitolo, pubblicato su [odoardovitolo.it](https://odoardovitolo.it).

Il sito è fatto con [Astro](https://astro.build) e viene pubblicato da Netlify a ogni modifica approvata sul ramo `main`.

## Come si modifica

1. Chiedi la modifica a Claude, che prepara le modifiche su un ramo separato e apre una richiesta di modifica (pull request).
2. Netlify crea un link di anteprima: controlla lì come viene la modifica.
3. Se va bene, approvi la richiesta su GitHub e la unisci: solo allora la modifica va online.

Ogni pubblicazione sul sito reale consuma crediti Netlify, le anteprime no. Conviene raccogliere più modifiche in una sola pubblicazione.

## Dove stanno le cose

| Cosa | File |
|---|---|
| Home (testi, sezioni, modulo, footer) | `src/pages/index.astro` |
| Numero di P.IVA nel footer | `src/pages/index.astro`, riga `const PIVA = ''` |
| Informativa privacy e cookie | `src/pages/privacy.astro` |
| Pagina dopo l'invio del modulo | `src/pages/grazie.astro` |
| Colori, tema scuro e versione smartphone | `src/styles/site.css` |
| Titolo, descrizione e anteprima per WhatsApp e LinkedIn | `src/layouts/Base.astro` |
| Foto, logo e immagine di anteprima | `public/` |

## Impostazioni su Netlify

- **Build:** `npm run build`, cartella da pubblicare `dist` (già scritto in `netlify.toml`).
- **Modulo contatti:** si chiama `contatti` e viene riconosciuto da Netlify Forms. Le notifiche email si attivano in *Forms → Form notifications*.
- **Statistiche (Umami, senza cookie):** si attivano aggiungendo la variabile d'ambiente `PUBLIC_UMAMI_WEBSITE_ID` con il codice del sito preso da Umami. Senza la variabile lo script non viene caricato. I click su pulsanti, casi e contatti sono già etichettati con `data-umami-event`.

## Regole

- Il repository è pubblico: non caricare dati riservati, numeri reali non pubblicabili, bozze o foto non anonimizzate.
- I numeri pubblicati vengono solo dalla Bussola Portfolio.

## Comandi per chi sviluppa

```
npm install
npm run dev      # sito in locale su http://localhost:4321
npm run build    # crea la versione pubblicabile in dist/
```
