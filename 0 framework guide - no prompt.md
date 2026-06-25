# Framework Guide - No Prompt

Questa guida è per l'utente umano. Non è un prompt da eseguire e non va fornita all'IA durante la generazione dei documenti di progetto.

## Scopo

Il framework genera una documentazione compatta per progetti di vibe coding e poi definisce un workflow operativo per l'IA.

La documentazione resta la fonte di verità. Ogni prompt produce un solo anello della catena e non deve duplicare responsabilità degli altri.

## Input Iniziale Opzionale

`vision.md` può essere creato dall'utente prima di avviare il framework.

Contiene l'idea originale in forma libera: obiettivo, contesto, vincoli, desideri, esempi o note grezze.

`vision.md` non sostituisce `docs/requirements.md`: è materiale di partenza da cui derivare requisiti e documenti successivi.

## Ordine Di Esecuzione

```text
vision.md
   ↓
1 requirements template prompt
   ↓
2 requirements prompt
   ↓
3 architecture prompt
   ↓
4 design prompt opzionale
   ↓
5 security prompt
   ↓
6 tasks prompt
   ↓
7 scelta del workflow
```

## Dipendenze

```text
1 requirements template prompt
- può usare vision.md se presente
- genera docs/requirements_template.md

2 requirements prompt
- usa vision.md se presente
- usa docs/requirements_template.md
- genera docs/requirements.md

3 architecture prompt
- usa docs/requirements.md
- genera docs/architecture.md

4 design prompt
- usa docs/requirements.md
- usa docs/architecture.md
- genera docs/design.md solo se il progetto prevede frontend/UI/UX

5 security prompt
- usa docs/requirements.md
- usa docs/architecture.md
- usa docs/design.md se presente
- genera docs/security.md

6 tasks prompt
- usa docs/requirements.md
- usa docs/architecture.md
- usa docs/security.md
- usa docs/design.md se presente
- genera docs/tasks.md

7 document driven workflow prompt
- usa tutti i documenti precedenti
- genera docs/workflow.md per il Document-Driven Workflow

7 agent driven workflow prompt
- usa tutti i documenti precedenti
- genera docs/workflow.md e agents/ per l'Agent-Driven Workflow

7tris dynamic agent driven workflow prompt
- usa tutti i documenti precedenti
- genera docs/workflow.md e agents/ per il Dynamic Agent-Driven Workflow
```

## Biforcazione Al Punto 7

I prompt da 1 a 6 sono comuni a tutti gli approcci.

Al punto 7 scegli ed esegui un solo workflow:

```text
7 document driven workflow prompt
7 agent driven workflow prompt
7tris dynamic agent driven workflow prompt
```

Non eseguire tutti i prompt 7 nello stesso progetto, perché generano alternative diverse per `docs/workflow.md`.

## Scelta Del Workflow

Document-Driven Workflow:
- per progetti semplici o medi;
- usa solo documentazione e regole operative compatte;
- non crea agenti persistenti.

Agent-Driven Workflow:
- per progetti più complessi;
- crea agenti statici specializzati coordinati da un orchestratore;
- mantiene la conoscenza di dominio in `docs/`.

Dynamic Agent-Driven Workflow:
- per progetti sperimentali o avanzati;
- crea un set minimo di agenti;
- consente la creazione di agenti specializzati a runtime quando giustificato;
- adatto a PoC con Spring AI o sistemi agentici dinamici.

## Output Finali Possibili

```text
docs/
├── requirements_template.md
├── requirements.md
├── architecture.md
├── design.md              # solo se serve UI/UX/frontend
├── security.md
├── tasks.md
├── workflow.md            # generato da uno solo dei prompt 7
└── decisions.md           # creato o aggiornato solo quando serve

agents/                   # solo per workflow agent-driven
```

## Regole Di Isolamento

- `requirements_template.md` definisce solo lo standard dei requisiti.
- `requirements.md` definisce cosa deve fare il sistema.
- `architecture.md` definisce come è costruito il sistema.
- `design.md` definisce UI/UX solo se necessaria.
- `security.md` definisce guardrail, policy e rischi.
- `tasks.md` definisce roadmap incrementale e ordine di implementazione.
- `workflow.md` definisce come l'IA deve lavorare.
- `agents/` definisce ruoli operativi solo negli approcci agent-driven.
- `decisions.md` traccia solo decisioni significative.

## Regole Generali

- Mantieni i documenti compatti.
- Evita duplicazioni tra file.
- Mantieni una sola fonte di verità per ogni informazione.
- Usa riferimenti tra documenti solo quando necessari.
- Ogni prompt deve generare esclusivamente il proprio output.
- Ogni documento prodotto deve essere ottimizzato per IA di coding e massimo rapporto informazioni/token.
