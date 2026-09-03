---
name: sg-implement
description: Implementer kode basert på en gitt oppgave, test-først (TDD), med typechecking underveis. Bruk denne skillen når brukeren ber om å bygge ny funksjonalitet. Skriver minst mulig kode av høy kvalitet som løser oppgaven, kjører deretter review-code-skillen og går tilbake og fikser det som må fikses til reviewen består.
---

# Implement

Når du implementerer ny funksjonalitet er målet å skrive den minste mengden kode av høy kvalitet som løser oppgaven — ikke mer.

## Workflow

### 1. Forstå oppgaven
- Les oppgavebeskrivelsen og relevant eksisterende kode før du skriver noe
- Hvis oppgaven er tvetydig på et punkt som faktisk endrer implementasjonen, spør — ikke gjett deg til en større løsning enn nødvendig

### 2. Skriv testen først (TDD)
- Skriv en test som beskriver forventet oppførsel før du implementerer den
- Bekreft at testen feiler av riktig grunn før du går videre

### 3. Implementer
- Skriv minst mulig kode som får testen til å bestå
- Følg konvensjonene som allerede finnes i kodebasen
- Ikke bygg for hypotetiske fremtidige behov — løs oppgaven som er gitt

### 4. Typecheck underveis
- Kjør typechecker (eller tilsvarende statisk sjekk) etter hver meningsfulle endring, ikke bare til slutt
- Fiks typefeil før du går videre til neste steg

### 5. Kjør review-code
- Når implementasjonen er ferdig, kjør `review-code`-skillen på endringene dine
- Hvis den ikke består: gå tilbake, fiks det som er flagget, og kjør review på nytt
- Gjenta til reviewen består

## Tone

Vær pragmatisk. Prioriter en løsning som er lett å forstå og vedlikeholde, fremfor en som er clever.
