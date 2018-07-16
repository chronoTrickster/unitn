# Esame teoria

[TOC]
### Note

- 30 e 38 sono uguali
- 2 e 44 sono uguali

---

### Esercizi

#### La funzione implementata dallo pseudo-codice:

```
int mistero(int a, int b) {
    if (b == 0) return a;
    return mistero(a / 2, b - 1);
}
```
- [ ] Può causare una crescità incontrollata dello stack
- [ ] Causa sempre ricorsione infinita
- [x] **Nessuna delle altre risposte**
- [ ] Non può essere implementata per via iterativa
- [ ] Non usa ricorsione in coda

#### La funzione implementata dallo pseudo-codice:

```
int somma(int a, int b) {
    if (a == 0) return b;
    return somma(a - 1, b) + 1;
}
```
- [ ] Nessuna delle altre risposte
- [ ] Non può essere implementata per via iterativa
- [ ] Cause sempre ricorsione infinita
- [ ] Usa ricorsione in coda
- [x] **Non usa ricorsione in coda** 

#### Si consideri lo pseudo-codice. Qual è il valore di ritorno di f(1, r(1), 1) se i parametri sono passati per nome?

```
int r(int x) {
    return r(x - 1);
}
int f(int a, int b, int c) {
    if (c == 1)
        return a;
    else
        return b;
}
```
- [ ] Non è possibile dirlo senza conoscere il tipo di scope utilizzato
- [ ] Nessuna delle altre risposte
- [x] **1**
- [ ] Si ha ricorsione infinita
- [ ] 0

#### Si consideri lo pseudo-codice. Qual è il valore di ritorno di pluto() se i parametri sono passati per valore?
```
int c = 2;
int pippo(int a) {
    c = c + 2;
    return a * 2;
}
int pluto(void) {
    return(pippo(c + 1));
}
```
- [ ] Nessuna delle altre risposte
- [ ] Dipende dal tipo di scope (statico o dinamico) utilizzato
- [ ] Non è possibile passare c+1 per valore
- [x] **6**
- [ ] 10

#### Dato il frammento di programma (espresso in pseudo-codice), qual è il valore di ritorno di f1(), assumendo scope statico?
```
int x, y, z;
void f3(void) {
    x = 0;
    y = 5;
}
void f2(void) {
    int y;
    f3();
    y = 0;
    z = 10;
}
int f1(void) {
    int x;
    x = -5;
    y = 10;
    z = x + y;
    f2();
    return z - y - x;
}
```
- [ ] 5
- [x] **Nessuna delle altre risposte**
- [ ] Non è possibile dirlo
- [ ] 0
- [ ] -5

#### 26. Se gli array sono memorizzati per colonne e int a\[25][25] è un un array multidimensionale di interi (si assuma che un intero sia memorizzato in 4 byte) con a\[0][0] che ha indirizzo 0x1000, qual è l’indirizzo di a\[5][10]?

- [ ] 0x11FE
- [ ] 0x100F
- [x] **0x13FC**
- [ ] 0x121C
- [ ] Nessuna delle altre risposte

#### 21. Se gli array sono memorizzati per colonne e char a\[100]\[100][100] è un un array multidimensionale di caratteri con a\[0][0] che ha indirizzo 0x1000, qual è l’indirizzo di a\[5]\[5][10]?

- [ ] Nessuna delle altre risposte
- [ ] 0x18899
- [ ] 0x51510
- [ ] 0xD54E
- [x] **0x19899**

#### 3. Se gli array sono memorizzati per righe e int a\[100][100] è un array multidimensionale di interi (si assuma che la dimensione di un intero sia 4 byte) con a\[0][0] che ha indirizzo 0x5000, qual è l'indirizzo di a\[5][10]?

- [x] **0x57F8** 
- [ ] Nessuna delle altre risposte
- [ ] 0x53ED 
- [ ] 0x5510 
- [ ] 0x51FE 

