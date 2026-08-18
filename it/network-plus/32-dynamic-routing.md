# 32 — Dynamic Routing

> 📚 **Corso:** CompTIA Network+ (N10-009)
> 
> 📅 **Ultima modifica:** 2026-08-18

---

## Introduzione al Routing Dinamico

Il routing dinamico è un processo automatizzato che consente ai router di scoprire le rotte e aggiornarsi a vicenda sulla base del percorso migliore disponibile. A differenza del **routing statico**, che richiede all'amministratore di rete di configurare manualmente ogni rotta su ogni dispositivo, il routing dinamico elimina la necessità di interventi manuali costanti o modifiche tramite SSH ogni volta che l'infrastruttura cambia. Quando un nuovo router viene aggiunto o rimosso, tutti gli altri dispositivi nella rete ne vengono informati automaticamente.

## Funzionamento e Requisiti di Sistema

Il processo di aggiornamento avviene dietro le quinte in tempo reale. I router monitorano il traffico nella propria sottorete locale per individuare altri router che inviano aggiornamenti di routing, spesso utilizzando messaggi **multicast**. Una volta costruita la propria tabella di routing, il router informa i vicini delle rotte che conosce.

Tuttavia, questa automazione comporta dei costi:

- **Risorse di sistema:** Il processo richiede un certo overhead in termini di **CPU e memoria** all'interno del router per gestire i calcoli e gli aggiornamenti.
- **Configurazione iniziale:** Sebbene riduca il lavoro a lungo termine, richiede una pianificazione e una configurazione iniziale del protocollo scelto che può variare in complessità.

---

## Criteri di Selezione e Tipi di Protocolli

### Criteri Decisionali

Ogni protocollo di routing utilizza criteri diversi per determinare il percorso migliore verso una destinazione remota. Alcuni dei fattori presi in considerazione includono:

- Lo **stato del link** (se il collegamento è attivo o meno).
- Il **numero di hop** (salti) necessari per raggiungere la destinazione.
- La **velocità** e il throughput della connessione.
- Il tempo di **convergenza**, ovvero la rapidità con cui la rete si aggiorna dopo un cambiamento.

## Protocolli di Routing Principali

### 1. EIGRP (Enhanced Interior Gateway Routing Protocol)

Questo protocollo è storicamente legato ad ambienti **Cisco**, sebbene sia disponibile anche su altri dispositivi.

- **Vantaggi:** È relativamente facile da configurare e converge molto rapidamente in caso di modifiche alla rete.
- **Efficienza:** È in grado di identificare ed evitare loop di rete e utilizza un traffico di rete minimo per gli aggiornamenti, preservando la larghezza di banda per altre applicazioni.

### 2. OSPF (Open Shortest Path First)

OSPF è un protocollo standard aperto ("Link State") utilizzato da molti produttori diversi, il che lo rende ideale per reti multi-vendor.

- **Sistemi Autonomi (AS):** Viene spesso implementato in reti sotto un unico controllo amministrativo, come una WAN con molti router.
- **Costo del Link:** Utilizza un concetto di "costo" assegnato a ogni collegamento, basato solitamente sulla velocità e disponibilità; il percorso con il costo più basso è considerato il migliore. Supporta inoltre il **bilanciamento del carico** tra link con costi identici.

### 3. BGP (Border Gateway Protocol)

BGP è classificato come un protocollo gateway esterno ed è il protocollo che "fa girare" **Internet**.

- **Utilizzo:** È progettato per collegare diversi Sistemi Autonomi o organizzazioni diverse tra loro.
- **Curiosità:** Viene talvolta chiamato il "protocollo dei tre tovaglioli" perché i suoi concetti fondamentali furono inizialmente abbozzati su dei tovaglioli di carta per risolvere il problema del routing dinamico su scala globale.
