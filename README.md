# Project Foundry

Project Foundry è un framework di prompt per trasformare una visione iniziale in documentazione operativa compatta per progetti di vibe coding e sviluppo assistito da IA.

Il repository non contiene codice applicativo: contiene una sequenza ordinata di prompt che genera documenti di progetto coerenti, isolati e ottimizzati per AI coding assistant. Il `README.md` è la guida introduttiva per l'utente umano e non è un prompt da eseguire.

## Indice

- [Scopo](#scopo)
- [Principi fondamentali](#principi-fondamentali)
- [File del framework](#file-del-framework)
- [Input iniziale](#input-iniziale)
- [Ordine di esecuzione](#ordine-di-esecuzione)
- [Dipendenze tra prompt](#dipendenze-tra-prompt)
- [Output generati](#output-generati)
- [Document-Driven Workflow](#document-driven-workflow)
- [Avvio dello sviluppo](#avvio-dello-sviluppo)
- [Decisioni di progetto](#decisioni-di-progetto)
- [Regole di isolamento](#regole-di-isolamento)
- [Uso rapido](#uso-rapido)

## Scopo

Il framework produce una catena documentale ordinata:

- visione iniziale;
- template dei requisiti;
- requisiti;
- architettura;
- design UI/UX, se necessario;
- logo e regole minime di utilizzo, se necessario;
- sicurezza;
- task di implementazione;
- workflow operativo per l'IA.

La documentazione generata diventa la fonte di verità del progetto. Ogni prompt produce un solo documento o gruppo di artefatti e non deve duplicare responsabilità già assegnate ad altri documenti.

## Principi fondamentali

Project Foundry applica una regola di compattezza a tutti i prompt e a tutti i documenti generati:

- alta densità informativa;
- nessuna ridondanza;
- nessuna sezione compilata solo per completezza;
- riferimenti ad altri documenti invece di duplicazioni;
- una sola fonte di verità per ogni informazione;
- documenti ottimizzati per IA di coding e massimo rapporto informazioni/token.

Usa italiano e UTF-8 salvo richiesta esplicita diversa.

## File del framework

```text
1 requirements template prompt.md
2 requirements prompt.md
3 architecture prompt.md
4 design prompt.md
4.1 optional design logo prompt.md
5 security prompt.md
6 tasks prompt.md
7 workflow prompt.md
8 activation prompt - soft.md
8 activation prompt - balanced.md
8 activation prompt - autonomous.md
README.md
```

I file numerati da `1` a `7` vanno usati in ordine. Il prompt `4.1 optional design logo prompt.md` è opzionale e va eseguito subito dopo `4 design prompt.md` quando il progetto richiede un logo, brand asset o una identità visiva.

I tre prompt `8 activation prompt` non generano nuovi documenti: servono ad avviare lo sviluppo reale con un coding agent dopo la conclusione della fase di progettazione. Va scelto un solo prompt `8`, in base al livello di autonomia desiderato.

## Input iniziale

`docs/vision.md` è scritto da esseri umani prima di avviare il framework.

Può contenere l'idea originale in forma libera: obiettivo, contesto, vincoli, desideri, esempi, riferimenti o note grezze.

`docs/vision.md` non sostituisce `docs/requirements.md`: è materiale di partenza da cui derivare requisiti e documenti successivi.

## Ordine di esecuzione

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
   ↓
8 activation prompt soft / balanced / autonomous
```

`4 design prompt.md` genera `docs/design.md` solo se il progetto prevede frontend, UI o UX.

`4.1 optional design logo prompt.md` va eseguito solo quando il progetto richiede logo, brand asset o identità visiva. Se eseguito, deve seguire immediatamente `4 design prompt.md` e aggiornare `docs/design.md` con le regole minime di utilizzo del logo ufficiale.

## Dipendenze tra prompt

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

8 activation prompt - soft / balanced / autonomous
- usa docs/workflow.md come guida principale
- usa docs/tasks.md come backlog operativo
- usa tutti gli altri documenti in docs/ come vincoli progettuali
- avvia lo sviluppo assistito da IA con livello di autonomia soft, balanced o autonomous
```

## Output generati

Il framework può generare:

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

`docs/design.md` viene creato solo se il progetto prevede UI, UX o frontend.

`assets/logo/` viene creato solo se viene eseguito `4.1 optional design logo prompt.md`.

`docs/decisions.md` non deve esistere per forza all'avvio: l'IA lo crea alla prima decisione significativa e lo aggiorna durante lo sviluppo.

## Document-Driven Workflow

I prompt da `1` a `6` generano la documentazione di progetto.

Il prompt `7 workflow prompt.md` genera sempre il Document-Driven Workflow in `docs/workflow.md`.

Il framework non crea agenti di sviluppo persistenti. L'AI coding assistant usa `docs/workflow.md` e i documenti in `docs/` come guida operativa, assumendo dinamicamente il ruolo necessario durante il lavoro.

Il Document-Driven Workflow:

- usa solo documentazione e regole operative compatte;
- mantiene `docs/` come unica fonte di verità;
- non crea agenti di sviluppo persistenti;
- guida l'IA nello sviluppo, nella verifica e nell'aggiornamento documentale.

## Avvio dello sviluppo

La generazione di `docs/workflow.md` conclude la fase di progettazione di Project Foundry. Da quel momento il progetto dispone dei documenti necessari per iniziare la fase di implementazione con un coding agent come Codex, Claude Code, Copilot, Gemini CLI o strumenti equivalenti.

Durante lo sviluppo, `docs/workflow.md` è il documento guida dell'intero lavoro: definisce come l'IA deve leggere il contesto, rispettare i vincoli, aggiornare la documentazione, gestire decisioni, verifiche, test e avanzamento. `docs/tasks.md` è il backlog operativo da implementare: contiene ordine di lavoro, stato dei task, dipendenze, criteri di completamento e verifiche attese.

Tutti gli altri documenti in `docs/` costituiscono i vincoli progettuali che il coding agent deve rispettare:

- `docs/requirements.md` definisce il comportamento atteso;
- `docs/architecture.md` definisce struttura, stack, componenti e pattern;
- `docs/security.md` definisce guardrail, rischi e controlli;
- `docs/design.md`, se presente, definisce UI/UX, accessibilità e regole visuali;
- `docs/decisions.md`, se presente, registra decisioni significative già assunte.

Project Foundry mette a disposizione tre modalità di attivazione, da scegliere in base al controllo desiderato sul lavoro del coding agent:

- `8 activation prompt - soft.md`: per seguire lo sviluppo passo passo. L'IA esegue un solo task alla volta, riepiloga il risultato, propone il task successivo e attende conferma.
- `8 activation prompt - balanced.md`: per un'autonomia intermedia. L'IA lavora su piccoli gruppi coerenti di task, riepiloga il gruppo completato, propone il gruppo successivo e attende conferma.
- `8 activation prompt - autonomous.md`: per massima autonomia. L'IA procede fino al completamento del progetto, fermandosi solo davanti a blocchi reali o decisioni che richiedono l'utente.

I prompt `8` non sostituiscono i documenti generati: li attivano come contesto operativo. Il README spiega quando usare ciascuna modalità; il prompt scelto definisce come il coding agent deve comportarsi durante l'implementazione.

## Decisioni di progetto

`docs/decisions.md` traccia solo decisioni significative emerse durante progetto e sviluppo. Non deve essere creato all'avvio se non esistono decisioni da registrare.

Formato minimo consigliato:

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

## Regole di isolamento

Ogni documento ha una responsabilità precisa:

- `docs/vision.md` contiene solo l'input umano iniziale.
- `docs/requirements_template.md` definisce solo lo standard dei requisiti.
- `docs/requirements.md` definisce cosa deve fare il sistema.
- `docs/architecture.md` definisce come è costruito il sistema.
- `docs/design.md` definisce UI/UX e regole minime di uso del logo solo se necessarie.
- `docs/security.md` definisce guardrail, policy e rischi.
- `docs/tasks.md` definisce roadmap incrementale, ordine di implementazione e stato.
- `docs/workflow.md` definisce come l'IA deve lavorare.
- `docs/decisions.md` traccia solo decisioni significative.
- I prompt `8 activation prompt` avviano lo sviluppo e non modificano la responsabilità dei documenti in `docs/`.

Ogni prompt deve generare esclusivamente il proprio output. Quando un'informazione appartiene a un altro documento, usa un riferimento invece di duplicarla.

## Uso rapido

1. Crea `docs/vision.md` con la visione iniziale del progetto.
2. Esegui `1 requirements template prompt.md`.
3. Esegui `2 requirements prompt.md`.
4. Esegui `3 architecture prompt.md`.
5. Esegui `4 design prompt.md` solo se il progetto richiede frontend, UI o UX.
6. Esegui `4.1 optional design logo prompt.md` solo se serve logo, brand asset o identità visiva.
7. Esegui `5 security prompt.md`.
8. Esegui `6 tasks prompt.md`.
9. Esegui `7 workflow prompt.md`.
10. Scegli una modalità tra `8 activation prompt - soft.md`, `8 activation prompt - balanced.md` e `8 activation prompt - autonomous.md`.
11. Avvia il coding agent con il prompt scelto e usa i documenti generati in `docs/` come base operativa per lo sviluppo assistito da IA.
