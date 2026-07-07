Agisci come Software Architect senior.

Input: `docs/vision.md` se presente e `docs/requirements.md`. Genera esclusivamente `docs/architecture.md` in Markdown, in versione compatta, isolata, senza duplicazioni, ottimizzata per IA di coding e massimo rapporto informazioni/token.

## Output Contract

Input richiesti:
- `docs/vision.md`, se presente.
- `docs/requirements.md`.

Output prodotto:
- `docs/architecture.md`.
- Stack tecnologico motivato.
- Struttura applicativa, componenti principali e dipendenze consentite.
- Modello dati al livello necessario.
- Convenzioni tecniche.
- Policy essenziali su error handling, logging, testing e documentazione codice.
- Decisioni architetturali da registrare in `docs/decisions.md` quando significative.

Non deve produrre:
- requisiti funzionali;
- design UI/UX;
- policy di sicurezza dettagliate;
- task di implementazione;
- workflow operativo per l'IA;
- codice applicativo;
- agenti.

## Scopo Del Documento

Definire come costruire il sistema per soddisfare i requisiti. Questo file è la fonte di verità delle scelte tecniche e strutturali.

## Struttura Richiesta

1. Overview: architettura generale e mappatura sintetica ai requisiti principali.
2. Stack tecnologico: linguaggio, framework, database se necessario, librerie principali e servizi esterni; motivare ogni scelta.
3. Architettura applicativa: layer/componenti, responsabilità e dipendenze consentite.
4. Struttura progetto: package/cartelle e convenzioni.
5. Componenti principali: responsabilità e requisiti collegati quando utile.
6. Modello dati: entità e relazioni al livello necessario.
7. Flussi applicativi: sequenze principali con diagrammi testuali solo se utili.
8. Error handling e logging: regole tecniche, livelli, punti di osservabilità e correlation/request id quando utili, senza duplicare `docs/security.md`.
9. Configurazione: proprietà, variabili d'ambiente e gestione segreti rimandando i dettagli a `docs/security.md`.
10. Performance e scalabilità: solo misure giustificate dai requisiti.
11. Testing strategy: unit, integration, mock e criteri per la logica principale.
12. Convenzioni di sviluppo: naming, pattern, dipendenze, regole di codifica e documentazione essenziale del codice.
13. README guidance: informazioni operative che dovrebbero emergere in `README.md` quando rilevanti.
14. Decisioni architetturali: decisione, motivazione, alternative, impatto; indicare cosa registrare in `docs/decisions.md`.

## Regole

- Genera un documento compatto e operativo: alta densità informativa, nessuna ridondanza, nessuna sezione compilata solo per completezza.
- Segui rigorosamente `docs/requirements.md`.
- Non introdurre tecnologie, componenti o pattern non necessari.
- La logging policy tecnica appartiene a questo documento; i vincoli di sicurezza sui log appartengono a `docs/security.md`.
- La code documentation policy deve restare essenziale: commenti in inglese, Javadoc breve solo su classi applicative principali, commenti solo su logica non immediata, vincoli di dominio, trade-off o assunzioni non ovvie.
- Evidenzia punti aperti solo quando una scelta non è determinabile dai requisiti.
- Usa italiano e UTF-8 salvo richiesta esplicita diversa.
