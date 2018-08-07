[fonte](https://drive.google.com/drive/u/1/folders/1GD7WRV2huMay1BVd_MPMI4z_nwEV3Yx5)

note: 7 lezioni

# SML

[TOC]
## Lezione 1

### Espressioni

Funzioni applicate ad un valore, hanno un tipo.

### Tipi 

- `unit`: single value
- `bool`: `true` o `false`
- `int`: integers (operators:`+ - * / ~ `)
- `real`: `3.14`
- `char`: `#"a"`
- `string`: `"Hello wor" ^ "ld"`
- `NaN`
- `inf`
- `tuples`: insieme di tipi

La conversione tra tipi non è automatica:

- `ord`: char to int
- `chr`: int to char

### Condizioni

`if <p> then <exp1> else <exp2>;`

`else`, `<exp1>`, `<exp2>` sono obbligatori.

### Variabili

##### Ambiente

identificatore + valore

##### Assegnazione

```
val <name> = <value>;
val <name>:<type> = <value>;
val <name> - <expression>;
```

Le variabili non possono essere modificate:

```
val a = 3;
val a = 5;
```

Vengono create 2 variabile con nome `a`, la seconda nasconde la prima.

### Funzioni

```
fn <param> => <expression>;
fn n => n+1;

(fn n => n+1) 5;

val increment = fn n => n+1;
increment 5;
```

### Case statements

```
fn x => case x of
	<pattern_1> => <expression_1>
|	<pattern_2> => <expression_2>
...
|	<pattern_n> => <expression_n>

val day = fn x => case x of
	1 => "Monday"
|	2 => "Tuesday"
|	_ => "Other";
```

### Pattern matching

Il pattern matching può sostituire case statements.

```
val day = fn 1 => "Monday"
		|	2 => "Tuesday"
		|	_ => "Other";
```

*vedi p.15 per spiegazione di pattern, anche se non si capisce niente*

### Ricorsione

```
val rec fact = fn =>
				if n = 0
					then 1
				else
					n * fact(n-1);
```

Oppure:

`fun fact = fn => ...`

### Ambiente

Standard ML utilizza **scope statico**.

```
> val v = 5;
> val f = fn v => 2*v;
> f 2;
val it = 4: int
```

```
> val f = fn x => x+y;
Static error (y has not been declared)

> val y = 2;
> val f = fn x => x+y;
> f 3;
val it = 5: int
```

##### let/local

`let` e `local` permettono il nesting.

`let <declarations> in <expression> end;`

*uhh*

### Ricorsione in coda

Ricorsione con la chiamata alla ricorsione alla fine.

- Con ricorsione in coda:

`fun fact n = if n = 0 then 1 else n * fact(n-1);`

- Senza ricorsione in coda:

`fun fact n = if n = 0 then 1 else fact(n-1) * n;`

### let / local

*vedi p.23-25*

### Currying

*vedi p.27-29*

## Lezione 3

### Sinonimi (type)

```
type time_t = int;
val a:time_t = 5;

type real_pair = real * real;
val freal = fn(x,y):real_pair => x * y;
```

### Datatype

```
datatype currency = eur | usd | ounce_gold;
val e = eur;
```

