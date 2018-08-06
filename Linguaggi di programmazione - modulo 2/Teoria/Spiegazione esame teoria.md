# Spiegazione esame teoria

[TOC]

## Esercizi

### 1. Ricorsione X

**Ricorsione**: una funzione è ricorsiva se definita in termini di se stessa.
*p.66*

**Ricorsione e iterazione**: ogni programma ricorsivo può essere tradotto in uno equivalente iterativo e viceversa (con efficienza variabile).
*p.67*

**Ricorsione in coda**: f è tail recorsive se contiene solo *chiamate in coda*. Una chiamata di g in f si dice in "in coda" se f restituisce il valore restituito da g senza ulteriore computazione.
*p.68*

### 2. Passaggio per valore

```
int f (int n){ //parametro formale
    return n+1;
}

x = f(4); //parametro attuale
```

Il valore dell'attuale è assegnato al formale, che si comporta come una variabile locale. Le modifiche al formale non passano all'attuale.
*p.78*

### 3. Passaggio per nome

Una chiamata alla procedura P equivale a eseguire il corpo di P dopo aver sostituito i parametri attuali al posto dei parametri formali. 
*p.84*

Presenta la lazy evaluation (vengono valutati solo quando incontrati nel codice)
*telegram*

### 4. Passaggio per riferimento/variabile

Viene passato un riferimento (indirizzo) all'attuale; i riferimenti al formale sono riferimenti all'attuale (*aliasing*). Le modifiche al formale passano all'attuale.
*p.78*

L'attuale deve essere un L-valore ("una variabile").
*p.80*

### 5. Scope statico X

**La variabile esiste SOLO nel blocco in cui viene creata.**

1. f1() = 10

```
int x, y, z;
f1(){
    int x; //xf1
    x = -5; //xf1 = -5
    y = 10; //y = 10
    z = x + y; // z = xf1 + y = -5 + 10 = 5
    f2(){
        int y; //yf2
        f3(){
            x = 0; //x = 0
            y = 5; // y = 5
        }
        y = 0; //yf2 = 0
        z = 10; //z = 10
    }
    return z - y - x; // z - y - xf1 = 10 - 5 - (-5) = 10
}
```

2. topolino() = 11

```
int x, y;
topolino(){
    int x, z; //x1, z1
    x = 5; //x1 = 5
    y = 15; //y = 15
    z = x + y; // z1 = x1 + y = 5 + 15 = 20
    pluto(){
      int y; //y2
      pippo(){
      	x = 8; //x = 8
      	y = 4; //y = 4
      }
      y = 3; //y2 = 3
    }
    return z - y - x; //z1 - y - x1 = 20 - 4 - 5 = 11
}
```

3. topolino() = 653

```
 int x, y, z;
 int topolino(void) {
      int x; //x1
      x = 5; //x1 = 5
      y = 15; // y = 15
      z = x + y; // z = x1 + y = 20
      paperino(){
        int y; //y2
      	minni(){
        	x = 4; //x = 4
      		y = 8; //y = 8
      	}
      	y = 1; //y2 = 1
      	z = 666; //z = 666
      }
      return z - y - x; //z - y - x1 = 666 - 8 - 5 = 653
}
```

### 6. Scope dinamico X

**La variabile esiste fino alla terminazione del blocco.**

1. topolino() = 14

```
int a, b, c;
void topolino(void) {
	int a; //a1
	a = 1; //a1 = 1
	b = 10; //b = 10
	pluto(){
		int c; //c1
		int b; //b1
		pippo(){
			int a; //a2
			a = 6; //a2 = 6
			b = 5; //b1 = 5
		}//a2 muore
		c = 3; //c1 = 3
		a = 4; //a1 = 4
	}//c1, b1 muore
	c = a + b; //a1 + b = 4 + 10 = 14
}
```

1. f1() = 0

```
int x, y, z;
int f1(void) {
	int x; //x1
	x = -5; //x1 = -5
	y = 10; //y = 10
	z = x + y; //z = x1 + y = -5 + 10 = 5
	f2(){
    	int y; //y1
		f3(){
			x = 0; //x1 = 0
			y = 5; //y1 = 5
		}
		y = 0; //y1 = 0
		z = 10; //z = 10
	}//y1 muore
	return z - y - x; // z - y - x1 = 10 - 10 - 0 = 0
}
```

### 7. Array per righe X

*NB: char = 1, int = 4, short int = 2*

Se gli array sono memorizzati **per righe** ed int **a\[A]\[B]** è un array multidimensionale di interi (si assuma che la dimensione di un intero sia D byte) con a\[0]\[0] che ha indirizzo INDIRIZZO_BASE, qual è l’indirizzo di a\[X]\[Y]?	

```
INDIRIZZO_BASE + (D*B*X) + (D*Y)
```

Se gli array sono memorizzati **per righe** ed int **a\[A]\[B]\[C]** è un array multidimensionale di interi (si assuma che la dimensione di un intero sia D byte) con a\[0]\[0] che ha indirizzo INDIRIZZO_BASE, qual è l’indirizzo di a\[X]\[Y]\[Z]?

```
INDIRIZZO_BASE + (D*B*C*X) + (D*C*Y) + (D*Z)
```

### 8. Array per colonne X

Se gli array sono memorizzati **per colonne** ed int **a\[A]\[B]** è un array multidimensionale di interi (si assuma che la dimensione di un intero sia D byte) con a\[0]\[0] che ha indirizzo INDIRIZZO_BASE, qual è l’indirizzo di a\[X]\[Y]?

