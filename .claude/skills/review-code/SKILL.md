---
name: review-code
description: Review koden i changes og/eller det som er committet på branchen, med fokus på industristandard, DRY-prinsippet, sikkerhet, ytelse og at alle tester består. Bruk denne skillen når brukeren ber om kodegjennomgang, code review, eller vil vite om koden er klar til å merges. Vurderer også om implementasjonen kunne vært gjort enklere og mer bærekraftig, og gir konkret, presis tilbakemelding uten fluff.
---

# Review Code

Når du reviewer kode er målet ditt å avdekke det som faktisk må endres før koden kan merges — ikke å liste opp alt du kommer på.

## Workflow

### 1. Finn omfanget
- Se på `git diff` / `git status` for uncommittede endringer, og committede endringer på branchen mot target (vanligvis `main`)
- Hvis brukeren peker på et PR-nummer eller en spesifikk branch, bruk `gh pr diff` eller tilsvarende for å hente det faktiske diffet

### 2. Vurder koden mot disse kriteriene
- **Korrekthet**: Gjør koden det den skal? Er det edge-cases som ikke er dekket?
- **Sikkerhet**: injection, usikker håndtering av secrets/input, manglende validering ved systemgrenser
- **Ytelse**: unødvendig arbeid, N+1-kall, ting som skalerer dårlig
- **DRY og gjenbruk**: er det duplisert logikk som burde vært delt?
- **Enkelhet**: kunne dette vært løst enklere eller mer bærekraftig, uten unødvendige abstraksjoner?
- **Industristandard**: følger koden konvensjonene som allerede finnes i resten av kodebasen?

### 3. Verifiser at tester består
- Kjør testsuiten (eller be brukeren bekrefte at den er kjørt) og sjekk at alt er grønt
- Flagg om nye endringer mangler testdekning for kritiske stier

### 4. Gi tilbakemelding
- List kun opp det som faktisk bør endres — ikke ramse opp ting "bare fordi"
- Vær konkret: pek på fil og linje (`fil.ts:42`), forklar hvorfor det er et problem, og foreslå en løsning
- Skill mellom det som *må* fikses og det som er en nice-to-have
- Hold det oversiktlig og forståelig — ingen fluff

## Tone

Vær direkte og presis. Ikke server en lang liste av observasjoner for observasjonens skyld — hver kommentar skal ha en konkret grunn til å eksistere.
