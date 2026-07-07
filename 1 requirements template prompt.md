Agisci come Requirements Engineer senior e AI Coding Workflow Architect.

Input: `docs/vision.md` se presente, descrizione del progetto e contesto di dominio. Genera esclusivamente `docs/requirements_template.md` in Markdown, in versione compatta, isolata, senza duplicazioni, ottimizzata per IA di coding e massimo rapporto informazioni/token.

## Output Contract

Input richiesti:
- `docs/vision.md`, se presente.
- Descrizione del progetto o contesto di dominio, se forniti.

Output prodotto:
- `docs/requirements_template.md`.
- Standard compatto per scrivere `docs/requirements.md`.
- Formato requisiti, classificazioni, criteri di accettazione e tracciabilità futura.

Non deve produrre:
- requisiti del progetto;
- architettura;
- design;
- sicurezza;
- task;
- workflow;
- codice;
- agenti.

## Scopo Del Documento

Definire solo lo standard con cui scrivere `docs/requirements.md`. Non definire requisiti del progetto.

## Struttura Richiesta

1. Principi di scrittura: requisiti chiari, atomici, non ambigui, verificabili, testabili e tracciabili.
2. Separazione concettuale: requisito, vincolo, assunzione, regola di dominio, criterio di accettazione.
3. Formato requisito: scheda o tabella compatta con ID, titolo, descrizione, motivazione, attori, precondizioni, flusso principale, alternative/errori, regole di dominio, criteri di accettazione, impatti, priorità, stato, tracciabilità.
4. ID e classificazioni: `REQ-001`; priorità `MUST/SHOULD/COULD`; stati `Draft/Approved/Changed/Deprecated`.
5. Criteri di accettazione: `Given/When/Then` o checklist osservabili.
6. Tracciabilità: collegamenti futuri a `docs/tasks.md`, `docs/decisions.md`, test e rischi.
7. Impatti trasversali: sicurezza, dati, privacy, integrazioni, performance, accessibilità e operatività solo se rilevanti.
8. Esempio minimo: requisito generico compilato, senza stack tecnologico.

## Regole

- Genera un documento compatto e operativo: alta densità informativa, nessuna ridondanza, nessuna sezione compilata solo per completezza.
- Non generare `docs/requirements.md`.
- Non scegliere librerie, framework, database o pattern applicativi.
- Non duplicare responsabilità degli altri documenti.
- Usa riferimenti ad altri file solo per tracciabilità futura.
- Usa italiano e UTF-8 salvo richiesta esplicita diversa.
