# Deploy — Collegamento dominio Register.it a Vercel

## Situazione attuale

Il sito è deployato su Vercel all'indirizzo `il-forno-madre.vercel.app`.  
Il dominio `ilfornomadre.it` è registrato su Register.it e va collegato a Vercel.

## Procedura

### 1. Aggiungere il dominio su Vercel

1. Accedi a [vercel.com](https://vercel.com) → seleziona il progetto `il-forno-madre`
2. Vai su **Settings → Domains**
3. Aggiungi `ilfornomadre.it` e `www.ilfornomadre.it`
4. Vercel mostrerà i record DNS da configurare

### 2. Configurare i DNS su Register.it

Accedi al pannello Register.it → **Gestione DNS** del dominio `ilfornomadre.it`.

#### Record per il dominio apex (`ilfornomadre.it`)

Vercel richiede un **A record** (non supporta ALIAS sul dominio apex su tutti i registrar):

```
Tipo:  A
Nome:  @ (o lascia vuoto per il dominio radice)
Valore: 76.76.21.21
TTL:   3600 (o "Automatico")
```

> Il valore `76.76.21.21` è l'IP statico di Vercel per i domini apex.  
> Verifica sempre l'IP corrente nel pannello Vercel del tuo progetto.

#### Record per il sottodominio www (`www.ilfornomadre.it`)

```
Tipo:  CNAME
Nome:  www
Valore: cname.vercel-dns.com.
TTL:   3600
```

> Il punto finale in `cname.vercel-dns.com.` è parte del valore — includilo se Register.it lo richiede.

### 3. Verifica su Vercel

- Dopo aver salvato i DNS su Register.it, torna su Vercel → Settings → Domains
- Vercel controllerà automaticamente la propagazione
- Quando il dominio è verificato apparirà il badge verde "Valid Configuration"

### 4. HTTPS

Vercel emette automaticamente il certificato SSL tramite Let's Encrypt. Non è necessaria nessuna configurazione manuale.

## Tempi di propagazione DNS

| Scenario | Tempo atteso |
|---|---|
| Propagazione minima | 15–30 minuti |
| Propagazione normale | 1–4 ore |
| Propagazione massima (worst case) | Fino a 48 ore |

In pratica con Register.it la propagazione avviene di solito entro 1–2 ore.

Per verificare la propagazione: [dnschecker.org](https://dnschecker.org) → inserisci `ilfornomadre.it` e controlla il record A.

## Redirect www → apex (o viceversa)

Vercel gestisce automaticamente il redirect tra `www.ilfornomadre.it` e `ilfornomadre.it`.  
Nel pannello Vercel → Domains, imposta quale versione è quella **primaria** — l'altra verrà reindirizzata con 308.

## Note

- Non eliminare i record DNS esistenti di Register.it prima di verificare che non siano in uso (email, ecc.)
- Se Register.it non supporta il record A con IP Vercel, valutare la migrazione dei nameserver a Cloudflare (gratis, propagazione più rapida)
