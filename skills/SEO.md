# SEO — Il Forno Madre

## Meta tag presenti (v1.0)

```html
<title>Il Forno Madre — Il tempo è il nostro ingrediente</title>

<meta name="description"
  content="Il Forno Madre è un laboratorio artigianale contemporaneo di pizza al taglio,
  basi pizza, focacce e prodotti da forno leggeri, digeribili e lavorati lentamente." />
```

**Lingua**: `<html lang="it">` — corretto per Google Italia.  
**Charset**: UTF-8.  
**Viewport**: impostato correttamente per mobile.

## Valutazione meta tag attuali

| Tag | Stato | Note |
|---|---|---|
| `<title>` | ✅ Buono | 55 caratteri, include nome + claim |
| `<meta description>` | ✅ Buono | 158 caratteri, descrittiva e pertinente |
| Open Graph | ❌ Mancante | Necessario per condivisione social |
| Twitter Card | ❌ Mancante | |
| Canonical | ❌ Mancante | Da aggiungere dopo collegamento dominio |
| Favicon / og:image | ❌ Mancante | |
| Schema.org (JSON-LD) | ❌ Mancante | Fondamentale per Local SEO |
| Google Search Console | ❌ Non verificato | |
| Sitemap.xml | ❌ Mancante | |
| robots.txt | ❌ Mancante | |

## Suggerimenti prioritari

### 1. Aggiungere Open Graph e Twitter Card

```html
<!-- Open Graph -->
<meta property="og:type" content="website" />
<meta property="og:title" content="Il Forno Madre — Il tempo è il nostro ingrediente" />
<meta property="og:description" content="Laboratorio artigianale di pizza al taglio, basi pizza e focacce a Racconigi (CN). Impasti lenti, gusto pieno, morso leggero." />
<meta property="og:url" content="https://www.ilfornomadre.it" />
<meta property="og:image" content="https://www.ilfornomadre.it/og-image.jpg" />
<meta property="og:locale" content="it_IT" />

<!-- Twitter Card -->
<meta name="twitter:card" content="summary_large_image" />
<meta name="twitter:title" content="Il Forno Madre — Il tempo è il nostro ingrediente" />
<meta name="twitter:description" content="Laboratorio artigianale di pizza al taglio a Racconigi. Impasti lenti, leggerezza vera." />
<meta name="twitter:image" content="https://www.ilfornomadre.it/og-image.jpg" />
```

### 2. Aggiungere Schema.org LocalBusiness (JSON-LD)

Fondamentale per apparire nelle ricerche locali "pizza al taglio Racconigi" e nel Knowledge Panel di Google.

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Bakery",
  "name": "Il Forno Madre",
  "description": "Laboratorio artigianale di pizza al taglio, basi pizza e focacce a Racconigi.",
  "url": "https://www.ilfornomadre.it",
  "telephone": "+393484214626",
  "email": "info@ilfornomadre.it",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "Via Augusto Levis n. 10",
    "addressLocality": "Racconigi",
    "postalCode": "12030",
    "addressRegion": "CN",
    "addressCountry": "IT"
  },
  "servesCuisine": "Pizza al taglio",
  "slogan": "Il tempo è il nostro ingrediente"
}
</script>
```

### 3. Tag canonical

Da aggiungere dopo il collegamento del dominio per evitare duplicati Vercel/dominio:

```html
<link rel="canonical" href="https://www.ilfornomadre.it" />
```

### 4. Google Search Console

1. Accedere a [search.google.com/search-console](https://search.google.com/search-console)
2. Aggiungere proprietà `https://www.ilfornomadre.it`
3. Verificare tramite tag HTML o record DNS
4. Inviare sitemap

### 5. robots.txt

Creare il file `/robots.txt` nella root:

```
User-agent: *
Allow: /

Sitemap: https://www.ilfornomadre.it/sitemap.xml
```

### 6. Sitemap.xml

Per ora è una pagina singola — sitemap minimale:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://www.ilfornomadre.it</loc>
    <changefreq>monthly</changefreq>
    <priority>1.0</priority>
  </url>
</urlset>
```

### 7. Ottimizzare le immagini

Le immagini attuali provengono da Unsplash — vanno sostituite con foto reali dei prodotti.  
Quando si aggiungono immagini proprie, includere sempre attributo `alt` descrittivo:

```html
<img src="pizza-al-taglio.jpg" alt="Pizza al taglio Il Forno Madre — impasto a lunga maturazione" />
```

## Keyword target

| Keyword | Volume stimato | Priorità |
|---|---|---|
| pizza al taglio Racconigi | Basso (locale) | Alta |
| forno artigianale Racconigi | Basso (locale) | Alta |
| basi pizza artigianali B2B | Medio | Media |
| pizza al taglio Cuneo | Medio | Media |
| focacce artigianali Piemonte | Basso | Bassa |
