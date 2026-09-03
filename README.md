# skill-garden

OBOS sine delte Claude-skills. Én skill per mappe under `.claude/skills/`, hver en selvstendig `SKILL.md`.

## Bruk det

```bash
git clone <this-repo> ~/skill-garden
claude --add-dir ~/skill-garden
```

Det er alt — hver skill under lastes automatisk, og holdes synkronisert med en `git pull`. Ingen symlinking per skill, ingen oppsett å gjøre på nytt når en ny skill legges til.

## Skills

| Skill | Formål |
|---|---|
| `review-code` | Reviewer en diff/PR for korrekthet, sikkerhet, ytelse |
| `diagnose-bugs` | Reproduser, isoler, og finn rotårsaken til en bug |
| `write-doc-to-notion` | Gjør kildemateriale om til en Notion-side |
| `refactor-code` | Forenkle eller restrukturer kode — én funksjon eller hele arkitekturen |
| `sharpen-plan` | Intervju-stil spørsmål for å pressteste en plan før dere bygger |
| `answer-conversation` | Les en Slack-/e-posttråd, produser svaret |
| `implement` | Bygg ny funksjonalitet test-først (TDD), typecheck underveis, gi stafettpinnen videre til `review-code` til slutt |
| `describe-pr` | Skriv PR-beskrivelsen fra diffen |
| `resolve-merge-conflict` | Løs en merge-konflikt |
| `research` | Undersøk ved bruk av høyt pålitelige primærkilder (dokumentasjon, spesifikasjoner — ikke blogginnlegg) |
| `write-tests` | Legg til tester i eksisterende kode som mangler dem (brukes ikke når `implement` allerede gjør TDD) |
| `thread-to-spec` | Gjør en samtaletråd om til et spec-dokument — pairer med `write-doc-to-notion` for publisering |
| `teach` | Forklar et eksisterende konsept/kodebase til personen, på deres nivå |
| `answer-pr-comments` | Jobb deg gjennom PR-kommentarer én og én og utform svar |
| `test-components-responsive-devices` | Test UI-komponenter på iOS-/Android-simulatorer på tvers av skjermstørrelser |

## Tre regler

1. **Én skill, én mappe** under `.claude/skills/` — ingenting løst ved siden av.
2. **`SKILL.md` er den eneste påkrevde filen.** Skript, maler, referansedokumenter er valgfrie og bor inne i samme mappe.
3. **Mappenavn = skill-navn**, kebab-case, verb-først — `refactor-code`, ikke `Refactor Code`.

## Legge til en skill

1. Opprett `.claude/skills/<kebab-case-verb-først-navn>/`.
2. Skriv `SKILL.md` — frontmatter (`name`, `description`) først, deretter steg-for-steg-instruksjoner.
3. Legg til denne raden i tabellen over.
4. Åpne en PR.
