---
name: sg-describe-pr
description: Skriv en PR-beskrivelse basert på kodeendringene — enten uncommittede endringer eller det som allerede er committet på branchen — som følger repoets PR-mal. Bruk denne skillen når brukeren vil ha en PR-beskrivelse utformet, vil ha hjelp til å skrive opp hva en branch gjør, eller er i ferd med å åpne en pull request. Forklarer problemet som løses og hva som ble gjort for å løse det, skrevet slik at noen uten kontekst på oppgaven kan følge det.
---

# Describe PR

Når du skriver en PR-beskrivelse er jobben din å gjøre det raskt for en reviewer uten kontekst å forstå hva som endret seg og hvorfor — ikke å gjenfortelle diffen linje for linje.

## Workflow

### 1. Samle endringene
- Se på uncommittede endringer (`git status` / `git diff`) og alt som er committet på gjeldende branch mot dens target (vanligvis `main`)
- Les den faktiske diffen — ikke bare gjett deg til intensjonen fra commit-meldinger alene, de kan være utdaterte eller ufullstendige

### 2. Velg malen
- Bruk `./templates/pr-template.no.md` (norsk) som standard, med mindre brukeren eller repoets eksisterende PR-er indikerer engelsk — bruk da `./templates/pr-template.md`
- Fyll ut hver seksjon i malen; ikke la en seksjon stå tom hvis det finnes informasjon tilgjengelig for den

### 3. Skriv beskrivelsen
Følg denne strukturen innenfor malens beskrivelses-seksjon:
- **Hva problemet er** — hvorfor måtte denne endringen gjøres? Hva var ødelagt, manglet, eller var tungvint før?
- **Hva som ble gjort for å løse det** — en klar, overordnet redegjørelse for tilnærmingen, ikke en linje-for-linje-fortelling om diffen

Skriv det slik at noen som ikke kjenner oppgaven kan lese det og forstå både motivasjonen og endringen — dette er det som gjør at reviewere kommer raskere gjennom køen sin.

### 4. Presenter utkastet
- Vis den utfylte malen til brukeren som markdown for gjennomgang
- Ikke åpne eller oppdater selve PR-en på GitHub uten brukerens eksplisitte godkjenning — dette er deres PR å poste

## Tone

Vær konsis. Reviewere har mange PR-er å komme gjennom — en klar, kort beskrivelse blir reviewet raskere enn en omfattende en.
