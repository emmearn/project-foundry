# Project Foundry

Project Foundry è un framework di prompt per trasformare una visione iniziale in documentazione operativa compatta per progetti di vibe coding e sviluppo assistito da IA.

Il repository non contiene codice applicativo: contiene una sequenza di prompt e una guida per generare documenti di progetto coerenti, isolati e ottimizzati per AI coding assistant.

## Scopo

Il framework produce una catena documentale ordinata:

- visione iniziale;
- requisiti;
- architettura;
- design UI/UX, se necessario;
- logo e regole minime di utilizzo, se necessario;
- sicurezza;
- task di implementazione;
- workflow operativo per l'IA.

La documentazione generata diventa la fonte di verità del progetto. Ogni prompt produce un solo documento o gruppo di artefatti e non deve duplicare responsabilità già assegnate ad altri documenti.

## Principio Di Compattezza

Tutti i prompt e tutti i documenti generati devono essere compatti, operativi e ottimizzati per IA di coding: alta densità informativa, nessuna ridondanza, nessuna sezione compilata solo per completezza, riferimenti ad altri documenti invece di duplicazioni.

## File Del Framework

```text
0 framework guide - no prompt.md
1 requirements template prompt.md
2 requirements prompt.md
3 architecture prompt.md
4 design prompt.md
4.1 optional design logo prompt.md
5 security prompt.md
6 tasks prompt.md
7 workflow prompt.md
```

`0 framework guide - no prompt.md` è una guida per l'utente umano. Non è un prompt da eseguire.

I file numerati da `1` a `7` vanno usati in ordine. Il prompt `4.1 optional design logo prompt.md` è opzionale e va eseguito subito dopo `4 design prompt.md` quando il progetto richiede un logo o una identità visiva.

## Workflow

Ordine consigliato:

```text
docs/vision.md
   -> 1 requirements template prompt
   -> 2 requirements prompt
   -> 3 architecture prompt
   -> 4 design prompt opzionale
   -> 4.1 optional design logo prompt opzionale
   -> 5 security prompt
   -> 6 tasks prompt
   -> 7 workflow prompt
```

`docs/vision.md` è l'input umano iniziale del sistema. Può contenere idea, obiettivo, contesto, vincoli, desideri, esempi o note grezze. Non sostituisce i documenti generati: li alimenta.

## Punto 7

`7 workflow prompt.md` genera sempre il Document-Driven Workflow.

Il framework non crea agenti di sviluppo persistenti: l'AI coding assistant usa `docs/workflow.md` e i documenti in `docs/` come guida operativa.

## Output Attesi

Il framework può generare:

```text
docs/
  vision.md                 # scritto da esseri umani
  requirements_template.md
  requirements.md
  architecture.md
  design.md
  security.md
  tasks.md
  workflow.md
  decisions.md              # creato o aggiornato dall'IA quando serve

assets/
  logo/                     # creato solo se si esegue il prompt 4.1
```

`docs/design.md` viene creato solo se il progetto prevede UI, UX o frontend.

`assets/logo/` viene creato solo se viene eseguito `4.1 optional design logo prompt.md`. In quel caso `docs/design.md` deve includere le regole minime di utilizzo del logo ufficiale.

`docs/decisions.md` non deve esistere per forza all'avvio: l'IA lo crea alla prima decisione significativa e lo aggiorna durante lo sviluppo.

## Uso Rapido

1. Crea `docs/vision.md` con la visione iniziale del progetto.
2. Apri `0 framework guide - no prompt.md` e segui l'ordine indicato.
3. Esegui i prompt da `1` a `6` nell'ordine, eseguendo `4.1` solo se serve un logo.
4. Esegui `7 workflow prompt.md`.
5. Usa i documenti generati in `docs/` come base operativa per lo sviluppo.

## Principi

- Mantieni i documenti compatti.
- Evita duplicazioni tra file.
- Mantieni una sola fonte di verità per ogni informazione.
- Aggiorna la documentazione solo quando cambia una decisione o un vincolo reale.
- Usa `docs/vision.md` come input umano iniziale.
- Usa `docs/decisions.md` per decisioni significative emerse durante progetto e sviluppo.
- Usa i documenti generati come contesto principale per l'IA di coding.
