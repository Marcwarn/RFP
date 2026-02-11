# Deployment Guide

## Alternativ 1: Vercel (Rekommenderat)

### Steg 1: Skapa GitHub Repository

```bash
# Skapa nytt repo på GitHub
gh repo create doings-rfp-evaluator --public --source=. --push

# Eller manuellt:
# 1. Gå till github.com/new
# 2. Skapa repo "doings-rfp-evaluator"
# 3. Följ instruktionerna för att pusha kod
```

### Steg 2: Koppla till Vercel

1. Gå till [vercel.com](https://vercel.com)
2. Klicka "Add New Project"
3. Importera ditt GitHub-repo
4. Klicka "Deploy"

### Steg 3: Konfiguration (valfritt)

Vercel känner automatiskt igen en statisk HTML-fil. Ingen extra konfiguration behövs.

**Custom domain:**
1. Settings → Domains
2. Lägg till din domän
3. Följ DNS-instruktionerna

---

## Alternativ 2: Netlify

### Steg 1: Drag & Drop

1. Gå till [netlify.com](https://netlify.com)
2. Logga in
3. Dra och släpp projektmappen
4. Klart!

### Steg 2: Koppla GitHub (för automatisk deploy)

1. "New site from Git"
2. Välj GitHub
3. Välj repo
4. Deploy

---

## Alternativ 3: GitHub Pages

### Steg 1: Aktivera Pages

1. Gå till repo Settings
2. Pages → Source: "main branch"
3. Klicka Save

### Steg 2: Byt filnamn

Byt namn på `Elisa_RFP_Evaluator_EN.html` till `index.html` för att det ska fungera som startsida.

---

## Alternativ 4: Egen server

### Nginx

```nginx
server {
    listen 80;
    server_name rfp.doings.se;

    root /var/www/rfp-evaluator;
    index Elisa_RFP_Evaluator_EN.html;

    location / {
        try_files $uri $uri/ =404;
    }
}
```

### Apache

```apache
<VirtualHost *:80>
    ServerName rfp.doings.se
    DocumentRoot /var/www/rfp-evaluator
    DirectoryIndex Elisa_RFP_Evaluator_EN.html
</VirtualHost>
```

---

## Miljövariabler

Appen använder **inga** miljövariabler. API-nycklar matas in av användaren och sparas i webbläsarens localStorage.

---

## SSL/HTTPS

Rekommenderas starkt! Både Vercel och Netlify ger automatisk SSL.

---

## CORS

Appen gör direkta API-anrop till:
- `api.anthropic.com` (Claude)
- `api.perplexity.ai` (Perplexity)

Dessa API:er stödjer CORS från webbläsare.

---

## Felsökning

### "API-nyckel fungerar inte"
- Kontrollera att nyckeln är korrekt
- Claude: börjar med `sk-ant-api03-`
- Perplexity: börjar med `pplx-`

### "Filen laddas inte"
- Kontrollera att webbläsaren är modern (Chrome, Firefox, Edge, Safari)
- Kontrollera JavaScript-konsolen (F12) för fel

### "Lösenordet fungerar inte"
- Standard: `ElisaRFP`
- Rensa sessionStorage om det finns problem

---

## Prestanda

Filen är ~300KB vilket laddar snabbt. CDN-resurser (React, Tailwind) cachas automatiskt av webbläsaren.

---

## Backup

All data sparas lokalt i webbläsaren. Rekommendera användare att:
1. Exportera till Word regelbundet
2. Inte rensa webbläsardata under pågående arbete
