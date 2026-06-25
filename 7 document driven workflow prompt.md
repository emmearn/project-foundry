Prompt per generare docs/workflow.md - Document-Driven Workflow

Agisci come AI Coding Workflow Architect.

Input: docs/requirements_template.md, docs/requirements.md, docs/architecture.md, docs/security.md, docs/tasks.md, docs/design.md se presente e docs/decisions.md se presente. Genera esclusivamente docs/workflow.md in Markdown, in versione compatta, isolata, senza duplicazioni, ottimizzata per IA di coding e massimo rapporto informazioni/token.

Scopo del documento
Definire solo il comportamento operativo dell'IA nel Document-Driven Workflow. Non generare requisiti, architettura, sicurezza, roadmap, agents o prompt riutilizzabili.

Contesto
- Questo prompt è una delle tre alternative del punto 7.
- Usalo solo se l'utente sceglie Document-Driven Workflow.
- Non generare Agent-Driven Workflow o Dynamic Agent-Driven Workflow.
- Non creare agents/.

Principi vincolanti
- docs/ è l'unica fonte di verità.
- Ogni richiesta parte dalla lettura dei documenti rilevanti.
- Non esistono agenti persistenti.
- L'IA assume dinamicamente il ruolo necessario: architect, developer, reviewer, security o altro.
- Mantieni una sola fonte di verità: rimanda ai documenti invece di duplicarne il contenuto.
- Limita sempre lo scope alla richiesta o al task corrente.

Struttura richiesta di docs/workflow.md
1. Workflow Overview
   - Definire il Document-Driven Workflow.
   - Stabilire che i documenti guidano ogni decisione.
   - Esplicitare che non esistono agenti persistenti.
   - Esplicitare che l'IA assume dinamicamente il ruolo più adatto.

2. Startup Workflow
   - Prima di qualsiasi modifica leggere docs/requirements.md, docs/architecture.md, docs/security.md e docs/tasks.md.
   - Leggere docs/design.md se presente o se la richiesta riguarda UI/UX/frontend.
   - Leggere docs/decisions.md se presente.
   - Usare docs/requirements_template.md solo quando si interpretano o aggiornano requisiti.
   - Identificare requisiti, task, vincoli architetturali e vincoli di sicurezza applicabili.
   - Se i documenti sono incoerenti, fermarsi e proporre la correzione documentale minima.

3. Development Workflow
   - Rispettare requirements, architecture, security e tasks.
   - Implementare solo ciò che serve alla richiesta o al task corrente.
   - Preferire semplicità, leggibilità, manutenibilità e testabilità.
   - Evitare overengineering, duplicazioni, dipendenze inutili e funzionalità non richieste.
   - Non cambiare API, modelli o comportamento senza requisito, task o decisione coerente.
   - Se emerge una decisione significativa, registrarla o proporne registrazione in docs/decisions.md.

4. Documentation Update Workflow
   - Aggiornare docs/requirements.md solo se cambia il comportamento atteso.
   - Aggiornare docs/architecture.md solo se cambiano struttura, stack, componenti, pattern o integrazioni.
   - Aggiornare docs/security.md solo se cambiano rischi, controlli, dati sensibili, autenticazione, autorizzazione o policy.
   - Aggiornare docs/design.md solo se cambiano UI/UX, componenti, accessibilità, layout o design system.
   - Aggiornare docs/tasks.md solo se cambiano roadmap, stato, priorità o dipendenze.
   - Aggiornare docs/decisions.md per decisioni significative.
   - Non aggiornare documenti senza necessità reale.

5. Testing Workflow
   - Scrivere unit test per logica applicativa e regole di dominio.
   - Scrivere integration test per confini tra componenti, persistenza, API o integrazioni esterne.
   - Scrivere regression test per bugfix quando tecnicamente possibile.
   - Eseguire test rilevanti; se non eseguibili, indicare motivo, rischio residuo e comando consigliato.

6. Refactoring Workflow
   - Consentire refactoring solo se motivato da task, bug, debito tecnico, sicurezza o chiarezza necessaria.
   - Non mescolare refactoring non richiesto con modifiche funzionali.
   - Preservare comportamento pubblico e compatibilità salvo requisito esplicito.

7. Security Workflow
   - Derivare regole operative da docs/security.md.
   - Non introdurre segreti nel codice, nei test, nella configurazione versionata o nei log.
   - Validare input esterni e gestire errori senza esporre dettagli interni.
   - Applicare least privilege e misure proporzionate al rischio.
   - Non disabilitare controlli senza decisione documentata.

8. Frontend Workflow
   - Applicare solo se docs/design.md esiste o se il progetto prevede UI/frontend.
   - Rispettare design system, componenti, accessibilità, responsive design e pattern UX.
   - Non introdurre nuovi colori, font, componenti o pattern senza aggiornare docs/design.md.
   - Se docs/design.md non esiste e serve UI, proporne la generazione prima dell'implementazione.

9. General Behaviour
   - Agire in modo deterministico e document-driven.
   - Dichiarare assunzioni solo quando necessarie.
   - Chiedere chiarimenti solo se l'ambiguità blocca una modifica corretta.
   - Preferire modifiche piccole, reversibili e verificabili.
   - Riportare a fine lavoro: modifiche, test, documenti aggiornati e rischi residui.

Regole finali
- Non generare docs/prompts.md.
- Non includere prompt riutilizzabili o sezioni dedicate a prompt da copiare.
- Non generare codice applicativo.
- Non generare agents/.
- Non duplicare contenuti di requirements, architecture, security, design o tasks.
