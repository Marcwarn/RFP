# Doings RFP Evaluator

Ett interaktivt verktyg för att skapa, utvärdera och förbättra RFP-svar (Request for Proposal) med hjälp av AI-agenter.

## Översikt

Doings RFP Evaluator är ett webbbaserat verktyg byggt för att hjälpa team att effektivt svara på RFP-förfrågningar. Verktyget kombinerar manuell redigering med AI-assisterade förbättringar för att skapa högkvalitativa RFP-svar.

### Huvudfunktioner

- **AI-agenter** - 7 specialiserade agenter som förbättrar svar
- **Real-time utvärdering** - Automatisk poängsättning mot RFP-krav
- **Kundinsikt** - Webbaserad research om kunden via Perplexity API
- **Import/Export** - Stöd för Word, HTML, CSV
- **Team-samarbete** - HITL (Human-in-the-Loop) granskningsflöde
- **Lösenordsskydd** - För säker delning inom team

## Snabbstart

### 1. Öppna filen
Öppna `Elisa_RFP_Evaluator_EN.html` i valfri modern webbläsare.

### 2. Logga in
Lösenord: `ElisaRFP`

### 3. Konfigurera API-nycklar (valfritt men rekommenderat)
Klicka på API-knappen och ange:
- **Claude API-nyckel** - För AI-analys och förbättringar
- **Perplexity API-nyckel** - För webbaserad kundinsikt

### 4. Ladda RFP-dokument
Klicka "Kundinsikt" → Ladda upp RFP-dokumentet (PDF/Word)

### 5. Generera kundinsikt
Klicka "Generera kundinsikt" för att söka information om kunden

### 6. Skriv/importera svar
- Skriv direkt i sektionerna, eller
- Använd "Klistra in AI-svar" för text från ChatGPT/Copilot
- Använd "Ladda Word-fil" för befintliga Word-dokument

### 7. Förbättra med agenter
Använd de 7 AI-agenterna för att förbättra svaren

### 8. Exportera
Exportera till Word, HTML eller CSV

## De 7 AI-agenterna

| Agent | Funktion |
|-------|----------|
| **Gap Filler** | Identifierar och fyller i saknade krav |
| **Refine** | Förbättrar språk och struktur |
| **Doings Coach** | Anpassar till Doings varumärke |
| **Weakness Analysis** | Hittar svagheter ur kundens perspektiv |
| **Critical Questions** | Genererar frågor evaluatorer kan ställa |
| **Stakeholder Mapping** | Kartlägger beslutsfattare |
| **ROI Calculator** | Bygger business case med ROI |

## Arbetsflöde

```
1. Ladda RFP → 2. Generera kundinsikt → 3. Skriv/importera svar
     ↓
4. Förbättra med agenter → 5. HITL-granskning → 6. Export
```

## Teknisk specifikation

### Stack
- **Frontend**: React 18 (via CDN)
- **Styling**: Tailwind CSS
- **Transpilering**: Babel Standalone
- **Dokumenthantering**: Mammoth.js (Word), PDF.js (PDF), SheetJS (Excel)

### API-integration
- **Claude API** - Anthropic's AI för analys och textgenerering
- **Perplexity API** - Webbaserad sökning för kundinsikt

### Datalagring
- **localStorage** - API-nycklar, svar, RFP-dokument
- **sessionStorage** - Autentiseringsstatus

## Filstruktur

```
elisa-rfp-evaluator/
├── Elisa_RFP_Evaluator_EN.html   # Huvudapplikation (single-file)
├── README.md                      # Denna dokumentation
└── docs/
    └── DEPLOYMENT.md              # Deployment-guide
```

## Deployment

### Lokal användning
Öppna HTML-filen direkt i webbläsaren.

### Vercel
1. Skapa GitHub-repo
2. Koppla till Vercel
3. Deploy

Se `docs/DEPLOYMENT.md` för detaljerad guide.

## Säkerhet

- **Lösenordsskydd**: Enkel autentisering för intern användning
- **API-nycklar**: Sparas lokalt i användarens webbläsare
- **Ingen server**: All data stannar på användarens dator

## Anpassning

### Ändra lösenord
Sök efter `TEAM_PASSWORD` i HTML-filen och ändra värdet.

### Ändra RFP-sektioner
Sök efter `rfpSections` för att modifiera sektionsstrukturen.

### Ändra varumärke
Sök efter `doingsExpertKnowledge` för Doings-specifik information.

## Support

Skapat av Doings för Elisa RFP 2026.

## Version

**v2.0** - Februari 2026
- Lösenordsskydd
- Hjälp-modal med dokumentation
- Förbättrade inline-förklaringar
- 7 AI-agenter
- HITL-granskningsflöde
