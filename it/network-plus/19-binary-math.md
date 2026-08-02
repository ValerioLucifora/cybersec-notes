# 19 — Binary Math

> 📚 **Corso:** CompTIA Network+ (N10-009)
> 
> 📅 **Ultima modifica:** 2026-08-02

---

## Definizione di Sistema Binario

Il sistema binario è un tipo di numerazione che utilizza solo due cifre: **0** o **1**. In informatica, ognuna di queste cifre è chiamata **bit**. Quando si raggruppano **otto bit** insieme, si ottiene un **byte**, spesso definito anche **ottetto** nel contesto delle reti.

## L'importanza del Sistema Binario

Saper convertire i numeri tra decimale e binario è una competenza fondamentale per comprendere il **subnetting IP**, che sarà un tema centrale nello studio delle reti.

---

## La Tabella di Conversione

### Come creare la tabella

Per effettuare le conversioni, è necessario creare una tabella di riferimento partendo da destra verso sinistra:

1. Si inizia scrivendo il numero **1** all'estrema destra.
2. Si raddoppia il numero precedente spostandosi verso sinistra: **2, 4, 8, 16, 32, 64, 128**.
3. Sebbene per un ottetto ci si fermi a 128, la tabella può essere estesa all'infinito (256, 512, ecc.) per calcolare numeri binari più grandi.

### Relazione con le potenze di due

I valori della tabella corrispondono alle **potenze di due**:

- 20=1
- 21=2
- 22=4
- ...e così via fino a 27=128.

---

## Conversione da Binario a Decimale

### Procedura di calcolo

Per convertire un numero binario in decimale, si allinea il numero binario sotto la tabella di conversione:

- In corrispondenza di ogni **0** binario, si riporta uno **0** nella riga del calcolo.
- In corrispondenza di ogni **1** binario, si riporta il **valore corrispondente** della tabella.
- Infine, si sommano tutti i numeri ottenuti per avere il valore decimale finale.

### Esempi pratici

- **00000010:** Solo la colonna del "2" ha un 1, quindi il risultato è **2**.
- **10000010:** Si sommano i valori delle colonne con l'1 (128 + 2), ottenendo **130**.
- **11111111:** Tutte le colonne hanno un 1. Sommando 128+64+32+16+8+4+2+1 si ottiene il valore massimo di un ottetto, ovvero **255**.

---

## Conversione da Decimale a Binario

### Il metodo del confronto

Per trasformare un numero decimale (es. **154**) in binario, si procede da sinistra a destra confrontando il numero con i valori della tabella:

1. **Confronto:** Il valore della tabella (es. 128) è minore o uguale al numero che vogliamo convertire?.
2. **Se sì:** Si scrive **1** nella colonna e si sottrae il valore della tabella dal totale (o si tiene traccia della somma accumulata).
3. **Se no:** Si scrive **0** e si passa alla colonna successiva.

Esempio: Convertire 154

- 128 è ≤ 154? Sì → **1** (rimane 26).
- 64 è ≤ 26? No → **0**.
- 32 è ≤ 26? No → **0**.
- 16 è ≤ 26? Sì → **1** (rimane 10).
- 8 è ≤ 10? Sì → **1** (rimane 2).
- 4 è ≤ 2? No → **0**.
- 2 è ≤ 2? Sì → **1** (rimane 0).
- 1 è ≤ 0? No → **0**.
- **Risultato:** 154 in decimale corrisponde a **10011010** in binario.

---

Capacità dei Bit e Risultati Possibili

Aumentando il numero di bit, aumenta esponenzialmente il numero di combinazioni e il valore decimale massimo raggiungibile:

- **2 bit:** 4 combinazioni possibili (00, 01, 10, 11), corrispondenti ai decimali 0, 1, 2 e 3.
- **3 bit:** 8 combinazioni.
- **4 bit:** 16 combinazioni.
- **8 bit (1 ottetto):** permette di rappresentare qualsiasi numero compreso tra **0 e 255**.