#### 12. Se gli array sono memorizzati per colonne ed int a\[100][100] è un array multidimensionale di interi (si assuma che la dimensione di un intero sia 4 byte)con a\[0][0] che ha indirizzo 0x5000, qual è l'indirizzo di a\[5][10]?

- [ ] 0x5510 
- [ ] 0x53ED
- [x] **Nessuna delle altre risposte**
- [ ] 0x500F
- [ ] 0x41FE 

#### 18. Se gli array sono memorizzati per righe e char a\[100]\[100][100] è un un array multidimensionale di caratteri con a\[0][0] che ha indirizzo 0x1000, qual è l’indirizzo di a\[5]\[5][10]?

- [ ] Nessuna delle altre risposte 
- [ ] 0x51510 
- [ ] 0xC54E
- [x] **0xD54E**
- [ ] 0x50510

#### 36. Se gli array sono memorizzati per colonne ed short int a\[100][100] è un array multidimensionale di interi corti (si assuma che la dimensione di uno short int sia 2 byte) con a\[0][0] che ha indirizzo 0x4100, qual è l'indirizzo di a\[5][10]?

- [x] **0x48DA** 
- [ ] 0x4510
- [ ] 0x47DA
- [ ] 0x41FE

#### 46. Se gli array sono memorizzati per colonne e char a\[100][100] è un array multidimensionale di caratteri con a\[0][0] che ha indirizzo 0x1100, qual è l'indirizzo di a\[5][10]?

- [x] **0x14ED** 
- [ ] 0x24ED
- [ ] 0x21FE
- [ ] 0x22FE

#### 50. Se gli array sono memorizzati per colonne ed short int a\[100][100] è un array multidimensionale di interi corti (si assuma che la dimensione di uno short int sia 2 byte) con a\[0][0] che ha indirizzo 0x4100, qual è l’indirizzo di a\[5][10]?:

- [x] **Nessuna delle altre risposte** 
- [ ] 0x41FE 
- [ ] 0x500F
- [ ] 0x47DA
- [ ] 0x4510
- [ ] 0x43ED

#### 15. Beta-riducendo (λn.λf.λx.f((nf)x))(λf.λx.f(f(f(fx)))) si ottiene:

- [ ] La riduzione non termina
- [ ] fx
- [x] **λf.λx.fffffx**
- [ ] Nessuna delle altre risposte
- [ ] λf.λx.f(f(f(fx)))

#### 1. Beta-riducendo (λn.λm.λf.λx.(nf)((mf)x))(λf.λx.ffffx)(λf.λx.fx) si ottiene:

- [ ] λf.λx.ffffx 
- [ ] f
- [ ] Nessuna delle altre risposte 
- [ ] λf.λx.ffffffx 
- [ ] x
- [x] **λf.λx.fffffx** 

#### 4. Beta-riducendo (λn.λm.λf.λx.(nf)((mf)x))(λf.λx.fx)(λf.λx.x) si ottiene:

- [ ] λf.λx.f(f(f(fx))) 
- [x] **λf.λx.fx** 
- [ ] Nessuna delle altre risposte 
- [ ] x
- [ ] fx

#### 27. Beta-riducendo (λa.((aλb.λc.c)λd.λe.d))(λf.λg.f) si ottiene:

- [x] **λb.λc.c** 
- [ ]  La riduzione non termina 
- [ ] c
- [ ] λb.λc.b 

#### 29. Beta-riducendo (λx.xy)(λz.zx)(λz.zx) si ottiene:

- [x] **yx(λz.zx)** 
- [ ] (λx.xy)yx
- [ ] xyz
- [ ] La riduzione non termina

#### 39. Beta-riducendo (λn.λf.λx.f((nf)x))(λf.λx.ffffx) si ottiene:

- [x] **λf.λx.fffffx** 
- [ ] fx
- [ ] L’espressione è irriducibile
- [ ] La riduzione non termina
- [ ] λf.λx.ffffffx

#### 40. Beta-riducendo ((λa.aaa)(λb.b))(λc.c) si ottiene:

