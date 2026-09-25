# Obiettivo

Crea `docs/tasks.md` trasformando i documenti di progetto in una roadmap incrementale e ordinata. Ogni task deve produrre un risultato osservabile, avere confini chiari e poter essere verificato oggettivamente.

# Fonti

Obbligatorie:

- `docs/vision.md`;
- `docs/requirements.md`;
- `docs/architecture.md`;
- `docs/security.md`.

Opzionali:

- `docs/design.md`, se presente;
- `docs/decisions.md`, se presente;
- repository esistente, se disponibile, come evidenza dello stato corrente.

Se manca una fonte obbligatoria, non generare il documento: indica esattamente cosa serve per procedere.

# Policy decisionale

- Ordina il lavoro per valore utilizzabile, dipendenze, riduzione del rischio e facilità di verifica.
- Preferisci vertical slice funzionanti a interi layer privi di risultato osservabile.
- Procedi autonomamente nella scomposizione quando l'ordine deriva chiaramente dalle dipendenze.
- Dichiara assunzioni che influenzano priorità, stato o sequenza.
- Chiedi chiarimenti solo quando priorità di prodotto o dipendenze sostanziali non possono essere dedotte dalle fonti.
- Non introdurre funzionalità, refactoring o infrastruttura non giustificati.

# Modifiche consentite

- Crea o aggiorna esclusivamente `docs/tasks.md`.
- Non modificare codice, configurazione o altri documenti.
- Se non puoi scrivere nel filesystem, restituisci il contenuto completo del documento e segnala che non è stato salvato.

# Struttura richiesta

Adatta la struttura al progetto e ometti categorie non applicabili.

1. **Obiettivo dell'MVP**: risultato minimo utilizzabile e requisiti coperti.
2. **Strategia di esecuzione**: criteri di ordinamento e dipendenze principali.
3. **Milestone incrementali**: ciascuna lascia il sistema in uno stato coerente e verificabile.
4. **Task ordinati**: usare il formato seguente.
5. **Debito tecnico**: solo rinvii consapevoli, identificati come `DEBT-001` e motivati.
6. **Evoluzioni future**: solo elementi esplicitamente fuori dall'MVP, identificati come `FUTURE-001`.

```md
### TASK-001 — Titolo orientato al risultato

- Stato: TODO | IN_PROGRESS | DONE | BLOCKED | DEFERRED
- Priorità: MUST | SHOULD | COULD
- Risultato: comportamento o artefatto osservabile prodotto dal task
- Ambito: confini inclusi ed eventuali esclusioni necessarie
- Dipendenze: task o prerequisiti, solo se presenti
- Riferimenti: requisiti, rischi, decisioni e documenti applicabili
- Completato quando:
  - criterio oggettivo
- Verifica:
  - test, comando o controllo capace di rilevare realisticamente un errore
- Note: soltanto assunzioni, blocchi o indicazioni non rappresentate altrove
```

# Regole di scomposizione

Un task è sufficientemente piccolo quando:

- produce un solo risultato osservabile;
- ha uno scope tecnico circoscritto;
- ha dipendenze esplicite;
- può essere completato senza decisioni progettuali nascoste;
- possiede criteri oggettivi di completamento;
- può essere verificato con un test, un comando o un controllo definito.

Se un task non soddisfa questi criteri, suddividilo per risultato o vertical slice. Non usare stime temporali come criterio di dimensionamento.

# Stati e aggiornamento

- Usa `DONE` solo quando esiste evidenza che criteri e verifiche siano soddisfatti.
- In un progetto nuovo, i task iniziano normalmente come `TODO`, `BLOCKED` o `DEFERRED`.
- In un progetto esistente, assegna stati sulla base di evidenze nel repository; se non puoi verificarle, non presumere `DONE`.
- Motiva `BLOCKED` indicando condizione e informazione necessaria per sbloccarlo.
- Motiva `DEFERRED` indicando perché il rinvio è accettabile.
- Integra sicurezza, logging, documentazione e accessibilità nei task pertinenti invece di relegarli automaticamente a una fase finale.

# Criteri di riuscita

- L'ordine è eseguibile dal primo task disponibile all'ultimo senza dipendenze implicite.
- Ogni requisito `MUST` è coperto da almeno un task oppure motivatamente già soddisfatto.
- Ogni rischio prioritario possiede un task o un criterio di completamento che ne implementa la mitigazione.
- Ogni task ha un risultato, criteri di completamento e una verifica concreta.
- Le milestone producono incrementi utilizzabili o tecnicamente verificabili.
- Non sono presenti task generici come "implementare backend", "fare sicurezza" o "scrivere test".
- Il documento rappresenta sia la roadmap sia lo stato corrente del lavoro.
- Il testo è in italiano e codificato in UTF-8, salvo richiesta esplicita diversa.

# Verifica finale

Prima di terminare:

1. controlla copertura e tracciabilità di requisiti e rischi;
2. cerca dipendenze circolari, salti logici e task troppo ampi;
3. verifica che ogni task abbia un solo risultato osservabile;
4. elimina attività non richieste o verifiche sproporzionate;
5. correggi direttamente ordine, scope e criteri insufficienti.
