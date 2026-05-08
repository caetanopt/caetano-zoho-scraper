# Caetano Zoho Scraper

Scraper automatizado que extrai contagens agregadas (leads + oportunidades) de campanhas do Zoho Analytics, por marca e por ID Landing, e publica num `zoho-data.json` que o dashboard interno consome.

## O que faz

- Corre **diariamente as 05:00 UTC** via GitHub Actions
- Para cada uma das 13 marcas mapeadas, abre o open-view publico do Zoho Analytics, aplica filtros (mes corrente, concessionario, lead source = Facebook+Instagram), itera os ID Landings disponiveis, e regista leads + oportunidades + taxa
- Faz `merge` com dados de meses anteriores (preserva historico)
- Commita o `zoho-data.json` no repo

## Tech

- Python 3.12
- Playwright (Chromium headless)
- GitHub Actions

## Trigger manual

No separador **Actions** > **Scrape Zoho Data** > botao **Run workflow**.