- [x] **λc.c** 
- [ ] λx.xa
- [ ] aaa
- [ ] La riduzione non termina

#### 42. Beta-riducendo (λa.aaa)((λb.b)(λc.c)) si ottiene:

- [x] **λa.a** 
- [ ] aaa
- [ ] λx.xa
- [ ] La riduzione non termina

#### 14. Nella sostituzione (λa.abc)[arrg/c]

- [x] **E’ necessario applicare una Alfa-equivalenza per evitare una cattura di variabile**
- [ ] Viene catturata la variabile c
- [ ] Si rischia di catturare la variabile “a” ed è necessario applicare Beta-equivalenza per risolvere in problema
- [ ] Non c’è alcuna cattura di variabile
- [ ] Nessuna delle altre risposte

---

### Teoria

#### I puntatori di catena statica contenuti in un record di attivazione:

- [ ] Nessuna delle altre risposte
- [ ] Servono per accedere alle variabili statiche
- [ ] Devono essere esplicitamente allocati e deallocati dal codice del programma che li usa
- [x] **Servono per identificare la zona di memoria in cui è memorizzata una variabile in caso di scope statico**
- [ ] Non esistono puntatori di catena statica in un record d'attivazione

#### 13. Il concetto di variabile modificabile:

- [ ] È l'unico concetto utilizzabile quando si parla di variabili
- [ ] È imposto dall'architettura di Von Neumann (variabili non modificabili richiederebbero macchine astratte caratterizzate da memoria a sola lettura)
- [ ] Nessuna delle altre risposte
- [x] **È tipico del paradigma di programmazione imperativo**
- [ ] Permette di evitare il fenomeno dell'aliasing

#### 8. Un'entità esprimibile è:

- [ ] Nessuna delle altre risposte
- [x] **Un'entità che può essere generata come risultato da un'espressione complessa o da una funzione**
- [ ] Un'entità che ancora non compare nell'ambiente
- [ ] Un'entità che può essere memorizzata
- [ ] Una generica entità a cui può essere dato un nome

#### 9. In assenza di ambiente non locale:

- [x] **Nessuna delle altre risposte**
- [ ] Per implementare funzioni definite ricorsivamente è necessario utilizzare un fixed point combinator
- [ ] Non si possono implementare algoritmi ricorsivi
- [ ] Non si possono implementare algoritmi iterativi o ricorsivi
- [ ] Non si possono implementare algoritmi iterativi

#### 5. I record di attivazione:

- [ ] Sono allocati dinamicamente solo in caso di scope dinamico
- [ ] Devono essere esplicitamente allocati e deallocati dal codice del programma che li usa
- [x] **Possono essere allocati sia sullo stack sia sullo heap (in caso, per esempio, di funzioni di ordine superiore)**
- [ ] Sono necessari solo in presenza di funzioni di ordine superiore
- [ ] Sono allocati solo sullo heap

#### Un garbage collector:

- [ ] Richiere un'implementazione complessa, usando la tecnica dei tombstone
- [ ] È implementabile solo in linguaggi di programmazione funzionali
- [ ] Può essere implementato tramite la tecninca del reference counting, che riesce sempre ad identificare tutta la memoria allocata dinamicamente ma non più utilizzata
- [ ] È implementabile tramite la tecnica di lucchetti e chiave, che però può causare dei memory leak
- [x] **Nessuna delle altre risposte**

#### 2. La ricorsione in coda:

- [ ] Permette di risolvere il problema della ricorsione infinita
- [ ] Richiede di non scrivere mai la chiamata ricorsiva come ultimo statement di una subroutine
- [ ] Richiede di non ritornare mai direttamente il valore ritornato da una chiamata ricorsiva
- [ ] Nessuna delle altre risposte
- [x] **Permette di evitare un'eccessiva crescita della dimensione dello stack**

#### 6. Si può dire che una macchina astratta che capisce il linguaggio C non sia implementata in modo puramente compilativo perché:

