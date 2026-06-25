Prompt per generare docs/design.md

Agisci come Senior Product Designer e UI/UX Designer.

Input: docs/requirements.md e docs/architecture.md. Genera esclusivamente docs/design.md in Markdown, in versione compatta, isolata, senza duplicazioni, ottimizzata per IA di coding e massimo rapporto informazioni/token, solo se il progetto prevede frontend, UI o UX. Se non serve UI, dichiara che docs/design.md non è necessario e fermati.

Scopo del documento
Definire solo design system e regole UX/UI. Non progettare singole schermate, mockup o implementazione.

Struttura richiesta
1. Principi di design: stile, tono visivo, semplicità desiderata, cosa evitare.
2. Layout: struttura generale, griglie, spaziature, larghezze, desktop/tablet/mobile.
3. Palette: primari, secondari, neutri, sfondi, success/warning/error/info.
4. Tipografia: font, gerarchia, dimensioni, pesi e spaziature.
5. Componenti: pulsanti, input, select, checkbox, card, tabelle, modali/dialog, menu, navbar/sidebar, alert, toast, badge.
6. Icone e immagini: stile, uso, dimensioni e coerenza.
7. UX guidelines: form, validazione, feedback, loading, empty state, errori, conferme distruttive.
8. Accessibilità: contrasto, focus, tastiera, label, testi alternativi, responsive.
9. Animazioni: uso, durata e limiti.
10. Consistenza: Do/Don't per uniformità.
11. Regole di implementazione UI: riuso componenti; nuovi colori/font/stili solo aggiornando docs/design.md.

Regole
- Usa requirements e architecture solo come contesto.
- Non generare codice, mockup, architecture, security, tasks, workflow o agents.
- Questo file è la fonte di verità per UI/UX e design system.
- Non duplicare contenuti di altri documenti.
- Usa riferimenti agli altri file solo quando necessari.
