# Obiettivo

Crea `docs/security.md` identificando rischi reali del progetto e traducendoli in controlli, vincoli e verifiche proporzionati. Parti da asset, dati, attori, confini di fiducia e flussi; usa le pratiche generali di sicurezza come controllo finale, non come checklist da compilare automaticamente.

# Fonti

Obbligatorie:

- `docs/vision.md`;
- `docs/requirements.md`;
- `docs/architecture.md`.

Opzionali:

- `docs/design.md`, se presente;
- repository e configurazione esistenti, se disponibili;
- `docs/decisions.md`, se presente;
- vincoli normativi o organizzativi forniti esplicitamente dall'utente.

Se manca una fonte obbligatoria, non generare il documento: indica esattamente cosa serve per procedere.

# Policy decisionale

- Applica controlli proporzionati agli asset, all'esposizione e all'impatto plausibile.
- Non inventare dati sensibili, requisiti normativi, certificazioni, ruoli o superfici d'attacco non supportati dalle fonti.
- Procedi autonomamente per misure consolidate, compatibili con l'architettura e prive di trade-off sostanziali.
- Dichiara assunzioni che influenzano minacce, impatto o controlli.
- Chiedi chiarimenti quando dati trattati, confini di fiducia o responsabilità esterne non sono determinabili e cambierebbero materialmente il rischio.
- Evidenzia il rischio residuo invece di presentare ogni controllo come garanzia assoluta.

# Modifiche consentite

- Crea o aggiorna esclusivamente `docs/security.md`.
- Non modificare codice, configurazione o altri documenti.
- Se non puoi scrivere nel filesystem, restituisci il contenuto completo del documento e segnala che non è stato salvato.

# Contenuto richiesto

Adatta la struttura al progetto e ometti le sezioni non applicabili.

1. **Contesto e obiettivi di sicurezza**: ambito, assunzioni e proprietà da preservare.
2. **Asset e dati**: informazioni, funzioni e risorse da proteggere; sensibilità, esposizione e ciclo di vita rilevante.
3. **Attori e privilegi**: utenti, amministratori, servizi e soggetti esterni, con capacità e limiti.
4. **Confini di fiducia e superfici d'attacco**: punti in cui dati o controllo attraversano sistemi, processi o responsabilità differenti.
5. **Flussi sensibili**: autenticazione, autorizzazione, dati, file, pagamenti, integrazioni o operazioni privilegiate quando presenti.
6. **Registro delle minacce**: per ogni rischio usare un ID `RISK-001`, scenario, asset coinvolto, probabilità qualitativa, impatto, mitigazioni, verifica e rischio residuo.
7. **Controlli e vincoli**: organizzati per aree realmente presenti, come identità, autorizzazione, validazione, segreti, dati, comunicazioni, filesystem, API, frontend, logging, dipendenze e operatività.
8. **Pratiche vietate**: divieti specifici e applicabili al progetto, non un catalogo indiscriminato.
9. **Verifica della sicurezza**: controlli automatici o manuali collegati ai rischi prioritari.
10. **Decisioni e questioni aperte**: scelte significative da registrare in `docs/decisions.md` e informazioni mancanti che cambiano il rischio.

# Confini

- Non riscrivere architettura o requisiti funzionali.
- Trasforma le scelte architetturali in vincoli di sicurezza soltanto quando esiste un rischio collegato.
- La struttura tecnica dei log resta in `docs/architecture.md`; qui definisci dati vietati, redazione, accesso e rischi.
- Non creare task, workflow o codice.
- Non prescrivere servizi o prodotti specifici quando è sufficiente definire il controllo richiesto.

# Criteri di riuscita

- Ogni controllo mitiga una minaccia, protegge un asset o soddisfa un vincolo esplicito.
- Minacce e mitigazioni sono prioritizzate, verificabili e collegate all'architettura reale.
- Autenticazione, autorizzazione e privacy compaiono solo se pertinenti, con il livello di dettaglio necessario.
- Segreti, dati sensibili e log hanno regole operative chiare quando presenti.
- Il documento distingue rischio mitigato, accettato e ancora aperto.
- Non sono introdotti obblighi normativi o controlli sproporzionati.
- Il testo è in italiano e codificato in UTF-8, salvo richiesta esplicita diversa.

# Verifica finale

Prima di terminare:

1. ricostruisci mentalmente i principali flussi e confini di fiducia;
2. verifica che ogni rischio prioritario abbia mitigazione, verifica e rischio residuo;
3. cerca controlli generici senza una minaccia corrispondente;
4. controlla duplicazioni o conflitti con `docs/architecture.md`;
5. correggi direttamente omissioni e misure sproporzionate.
