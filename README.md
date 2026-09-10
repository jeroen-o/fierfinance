# Handoff: FierFinance.nl — website concept (Modernist)

## Overview
Eén-pagina websiteconcept voor Fier Finance, de formule van zelfstandige, lokale financiële kantoren (hypotheken, verzekeringen, kredieten, bankzaken, makelaardij, volmacht). Doel: het merkgevoel "fier" (trots zonder opschepperij, rechtop staan) vertalen naar een strakke, modernistische site met één rood accent, zichtbaar raster en 2px-lijnen. Bevat ook het gekozen logo (richting 1c: rode F in een vierkant).

## Direct online zetten (GitHub Pages)
`index.html` in de root is een **zelfstandige, werkende versie** van de Modernist-site (alle stijlen, scripts, logo's en de foto zitten erin gebundeld). Push deze map als repo-root en zet GitHub Pages aan (Settings → Pages → branch `main`, folder `/`). De site staat dan meteen live. De bestanden in `design/` zijn de bewerkbare bron voor een developer die de site nabouwt.

## About the Design Files
De bestanden in `design/` zijn **design-referenties in HTML** — prototypes die look & gedrag tonen, geen productiecode. De opdracht is deze ontwerpen **na te bouwen in de doelomgeving** (Next.js/React, Astro, WordPress-thema, …) met de daar gebruikelijke patterns. Bestaat er nog geen omgeving: kies een statische-site-framework (bv. Astro of Next.js) en implementeer daar.

- `design/Fier Finance.dc.html` — de complete pagina (template + logica in één bestand)
- `design/Fier Finance Logo.dc.html` — de drie logo-richtingen; **1c is gekozen**
- `design/styles.css` — design-tokens en componentklassen (bron van waarheid voor kleur/typo/spacing)
- `design/assets/` — partnerlogo's en ASN-logo

## Fidelity
**High-fidelity.** Kleuren, typografie, spacing en copy zijn definitief bedoeld. Foto en klantcitaat zijn placeholders.

## Design Tokens
Font: **Archivo** (Google Fonts), 400 / 600 / 800. Headings 800, letter-spacing −0.015 tot −0.03em.

Kleuren
- Achtergrond `#f3f2f2` · Surface `#eae9e9` · Tekst `#201e1d`
- **Accent `#f0533d`** (ASN-eekhoornrood; overschrijft het systeemrood) · hover `#d8412c` · pressed / klein accenttekst `#a82b18`
- Accent-ramp: 100 `#fff2ef` · 200 `#ffe0d9` · 800 `#7c1405`
- Neutraal: 700 `#605d5d` (kickers, footer) · 800 `#444141` (bodytekst gedempt)
- Divider: `color-mix(in srgb, #201e1d 40%, transparent)`, altijd **2px**

Spacing: 4 / 8 / 12 / 16 / 24 / 32 px; pagina-ritme 28px (regelhoogte) en 14px halve stap. Sectiepadding 70–112px.
Radius: **0** overal. Schaduwen: niet gebruikt.
Container: max-width 1200px, zijmarge `clamp(20px, 5vw, 72px)`.
Focus: `outline: 2px solid accent; offset 2px`. Selectie: accent 30%.

## Logo (1c — gekozen)
Het F-blok wordt ook gebruikt als nummer-markering bij diensten 01–06 (28px) en in de nav (32px) en footer (36px).

### Logo-specificaties
- Vierkant in accent `#f0533d`, witte (`#f3f2f2`) Archivo 800 "F", links-boven uitgelijnd; letter ≈ 0.85× blokhoogte, line-height 0.8, padding ≈ 11% boven / 12,5% links.
- Formaten: nav 32px, footer/diensten-nummering 28–36px, poster-close 72px (omgekeerd: blok `#f3f2f2`, F in accent).
- Lockup: blok + "Fier" (800) / "Finance" (400) in twee regels, of één regel "Fier Finance" (800). Sub-merken: "Fier" 800 + naam 400 (Hypotheken, Verzekeren, Kredieten, Wonen, Volmacht, Bankzaken).

## Screens / Sections (van boven naar beneden)

### 1. Nav (`.nav`)
Flex, 2px onderlijn. Links: logo-blok 32px + "Fier Finance" 18px/800. Links (14px): Diensten · Bankzaken · Kantoren · Waarom Fier · Ondernemers. Rechts: primaire knop "Maak een afspraak". Labels nooit wrappen, altijd links uitgelijnd. Onder 480px: links verbergen, brand + knop blijven.

### 2. Hero
Padding 112px boven / 84 onder. Grid: titel (1fr) + rechts ASN-blok (auto), align end.
- H1 `clamp(42px, 6.2vw, 84px)`, line-height 1.06, letter-spacing −0.02em, margin-left −0.058em. Regel 1 "Fier Finance." in tekstkleur, regel 2 "Fier vooruit." in accent. Tagline is wisselbaar (3 varianten, zie State).
- Rechts: kicker "ZELFSTANDIG ADVISEUR VAN" (13px, 0.08em, uppercase, neutraal-700) + ASN-logo `clamp(28px, 3vw, 40px)` hoog.
- Sub: 17px/28px, max 58ch, margin-top 36px — het merkverhaal (exacte copy in HTML).
- Knoppen (gap 12px, wrap): primair "Plan een kennismaking", secundair (outline) "Bankzaken" → #bankzaken, ghost "Vind een kantoor bij jou".

### 3. Kernwaarden
Drie gelijke cellen, gescheiden door 2px verticale lijnen, 2px lijn boven en onder. Titel `clamp(28px, 3vw, 40px)` 800 in accent: "Eén adres" / "Eén adviseur" / "100% zelfstandig"; daaronder uppercase 13px label.

### 4. Diensten (#diensten)
Kicker "DE FIER-FAMILIE", H2 "Alles wat met geld te maken heeft. Onder één naam." (max 24ch). Zes rijen met 2px lijn boven elke rij en onder de laatste. Grid `minmax(64px,160px) minmax(0,420px) minmax(0,1fr)`, kolomgap `clamp(24px, 4vw, 72px)`, padding 42px 0, baseline-aligned.
- Kolom 1: F-blok 28px (accentvlak, witte F) + nummer 01–06 (18px/800, tnum).
- Kolom 2: H3 24px + `.tag.tag-neutral` doelgroep.
- Kolom 3: copy 15.5px/28px neutraal-800, max 52ch.
Inhoud: Fier Hypotheken · Fier Verzekeren · Fier Kredieten · Fier Wonen (optioneel, prop) · Fier Bankzaken · Fier Volmacht — copy in de HTML.
Onder 880px: één kolom, gap 14px.

### 5. Bankzaken (#bankzaken)
Kicker "BANKZAKEN". Twee kolommen (auto-fit, min 300px). Links: H2 32px/42px, twee alinea's over ASN Bank als Zelfstandig Adviseur, daaronder 2px lijn + ASN-logo 28px + label "ZELFSTANDIG ADVISEUR VAN ASN BANK". Rechts: drie rijen (Particulier / Bedrijf / Initiatieven), elk H3 20px + copy + knop "Meer informatie" rechts (primair, primair, secundair), 2px lijnen tussen rijen. Sectie sluit met 2px lijn.

### 6. Kantoren (#kantoren)
Twee kolommen (auto-fit, min 300px), gap `clamp(24px, 5vw, 96px)`. Links: kicker "JOUW KANTOOR", H2 "Een adviseur die je bij naam kent.", copy, formulier: `.field` label "Postcode" + `.input` placeholder "1234 AB" + primaire knop "Vind mijn kantoor" + secundaire "Bankzaken". Rechts: foto `kop-munt_5.png` (adviseurs), **in kleur** (uitzondering op de grayscale-regel), 951:665, cover-crop. Onder 720px foto boven de tekst.
Resultaat na zoeken (≥4 tekens): blok met 2px lijn boven, kantoornaam 17px/800, adres + adviseur 14px, `.tag.tag-accent` afstand.

### 7. Onze partners (#partners)
Kicker "ONZE PARTNERS", H2 "Onafhankelijk. We vergelijken voor je bij alle grote aanbieders." Twee marquee-rijen, gap 28px, overflow hidden. Cel 270×108px, padding 0 42px, logo `object-fit: contain`, **`mix-blend-mode: multiply`** (laat witte logo-achtergronden wegvallen). Rij 1 = eerste 13 logo's, 55s; rij 2 = rest, 70s; lineair, oneindig, lijst gedupliceerd en translateX 0 → −50%. Uit bij `prefers-reduced-motion`. Logo's in kleur (uitzondering op de grayscale-regel). Sectie sluit met 2px lijn.

### 8. Waar de naam voor staat (#waarom)
Kicker + H2 "Fier is trots zonder opschepperij." Drie cellen met 2px lijnen boven/onder/tussen: "Fier op je huis" / "Fier op je bedrijf" / "Fier op wat je geregeld hebt", H3 20px + copy 15.5px/28px.

### 9. Particulier of ondernemer (#ondernemers)
Links: kicker "VOOR WIE", H2 "Particulier of ondernemer — één gesprek.", `.seg` segmented control (radio's) Particulier | Ondernemer. Rechts: `.table` met kolommen "Vraag" / "Fier regelt", 4 rijen per doelgroep (copy in HTML).

### 10. Quote
Blockquote Archivo 800 `clamp(24px, 2.6vw, 34px)`, line-height 1.25, max 32ch. Figcaption 15.5px neutraal-700, 42px eronder. Attributie: "— Peter van Warmerhof, klant van Fier Finance". Citaattekst nog te bevestigen.

### 11. Poster close
Volle breedte in accent, tekst in `#f3f2f2`. Padding 84px. Omgekeerd logo-blok 72px, H3 `clamp(34px, 4.2vw, 56px)` "Fier Finance." / "Fier vooruit.", ghost-knop met lichte 1px outline "Maak een afspraak bij jouw kantoor".

### 12. Footer
Drie kolommen (auto-fit, min 200px), 13px/22px neutraal-700: logo-lockup + "Zelfstandig advies. Fier geregeld." · Merkfamilie · Toezicht (AFM/Kifid/DVD/Privacy — invullen per kantoor).

## Interactions & Behavior
- Anker-navigatie met smooth scroll.
- Knoppen: primair hover `#d8412c`, active `#a82b18`; secundair hover tekst 7%; ghost hover accent 10%. Focus-ring 2px accent.
- Postcode-formulier: submit → toon kantoorresultaat als invoer ≥4 tekens (nu statische demo "Fier Finance Amersfoort"; koppel aan kantorenlijst/geo-API).
- Segmented control wisselt tabelrijen particulier/ondernemer.
- Marquee: zie sectie 7.

## State Management
- `tagline`: "Fier vooruit." | "Trots op wat je opbouwt." | "Fier geregeld." (CMS-instelling)
- `toonWonen`: boolean — Fier Wonen tonen (alleen kantoren met makelaardij)
- `postcode`, `gezocht`, gevonden kantoor
- `doelgroep`: particulier | ondernemer

## Responsive
Fluid, max 1200px. Grids met `auto-fit, minmax(…,1fr)`. Breakpoints: 880px (dienstenrijen stapelen), 720px (foto boven, hero-padding kleiner), 480px (navlinks weg). Geen tekstwrap in knoppen/tags/navlabels.

## Assets (`design/assets/`)
- `logo-asn.svg` — ASN Bank (kleur eekhoorn `#f0533d` = accent)
- Partnerlogo's (25): ABN AMRO, ASN Bank, a.s.r., Allianz, Argenta, Attens, BLG Wonen, bijBouwe, bunq, Centraal Beheer, Florius, ING, Jens (`images.png`), Knab, Lloyds Bank, Merius, MUNT, NIBC, Nationale-Nederlanden, Obvion, Socio Hypotheek, Syntrus Achmea, Tulp Hypotheken, Venn, Vista (`vista-hypotheken-fixed.png` is de rechtop gezette versie)
- Lucide-icons indien nodig. `kop-munt_5.png` — adviseursfoto (kantoren-sectie). Citaattekst van Peter van Warmerhof nog te bevestigen.
- Let op: partnerlogo's zijn merkeigendom van de betreffende partijen; gebruik alleen met toestemming.
