# Automazione lead e follow-up (HubSpot)

Ogni mattina, dal lunedì al venerdì alle 7:47 (ora italiana), un'attività pianificata di Claude controlla in HubSpot
i lead in sequenza, aggiorna la loro fase e ti prepara le attività del giorno. Non invia mai email da sola.

## Cosa fai tu

1. In HubSpot, sul contatto, imposta **Sequenza Cascoo = Da contattare** e scegli la **Variante sequenza** (A diretta o B consulenziale; se la lasci vuota vale A).
2. La mattina dopo trovi l'attività **[Sequenza] Cold email**. Manda la cold da eM Client con il modello indicato (per chi ti ha già scritto l'attività indica il modello di ripresa contatto, con oggetto e data dell'ultimo scambio) e **segna l'attività come completata**.
3. Stessa cosa per **[Sequenza] Follow-up 1** e **[Sequenza] Follow-up 2** quando compaiono.

Segnare l'attività come completata è il passaggio che conta: HubSpot non registra quasi mai le email che invii da eM Client,
quindi è così che l'automazione sa che hai inviato.

## Cosa fa l'automazione

| Fase attuale | Cosa controlla | Cosa fa |
|---|---|---|
| Da contattare | Non c'è ancora l'attività della cold | Crea l'attività **Cold email** |
| Da contattare | Attività Cold email completata | Passa a **Cold inviata**, prossimo follow-up a +3 giorni |
| Cold inviata | È arrivato il giorno | Crea l'attività **Follow-up 1** con il testo pronto |
| Cold inviata | Attività Follow-up 1 completata | Passa a **Follow-up 1 inviato**, prossimo a +4 giorni (giorno 7) |
| Follow-up 1 inviato | È arrivato il giorno | Crea l'attività **Follow-up 2** |
| Follow-up 1 inviato | Attività Follow-up 2 completata | Passa a **Follow-up 2 inviato**, chiusura a +7 giorni (giorno 14) |
| Follow-up 2 inviato | Sono passati 7 giorni senza risposta | Passa a **Fuori sequenza**, Lead Status = Bad Timing |
| Dopo la cold | Il lead ha risposto | Passa a **Ha risposto**, Lead Status = Connected, attività "Rispondi" ad alta priorità |

Le date che cadono di sabato o domenica slittano al lunedì.
Conferme di lettura (Gelesen, Letto), risposte automatiche e mancati recapiti non fermano la sequenza.

## Requisiti

- La casella poato@cascoo.eu deve restare collegata a HubSpot: è così che l'automazione vede le risposte dei lead.
- Il controllo gira dentro la sessione Claude Code in cui è stato creato: non archiviarla.

## Viste utili in HubSpot

Crea in Contatti una vista filtrata **Sequenza Cascoo è uno tra Cold inviata, Follow-up 1 inviato, Follow-up 2 inviato**
con le colonne Prossimo follow-up e Ultimo invio sequenza: è il tuo cruscotto della sequenza.
