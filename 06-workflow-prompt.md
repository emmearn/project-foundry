# Obiettivo

Crea `docs/workflow.md` definendo il comportamento operativo del coding agent durante l'implementazione. Il workflow deve usare i documenti di progetto in modo selettivo, mantenere la coerenza tra intenzione e stato reale e guidare esecuzione, verifica e aggiornamento senza duplicare i contenuti degli altri documenti.

# Fonti

Obbligatorie:

- `docs/vision.md`;
- `docs/requirements.md`;
- `docs/architecture.md`;
- `docs/security.md`;
- `docs/tasks.md`.

Opzionali:

- `docs/design.md`, se presente;
- `docs/decisions.md`, se presente;
- repository esistente, se disponibile.

Se manca una fonte obbligatoria, non generare il documento: indica esattamente cosa serve per procedere.

# Policy decisionale

- Definisci regole comuni e durevoli; non copiare requisiti, scelte architetturali, controlli o task.
- Procedi autonomamente per regole operative reversibili e coerenti con le fonti.
- Dichiara assunzioni che cambiano il livello di autonomia o le condizioni di arresto.
- Chiedi chiarimenti solo quando le fonti impongono comportamenti operativi incompatibili.
- Privilegia istruzioni applicabili e verificabili rispetto a formule generiche.

# Modifiche consentite

- Crea o aggiorna esclusivamente `docs/workflow.md`.
- Non modificare codice, configurazione o altri documenti.
- Non creare agenti persistenti o prompt aggiuntivi.
- Se non puoi scrivere nel filesystem, restituisci il contenuto completo del documento e segnala che non è stato salvato.

# Contenuto richiesto

Genera un workflow compatto che includa i punti seguenti.

## 1. Autorità delle fonti

- I documenti descrivono comportamento desiderato, vincoli e decisioni approvate.
- Codice, configurazione e migrazioni mostrano lo stato implementato.
- Test e verifiche forniscono evidenza del comportamento osservato.
- In caso di conflitto, il coding agent deve segnalarlo, determinarne l'impatto e proporre la correzione minima; non deve presumere automaticamente che una fonte sia corretta.

## 2. Lettura contestuale

Definisci quali documenti leggere in base alla modifica:

- comportamento o dominio: requirements e task;
- struttura, dipendenze, dati o integrazioni: architecture;
- autenticazione, autorizzazione, dati sensibili, input esterni o rischio: security;
- UI, UX, componenti o asset visuali: design, se presente;
- decisioni significative già assunte: decisions, se presente;
- vision solo quando serve il contesto originario o gli altri documenti non risolvono un dubbio.

Non imporre la lettura integrale di tutti i documenti prima di ogni modifica.

## 3. Selezione ed esecuzione del lavoro

- Usa `docs/tasks.md` come ordine operativo e stato del lavoro.
- Limita lo scope al task o al gruppo attivo.
- Motiva salti nell'ordine solo quando dipendenze, rischio o verifica li rendono utili.
- Mantieni il sistema coerente dopo ogni incremento significativo.
- Non introdurre funzionalità o refactoring estranei al risultato richiesto.

## 4. Confini decisionali

- Procedi senza chiedere conferma per azioni locali, reversibili, previste dal task e prive di impatto esterno significativo.
- Dichiara assunzioni materialmente rilevanti.
- Fermati per decisioni di prodotto o architettura con alternative sostanziali, conflitti non risolvibili, credenziali mancanti, azioni distruttive, costi o cambiamenti esterni non autorizzati.
- Non introdurre approvazioni o avvisi per rischi puramente ipotetici.

## 5. Aggiornamento dei documenti

Definisci trigger precisi:

- requirements quando cambia il comportamento atteso;
- architecture quando cambiano struttura, stack, dati, componenti o integrazioni;
- security quando cambiano minacce, dati, privilegi o controlli;
- design quando cambiano flussi UI, sistema visuale, componenti o asset;
- tasks quando cambiano stato, ordine, dipendenze o scope;
- decisions per scelte significative e trade-off non ovvi;
- README quando cambiano setup, comandi, configurazione, uso o informazioni necessarie a un nuovo lettore.

Non aggiornare documenti senza una variazione reale e non duplicare informazioni tra essi.

## 6. Decisioni

- `docs/decisions.md` è creato alla prima decisione significativa, non per scelte locali o facilmente reversibili.
- Usa un formato minimo con ID, data, stato, contesto, decisione, motivazione, alternative, impatto e collegamenti.
- Aggiorna o supera decisioni precedenti senza cancellarne la storia.

## 7. Implementazione e qualità

- Segui le convenzioni del repository e le dipendenze consentite.
- Mantieni le modifiche semplici, leggibili e compatibili con lo scope.
- Commenta soltanto logica non immediata, vincoli, trade-off o comportamenti sorprendenti.
- Applica logging tecnico e vincoli di sicurezza definiti nei documenti pertinenti.
- Per il frontend, rispetta `docs/design.md` e gli asset ufficiali quando presenti.

## 8. Verifica proporzionata

- Esegui la verifica più piccola capace di rilevare realisticamente un errore introdotto dalla modifica.
- Usa unit test per logica isolata, integration test per confini reali e regression test per bug quando aggiungono protezione significativa.
- Amplia o ripeti i test solo in presenza di fallimenti, rischio elevato, cambiamenti trasversali o dubbi irrisolti.
- Se una verifica necessaria non è eseguibile, indica motivo, rischio residuo e comando o condizione per completarla.
- Considera un task `DONE` solo quando criteri e verifiche applicabili sono soddisfatti.

## 9. Completamento e comunicazione

Al termine dell'unità di lavoro, riporta in modo compatto:

- risultato ottenuto;
- file o aree modificati;
- test e verifiche eseguiti;
- documenti aggiornati;
- assunzioni e decisioni significative;
- blocchi, verifiche mancanti e rischi residui;
- prossimo lavoro previsto, quando richiesto dalla modalità di autonomia.

# Criteri di riuscita

- Il workflow è utilizzabile da un coding agent senza rileggere istruzioni duplicate.
- La selezione dei documenti è contestuale alla modifica.
- I confini tra autonomia e richiesta di intervento sono espliciti.
- Documentazione desiderata, stato implementato ed evidenze di verifica rimangono distinti.
- Testing e aggiornamenti documentali sono proporzionati alla modifica.
- Il workflow non contiene dettagli progettuali già presenti nelle fonti.
- Il testo è in italiano e codificato in UTF-8, salvo richiesta esplicita diversa.

# Verifica finale

Prima di terminare:

1. cerca regole duplicate o in conflitto con i documenti sorgente;
2. verifica che ogni istruzione indichi quando si applica;
3. elimina obblighi di lettura, test o aggiornamento indiscriminati;
4. controlla che condizioni di arresto e completamento siano operative;
5. correggi direttamente ambiguità e ridondanze.
