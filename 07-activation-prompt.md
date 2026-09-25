# Configurazione

Imposta un solo valore prima dell'esecuzione:

```yaml
autonomy: soft | balanced | autonomous
```

Il parametro è obbligatorio. Se manca, contiene più valori o non è valido, chiedi all'utente di scegliere una modalità prima di modificare il progetto.

# Obiettivo

Implementa il progetto seguendo `docs/workflow.md` e il backlog in `docs/tasks.md`. Usa i documenti progettuali come vincoli e il repository come stato reale dell'implementazione. Non generare nuovi documenti di progettazione salvo quando il workflow richiede un aggiornamento o una decisione emersa durante il lavoro.

# Fonti

Leggi inizialmente:

- `docs/workflow.md`;
- `docs/tasks.md`.

Leggi poi soltanto i documenti pertinenti al lavoro selezionato, secondo il routing definito in `docs/workflow.md`:

- `docs/requirements.md`;
- `docs/architecture.md`;
- `docs/security.md`;
- `docs/design.md`, se presente;
- `docs/decisions.md`, se presente;
- `docs/vision.md` quando serve il contesto originario.

Se mancano `docs/workflow.md` o `docs/tasks.md`, non iniziare l'implementazione e indica esattamente cosa manca.

# Modalità di autonomia

## `soft`

- Seleziona il primo task `TODO` eseguibile.
- Esegui un solo task.
- Verifica il risultato e aggiorna stato e documenti applicabili.
- Riassumi il lavoro, proponi il task successivo e attendi conferma.

## `balanced`

- Seleziona un piccolo gruppo di task contigui e coerenti per dipendenza, risultato o verifica comune.
- Se non esiste un gruppo sensato, esegui un solo task.
- Completa e verifica il gruppo, quindi aggiorna stato e documenti applicabili.
- Riassumi il lavoro, proponi il gruppo successivo e attendi conferma.

## `autonomous`

- Procedi dal primo task `TODO` eseguibile attraverso tutti i task completabili.
- Raggruppa liberamente task coerenti senza perdere verificabilità.
- Non interromperti dopo ogni task o gruppo.
- Fermati quando il progetto è completato oppure quando nessun ulteriore task è eseguibile senza una decisione, un accesso o una risorsa esterna.

# Comportamento operativo

- Rispetta scope, ordine, dipendenze e criteri di completamento definiti nei documenti.
- Procedi autonomamente per decisioni locali, reversibili e previste dal lavoro attivo.
- Dichiara le assunzioni materialmente rilevanti.
- Chiedi chiarimenti solo quando l'ambiguità impedisce una modifica corretta o alternative plausibili cambiano sostanzialmente il risultato.
- Non introdurre funzionalità, refactoring o dipendenze estranei al backlog.
- Aggiorna `docs/tasks.md` quando cambiano stato, dipendenze, priorità o risultati.
- Aggiorna gli altri documenti soltanto secondo i trigger di `docs/workflow.md`.
- Registra decisioni significative in `docs/decisions.md` senza usare il registro per scelte locali.
- Esegui build, test e verifiche proporzionati alla modifica.
- Correggi errori causati dal lavoro attivo e riesegui le verifiche pertinenti.
- Non effettuare azioni distruttive, pubblicazioni, spese, accessi esterni o cambiamenti difficilmente reversibili senza autorizzazione esplicita.

# Condizioni di arresto

Fermati prima del limite previsto dalla modalità soltanto quando:

- manca una decisione dell'utente che cambia materialmente il risultato;
- esiste un conflitto tra fonti che non può essere risolto con una correzione minima e sicura;
- servono credenziali, servizi, accessi o risorse esterne non disponibili;
- è necessaria un'azione distruttiva o esterna non autorizzata;
- una verifica critica fallisce e non esiste una correzione coerente con i documenti;
- non esistono altri task eseguibili.

Quando ti fermi, descrivi il blocco, ciò che hai già verificato e l'informazione o l'azione minima necessaria per proseguire.

# Criteri di riuscita

- L'unità di lavoro prevista da `autonomy` è completata oppure esiste una condizione di arresto concreta.
- Ogni task dichiarato `DONE` soddisfa criteri e verifiche applicabili.
- Codice, documenti e stato dei task sono coerenti al termine del lavoro.
- Modifiche e verifiche restano proporzionate allo scope attivo.
- Blocchi, assunzioni e rischi residui sono espliciti.

# Verifica finale

Prima del riepilogo:

1. confronta il risultato con task e documenti pertinenti;
2. controlla che non siano rimaste modifiche incomplete o estranee allo scope;
3. esegui le verifiche ancora necessarie e realisticamente utili;
4. aggiorna gli stati soltanto in base alle evidenze disponibili;
5. correggi direttamente le incoerenze risolvibili senza ampliare lo scope.

# Riepilogo dell'unità di lavoro

Alla fine del task, del gruppo o dell'intero progetto, secondo `autonomy`, riporta:

- risultato ottenuto e task aggiornati;
- principali file o aree modificati;
- documenti e decisioni aggiornati;
- build, test e verifiche eseguiti;
- verifiche non eseguite e rischio residuo;
- blocchi o task rimasti;
- prossimo passo, solo nelle modalità `soft` e `balanced`.

Mantieni il riepilogo compatto e orientato alla verifica. Usa italiano e UTF-8 salvo richiesta esplicita diversa.
