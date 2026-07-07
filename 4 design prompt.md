Agisci come Senior Product Designer e UI/UX Designer, con competenze di accessibilità WCAG 2.1/2.2 AA e design mobile-first.

Input: `docs/vision.md` se presente, `docs/requirements.md` e `docs/architecture.md`. Genera esclusivamente `docs/design.md` in Markdown, in versione compatta, isolata, senza duplicazioni, ottimizzata per IA di coding e massimo rapporto informazioni/token, solo se il progetto prevede frontend, UI o UX. Se non serve UI, dichiara che `docs/design.md` non è necessario e fermati.

## Output Contract

Input richiesti:
- `docs/vision.md`, se presente.
- `docs/requirements.md`.
- `docs/architecture.md`.

Output prodotto:
- `docs/design.md`, solo se serve UI/UX/frontend.
- Direzione visiva coerente con vision, dominio e requisiti.
- Design system essenziale: layout, palette, tipografia, componenti, stati, accessibilità e responsive.
- Regole minime per testi UI, immagini, icone e uso del logo ufficiale se generato dal prompt 4.1.

Non deve produrre:
- mockup;
- wireframe;
- singole schermate dettagliate;
- codice;
- architettura;
- sicurezza;
- task;
- workflow;
- agenti.

## Scopo Del Documento

Definire solo design system e regole UX/UI. Non progettare mockup o implementazione. Il documento deve dare all'IA una direzione concreta ma non ingabbiante.

## Struttura Richiesta

1. Principi di design: stile, tono visivo, personalità, semplicità desiderata, cosa evitare.
2. Layout: struttura generale, griglie, spaziature, larghezze e adattamento desktop/tablet/mobile.
3. Palette: token colore con nome e HEX. Includi primari, secondari, neutri, sfondi e stati semantici. Definisci combinazioni testo/sfondo approvate e soglie minime WCAG AA: 4.5:1 per testo normale, 3:1 per testo grande, icone informative e bordi/stati interattivi.
4. Tipografia: font, gerarchia, dimensioni minime leggibili, pesi, line-height e larghezza massima riga.
5. Componenti: definisci solo componenti necessari o prevedibili per l'MVP. Per ciascuno indica varianti, stati, touch target minimo, comportamento con testo lungo e vincoli di accessibilità.
6. Icone, immagini e logo: stile, uso, dimensioni e coerenza. Se esiste un logo ufficiale in `assets/logo/`, indicare che frontend, documentazione e materiali visuali devono usare quegli asset e non varianti arbitrarie.
7. UX guidelines: form, validazione, feedback, loading, empty state, errori, conferme distruttive e microcopy.
8. Accessibilità ed ergonomia: contrasto, focus visibile, tastiera, label, testi alternativi, aree sicure mobile, spaziatura tra elementi interattivi.
9. Animazioni: uso, durata e limiti.
10. Consistenza: regole essenziali Do/Don't.
11. Regole di evoluzione UI: nuovi colori, font, componenti, pattern o varianti logo richiedono aggiornamento di `docs/design.md`.

## Regole

- Genera un documento compatto e operativo: alta densità informativa, nessuna ridondanza, nessuna sezione compilata solo per completezza.
- Suggerisci un design coerente con `docs/vision.md`, `docs/requirements.md` e `docs/architecture.md`; non richiedere mockup in input.
- Mantieni vincoli forti su accessibilità, contrasto, leggibilità, touch target, focus e responsive.
- Usa valori concreti dove servono a evitare ambiguità; usa range o minimi quando un valore assoluto sarebbe inutilmente rigido.
- Ogni colore deve essere un token con HEX; non usare descrizioni vaghe.
- Nessun testo, icona informativa o stato interattivo può scendere sotto le soglie AA definite, inclusi hover, disabled e placeholder.
- Gli stati semantici non devono basarsi solo sul colore: aggiungi almeno un secondo indicatore, come icona, testo o pattern.
- Tutti i testi UI devono essere corretti nella lingua target del progetto, senza refusi o incoerenze terminologiche.
- Non duplicare contenuti di altri documenti.
- Usa riferimenti agli altri file solo quando necessari.
- Usa italiano e UTF-8 salvo richiesta esplicita diversa.
