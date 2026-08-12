# 29 — Infrastructure as Code (IaC)

> 📚 **Corso:** CompTIA Network+ (N10-009)
> 
> 📅 **Ultima modifica:** 2026-08-13

---

## **1. Cos'è l'Infrastructure as Code (IaC)**

L'**Infrastructure as Code (IaC)** è un concetto che permette di descrivere le tecnologie di rete e l'intera infrastruttura informatica utilizzando file di configurazione, ovvero sotto forma di **codice**. Invece di installare e configurare manualmente ogni singolo dispositivo, si crea un file che definisce ogni componente: server, firewall, switch, router e applicazioni.

### **Vantaggi principali:**

- **Automazione:** È possibile istruire il cloud per costruire l'intero sistema basandosi sulle specifiche del codice.
- **Duplicazione:** È estremamente semplice creare un duplicato esatto di un'intera infrastruttura in un altro data center semplicemente spostando e applicando il codice.
- **Versionamento:** Si possono creare diverse versioni dell'infrastruttura, apportare modifiche minori e ridistribuire la configurazione aggiornata.

**Esempio**:

```
all:
	hosts:
		mail.example.com:
	children:
		webservers:
			hosts:
				foo.example.com:
				bar.example.com:
		dbservers:
			hosts:
				one.example.com:
				two.example.com:
				three.example.com:
```

## **2. Automazione della Risposta: I Playbook**

Oltre alla costruzione dell'infrastruttura, è possibile automatizzare la **risposta ai problemi** attraverso i **Playbook**. Un Playbook è una serie definita di passaggi da seguire per risolvere o affrontare una questione specifica.

- **Esempi di utilizzo:** Investigare una violazione di dati o recuperare sistemi dopo un attacco ransomware.
- **Processo automatico:** Un sistema può identificare un malware, consultare il Playbook e procedere autonomamente a isolare il dispositivo, cancellare i dati, reinstallare il sistema operativo e reinserire il dispositivo nell'infrastruttura.
- **SOAR (Security Orchestration, Automation, and Response):** I Playbook sono comunemente implementati all'interno di piattaforme SOAR, console centralizzate che permettono di gestire, monitorare e automatizzare tutte le operazioni di sicurezza in un unico ambiente.

## **3. Gestione e Standardizzazione dell'Infrastruttura**

L'IaC risolve diverse problematiche legate alla gestione di grandi parchi macchine:

- **Configuration Drift (Deriva della configurazione):** Evita che si creino piccole differenze di configurazione tra diverse istanze di un'applicazione.
- **Conformità (Compliance):** Assicura che tutti i sistemi rispettino gli stessi standard, poiché sono creati dalle stesse definizioni di codice.
- **Ambienti Test e Produzione:** Permette di garantire che l'ambiente di test sia identico a quello di produzione, facilitando i passaggi tra le due fasi.
- **Aggiornamenti semplificati:** Per aggiornare un software o modificare una configurazione, basta cambiare la definizione nel file IaC e ridistribuirlo; il sistema rileverà le differenze e applicherà solo le modifiche necessarie.
- **Documentazione:** L'IaC può essere usato per scansionare un sistema esistente e tradurre la sua configurazione in un file, fornendo una documentazione accurata e riproducibile.

## **4. Controllo del Codice Sorgente (Source/Version Control)**

In ambienti complessi dove molte persone lavorano sugli stessi file di configurazione, è fondamentale utilizzare sistemi di **Source Control** (o Version Control).

- **Repository Centralizzato:** Tutti i cambiamenti sono conservati in un unico punto, evitando che i singoli amministratori apportino modifiche isolate.
- **Git:** È uno dei sistemi di controllo di versione più popolari per gestire i codici sorgente tra più utenti.
- **Gestione dei conflitti:** Se due persone modificano la stessa riga di codice, il software di controllo versione rileva il conflitto e permette a un amministratore di decidere quale modifica mantenere.
- **Branching (Ramificazione):** Questa funzione permette di creare una "branca" del codice di produzione per fare test o ottimizzazioni in un ambiente separato. Una volta verificata la validità delle modifiche, queste possono essere unite (**merge**) nuovamente nel codice principale per aggiornare l'ambiente di produzione.
