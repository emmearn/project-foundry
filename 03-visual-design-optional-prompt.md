# Applicabilità

Questo prompt è opzionale. Eseguilo solo quando il progetto richiede UI, UX, identità visiva, logo o altri asset di brand.

Determina dalle fonti quali risultati sono necessari:

- se serve UI/UX, crea `docs/design.md`;
- se sono richiesti esplicitamente logo o identità visiva, crea gli asset in `assets/logo/` e documentane l'uso in `docs/design.md`;
- se servono entrambi, trattali come un unico sistema visivo coerente;
- non generare logo o asset di brand per la sola presenza di un frontend.

Se dalle fonti non emerge alcuna esigenza visuale, non modificare file e segnala che il passaggio può essere saltato.

# Obiettivo

Definisci la direzione UI/UX e visuale minima necessaria a implementare il progetto in modo coerente. Il documento deve guidare le decisioni senza trasformarsi in un design system sovradimensionato o in una raccolta di dettagli prematuri.

# Fonti

Obbligatorie:

- `docs/vision.md`;
- `docs/requirements.md`;
- `docs/architecture.md`.

Opzionali:

- riferimenti visuali e preferenze forniti dall'utente;
- UI o asset già presenti nel repository;
- `docs/decisions.md`, se presente.

Se manca una fonte obbligatoria, non generare gli artefatti: indica esattamente cosa serve per procedere.

# Policy decisionale

- Deriva stile, gerarchia e comportamento dalle fonti; non imporre tendenze o preferenze personali.
- Procedi autonomamente per scelte reversibili e locali che non cambiano identità o comportamento del prodotto.
- Dichiara assunzioni che influenzano struttura dell'interfaccia, tono o identità visiva.
- Chiedi chiarimenti solo quando direzioni plausibili produrrebbero esperienze o identità sostanzialmente diverse.
- Usa valori concreti soltanto quando evitano ambiguità implementative; preferisci principi, range e token essenziali a specifiche pervasive.
- Riusa componenti, stili e asset esistenti quando coerenti con le fonti.

# Modifiche consentite

- Crea o aggiorna `docs/design.md`.
- Crea o aggiorna file in `assets/logo/` solo quando logo o identità visiva sono richiesti esplicitamente.
- Non modificare codice applicativo, architettura, requisiti, sicurezza, task o workflow.
- Se non puoi scrivere nel filesystem, restituisci la specifica completa e segnala quali artefatti non sono stati salvati.

# Contenuto di `docs/design.md`

Adatta il documento alle esigenze effettive. Ometti categorie non utili.

1. **Obiettivo dell'esperienza**: utenti, contesto d'uso e qualità percettive da ottenere.
2. **Direzione visuale**: stile, tono, personalità e scelte da evitare.
3. **Struttura e flussi**: gerarchia delle informazioni, viste o superfici necessarie e percorsi principali; non produrre mockup dettagliati.
4. **Layout e adattamento**: principi di composizione, densità, spaziatura e comportamento sui formati rilevanti.
5. **Fondamenti visuali**: colori, tipografia, icone e immagini strettamente necessari. Definisci token riutilizzabili quando servono all'implementazione; evita palette o scale estese senza necessità.
6. **Componenti**: solo componenti richiesti o chiaramente prevedibili per l'MVP, con varianti e comportamenti essenziali.
7. **Stati e interazioni**: normale, focus, loading, empty, errore, successo e disabled quando applicabili; includi validazione, feedback e azioni distruttive.
8. **Accessibilità e usabilità**: leggibilità, navigazione da tastiera, focus riconoscibile, semantica, alternative testuali, dimensionamento degli elementi interattivi e stati non comunicati dal solo colore. Esprimi risultati verificabili senza imporre uno standard nominale non richiesto.
9. **Contenuti e microcopy**: tono, terminologia e regole necessarie a evitare testi ambigui o incoerenti.
10. **Evoluzione**: quando una nuova scelta visuale richiede l'aggiornamento di `docs/design.md`.

Se il progetto richiede soltanto un logo o un'identità visiva senza UI, crea un documento minimale contenente direzione visuale, token necessari e regole d'uso degli asset.

# Sottofase logo e identità visiva

Esegui questa sottofase soltanto quando richiesta esplicitamente dalle fonti o dall'utente.

1. Valuta sinteticamente le direzioni coerenti con il progetto e scegline una sola.
2. Genera un simbolo semplice, riconoscibile, scalabile e utilizzabile su sfondi rilevanti.
3. Usa esclusivamente colori e stile definiti in `docs/design.md`.
4. Se gli strumenti lo consentono, produci soltanto le varianti realmente necessarie, scegliendo tra:

```text
assets/logo/logo.svg
assets/logo/logo.png
assets/logo/logo-light.png
assets/logo/logo-dark.png
assets/logo/logo-icon.png
```

5. Non dichiarare vettoriale un asset raster e non creare file segnaposto. Se non puoi generare immagini, inserisci in `docs/design.md` una specifica realizzabile e segnala il limite.
6. Documenta in `docs/design.md` percorsi, variante per contesto, dimensione minima, area libera e trasformazioni vietate.
7. Evita dettagli fragili e cliché visuali, salvo pertinenza esplicita con la vision.

# Criteri di riuscita

- Ogni scelta visuale deriva da un'esigenza, da una fonte o da un vincolo del progetto.
- Il documento contiene abbastanza informazioni per un'implementazione coerente, senza anticipare ogni schermata o variante possibile.
- Componenti, stati e flussi coprono l'MVP senza creare un catalogo generico.
- Le aspettative di accessibilità e usabilità sono osservabili e applicabili.
- Gli asset di brand vengono prodotti solo quando richiesti e risultano coerenti con il sistema visuale.
- Il testo è in italiano e codificato in UTF-8, salvo richiesta esplicita diversa.

# Verifica finale

Prima di terminare:

1. confronta il risultato con vision, requisiti e vincoli tecnici;
2. elimina dettagli non motivati, componenti ipotetici e ripetizioni;
3. verifica la presenza degli stati necessari e dei principali percorsi utente;
4. controlla coerenza, leggibilità e utilizzabilità sui contesti rilevanti;
5. se hai generato asset, verifica che esistano, siano richiamati correttamente e non contraddicano `docs/design.md`.
