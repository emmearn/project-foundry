Agisci come AI Coding Workflow Architect.

Input: `docs/vision.md` se presente, `docs/requirements_template.md`, `docs/requirements.md`, `docs/architecture.md`, `docs/security.md`, `docs/tasks.md`, `docs/design.md` se presente e `docs/decisions.md` se presente. Genera esclusivamente `docs/workflow.md` in Markdown, in versione compatta, isolata, senza duplicazioni, ottimizzata per IA di coding e massimo rapporto informazioni/token.

## Output Contract

Input richiesti:
- `docs/vision.md`, se presente.
- `docs/requirements_template.md`.
- `docs/requirements.md`.
- `docs/architecture.md`.
- `docs/security.md`.
- `docs/tasks.md`.
- `docs/design.md`, se presente.
- `docs/decisions.md`, se presente.

Output prodotto:
- `docs/workflow.md`.
- Regole operative del Document-Driven Workflow.
- Validazione finale della coerenza documentale.
- Responsabilità operative su task, documenti, decisioni, test, sicurezza, UI, logging e README.

Non deve produrre:
- requisiti;
- architettura;
- design;
- sicurezza;
- roadmap;
- prompt riutilizzabili;
- codice applicativo;
- `agents/`.

## Scopo Del Documento

Definire solo il comportamento operativo dell'IA nel Document-Driven Workflow. Non generare requisiti, architettura, sicurezza, roadmap, agenti o prompt riutilizzabili.

## Contesto

- Questo prompt è il punto 7 del framework.
- Genera sempre il Document-Driven Workflow.
- Non creare `agents/`.

## Principi Vincolanti

- `docs/` è l'unica fonte di verità.
- Ogni richiesta parte dalla lettura dei documenti rilevanti.
- Non esistono agenti persistenti.
- L'IA assume dinamicamente il ruolo necessario: architect, developer, reviewer, security, designer o altro.
- Mantieni una sola fonte di verità: rimanda ai documenti invece di duplicarne il contenuto.
- Limita sempre lo scope alla richiesta o al task corrente.

## Struttura Richiesta Di `docs/workflow.md`

1. Workflow Overview
   - Definire il Document-Driven Workflow.
   - Stabilire che i documenti guidano ogni decisione.
   - Esplicitare che non esistono agenti persistenti.
   - Esplicitare che l'IA assume dinamicamente il ruolo più adatto.

2. Startup Workflow
   - Prima di qualsiasi modifica leggere `docs/requirements.md`, `docs/architecture.md`, `docs/security.md` e `docs/tasks.md`.
   - Leggere `docs/design.md` se presente o se la richiesta riguarda UI/UX/frontend.
   - Leggere `docs/decisions.md` se presente.
   - Usare `docs/vision.md` come contesto iniziale quando presente.
   - Usare `docs/requirements_template.md` solo quando si interpretano o aggiornano requisiti.
   - Identificare requisiti, task, vincoli architetturali e vincoli di sicurezza applicabili.
   - Se i documenti sono incoerenti, fermarsi e proporre la correzione documentale minima.

3. Pipeline Validation
   - Verificare che ogni documento richiesto esista o sia esplicitamente non necessario.
   - Verificare coerenza tra requisiti, architettura, design, sicurezza e task.
   - Verificare che `docs/tasks.md` sia ordinato e sviluppabile dal primo task all'ultimo.
   - Verificare che eventuali logo asset in `assets/logo/` siano richiamati da `docs/design.md`.
   - Verificare che decisioni significative siano registrate in `docs/decisions.md` o proposte per la registrazione.
   - Verificare assenza di duplicazioni evidenti e conflitti tra fonti di verità.

4. Development Workflow
   - Rispettare requirements, architecture, security, design se presente e tasks.
   - Implementare solo ciò che serve alla richiesta o al task corrente.
   - Quando la richiesta è generica o riguarda avanzamento progetto, proporre il prossimo task `TODO` eseguibile in `docs/tasks.md`.
   - Se utile, proporre un mini blocco di task contigui o fortemente collegati, motivando perché conviene eseguirli insieme.
   - Ogni salto nell'ordine dei task richiede motivazione esplicita prima di modificare codice.
   - Preferire semplicità, leggibilità, manutenibilità e testabilità.
   - Evitare overengineering, duplicazioni, dipendenze inutili e funzionalità non richieste.
   - Non cambiare API, modelli o comportamento senza requisito, task o decisione coerente.

