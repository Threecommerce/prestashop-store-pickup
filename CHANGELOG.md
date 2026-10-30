# Changelog

## 1.0.1 — 2026-10-29
- Fix (grave): il corriere "Ritiro in negozio" non compariva al checkout (PrestaShop scarta i corrieri di modulo senza fasce). Ora il corriere ha `need_range`, una fascia ampia di peso e di prezzo e righe `delivery` a 0 per ogni zona; il costo resta quello del modulo.
- Aggiornamento da 1.0.0: `upgrade-1.0.1` ripara il corriere esistente; le zone aggiunte o riattivate dopo vengono coperte (hook `actionObjectZoneAddAfter`/`UpdateAfter`).
- Fix: il salvataggio della configurazione falliva sempre su PrestaShop 9 ("Token di sicurezza non valido"), ora validato con il meccanismo del core (PS 8 e 9).
- Fix: il blocco del negozio di ritiro è ora visibile nel dettaglio ordine e nel tracciamento ospite del tema Hummingbird (hook chiamato senza parametri): l'ordine è ricavato dalla richiesta con la stessa autorizzazione del core.

## 1.0.0 — 2026-10-27
- Prima versione, port di `m2-store-pickup` 2.1.0 per PrestaShop 8/9.
- Corriere "Ritiro in negozio" creato all'installazione (costo configurabile, 0 = gratuito; nascosto se nessun negozio è abilitato).
- Flag "Disponibile per il ritiro" per negozio, aggiunto al form dello store locator tramite i suoi hook.
- Scelta del negozio al checkout da elenco o mappa (Google Maps / OpenStreetMap, configurazione dello store locator) con `displayCarrierExtraContent`.
- Blocco lato server: passo Spedizione e validazione ordine rifiutano il ritiro senza un negozio valido.
- Negozio di ritiro salvato con l'ordine e mostrato in conferma ordine, dettaglio ordine, e-mail e back office.
- Traduzione italiana.
