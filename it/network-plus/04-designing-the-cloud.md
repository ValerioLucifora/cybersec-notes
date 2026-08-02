# 04 — Designing the Cloud

> 📚 **Corso:** CompTIA Network+ (N10-009)
> 
> 📅 **Ultima modifica:** 2026-08-02

---

## Le Reti Virtuali nel Cloud Computing

L'evoluzione verso il cloud non riguarda solo i server, ma l'intera infrastruttura di rete. Quando si migrano i server fisici in un ambiente cloud, è necessario virtualizzare anche i componenti che li collegano.

## 1. Network Function Virtualization (NFV)

La **Network Function Virtualization (NFV)** è il processo di sostituzione dei dispositivi di rete fisici (come router, switch e firewall) con le loro versioni virtuali.

- **Funzionalità invariata:** Sebbene questi dispositivi non siano più fisici, mantengono le stesse identiche capacità. È possibile gestire interfacce e configurazioni direttamente tramite l'**hypervisor**.
- **Flessibilità e Rapidità:** Proprio come si può attivare un server con un clic, è possibile distribuire istantaneamente un nuovo firewall virtuale o modificare la configurazione di un router all'interno del mondo virtualizzato.

## 2. Virtual Private Cloud (VPC)

Un'istanza comune nel cloud è la **Virtual Private Cloud (VPC)**. Si tratta di un ambiente isolato dove girano applicazioni specifiche (ad esempio, un server web e un database insieme a bilanciatori di carico e switch virtuali).

- **Isolamento:** Le aziende utilizzano VPC separate per diverse applicazioni o dipartimenti per mantenere i sistemi distinti pur gestendoli come singole appliance virtuali.

## 3. Connettività e Instradamento

Per far comunicare queste entità virtuali tra loro o con il mondo esterno, si utilizzano diversi strumenti:

- **Transit Gateway:** Funziona come un "router cloud". Permette la comunicazione tra diverse VPC che altrimenti rimarrebbero isolate.
- **Internet Gateway:** Consente l'accesso alle applicazioni da qualsiasi parte del mondo tramite Internet.
- **VPC NAT Gateway:** Permette ai dispositivi nelle reti private di uscire su Internet (ad esempio per aggiornamenti), ma impedisce ai dispositivi esterni di avviare connessioni verso l'interno.
- **VPN (Virtual Private Network):** Fornisce un accesso sicuro a una VPC da un sito remoto o dalla postazione di un utente, creando un tunnel crittografato.
- **VPC Endpoint:** Crea una connessione diretta tra VPC di diversi fornitori cloud o tra una VPC e servizi di archiviazione (cloud storage), senza passare per l'internet pubblico.

## 4. Sicurezza della Rete Virtuale

La sicurezza nel cloud viene gestita attraverso regole basate su protocolli e porte (TCP/UDP) o indirizzi IP (Layer 3).

- **Network Security Lists:** Sono firewall applicati a intere sottoreti. Sono ampi, ma possono mancare di precisione poiché applicano le stesse regole a tutte le reti virtuali assegnate.
- **Network Security Groups (NSG):** Offrono una maggiore **granularità**. Permettono di assegnare regole di sicurezza a singole schede di rete virtuali (**vNIC**), consentendo regole diverse per interfacce diverse all'interno della stessa sottorete.
- **Virtual Firewalls:** Per una sicurezza ancora più avanzata rispetto ai gruppi di sicurezza standard, è possibile implementare piattaforme di firewall virtualizzati dedicate.
