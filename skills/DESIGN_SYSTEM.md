# Design System — Il Forno Madre

## Palette colori

Definita come CSS custom properties in `:root`. Non modificare questi valori.

| Token | Valore | Nome editoriale | Uso |
|---|---|---|---|
| `--paper` | `#fffaf2` | Carta | Background principale |
| `--cream` | `#f4ecdf` | Crema | Background secondario, gradienti hero |
| `--flour` | `#fbf6ed` | Farina | Background sezioni alternate (manifesto, professionisti) |
| `--ink` | `#241b16` | Inchiostro | Testo principale, heading, sezione prodotti |
| `--charcoal` | `#17120f` | Carbone | Background sezione brand (dark) |
| `--muted` | `#75675c` | Muto | Testo corpo, paragrafi, dettagli |
| `--terracotta` | `#9a4f35` | Terracotta | Eyebrow, accenti, sigillo brand |
| `--copper` | `#b9825a` | Rame | Eyebrow su sfondi scuri |
| `--olive` | `#6f7157` | Oliva | Quarto colore palette (uso decorativo) |
| `--line` | `rgba(36, 27, 22, 0.13)` | Linea | Bordi, separatori su fondo chiaro |
| `--white-line` | `rgba(255, 250, 242, 0.16)` | Linea chiara | Bordi su sfondi scuri |
| `--shadow` | `0 26px 80px rgba(36, 27, 22, 0.12)` | Ombra | Card principali |

## Tipografia

### Font

- **Heading / Display**: Cormorant Garamond — pesi 400, 500, 600, 700
- **Body / UI**: Inter — pesi 300, 400, 500, 600, 700

```css
font-family: "Cormorant Garamond", serif;  /* h1, h2, h3, .display-logo, .quote-card p */
font-family: "Inter", sans-serif;           /* tutto il resto */
```

### Scale tipografica

| Elemento | Dimensione | Note |
|---|---|---|
| `h1` | `clamp(62px, 8.5vw, 132px)` | Line-height 0.98, letter-spacing -0.045em |
| `h2` | `clamp(44px, 5.4vw, 82px)` | Margin-bottom 24px |
| `h3` | `clamp(30px, 3vw, 46px)` | Margin-bottom 14px |
| `.display-logo` | `clamp(56px, 6vw, 92px)` | Cormorant Garamond |
| `.lead` | `clamp(18px, 2vw, 22px)` | Line-height 1.65, colore muted |
| `p` (corpo) | `17px` | Colore muted |
| `.eyebrow` | `11px` | Uppercase, letter-spacing 0.2em, peso 700, terracotta |
| `.btn-line` | `12px` | Uppercase, letter-spacing 0.12em, peso 700 |
| `footer` | `13px` | Colore muted |

### Principi tipografici

- Heading sempre in Cormorant Garamond con letter-spacing negativo (`-0.045em`)
- Line-height heading: `0.98` — quasi nessun interlinea
- Body in Inter con line-height `1.55`
- Eyebrow sempre uppercase con ampio letter-spacing (`0.2em`)

## Layout

- Container: `width: min(1180px, calc(100% - 40px)); margin: 0 auto`
- Sezioni: `padding: 118px 0` (desktop), `86px 0` (tablet)
- Breakpoint principale: `980px`
- Breakpoint mobile: `560px`

## Componenti principali

### Navigation
```css
position: fixed; top: 0; z-index: 30;
background: linear-gradient(to bottom, rgba(255,250,242,0.95), rgba(255,250,242,0));
backdrop-filter: blur(10px);
```

### Card prodotti (hover)
```css
transition: transform 1s ease;
/* hover */ transform: scale(1.045);
```

### Button `.btn-line`
```css
padding-bottom: 7px;
border-bottom: 1px solid var(--ink);
```

### Border-radius scale
| Uso | Valore |
|---|---|
| Card piccole | `26–28px` |
| Card medie | `30–34px` |
| Card grandi / sezioni | `38–42px` |

## Regole CSS da rispettare

1. Usare esclusivamente i token CSS definiti in `:root` — no colori hardcoded
2. Non aggiungere font diversi da Cormorant Garamond e Inter
3. Mantenere molto spazio bianco — padding generosi, non riempire
4. Ogni modifica CSS deve essere verificata su viewport 375px
5. Non toccare le transizioni `hover::after` sulle card prodotti
6. Mantenere la gerarchia heading → lead → body → eyebrow
