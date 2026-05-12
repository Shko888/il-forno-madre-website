# TODO — Il Forno Madre Website

## Priorità alta

- [ ] **Collegare dominio Register.it a Vercel**  
  Configurare A record (`76.76.21.21`) e CNAME (`www → cname.vercel-dns.com`).  
  Vedi `skills/DEPLOY.md` per la procedura completa.

- [ ] **Aggiungere link alla piattaforma B2B**  
  Inserire nella sezione "Per professionisti" un CTA che rimandi a `il-forno-madre.vercel.app`.  
  Valutare se usare il dominio definitivo della B2B app.

- [ ] **Sostituire immagini Unsplash con foto reali dei prodotti**  
  Le immagini attuali sono placeholder da Unsplash.  
  Foto necessarie: pizza al taglio, basi pizza, focacce, laboratorio/forno, dettaglio impasto.  
  Ottimizzare in WebP, max 200KB per immagine.

## Priorità media

- [ ] **Google Analytics 4**  
  Aggiungere il tag GA4 nell'`<head>` per tracciare visite, provenienza e comportamento.

- [ ] **Google Search Console**  
  Verificare il dominio, inviare sitemap, monitorare indicizzazione.  
  Vedi `skills/SEO.md` per la procedura.

- [ ] **Aggiungere meta tag Open Graph e Schema.org LocalBusiness**  
  Migliora la condivisione social e la visibilità nelle ricerche locali.  
  Il codice completo è in `skills/SEO.md`.

- [ ] **Aggiungere robots.txt e sitemap.xml**  
  File necessari per l'indicizzazione corretta.

- [ ] **Tag canonical**  
  Da aggiungere dopo il collegamento del dominio.

## Priorità bassa

- [ ] **Pagina /ordini che rimanda alla B2B app**  
  Semplice pagina di redirect o interstitial che spiega la piattaforma B2B  
  e reindirizza i professionisti all'app per gli ordini.

- [ ] **Favicon e og:image**  
  Creare favicon SVG basato sul segno del marchio (cerchio con taglio).  
  Creare og:image 1200×630px per la condivisione social.

- [ ] **Google Business Profile**  
  Creare o rivendicare il profilo Google Maps per "Il Forno Madre Racconigi".

- [ ] **Cookie banner**  
  Necessario se si aggiunge GA4 o altri tracker.  
  Soluzione leggera, senza librerie pesanti.
