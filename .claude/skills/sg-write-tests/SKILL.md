---
name: sg-write-tests
description: Skriv tester til en spesifikk oppgave dere jobber med, eller utvid testdekningen på et område brukeren peker deg til. Bruk denne skillen når eksisterende kode mangler tester og brukeren ber om å få lagt til testdekning. Brukes ikke når implement-skillen allerede dekker det test-først (TDD) som en del av å bygge ny funksjonalitet.
---

# Write Tests

Når du skriver tester til eksisterende kode er målet å dekke reell oppførsel og reelle edge-cases — ikke å maksimere antall tester.

## Workflow

### 1. Avgrens omfanget
- Er dette tester for en spesifikk oppgave, eller en generell utvidelse av dekningen i et område brukeren peker på?
- Les koden som skal testes grundig før du skriver noe

### 2. Identifiser hva som må dekkes
- Kjerneoppførselen (happy path)
- Edge-cases: tomme input, grenseverdier, feilstier
- Eksisterende bugs eller regresjoner som er verdt å låse fast med en test

### 3. Skriv testene
- Følg testkonvensjonene som allerede finnes i kodebasen (rammeverk, navngiving, struktur)
- Én test skal verifisere én ting — gjør det tydelig hva som feiler og hvorfor hvis testen slår ut
- Ikke skriv tester som bare speiler implementasjonen — test oppførsel, ikke detaljer

### 4. Verifiser
- Kjør testsuiten og bekreft at de nye testene består
- Bekreft at en test faktisk feiler når den skal (fjern midlertidig implementasjonen, eller injiser en feil) for å unngå tester som aldri kan feile

## Tone

Vær presis om hva som er testet og hva som eventuelt fortsatt mangler dekning.
