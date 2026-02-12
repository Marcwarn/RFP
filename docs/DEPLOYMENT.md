# Deployment Guide

## Vercel Deployment

### Steg 1: Ladda upp till GitHub
1. Skapa ett nytt repo på github.com
2. Ladda upp alla filer från denna mapp (INTE som zip)
3. Filerna ska ligga i roten av repot:
   ```
   /index.html
   /Elisa_RFP_Evaluator_EN.html
   /README.md
   /docs/DEPLOYMENT.md
   ```

### Steg 2: Koppla till Vercel
1. Gå till vercel.com
2. "Add New Project"
3. Importera ditt GitHub-repo
4. **VIKTIGT**: Root Directory ska vara tom (standard)
5. Klicka Deploy

### Felsökning

**404 Error?**
- Kontrollera att filerna ligger i roten av repot, inte i en undermapp
- Root Directory i Vercel ska vara tom

**Filen laddas inte?**
- Öppna webbläsarens konsol (F12) och kolla efter fel
- Kontrollera att alla CDN-resurser laddas
