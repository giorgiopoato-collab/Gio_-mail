# Pulsanti di richiesta per email ai lead

Apri `generatore-pulsanti.html` nel browser (doppio clic sul file).

1. Inserisci l'email dove vuoi ricevere le richieste, il tuo nome e, se vuoi, l'azienda del lead.
2. Scegli la frase sopra i pulsanti (diretta o consulenziale, con il tu o con il Lei).
3. Premi **Copia per Gmail / Outlook** e incolla nel corpo dell'email.
   Per HubSpot o altri strumenti di email marketing usa **Copia codice HTML**.

## Cosa succede quando il lead clicca

Gli si apre il suo programma di posta con un'email già indirizzata a te:

| Pulsante | Oggetto | Campi già pronti da compilare |
|---|---|---|
| Richiedi campionatura | Richiesta campionatura - [Azienda] | Azienda, referente, articoli, indirizzo di spedizione |
| Richiedi preventivo | Richiesta preventivo - [Azienda] | Azienda, referente e telefono, articoli, quantità annua, tempi di consegna |
| Fissa una visita in sede | Richiesta visita in sede - [Azienda] | Azienda, indirizzo sede, referente, giorni preferiti, argomenti |

Il lead deve solo compilare le righe e premere invio. Così le richieste ti arrivano già qualificate.

## Limiti da sapere

- Il link funziona solo se il lead ha un programma di posta configurato (quasi sempre vero in azienda).
  Su webmail senza app predefinita il clic può non aprire nulla.
- Con un link email non puoi sapere chi ha cliccato senza inviare. Se ti serve tracciare i clic,
  il passo successivo è sostituire i link con un modulo (ad esempio un modulo HubSpot).

## Modelli per eM Client

Nella cartella `modelli-emclient/` ci sono due email complete, testo e pulsanti insieme, con le richieste indirizzate a poato@cascoo.eu:

- `cascoo-cold-A-diretta.html`
- `cascoo-cold-B-consulenziale.html`
- `cascoo-followup1-A-diretta.html` e `cascoo-followup1-B-consulenziale.html` (dopo 3 giorni)
- `cascoo-followup2-A-diretta.html` e `cascoo-followup2-B-consulenziale.html` (dopo 7 giorni)

Per importarle: in eM Client vai su Impostazioni > Posta > Modelli e firme > Modelli di posta > Nuovo.
Poi clic destro nell'editor > Modifica sorgente, incolla tutto il contenuto del file e salva.
Prima di ogni invio sostituisci [Nome], [Azienda], [carrelli / macchinari / attrezzature] e [telefono].
