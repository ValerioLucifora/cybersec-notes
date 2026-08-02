# 06 — Introduction to IP

> 📚 **Corso:** CompTIA Network+ (N10-009)
> 
> 📅 **Ultima modifica:** 2026-08-02

---

## **Introduzione e Analogia del Trasloco**

Per comprendere il funzionamento dell'Internet Protocol (IP), è utile ricorrere a un'analogia: quella di un **camion per traslochi**. In questo scenario, le **strade** rappresentano la rete fisica (Ethernet, Wi-Fi o reti geografiche), mentre il **camion** è il protocollo IP, che si occupa del "lavoro pesante" di spostare i dati da un punto all'altro.

I dati delle applicazioni non vengono caricati sfusi sul camion, ma sono impacchettati in **scatole virtuali**, che corrispondono ai protocolli **TCP** o **UDP**. Questo processo, in cui i dati vengono inseriti in protocolli via via più grandi, è chiamato **incapsulamento**.

## **La Struttura del Frame e l'Incapsulamento**

Quando visualizziamo i dati che viaggiano su una rete Ethernet, possiamo notare una struttura a strati:

- All'inizio si trova l'**Header Ethernet**, seguito dal carico utile (**Payload**) e si conclude con un **Trailer Ethernet**.
- All'interno del payload Ethernet troviamo l'**Header IP**, che contiene a sua volta il payload IP.
- Dentro l'Header IP si trova l'**Header TCP o UDP**, che contiene infine i **dati dell'applicazione** (come i dati di un sito web HTTP).

## **Protocolli di Trasporto: TCP vs. UDP**

Sia il TCP che l'UDP operano al **Livello 4 (Trasporto)** del modello OSI e permettono il **multiplexing**, ovvero il trasferimento simultaneo di più applicazioni tra gli stessi dispositivi.

### **TCP (Transmission Control Protocol)**

- **Orientato alla connessione:** Esiste un processo formale per stabilire e chiudere la comunicazione tra i dispositivi.
- **Affidabile:** Il destinatario invia un **messaggio di conferma (acknowledgement)** per ogni pacchetto ricevuto. Se il mittente non riceve la conferma, presume che il dato sia andato perso e lo reinvia.
- **Controllo del flusso:** Il destinatario può chiedere al mittente di rallentare o velocizzare la trasmissione dei dati.

### **UDP (User Datagram Protocol)**

- **Connectionless (Senza connessione):** Non c'è un processo formale di apertura o chiusura della sessione.
- **"Non affidabile":** Viene definito così non perché funzioni male, ma perché **non prevede conferme di ricezione**.
- **Nessun recupero errori:** Se un dato viene perso, l'UDP non ha modo di saperlo o di richiederne il rinvio, e non permette il controllo del flusso.

## **Indirizzamento IP e Numeri di Porta**

Continuando l'analogia del trasloco, l'**indirizzo IP** rappresenta l'indirizzo della casa di destinazione, mentre il **numero di porta** indica la **stanza specifica** dove consegnare la scatola.

- Le porte permettono di consegnare i dati all'applicazione corretta in esecuzione sul server.
- Un **Socket** è la combinazione di un indirizzo IP, un protocollo (TCP o UDP) e un numero di porta.

## **Tipologie di Porte e Range**

I numeri di porta possono variare da **0 a 65.535**. Si suddividono generalmente in due categorie:

1. **Porte Non-Effimere (Permanenti):** Solitamente comprese tra **0 e 1.023**. Sono associate a servizi standard, come la porta 80 per il traffico web HTTP o la 443 per l'HTTPS.
2. **Porte Effimere (Temporanee):** Solitamente comprese tra **1.024 e 65.535**. Vengono utilizzate dai client per gestire sessioni temporanee.

È importante sottolineare che **cambiare un numero di porta non è un meccanismo di sicurezza**; per decidere quale traffico sia permesso o meno è sempre necessario l'utilizzo di un **firewall**. Inoltre, le porte TCP sono distinte dalle porte UDP: la porta TCP 80 è diversa dalla porta UDP 80.

## **Esempio Pratico di Comunicazione**

Immaginiamo un client (10.0.0.1) che comunica con un server (10.0.0.2). Il client può utilizzare più applicazioni contemporaneamente:

- **Web:** Il client usa una porta effimera casuale (es. 3000) per connettersi alla porta **TCP 80** del server.
- **VoIP:** Utilizza una porta sorgente (es. 7100) per connettersi alla porta **UDP 54**.
- **Email:** Utilizza una porta sorgente (es. 4407) verso la porta **TCP 143**.

Per rispondere, il server inverte semplicemente gli indirizzi IP e le porte di origine e destinazione, permettendo così il ritorno dei dati verso l'applicazione corretta sul client.
