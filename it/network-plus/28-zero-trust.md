# 28 — Zero Trust

> 📚 **Corso:** CompTIA Network+ (N10-009)
> 
> 📅 **Ultima modifica:** 2026-08-11

---

## **1. Introduzione allo Zero Trust**

Tradizionalmente, la sicurezza informatica si è concentrata sulla protezione dei **confini della rete**, controllando chi entra e chi esce. Tuttavia, una volta superato il perimetro, le reti tendevano a essere completamente accessibili, creando gravi rischi per la sicurezza.

Lo **Zero Trust** è un approccio olistico alla sicurezza che modifica radicalmente questo paradigma:

- **Nessuna fiducia predefinita:** Ogni utente, dispositivo e applicazione è considerato intrinsecamente non affidabile.
- **Verifica costante:** Ogni tipo di traffico deve essere controllato e verificato per garantire che solo gli utenti corretti accedano ai dati appropriati.
- **Tecnologie coinvolte:** L'implementazione include autenticazione, crittografia, firewall aggiuntivi e monitoraggio costante della rete.

## **2. Autenticazione e Identità Adattiva**

Il processo di accesso inizia con l'autenticazione (username, password e altri fattori), ma lo Zero Trust introduce il concetto di **identità adattiva** (Adaptive Identity) all'interno di una politica basata sul contesto.

Per determinare il livello di rischio di un tentativo di accesso, il sistema valuta diversi fattori:

- **Chi è l'utente:** Ad esempio, se si tratta di un dipendente storico o di un fornitore esterno appena assunto.
- **Posizione geografica:** Se l'utente si collega dall'area locale o da un paese straniero.
- **Dettagli tecnici:** Viene analizzato l'indirizzo IP e il tipo di connessione (es. VPN).
- **Comportamento:** Se un utente inserisce le credenziali corrette ma in un **orario insolito** o da una **posizione sospetta**, l'autenticazione può essere negata o può essere richiesto un ulteriore fattore di verifica.

## **3. Autorizzazione e Controllo degli Accessi**

Una volta che l'identità è stata verificata con successo, lo Zero Trust definisce quali permessi specifici deve avere l'utente.

- **Accesso basato sul ruolo:** Ad esempio, un addetto all'help desk può solo visualizzare un database, mentre il suo manager potrebbe avere i permessi per modificarlo.
- **Contesto del dispositivo:** Se un utente utilizza un **laptop aziendale verificato** tramite certificato, potrebbe ricevere permessi maggiori rispetto a chi usa un dispositivo non riconosciuto.
- **Principio del minimo privilegio (Least Privilege):** È una pratica fondamentale che consiste nel fornire solo i diritti necessari allo svolgimento del proprio lavoro. Non devono essere assegnati diritti amministrativi arbitrari, poiché se un dispositivo viene infettato da un **malware**, quest'ultimo otterrebbe i medesimi privilegi amministrativi dell'utente, mettendo a rischio l'intero sistema.

## **4. SASE (Secure Access Service Edge)**

Con utenti e applicazioni distribuiti ovunque (ufficio, casa, cloud pubblico o data center privati), è necessario un meccanismo di comunicazione sicuro indipendente dalla posizione fisica.

Il **SASE** rappresenta l'evoluzione della VPN e sposta le tecnologie di sicurezza direttamente nel **cloud**, vicino a dove risiedono i dati.

- **Client SASE:** Viene installato su ogni dispositivo dell'utente per garantire protezione ovunque esso si trovi.
- **Servizi offerti:** SASE combina funzionalità di rete (Network as a Service, come instradamento e QoS) con funzionalità di sicurezza (Security as a Service).
- **Componenti di sicurezza:** Include firewall come servizio (Firewall as a Service), sicurezza DNS e accesso alla rete Zero Trust (ZTNA).
- **Esperienza utente:** La connessione avviene in modo automatico e trasparente; l'utente non deve attivare o disattivare manualmente le funzioni, poiché la sicurezza è integrata nell'intero processo.
