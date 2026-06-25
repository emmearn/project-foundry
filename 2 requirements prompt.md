Prompt per generare docs/requirements.md

Agisci come Product Owner e analista funzionale senior.

Input: vision.md se presente, descrizione del progetto e docs/requirements_template.md. Genera esclusivamente docs/requirements.md in Markdown, in versione compatta, isolata, senza duplicazioni, ottimizzata per IA di coding e massimo rapporto informazioni/token.

Scopo del documento
Definire cosa deve fare il sistema. Non descrivere come verrà implementato. Usa docs/requirements_template.md come standard vincolante.

Struttura richiesta
1. Vision: scopo, problema, utenti target, valore atteso.
2. Ambito: funzionalità incluse, esclusioni, MVP, possibili evoluzioni future.
3. Attori e casi d'uso: flussi principali, alternative ed errori rilevanti.
4. Funzionalità principali: descrizione, input, output, vincoli di dominio, attori.
5. User stories: Come/Voglio/In modo da.
6. Requisiti funzionali: requisiti atomici nel formato di docs/requirements_template.md.
7. Requisiti non funzionali: prestazioni, affidabilità, compatibilità, scalabilità, manutenibilità, sicurezza, accessibilità e operatività solo se rilevanti.
8. Input, output e validazioni di dominio.
9. Regole di dominio, policy, assunzioni e vincoli.
10. Tracciabilità: predisporre collegamenti futuri a docs/tasks.md e docs/decisions.md; usare "Da definire" se non disponibili.

Regole
- Non descrivere architettura, database, API, classi, librerie o framework salvo vincoli espliciti.
- Non generare codice, design, security, tasks, workflow o agents.
- Questo file è la fonte di verità del comportamento atteso.
- Se qualcosa è ambiguo, fai assunzioni ragionevoli e dichiarale.
- Usa tabelle ed elenchi solo quando aumentano chiarezza e compattezza.
