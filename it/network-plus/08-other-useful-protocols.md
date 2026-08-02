# 08 — Other Useful Protocols

> 📚 **Corso:** CompTIA Network+ (N10-009)
> 
> 📅 **Ultima modifica:** 2026-08-02

---

## 1. ICMP (Internet Control Message Protocol)

L'**ICMP** è un protocollo utilizzato dai professionisti di rete per verificare se un dispositivo è attivo e operativo.

- **Funzionamento:** Può essere paragonato a un messaggio di testo inviato per vedere se qualcuno risponde. Sebbene sia trasportato da IP, **non utilizza TCP o UDP**, essendo un protocollo a sé stante.
- **Utilizzo comune:** È il protocollo alla base del comando **Ping**.
- **Messaggi amministrativi:** Oltre alla verifica dell'attività, l'ICMP fornisce informazioni su problemi di rete, come quando una rete non è raggiungibile o quando il "Time to Live" (TTL) dei dati è scaduto (messaggio _time exceeded_),.

## 2. GRE (Generic Routing Encapsulation)

Il protocollo **GRE** viene utilizzato per creare un "tunnel" tra due endpoint, una pratica comune nelle VPN.

- **Incapulamento:** Permette di inserire informazioni all'interno di un pacchetto IP, inviarle attraverso il tunnel GRE e decapsularle sul lato opposto.
- **Limitazioni sulla sicurezza:** È importante notare che il protocollo GRE **non fornisce la crittografia dei dati**. Per proteggere le informazioni, è necessario utilizzare protocolli VPN aggiuntivi.

## 3. VPN e Concentratori VPN

Le **VPN (Virtual Private Networks)** utilizzano protocolli specifici per criptare e proteggere i dati inviati attraverso i tunnel.

- **Concentratore VPN:** È un dispositivo dedicato alla gestione del processo di crittografia e decrittografia in un punto centrale. Spesso questa funzione è integrata nei firewall esistenti.
- **Hardware vs Software:** I concentratori sono spesso dispositivi hardware specializzati per garantire efficienza e velocità, ma per un numero limitato di utenti possono essere implementati anche tramite software in un sistema operativo.
- **Configurazione Site-to-Site:** In questo scenario, una rete aziendale si connette a una sede remota tramite Internet utilizzando firewall o router come concentratori per criptare tutto il traffico.

## 4. IPsec (Internet Protocol Security)

L'**IPsec** è uno dei protocolli più diffusi per la crittografia dei dati nelle VPN.

- **Funzionalità:** Fornisce riservatezza tramite la **crittografia**, integrità tramite **firme digitali** per ogni pacchetto e funzionalità anti-replay.
- **Standardizzazione:** Essendo un protocollo standard, permette a dispositivi di produttori diversi (es. firewall di marche differenti) di connettersi e trasferire dati in modo sicuro.

## Il processo di scambio chiavi (IKE)

Prima di inviare dati, IPsec deve creare il tunnel attraverso l'**IKE (Internet Key Exchange)**, che permette alle due parti di concordare le chiavi di sicurezza (Security Association o SA).

- **Fase 1 (ISAKMP):** Utilizza spesso l'algoritmo Diffie-Hellman per creare una chiave segreta condivisa, operando solitamente sulla porta **UDP 500**.
- **Fase 2:** Vengono scelti i cifrari, la dimensione delle chiavi e negoziate le SA in entrata e in uscita per il tunnel.

## Modalità di trasporto e di tunnel

Esistono due modi principali per proteggere i dati con IPsec:

- **Transport Mode:** Viene inserito un header IPsec tra l'header IP originale e i dati. L'header IP originale rimane in chiaro, rendendo visibile la destinazione finale del pacchetto a chiunque lo intercetti.
- **Tunnel Mode:** È la modalità più sicura e comune. L'**intero pacchetto originale (header IP e dati) viene criptato**. Viene aggiunto un nuovo header IP che indica la destinazione del concentratore IPsec, nascondendo la destinazione finale reale.

## Protocolli AH ed ESP

All'interno di IPsec si utilizzano comunemente due protocolli:

- **Authentication Header (AH):** Fornisce integrità dei dati tramite hashing, ma invia le informazioni in chiaro (non criptate).
- **Encapsulation Security Payload (ESP):** È il protocollo preferito poiché **cripta i dati originali** e fornisce contemporaneamente l'autenticazione per garantire che i dati siano ricevuti correttamente.
