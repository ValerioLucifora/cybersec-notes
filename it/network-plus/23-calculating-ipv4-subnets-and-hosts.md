# 23 — Calculating IPv4 Subnets and Hosts

> 📚 **Corso:** CompTIA Network+ (N10-009)
> 
> 📅 **Ultima modifica:** 2026-08-05

---

## Introduzione al Subnetting

Il processo di creazione di reti più piccole è fondamentale perché sarebbe tecnicamente impossibile per un singolo dispositivo conoscere la posizione di ogni altro dispositivo nel mondo. Attraverso il subnetting, creiamo reti di dimensioni ridotte collegate da router, che permettono di inoltrare i pacchetti verso la destinazione finale senza che il mittente conosca l'esatta posizione del destinatario.

## Variable Length Subnet Masks (VLSM)

A differenza delle reti basate sulle classi (classful), che hanno un numero fisso di bit nella maschera di sottorete, il sistema **VLSM** permette di definire maschere di lunghezza variabile.

- **Flessibilità:** Gli amministratori di rete possono creare reti della dimensione esatta necessaria, decidendo quanti bit dedicare alla subnet e quanti agli host.
- **Analogia della pizza:** Dividere una rete con VLSM è come decidere in quante fette tagliare una pizza: si può scegliere di dividerla in due, quattro, otto o più parti a seconda delle necessità.

## Il concetto di "Prestito" dei Bit

Per creare delle subnet, si "prendono in prestito" dei bit che originariamente appartenevano alla sezione degli host dell'indirizzo IP.

- **Esempio Classe A:** Un indirizzo di Classe A (come 10.0.0.0) ha un prefisso predefinito di **/8** (255.0.0.0).
- Se spostiamo la linea di demarcazione (ad esempio a **/24**), stiamo prendendo in prestito 16 bit dalla sezione host per trasformarli in bit di subnet.
- Ciò riduce lo spazio disponibile per gli host, ma aumenta drasticamente il numero di reti indipendenti che possiamo creare.

## Formule per il Calcolo Rapido

Invece di convertire costantemente tra binario e decimale, è più efficiente utilizzare le **potenze di due**:

1. **Numero di Subnet:** 2n (dove _n_ è il numero di bit presi in prestito per la subnet).
2. **Numero di Host per Subnet:** (2h)−2 (dove _h_ è il numero di bit rimanenti per gli host).
    - _Nota:_ Si sottrae 2 perché ogni sottorete deve riservare un indirizzo per l'**indirizzo di rete** e uno per l'**indirizzo di broadcast**.

## Esempi Pratici di Calcolo

### 1. Indirizzo 10.1.1.0/24 (Classe A modificata)

- **Default Classe A:** /8 (8 bit di rete).
- **Bit presi in prestito (Subnet):** 16 (poiché 24 - 8 = 16).
- **Bit Host rimanenti:** 8 (poiché 32 - 24 = 8).
- **Calcolo:**
    - Subnet: 216=65.536.
    - Host: (28)−2=254.

### 2. Indirizzo 192.168.1.0/26 (Classe C modificata)

- **Default Classe C:** /24 (24 bit di rete).
- **Bit presi in prestito (Subnet):** 2 (26 - 24 = 2).
- **Bit Host rimanenti:** 6 (32 - 26 = 6).
- **Calcolo:**
    - Subnet: 22=4.
    - Host: (26)−2=62.

### 3. Indirizzo 172.16.5.0/21 (Classe B modificata)

- **Default Classe B:** /16 (16 bit di rete).
- **Bit presi in prestito (Subnet):** 5 (21 - 16 = 5).
- **Bit Host rimanenti:** 11 (32 - 21 = 11).
- **Calcolo:**
    - Subnet: 25=32.
    - Host: (211)−2=2.046.

L'utilizzo delle potenze di due è un metodo rapido, ma esistono ulteriori scorciatoie per velocizzare ulteriormente questi calcoli nel lavoro quotidiano.
