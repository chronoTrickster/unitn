[TOC]
## Macchine astratte ##

**Macchina astratta M~L~**: insieme di algoritmi e strutture dati che permettono di memorizzare ed eseguire programmi. 
Ad ogni macchina astratta è associato un (solo) linguaggio **L**. 
Per eseguire un programma in **L**, **M~L~** deve:

- eseguire operazioni;
- controllare il flusso di esecuzione;
- trasferire dati;
- gestire la memoria.

**Implementazione software:** implementando in software **M~L~** il software viene eseguito su una Macchina Ospite **Mo~Lo~** (con un linguaggio macchina **Lo**). Esistono 2 tipologie:

**Implementazione puramente interpretativa:** avviene grazie ad un programma (interprete) scritto in **Lo** che capisce ed esegue programmi scritti in **L** (traduzione istruzione per istruzione). 

**Implementazione puramente compilativa:** un compilatore traduce l’intero programma da **L** a **Lo** prima dell’esecuzione. 

**Implementazione ibrida:** il compilatore traduce in un linguaggio intermedio **Li**, l’interprete esegue il programma scritto in **Li**.

**Compilari vs Interpreti:** interpretativa: poco efficiente, ma flessibile, portatile e con debugging semplificato. Compilativa: efficiente, complessa, debugging complesso. 

**In pratica:** compilativi: c, c++, fortran, pascal, ada. Interpretativi: lisp, ml, perl, postscript, pascal, prolog, java, smalltalk.

**Definizioni:** programma come funzione:

- **P^L^:D&rarr;D**
  	 **P^L^**: programma scritto in **L**;
  	 **D**: insieme di input e output;
- **P^L^(i) = o**
   	 **i** ∈ **D**: input, **o** ∈ **D**: output.

Interpeti e compilatori sono anche loro programmi.

**Definizione di interprete**: interprete per linguaggio **L** scritto in **Lo**

