Prompt per generare Dynamic Agent-Driven Workflow

Agisci come AI Coding Workflow Architect.

Input: docs/requirements_template.md, docs/requirements.md, docs/architecture.md, docs/security.md, docs/tasks.md, docs/design.md se presente e docs/decisions.md se presente.

Output: genera esclusivamente docs/workflow.md e agents/ in Markdown, in versione compatta, isolata, senza duplicazioni, ottimizzata per IA di coding e massimo rapporto informazioni/token.

Scopo del prompt
Definire la configurazione operativa per usare un Dynamic Agent-Driven Workflow, alternativa avanzata a Document-Driven Workflow e Agent-Driven Workflow.

Filosofia vincolante
- docs/ è l'unica fonte di verità del progetto.
- Il comportamento operativo vive solo in docs/workflow.md e agents/.
- Non creare un set completo e statico di agenti.
- Creare solo agenti minimi fondamentali.
- Gli agenti minimi possono proporre o generare agenti specializzati solo quando necessario.
- Gli agenti dinamici non duplicano requirements, architecture, security, tasks, design o decisions.
- Il workflow deve supportare una PoC Spring AI con agenti specializzati creati a runtime.

Genera docs/workflow.md con questa struttura
1. Workflow Overview
   - Definire il Dynamic Agent-Driven Workflow.
   - Specificare che docs/ resta l'unica fonte di verità.
   - Specificare che agents/ contiene solo agenti minimi iniziali e agenti dinamici eventualmente creati.
   - Distinguere questo workflow dagli altri prompt 7 senza modificarli.

2. Core Agents
   - orchestrator-agent.md: punto di ingresso e coordinamento.
   - agent-factory-agent.md: creazione o proposta di agenti specializzati.
   - context-agent.md: gestione del contesto documentale minimo.
   - security-agent.md: verifica rischi e vincoli.
   - review-agent.md: review finale di risultato, coerenza e agenti creati.

3. Orchestrator Workflow
   - Ricevere la richiesta utente.
   - Leggere documentazione rilevante tramite Context Agent.
   - Classificare task, scope, rischi e dipendenze.
   - Decidere se bastano agenti esistenti.
   - Coinvolgere Agent Factory solo se serve un agente specializzato riutilizzabile.
   - Coordinare esecuzione, test, security review e final review.
   - Aggiornare docs/tasks.md e docs/decisions.md solo quando necessario.
   - Produrre risultato finale con modifiche, test, documenti aggiornati, agenti creati e rischi residui.

4. Agent Factory Workflow
   - Analizzare task, documentazione e agenti esistenti.
   - Verificare se un agente esistente copre il bisogno.
   - Creare o proporre un nuovo agente solo se necessario.
   - Definire Mission, Responsibilities, Read, Write, Forbidden Actions.
   - Evitare agenti troppo specifici, ridondanti, temporanei o basati su preferenze stilistiche.
   - Mantenere ogni agente compatto, riutilizzabile e con ambito chiaro.

5. Dynamic Agent Creation Rules
   - Creare un agente solo se il task richiede competenze ricorrenti e specializzate.
   - Creare un agente solo se nessun agente esistente copre adeguatamente il bisogno.
   - Creare un agente solo se può essere riutilizzato in task futuri.
   - Creare un agente solo se il suo ambito è chiaro, limitato e documentabile.
   - Non creare agenti per task singoli e banali.
   - Non creare agenti per modifiche locali.
   - Non creare agenti per responsabilità già coperte.
   - Non creare agenti per preferenze stilistiche.
   - Non creare agenti che duplicano documentazione di dominio.

6. Documentation Workflow
   - Gli agenti leggono sempre docs/ prima di decidere.
   - Context Agent sintetizza solo il contesto minimo necessario.
   - Aggiornare docs/tasks.md solo se cambiano task, stato, priorità, dipendenze o roadmap.
   - Aggiornare docs/decisions.md per decisioni significative su prodotto, architettura, sicurezza, processo o nuovi agenti.
   - Aggiornare altri documenti solo secondo la loro responsabilità specifica.
   - Aggiornare README.md quando cambiano setup, prerequisiti, comandi di avvio/test/build, configurazione richiesta, modalità d'uso, funzionalità principali, stato MVP o informazioni necessarie a un nuovo lettore.
   - Mantenere README.md come guida d'ingresso sintetica per umani: operativo, leggibile, non duplicativo rispetto a docs/.
   - Rimandare a docs/ per requisiti, architettura, sicurezza, task, decisioni e workflow dettagliati.
   - Se i documenti sono incoerenti, proporre correzione documentale minima prima dell'implementazione.

7. Code Documentation Workflow
   - Applicare la code documentation policy definita in docs/architecture.md.
   - Quando una classe applicativa principale è completata o stabilizzata, verificare se serve una breve Javadoc in inglese.
   - Quando un flusso applicativo è completato, rivedere entry point e componenti attraversati per aggiungere, aggiornare o rimuovere commenti dove utile.
   - Commentare solo logica non immediata, vincoli di dominio, trade-off, assunzioni o comportamenti sorprendenti.
   - Evitare commenti banali, descrizioni di getter/setter, assegnazioni o contenuti già evidenti dai nomi.
   - Preferire nomi chiari a commenti esplicativi quando possibile.

