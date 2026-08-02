# 02 — Network Devices

> 📚 **Corso:** CompTIA Network+ (N10-009)
> 
> 📅 **Ultima modifica:** 2026-08-02

---

## 1. Dispositivi di Instradamento e Commutazione

**Router (Livello 3 OSI)** Il router è uno dei dispositivi più comuni e opera al **livello 3 (Network Layer)** del modello OSI. La sua funzione principale è quella di instradare i dati tra diverse subnet IP, che si trovino nello stesso data center o in parti diverse del mondo. Per determinare il "salto" (hop) successivo dell'informazione, il router utilizza gli **indirizzi IP**. Questi dispositivi collegano spesso reti di tipo diverso, come una LAN (Local Area Network) a una WAN (Wide Area Network), utilizzando interfacce in rame o in fibra ottica.

**Switch (Livello 2 OSI)** Gli switch operano al **livello 2 (Data Link Layer)** e utilizzano gli **indirizzi MAC** per inoltrare il traffico. Il loro funzionamento è basato principalmente sull'hardware tramite circuiti integrati specifici chiamati **ASIC** (Application Specific Integrated Circuit). Molti switch aziendali supportano la tecnologia **PoE (Power over Ethernet)**, che permette di trasmettere energia elettrica sugli stessi cavi della connessione ethernet.

**Switch di Livello 3** In alcuni casi, le funzionalità di routing sono integrate direttamente all'interno di uno switch. Questi vengono chiamati **switch di livello 3**, poiché combinano le capacità di commutazione del livello 2 e quelle di instradamento del livello 3 nello stesso pezzo di equipaggiamento.

## 2. Sicurezza della Rete

**Firewall** I firewall tradizionali filtrano il traffico in base al numero di porta TCP o UDP. I moderni **Next-Generation Firewall (NGFW)**, invece, sono in grado di identificare le singole applicazioni che attraversano la rete. Spesso i firewall fungono anche da router (livello 3), gestendo la comunicazione tra l'interno e l'esterno della rete, e supportano funzioni come **NAT (Network Address Translation)**, VPN per il traffico criptato e protocolli di routing dinamico.

**IDS e IPS** Questi sistemi cercano attacchi in entrata identificando minacce comuni come exploit del sistema operativo o vulnerabilità delle applicazioni (es. buffer overflow o cross-site scripting).

- **IDS (Intrusion Detection System):** Monitora il traffico e genera un allarme o un avviso se rileva un attacco.
- **IPS (Intrusion Prevention System):** Va oltre la semplice segnalazione, essendo in grado di **bloccare l'attacco** prima che entri nella rete.

## 3. Ottimizzazione e Controllo del Traffico

**Load Balancer (Bilanciatore di Carico)** Il bilanciatore di carico distribuisce il traffico tra più server fisici per garantire l'operatività di siti ad alto traffico. Se un server fallisce, il load balancer lo esclude dalla rotazione, mantenendo la disponibilità del servizio attraverso i restanti server. Può anche ottimizzare le comunicazioni tramite il **TCP offloading**, gestire la crittografia (SSL offload), eseguire il caching dei dati e dare priorità a certi tipi di traffico tramite il **QoS (Quality of Service)**.

**Proxy** Un proxy funge da intermediario tra l'utente e internet. Riceve le richieste dell'utente, le esegue per suo conto, verifica che la risposta non contenga software malevolo e infine la consegna all'utente. Può essere **esplicito** (richiede configurazione sul dispositivo) o **trasparente** (opera invisibilmente). I proxy sono utili per il caching delle risposte, il filtraggio degli URL e la scansione dei contenuti.

## 4. Archiviazione di Rete (Storage)

**NAS (Network Attached Storage)** Il NAS fornisce un accesso a **livello di file**. Ciò significa che per modificare un file, l'intero documento deve essere trasferito sulla memoria del sistema e, una volta modificato, riscritto interamente sul NAS.

**SAN (Storage Area Network)** La SAN è più efficiente per file di grandi dimensioni poiché fornisce un accesso a **livello di blocco**. Questo permette di modificare solo i blocchi specifici di dati che sono stati cambiati, senza dover copiare l'intero file. Sia NAS che SAN vengono solitamente isolati su reti ad alta larghezza di banda.

## 5. Connettività Wireless

**Access Point (AP)** Un access point permette la comunicazione wireless e funge da ponte tra la rete wireless (802.11) e la rete cablata ethernet (802.3), operando al **livello 2 (OSI)**. A differenza dei router domestici, gli AP aziendali sono dispositivi dedicati a una singola funzione.

**Wireless LAN Controller (WLC)** Nelle grandi aziende con molti AP, il WLC funge da strumento di gestione centralizzata. Permette di configurare, monitorare e aggiornare tutti gli access point da un'unica interfaccia, facilitando anche il **roaming** degli utenti tra diverse zone dell'edificio senza perdere la connessione. Generalmente, questi sistemi sono proprietari: l'access point e il controller devono essere dello stesso produttore.
