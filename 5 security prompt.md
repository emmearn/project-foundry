Agisci come Security Architect senior.

Input: `docs/vision.md` se presente, `docs/requirements.md`, `docs/architecture.md` e `docs/design.md` se presente. Genera esclusivamente `docs/security.md` in Markdown, in versione compatta, isolata, senza duplicazioni, ottimizzata per IA di coding e massimo rapporto informazioni/token.

## Output Contract

Input richiesti:
- `docs/vision.md`, se presente.
- `docs/requirements.md`.
- `docs/architecture.md`.
- `docs/design.md`, se presente.

Output prodotto:
- `docs/security.md`.
- Guardrail, policy, rischi, mitigazioni e vincoli di sicurezza proporzionati al progetto.
- Pratiche vietate e rischi residui.
- Decisioni di sicurezza da registrare in `docs/decisions.md` quando significative.

Non deve produrre:
- requisiti funzionali;
- architettura;
- design;
- task;
- workflow;
- codice;
- agenti.

## Scopo Del Documento

Definire solo guardrail, policy, rischi e vincoli di sicurezza proporzionati al progetto. Questo file è la fonte di verità della sicurezza.

## Struttura Richiesta

1. Principi: security by default, least privilege, fail securely, defense in depth, secure by design.
2. Segreti: nessun segreto nel codice o in Git; variabili d'ambiente/secret manager; divieto di loggare dati sensibili.
3. Autenticazione e sessioni: meccanismi, token, password policy, session management; se non richiesti, dichiararlo.
4. Autorizzazione: ruoli, permessi e controlli API/business.
5. Input validation e output handling: whitelist, limiti, sanitizzazione, mascheramento, nessuno stacktrace all'utente.
6. Logging ed error handling sicuri: masking/redaction, messaggi sicuri, divieto di loggare segreti, token, password, PII, payload sensibili, prompt/input utente o output AI sensibili.
7. Comunicazioni: HTTPS/TLS, certificati, divieto di protocolli insicuri se c'è rete.
8. Database e filesystem: query parametrizzate, privilegi minimi, backup/retention se rilevanti, path validation.
9. API e integrazioni: rate limit, timeout, retry controllati, validazione request/response se applicabili.
10. Frontend e UX di sicurezza: solo se `docs/design.md` è presente.
11. Privacy: dati personali, minimizzazione e retention.
12. Dipendenze: librerie mantenute, minime e aggiornate.
13. Minacce, mitigazioni e rischi residui: collegare a requisiti/componenti quando utile.
14. Pratiche vietate: segreti hardcoded, segreti in repo, SQL concatenato, SSL disabilitato, stacktrace esposti, log sensibili, controlli disattivati senza motivo, dipendenze obsolete.

## Regole

- Genera un documento compatto e operativo: alta densità informativa, nessuna ridondanza, nessuna sezione compilata solo per completezza.
- Non duplicare scelte tecniche di `docs/architecture.md`: trasformale solo in vincoli di sicurezza.
- Applica solo misure giustificate; evita overengineering.
- La logging policy tecnica resta in `docs/architecture.md`; qui definisci solo vincoli e rischi di sicurezza collegati ai log.
- Usa riferimenti agli altri file solo per contesto o tracciabilità.
- Indica decisioni da registrare in `docs/decisions.md` quando significative.
- Usa italiano e UTF-8 salvo richiesta esplicita diversa.
