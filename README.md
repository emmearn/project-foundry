# Project Foundry

Project Foundry e' un framework di prompt per trasformare un'idea iniziale in una documentazione operativa compatta per progetti di vibe coding e sviluppo assistito da IA.

Il repository non contiene codice applicativo: contiene una sequenza di prompt e una guida per generare documenti di progetto coerenti, isolati e ottimizzati per essere usati da agenti o AI coding assistant.

## Scopo

Il framework aiuta a produrre una catena documentale ordinata:

- requisiti;
- architettura;
- design UI/UX, se necessario;
- sicurezza;
- task di implementazione;
- workflow operativo per l'IA.

La documentazione generata diventa la fonte di verita' del progetto. Ogni prompt produce un solo documento o gruppo di artefatti e non deve duplicare responsabilita' gia' assegnate agli altri documenti.

## File Del Framework

```text
0 framework guide - no prompt.md
1 requirements template prompt.md
2 requirements prompt.md
3 architecture prompt.md
4 design prompt.md
5 security prompt.md
6 tasks prompt.md
7 document driven workflow prompt.md
7 agent driven workflow prompt.md
7tris dynamic agent driven workflow prompt.md
```

`0 framework guide - no prompt.md` e' una guida per l'utente umano. Non e' un prompt da eseguire.

I file numerati da `1` a `6` vanno usati in ordine. Al punto `7` va scelto un solo workflow tra le alternative disponibili.

## Workflow

Ordine consigliato:

```text
vision.md
   -> 1 requirements template prompt
   -> 2 requirements prompt
   -> 3 architecture prompt
   -> 4 design prompt opzionale
   -> 5 security prompt
   -> 6 tasks prompt
   -> 7 scelta del workflow
```

`vision.md` e' opzionale e puo' contenere l'idea iniziale in forma libera: obiettivo, contesto, vincoli, desideri, esempi o note grezze.

## Scelta Del Punto 7

Scegli una sola delle tre alternative:

- `7 document driven workflow prompt.md`: per progetti semplici o medi, senza agenti persistenti.
- `7 agent driven workflow prompt.md`: per progetti piu' complessi, con agenti statici specializzati.
- `7tris dynamic agent driven workflow prompt.md`: per progetti sperimentali o avanzati, con agenti specializzati creati a runtime quando serve.

Non eseguire piu' prompt del punto `7` nello stesso progetto: generano strategie alternative per `docs/workflow.md`.

## Output Attesi

Il framework puo' generare:

```text
docs/
  requirements_template.md
  requirements.md
  architecture.md
  design.md
  security.md
  tasks.md
  workflow.md
  decisions.md

agents/
```

`docs/design.md` viene creato solo se il progetto prevede UI, UX o frontend.

`agents/` viene creato solo nei workflow agent-driven.

## Uso Rapido

1. Crea `vision.md`, se vuoi partire da una descrizione libera del progetto.
2. Apri `0 framework guide - no prompt.md` e segui l'ordine indicato.
3. Esegui i prompt da `1` a `6` con l'AI assistant scelto.
4. Scegli un solo prompt del punto `7`.
5. Usa i documenti generati in `docs/` come base operativa per lo sviluppo.

## Principi

- Mantieni i documenti compatti.
- Evita duplicazioni tra file.
- Mantieni una sola fonte di verita' per ogni informazione.
- Aggiorna la documentazione solo quando cambia una decisione o un vincolo reale.
- Usa i documenti generati come contesto principale per l'IA di coding.
