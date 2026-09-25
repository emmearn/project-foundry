# Project Foundry

Project Foundry è un framework di prompt per trasformare una visione iniziale in documentazione operativa e guidare lo sviluppo assistito da IA.

Il repository non contiene codice applicativo. Contiene sette prompt autosufficienti, pensati per essere eseguiti in ordine tramite copia-incolla con un coding agent. Ogni prompt produce un documento o avvia una fase precisa, senza richiedere template esterni.

## Principi

- Una responsabilità principale per ogni documento.
- Istruzioni dirette, confini decisionali espliciti e criteri di riuscita verificabili.
- Assunzioni consentite solo per scelte reversibili e a basso impatto.
- Chiarimenti richiesti soltanto quando cambiano materialmente il risultato.
- Documenti compatti, senza duplicazioni o sezioni compilate per completezza.
- Verifiche proporzionate al rischio e alla modifica.
- Italiano e UTF-8, salvo richiesta esplicita diversa.

## File

```text
01-requirements-prompt.md
02-architecture-prompt.md
03-visual-design-optional-prompt.md
04-security-prompt.md
05-tasks-prompt.md
06-workflow-prompt.md
07-activation-prompt.md
README.md
```

I numeri rappresentano l'ordine di esecuzione. Il passaggio `03` è opzionale: saltalo quando il progetto non richiede UI, UX, identità visiva, logo o altri asset di brand.

## Input iniziale

Prima di eseguire i prompt, crea `docs/vision.md`.

La vision può essere scritta liberamente, ma dovrebbe descrivere almeno:

- problema e risultato desiderato;
- utenti o soggetti interessati;
- ambito e vincoli già noti;
- contesto di dominio;
- eventuali riferimenti o preferenze;
- se applicabile, stato del progetto esistente e aspetti da preservare o modificare.

`docs/vision.md` è il contesto originario, non la specifica finale. I prompt successivi trasformano la vision in documenti operativi e segnalano le ambiguità che cambierebbero materialmente il risultato.

## Ordine di esecuzione

```text
docs/vision.md
      ↓
01 Requirements
      ↓
02 Architecture
      ↓
03 Visual design e logo, opzionale
      ↓
04 Security
      ↓
05 Tasks
      ↓
06 Workflow
      ↓
07 Activation
```

## Prompt e output

| Fase | Fonti principali | Output | Note |
|---|---|---|---|
| `01 Requirements` | vision e contesto utente | `docs/requirements.md` | Contiene direttamente il template dei requisiti. |
| `02 Architecture` | vision e requirements | `docs/architecture.md` | Distingue progetto nuovo o esistente dalle fonti e dal repository disponibile. |
| `03 Visual design` | vision, requirements e architecture | `docs/design.md`, eventuali `assets/logo/` | Eseguire solo quando servono UI, UX o identità visiva. Il logo non viene generato automaticamente per ogni frontend. |
| `04 Security` | vision, requirements, architecture ed eventuale design | `docs/security.md` | Parte da asset, dati, attori, confini di fiducia e minacce reali. |
| `05 Tasks` | tutti i documenti progettuali applicabili | `docs/tasks.md` | Produce milestone e task ordinati, osservabili e verificabili. |
| `06 Workflow` | documenti precedenti ed eventuali decisioni | `docs/workflow.md` | Definisce come il coding agent deve operare durante lo sviluppo. |
| `07 Activation` | workflow, tasks e documenti pertinenti | codice, test e aggiornamenti previsti dal workflow | Avvia lo sviluppo con il livello di autonomia scelto. |

## Documenti generati

Il flusso completo può produrre:

```text
docs/
├── vision.md          # input umano
├── requirements.md    # comportamento atteso
├── architecture.md    # struttura e scelte tecniche
├── design.md          # solo se serve una fase visuale
├── security.md        # rischi, controlli e vincoli
├── tasks.md           # roadmap e stato del lavoro
├── workflow.md        # comportamento operativo del coding agent
└── decisions.md       # creato quando emerge la prima decisione significativa

assets/
└── logo/              # solo se logo o identità visiva sono richiesti
```

## Responsabilità dei documenti

