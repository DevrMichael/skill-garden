---
name: diagnose-bugs
description: Reproduser, isoler og finn rotårsaken til en bug i koden. Bruk denne skillen når brukeren rapporterer en feil, uventet oppførsel, eller ber om å finne ut hvorfor noe ikke fungerer. Prioriterer bugs som er ødeleggende for appen (krasjer, datatap, feil som blokkerer kjernefunksjonalitet) foran mindre kosmetiske feil.
---

# Diagnose Bugs

Når du diagnostiserer en bug er målet å finne rotårsaken — ikke bare symptomet — før du foreslår en fiks.

## Workflow

### 1. Forstå symptomet
- Få en presis beskrivelse av hva som skjer, kontra hva som forventes å skje
- Spør etter feilmeldinger, stack traces, logger eller skjermbilder hvis det ikke allerede er gitt

### 2. Reproduser
- Finn stegene som trigger buggen
- Bekreft at du kan observere problemet selv (kjør koden, kjør testen, les loggen) før du konkluderer med noe

### 3. Isoler
- Snevre inn hvor i koden problemet oppstår — bruk `git blame`/`git log` for å se om en nylig endring er årsaken
- Sjekk om buggen er ny (regresjon) eller om den alltid har vært der
- Skill mellom flere mulige feilkilder ved å teste hver hypotese isolert

### 4. Prioriter
- Vurder alvorlighetsgraden: krasjer appen, mister data, eller blokkerer buggen kjernefunksjonalitet? Fokuser der først
- Ikke la mindre, kosmetiske feil stjele tid fra det som faktisk er ødeleggende

### 5. Finn rotårsaken
- Ikke stopp ved første plausible forklaring — verifiser at det faktisk er årsaken, ikke bare en korrelasjon
- Forklar mekanismen: hvorfor produserer koden dette symptomet gitt disse input/tilstandene?

### 6. Foreslå fiksen
- Fiks rotårsaken, ikke bare symptomet
- Nevn om det er relaterte steder i kodebasen som kan ha samme feil

## Tone

Vær systematisk og vis resonnementet ditt — hvilken hypotese du testet og hvorfor den ble bekreftet eller avkreftet.
