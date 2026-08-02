# 01 — OSI Model

> 📚 **Corso:** CompTIA Network+ (N10-009)
> 
> 📅 **Ultima modifica:** 2026-08-02

---

## Il Modello OSI (Open Systems Interconnection)

Il modello di riferimento **Open Systems Interconnection (OSI)** è un framework utilizzato in ambito informatico per descrivere il processo che i dati seguono mentre attraversano le reti. Non si tratta di una descrizione dettagliata dei dati stessi, ma di una panoramica generale del loro percorso attraverso i sistemi. Sebbene la maggior parte dei protocolli moderni si basi sullo stack TCP/IP, il modello OSI è applicabile a molti protocolli diversi e permette ai professionisti IT di comunicare utilizzando un linguaggio comune.

## Struttura e Memorizzazione dei Livelli

Il modello OSI è composto da **sette livelli distinti**. Partendo dall'alto verso il basso, i livelli sono:

- **Livello 7:** Applicazione (Application)
- **Livello 6:** Presentazione (Presentation)
- **Livello 5:** Sessione (Session)
- **Livello 4:** Trasporto (Transport)
- **Livello 3:** Rete (Network)
- **Livello 2:** Collegamento dati (Data Link)
- **Livello 1:** Fisico (Physical)

Per facilitare la memorizzazione di questa sequenza (dall'alto verso il basso), viene spesso utilizzata la **mnemonica** inglese: _"All People Seem To Need Data Processing"_.

---

## Analisi Dettagliata dei Sette Livelli

### Livello 1: Livello Fisico (Physical Layer)

Il livello fisico descrive i **segnali fisici** inviati attraverso cavi, fibre ottiche o reti wireless. A questo livello non si parla di protocolli complessi, ma della trasmissione pura del segnale da un punto all'altro della rete. I problemi di Livello 1 riguardano solitamente cavi danneggiati, interferenze wireless o schede di rete malfunzionanti.

### Livello 2: Livello di Collegamento Dati (Data Link Layer)

Questo è il livello fondamentale per la comunicazione tra due dispositivi ed è spesso associato agli **indirizzi MAC** (Media Access Control), ovvero gli indirizzi hardware delle schede di rete. Poiché gli switch di rete decidono come inoltrare il traffico basandosi sull'indirizzo MAC di destinazione, questo livello è comunemente chiamato **"switching layer"**.

### Livello 3: Livello di Rete (Network Layer)

Conosciuto anche come **"routing layer"**, è il livello in cui operano i router per determinare il percorso migliore per i dati basandosi sull'**indirizzo IP** di destinazione. In questo livello avviene anche la frammentazione dei pacchetti in pezzi più piccoli, se necessario, per permetterne il transito attraverso diverse reti. Qualsiasi problema relativo a indirizzi IP, subnet mask o instradamento appartiene al Livello 3.

### Livello 4: Livello di Trasporto (Transport Layer)

Questo livello è responsabile del trasporto delle informazioni tra i dispositivi ed è paragonabile a un **"ufficio postale"**. I protocolli principali che operano qui sono **TCP** (Transmission Control Protocol) e **UDP** (User Datagram Protocol). Il Livello 4 gestisce l'incapsulamento dei dati in pezzi gestibili e utilizza i **numeri di porta** (come la porta 80 o 443) per dirigere il traffico.

### Livello 5: Livello di Sessione (Session Layer)

Il livello di sessione gestisce la comunicazione tra il punto A e il punto B, occupandosi di **iniziare, interrompere o riavviare le sessioni**. Viene utilizzato per il controllo dei protocolli di comunicazione e per il tunneling delle informazioni all'interno dei dati esistenti.

### Livello 6: Livello di Presentazione (Presentation Layer)

Questo livello formatta i dati in un modo che sia comprensibile per l'utente, occupandosi della codifica dei caratteri e della **crittografia/decrittografia** (come SSL o TLS). Spesso il Livello 6 opera in stretta collaborazione con il livello superiore di applicazione.

### Livello 7: Livello di Applicazione (Application Layer)

È il livello con cui l'utente interagisce direttamente attraverso lo schermo. Qualsiasi messaggio o interfaccia visibile fa parte di questo livello. Esempi comuni di protocolli di Livello 7 includono **HTTP/HTTPS, FTP, DNS e POP3**.

---

## Esempio Pratico: Analisi con Wireshark

L'utilizzo di strumenti come **Wireshark** permette di visualizzare come questi livelli operino concretamente in un singolo frame di rete. Analizzando un pacchetto di traffico verso Google Mail, si può notare la suddivisione:

- **Segnali elettrici:** Associati al Livello 1 (Fisico).
- **Frame Ethernet:** Contenente gli indirizzi MAC, associato al Livello 2 (Data Link).
- **Protocollo IP:** Con indirizzi sorgente e destinazione, associato al Livello 3 (Rete).
- **Segmento TCP:** Con i relativi numeri di porta, associato al Livello 4 (Trasporto).
- **SSL/TLS:** Che gestisce la crittografia e le sessioni, coprendo le funzioni dei Livelli 5, 6 e 7