- [x] **Gli eseguibili generati da un compilatore C in genere non eseguono direttamente sulla macchina hardware, ma su una macchina astratta che include il runtime del linguaggio e le funzionalità del Sistema Operativo**
- [ ] Gli eseguibili generati dal compilatore vengono comunque interpretati da una macchina virtuale
- [ ] Una macchina astratta che capisca un linguaggio di alto livello come il C non è mai implementabile con un compilatore
- [ ] Il runtime del linguaggio C è comunque sempre interpretato
- [ ] Nessuna delle altre risposte

#### 7. Il costrutto for dei linguaggi C, C++ e Java:

- [ ] Nessuna delle altre risposte
- [x] **Non è un costrutto di iterazione determinata** 
- [ ] E' necessario a tali linguaggi per implementare qualsiasi tipo di algoritmo
- [ ] E' un costrutto di iterazione determinata
- [ ] Permette di sapere in anticipo quante volte il ciclo verrà ripetuto (indipendentemente dal corpo del ciclo)

#### 10. I puntatori di catena dinamica contenuti in un record di attivazione:

- [ ] Collegano una lista di zone di memoria gestita dinamicamente
- [ ] Servono per accedere alle variabili dinamiche
- [ ] Non esistono “puntatori di catena dinamica” in un record di attivazione
- [ ] Nessuna delle altre risposte
- [x] **Permettono, a partire da un RdA, di trovare il RdA precedente sullo stack**

#### 11. In presenza di variabili modificabili:

- [ ] Nessuna delle altre risposte 
- [x] **Esistono un Ambiente che associa valori denotabili (fra cui le locazioni di memoria) a nomi ed una Memoria che associa locazioni di memoria a valori memorizzabili**
- [ ] Non esistono valori denotabili
- [ ] La valutazione del comando di assegnamento restituisce sempre un valore
- [ ] Il comando di assegnamento non ha effetti collaterali

#### 16. Il fenomeno della cattura di variabili:

- [ ] Nessuna delle altre risposte 
- [ ] Non può essere evitato in alcun modo
- [x] **Fa si che dopo una sostituzione una variabile libera diventi legata (per esempio da un’astrazione λx.)**
- [ ] Comporta la “sparizione” di variabili libere durante un’astrazione funzione
- [ ] E’ dovuto all’assenza di un ambiente non locale

#### 17. Una Macchina Astratta ML (LO) è:

- [ ] Nessuna delle altre risposte 
- [ ] E’ un modo per descrivere un interprete
- [ ] E’ implementabile solo basandosi sull’architettura di Von Neumann
- [ ] E’ un modo per descrivere un compilatore
- [x] **E’ associata ad un proprio linguaggio macchina L, che è in grado di capire ed eseguire**

#### 19. Il passaggio di parametri per nome:

- [ ] Nessuna delle altre risposte 
- [ ] Permette di passare valori solo dal chiamante al chiamato (e non viceversa)
- [x] **E’ implementabile passando una chiusura come parametro**
- [ ] Ha un valore solo teorico e non è implementabile in pratica
- [ ] Permette la cattura di variabili libere in modo da effetti non deterministici

#### 20. La tecnica del display: 

- [ ] Nessuna delle altre risposte 
- [ ] Permette di implementare facilmente lo scope dinamico
- [x] **Permette di ridurre il costo derivante dalla scansione della catena statica quando di implementa lo scope statico**
- [ ] Permette di visualizzare le zone di memoria allocata dinamicamente
- [ ] Permette di implementare le regole di scope statico senza generare frammentazione della memoria

#### 22. Un compilatore da un linguaggio L ad un linguaggio LO è:

- [x] **Un programma che trasforma un programma PL (espresso nel linguaggio L) in un programma PLO (espresso nel linguaggio LO) tale che per ogni input I si ha PL(I) = PLO(I)**
- [ ] Un programma scritto nel linguaggio LO che riceve come ingresso un programma PL (espresso nel linguaggio L) ed il suo input I generando lo stesso output che genera PL con input I
- [ ] L’implementazione di una macchina astratta scritta nel linguaggio LO, che capisce programmi scritti nel linguaggio L
- [ ] Una implementazione di macchine astratte indipendente dalla macchina fisica

