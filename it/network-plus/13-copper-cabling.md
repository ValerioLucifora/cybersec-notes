# 13 — Copper Cabling

> 📚 **Corso:** CompTIA Network+ (N10-009)
> 
> 📅 **Ultima modifica:** 2026-08-02

---

## **L'Importanza del Cablaggio nelle Reti**

Il cablaggio rappresenta la **fondamenta di ogni infrastruttura di rete**, che si tratti di router, switch o access point wireless. È fondamentale scegliere il cavo corretto fin dall'inizio, poiché una volta installato è estremamente difficile e costoso rimuoverlo o sostituirlo. Anche le reti prevalentemente wireless dipendono in ultima analisi da una connessione cablata per garantire il miglior throughput possibile.

## **Cavi in Rame a Coppia Intrecciata (Twisted Pair)**

Il cavo a coppia intrecciata è la tipologia più diffusa per le connessioni Ethernet cablate e consiste in più fili di rame intrecciati all'interno di una singola guaina.

- **Gestione del segnale:** I fili sono accoppiati per inviare lo stesso segnale in forme diverse (ad esempio, "transmit plus" e "transmit minus"), permettendo al ricevente di **riconoscere e correggere eventuali interferenze**.
- **Struttura fisica:** L'intreccio assicura che almeno uno dei fili si allontani costantemente dalla fonte di interferenza. Inoltre, diverse coppie all'interno dello stesso cavo hanno **tassi di intreccio differenti** (alcune sono più strette di altre) per migliorare le prestazioni.

## **Standard di Rete e Categorie di Cavi**

È importante comprendere che il cavo in sé non possiede una "velocità" intrinseca, ma supporta un segnale che permette l'invio di dati.

- **Standard IEEE 802.3:** Questi standard determinano la quantità di dati che possono transitare e specificano il tipo minimo di cavo richiesto per ogni tecnologia (ad esempio, il 1000Base-T richiede almeno un cavo di Categoria 5).
- **Categorie di cavi:** Per facilitare la scelta, i cavi sono classificati in categorie (come **Cat 5, Cat 6 o Cat 7**). L'uso di un cavo di categoria superiore a quella minima richiesta funzionerà correttamente.

## **Cavi Coassiali e Twinax**

Oltre alla coppia intrecciata, esistono altre tipologie di cavi in rame utilizzate in contesti specifici:

- **Cavo Coassiale:** In questo cavo, il conduttore centrale, l'isolante, la schermatura e la guaina esterna condividono lo stesso asse. Il tipo **RG6** è comune per le connessioni internet tramite modem via cavo.
- **Cavo Twinax (Twinaxial):** Presenta due conduttori interni ed è spesso associato allo standard **10 Gigabit Ethernet** tramite interfacce SFP+. Offre una comunicazione full duplex, bassi costi e una latenza inferiore rispetto alla coppia intrecciata, ma è limitato a distanze brevi, circa **5 metri**.

## **Sicurezza Antincendio: Il Plenum**

Il "plenum" è lo spazio tra il controsoffitto e il soffitto reale, utilizzato spesso per far passare cavi e infrastrutture.

- **Rischi di incendio:** Se questo spazio è utilizzato per la circolazione dell'aria (senza condotti chiusi), diventa un'area condivisa dove un incendio potrebbe propagare fumi tossici in tutto l'edificio attraverso il sistema di ventilazione.
- **Materiali dei cavi:** I cavi standard hanno spesso una guaina in **PVC** (polivinilcloruro), che produce molto fumo e gas tossici se brucia.
- **Cavi Plenum-rated:** In queste aree è obbligatorio usare cavi classificati "plenum", realizzati in **FEP** (etilene propilene fluorurato) o PVC a basso fumo. Questi cavi sono più sicuri in caso di incendio, sebbene possano essere meno flessibili e quindi più difficili da installare negli angoli stretti.

In sintesi, è essenziale verificare sempre dove verrà posato il cavo per selezionare il tipo corretto e garantire sia la performance che la sicurezza dell'edificio.
