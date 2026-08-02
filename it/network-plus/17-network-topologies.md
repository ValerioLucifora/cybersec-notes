# 17 — Network Topologies

> 📚 **Corso:** CompTIA Network+ (N10-009)
> 
> 📅 **Ultima modifica:** 2026-08-02

---

## Introduzione alle Topologie di Rete

Le reti possono essere connesse in molti modi diversi e la scelta della topologia è fondamentale sia durante la fase di **pianificazione e progettazione**, sia durante il **troubleshooting**. Conoscere la topologia permette di visualizzare come una rete si connette alle altre e come i dati vengono trasmessi tra i diversi nodi.

## Topologia a Stella (Star Network)

La topologia a stella, talvolta chiamata **Hub and Spoke**, è una delle configurazioni più popolari nelle grandi reti aziendali per connettere i dispositivi tra loro.

#### Funzionamento e Caratteristiche

- **Dispositivo Centrale:** Esiste un componente di rete centrale a cui tutti gli altri dispositivi si collegano direttamente.
- **Esempio Pratico:** Un esempio classico è la rete **Ethernet commutata (switched ethernet)**, dove uno switch siede al centro e tutti i dispositivi si connettono ad esso.
- **Comunicazione:** Se due nodi della rete vogliono comunicare, devono necessariamente far transitare i dati attraverso il componente centrale.

## Topologia Mesh (A Maglia)

In una rete mesh, un dispositivo o una sede si connette a un'altra attraverso **più di una connessione di rete**.

#### Vantaggi Principali

- **Ridondanza:** Se un collegamento fallisce, è possibile utilizzare un percorso alternativo per completare la comunicazione.
- **Bilanciamento del Carico (Load Balancing):** I dati possono essere suddivisi tra i diversi collegamenti disponibili per ottimizzare le prestazioni.
- **Utilizzo nelle WAN:** Sebbene applicabile alle reti locali (LAN), la topologia mesh è molto comune nelle reti geografiche (**WAN**) per garantire la connettività con i siti remoti a prescindere dai guasti sui singoli link.


## Reti Ibride

Nelle grandi reti aziendali è comune trovare diverse architetture utilizzate in diverse sezioni dell'infrastruttura. Quando si combinano insieme più topologie (ad esempio una parte a stella, una mesh e una point-to-point), si crea una **rete ibrida**.

## Architettura Spine and Leaf

Molti data center moderni utilizzano l'architettura **Spine and Leaf**.

- **Struttura:** Si compone di switch di livello superiore (Spine) e switch di livello intermedio (Leaf) a cui si collegano i dispositivi finali.
- **Regole di Connessione:** Ogni switch Spine è collegato a tutti i Leaf, e ogni Leaf è collegato a tutti gli Spine. Tuttavia, i Leaf non si collegano mai direttamente tra loro, così come gli Spine non hanno collegamenti diretti tra loro.
- **Top-of-Rack (ToR):** In questa configurazione, ogni rack fisico del data center ha uno switch Leaf posizionato in cima a cui si connettono tutti i dispositivi del rack stesso. Questo semplifica il cablaggio, garantisce ridondanza e aumenta le prestazioni poiché ogni dispositivo è a un solo "salto" di switch di distanza da qualsiasi altro nel data center.
- **Costi:** Sebbene efficiente per piccoli data center, il costo può aumentare notevolmente in strutture con centinaia o migliaia di rack, poiché è necessario uno switch dedicato per ogni rack.

## Topologia Point-to-Point (Punto a Punto)

Come suggerisce il nome, questa topologia prevede un singolo punto collegato direttamente a un altro singolo punto.

- **Reti WAN:** Era un design molto comune nelle vecchie reti WAN che utilizzavano connessioni come le linee **T1 o T3**.
- **Reti LAN:** Può essere utilizzata anche in ambito locale, ad esempio per connettere tra loro due edifici diversi all'interno di un campus universitario o aziendale.
