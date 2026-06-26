Prompt per generare docs/tasks.md

Agisci come Technical Project Manager senior.

Input: docs/requirements.md, docs/architecture.md, docs/security.md e docs/design.md se presente. Genera esclusivamente docs/tasks.md in Markdown, in versione compatta, isolata, senza duplicazioni, ottimizzata per IA di coding e massimo rapporto informazioni/token.

Scopo del documento
Definire solo roadmap incrementale, ordine di implementazione, avanzamento del progetto e task verificabili. Questo file è la fonte di verità dell'ordine di lavoro e dello stato dei task.

Struttura richiesta
1. Strategia MVP: minimo indispensabile per una prima versione utilizzabile, collegato ai requisiti.
2. Criteri di ordinamento: valore utente, dipendenze tecniche, riduzione rischio, semplicità di verifica.
3. Milestone incrementali: ogni milestone lascia il sistema funzionante.
4. Stato avanzamento: tasks.md deve essere aggiornabile durante il progetto e deve indicare chiaramente quali task sono da fare, in corso, completati, bloccati o rimandati.
5. Task: attività piccole, indipendenti, delegabili e completabili in meno di mezza giornata.
6. Formato task: ID TASK-001, stato TODO/IN_PROGRESS/DONE/BLOCKED/DEFERRED, descrizione, priorità MUST/SHOULD/COULD, dipendenze, requisiti collegati, documenti di riferimento, criteri di completamento, verifica/test, documentazione del codice essenziale e README.md aggiornati dove rilevante.
7. Regole di aggiornamento: quando un task avanza, aggiornare il suo stato; quando viene completato, segnare DONE solo se criteri di completamento e verifica sono soddisfatti; se è bloccato, indicare il motivo minimo; se è rinviato, segnare DEFERRED e motivare brevemente.
8. Vertical slices: preferire incrementi funzionali completi rispetto a layer completi non utilizzabili.
9. Testing: unit, integration e UI test quando rilevanti.
10. Sicurezza: integrare docs/security.md nei task pertinenti, non solo in una fase finale.
11. Debito tecnico: sezione DEBT-001 per rinvii accettabili.
12. Funzionalità future: sezione FUTURE-001 per evoluzioni non necessarie all'MVP.
13. Tracciabilità: collegare task a requisiti e decisioni future quando utile.

Ordine preferito, se coerente col progetto
Setup, core domain, funzionalità essenziali, persistenza se necessaria, API/interfacce, error handling, sicurezza, UI se presente, osservabilità, hardening, ottimizzazioni, funzionalità accessorie.

Regole
- Non generare codice, requirements, architecture, design, security, workflow o agents.
- Non introdurre funzionalità non richieste.
- Non duplicare contenuti degli altri documenti.
- Ogni task deve avere criteri oggettivi di completamento e verifica.
- I criteri di completamento devono includere documentazione del codice essenziale aggiornata dove rilevante.
- I criteri di completamento devono includere README.md aggiornato quando cambiano setup, comandi, configurazione, modalità d'uso, funzionalità principali, stato MVP o informazioni necessarie a un nuovo lettore.
- Ogni task deve avere uno stato esplicito e aggiornabile.
- Non usare tasks.md come semplice backlog statico: deve rappresentare anche l'avanzamento corrente del progetto.
- Non segnare un task come DONE senza evidenza di completamento e verifica.
- Rimanda ciò che non serve al valore principale.
