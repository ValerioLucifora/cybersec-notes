# 24 — Magic Number Subnetting

> 📚 **Corso:** CompTIA Network+ (N10-009)
> 
> 📅 **Ultima modifica:** 2026-08-06

---

## Introduzione al Subnetting Rapido

Il subnetting tradizionale richiede spesso la conversione degli indirizzi IP e delle maschere di sottorete (subnet mask) in formato binario, un processo che può risultare lungo e soggetto a errori. Il metodo del **Magic Number** è una scorciatoia che permette di calcolare rapidamente le informazioni fondamentali di una rete (Subnet ID, indirizzo di broadcast e intervallo host) utilizzando solo potenze di due e semplici operazioni aritmetiche, spesso eseguibili a mente.

## Gli Obiettivi del Calcolo

L'applicazione di questo metodo mira a ottenere quattro informazioni essenziali per ogni sottorete:

1. **Subnet ID (o Network Address):** Il primo indirizzo della sottorete.
2. **Broadcast Address:** L'ultimo indirizzo della sottorete.
3. **Primo host utilizzabile:** Il primo indirizzo assegnabile a un dispositivo (Subnet ID + 1).
4. **Ultimo host utilizzabile:** L'ultimo indirizzo assegnabile a un dispositivo (Broadcast - 1).

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

**Formula:** 256−valore ottetto interessante=Magic Number

Questo numero rappresenta la dimensione del blocco di indirizzi (inclusi ID di rete e broadcast) per ogni sottorete.

### 3. Determinare il Subnet ID

Per trovare il Subnet ID nell'ottetto interessante, bisogna individuare il multiplo del Magic Number più vicino (per difetto) al valore dell'ottetto corrispondente nell'indirizzo IP.

- _Esempio:_ Se l'IP nell'ottetto interessante è 77 e il Magic Number è 16, i blocchi sono 0, 16, 32, 48, 64, 80. Il 77 cade nel blocco che inizia con **64**.

### 4. Calcolare l'Indirizzo di Broadcast

Una volta noto il Subnet ID dell'ottetto interessante, si calcola il broadcast con la seguente formula:

**Formula:** Subnet ID+Magic Number−1=Broadcast

Per gli altri ottetti:

- Se la maschera era 255, si copia il valore del Subnet ID.
- Se la maschera era 0, l'ottetto del broadcast sarà **255**.

---

## Esempio Pratico Riassuntivo

Consideriamo l'IP **10.180.122.244** con maschera **255.248.0.0**:

1. **Ottetto Interessante:** Il secondo (valore 248).
2. **Magic Number:** 256−248=8.
3. **Subnet ID:** L'IP nell'ottetto interessante è 180. I multipli di 8 vicini a 180 includono 176 (8x22). Il Subnet ID è quindi **10.176.0.0**.
4. **Broadcast:** 176(Subnet ID)+8(Magic Number)−1=183. Il broadcast finale è **10.183.255.255**.
5. **Host:** Il primo host è **10.176.0.1** e l'ultimo è **10.183.255.254**.
