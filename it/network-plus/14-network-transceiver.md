# 14 — Network Transceiver

> 📚 **Corso:** CompTIA Network+ (N10-009)
> 
> 📅 **Ultima modifica:** 2026-08-02

---

## Cos'è un Ricetrasmettitore

Il termine **ricetrasmettitore** (transceiver) nasce dalla combinazione delle parole **trasmettitore e ricevitore**, poiché queste due funzioni sono solitamente unite all'interno dello stesso componente hardware. La loro funzione principale è fornire **modularità** ai dispositivi di rete, come gli switch.

Invece di avere porte con configurazione fissa, gli switch dispongono di interfacce aperte dove è possibile inserire il ricetrasmettitore più adatto al supporto (media) o al tipo di rete che si desidera utilizzare. Ad esempio, è possibile inserire un modulo in rame per il Gigabit Ethernet o un modulo in fibra per una connessione a 10 Gigabits nello stesso switch, a seconda delle necessità.

## Flessibilità e Modularità

La modularità dei ricetrasmettitori permette di decidere quale tipo di cavo sia più adatto alla propria configurazione. Se le esigenze cambiano durante l'installazione, è possibile rimuovere un modulo in rame e sostituirlo con uno in fibra senza dover cambiare l'intero switch. Sebbene questa modularità possa comportare un costo aggiuntivo, offre il grande vantaggio di potersi collegare a qualsiasi tipo di rete.

È importante ricordare che i ricetrasmettitori devono corrispondere alla tecnologia dello switch: ad esempio, uno switch Ethernet richiede ricetrasmettitori **Ethernet**, mentre uno switch Fiber Channel richiede moduli **Fiber Channel**; i due tipi non sono intercambiabili.

## Formati Comuni: SFP e SFP+

Esistono diversi formati fisici (form factors) per i ricetrasmettitori, scelti in base alla velocità e al tipo di connessione:

- **SFP (Small Form-factor Pluggable):** È un formato molto comune, generalmente associato a velocità **Gigabit Ethernet (1 Gbps)**. Può ospitare sia connessioni in fibra che connettori RJ45 per cavi in rame.
- **SFP+ (Enhanced Small Form-factor Pluggable):** Si tratta di una versione potenziata dell'SFP. Sebbene le dimensioni fisiche siano identiche a quelle di un SFP standard, l'SFP+ supporta velocità molto più elevate, fino a **16 Gbps**, ed è comunemente utilizzato per connessioni a **10 Gbps**.

## Soluzioni ad Alta Densità: QSFP e QSFP+

Nei data center, dove lo spazio nei rack è limitato (standard di 19 pollici), è fondamentale massimizzare la connettività in spazi ridotti. Per questo motivo sono stati creati i formati **Quad**:

- **QSFP (Quad Small Form-factor Pluggable):** Questo modulo combina **quattro canali** di trasmissione in un unico spazio. Se un SFP standard gestisce 1 Gbps, un QSFP può arrivare a un throughput di **4 Gbps**.
- **QSFP+ (Quad SFP+):** Seguendo la stessa logica, il QSFP+ raggruppa quattro canali SFP+ da 10 Gbps ciascuno, permettendo di raggiungere una velocità totale di **40 Gbps** su un'unica interfaccia.

## Efficienza e Dimensioni

Sebbene i moduli QSFP e QSFP+ siano leggermente più grandi rispetto ai formati SFP e SFP+ standard, non sono grandi quattro volte tanto. Questo design permette di ottenere una notevole **efficienza di spazio**, consentendo di gestire più collegamenti separati attraverso un'unica interfaccia fisica, con conseguenti benefici economici sia per l'attrezzatura che per il cablaggio utilizzato.
