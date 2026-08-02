# 20 — IPv4 Addressing

> 📚 **Corso:** CompTIA Network+ (N10-009)
> 
> 📅 **Ultima modifica:** 2026-08-02

---

## **1. Introduzione all'Indirizzamento IPv4**

- **Definizione e Unicità:** Un indirizzo IP versione 4 è l'identificatore univoco che ogni dispositivo deve possedere per comunicare su una rete che utilizza il protocollo IP.
- **Formato:** Si presenta come una serie di quattro numeri separati da punti (ad esempio, 192.168.1.165).
- **Subnet Mask (Maschera di Sottorete):** È un valore a quattro ottetti (es. 255.255.255.0) utilizzato insieme all'indirizzo IP per determinare a quale sottorete appartiene il dispositivo.
- **Funzione della Subnet Mask:** Non viene trasmessa sulla rete; viene usata localmente dal dispositivo per capire quali altri indirizzi sono locali e quali si trovano all'esterno della propria sottorete.

## **2. Gateway e Indirizzi Speciali**

- **Default Gateway:** È l'indirizzo IP di un dispositivo (solitamente un router) situato sulla sottorete locale che permette la comunicazione con l'esterno. Deve necessariamente far parte della rete locale.
- **Loopback Address (Indirizzo di Loopback):** Serve a definire il dispositivo locale senza conoscerne l'IP specifico ed è utile per verificare che lo stack IP funzioni correttamente. Il range va da 127.0.0.1 a 127.255.255.255.
- **Indirizzi Riservati:** Esiste un intervallo di indirizzi (da 240.0.0.1 a 254.255.255.255), inclusi quelli di Classe E, riservati per usi futuri o test e che non dovrebbero mai essere assegnati ai dispositivi.
- **Virtual IP (VIP):** Sono indirizzi non associati a un adattatore Ethernet fisico, ma assegnati internamente a un dispositivo, come una macchina virtuale, per poterlo referenziare costantemente.

## **3. Struttura Tecnica dell'Indirizzo IPv4**

- **Livello OSI:** Il protocollo IP versione 4 opera al **Livello 3 (Network Layer)** del modello OSI.
- **Composizione in Bit:** Un indirizzo IPv4 è composto da un totale di **32 bit**, che corrispondono a 4 byte o 4 ottetti.
- **Ottetti:** Ogni ottetto è formato da 8 bit; per questo motivo, il valore decimale massimo che ogni gruppo può raggiungere è 255.

## **4. Metodi di Configurazione**

- **Configurazione Manuale:** In passato, l'indirizzo IP, la subnet mask e il gateway dovevano essere inseriti manualmente su ogni singolo dispositivo.
- **DHCP (Dynamic Host Configuration Protocol):** È il protocollo moderno che assegna automaticamente tutte le impostazioni di configurazione IP quando un dispositivo si connette a una rete cablata o wireless.
- **APIPA (Automatic Private IP Addressing):** Se non è disponibile un server DHCP, il dispositivo si auto-assegna un indirizzo "link local" tramite il processo APIPA.
- **Limitazioni APIPA:** Gli indirizzi APIPA (nel range 169.254.1.0 - 169.254.254.255) permettono di comunicare solo con altri dispositivi nella sottorete locale e non possono navigare su Internet. Il sistema usa il protocollo ARP per assicurarsi che nessun altro nella rete stia già usando quell'indirizzo.

## **5. Indirizzi Privati e NAT**

- **Scarsità di Indirizzi:** Poiché gli indirizzi IPv4 disponibili nel mondo sono terminati, sono state create strategie per estenderne la funzionalità.
- **Indirizzi IP Privati:** Sono range di indirizzi utilizzabili solo all'interno di una rete aziendale o domestica e non sono instradabili sulla rete pubblica (Internet).
- **NAT (Network Address Translation):** È la funzionalità che permette di convertire un indirizzo IP privato in un indirizzo pubblico, consentendo ai dispositivi interni di comunicare su Internet.
- **Standard RFC 1918:** È il documento che definisce i tre range di indirizzi privati:
    - **10.0.0.0 - 10.255.255.255:** Un singolo blocco di Classe A (/8) con oltre 16 milioni di indirizzi.
    - **172.16.0.0 - 172.31.255.255:** 16 blocchi contigui di Classe B (/12) con circa 1 milione di indirizzi.
    - **192.168.0.0 - 192.168.255.255:** 256 blocchi contigui di Classe C (/16) con oltre 65.000 indirizzi.
