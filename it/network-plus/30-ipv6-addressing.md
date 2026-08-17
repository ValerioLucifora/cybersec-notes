# 30 — IPv6 Addressing

> 📚 **Corso:** CompTIA Network+ (N10-009)
> 
> 📅 **Ultima modifica:** 2026-08-17

---

## **1. La necessità del passaggio a IPv6**

### **L'esaurimento degli indirizzi IPv4** 
Attualmente si stima che ci siano circa **20 miliardi di dispositivi connessi a Internet**, ma il protocollo **IPv4 può supportarne solo 4,29 miliardi**. Per ovviare a questo limite, sono stati utilizzati metodi come il **NAT (Network Address Translation)**, che permette a centinaia o migliaia di dispositivi di connettersi utilizzando un numero minimo di indirizzi IPv4 pubblici. Tuttavia, gli indirizzi IPv4 sono ormai esauriti e il NAT aggiunge complessità tecnica che alcune applicazioni preferirebbero evitare.

### **La soluzione IPv6**
IPv6 nasce per risolvere definitivamente questo vincolo. Mentre gli indirizzi IPv4 sono lunghi 32 bit, gli **indirizzi IPv6 sono di 128 bit**, offrendo uno spazio di indirizzamento enormemente più vasto. Per dare un'idea della grandezza, ogni granello di sabbia sulla Terra potrebbe avere 45 quintilioni di indirizzi IPv6 unici.

---

## **2. Struttura e Formato dell'Indirizzo IPv6**

### **Caratteristiche tecniche** 
A differenza dell'IPv4, che usa numeri decimali e punti, l'IPv6 utilizza **valori esadecimali separati da due punti (:)**. Un indirizzo completo da 128 bit è composto da **8 sezioni**, ognuna delle quali:

- È lunga **16 bit**.
- Equivale a **2 byte** (o due ottetti).

### **Indirizzo d'esempio**

fe80::5d18:652:6ffd:8f52

---

## **3. Regole di Compressione degli Indirizzi**

Poiché scrivere 128 bit in esadecimale può risultare complesso, esistono due regole fondamentali per abbreviarli:

- **Rimozione degli zeri iniziali:** All'interno di ogni gruppo, gli zeri che precedono altri numeri possono essere eliminati (ad esempio, `0001` diventa `1`).
- **Abbreviazione con doppi due punti:** Se ci sono due o più gruppi consecutivi composti interamente da zeri, possono essere sostituiti da un doppio due punti. Questa operazione può essere eseguita **una sola volta** per indirizzo per evitare ambiguità. 

- **Esempio di Compressione 1:**
    - _Indirizzo originale:_ `2600:dddd:1111:0001:0000:0000:0000:0001`.
    - _Processo:_ Vengono rimossi gli zeri iniziali (es. `0001` diventa `1`) e i tre gruppi consecutivi di zeri vengono sostituiti dal doppio due punti (`::`).
    - _Risultato finale:_ **2600:dddd:1111:1::1**.
- **Esempio di Compressione 2:**
    - _Indirizzo originale:_ `2601:04C3:4002:be00:0000:0000:0000:0066`.
    - _Processo:_ Si eliminano gli zeri iniziali e si raggruppano i tre blocchi finali di zeri.
    - _Risultato finale:_ **2601:4C3:4002:be00::66**.

---

## **4. Strategie di Migrazione e Coesistenza**

Poiché IPv4 e IPv6 non possono comunicare direttamente tra loro, sono necessarie strategie per far convivere i sistemi legacy con quelli moderni.

### **Tunneling (6to4 e 4in6)** 
Il tunneling consiste nell'incapsulare il traffico di un protocollo all'interno dell'altro (es. IPv6 dentro IPv4) per attraversare reti che non supportano il protocollo originale.

- Il metodo **6to4** crea un indirizzo IPv6 basato sull'IPv4 esistente, ma richiede router di relay specializzati e non supporta il NAT.
- Oggi il tunneling è considerato una soluzione a breve termine e non è più comune nelle reti aziendali moderne; ad esempio, il supporto a 6to4 è stato rimosso dalle versioni recenti di Windows.

### **Dual Stack** 
È il metodo di migrazione più comune. Consiste nel configurare un sistema (es. scheda di rete) affinché abbia **sia un indirizzo IPv4 che un indirizzo IPv6 assegnati contemporaneamente**. Il sistema utilizzerà tabelle di routing e impostazioni indipendenti per ciascun protocollo, permettendo alle applicazioni di scegliere quale versione utilizzare in base alla disponibilità sulla rete.

---

## **5. Traduzione: NAT64 e DNS64**

Quando un dispositivo puramente IPv6 deve comunicare con uno puramente IPv4, si utilizza la traduzione tramite **NAT64**.

- **NAT64:** Un router specializzato traduce i pacchetti tra i due protocolli in modo trasparente.
- **DNS64:** È una componente fondamentale di questo processo. Quando un client IPv6 richiede l'indirizzo di un server che supporta solo IPv4, il server DNS64 riceve la risposta IPv4 e crea una versione IPv6 sintetica di quell'indirizzo. Questo indirizzo "fittizio" reindirizza il traffico del client verso il router NAT64, che poi effettua la traduzione finale verso il server IPv4 di destinazione.
