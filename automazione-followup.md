# Automazione lead e follow-up (HubSpot)

Ogni mattina, dal lunedì al venerdì alle 7:47 (ora italiana), un'attività pianificata di Claude controlla in HubSpot
i lead in sequenza, aggiorna la loro fase e ti prepara le attività del giorno. Non invia mai email da sola.

## Cosa fai tu

1. In HubSpot, sul contatto, imposta **Sequenza Cascoo = Da contattare** e scegli la **Variante sequenza** (A diretta o B consulenziale; se la lasci vuota vale A).
2. Manda la cold email da eM Client con il modello `cascoo-cold-A-diretta` o `cascoo-cold-B-consulenziale`.
3. Quando trovi in HubSpot un'attività **[Sequenza]** in scadenza oggi, apri il modello eM Client indicato, invialo e segna l'attività come completata.

Fine. Il resto lo fa l'automazione.

## Cosa fa l'automazione

| Fase attuale | Cosa controlla | Cosa fa |
|---|---|---|
| Da contattare | Trova un'email inviata da te al contatto | Passa a **Cold inviata**, prossimo follow-up a +3 giorni |
| Cold inviata | È arrivato il giorno del follow-up | Crea l'attività **Follow-up 1** con il testo pronto |
| Cold inviata | Trova un nuovo invio tuo | Passa a **Follow-up 1 inviato**, prossimo a +4 giorni (giorno 7) |
| Follow-up 1 inviato | È arrivato il giorno | Crea l'attività **Follow-up 2** |
| Follow-up 1 inviato | Trova un nuovo invio tuo | Passa a **Follow-up 2 inviato**, chiusura a +7 giorni (giorno 14) |
| Follow-up 2 inviato | Sono passati 7 giorni senza risposta | Passa a **Fuori sequenza**, Lead Status = Bad Timing |
| Qualsiasi | Il lead ha risposto (non risposta automatica) | Passa a **Ha risposto**, Lead Status = Connected, attività "Rispondi" ad alta priorità |

Le date che cadono di sabato o domenica slittano al lunedì.
Le risposte automatiche (fuori ufficio, Abwesenheit, ecc.) non fermano la sequenza: l'automazione aggiunge solo una nota.

## Requisiti

- La casella poato@cascoo.eu deve restare collegata a HubSpot (è così che l'automazione vede invii e risposte).
- Se mandi un'email da un'altra casella, HubSpot non la vede: aggiorna tu a mano **Ultimo invio sequenza** e la fase.

## Viste utili in HubSpot

Crea in Contatti una vista filtrata **Sequenza Cascoo è uno tra Cold inviata, Follow-up 1 inviato, Follow-up 2 inviato**
con le colonne Prossimo follow-up e Ultimo invio sequenza: è il tuo cruscotto della sequenza.
