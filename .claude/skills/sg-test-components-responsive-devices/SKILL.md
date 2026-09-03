---
name: sg-test-components-responsive-devices
description: Test UI-komponenter på tvers av iOS- og Android-simulatorer med ulike skjermstørrelser for å sikre at de ser bra ut på alle enheter. Bruk denne skillen når brukeren vil verifisere responsivt design, teste komponenter på mobile enheter, sjekke layout på ulike skjermstørrelser, eller sikre UI-konsistens på tvers av plattformer. Hjelper med å identifisere visuelle bugs, layout-problemer, og gir anbefalinger for fikser.
---

# Test Components on Responsive Devices

Når du tester UI-komponenter på tvers av flere enheter og skjermstørrelser er målet ditt å systematisk verifisere at komponentene rendres riktig og ser bra ut på både iOS- og Android-simulatorer med ulike skjermdimensjoner.

## Workflow

### 1. Planlegg teststrategien
Hjelp først brukeren med å identifisere hva som må testes ved å spørre:
- Hvilke komponenter eller skjermer bør testes?
- Hva er de kritiske brukerflytene eller visuelle elementene?
- Er det kjente problemområder eller edge-cases?

Lag en testplan som inkluderer:
- **Komponenter å teste**: Liste over spesifikke komponenter eller skjermer
- **Enheter**: iOS (ulike iPhone-størrelser) og Android (ulike størrelser/tetthet)
- **Skjermorienteringer**: Portrett og landskap hvis relevant
- **Nøkkelområder å verifisere**: Layout, tekstoverflow, touch-targets, avstand, bilder

### 2. Start dev-serveren
Hjelp brukeren med å starte utviklingsserveren (hvis den ikke allerede kjører). Dette kan innebære:
- Kjøre `npm run dev`, `yarn start`, eller lignende byggekommandoer
- Bekrefte at serveren er tilgjengelig lokalt
- Notere port og URL

### 3. Start simulatorer og test
Bruk tilgjengelige iOS Simulator- og Android Emulator-verktøy:
- Ta skjermbilder av hver komponent på hver enhet/skjermstørrelse
- Dokumenter det du observerer (layout, avstand, tekstsynlighet, farger, interaktive elementer)
- Noter eventuelle visuelle uoverensstemmelser eller problemer

### 4. Analyser funn
Dokumenter for hvert problem som blir funnet:
- **Komponent/skjerm**: Hva som ble testet
- **Enhet**: iOS/Android, skjermstørrelse, orientering
- **Problem**: Hva som ser feil eller ødelagt ut
- **Alvorlighetsgrad**: Kritisk (bryter funksjonalitet), Høy (ser dårlig ut), Medium (mindre kosmetisk problem), Lav (finpuss)
- **Mulig årsak**: Hvorfor dette kan skje (overflow, responsivt breakpoint, manglende media query)
- **Anbefalt fiks**: Konkrete CSS- eller layout-endringer for å adressere det

### 5. Generer rapport
Gi en tydelig, organisert rapport som inkluderer:
- Sammendrag av komponenter testet og enheter dekket
- Liste over funn (gruppert etter alvorlighetsgrad)
- Skjermbilder eller beskrivelser av hvert problem
- Konkrete anbefalinger for fikser (CSS-endringer, layout-justeringer, breakpoint-oppdateringer)
- Neste steg for brukeren

## Tips for effektiv testing

- **Test systematisk**: Gå gjennom hver komponent og skjermstørrelse metodisk, ikke hopp over noe
- **Se etter vanlige problemer**: Tekstoverflow, for små knapper, bilder som ikke skalerer, avstand som bryter sammen, overlappende elementer
- **Prøv interaksjoner**: Trykk på knapper, scroll, fyll ut skjemaer hvis mulig — se om UI-et responderer riktig
- **Landskap teller**: Ikke glem å rotere og teste overganger mellom portrett/landskap
- **Vær grundig, men fokusert**: Test reelle scenarioer brukeren bryr seg om, ikke alle mulige dimensjoner

## Output-stil

Vær samtalepreget og praktisk i funnene dine. Ikke bare list opp problemer — forklar hva som gikk galt og hvorfor du tror det skjedde. Gi handlingsrettede anbefalinger som brukeren kan implementere umiddelbart.
