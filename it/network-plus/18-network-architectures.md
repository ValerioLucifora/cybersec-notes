# 18 — Network Architectures

> 📚 **Corso:** CompTIA Network+ (N10-009)
> 
> 📅 **Ultima modifica:** 2026-08-02

---

## 1. L'Architettura a Tre Livelli (Three-Tiered Architecture)

L'architettura a tre livelli è un design standard molto comune nelle reti aziendali di grandi dimensioni. Questo modello suddivide la rete in tre strati gerarchici per ottimizzare la gestione delle risorse e la connettività.

- **Livello Core (Core Layer):** Rappresenta il cuore della rete e funge da punto centrale per tutte le risorse critiche. Qui si trovano i server, le applicazioni, i database e i router principali che collegano le diverse parti dell'infrastruttura.
- **Livello di Distribuzione (Distribution Layer):** Agisce come punto intermedio tra gli utenti finali e le risorse centrali del core. Questo strato è composto da una serie di switch che garantiscono connettività e ridondanza, assicurando che ci siano percorsi multipli per raggiungere il core in caso di guasto.
- **Livello di Accesso (Access Layer):** È il punto di connessione fisica per gli utenti. Gli switch di accesso sono solitamente posizionati vicino alle postazioni di lavoro, ad esempio sullo stesso piano di un edificio, e permettono ai dispositivi degli utenti di collegarsi al livello di distribuzione.

Per comprendere meglio questa struttura, si può utilizzare l'**analogia di una città**: il **Core** è il centro città con le risorse principali; la **Distribuzione** rappresenta le autostrade che collegano la periferia al centro; l'**Accesso** sono le strade locali che collegano le singole case alle autostrade.

## 2. Architettura a Core Collassato (Two-Tier / Collapsed Core)

Nelle organizzazioni più piccole, un'architettura a tre livelli potrebbe risultare eccessiva e costosa. In questi scenari si adotta spesso un'architettura a **core collassato**.

Questo modello a due livelli **unisce il livello core e il livello di distribuzione** in un unico strato funzionale, mantenendo separato solo il livello di accesso. I principali vantaggi di questo approccio includono un design semplificato, una risoluzione dei problemi più agevole e costi inferiori grazie al minor numero di dispositivi necessari. Tuttavia, lo svantaggio principale è la **minore ridondanza**: la perdita di un singolo componente può avere un impatto maggiore sulla resilienza dell'intera rete rispetto al modello a tre livelli.

## 3. Flussi di Traffico nel Data Center

Quando si analizza il movimento dei dati all'interno di un data center, è essenziale identificare l'origine e la destinazione del traffico attraverso due definizioni principali:

- **Traffico East-West (Est-Ovest):** Si riferisce al traffico in cui sia l'origine che la destinazione si trovano all'interno dello stesso data center. Un esempio tipico è lo scambio di dati tra un file server e un image server sulla stessa rete locale. Questo tipo di traffico beneficia solitamente di tempi di risposta molto rapidi.
- **Traffico North-South (Nord-Sud):** Indica il traffico che entra nel data center da una fonte esterna o che ne esce verso l'esterno (ad esempio, verso Internet). Questo flusso richiede una gestione della sicurezza più rigorosa, poiché i dati interagiscono con reti esterne non controllate dall'organizzazione.