```
INDIRIZZO_BASE + (D*A*Y) + (D*X)
```
Se gli array sono memorizzati **per colonne** ed int **a\[A]\[B]\[C]** è un array multidimensionale di interi (si assuma che la dimensione di un intero sia D byte) con a\[0]\[0] che ha indirizzo INDIRIZZO_BASE, qual è l’indirizzo di a\[X]\[Y]\[Z]?


```
INDIRIZZO_BASE + (D*A*B*Z) + (D*A*Y) + (D*X)
```
### 9. Beta riduzioni X

[Stack overflow](https://stackoverflow.com/questions/34140819/lambda-calculus-reduction-steps?utm_medium=organic&utm_source=google_rich_qa&utm_campaign=google_rich_qa): Lambdas are like a funtion, they take a function as input, they return a function.

#### Operazioni

- Alpha conversion:

```
(λx.xx)(λx.x) becomes (λx.xx)(λy.y) or (λx.xx)(λx'.x') 
```

- Beta reduction: sostituzione

```
(λx.xy)z
	λx = x nome del parametro
	xy = output //dopo il punto
	z = input //dopo la parentesi

(λx.xy)z >> zy
```

- Eta conversion/eta reduction

```
λx.(f x) = f if f does not make use of x 
ex: (λx.(λy.yy)x) becomes (λy.yy), because f = (λy.yy)
```

#### Notazione

```
(λ param . output)input => output [param := input] => result

(λx.xy)z
= (xy)[x:=z]
= (zy)
= zy
```

#### Esempi

```
(λxyz.xyz)(λx.xx)(λx.x)x
//togli la prima variabile che trovi dopo λ, 
//sostituisci la sua occorrenza dopo il punto con il primo contenuto al di fuori delle parentesi
(λyz.(λx.xx)yz)(λx.x)x //sostituisco x con (λx.xx)
(λyz.yyz)(λx.x)x //sostituisco le x con y
(λz.(λx.x)(λx.x)z)x //sostituisco le y con (λx.x)
(λz.(λx.x)z)x // sostituisco la x con (λx.x)
(λz.z)x //sostituisco x con z
x // sostituisco z con x
```

1. **( λn.λf.λx.f ( (nf) x) )  ( λf.λx.f (f (f (fx) ) ) )**

(**λn**.λf.λx. f((**n**f)x) ) **(λf.λx.f(f(f(fx))))**
//sostituisco la 'n' in 'f((nf)x)' con '(λf.λx.f(f(f(fx))))' e rimuovo λn

λf.λx.f(((**λf**.λx. **f**(**f**(**f**(**f**x)))) **f**)x)
//sostituisco le f con f e rimuovo λf

λf.λx.f(((**λx**. f(f(f(f**x**))))**x**)
//sostituisco le x con x e rimuovo λx

λf.λx.f(f(f(f(fx))))
//sistemo le parentesi

λf.λx.fffffx

2. **(λn.λm.λf.λx.(nf)((mf)x))(λf.λx.ffffx)(λf.λx.fx)**

(**λn.**λm.λf.λx. (**n**f)((mf)x) ) **(λf.λx.ffffx)** (λf.λx.fx)

(λm.λf.λx. ( (**λf**.λx.**ffff**x) **f**)((mf)x) )  (λf.λx.fx)

(λm.λf.λx. ( (**λx**.ffff**x**) ) **((mf)x)** )  (λf.λx.fx)

(λm.λf.λx. ( (ffff ((mf)x) ) ) )  (λf.λx.fx)

(**λm**.λf.λx.ffff**m**fx)  **(λf.λx.fx)**

(λf.λx.ffff(**λf**.λx.**f**x)**f**x)  

(λf.λx.ffff(**λx**.f**x**)**x**)  

(λf.λx.ffff(fx))  

**λf.λx.fffffx** 

3. **(λn.λm.λf.λx.(nf)((mf)x))(λf.λx.fx)(λf.λx.x)**

(**λn**.λm.λf.λx.(**n**f)((mf)x)) **(λf.λx.fx)** (λf.λx.x)

(λm.λf.λx.( (**λf**.λx.**f**x)**f**) ((mf)x)) (λf.λx.x)

(λm.λf.λx.( (**λx**.f**x**) **((mf)x)**) (λf.λx.x)

(**λm**.λf.λx.f**m**fx) **(λf.λx.x)**

(λf.λx.f(**λf**.λx.x)**f**x) 

...

**λf.λx.fx**

4. **(λa.((aλb.λc.c)λd.λe.d))(λf.λg.f)** ????
5. **(λx.xy)(λz.zx)(λz.zx)**

(**λx**.**x**y)**(λz.zx)**(λz.zx)

((**λz**.**z**x)**y**)(λz.zx)

yx(λz.zx)

7. **((λa.aaa)(λb.b))(λc.c)**

((**λa**.**aaa**)**(λb.b)**)(λc.c)

((**λb**.**b**)**(λb.b)**(λb.b))(λc.c)

((**λb**.**b**)**(λb.b)**)(λc.c)

(**λb**.**b**)**(λc.c)**

**(λc.c)**

8. **(λa.aaa)((λb.b)(λc.c))**

(**λa**.**aaa**) **((λb.b)(λc.c))**

((**λb**.**b**)**(λc.c)**) ((λb.b)(λc.c)) ((λb.b)(λc.c))

(λc.c)(λc.c)(λc.c)

**(λc.c)**





