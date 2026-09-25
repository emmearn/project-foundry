# Obiettivo

Crea `docs/requirements.md` descrivendo cosa deve fare il sistema e quali risultati deve garantire, senza prendere decisioni implementative. Usa come schema il template incluso in questo prompt e compila soltanto le sezioni applicabili al progetto.

# Fonti

Obbligatorie:

- `docs/vision.md`.

Opzionali:

- descrizione del progetto, contesto di dominio e vincoli forniti dall'utente;
- repository esistente, se disponibile, esclusivamente come evidenza del contesto attuale.

Se `docs/vision.md` manca, non generare il documento: indica esattamente cosa serve per procedere.

# Policy decisionale

- Procedi autonomamente per dettagli reversibili, locali e a basso impatto.
- Dichiara le assunzioni che influenzano materialmente ambito, comportamento o criteri di accettazione.
- Chiedi chiarimenti solo quando alternative plausibili produrrebbero requisiti significativamente diversi.
- Non inventare vincoli legali, commerciali, organizzativi, tecnici o di integrazione non supportati dalle fonti.
- Se una fonte è ambigua ma non blocca la definizione del comportamento atteso, scegli l'interpretazione più semplice e registrala come assunzione.

# Modifiche consentite

- Crea o aggiorna esclusivamente `docs/requirements.md`.
- Non modificare altri file.
- Se non puoi scrivere nel filesystem, restituisci il contenuto completo del documento e segnala che non è stato salvato.

# Confini

Il documento deve definire il comportamento atteso, non la sua implementazione. Non scegliere stack, framework, database, API tecniche, classi, pattern applicativi, design UI dettagliato, controlli di sicurezza implementativi, task o workflow.

# Template di `docs/requirements.md`

Adatta il template al progetto. Ometti sezioni e campi non applicabili; non riempirli con testo generico o formule come "non applicabile".

```md
# Requisiti

## 1. Contesto e obiettivo

- Problema da risolvere
- Utenti o soggetti interessati
- Valore e risultato atteso
- Collegamento sintetico a `docs/vision.md`, senza ripeterne il contenuto

## 2. Ambito

### Incluso

### Escluso

### MVP

## 3. Attori

Elencare solo gli attori che interagiscono con il sistema o ne influenzano il comportamento.

## 4. Flussi e casi d'uso

Descrivere soltanto i flussi necessari a chiarire sequenze, alternative, errori o interazioni tra più attori. Usare casi d'uso oppure user story, scegliendo il formato più adatto; non rappresentare la stessa informazione in entrambi i modi.

## 5. Requisiti

### REQ-001 — Titolo breve

- Tipo: Funzionale | Non funzionale | Vincolo | Regola di dominio
- Priorità: MUST | SHOULD | COULD
- Descrizione: comportamento o risultato osservabile
- Motivazione: perché è necessario, solo se non evidente
- Dipendenze: altri requisiti, solo se presenti
- Criteri di accettazione:
  - condizione osservabile o scenario Given/When/Then

Ripetere la scheda per ogni requisito. Aggiungere attori, precondizioni, alternative o impatti trasversali soltanto quando chiariscono il requisito e non sono già descritti altrove.

## 6. Regole di dominio

Regole condivise da più requisiti, senza duplicarle nelle singole schede.

## 7. Dati, input e output

Definire dati, validazioni e risultati rilevanti a livello di dominio, senza progettare schema fisico, API o persistenza.

## 8. Assunzioni e vincoli

Separare chiaramente fatti espliciti, assunzioni adottate e vincoli imposti dalle fonti.

## 9. Questioni aperte

Includere solo decisioni irrisolte che possono cambiare materialmente ambito o comportamento. Non usare questa sezione per dettagli implementativi.
```

# Criteri di riuscita

- Ogni requisito è atomico, non ambiguo, osservabile e identificato.
- Ogni requisito `MUST` possiede almeno un criterio di accettazione verificabile.
- Requisiti, vincoli, assunzioni e regole di dominio sono distinguibili.
- Casi d'uso, user story e requisiti non duplicano la stessa informazione.
- I requisiti non funzionali esprimono risultati o limiti misurabili quando le fonti consentono di definirli.
- Nessuna decisione tecnica è presentata come requisito, salvo vincolo esplicito delle fonti.
- Il documento è compatto ma completo: la brevità non elimina eccezioni, errori o criteri necessari.
- Il testo è in italiano e codificato in UTF-8, salvo richiesta esplicita diversa.

# Verifica finale

Prima di terminare:

1. confronta ogni sezione con `docs/vision.md`;
2. elimina duplicazioni e contenuti generici;
3. individua contraddizioni, termini ambigui e requisiti non supportati;
4. verifica la copertura dei flussi principali, delle alternative e degli errori rilevanti;
5. correggi direttamente i problemi rilevati nel documento.
