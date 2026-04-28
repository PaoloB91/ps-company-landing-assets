# PS Company — Landing Assets (CDN pubblico)

Asset pubblici (immagini, font, video) referenziati dalle landing page dei clienti PS Company SRL.

## Perché questo repo esiste

Il piano agency Duda di PS Company non espone API per upload diretto immagini in libreria media. Per automatizzare i deploy delle landing su Duda (skill `duda-deploy` nel workspace Claude), le immagini vengono ospitate qui e referenziate via URL `raw.githubusercontent.com`.

## URL pattern

```
https://raw.githubusercontent.com/PaoloB91/ps-company-landing-assets/main/<cliente>/<progetto>/<file>
```

Esempi:
- `https://raw.githubusercontent.com/PaoloB91/ps-company-landing-assets/main/ameco/spurghi-2026/logo-ameco.png`
- `https://raw.githubusercontent.com/PaoloB91/ps-company-landing-assets/main/ameco/spurghi-2026/espurghi-bismantova.jpg`

## Struttura cartelle

```
<cliente>/
  <progetto>/
    <file-immagine.ext>
```

Convenzioni:
- Nomi cliente in **kebab-case** (es. `ameco`, `vezzani-forni`, `bonacini-morani`)
- Nomi progetto/landing in **kebab-case** (es. `spurghi-2026`, `bagni-chimici-2026`)
- File con nome significativo (`logo-ameco.png` non `IMG_001.jpg`)

## Cosa NON mettere qui

- File con dati sensibili o riservati (questo repo è **PUBBLICO**)
- Codice sorgente (vivere nel workspace Claude o in repo dedicati)
- Asset di clienti che hanno richiesto esplicitamente di non condividere materiale

## Come aggiungere asset (workflow standard)

Lo fa la skill `duda-deploy` automaticamente quando si lancia un nuovo deploy. Manualmente:

```bash
cd /Users/paolo/Repos/ps-company-landing-assets
mkdir -p <cliente>/<progetto>
cp /path/to/images/*.jpg <cliente>/<progetto>/
git add . && git commit -m "Add <cliente> <progetto> assets" && git push
```

Gli URL raw sono live ~1 minuto dopo il push.

## Clienti attivi

- **ameco** — Spurghi e servizi ambientali, Castelnovo ne' Monti (RE)
  - `spurghi-2026/` — landing Google Ads Spurghi 2026

## Licensing

Le immagini caricate qui sono di proprietà dei rispettivi clienti. Vengono conservate qui come hosting tecnico per landing page autorizzate. Per dubbi, contattare PS Company SRL.