- `vision.md` conserva l'intenzione e il contesto originari.
- `requirements.md` definisce il comportamento atteso, l'ambito e i criteri di accettazione.
- `architecture.md` definisce struttura, componenti, dati, integrazioni e convenzioni tecniche.
- `design.md` definisce esperienza, sistema visuale e uso degli asset quando necessari.
- `security.md` collega asset e minacce a controlli e verifiche proporzionati.
- `tasks.md` definisce ordine, dipendenze, completamento e stato del lavoro.
- `workflow.md` definisce come selezionare il contesto, implementare, verificare e aggiornare i documenti.
- `decisions.md` conserva decisioni significative e trade-off non ovvi.

I documenti descrivono lo stato desiderato e le decisioni approvate. Il repository mostra lo stato implementato; test e verifiche forniscono evidenza del comportamento osservato. Il workflow stabilisce come gestire eventuali conflitti senza presumere automaticamente che una fonte sia corretta.

## Fase visuale opzionale

Esegui `03-visual-design-optional-prompt.md` quando serve almeno uno dei seguenti elementi:

- interfaccia utente;
- esperienza o flusso UX;
- sistema visuale;
- logo o identità di brand;
- asset grafici ufficiali.

Il prompt decide gli output applicabili sulla base della vision e dei requisiti:

- UI/UX senza branding: genera soltanto `docs/design.md`;
- UI/UX con identità visiva richiesta: genera design e asset necessari;
- solo identità visiva: genera un `docs/design.md` minimale e gli asset supportati;
- nessuna esigenza visuale: non modifica file e segnala che la fase può essere saltata.

## Task e avanzamento

`docs/tasks.md` è sia roadmap sia stato corrente del lavoro. Un task è sufficientemente piccolo quando produce un solo risultato osservabile, ha scope e dipendenze chiari e possiede una verifica concreta. Non vengono usate stime temporali per determinare la dimensione dei task.

Stati disponibili:

```text
TODO
IN_PROGRESS
DONE
BLOCKED
DEFERRED
```

Un task può diventare `DONE` solo quando criteri di completamento e verifiche applicabili sono soddisfatti.

## Workflow di sviluppo

`06-workflow-prompt.md` genera sempre `docs/workflow.md`. Il workflow non obbliga il coding agent a leggere ogni documento prima di ogni modifica: seleziona il contesto in base al lavoro corrente.

In generale:

- requirements e tasks guidano modifiche funzionali;
- architecture guida struttura, dati, dipendenze e integrazioni;
- security guida cambiamenti che coinvolgono privilegi, dati sensibili, input esterni o rischio;
- design guida UI, UX, componenti e asset visuali;
- decisions conserva scelte significative già assunte;
- vision viene consultata quando serve il contesto originario.

Il framework non richiede agenti persistenti. Il coding agent applica durante il lavoro le competenze necessarie alla modifica corrente.

## Attivazione e autonomia

Prima di eseguire `07-activation-prompt.md`, imposta un solo parametro:

```yaml
autonomy: soft
```

Valori consentiti:

- `soft`: esegue un task, verifica, aggiorna lo stato e attende conferma;
- `balanced`: esegue un piccolo gruppo coerente di task, verifica e attende conferma;
- `autonomous`: prosegue attraverso tutti i task eseguibili e si ferma solo a completamento o davanti a un blocco reale.

Il parametro è obbligatorio. Non esistono altri parametri di avanzamento: unità di lavoro e punto di arresto derivano direttamente dalla modalità scelta.

## Decisioni di progetto

`docs/decisions.md` non deve esistere all'avvio. Viene creato quando emerge la prima decisione significativa, non per scelte locali o facilmente reversibili.

Formato minimo:

```text
DEC-001
- Data:
- Stato: Proposed | Accepted | Superseded | Deprecated
- Contesto:
- Decisione:
- Motivazione:
- Alternative considerate:
- Impatto:
- Collegamenti:
```

## Uso rapido

1. Crea `docs/vision.md`.
2. Esegui `01-requirements-prompt.md`.
3. Esegui `02-architecture-prompt.md`.
4. Esegui `03-visual-design-optional-prompt.md` se il progetto richiede una fase visuale.
5. Esegui `04-security-prompt.md`.
6. Esegui `05-tasks-prompt.md`.
7. Esegui `06-workflow-prompt.md`.
8. Imposta `autonomy` in `07-activation-prompt.md`.
9. Esegui il prompt di attivazione per iniziare lo sviluppo.