![Definizione di interprete](https://github.com/FakeKanaan/unitn/blob/master/docs/Linguaggi%20di%20programmazione%20-%20modulo%202/media/1.png)

**Definizione di compilatore:**

![Definizione di compilatore](https://github.com/FakeKanaan/unitn/blob/master/docs/Linguaggi%20di%20programmazione%20-%20modulo%202/media/2.png)



---

## Capitolo 6 - I nomi e l'ambiente 

**Nomi:** sequenza di caratteri usata per denotare qualcos’altro, spesso identificatori (x, pi, f).

**Oggetti denotabili:** quando puo essergli associato (binding) un nome, nomi definiti dall’utenteo dal linguaggio.

**Ambiente:** insieme delle associazioni tra nomi e oggetti denotabili.

- Dichiarazione: meccanismo col quale si crea un’associazione in ambiente.
- Aliasing: nomi diversi denotano lo stesso oggetto.
- Lo stesso nome può denotare oggetti distini.

**Blocchi**: regione testuale del programma, identificato da un inizio ed una fine {}, può contenere dichiarazioni locali a quella regione. Associato ad una procedura.

**Suddividiamo l’ambiente:**

- ambiente locale: associazione create all’ingresso nel blocco;                 
- ambiente non locale: associazioni ereditate da altri blocchi;                 
- ambiente globale: ambiente non locale le quali associazioni sono comuni a tutti i blocchi.

**Operazioni sull'ambiente:** 

- creazione (naming): associazione nome-oggetto;
- riferimento (referencing): oggettto denotato mediante il suo nome;
- disattivazione: associazione nome-oggetto (entrata in blocco con dichiarazione che maschera)(riattivazione);
- distruzione (unnaming): associazione nome-oggetto, uscita da blocco con dichiarazione locale.

**Regole di scope:** una dichiarazione locale ad un blocco è visibile in quel blocco e in tutti i blocchi in esso annidati, a meno di mascheramento (dichiaramento con lo stesso nome).

**Scope statico:** un nome non locale è risolto nel blocco che testualmente lo racchiude.

**Scope dinamico:** un nome non locale è risolto nel blocco attivato più di recente e non ancora disattivato.

---

## Capitolo 7 - La gestione della memoria

**Tipi di allocazine della memoria:**

- statica: memoria allocata a tempo di compilazione;
- dinamica: memoria allocata a tempo d'esecuzione (pila, heap).

**Allocazione statica:** l'oggetto ha un indirizzo assoluto mantenuto tutta l'esecuzione del programma. *L'allocazione statica non permette ricorsione.*

**Allocazione dinamica: pila**

- Per ogni istanza di un sottoprogramma a run-time abbiamo un record di attivazione (RdA o frame) contenente le informazioni relative a tale istanza.
- Ogni blocco ha un suo RdA.
- La pila gestiche i RdA.

![Allocazione dinamica: pila](https://github.com/FakeKanaan/unitn/blob/master/docs/Linguaggi%20di%20programmazione%20-%20modulo%202/media/3.png)

**Allocazione dinamica: heap**

*Heap:* regione di memoria i cui blocchi possono essere allocati e dealloacati in momenti arbitrari.
Necessario utilizzarlo quando il linguaggio permette:

- allocazione esplicita di memoria a run-time;
- oggetti di dimensioni variabili;
- oggetti con vita non LIFO.

I vantaggi sono: gestione efficiente dello spazio (frammentazione) e velocità di accesso

**Heap con blocchi di dimensione fissa**:

Suddiviso in blocchi di dimensione fissa.

1. In origine tutti i blocchi sono collegati nella lista libera; 
2. vengono allocati uno o più blocchi contigui;
3. alla deallacoazione il blocco viene restituito alla lista libera.

**Heap con blocchi di dimensione fissa**:

1. In origine un unico blocco nell'heap;
2. all'allocazione viene determinato un blocco libero dalla dimensione opportuna;
3. alla deallocazione viene restituito il blocco alla lista libera.

Bisogna evitare lo spreco di memoria (frammentazione).

**Frammentazione:**

- Frammentazione *interna*: lo spazio richiesto è X, vienne allocato un blocco Y (>X), Y-X spazio è sprecato.
- Frammentazione *esterna*: è presente lo spazio ma è frammentato in blocchi separati "piccoli"

**Lista libera (LL)**:

1. Inizialmente un solo blocco, della dimensione dell'heap;
2. ad ogni richiesta di allocazione *cerca* il blocco di dimensione opportuna:
   - first bit: primo blocco grande abbastanza;
   - best fit: quello di dimensione più piccola, grande abbastanza;
3. se il blocco è molto grande viene diviso e la parte inutilizzata è aggiunta alla LL;
4. alla deallocazione il blocco viene restituito alla LL.

**Gestione dell'heap:** per migliolare il costo dell'allocazione si usano liste libere multipli; la ripartizione dei blocchi fra le varie liste può essere:

- statica;
- dinamica: buddy system, fibonacci system.

**Implementazione delle regole di scope**:

| scope statico  | scope dinamico                       |
| -------------- | ------------------------------------ |
| catena statica | A-list                               |
| display        | tabella centrale dell'ambiente (CRT) |

**Il display e come si determina**:

???

**Scope dinamico:**con scope dinamico l'associazione nomi-oggetti dipende:

- dal flusso del controllo run-time;
- dall'ordine con cui i sottoprogrammi sono chiamati.

La *regola*: l'associazione per un nome è quella determinata per ultima nell'esecuzione.

Implementazione tramite A-list o CRT, relativi vantaggi e svantaggi.

---

## Capitolo 8 - Strutturare il controllo ##



**Controllo del flusso:**

- Espressioni
  - Notazioni
  - Valutazione
  - Problemi
- Comandi
  - Assegnamento
  - Sequenziale
  - Condizionale
- Comandi iterativi
- Ricorsione

**Variabile**: un contenitore di valori (modificabili-ish) che ha un nome.

**Assegnamento:** comando che modifica il valore di una variabile.

**Modelli di variabile:** 

- Linguaggi funzionali (Lisp, ML, Haskell, Smalltalk): una variabile denota un valore e non è modificabile.
- Linguaggi logici: una variabile è modificabile entro certi limiti (istanziazione).
- Clu, modello a oggetti/riferimento:  una variabile è un riferimento ad un valore, con un nome.
- Java: variabile modificabile (int, bool, etc); modello a riferimento per le classi.

~~**Operatori di assegnamento**~~

**Ambiente e memoria:** 

- Nei linguaggi *imperativi* sono presenti 3 domini semantici:

  - valori denotabili;
  - valori memorizzabili;
  - valori esprimibili.

  La semantica:

  - ambiente: nomi &rarr; valori denotabili;
  - memoria: locazioni &rarr; valori memorizzabili;
  - permette l'aliasing.

- I linguaggi *funzionali* usano solo l'ambiente.

**Iterazione:** insieme alla ricorsione è uno dei meccanismi che permette il calcolo Turing completo.

- *indeterminata* (`while`, `while do`,`repeat`, ...): cicli controllati logicamente;
- *determinata* (`do`, `for`, ...): cicli controllati numericamente, con numero di ripetizioni del ciclo determinate dall'inizio del ciclo;
- controllata numericamente (?).

**Ricorsione:** una funzione è ricorsiva se definita in termini di se stessa.

**Ricorsione in coda**.

---

## Capitolo 9 - Astrazione sul controllo: sottoprogrammi ed eccezioni

**Astrazione (uhm):** 

- identificare le proprietà importanti di cosa si vuole descrivere;
- concentrarsi sulle questioni rilevanti

**Parametri:**

- Dichiarazione:

  `int f(int `**n**`){return n+1;}` *parametro formale*

- Chiamate/uso:

  `x = f(`**y**`)` *parametro attuale*

**Modalità di passaggio dei parametri:**

- per *valore*: il valore dell'attuale è assegnato al formale, che si comporta come una variabile locale, modifiche al formale non passano all'attuale;
- per *riferimento* (per variabile): viene passato un riferimento (indirizzo) all'attuale, modifiche al formale passano all'attuale.

---

## Capitolo 10 - Strutturare i dati

**Tipo di dato:** una collezione di valori (omogenei) dotata di un insieme di operazioni per manipolare tali valori.

**A cosa servono:** 

- a livello di progetto: organizzazo l'informazione;
- a livello di programma: identificano e prevengono errori;
- a livello di implementazione: permettono ottimizzazioni.

**Array:** una collezione di dati omogenei che svolge da funzione da un tipo indice (discreto) al tipo degli elementi (un tipo).
Esistono gli *array multidimensionali*: funzione da tipo indice a tipo array.

**Memorizzazione degli array:** gli elementi sono memorizzati in locazioni contigue:

- ordine di riga: `V[1,1]; V[1,2]; V[1,3]; ...; V[1,10]; V[2,1]; ...`
- ordine di colonne: `V[1,1]; V[2,1]; V[3,1]; ...; V[10,1]; V[1,2]; ...`

**Calcolo degli indirizzi:** 
uhhhh vedi slide ? p.90

**Equivalenza tra tipi:** due tipi (T e S) sono equivalenti se sono lo stesso tipo.

- Equivalenza *per nome*: se hanno lo stesso nome.
- Equivalenza *strutturale*: se hanno la stessa struttura, proprietà:
  - un nome di tipo è equivalente a se stesso;
  - se un tipo `T` è introdotto con una definizione `type T = espressione`, `T` è equivalente a `espressione`.

**Compatibilità tra tipi:** due tipi sono compatibili quando oggetti di T possono essere usati in un contesto dove si attende valori di S. T e S sono equivalenti se:

- T e S sono equivalenti;
- i valori di T sono un sottoinsieme dei valori di S (intervallo);
- tutte le operazioni sui valori di S sono possibili anche sui valori di T (estensione);
- i valori di T corrispondono in modo canonico ad alcuni valori di S (int e float);
- i valori di T possono essere fatti corrispondere ad alcuni valori di S (float e int con troncamento).

**Conversione di tipo:** se T e S sono compatibili è comunque necessaria una conversione, esistono 2 meccanismi:

- conversione *implicita* (coerzione), ci sono 3 possibilità, i tipi sono diversi ma:
  - con stessi valori e stessa rappresentazione;
  - con valori diversi, ma stessa rappresentazione nell'intersazione
  - con valori e rappresentazioni diverse;
- conversione *esplicita* (cast): casi analoghi alla coerzione.

**Tombstones:** p.98

**Locks and keys:** p.99

**Garbage collection:** 

- l'utente alloca liberamente la memoria;
- non è permesso deallocare la memoria;
- il sistema periodicamente recupera la memoria allocata e non più utilizzabile.

**Garbage collection, mark and sweep:** p.101

---

## Capitolo 11 - Astrazione sui dati

**Astrazione e modularità:** 

- *componente*: unità di programma;
- *interfaccia*: tipi e operazioni definiti in un componente che sono visibili fuori del componente stesso;
- *specifica*: funzionamento inteso del componente, espresso mediante proprietà osservabili attraverso l'interfaccia;
- *implementazione*: strutture dati e funzioni definiti dentro al componente, non necessariamente visibili da fuori.

**Supporto linguistico per l'astrazione:** 

- astrazione sul controllo: nasconde la realizzazione nel corpo di procedure;
- astrazione sui dati: nasconde decisioni sulla rappresentazione delle strutture dati e sull'implementazione delle operazioni.

**Principio di incapsulamento:** due implementazioni corrette di un tipo non sono distinguibili dai clienti di quel tipo.

**Moduli:** il costrutto generale per l'information hiding, composto da due parti:

- interfaccia: insieme di nomi e tipi;
- implementazione: dichiarazioni per ogni nome dell'interfaccia, dichiarazioni aggiuntive nascoste.

---

## Capitolo 12 - Il paradigma orientato agli oggetti

