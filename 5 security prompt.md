Prompt per generare docs/security.md

Agisci come Security Architect senior.

Input: docs/requirements.md, docs/architecture.md e docs/design.md se presente. Genera esclusivamente docs/security.md in Markdown, in versione compatta, isolata, senza duplicazioni, ottimizzata per IA di coding e massimo rapporto informazioni/token.

Scopo del documento
Definire solo guardrail, policy, rischi e vincoli di sicurezza proporzionati al progetto. Questo file è la fonte di verità della sicurezza.

Struttura richiesta
1. Principi: security by default, least privilege, fail securely, defense in depth, secure by design.
2. Segreti: nessun segreto nel codice o in Git; variabili d'ambiente/secret manager; divieto di loggare dati sensibili.
3. Autenticazione e sessioni: meccanismi, token, password policy, session management; se non richiesti, dichiararlo.
4. Autorizzazione: ruoli, permessi e controlli API/business.
5. Input validation e output handling: whitelist, limiti, sanitizzazione, mascheramento, nessuno stacktrace all'utente.
6. Logging ed error handling: livelli, correlation id quando utile, messaggi sicuri e standardizzati, masking/redaction, divieto di loggare segreti, token, password, PII, payload sensibili, prompt/input utente o output AI sensibili.
7. Comunicazioni: HTTPS/TLS, certificati, divieto di protocolli insicuri se c'è rete.
8. Database e filesystem: query parametrizzate, privilegi minimi, backup/retention se rilevanti, path validation.
9. API e integrazioni: rate limit, timeout, retry controllati, validazione request/response se applicabili.
10. Frontend e UX di sicurezza: solo se docs/design.md è presente.
11. Privacy: dati personali, minimizzazione e retention.
12. Dipendenze: librerie mantenute, minime e aggiornate.
13. Minacce, mitigazioni e rischi residui: collegare a requisiti/componenti quando utile.
14. Pratiche vietate: segreti hardcoded, segreti in repo, SQL concatenato, SSL disabilitato, stacktrace esposti, log sensibili, controlli disattivati senza motivo, dipendenze obsolete.

Regole
- Non generare codice, requirements, architecture, design, tasks, workflow o agents.
- Non duplicare scelte tecniche di docs/architecture.md: trasformale solo in vincoli di sicurezza.
- Applica solo misure giustificate; evita overengineering.
- La logging policy deve favorire diagnosi e audit tecnico senza aumentare il rischio di esposizione dati o creare rumore operativo.
- Usa riferimenti agli altri file solo per contesto o tracciabilità.
- Indica decisioni da registrare in docs/decisions.md quando significative.
