# 31 — Static Routing

> 📚 **Corso:** CompTIA Network+ (N10-009)
> 
> 📅 **Ultima modifica:** 2026-08-18

---

## Il Ruolo del Router nel Traffico di Rete

I router utilizzati nelle case e negli uffici hanno il compito fondamentale di **inoltrare il traffico tra diverse subnet IP**. Sebbene il processo possa essere tecnologicamente complesso, si riduce a pochi passaggi essenziali:

1. **Identificazione:** Il router esamina il pacchetto in entrata per identificare l'indirizzo IP di destinazione.
2. **Consultazione:** Il router consulta le proprie **tabelle di routing** per determinare il percorso migliore.
3. **Inoltro:** Se la destinazione fa parte di una subnet connessa direttamente, il pacchetto viene inviato localmente; altrimenti, viene inviato al **"next hop"** (il salto successivo), ovvero l'indirizzo IP del router successivo nella catena.

Se un router non trova una corrispondenza per l'IP di destinazione nella sua tabella, il pacchetto viene semplicemente **scartato**.

## Il Problema delle Reti non Connesse Direttamente

In una rete con più router, ogni dispositivo conosce inizialmente solo le reti a cui è fisicamente collegato. Ad esempio, se il Router 1 è collegato a tre subnet locali, saprà come gestire il traffico per quelle specifiche reti, ma non avrà alcuna informazione sulle reti posizionate "dietro" un Router 2 o un Router 3.

Senza un intervento manuale o un protocollo dinamico, se un utente cerca di inviare dati a una subnet remota non presente nella tabella di routing, il router non saprà dove inviare il traffico e lo eliminerà.

## Definizione di Routing Statico

Il **routing statico** consiste nella creazione manuale, da parte di un amministratore di rete, delle voci all'interno della tabella di routing. Questo metodo richiede la configurazione manuale di ogni rotta su ogni router della rete. È una soluzione molto rapida per reti di piccole dimensioni e non comporta l'uso di cicli di CPU o memoria per processare protocolli dinamici.

## Vantaggi e Svantaggi del Routing Statico

L'uso del routing statico presenta caratteristiche specifiche che lo rendono adatto solo a determinati scenari:

- **Vantaggi:**
    - **Basso overhead:** Non essendoci protocolli di routing dinamico, non c'è consumo di banda per gli aggiornamenti né carico extra su CPU e RAM.
    - **Sicurezza:** Poiché non vengono scambiati aggiornamenti automatici tra router, è considerato un metodo più sicuro.
    - **Ideale per "Stub Networks":** È perfetto per sedi remote con un'unica connessione verso l'esterno.
- **Svantaggi:**
    - **Scarsa scalabilità:** Gestire manualmente centinaia o migliaia di router sarebbe estremamente oneroso in termini di tempo.
    - **Nessuna ridondanza automatica:** Se un collegamento si interrompe, il router non può ricalcolare il percorso automaticamente; l'amministratore deve intervenire manualmente.
    - **Rischio di errori umani:** Una configurazione errata può portare alla creazione di **routing loop** (anelli di instradamento).

## Esempio Pratico di Configurazione

Per permettere al Router 1 di comunicare con le reti remote, l'amministratore deve accedere al router (solitamente tramite SSH) e aggiungere le rotte statiche.

Per raggiungere la rete 10.10.20.0/24 (situata dietro il Router 2), si configura il Router 1 affinché invii tutto il traffico destinato a quel range all'indirizzo **10.10.40.2** (l'interfaccia del Router 2). Una volta ricevuto il pacchetto, il Router 2 consulterà la propria tabella, vedrà che la rete è connessa localmente e consegnerà il pacchetto alla destinazione finale. Lo stesso processo viene applicato per le reti dietro il Router 3, specificando il relativo indirizzo di "next hop".
