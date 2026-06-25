Prompt per generare docs/architecture.md

Agisci come Software Architect senior.

Input: docs/requirements.md. Genera esclusivamente docs/architecture.md in Markdown, in versione compatta, isolata, senza duplicazioni, ottimizzata per IA di coding e massimo rapporto informazioni/token.

Scopo del documento
Definire come costruire il sistema per soddisfare i requisiti. Questo file è la fonte di verità delle scelte tecniche e strutturali.

Struttura richiesta
1. Overview: architettura generale e mappatura sintetica ai requisiti principali.
2. Stack tecnologico: linguaggio, framework, database se necessario, librerie principali e servizi esterni; motivare ogni scelta.
3. Architettura applicativa: layer/componenti, responsabilità e dipendenze consentite.
4. Struttura progetto: package/cartelle e convenzioni.
5. Componenti principali: responsabilità e requisiti collegati quando utile.
6. Modello dati: entità e relazioni al livello necessario.
7. Flussi applicativi: sequenze principali con diagrammi testuali se utili.
8. Error handling e logging: regole tecniche senza duplicare docs/security.md.
9. Configurazione: proprietà, variabili d'ambiente e gestione segreti rimandando i dettagli a docs/security.md.
10. Performance e scalabilità: solo misure giustificate dai requisiti.
11. Testing strategy: unit, integration, mock e criteri per la logica principale.
12. Convenzioni di sviluppo: naming, pattern, dipendenze e regole di codifica.
13. Decisioni architetturali: decisione, motivazione, alternative, impatto; indicare cosa registrare in docs/decisions.md.

Regole
- Segui rigorosamente docs/requirements.md.
- Non introdurre tecnologie, componenti o pattern non necessari.
- Non generare codice, requirements, design, security dettagliata, tasks, workflow o agents.
- Non duplicare responsabilità di security, tasks o workflow.
- Evidenzia punti aperti solo quando una scelta non è determinabile dai requisiti.