8. Execution Workflow
   - Startup: leggere documentazione rilevante.
   - Context: produrre sintesi minima e vincoli applicabili.
   - Agent Selection: usare agenti esistenti o coinvolgere Agent Factory.
   - Execution: applicare modifiche nello scope minimo.
   - Security: verificare rischi e controlli proporzionati.
   - Testing: eseguire test rilevanti o indicare perché non eseguibili.
   - Review: verificare coerenza, regressioni, duplicazioni, overengineering e necessità degli agenti creati.
   - Closure: riportare risultato, test, documenti aggiornati, agenti creati e rischi residui.

9. Anti-Proliferation Rules
   - Preferire agenti esistenti.
   - Preferire istruzioni nel workflow rispetto a nuovi agenti se il bisogno non è ricorrente.
   - Eliminare o non creare agenti ridondanti.
   - Ogni agente dinamico deve avere responsabilità distinta e riutilizzabile.
   - Motivare la creazione di un agente e registrarla in docs/decisions.md quando significativa.

10. General Execution Rules
   - Limitare lo scope alla richiesta o al task corrente.
   - Preferire semplicità, leggibilità, manutenibilità e testabilità.
   - Evitare overengineering, duplicazioni, dipendenze inutili e funzionalità non richieste.
   - Non cambiare API, modelli o comportamento senza requisito, task o decisione coerente.
   - Non duplicare contenuto di docs/ dentro workflow.md o agents/.

Genera agents/ con solo questi agenti iniziali
- orchestrator-agent.md
- agent-factory-agent.md
- context-agent.md
- review-agent.md
- security-agent.md

Non generare agenti statici completi come backend-agent.md, frontend-agent.md, database-agent.md, devops-agent.md o simili salvo motivazione esplicita derivata dalla documentazione.

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
- Usare istruzioni prescrittive e direttamente eseguibili dall'IA.

Contenuto richiesto degli agenti minimi

orchestrator-agent.md
- Mission: coordinare l'intero Dynamic Agent-Driven Workflow.
- Responsibilities: ricevere richiesta, leggere documentazione tramite Context Agent, capire task/scope/rischi/dipendenze, decidere agenti esistenti o Agent Factory, coordinare esecuzione/test/security/review/code documentation, proporre aggiornamenti documentali e README.md solo quando utile.
- Read: docs/requirements.md, docs/architecture.md, docs/security.md, docs/tasks.md, docs/design.md se presente, docs/decisions.md se presente, agents/ rilevanti.
- Write: docs/workflow.md se cambia workflow, docs/tasks.md se cambia roadmap/stato/dipendenze, docs/decisions.md per decisioni significative, output finale.
- Forbidden Actions: bypassare documentazione, creare agenti senza Agent Factory, duplicare docs/, introdurre scope non richiesto.

agent-factory-agent.md
- Mission: creare o proporre agenti specializzati solo quando necessario.
- Responsibilities: analizzare task/documentazione/agenti, verificare copertura esistente, creare agente riutilizzabile con ambito chiaro, evitare agenti ridondanti o temporanei.
- Read: docs/workflow.md, docs/tasks.md, docs/architecture.md, docs/security.md, docs/decisions.md se presente, agents/ esistenti.
- Write: nuovi agents/*-agent.md solo se giustificati; docs/decisions.md se creazione significativa.
- Forbidden Actions: creare agenti per task banali/locali, duplicare docs/, sovrapporsi ad agenti esistenti, generare set statici completi.

context-agent.md
- Mission: fornire il contesto documentale minimo necessario.
- Responsibilities: leggere documenti rilevanti, sintetizzare vincoli/requisiti/task/decisioni applicabili, identificare incoerenze, proporre aggiornamenti minimi.
- Read: docs/requirements_template.md, docs/requirements.md, docs/architecture.md, docs/security.md, docs/tasks.md, docs/design.md se presente, docs/decisions.md se presente.
- Write: sintesi contestuale operativa; proposte di aggiornamento documentale minimo.
- Forbidden Actions: inventare requisiti, duplicare interi documenti, decidere implementazioni fuori dai documenti, aggiornare documenti senza necessità.

security-agent.md
- Mission: verificare vincoli e rischi di sicurezza.
- Responsibilities: leggere docs/security.md, identificare rischi introdotti dal task, bloccare modifiche insicure, proporre controlli minimi proporzionati, segnalare aggiornamenti necessari.
- Read: docs/security.md, docs/requirements.md, docs/architecture.md, docs/design.md se rilevante, docs/decisions.md se presente.
- Write: finding di sicurezza; docs/security.md solo se cambia profilo di rischio; docs/decisions.md se serve.
- Forbidden Actions: disabilitare controlli, introdurre segreti, duplicare policy, proporre misure non proporzionate.

review-agent.md
- Mission: revisionare risultato finale e agenti creati.
- Responsibilities: verificare coerenza con requirements/architecture/security/tasks, individuare bug/regressioni/duplicazioni/overengineering, verificare test/rischi residui, validare necessità degli agenti creati, rilevare README.md obsoleto quando impatta l'ingresso al progetto e commenti mancanti o superflui rispetto alla code documentation policy.
- Read: documenti docs/ rilevanti, agenti coinvolti o creati, modifiche prodotte, report test e security finding.
- Write: finding ordinati per severità; raccomandazione finale.
- Forbidden Actions: approvare modifiche non verificate, ignorare agenti ridondanti, riscrivere codice senza richiesta, duplicare analisi già presenti.

Regole finali
- Non modificare altri prompt del framework.
- Non generare codice applicativo.
- Non generare Document-Driven Workflow.
- Non generare Agent-Driven Workflow statico.
- Non generare docs/prompts.md.
- Non creare agenti statici non necessari.
- Non duplicare informazioni di dominio dentro gli agenti.
