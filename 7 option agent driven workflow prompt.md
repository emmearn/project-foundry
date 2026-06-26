Prompt per generare Agent-Driven Workflow

Agisci come AI Coding Workflow Architect.

Input: docs/requirements_template.md, docs/requirements.md, docs/architecture.md, docs/security.md, docs/tasks.md, docs/design.md se presente e docs/decisions.md se presente.

Output: genera esclusivamente docs/workflow.md e agents/ in Markdown, in versione compatta, isolata, senza duplicazioni, ottimizzata per IA di coding e massimo rapporto informazioni/token.

Scopo del prompt
Definire la configurazione operativa per usare un Agent-Driven Workflow alternativo al Document-Driven Workflow e al Dynamic Agent-Driven Workflow.

Filosofia vincolante
- docs/ è l'unica fonte di verità del progetto.
- Gli agenti non possiedono conoscenza di dominio.
- Gli agenti non duplicano requirements, architecture, security, tasks, design o decisions.
- Gli agenti rappresentano solo ruoli operativi statici.
- L'Orchestrator coordina il workflow agentico e decide dinamicamente quali agenti coinvolgere.
- Il workflow deve essere scalabile, modulare ed estendibile.

Genera docs/workflow.md con questa struttura
1. Workflow Overview
   - Definire l'Agent-Driven Workflow.
   - Specificare che docs/ resta l'unica fonte di verità.
   - Specificare che agents/ contiene solo ruoli operativi.
   - Distinguere questo workflow dagli altri prompt 7 senza modificarli.

2. Orchestrator Responsibilities
   - Ricevere la richiesta utente.
   - Leggere i documenti rilevanti.
   - Classificare il tipo di modifica.
   - Selezionare solo gli agenti necessari.
   - Coordinare passaggi, dipendenze, verifiche e aggiornamenti documentali.
   - Produrre risultato finale con modifiche, test, documenti aggiornati e rischi residui.

3. Dynamic Agent Selection
   - Modifiche semplici: Implementation Agent, Testing Agent, Review Agent.
   - Modifiche funzionali: Requirements Agent, Implementation Agent, Testing Agent, Review Agent.
   - Modifiche architetturali: Requirements Agent, Architecture Agent, Security Agent, Implementation Agent, Testing Agent, Review Agent.
   - Modifiche di sicurezza: Security Agent, Implementation Agent, Testing Agent, Review Agent.
   - Modifiche frontend: leggere docs/design.md se presente e coinvolgere agenti necessari.

4. Execution Workflow
   - Startup: leggere documentazione rilevante prima di agire.
   - Planning: identificare requisiti, task, vincoli, rischi e agenti richiesti.
   - Execution: applicare modifiche nello scope minimo necessario.
   - Verification: eseguire test e review coerenti.
   - Documentation: aggiornare docs/ solo quando necessario.
   - Closure: riportare risultato, test, documenti aggiornati e rischi residui.

5. Collaboration Rules
   - Gli agenti comunicano tramite output sintetici e riferimenti a docs/.
   - Nessun agente duplica contenuto di docs/.
   - Ogni agente legge prima di decidere.
   - L'Orchestrator risolve conflitti consultando docs/ e docs/decisions.md se presente.
   - Se i documenti sono incoerenti, proporre correzione documentale minima prima dell'implementazione.

6. Documentation Update Rules
   - Aggiornare docs/requirements.md solo se cambia il comportamento atteso.
   - Aggiornare docs/architecture.md solo se cambiano struttura, stack, componenti, pattern o integrazioni.
   - Aggiornare docs/security.md solo se cambiano rischi, controlli o policy.
   - Aggiornare docs/design.md solo se cambiano UI/UX o design system.
   - Aggiornare docs/tasks.md solo se cambiano roadmap, stato, priorità o dipendenze.
   - Aggiornare docs/decisions.md per decisioni significative.
   - Aggiornare README.md quando cambiano setup, prerequisiti, comandi di avvio/test/build, configurazione richiesta, modalità d'uso, funzionalità principali, stato MVP o informazioni necessarie a un nuovo lettore.
   - Mantenere README.md come guida d'ingresso sintetica per umani: operativo, leggibile, non duplicativo rispetto a docs/.
   - Rimandare a docs/ per requisiti, architettura, sicurezza, task, decisioni e workflow dettagliati.

7. Code Documentation Rules
   - Applicare la code documentation policy definita in docs/architecture.md.
   - Quando una classe applicativa principale è completata o stabilizzata, verificare se serve una breve Javadoc in inglese.
   - Quando un flusso applicativo è completato, rivedere entry point e componenti attraversati per aggiungere, aggiornare o rimuovere commenti dove utile.
   - Commentare solo logica non immediata, vincoli di dominio, trade-off, assunzioni o comportamenti sorprendenti.
   - Evitare commenti banali, descrizioni di getter/setter, assegnazioni o contenuti già evidenti dai nomi.
   - Preferire nomi chiari a commenti esplicativi quando possibile.

8. General Execution Rules
   - Limitare lo scope alla richiesta o al task corrente.
   - Preferire semplicità, leggibilità, manutenibilità e testabilità.
   - Evitare overengineering, duplicazioni, dipendenze inutili e funzionalità non richieste.
   - Non cambiare API, modelli o comportamento senza requisito, task o decisione coerente.
   - Eseguire test rilevanti; se non eseguibili, indicare motivo, rischio residuo e comando consigliato.

