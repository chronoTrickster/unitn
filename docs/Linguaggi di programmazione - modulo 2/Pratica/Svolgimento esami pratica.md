## Giugno 2015

**Definisco un nuovo tipo: naturale.**

```
datatype naturale = zero | successivo of naturale;
```

Naturale può avere 2 “valori”:

- zero

- successivo x, x è uno dei 2 valori di naturale.

  ​	successivo zero	//1

  ​	successivo(successivo zero)	//2

  ​	...

**Definisco la somma.**

```
val rec somma = fn 
				zero		    => (fn n => n)
			|	successivo a	=> (fn n => successivo (somma a n));
```

**Esempio di chiamata**

```
> somma zero zero; 
zero
> somma (successivo zero) zero;
(successivo zero)
> somma (successivo zero) (successivo zero);
successivo(successivo zero)
> somma (successivo(successivo zero)) (successivo zero);
successivo(successivo(successivo zero))
```

**Spiegazione**

1. `val rec somma=`  definisco la funzione ricorsiva somma
2. `fn zero => (fn n => n)` 

Se il primo parametro è `zero` ritorno il secondo

1. `| successivo a => (fn n => successivo (somma a n));` 

Se il primo parametro è `successivo qualcosa`   

`	a = qualcosa`

`n = secondo parametro`

ritorno `successivo` + quello che mi ritorna `somma a n` (qualcosa + secondo parametro)
