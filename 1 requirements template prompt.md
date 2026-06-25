Prompt per generare docs/requirements_template.md

Agisci come Requirements Engineer senior e AI Coding Workflow Architect.

Input: vision.md se presente, descrizione del progetto e contesto di dominio. Genera esclusivamente docs/requirements_template.md in Markdown, in versione compatta, isolata, senza duplicazioni, ottimizzata per IA di coding e massimo rapporto informazioni/token.

Scopo del documento
Definire solo lo standard con cui scrivere docs/requirements.md. Non definire requisiti del progetto.

Struttura richiesta
1. Principi di scrittura: requisiti chiari, atomici, non ambigui, verificabili, testabili e tracciabili.
2. Separazione concettuale: requisito, vincolo, assunzione, regola di dominio, criterio di accettazione.
3. Formato requisito: scheda o tabella con ID, titolo, descrizione, motivazione, attori, precondizioni, flusso principale, alternative/errori, regole di dominio, criteri di accettazione, impatti, priorità, stato, tracciabilità.
4. ID e classificazioni: REQ-001; priorità MUST/SHOULD/COULD; stati Draft/Approved/Changed/Deprecated.
5. Criteri di accettazione: Given/When/Then o checklist osservabili.
6. Tracciabilità: collegamenti futuri a docs/tasks.md, docs/decisions.md, test e rischi.
7. Impatti trasversali: sicurezza, dati, privacy, integrazioni, performance, accessibilità e operatività solo se rilevanti.
8. Esempio minimo: requisito generico compilato, senza stack tecnologico.

Regole
- Non generare docs/requirements.md.
- Non generare codice, architettura, design, security, tasks, workflow o agents.
- Non scegliere librerie, framework, database o pattern applicativi.
- Non duplicare responsabilità degli altri documenti.
- Usa riferimenti ad altri file solo per tracciabilità futura.
