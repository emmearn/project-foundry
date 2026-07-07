# Framework Guide - No Prompt

Questa guida è per l'utente umano. Non è un prompt da eseguire e non va fornita all'IA durante la generazione dei documenti di progetto.

## Scopo

Il framework genera una documentazione compatta per progetti di vibe coding e poi definisce un workflow operativo per l'IA.

La documentazione resta la fonte di verità. Ogni prompt produce un solo anello della catena e non deve duplicare responsabilità degli altri.

## Regola Di Compattezza

Tutti i prompt e tutti i documenti generati devono essere compatti, operativi e ottimizzati per IA di coding: alta densità informativa, nessuna ridondanza, nessuna sezione compilata solo per completezza, riferimenti ad altri documenti invece di duplicazioni.

## Input Iniziale

`docs/vision.md` è scritto da esseri umani prima di avviare il framework.

Contiene l'idea originale in forma libera: obiettivo, contesto, vincoli, desideri, esempi o note grezze.

`docs/vision.md` non sostituisce `docs/requirements.md`: è materiale di partenza da cui derivare requisiti e documenti successivi.

## Ordine Di Esecuzione

```text
docs/vision.md
   ↓
1 requirements template prompt
   ↓
2 requirements prompt
   ↓
3 architecture prompt
   ↓
4 design prompt opzionale
   ↓
4.1 optional design logo prompt opzionale
   ↓
5 security prompt
   ↓
6 tasks prompt
   ↓
7 workflow prompt
```

`4.1 optional design logo prompt.md` va eseguito solo quando il progetto richiede logo, brand asset o identità visiva. Se eseguito, deve seguire immediatamente `4 design prompt.md`.

## Dipendenze

```text
1 requirements template prompt
- usa docs/vision.md se presente
- genera docs/requirements_template.md

2 requirements prompt
- usa docs/vision.md se presente
- usa docs/requirements_template.md
- genera docs/requirements.md

3 architecture prompt
- usa docs/vision.md se presente
- usa docs/requirements.md
- genera docs/architecture.md

4 design prompt
- usa docs/vision.md se presente
- usa docs/requirements.md
- usa docs/architecture.md
- genera docs/design.md solo se il progetto prevede frontend/UI/UX

4.1 optional design logo prompt
- usa docs/vision.md se presente
- usa docs/requirements.md
- usa docs/design.md
- genera assets/logo/
- aggiorna docs/design.md con le regole minime di utilizzo del logo ufficiale

5 security prompt
- usa docs/vision.md se presente
- usa docs/requirements.md
- usa docs/architecture.md
- usa docs/design.md se presente
- genera docs/security.md

6 tasks prompt
- usa docs/vision.md se presente
- usa docs/requirements.md
- usa docs/architecture.md
- usa docs/security.md
- usa docs/design.md se presente
- genera docs/tasks.md

7 workflow prompt
- usa tutti i documenti precedenti
- usa docs/decisions.md se presente
- valida la coerenza della pipeline
- genera docs/workflow.md per il Document-Driven Workflow
```

## Punto 7

I prompt da 1 a 6 generano la documentazione di progetto.

Il punto 7 genera sempre il Document-Driven Workflow:

```text
7 workflow prompt
```

Il framework non genera agenti di sviluppo persistenti. L'IA usa `docs/workflow.md` e i documenti in `docs/` come guida operativa.

## Decisions

`docs/decisions.md` non deve esistere all'avvio.

L'IA lo crea quando emerge la prima decisione significativa e lo aggiorna durante lo sviluppo. Il formato minimo consigliato è:

```text
DEC-001
- Data:
- Stato: Proposed/Accepted/Superseded/Deprecated
- Contesto:
- Decisione:
- Motivazione:
- Alternative considerate:
- Impatto:
- Collegamenti: requisiti, task, documenti o rischi collegati
```

## Workflow

Document-Driven Workflow:

- usa solo documentazione e regole operative compatte;
- mantiene `docs/` come unica fonte di verità;
- non crea agenti di sviluppo persistenti;
- consente all'IA di assumere dinamicamente il ruolo necessario durante il lavoro.

## Output Finali Possibili

```text
docs/
├── vision.md                 # input umano iniziale
├── requirements_template.md
├── requirements.md
├── architecture.md
├── design.md                 # solo se serve UI/UX/frontend
├── security.md
├── tasks.md
├── workflow.md               # generato dal prompt 7
└── decisions.md              # creato o aggiornato dall'IA quando serve

assets/
└── logo/                     # solo se si esegue il prompt 4.1
```

## Regole Di Isolamento

- `docs/vision.md` contiene solo l'input umano iniziale.
- `requirements_template.md` definisce solo lo standard dei requisiti.
- `requirements.md` definisce cosa deve fare il sistema.
- `architecture.md` definisce come è costruito il sistema.
- `design.md` definisce UI/UX e regole minime di uso del logo solo se necessarie.
- `security.md` definisce guardrail, policy e rischi.
- `tasks.md` definisce roadmap incrementale, ordine di implementazione e stato.
- `workflow.md` definisce come l'IA deve lavorare.
- `decisions.md` traccia solo decisioni significative.

## Regole Generali

- Mantieni i documenti compatti.
- Evita duplicazioni tra file.
- Mantieni una sola fonte di verità per ogni informazione.
- Usa riferimenti tra documenti solo quando necessari.
- Ogni prompt deve generare esclusivamente il proprio output.
- Ogni documento prodotto deve essere ottimizzato per IA di coding e massimo rapporto informazioni/token.
- Usa italiano e UTF-8 salvo richiesta esplicita diversa.
