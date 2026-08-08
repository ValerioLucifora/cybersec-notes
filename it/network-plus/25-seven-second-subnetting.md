# 25 — Seven Second Subnetting

> 📚 **Corso:** CompTIA Network+ (N10-009)
> 
> 📅 **Ultima modifica:** 2026-08-08

---

## **Introduzione al Metodo "Seven Second Subnetting"**

Il "Seven Second Subnetting" è una tecnica di scelta rapida progettata per calcolare i parametri di una sottorete in modo estremamente veloce durante gli esami di certificazione. A differenza del metodo tradizionale che richiede la conversione manuale in binario, questo sistema si basa su una **tabella predefinita** creata all'inizio della sessione d'esame.

L'unico calcolo matematico richiesto consiste nell'aggiungere o sottrarre il valore **1** per determinare il primo e l'ultimo indirizzo IP utilizzabile. Questo metodo è efficace sia che si utilizzi una lavagna fisica in un centro d'esame, sia che si utilizzi una lavagna virtuale online.

---

## **La Creazione della Tabella di Riferimento**

Il cuore di questo processo è la costruzione di una tabella che permette di tradurre istantaneamente le notazioni CIDR in maschere decimali e viceversa.


| Masks (CIDR) | Masks (CIDR) | Masks (CIDR) | Masks (CIDR) | Masks (decimale) | Reti | Indirizzi |
| ------------ | ------------ | ------------ | ------------ | ---------------- | ---- | --------- |
| /1           | /9           | /17          | /25          | 128              | 2    | 128       |
| /2           | /10          | /18          | /26          | 192              | 4    | 64        |
| /3           | /11          | /19          | /27          | 224              | 8    | 32        |
| /4           | /12          | /20          | /28          | 240              | 16   | 16        |
| /5           | /13          | /21          | /29          | 248              | 32   | 8         |
| /6           | /14          | /22          | /30          | 252              | 64   | 4         |
| /7           | /15          | /23          | /31          | 254              | 128  | 2         |
| /8           | /16          | /24          | /32          | 255              | 256  | 1         |


---

## **Il Processo in Quattro Fasi**

Una volta pronta la tabella, il calcolo di qualsiasi sottorete segue quattro passaggi logici:

- **Fase 1: Conversione della maschera.** Converti la notazione CIDR (es. /26) nel formato decimale puntato (es. 255.255.255.192) usando la tabella.
- **Fase 2: Determinazione dell'indirizzo di rete.** Identifica l'indirizzo iniziale della sottorete a cui appartiene l'IP dato.
- **Fase 3: Determinazione dell'indirizzo di broadcast.** Trova l'ultimo indirizzo della gamma della sottorete.
- **Fase 4: Calcolo degli IP utilizzabili.** Determina il primo IP aggiungendo 1 all'indirizzo di rete e l'ultimo IP sottraendo 1 all'indirizzo di broadcast.

---

## **Regole Pratiche per gli Ottetti**

Per accelerare i calcoli, si applicano regole fisse in base al valore della maschera di sottorete in ogni ottetto:

- **Se la maschera è 255:** Trascrivi semplicemente il numero dell'indirizzo IP originale per quell'ottetto.
- **Se la maschera è 0:**
    - Per l'**indirizzo di rete**, scrivi **0**.
    - Per l'**indirizzo di broadcast**, scrivi **255**.
- **Se la maschera è un valore intermedio (es. 192, 224, 240):** Consulta la tabella dei "confini" per vedere in quale blocco cade il numero del tuo IP e usa l'inizio del blocco per la rete e la fine del blocco per il broadcast.

---

## **Esempio Pratico: Subnetting su base 8-bit (/24)**

- **IP di partenza:** 165.245.12.88/24
- **CIDR:** /24
- **Conversione Maschera:** Consultando la tabella, un /24 corrisponde a **255.255.255.0**.
- **Indirizzo di Rete:** Si applicano le regole: dove la maschera è 255 si riporta il numero dell'IP; dove è 0, si scrive 0.
    - Risultato: **165.245.12.0**.
- **Indirizzo di Broadcast:** Dove la maschera è 255 si riporta il numero dell'IP; dove è 0, si scrive 255.
    - Risultato: **165.245.12.255**.
- **IP Utilizzabili:** Si aggiunge 1 alla rete e si sottrae 1 al broadcast.
    - Primo IP: 165.245.12.1; 
    - Ultimo IP: 165.245.12.254.
