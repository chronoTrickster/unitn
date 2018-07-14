# Esame teoria

### Esercizi

##### La funzione implementata dallo pseudo-codice:

```
int mistero(int a, int b) {
    if (b == 0) return a;
    return mistero(a / 2, b - 1);
}
```
- [ ] Può causare una crescità incontrollata dello stack
- [ ] Causa sempre ricorsione infinita
- [x] Nessuna delle altre risposte
- [ ] Non può essere implementata per via iterativa
- [ ] Non usa ricorsione in coda

##### La funzione implementata dallo pseudo-codice:

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
- [x] Non usa ricorsione in coda 

##### Si consideri lo pseudo-codice. Qual è il valore di ritorno di f(1, r(1), 1) se i parametri sono passati per nome?

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
- [x] 1
- [ ] Si ha ricorsione infinita
- [ ] 0

##### Si consideri lo pseudo-codice. Qual è il valore di ritorno di pluto() se i parametri sono passati per valore?
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
- [x] 6
- [ ] 10

##### Dato il frammento di programma (espresso in pseudo-codice), qual è il valore di ritorno di f1(), assumendo scope statico?
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
- [x] Nessuna delle altre risposte
- [ ] Non è possibile dirlo
- [ ] 0
- [ ] -5

##### Se gli array sono memorizzati per colonne e int a\[25][25] è un un array multidimensionale di interi (si assuma che un intero sia memorizzato in 4 byte) con a\[0][0] che ha indirizzo 0x1000, qual è l’indirizzo di a\[5][10]?

- [ ] 0x11FE
- [ ] 0x100F
- [x] 0x13FC
- [ ] 0x121C
- [ ] Nessuna delle altre risposte

##### Se gli array sono memorizzati per colonne e char a\[100]\[100][100] è un un array multidimensionale di caratteri con a\[0][0] che ha indirizzo 0x1000, qual è l’indirizzo di a\[5]\[5][10]?

- [ ] Nessuna delle altre risposte
- [ ] 0x18899
- [ ] 0x51510
- [ ] 0xD54E
- [x] 0x19899

---

### Teoria

##### I puntatori di catena statica contenuti in un record di attivazione:

- [ ] Nessuna delle altre risposte
- [ ] Servono per accedere alle variabili statiche
- [ ] Devono essere esplicitamente allocati e deallocati dal codice del programma che li usa
- [x] Servono per identificare la zona di memoria in cui è memorizzata una variabile in caso di scope statico
- [ ] Non esistono puntatori di catena statica in un record d'attivazione

##### Il concetto di variabile modificabile:

- [ ] È l'unico concetto utilizzabile quando si parla di variabili
- [ ] È imposto dall'architettura di Von Neumann (variabili non modificabili richiederebbero macchine astratte caratterizzate da memoria a sola lettura)
- [ ] Nessuna delle altre risposte
- [x] È tipico del paradigma di programmazione imperativo
- [ ] Permette di evitare il fenomeno dell'aliasing

##### Un'entità esprimibile è:

- [ ] Nessuna delle altre risposte
- [x] Un'entità che può essere generata come risultato da un'espressione complessa o da una funzione
- [ ] Un'entità che ancora non compare nell'ambiente
- [ ] Un'entità che può essere memorizzata
- [ ] Una generica entità a cui può essere dato un nome

##### In assenza di ambiente non locale:

- [x] Nessuna delle altre risposte
- [ ] Per implementare funzioni definite ricorsivamente è necessario utilizzare un fixed point combinator
- [ ] Non si possono implementare algoritmi ricorsivi
- [ ] Non si possono implementare algoritmi iterativi o ricorsivi
- [ ] Non si possono implementare algoritmi iterativi

##### I record di attivazione:

- [ ] Nessuna delle altre risposte
- [ ] Devono essere esplicitamente allocati e deallocati dal codice del programma che li usa
- [x] Possono essere allocati sia sullo stack sia sullo heap (in caso, per esempio, di funzioni di ordine superiore)
- [ ] Sono necessari solo in presenza di funzioni di ordine superiore
- [ ] Sono allocati solo sullo heap