Genera agents/ con questi file minimi
- orchestrator-agent.md
- requirements-agent.md
- architecture-agent.md
- implementation-agent.md
- testing-agent.md
- security-agent.md
- review-agent.md

Formato obbligatorio per ogni agente
Ogni file agente deve contenere esclusivamente:
- Mission
- Responsibilities
- Read
- Write
- Forbidden Actions

Regole comuni per tutti gli agenti
- Essere estremamente compatti.
- Rimandare sempre ai documenti in docs/.
- Non duplicare conoscenza di dominio.
- Scrivere solo i file consentiti dalla sezione Write.
- Non introdurre agenti aggiuntivi salvo necessità esplicita.

Contenuto richiesto degli agenti

orchestrator-agent.md
- Mission: coordinare l'intero Agent-Driven Workflow.
- Responsibilities: analizzare richieste, leggere documenti, selezionare agenti, ordinare attività, risolvere conflitti, coordinare test/review/documentazione, aggiornare README.md solo quando utile, produrre risultato finale.
- Read: tutti i documenti in docs/ e agents/ necessari.
- Write: docs/workflow.md, docs/decisions.md quando necessario, aggiornamenti documentali necessari, output finale.
- Forbidden Actions: duplicare docs/, bypassare agenti necessari, introdurre scope non richiesto, ignorare incoerenze documentali.

requirements-agent.md
- Mission: garantire coerenza con requisiti e scope funzionale.
- Responsibilities: interpretare requisiti, verificare ambiguità, identificare impatti funzionali, proporre aggiornamenti minimi ai requisiti.
- Read: docs/requirements_template.md, docs/requirements.md, docs/tasks.md, docs/decisions.md se presente.
- Write: docs/requirements.md solo se cambia comportamento atteso; docs/decisions.md se serve.
- Forbidden Actions: scegliere implementazioni tecniche, modificare architettura, duplicare requisiti.

architecture-agent.md
- Mission: garantire coerenza tecnica e strutturale.
- Responsibilities: valutare impatti architetturali, componenti, dipendenze, pattern, integrazioni e coerenza con requirements.
- Read: docs/requirements.md, docs/architecture.md, docs/security.md, docs/decisions.md se presente.
- Write: docs/architecture.md solo se cambiano scelte tecniche; docs/decisions.md se serve.
- Forbidden Actions: introdurre overengineering, dipendenze inutili, decisioni non motivate o duplicazioni di security/tasks.

implementation-agent.md
- Mission: implementare modifiche nello scope minimo necessario.
- Responsibilities: modificare codice/configurazione, rispettare architecture/security/tasks/design, mantenere semplicità, testabilità e documentazione essenziale del codice dove rilevante.
- Read: docs/requirements.md, docs/architecture.md, docs/security.md, docs/tasks.md, docs/design.md se rilevante, docs/decisions.md se presente.
- Write: codice e configurazione necessari; docs/tasks.md solo per stato o dipendenze se richiesto dal workflow.
- Forbidden Actions: cambiare comportamento non richiesto, ignorare test, introdurre dipendenze inutili, aggiungere commenti banali, aggiornare documenti non pertinenti.

testing-agent.md
- Mission: verificare correttezza e regressioni.
- Responsibilities: definire/eseguire unit test, integration test, regression test e test UI se rilevanti.
- Read: docs/requirements.md, docs/architecture.md, docs/security.md, docs/tasks.md, docs/design.md se rilevante.
- Write: test e report sintetico di verifica.
- Forbidden Actions: ridurre copertura senza motivo, ignorare fallimenti, sostituire test necessari con sola analisi manuale.

security-agent.md
- Mission: garantire conformità a docs/security.md.
- Responsibilities: valutare rischi, segreti, input/output, autorizzazione, logging, dipendenze, privacy e mitigazioni.
- Read: docs/security.md, docs/requirements.md, docs/architecture.md, docs/design.md se rilevante, docs/decisions.md se presente.
- Write: docs/security.md solo se cambia profilo di rischio; docs/decisions.md se serve; finding di sicurezza.
- Forbidden Actions: disabilitare controlli, introdurre segreti, duplicare policy, proporre misure non proporzionate.

review-agent.md
- Mission: revisionare coerenza, qualità e rischi prima della chiusura.
- Responsibilities: cercare bug, regressioni, incoerenze con docs/, test mancanti, rischi di sicurezza, overengineering, dipendenze inutili, README.md obsoleto quando impatta l'ingresso al progetto, e commenti mancanti o superflui rispetto alla code documentation policy.
- Read: documenti docs/ rilevanti, modifiche prodotte, report test, decisioni.
- Write: finding ordinati per severità e raccomandazione finale.
- Forbidden Actions: riscrivere codice senza richiesta, duplicare analisi già presenti, approvare modifiche non verificate.

Regole finali
- Non modificare altri prompt del framework.
- Non modificare la struttura di docs/.
- Non generare Document-Driven Workflow.
- Non generare Dynamic Agent-Driven Workflow.
- Non generare docs/prompts.md.
- Non duplicare contenuto dei documenti di progetto.