5. Decisions Workflow
   - `docs/decisions.md` non deve esistere per forza all'avvio.
   - Crearlo quando emerge la prima decisione significativa.
   - Aggiornarlo durante lo sviluppo quando cambiano stack, architettura, sicurezza, dati, integrazioni, UX rilevante o trade-off non banali.
   - Formato minimo: ID, data, stato, contesto, decisione, motivazione, alternative considerate, impatto, collegamenti.

6. Documentation Update Workflow
   - Aggiornare `docs/requirements.md` solo se cambia il comportamento atteso.
   - Aggiornare `docs/architecture.md` solo se cambiano struttura, stack, componenti, pattern o integrazioni.
   - Aggiornare `docs/security.md` solo se cambiano rischi, controlli, dati sensibili, autenticazione, autorizzazione o policy.
   - Aggiornare `docs/design.md` solo se cambiano UI/UX, componenti, accessibilità, layout, design system o logo.
   - Aggiornare `docs/tasks.md` solo se cambiano roadmap, stato, priorità o dipendenze.
   - Aggiornare `docs/decisions.md` per decisioni significative.
   - Aggiornare `README.md` quando cambiano setup, prerequisiti, comandi, configurazione richiesta, modalità d'uso, funzionalità principali, stato MVP o informazioni necessarie a un nuovo lettore.
   - Mantenere `README.md` come guida d'ingresso sintetica per umani, non duplicativa rispetto a `docs/`.
   - Non aggiornare documenti senza necessità reale.

7. Code Documentation Workflow
   - Applicare la code documentation policy definita in `docs/architecture.md`.
   - Verificare se servono brevi commenti o Javadoc in inglese su classi applicative principali stabilizzate.
   - Commentare solo logica non immediata, vincoli di dominio, trade-off, assunzioni o comportamenti sorprendenti.
   - Evitare commenti banali o contenuti già evidenti dai nomi.

8. Logging Workflow
   - Applicare la logging policy tecnica di `docs/architecture.md` e i vincoli di sicurezza di `docs/security.md`.
   - Aggiungere log solo se aiutano diagnosi, audit tecnico, troubleshooting o comprensione dello stato operativo.
   - Usare livelli coerenti con lo stack e correlation/request id per flussi multi-step quando utile.
   - Non loggare segreti, token, password, PII, payload sensibili, prompt/input utente o output AI sensibili.
   - Rimuovere log temporanei, rumorosi, duplicati o banali.

9. Testing Workflow
   - Scrivere unit test per logica applicativa e regole di dominio.
   - Scrivere integration test per confini tra componenti, persistenza, API o integrazioni esterne.
   - Scrivere regression test per bugfix quando tecnicamente possibile.
   - Eseguire test rilevanti; se non eseguibili, indicare motivo, rischio residuo e comando consigliato.

10. Refactoring Workflow
   - Consentire refactoring solo se motivato da task, bug, debito tecnico, sicurezza o chiarezza necessaria.
   - Non mescolare refactoring non richiesto con modifiche funzionali.
   - Preservare comportamento pubblico e compatibilità salvo requisito esplicito.

11. Security Workflow
   - Derivare regole operative da `docs/security.md`.
   - Non introdurre segreti nel codice, nei test, nella configurazione versionata o nei log.
   - Validare input esterni e gestire errori senza esporre dettagli interni.
   - Applicare least privilege e misure proporzionate al rischio.
   - Non disabilitare controlli senza decisione documentata.

12. Frontend Workflow
   - Applicare solo se `docs/design.md` esiste o se il progetto prevede UI/frontend.
   - Rispettare design system, componenti, accessibilità, responsive design e pattern UX.
   - Usare il logo ufficiale in `assets/logo/` quando presente e richiamato da `docs/design.md`.
   - Non introdurre nuovi colori, font, componenti, pattern o varianti logo senza aggiornare `docs/design.md`.
   - Se `docs/design.md` non esiste e serve UI, proporne la generazione prima dell'implementazione.

13. General Behaviour
   - Agire in modo deterministico e document-driven.
   - Dichiarare assunzioni solo quando necessarie.
   - Chiedere chiarimenti solo se l'ambiguità blocca una modifica corretta.
   - Preferire modifiche piccole, reversibili e verificabili.
   - Riportare a fine lavoro: modifiche, test, documenti aggiornati e rischi residui.

## Regole Finali

- Genera un documento compatto e operativo: alta densità informativa, nessuna ridondanza, nessuna sezione compilata solo per completezza.
- Non generare `docs/prompts.md`.
- Non includere prompt riutilizzabili o sezioni dedicate a prompt da copiare.
- Non generare codice applicativo.
- Non generare `agents/`.
- Non duplicare contenuti di requirements, architecture, security, design o tasks.
- Usa italiano e UTF-8 salvo richiesta esplicita diversa.
