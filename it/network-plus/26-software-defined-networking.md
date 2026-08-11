# 26 — Software Defined Networking (SDN)

> 📚 **Corso:** CompTIA Network+ (N10-009)
> 
> 📅 **Ultima modifica:** 2026-08-11

---

## Introduzione alla Virtualizzazione delle Reti

Una delle sfide principali del mondo virtuale è trasferire le funzioni dei dispositivi fisici (come router, switch e firewall) in un **ambiente virtualizzato**. Creando versioni software delle funzioni hardware, è possibile implementare queste capacità ovunque in un ambiente virtuale, offrendo una flessibilità e una funzionalità aggiuntive alla rete.

---

## I Tre Piani del Networking

Per comprendere come funziona un dispositivo di rete (fisico o virtuale), le sue capacità vengono suddivise in tre livelli o "piani" distinti:

- **Data Plane (Infrastructure Layer):** È la parte del dispositivo che svolge il "lavoro pesante" di **inoltro del traffico**. Si occupa di trasferire le informazioni da un'interfaccia all'altra e gestisce funzioni come il trunking, la crittografia e la Network Address Translation (NAT). In un firewall, questo piano corrisponde alle interfacce fisiche a cui sono connesse le reti.
- **Control Plane (Control Layer):** Questo livello determina **dove devono andare i dati**. Contiene le tabelle di routing, le tabelle di switching e tutte le logiche che controllano il funzionamento e le decisioni di inoltro del dispositivo.
- **Management Plane (Application Layer):** È lo strato utilizzato dall'amministratore di rete per **gestire il dispositivo**. Vi si accede ogni volta che si utilizza una connessione SSH, una console o un'interfaccia web per configurare l'apparato.

---

## Software Defined WAN (SD-WAN)

L'**SD-WAN** è l'applicazione dei concetti di software-defined networking alle reti geografiche (WAN), progettata specificamente per gestire le complessità degli ambienti basati sul **cloud**.

Il passaggio dal Data Center al Cloud

In passato, tutte le risorse (email, database, applicazioni) erano concentrate in un unico data center centrale, facilitando le connessioni WAN dalle sedi remote. Oggi, poiché i servizi si sono spostati nel cloud e possono trovarsi ovunque nel mondo, la connettività è diventata più complessa.

## Caratteristiche principali dell'SD-WAN:

- **Application Aware (Consapevolezza delle Applicazioni):** L'SD-WAN riconosce quale applicazione sta trasmettendo dati (ad esempio un'email o un database) e inoltra il traffico verso il servizio cloud più vicino e specifico per quell'utente.
- **Zero-touch provisioning:** Permette ai router e agli switch remoti di **aggiornarsi automaticamente** in caso di modifiche alla rete o alla posizione dei servizi, senza bisogno di intervento manuale da parte degli amministratori.
- **Agnostico rispetto al trasporto:** La tecnologia è progettata per funzionare indipendentemente dal tipo di connessione fisica utilizzata, che sia fibra ottica ad alta velocità, 5G o DSL.
- **Gestione centralizzata delle policy:** Invece di configurare ogni singolo router, l'amministratore definisce le policy su una **console centrale**; queste modifiche vengono poi inviate automaticamente a tutti i dispositivi SD-WAN della rete.

## Vantaggi Operativi

L'uso della tecnologia SD-WAN consente agli utenti nelle sedi remote di accedere direttamente ai servizi cloud (come l'email o i database) in modo ottimizzato, pur mantenendo la possibilità di collegarsi direttamente al data center centrale quando necessario.
