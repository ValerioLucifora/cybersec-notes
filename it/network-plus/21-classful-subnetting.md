# 21 — Classful Subnetting

> 📚 **Corso:** CompTIA Network+ (N10-009)
> 
> 📅 **Ultima modifica:** 2026-08-03

---

## Il Subnetting basato su classi (Classful Subnetting)

Il subnetting basato sulle classi è un metodo per descrivere un indirizzo IP in relazione alla sua **subnet mask predefinita**. Sebbene questo sistema non venga più utilizzato ufficialmente dal 1993, rimane un concetto fondamentale perché funge da **punto di partenza** per comprendere come suddividere le reti oggi.

## Classi di Indirizzi e Subnet Mask

Il sistema suddivide gli indirizzi in diverse classi principali (A, B e C), ognuna con una demarcazione netta tra la parte dell'indirizzo dedicata alla rete e quella dedicata agli host.

- **Classe A:** Gli indirizzi che iniziano con un primo ottetto compreso tra **0 e 127**. La subnet mask predefinita è **255.0.0.0**, il che significa che i primi 8 bit sono per la rete e i restanti 24 per gli host.
- **Classe B:** Indirizzi con il primo ottetto tra **128 e 191**. La subnet mask predefinita è **255.255.0.0** (16 bit di rete, 16 bit di host).
- **Classe C:** Indirizzi con il primo ottetto tra **192 e 223**. La subnet mask predefinita è **255.255.255.0** (24 bit di rete, 8 bit di host).
- **Classe D:** Indirizzi tra **224 e 239**, utilizzati esclusivamente per la comunicazione **multicast** e non assegnati a singoli dispositivi.
- **Classe E:** Indirizzi tra **240 e 255**, considerati una gamma **riservata** per scopi futuri o sperimentali.

## Identificazione tramite Bit Binari

È possibile determinare la classe di un indirizzo osservando i bit iniziali del primo ottetto:

- **Classe A:** Il primo bit è sempre **0**.
- **Classe B:** I primi due bit sono **10**.
- **Classe C:** I primi tre bit sono **110**.
- **Classe D:** I primi quattro bit sono **1110**.
- **Classe E:** I primi quattro bit sono **1111**.

## I Quattro Valori Fondamentali di una Sottorete

Quando si calcola una sottorete IP, è essenziale identificare quattro valori chiave:

1. **Indirizzo di Rete (Network Address):** Definisce la sottorete stessa. Si calcola impostando a **zero** tutti i bit della parte host.
2. **Primo Indirizzo Host Utilizzabile:** È sempre il valore numerico immediatamente **successivo** all'indirizzo di rete.
3. **Indirizzo di Broadcast della Rete:** È l'ultimo indirizzo della sottorete, usato per inviare dati a tutti i dispositivi contemporaneamente. Si calcola impostando a **uno** (255 in decimale) tutti i bit della parte host.
4. **Ultimo Indirizzo Host Utilizzabile:** È il valore numerico immediatamente **precedente** all'indirizzo di broadcast.

## Esempi Pratici di Calcolo

### Esempio Classe A (Indirizzo 10.74.22.11)

Poiché inizia con 10, è una Classe A con mask 255.0.0.0.

- **Indirizzo di Rete:** 10.0.0.0.
- **Primo Host:** 10.0.0.1.
- **Broadcast:** 10.255.255.255.
- **Ultimo Host:** 10.255.255.254.

### Esempio Classe B (Indirizzo 172.16.18.200)

Inizia con 172, quindi è Classe B con mask 255.255.0.0.

- **Indirizzo di Rete:** 172.16.0.0.
- **Primo Host:** 172.16.0.1.
- **Broadcast:** 172.16.255.255.
- **Ultimo Host:** 172.16.255.254.

### Esempio Classe C (Indirizzo 192.168.4.77)

Inizia con 192, quindi è Classe C con mask 255.255.255.0.

- **Indirizzo di Rete:** 192.168.4.0.
- **Primo Host:** 192.168.4.1.
- **Broadcast:** 192.168.4.255.
- **Ultimo Host:** 192.168.4.254.
