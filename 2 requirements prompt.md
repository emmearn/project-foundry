Agisci come Product Owner e analista funzionale senior.

Input: `docs/vision.md` se presente, descrizione del progetto e `docs/requirements_template.md`. Genera esclusivamente `docs/requirements.md` in Markdown, in versione compatta, isolata, senza duplicazioni, ottimizzata per IA di coding e massimo rapporto informazioni/token.

## Output Contract

Input richiesti:
- `docs/vision.md`, se presente.
- `docs/requirements_template.md`.
- Descrizione del progetto o contesto di dominio, se forniti.

Output prodotto:
- `docs/requirements.md`.
- Visione funzionale, ambito, attori, casi d'uso, requisiti funzionali e non funzionali.
- Regole di dominio, assunzioni, vincoli e tracciabilità futura.

Non deve produrre:
- architettura;
- database;
- API tecniche;
- classi;
- librerie o framework, salvo vincoli espliciti;
- design;
- sicurezza dettagliata;
- task;
- workflow;
- codice;
- agenti.

## Scopo Del Documento

Definire cosa deve fare il sistema. Non descrivere come verrà implementato. Usa `docs/requirements_template.md` come standard vincolante.

## Struttura Richiesta

1. Vision: scopo, problema, utenti target, valore atteso.
2. Ambito: funzionalità incluse, esclusioni, MVP, possibili evoluzioni future.
3. Attori e casi d'uso: flussi principali, alternative ed errori rilevanti.
4. Funzionalità principali: descrizione, input, output, vincoli di dominio, attori.
5. User stories: Come/Voglio/In modo da.
6. Requisiti funzionali: requisiti atomici nel formato di `docs/requirements_template.md`.
7. Requisiti non funzionali: prestazioni, affidabilità, compatibilità, scalabilità, manutenibilità, sicurezza, accessibilità e operatività solo se rilevanti.
8. Input, output e validazioni di dominio.
9. Regole di dominio, policy, assunzioni e vincoli.
10. Tracciabilità: predisporre collegamenti futuri a `docs/tasks.md` e `docs/decisions.md`; usare "Da definire" se non disponibili.

## Regole

- Genera un documento compatto e operativo: alta densità informativa, nessuna ridondanza, nessuna sezione compilata solo per completezza.
- Questo file è la fonte di verità del comportamento atteso.
- I requisiti non funzionali definiscono obiettivi e vincoli osservabili; le policy tecniche dettagliate spettano ai documenti successivi.
- Se qualcosa è ambiguo, fai assunzioni ragionevoli e dichiarale.
- Usa tabelle ed elenchi solo quando aumentano chiarezza e compattezza.
- Usa italiano e UTF-8 salvo richiesta esplicita diversa.
