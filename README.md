# 🍀 Dani Painel Launcher

Página launcher PWA pro painel da Dani (Trevo Legaliza).

## Por que isso existe?

O painel da Dani é hospedado em Google Apps Script Web App. O Apps Script encapsula o painel num **iframe** dentro de `script.google.com` — e iOS Safari / Android Chrome leem `apple-touch-icon` apenas do **top-level frame**.

Resultado: quando alguém adicionava o painel à tela inicial direto pela URL do Apps Script, o ícone aparecia como emoji ou screenshot (em vez da logo Dani).

Esta página resolve isso: ela é uma "ponte" hospedada no GitHub Pages com:
- Meta tags PWA corretas no top-level frame
- `apple-touch-icon` apontando pra logo Dani (180×180 PNG)
- `manifest.webmanifest` pra Android Chrome
- Redirect JS pra URL do Apps Script

## Como usar

1. Abre `https://trevolegaliza-source.github.io/dani-painel-launcher/` no Safari (iPhone) ou Chrome (Android)
2. Toca em **Compartilhar** → **"Adicionar à Tela de Início"**
3. Toca em **Adicionar**
4. Ícone "dani" aparece na tela inicial 🍀
5. Tap → abre direto no painel da Dani (Apps Script)

## Arquivos

- `index.html` — página launcher com meta tags + redirect
- `manifest.webmanifest` — Web App Manifest pra Android
- `dani-icon-180.png` — ícone PWA (hospedado em `trevo-brand-assets`)

## Manutenção

Se a URL do Apps Script Web App mudar (por re-deploy), atualizar `PAINEL_URL` em `index.html` linha ~120 e `start_url` em `manifest.webmanifest`.
