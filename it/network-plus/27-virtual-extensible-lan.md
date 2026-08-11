# 27 — Virtual Extensible LAN (VXLAN)

> 📚 **Corso:** CompTIA Network+ (N10-009)
> 
> 📅 **Ultima modifica:** 2026-08-11

---

## **Introduzione: La necessità dell'Interconnessione tra Data Center**

Molte organizzazioni distribuiscono le proprie applicazioni e server su più data center sparsi nel mondo. Per gestire queste risorse in modo efficiente, è necessaria la **Data Center Interconnection (DCI)**, un sistema che permette di collegare questi diversi siti in modo fluido.

Senza una tecnologia adeguata, sorgono diverse sfide:

- **Schemi di indirizzamento IP differenti:** Ogni data center potrebbe avere una propria configurazione IP non compatibile con le altre.
- **Connettività eterogenea:** Alcuni siti possono essere collegati tramite fibra ottica ad alta velocità, altri tramite Ethernet o connessioni basate su rame.
- **Indipendenza delle applicazioni:** Le applicazioni dovrebbero poter funzionare in qualsiasi posizione senza doversi preoccupare dell'infrastruttura di rete sottostante o dello schema IP locale.

## **I Limiti delle VLAN Tradizionali**

Sebbene le VLAN (Virtual Local Area Networks) siano comunemente usate per estendere i segmenti di rete a livello 2, presentano due limitazioni principali che il VXLAN mira a superare:

1. **Scalabilità ridotta:** Le VLAN supportano solo circa **4.000** reti virtuali.
2. **Vincolo al Livello 2:** Le VLAN non sono nativamente instradabili (non-routable), il che ne limita l'uso in infrastrutture complesse che richiedono il passaggio attraverso reti di Livello 3.

## **Che cos'è il VXLAN (Virtual Extensible LAN)?**

Il VXLAN è una tecnologia progettata per supportare i moderni ambienti virtuali su larga scala e il cloud. Rispetto alle VLAN tradizionali, offre vantaggi significativi:

- **Enorme capacità:** Può supportare fino a **16 milioni** di reti virtuali.
- **Instradamento su Livello 3:** Le reti virtuali VXLAN possono essere collegate tra loro tramite una rete di Livello 3, rendendo molto semplice l'instradamento del traffico attraverso la rete internet pubblica.

## **Componenti e Funzionamento del VXLAN**

Per far comunicare macchine virtuali (VM) situate in data center diversi come se fossero sulla stessa rete locale, il VXLAN utilizza alcuni componenti chiave:

- **VXLAN Tunnel Endpoint (VTEP):** È il punto terminale del tunnel VXLAN, spesso situato nello switch "top-of-rack" o nel server di virtualizzazione. Ogni VTEP ha un proprio indirizzo IP specifico.
- **VXLAN Network Identifier (VNI):** È un identificativo che permette di associare correttamente le reti virtuali tra i diversi siti. Ad esempio, il VNI 2000 di un data center comunicherà direttamente con il VNI 2000 di un altro data center attraverso il tunnel.

## **Il Processo di Incapsulamento e il Tunneling**

Il cuore del VXLAN è la sua capacità di trasportare frame Ethernet su una rete IP esistente tramite un **tunnel**. Il processo avviene in questo modo:

1. **Frame Originale:** Si parte dal frame Ethernet standard (composto da header Ethernet, header IP e payload) generato dalla macchina virtuale.
2. **Incapsulamento:** Questo frame originale viene inserito all'interno di un **header VXLAN**. A sua volta, tutto questo viene impacchettato dentro un pacchetto **UDP**, poi in un pacchetto **IP** e infine in un nuovo **frame Ethernet** per il trasporto.
3. **Trasporto e Decapsulamento:** Il pacchetto viaggia attraverso il tunnel VXLAN. Una volta arrivato a destinazione, il VTEP ricevente rimuove gli header del tunnel (decapsulamento) e consegna il frame Ethernet originale alla macchina virtuale di destinazione.

Grazie a questo meccanismo, le macchine virtuali situate in data center fisicamente distanti possono comunicare come se fossero **direttamente collegate** tra loro.
