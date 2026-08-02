# 07 — Common Ports

> 📚 **Corso:** CompTIA Network+ (N10-009)
> 
> 📅 **Ultima modifica:** 2026-08-02

---

## **Protocolli di Trasferimento File**

### **FTP (File Transfer Protocol)**

L'FTP è un protocollo generico per il trasferimento di file utilizzato su diversi sistemi operativi come Windows, Linux e macOS. A differenza di altre applicazioni, utilizza due porte distinte: la **porta TCP 20** per il trasferimento dei dati e la **porta TCP 21** per le informazioni di controllo. Supporta l'autenticazione tramite nome utente e password e permette di gestire i file da remoto, consentendo di rinominarli, eliminarli o elencarli nelle directory,.

### **SFTP (Secure FTP)**

L'SFTP è la versione sicura dell'FTP e permette di trasferire file assicurando che l'intera comunicazione sia criptata di default. Utilizza il protocollo **SSH (Secure Shell)** per gestire la crittografia, pertanto opera sulla **porta TCP 22**. Offre le stesse funzionalità di gestione file dell'FTP, ma con un livello di sicurezza superiore.

### **TFTP (Trivial File Transfer Protocol)**

Il TFTP viene utilizzato per trasferimenti di file molto semplici e veloci, solitamente per piccoli file di configurazione, poiché non richiede autenticazione. Funziona sulla **porta UDP 69** ed è estremamente efficiente grazie al ridotto sovraccarico di dati,. Un esempio comune di utilizzo è il download del file di configurazione per i telefoni VoIP.

---

## **Accesso Remoto e Terminale**

### **SSH (Secure Shell) e Telnet**

L'**SSH** utilizza la **porta TCP 22** per permettere la comunicazione sicura e criptata con un dispositivo remoto tramite riga di comando. Al contrario, il protocollo **Telnet**, che opera sulla **porta TCP 23**, invia tutte le informazioni in chiaro,. Poiché Telnet non dispone di crittografia, le credenziali di accesso possono essere facilmente intercettate, motivo per cui è stato ampiamente sostituito da SSH nelle reti moderne.

### **RDP (Remote Desktop Protocol)**

L'RDP consente di visualizzare e gestire il desktop di un dispositivo remoto, solitamente basato su Windows. Utilizza la **porta TCP 3389** e, sebbene sia associato a Windows, esistono client RDP per molti altri sistemi operativi come macOS, Linux, iOS e Android,.

---

## **Gestione della Posta Elettronica**

### **SMTP (Simple Mail Transfer Protocol)**

L'SMTP è il protocollo fondamentale per il trasferimento di email tra server e per l'invio di messaggi da parte dei client,. Utilizza comunemente la **porta TCP 25** per i trasferimenti non criptati (in chiaro) tra server. Per una maggiore sicurezza, molti server SMTP preferiscono la **porta TCP 587**, che integra la crittografia TLS.

---

## **Servizi di Infrastruttura di Rete**

### **DNS (Domain Name System)**

Il DNS traduce i nomi di dominio (come www.professormesser.com) in indirizzi IP. Le query standard utilizzano la **porta UDP 53**, mentre i trasferimenti di dati più corposi tra server DNS avvengono sulla **porta TCP 53**,. È una risorsa critica; senza DNS, la comunicazione con i server web sarebbe estremamente difficile.

### **DHCP (Dynamic Host Configuration Protocol)**

Il DHCP automatizza la configurazione degli indirizzi IP per i dispositivi che si connettono alla rete. Utilizza le **porte UDP 67 e 68**. I server DHCP assegnano indirizzi da un pool disponibile per un tempo limitato (lease time), e possono anche riservare indirizzi specifici basandosi sul MAC address di un dispositivo.

### **NTP (Network Time Protocol)**

L'NTP viene utilizzato per sincronizzare l'orario di tutti i dispositivi sulla rete, inclusi router, switch e server. Opera sulla **porta UDP 123**. La sincronizzazione temporale è fondamentale non solo per la precisione, ma anche per la gestione e l'analisi dei file di log provenienti da dispositivi diversi.

---

## **Gestione, Monitoraggio e Log**

### **SNMP (Simple Network Management Protocol)**

L'SNMP permette ai professionisti di rete di monitorare le prestazioni dei dispositivi. Utilizza la **porta UDP 161** per le interrogazioni (query) dei manager ai dispositivi. Esistono tre versioni: la **v1** e la **v2** inviano dati in chiaro, mentre la **v3** offre autenticazione e crittografia. Inoltre, i dispositivi possono inviare notifiche proattive (trap) al server di gestione tramite la **porta UDP 162**.

### **Syslog**

Il Syslog è il protocollo standard per consolidare i file di log di router, firewall e server in un unico database centrale, spesso un SIEM. Utilizza la **porta UDP 514** per trasferire questi dati attraverso la rete.

---

## **Accesso ai Dati e Servizi Web**

### **HTTP e HTTPS**

I browser web utilizzano il protocollo **HTTP** sulla **porta TCP 80** per comunicazioni non criptate. Per proteggere i dati, si utilizza l'**HTTPS**, che cripta la comunicazione tramite SSL o TLS sulla **porta TCP 443**.

### **LDAP (Lightweight Directory Access Protocol)**

L'LDAP viene utilizzato per interrogare e gestire database gerarchici di utenti e dispositivi in una rete,. La versione standard utilizza la **porta TCP 389**, mentre la versione sicura (**LDAPS**) utilizza la **porta TCP 636**,.

### **SMB (Server Message Block)**

L'SMB è il protocollo integrato in Windows per la condivisione di file, stampanti e per l'autenticazione di rete. Le versioni moderne comunicano direttamente su IP utilizzando la **porta TCP 445**,.

### **SQL e SIP**

- **MS SQL Server:** I database SQL di Microsoft utilizzano tipicamente la **porta TCP 1433** per la gestione delle query.
- **SIP (Session Initiation Protocol):** Utilizzato per il controllo delle chiamate VoIP e videoconferenze, opera sulle **porte TCP 5060 e 5061** per avviare, gestire e terminare le sessioni.
