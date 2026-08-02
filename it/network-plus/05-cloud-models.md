# 05 — Cloud Models

> 📚 **Corso:** CompTIA Network+ (N10-009)
> 
> 📅 **Ultima modifica:** 2026-08-02

---

## **Modelli di Cloud Computing**

### **Introduzione alle modalità di distribuzione**

Quando si distribuisce un'applicazione basata su cloud, è fondamentale considerare chi dovrà accedervi e da dove.

- **Cloud Pubblico (Public Cloud):** Ideale se l'applicazione deve essere accessibile a chiunque su Internet.
- **Cloud Privato (Private Cloud):** Utilizzato per applicazioni ad uso esclusivamente interno, spesso ospitate in un data center locale virtualizzato di proprietà dell'organizzazione.
- **Cloud Ibrido (Hybrid Cloud):** Una configurazione che combina l'utilizzo di cloud pubblici e privati per gestire diverse esigenze applicative.

---

## **Software as a Service (SaaS)**

Il modello **Software as a Service** è comunemente associato al software "on-demand".

- **Gestione:** L'applicazione è scritta e gestita interamente da terze parti. L'utente non deve installare software localmente, né occuparsi di aggiornamenti o manutenzione.
- **Accesso:** L'utente accede semplicemente tramite un browser, inserendo le proprie credenziali.
- **Dati:** I dati sono memorizzati su una piattaforma cloud di terze parti, consentendo una gestione centralizzata.
- **Esempi:** Servizi come Google Mail o Office 365 sono esempi tipici di SaaS, dove l'utente si limita a utilizzare l'applicazione pronta all'uso.

---

## **Infrastructure as a Service (IaaS)**

Conosciuto anche come **Hardware as a Service (HaaS)**, questo modello fornisce le risorse di calcolo necessarie per eseguire le proprie applicazioni.

- **Responsabilità dell'utente:** In questo modello, l'utente è responsabile dell'installazione del software, della gestione dei dati e di tutti gli aggiornamenti necessari.
- **Controllo:** Sebbene l'applicazione e i dati risiedano nel cloud, l'utente ha un controllo molto maggiore sull'accesso e sulla sicurezza rispetto ad altri modelli.
- **Esempio:** Un esempio comune è rappresentato dai fornitori di servizi web, dove è possibile acquistare tempo di utilizzo su un server specifico che viene reso disponibile su Internet.

---

## **Platform as a Service (PaaS)**

Il modello **Platform as a Service** rappresenta una via di mezzo tra SaaS e IaaS.

- **Sviluppo:** Il provider fornisce tutti gli strumenti e i "mattoni" (building blocks) necessari per costruire un'applicazione personalizzata.
- **Divisione dei compiti:** Il provider PaaS è responsabile del motore sottostante che fa girare l'applicazione, mentre l'utente è responsabile dello sviluppo, della personalizzazione e della manutenzione delle app create.
- **Esempio:** Salesforce.com è un esempio di PaaS, in quanto offre gli strumenti per creare applicazioni personalizzate che girano sulla loro piattaforma.

---

## **La Matrice di Responsabilità nel Cloud**

La scelta del modello dipende dal livello di responsabilità che un'organizzazione è disposta ad assumersi.

- **Soluzione On-Premise (Locale):** Il cliente è responsabile di tutto, dai dati alle applicazioni, fino al data center fisico.
- **IaaS:** Il provider gestisce il data center fisico, la rete e l'host fisico; il cliente gestisce tutto il resto.
- **PaaS:** Alcuni elementi come i controlli di rete e le applicazioni possono essere condivisi tra cliente e provider, ma il cliente resta responsabile di account, dispositivi e dati.
- **SaaS:** Il provider si assume la maggior parte delle responsabilità, inclusa l'intera gestione delle applicazioni. Il cliente rimane responsabile solo degli strati superiori, come i dati e gli account.
