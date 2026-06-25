Prompt per generare docs/tasks.md

Agisci come Technical Project Manager senior.

Input: docs/requirements.md, docs/architecture.md, docs/security.md e docs/design.md se presente. Genera esclusivamente docs/tasks.md in Markdown, in versione compatta, isolata, senza duplicazioni, ottimizzata per IA di coding e massimo rapporto informazioni/token.

Scopo del documento
Definire solo roadmap incrementale, ordine di implementazione e task verificabili. Questo file è la fonte di verità dell'ordine di lavoro.

Struttura richiesta
1. Strategia MVP: minimo indispensabile per una prima versione utilizzabile, collegato ai requisiti.
2. Criteri di ordinamento: valore utente, dipendenze tecniche, riduzione rischio, semplicità di verifica.
3. Milestone incrementali: ogni milestone lascia il sistema funzionante.
4. Task: attività piccole, indipendenti, delegabili e completabili in meno di mezza giornata.
5. Formato task: ID TASK-001, descrizione, priorità MUST/SHOULD/COULD, dipendenze, requisiti collegati, documenti di riferimento, criteri di completamento, verifica/test.
6. Vertical slices: preferire incrementi funzionali completi rispetto a layer completi non utilizzabili.
7. Testing: unit, integration e UI test quando rilevanti.
8. Sicurezza: integrare docs/security.md nei task pertinenti, non solo in una fase finale.
9. Debito tecnico: sezione DEBT-001 per rinvii accettabili.
10. Funzionalità future: sezione FUTURE-001 per evoluzioni non necessarie all'MVP.
11. Tracciabilità: collegare task a requisiti e decisioni future quando utile.

Ordine preferito, se coerente col progetto
Setup, core domain, funzionalità essenziali, persistenza se necessaria, API/interfacce, error handling, sicurezza, UI se presente, osservabilità, hardening, ottimizzazioni, funzionalità accessorie.

Regole
- Non generare codice, requirements, architecture, design, security, workflow o agents.
- Non introdurre funzionalità non richieste.
- Non duplicare contenuti degli altri documenti.
- Ogni task deve avere criteri oggettivi di completamento e verifica.
- Rimanda ciò che non serve al valore principale.
