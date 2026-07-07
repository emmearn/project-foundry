Prompt per generare docs/design.md

Agisci come Senior Product Designer e UI/UX Designer, con competenze specifiche di accessibilità (WCAG 2.1/2.2 AA) e design di interfacce mobile-first.

Input: docs/requirements.md e docs/architecture.md. Genera esclusivamente docs/design.md in Markdown, in versione compatta, isolata, senza duplicazioni, ottimizzata per IA di coding e massimo rapporto informazioni/token, solo se il progetto prevede frontend, UI o UX. Se non serve UI, dichiara che docs/design.md non è necessario e fermati.

Scopo del documento
Definire solo design system e regole UX/UI. Non progettare singole schermate, mockup o implementazione.

Struttura richiesta

1. Principi di design: stile, tono visivo, semplicità desiderata, cosa evitare.

2. Layout: struttura generale, griglie, spaziature, larghezze, desktop/tablet/mobile.

3. Palette (sezione a controllo rigoroso):
   - Definisci ogni colore come token (nome + valore HEX), non come descrizione generica.
   - Categorie obbligatorie: primari, secondari, neutri (almeno 5 gradazioni da testo-scuro a sfondo-chiaro), sfondi (base/alternato/elevato), stati semantici (success/warning/error/info) con relativa variante "on-color" per il testo sopra.
   - Per ogni combinazione testo/sfondo effettivamente usata nei componenti, specifica il rapporto di contrasto minimo richiesto: 4.5:1 per testo normale, 3:1 per testo grande (≥18px regular o ≥14px bold) e per icone/elementi grafici informativi, 3:1 per i bordi/stati di componenti interattivi (WCAG 2.1 AA).
   - Vieta esplicitamente combinazioni a basso contrasto (es. testo grigio chiaro su bianco, colore su colore simile in luminanza) e indica una regola generale: "nessun testo o icona informativa può scendere sotto la soglia di contrasto AA, indipendentemente dallo stato (hover, disabled, placeholder)". Per lo stato disabled, definisci comunque una soglia minima di leggibilità (non solo estetica).
   - Specifica come si segnala uno stato (errore, successo, warning) non solo col colore ma anche con un secondo indicatore (icona, testo, pattern), per non affidarsi al colore da solo.
   - Se possibile, fornisci la palette in forma tabellare: Nome token | HEX | Uso | Contrasto minimo richiesto | Coppia di riferimento (testo/sfondo).

4. Tipografia: font, gerarchia, dimensioni, pesi, spaziature. Specifica dimensione minima leggibile per corpo testo (mai sotto 14-16px su mobile), altezza riga minima (line-height ≥1.4 per testo corrente), e larghezza massima riga per leggibilità (misura ottimale caratteri per riga).

5. Componenti: pulsanti, input, select, checkbox, card, tabelle, modali/dialog, menu, navbar/sidebar, alert, toast, badge.
   - Pulsanti: definisci area minima di tocco 44x44pt (iOS) / 48x48dp (Android) o equivalente, padding interno minimo orizzontale/verticale che garantisca spazio sufficiente per il testo più lungo previsto (no troncamenti forzati, gestione a capo o ellissi solo come fallback esplicito), spaziatura minima tra pulsanti/elementi tappabili adiacenti per evitare tocchi accidentali.
   - Per ogni componente interattivo, specifica dimensione minima touch target su mobile e comportamento in caso di testo variabile (multilingua, testo lungo).

6. Icone e immagini: stile, uso, dimensioni e coerenza.

7. UX guidelines: form, validazione, feedback, loading, empty state, errori, conferme distruttive.
   - Tutti i testi UI (label, placeholder, messaggi di errore/successo/warning, microcopy, testi di bottoni, empty state) devono essere corretti dal punto di vista ortografico e grammaticale nella lingua target del progetto: nessun refuso, nessun errore di battitura, nessuna incoerenza terminologica tra componenti equivalenti.

8. Accessibilità ed ergonomia (sezione a controllo rigoroso):
   - Contrasto: rimanda ai valori definiti in sezione 3, applicabili a tutti i componenti senza eccezioni.
   - Focus: stile di focus visibile e distinguibile su ogni elemento interattivo, con contrasto minimo 3:1 rispetto allo sfondo adiacente.
   - Tastiera: tutti gli elementi interattivi devono essere navigabili e attivabili da tastiera, ordine di tabulazione logico.
   - Label e testi alternativi: obbligatori su ogni input, icona funzionale e immagine informativa.
   - Ergonomia mobile: posiziona le azioni primarie/frequenti nella zona raggiungibile dal pollice (parte bassa/centrale dello schermo), evita azioni critiche negli angoli superiori estremi, mantieni spaziatura minima tra elementi tappabili per prevenire mis-tap, tieni conto di aree sicure (notch, gesture bar).
   - Responsive: regole minime di adattamento tra breakpoint (nessun testo o pulsante che si comprima sotto le soglie di leggibilità/tocco definite sopra).

9. Animazioni: uso, durata e limiti.

10. Consistenza: Do/Don't per uniformità.

11. Regole di implementazione UI: riuso componenti; nuovi colori/font/stili solo aggiornando docs/design.md, con verifica obbligatoria del contrasto prima dell'aggiunta di qualsiasi nuovo token colore. Ogni nuovo testo UI introdotto va sottoposto a controllo ortografico/grammaticale prima dell'inserimento.

Regole
- Usa requirements e architecture solo come contesto.
- Non generare codice, mockup, architecture, security, tasks, workflow o agents.
- Ogni valore di colore, dimensione o soglia deve essere un numero o HEX concreto, mai una descrizione vaga (es. no "contrasto adeguato", sì "contrasto minimo 4.5:1").
- Prima di finalizzare il documento, esegui un controllo ortografico e grammaticale su tutti i testi presenti (inclusi i testi di esempio nei componenti e nelle UX guidelines): correggi refusi, errori di battitura, concordanze errate e incoerenze terminologiche.
- Questo file è la fonte di verità per UI/UX e design system.
- Non duplicare contenuti di altri documenti.
- Usa riferimenti agli altri file solo quando necessari.