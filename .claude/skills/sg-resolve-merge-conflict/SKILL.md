---
name: sg-resolve-merge-conflict
description: Fiks merge-konflikten(e) på gjeldende branch. Bruk denne skillen når git rapporterer konflikterende filer under en merge eller rebase, eller når brukeren ber om hjelp til å løse en merge-konflikt. Forstår intensjonen bak begge sidene av konflikten før den løses, slik at ingens arbeid går tapt.
---

# Resolve Merge Conflict

Når du løser en merge-konflikt er målet å bevare intensjonen bak begge endringene — ikke bare å velge en side og gå videre.

## Workflow

### 1. Kartlegg konflikten
- Kjør `git status` for å se hvilke filer som er i konflikt
- Sjekk hvilken operasjon som pågår (merge, rebase, cherry-pick) — det påvirker hvordan du fullfører etterpå

### 2. Forstå begge sider
For hver konflikt:
- Les `git log`/`git blame` på begge sider for å forstå hvorfor hver endring ble gjort
- Ikke anta at "ours" eller "theirs" automatisk er riktig — les innholdet

### 3. Løs konflikten
- Kombiner endringene der begge er relevante og forenlige
- Hvis endringene faktisk er uforenlige (samme linje endret på fundamentalt forskjellige måter), vurder intensjonen bak begge og løs det på en måte som beholder begge formål — spør brukeren hvis det er uklart hvilken retning som er riktig
- Fjern konfliktmarkørene (`<<<<<<<`, `=======`, `>>>>>>>`) fullstendig

### 4. Verifiser
- Kjør testsuiten for å bekrefte at løsningen faktisk fungerer, ikke bare at den kompilerer
- Sjekk gjennom filene som var i konflikt en gang til for gjenværende markører eller feil

### 5. Fullfør
- Stage de løste filene og fullfør operasjonen (`git merge --continue`, `git rebase --continue`, osv.)
- Ikke bruk `--abort` eller andre destruktive kommandoer uten at brukeren har bedt om det

## Tone

Vær tydelig på hva du valgte å beholde fra hver side og hvorfor, spesielt der løsningen ikke var opplagt.
