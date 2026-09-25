# Obiettivo

Crea `docs/architecture.md` definendo come costruire o evolvere il sistema per soddisfare `docs/requirements.md`. Produci decisioni tecniche motivate, proporzionate e applicabili, senza introdurre funzionalità non richieste.

# Fonti

Obbligatorie:

- `docs/vision.md`;
- `docs/requirements.md`.

Opzionali:

- repository esistente, inclusi manifest, configurazione, struttura e convenzioni;
- vincoli tecnici forniti dall'utente;
- `docs/decisions.md`, se presente.

Se manca una fonte obbligatoria, non generare il documento: indica esattamente cosa serve per procedere.

# Policy decisionale

- Determina dalle fonti e dal repository disponibile se il progetto è nuovo o esistente; non richiedere un parametro dedicato.
- In un progetto esistente, preserva stack, struttura, interfacce pubbliche e convenzioni già adottate, salvo incompatibilità con i requisiti o richiesta esplicita di cambiamento.
- Se la descrizione del progetto e il repository divergono, segnala la discrepanza e non scegliere arbitrariamente quale sia corretta.
- Procedi autonomamente per decisioni reversibili, locali e chiaramente dominate da una soluzione semplice.
- Dichiara assunzioni e trade-off che influenzano struttura, dati, integrazioni o operatività.
- Chiedi chiarimenti solo quando alternative plausibili comportano differenze sostanziali in costi, rischi, compatibilità o comportamento.
- Preferisci la soluzione più semplice capace di soddisfare i requisiti; non aggiungere componenti per completezza teorica.

# Modifiche consentite

- Crea o aggiorna esclusivamente `docs/architecture.md`.
- Non modificare codice, configurazione o altri documenti.
- Se non puoi scrivere nel filesystem, restituisci il contenuto completo del documento e segnala che non è stato salvato.

# Contenuto richiesto

Adatta la struttura al progetto e ometti le sezioni non applicabili.

1. **Contesto tecnico**: obiettivi architetturali, vincoli derivati dai requisiti e stato esistente rilevante.
2. **Architettura generale**: stile, confini e responsabilità principali, con mappatura sintetica ai requisiti più importanti.
3. **Stack e dipendenze principali**: tecnologie nuove o esistenti e motivazione delle scelte; non elencare dipendenze minori.
4. **Componenti e dipendenze consentite**: responsabilità, interfacce e direzione delle dipendenze.
5. **Struttura del repository**: cartelle o package necessari e convenzioni essenziali.
6. **Dati**: entità, relazioni, proprietà e ciclo di vita al livello richiesto, senza anticipare dettagli inutili.
7. **Flussi tecnici critici**: soltanto sequenze con più componenti, integrazioni o failure mode rilevanti.
8. **Integrazioni e configurazione**: confini esterni, timeout, retry, proprietà e variabili d'ambiente; rimandare segreti e controlli a `docs/security.md`.
9. **Errori, logging e osservabilità**: regole tecniche, livelli, informazioni diagnostiche e identificatori di correlazione quando utili.
10. **Prestazioni e scalabilità**: solo obiettivi e misure giustificati dai requisiti.
11. **Strategia di verifica**: test e controlli adeguati ai confini e ai rischi del sistema.
12. **Convenzioni di sviluppo**: naming, pattern, dipendenze, documentazione del codice e compatibilità da preservare.
13. **Decisioni e questioni aperte**: decisioni significative da registrare in `docs/decisions.md` e scelte realmente irrisolte.

Usa diagrammi testuali solo quando rendono più chiari confini o sequenze che la prosa non descrive altrettanto bene.

# Confini

- Non riscrivere i requisiti funzionali.
- Non definire design UI/UX o asset visuali.
- Non produrre un catalogo generico di controlli di sicurezza.
- Non creare roadmap, task, workflow o codice applicativo.
- La logging policy tecnica appartiene a questo documento; masking, dati vietati e rischi dei log appartengono a `docs/security.md`.

# Criteri di riuscita

- Ogni componente o tecnologia risponde a un requisito, a un vincolo o a una necessità operativa identificabile.
- Le dipendenze consentite e i confini tra componenti sono espliciti.
- Le scelte esistenti sono preservate oppure la loro sostituzione è motivata.
- Alternative e trade-off sono documentati solo per decisioni significative.
- La strategia di verifica è proporzionata ai rischi e non impone test privi di valore diagnostico.
- Il documento è compatto, operativo e privo di sezioni compilate per completezza.
- Il testo è in italiano e codificato in UTF-8, salvo richiesta esplicita diversa.

# Verifica finale

Prima di terminare:

1. verifica la copertura dei requisiti e dei vincoli tecnici;
2. cerca tecnologie, componenti o pattern non giustificati;
3. controlla incompatibilità con il repository esistente;
4. elimina duplicazioni con requisiti e sicurezza;
5. correggi direttamente incoerenze e dettagli prematuri.