#### 23. Il costrutto for dei linguaggi C, C++ e Java non è un costrutto di iterazione determinata perchè:

- [x] **Dall’interno del ciclo è possibile modificare il valore del contatore** 
- [ ] L’esistenza di costrutti di iterazione derminata implicherebbe che C, C++ e Java non sono Turing-completi
- [ ] Non esistono costrutti di iterazione determinata
- [ ] C, C++ e Java sono linguaggi imperativi

#### 24. Un oggetto denotabile (intendendo per “oggetto” una generica entità che può essere una variabile, una funzione, etc...) è:

- [x] **Nessuna delle altre risposte** 
- [ ] Un “oggetto” che può essere memorizzato in una variabile
- [ ] Un “oggetto” per cui compare un binding nell’ambiente
- [ ] Un “oggetto” che ancora non compare nell’ambiente
- [ ] Un “oggetto” che può essere generato come risultato da un’espressione complessa o da una funzione

#### 25. L’ambiente non locale di un blocco di codice è:

- [x] **L’insieme dei binding visibili dentro al blocco, ma non direttamente definiti in esso** 
- [ ]  L’insieme dei valori che le variabili non locali possono assumere
- [ ] L’insieme dei binding creati all’interno del blocco di codice
- [ ] Il subset dell’ambiente non visibile dentro al blocco di codice

#### 28. I puntatori di catena dinamica contenuti in un record di attivazione:

- [x] **Nessuna delle altre risposte** 
- [ ] Non esistono "puntatori di catena dinamica" in un record di attivazione
- [ ] Servono per identificare la zona di memoria in cui è memorizzata una variabile locale
- [ ] Devono essere esplicitamente allocati e deallocati dal codice del programma che li usa
- [ ] Servono per accedere alle variabili dinamiche

#### 30. L’allocazione dinamica della memoria:

- [x] **Può essere fatta sia dallo stack che dallo heap**
- [ ] Può essere fatta solo dallo stack
- [ ] Può essere fatta solo dallo heap
- [ ] E’ sempre effettuata solo dal compilatore o dall’interprete

#### 31. Un compilatore da un linguaggio L ad un linguaggio LO è: 

- [x] **Nessuna delle altre risposte**
- [ ] Una implementazione di macchine astratte indipendente dalla macchina fisica
- [ ] Un programma che trasforma un programma PLO (espresso nel linguaggio LO) in un programma PL (espresso nel linguaggio L) tale che per ogni input I si ha PL(I) = PLO(I)
- [ ] L'implementazione di una macchina astratta scritta nel linguaggio LO, che capisce programmi scritti nel linguaggio L
- [ ] Un programma scritto nel linguaggio LO che riceve come ingresso un programma PL (espresso nel linguaggio L) ed il suo input I generando lo stesso output che genera PL con input I

#### 33. La frammentazione esterna causa:

- [x] **L'impossibilità di allocare grandi blocchi di memoria anche se la memoria libera totale è suffciente**
- [ ] Uno spreco di memoria
- [ ] Un rallentamento rilevante nelle operazioni di allocazione della memoria
- [ ] Il funzionamento non corretto di programmi che allocano memoria dinamicamente

#### 34. La valutazione con corto circuito del predicato "A && B" (dove "&&" rappresenta un "AND" logico):

- [x] **Stabilisce che se "A" è falso allora "B" non viene valutato** 
- [ ] Stabilisce che se "B" è vero allora "A" non viene valutato
- [ ] Crea un non-determinismo nell'ordine della valutazione di "A" e "B"
- [ ] Stabilisce che "A" e "B" devono essere valutati in parallelo

#### 35. Se l'ambiente di una funzione non contiene il nome della funzione stessa:

