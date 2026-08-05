# 22 — IPv4 Subnet Masks

> 📚 **Corso:** CompTIA Network+ (N10-009)
> 
> 📅 **Ultima modifica:** 2026-08-05

---

## Introduzione al Subnetting Classless

A partire dal 1993, il sistema di rete non utilizza più il subnetting basato sulle classi (Classe A, B o C). Al suo posto viene impiegato il **subnetting classless**, noto anche come **CIDR** (_Classless Inter-Domain Routing_), che permette una gestione più flessibile degli indirizzi IP. Questa metodologia consente di assegnare maschere di sottorete che non devono necessariamente rientrare nei rigidi schemi delle vecchie classi predefinite.

## La Notazione CIDR (Cider Block Notation)

Invece di scrivere sempre la maschera di sottorete in formato decimale (come 255.255.255.0), si utilizza spesso la **notazione CIDR**, che indica semplicemente il **numero di bit** che compongono la maschera.

- Ad esempio, una maschera decimale 255.0.0.0 corrisponde a una notazione **/8**, perché contiene otto bit individuali.
- Un indirizzo IP scritto come 192.168.1.44**/24** indica che la maschera di sottorete ha 24 bit attivi, il che equivale a 255.255.255.0.

## Configurazione dei Dispositivi

La scelta della notazione dipende spesso dal dispositivo o dal sistema operativo che si sta configurando.

- **Sistemi Operativi (es. Windows):** Solitamente richiedono l'inserimento della maschera di sottorete in formato **decimale**.
- **Router e Switch:** Frequentemente utilizzano la **notazione CIDR** (es. /8 invece di 255.0.0.0). È sempre fondamentale consultare la documentazione del dispositivo per verificare quale formato sia preferito.

## Struttura Binaria della Maschera

Una maschera di sottorete è composta da una serie **contigua di uno** (a sinistra) seguiti da una serie di **zeri** (a destra).

- **Bit a 1:** Rappresentano la parte della rete (_network_) dell'indirizzo.
- **Bit a 0:** Rappresentano la parte dell'host (_host_) dell'indirizzo.

Ad esempio, in una maschera **/24**, ci sono 24 bit impostati a "1" e 8 bit impostati a "0", il che significa che la porzione di rete è lunga 24 bit e quella host 8 bit.

## Conversione da Binario a Decimale

Poiché le maschere seguono regole precise (bit contigui), esistono solo determinati valori decimali che si possono incontrare in un ottetto. È possibile creare una tabella di riferimento per facilitare la conversione:

- 10000000 = 128
- 11000000 = 192
- 11100000 = 224
- 11110000 = 240
- 11111111 = 255.

## Esempi di Calcolo

Il video fornisce diversi esempi pratici per convertire la notazione CIDR in decimale e viceversa:

- **/12:** Composta da 8 bit nel primo ottetto e 4 nel secondo. In decimale è **255.240.0.0**.
- **/16:** Composta da 16 bit (due ottetti completi di "1"). In decimale è **255.255.0.0**.
- **/19:** Composta da 8+8+3 bit. In decimale è **255.255.224.0**.
- **/26:** Composta da 8+8+8+2 bit. In decimale è **255.255.255.192**.
- **/20:** Composta da 20 bit totali (8+8+4), che si traduce in **255.255.240.0** in formato decimale.
