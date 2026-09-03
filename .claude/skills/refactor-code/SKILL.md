---
name: refactor-code
description: Se gjennom kode — enten det brukeren peker deg til eller hele kodebasen — for muligheter til å refaktorere den slik at den blir mer bærekraftig. Bruk denne skillen når brukeren ber om refactoring, ønsker å rydde opp i eksisterende kode, eller lurer på om en del av arkitekturen kan forenkles.
---

# Refactor Code

Når du refaktorerer er målet å gjøre koden mer bærekraftig — enklere å forstå, endre og bygge videre på — uten å endre oppførselen.

## Workflow

### 1. Avgrens omfanget
- Er dette en spesifikk funksjon/fil brukeren peker på, eller et åpent søk gjennom kodebasen etter muligheter?
- Hvis det er et åpent søk: se etter duplisert logikk, unødvendige abstraksjoner, dårlig navngiving, og steder hvor kompleksiteten ikke matcher problemet

### 2. Forstå gjeldende oppførsel
- Les koden og eventuelle tester grundig før du endrer noe
- Hvis det ikke finnes tester som dekker oppførselen du skal endre, sørg for dekning først slik at du kan verifisere at refaktoreringen ikke endrer noe

### 3. Foreslå refaktoreringen
- Beskriv hva som er problemet med dagens struktur, og hvorfor den foreslåtte endringen gjør den mer bærekraftig
- Prioriter endringer med høyest verdi-per-risiko — ikke refaktorer for refaktoreringens skyld

### 4. Gjennomfør
- Gjør endringen i små, verifiserbare steg
- Kjør testene etter hvert steg for å bekrefte at oppførselen er uendret
- Ikke bland refaktorering med nye features i samme endring

### 5. Oppsummer
- Forklar kort hva som ble endret og hvorfor det gjør koden mer bærekraftig

## Tone

Vær ærlig om avveininger — ikke alt som kan refaktoreres bør refaktoreres. Si fra hvis noe ikke er verdt risikoen.
