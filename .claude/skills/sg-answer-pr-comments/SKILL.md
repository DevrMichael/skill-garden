---
name: sg-answer-pr-comments
description: Adresser PR-kommentarer på gjeldende branch på en gjennomtenkt og samarbeidsvillig måte. Bruk denne skillen når brukeren vil håndtere tilbakemeldinger fra code review, svare på PR-kommentarer, eller jobbe seg gjennom reviewer-forslag. Hjelper med å liste opp alle kommentarer, diskutere dem én og én, foreslå løsninger basert på koden, og holde en uformell, åpen dialog.
---

# Answer PR Comments

Når du svarer på kommentarer på en pull request er rollen din å legge til rette for en gjennomtenkt diskusjon, forstå tilbakemeldingen fra revieweren, og hjelpe brukeren med å ta de beste avgjørelsene for koden.

## Workflow

### 1. List opp alle kommentarer
Identifiser først alle kommentarer på PR-en for gjeldende branch:
- Les PR-en for å finne alle review-kommentarer, forslag og diskusjoner
- Trekk dem ut i en tydelig liste med:
  - Kommentar-ID eller lokasjon (fil, linjenummer)
  - Hvem som la igjen kommentaren
  - Kommentarteksten (eller et sammendrag)
  - Nåværende status (ubesvart, adressert, osv.)

Presenter denne listen for brukeren slik at de kan se alt som trenger oppmerksomhet. Ikke svar på eller løs kommentarer ennå — bare vis hva som finnes.

### 2. Adresser kommentarer én og én
Ta for deg hver kommentar brukeren vil diskutere, og:
- **Forstå tilbakemeldingen**: Hva peker revieweren faktisk på?
- **Se på kodekonteksten**: Se på den faktiske koden kommentaren gjelder for å forstå problemet
- **Vær åpen**: Ikke anta at revieweren tar feil. Vurder perspektivet deres selv om du er uenig
- **Foreslå alternativer**: Hvis kommentaren peker på et reelt problem, foreslå konkrete måter å fikse det på. Hvis du tror kommentaren bommer, forklar hvorfor og tilby alternativer

### 3. Diskuter i fellesskap
For hver kommentar:
- Anerkjenn tilbakemeldingen
- Still oppklarende spørsmål hvis noe er uklart
- Forklar tankegangen din eller avveiningene som er involvert
- Foreslå konkrete kodeendringer eller refaktorering hvis nødvendig
- Vær uformell og vennlig — dette er en samtale, ikke en sjekkliste

### 4. Bestem sammen
Hjelp brukeren med å avgjøre om de skal:
- **Enig, fiks det**: Revieweren har rett, implementer forslaget
- **Enig, men nyanser**: Tilbakemeldingen er gyldig men trenger nyanser — kanskje justere eller delvis adressere den
- **Respektfullt uenig**: Forklar hvorfor gjeldende tilnærming er bedre, og tilby å diskutere videre
- **La stå som det er**: Kommentaren gjelder kanskje ikke for denne spesifikke konteksten

### 5. Hjelp til å utforme svar og gå videre
Når dere har diskutert en kommentar:
- Hvis dere fikser, hjelp til å utforme kodeendringen
- Bekreft at brukeren vil at den skal appliseres
- Hjelp til å utforme et svar som skal postes (men du poster det ikke — brukeren håndterer det)
- Gå videre til neste kommentar

## Tips for gode svar

- **Vær konkret**: Ikke si "vi refaktorerer" — si hva du ville refaktorert og hvorfor
- **Vis respekt**: Selv om du er uenig, anerkjenn revieweren sin bekymring
- **Underbygg**: Hvis du mener en annen tilnærming er bedre, forklar resonnementet
- **Hold det kort**: Reviewere har det travelt — kom til poenget
- **Tilby å snakke**: Hvis det er komplekst, foreslå en rask prat eller dypere diskusjon
- **Inkluder kodeeksempler**: Når du foreslår endringer, vis hvordan fiksen ville sett ut
- **Du poster ikke**: Utform svaret for at brukeren skal gjennomgå og poste det selv

## Tone

Hold svarene uformelle og samarbeidsvillige:
- Bruk førsteperson ("jeg tenker", "vi kunne")
- Anerkjenn gode observasjoner: "Godt poeng, det gikk meg forbi"
- Foreslå fremfor å kreve: "Kanskje vi kunne..." fremfor "Du tar feil"
- Ha personlighet: Dette er en samtale mellom mennesker, ikke et formelt dokument
- Vær profesjonell men vennlig: Ingen grunn til å være stiv

## Når du er usikker

Hvis en kommentar er tvetydig eller du er usikker på hva revieweren mener:
- Be brukeren om å presisere tilbakemeldingen
- Se på kodekonteksten sammen
- Sjekk om det er et mønster eller en tidligere samtale som forklarer det
- Foreslå et oppfølgingsspørsmål til revieweren om nødvendig
