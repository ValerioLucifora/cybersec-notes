# 24 — Magic Number Subnetting

> 📚 **Corso:** CompTIA Network+ (N10-009)
> 
> 📅 **Ultima modifica:** 2026-08-08

---
## Introduzione al Subnetting Rapido

Il subnetting tradizionale richiede spesso la conversione degli indirizzi IP e delle maschere di sottorete (subnet mask) in formato binario, un processo che può risultare lungo e soggetto a errori. Il metodo del **Magic Number** è una scorciatoia che permette di calcolare rapidamente le informazioni fondamentali di una rete (Subnet ID, indirizzo di broadcast e intervallo host) utilizzando solo potenze di due e semplici operazioni aritmetiche, spesso eseguibili a mente.

## Gli Obiettivi del Calcolo

L'applicazione di questo metodo mira a ottenere quattro informazioni essenziali per ogni sottorete:

1. **Subnet ID (o Network Address):** Il primo indirizzo della sottorete.
2. **Broadcast Address:** L'ultimo indirizzo della sottorete.
3. **Primo host utilizzabile:** Il primo indirizzo assegnabile a un dispositivo (Subnet ID + 1).
4. **Ultimo host utilizzabile:** L'ultimo indirizzo assegnabile a un dispositivo (Broadcast - 1).

## Esempio 0: Determinare la maschera corretta per le proprie esigenze

Prima di calcolare gli indirizzi, il video mostra come scegliere la subnet mask adatta.

- **Scenario:** Hai la rete **192.168.1.0/24** e devi supportare almeno **40 dispositivi** per sottorete.
- **Ragionamento:**
    - Con **/24** (255.255.255.0) hai 1 rete da 254 host. Troppi host, poche reti.
    - Con **/25** (255.255.255.128) hai 2 reti da 126 host. Ancora troppi host.
    - Con **/26** (255.255.255.192) hai 4 reti da **62 host** (calcolato come 26−2). Questo numero è perfetto perché copre i 40 richiesti lasciando un margine.
    - Con **/27** (255.255.255.224) avresti 8 reti ma solo 30 host ciascuna, che sono insufficienti.


| Subnet Mask in Decimale | Subnet Mask in Binario              | Notazione CIDR | Reti | Host |
| ----------------------- | ----------------------------------- | -------------- | ---- | ---- |
| 255.255.255.0           | 11111111.11111111.11111111.00000000 | /24            | 1    | 254  |
| 255.255.255.128         | 11111111.11111111.11111111.10000000 | /25            | 2    | 126  |
| 255.255.255.192         | 11111111.11111111.11111111.11000000 | /26            | 4    | 62   |
| 255.255.255.224         | 11111111.11111111.11111111.11100000 | /27            | 8    | 30   |
| 255.255.255.240         | 11111111.11111111.11111111.11110000 | /28            | 16   | 14   |
| 255.255.255.248         | 11111111.11111111.11111111.11111000 | /29            | 32   | 6    |


---

## Preparazione e Strumenti Utili

Prima di iniziare i calcoli, è utile avere familiarità con alcune tabelle di riferimento che velocizzano il processo:

- **Conversione CIDR-Decimale:** Sapere a quale valore decimale corrisponde una notazione CIDR (es. /25 = 128, /26 = 192, /27 = 224).
- **Identificazione dell'Ottetto Interessante:** Sapere in quale ottetto ricade la maschera in base al CIDR:
    - Ottetto 2: da /9 a /16.
    - Ottetto 3: da /17 a /24.
    - Ottetto 4: da /25 a /30.
- **Tabella degli intervalli (Host Blocks):** Visualizzare i blocchi in base al numero di host (es. blocchi di 64: 0-63, 64-127, ecc.).

---

## I Passaggi del Metodo "Magic Number"

### 1. Identificare l'Ottetto Interessante

L'**ottetto interessante** è quello in cui il valore della subnet mask non è né 255 né 0.

- Se l'ottetto della maschera è **255**, l'ottetto corrispondente dell'IP viene copiato tal quale nel Subnet ID.
- Se l'ottetto della maschera è **0**, l'ottetto corrispondente del Subnet ID sarà sempre 0.

### 2. Calcolare il Magic Number

Il "Magic Number" si ottiene sottraendo il valore decimale dell'ottetto interessante della maschera da **256**.

$$
Formula: 256−valore ottetto interessante=Magic Number
$$

Questo numero rappresenta la dimensione del blocco di indirizzi (inclusi ID di rete e broadcast) per ogni sottorete.

### 3. Determinare il Subnet ID

Per trovare il Subnet ID nell'ottetto interessante, bisogna individuare il multiplo del Magic Number più vicino (per difetto) al valore dell'ottetto corrispondente nell'indirizzo IP.

- _**Esempio Pratico**:
	 - Indirizzo IP: 165.245.77.14
	 - Subnet Mask: 255.255.240.0
	 - Numero Magico: 256-240=16


| Mask      | 255.    | 255.    | ==240.==           | 0    |
| --------- | ------- | ------- | ------------------ | ---- |
| Azione    | copiare | copiare | ==**256-240=16**== | zero |
| IP        | 165.    | 245.    | ==**77.**==        | 14   |
| Subnet ID | 165.    | 245.    | ==**64.**==        | 0    |

| 0   | 16  | 32  | 48  | 64  | 80  | 96  | 112 | 128 | 144 | 160 | 176 | 192 | 208 | 224 | 240 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
- 77 si trova nel range tra 64 e 79, quindi si prende la cifra più piccola (si segue la regola delle cifre prese per difetto)

### 4. Calcolare l'Indirizzo di Broadcast

Una volta noto il Subnet ID dell'ottetto interessante, si calcola il broadcast con la seguente formula:

$$
Formula: Subnet ID+Magic Number−1=Broadcast
$$

Per gli altri ottetti:

- Se la maschera era 255, si copia il valore del Subnet ID.
- Se la maschera era 0, l'ottetto del broadcast sarà **255**.

- _**Esempio Pratico**:
	- Indirizzo IP: 165.245.77.14
	- Subnet Mask: 255.255.240.0
	- Subnet ID: 165.245.64.0


| Mask      | 255.    | 255.    | ==**240.**==       | 0    |
| --------- | ------- | ------- | ---------- | ---- |
| Azione    | copiare | copiare | ==**256-240=16**== | zero |
| Subnet ID | 165.    | 245.    | ==**64.**==        | 0    |
| Broadcast | 165.    | 245.    | ==**79.**==        | 255  |

- Calcolo: Subnet ID+ Numero Magico -1 = 64+16-1=**79**

---
