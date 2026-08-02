# 09 — Network Communication

> 📚 **Corso:** CompTIA Network+ (N10-009)
> 
> 📅 **Ultima modifica:** 2026-08-02

---

## Comunicazione di Rete (Network Communication)

La comunicazione all'interno di una rete può avvenire in diverse modalità a seconda del numero di destinatari e della logica di instradamento dei dati. Le quattro tipologie principali sono Unicast, Multicast, Anycast e Broadcast.

## Unicast: Relazione Uno-a-Uno

La modalità **unicast** è uno dei metodi più comuni per l'invio di informazioni. In questo scenario, una singola stazione invia dati direttamente a un'altra stazione specifica.

- **Utilizzo:** Viene impiegata ogni volta che è necessaria una comunicazione privata tra due dispositivi, come quando si visita un sito web, si trasferiscono file o si controlla la posta elettronica.
- **Vantaggi e Svantaggi:** È molto efficiente per le sessioni individuali sia in IPv4 che in IPv6, ma diventa uno svantaggio se si devono inviare gli stessi dati a molte persone contemporaneamente, poiché richiederebbe la creazione di connessioni separate per ogni destinatario.

## Multicast: Relazione Uno-a-Molti

Il **multicast** permette di inviare informazioni a più destinatari simultaneamente. Invece di stabilire molteplici connessioni uno-a-uno, il mittente invia i dati a un indirizzo multicast e i dispositivi interessati si "iscrivono" a quel flusso per riceverli.

- **Applicazioni:** È spesso utilizzato per lo streaming multimediale, la ricezione di dati di borsa in tempo reale o per l'invio di aggiornamenti di routing tra dispositivi.
- **Caratteristiche:** È una modalità specializzata che richiede apparecchiature di rete in grado di riconoscere e gestire questo tipo di traffico. Sebbene sia molto efficiente, non viene solitamente utilizzato per comunicazioni tra reti diverse o in reti estremamente vaste.

## Anycast: Relazione Uno-verso-il-più-vicino

La comunicazione **anycast** viene utilizzata quando un dispositivo deve inviare dati a "uno tra molti" possibili destinatari. In questo caso, più dispositivi condividono lo stesso indirizzo IP e sono configurati in modo simile.

- **Funzionamento:** Quando il mittente invia i dati a quell'indirizzo IP, la rete instrada il traffico verso il dispositivo che risulta geograficamente o logicamente più vicino.
- **Esempio tipico:** Un uso comune è l'**Anycast DNS**, dove una query viene inviata al data center più vicino per garantire una risposta rapida. È supportato sia da IPv4 che da IPv6.

## Broadcast: Relazione Uno-a-Tutti

Il **broadcast** rappresenta una relazione "uno-a-tutti", in cui un singolo pacchetto viene inviato e ricevuto da ogni dispositivo presente sulla rete locale.

- **Limitazioni:** La portata del broadcast è limitata al **dominio di broadcast locale**; ciò significa che un pacchetto broadcast non può uscire dalla rete locale per diffondersi su internet.
- **Uso e Evoluzione:** Viene tipicamente usato per richieste ARP o aggiornamenti di routing in IPv4. Tuttavia, è importante notare che **in IPv6 il broadcast è stato rimosso** e sostituito da forme più efficienti di comunicazione multicast.
