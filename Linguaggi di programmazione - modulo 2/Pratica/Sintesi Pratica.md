[slides SML][https://drive.google.com/drive/u/0/folders/1GD7WRV2huMay1BVd_MPMI4z_nwEV3Yx5]

## 1

###### Espressioni: 

###### Types: 

- **unit**: single valuse, used for expressions that don't return a value
- **bool**: `true` and `false`
- **int**: integers, *operators*: + - *
- **real**
- **NaN**, **inf**
- **char**: #"a"
- **string**

###### Conditionals:

`if <p> then <exp1>  else <exp2>;`

###### Variables:

`val <name> = <value>;`

`val <name>:<type> = <value>;`

`val <name> - <value>;`

###### Functions:

`fn <param> => <expression>;`

​	examples: 

- `fn n => n+1;` &rarr; `(fn n => n+1) 5;`
- `val increment = fn n => n+1;` &rarr; `increment 5;`

###### Cases:

```
fn x => case x of
	<pattern_1> => <expression_1>
|	<pattern_2> => <expression_2>
	...
|	<pattern_n> => <expression_n>
```
​	example:
```
val day = fn n => case n of
	1 => "Monday"
|	2 => "Tuesday"
|	_ => "Other";
```