- [x] **Non è possibile per la funzione invocarsi ricorsivamente** 
- [ ] Non ci sono particolari conseguenze
- [ ] La funzione non può usare scope dinamico
- [ ] La funzione non può usare scope statico

#### 37. La frammentazione interna causa:

- [x] **Uno spreco di memoria** 
- [ ] Il funzionamento non corretto di programmi che allocano memoria dinamicamente
- [ ] Un rallentamento rilevante nelle operazioni di allocazione della memoria
- [ ] L'impossibilità di allocare grandi blocchi di memoria anche se la memoria libera totale è suffciente

#### 38. L'allocazione dinamica della memoria:

- [x] **Può essere fatta sia dallo stack che dallo heap**
- [ ] E' sempre effettuata solo dal compilatore o dall'interprete
- [ ] Può essere fatta solo dallo stack
- [ ] Può essere fatta solo dallo heap

#### 41. L'ambiente (o environment) è:

- [x] **L'insieme delle associazioni (nome, entità denotabile) esistenti in uno specifico punto del programma ed in uno specifico momento durante l'esecuzione di un programma**
- [ ] L'insieme dei valori che una variabile assume durante l'esecuzione di un programma
- [ ] Un insieme di associazioni (nome, valore) definite staticamente durante lo sviluppo di un programma
- [ ] Una lista di coppie (nome, tipo) che permette di accedere alle variabili di un programma

#### 43. Si può dire che una macchina astratta che capisce il linguaggio Java non sia implementata in modo puramente compilativo perché:

- [x] **Non esistendo un vero e proprio runtime per Java, non si può parlare di compilazione pura**
- [ ] La macchina virtuale di Java (JVM) deve comunque essere compilata
- [ ] Una macchina astratta che capisca un linguaggio di alto livello come Java non è mai implementabile con un compilatore
- [ ] Non esistono compilatori Java

#### 45. La memoria gestita staticamente:

- [x] **E’ allocata dal compilatore prima dell’esecuzione del programma. Le entità allocate staticamente in memoria risiedono in una zona fissa di memoria durante tutta l’esecuzione del programma**
- [ ] E’ una memoria a sola lettura
- [ ] E’ allocata prima dell’esecuzione del programma. Le entità allocate staticamente possono essere deallocate durante l’esecuzione del programma, per liberare memoria
- [ ] E’ allocata esplicitamente dal programma a tempo di esecuzione, ma una volta allocata è staticamente legata al programma e non può essere liberata fino alla sua terminazione

#### 47. Un interprete di un linguaggio L scritto in un linguaggio LO è:

- [x] **Un programma scritto nel linguaggio LO che riceve come ingresso un programma PL (espresso nel linguaggio L) ed il suo input I generando lo stesso output che genera PL con input I**
- [ ] Un programma che trasforma un programma PL (espresso nel linguaggio L) in un programma PLO (espresso nel linguaggio LO) tale che per ogni input I si ha PL(I) = PLO(I)
- [ ] Una implementazione di macchine astratte indipendente dalla macchina fisica
- [ ] L'implementazione di una macchina astratta scritta nel linguaggio LO, che capisce programmi scritti nel linguaggio L

#### 48. In caso di scope statico:

- [x] **I legami fra nomi ed oggetto possono essere determinati semplicemente leggendo il testo di un programma**
- [ ] Il valore assegnato ad una variabile non può essere modificato
- [ ] I legami fra nomi ed oggetto possono essere determinati solo a tempo di esecuzione
- [ ] Non è possibile annidare più blocchi di istruzioni

#### 49. Un garbage collector:

- [x] **Può essere implementato tramite la tecnica detta “mark and sweep”, che riesce sempre ad identificare tutta la memoria allocata dinamicamente ma non più utilizzata**
- [ ] Richiede un’implementazione complessa, usando la tecnica dei tombstone (pietre tombali)
- [ ] E’ implementabile solo in linguaggi di programmazione funzionali
- [ ] E’ implementabile tramite la tecnica di lucchetti e chiavi, che però può causare dei memory leak





