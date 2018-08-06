###### Expressions

```
+       integer or real addition
-       integer or real subtraction
*       integer or real multiplication
/       real division
div     integer division        e.g. 27 div 10 is 2
mod     remainder               e.g. 27 mod 10 is 7
^       string concatenation    e.g. "cub"^"a"
```

###### Functions

```
> fun double x = 2*x;
> double 3; 
val it = 6: int

> fun times4 x = double(double x);
> times4 3; 
val it = 12: int
---

fun add_them (a, b) = a+b;
val test = add_them (3, 4);

fun thermometer temp =
    if temp < 37
    then "Cold"
    else if temp > 37
         then "Warm"
         else "Normal";
val test_thermo = thermometer 40;

(*Recursive *)
fun fibonacci n =
    if n = 0 then 0 else                  
    if n = 1 then 1 else                 
    fibonacci (n - 1) + fibonacci (n - 2);
   
(*PATTERN MATCHING*)
fun fibonacci 0 = 0  
  | fibonacci 1 = 1  
  | fibonacci n = fibonacci (n - 1) + fibonacci (n - 2)
```

###### Operators

```
andalso
orelse
not
=	==
<>	!=
>
<
~   -
:: the cons operator, add one element to a list
@ appends same type lists
```

###### String, Lists[] , Tuples() , Records{}

```
val listofchars = [ #"H", #"e", #"l", #"l", #"o"];
val bob = String.implode listofchars;
cal count_bob = String.size bob;

val numbers = [1, 2, 3, 4, 5];
val numbers_count = List.length numbers;
val more_numbers = 13 :: numbers (*make [13, 1, 2, 3, 4, 5]*);

val guest_list = [ "Mom", "Dad"] @ [ "Aunt", "Uncle"];

val groups = [ [ "Alice", "Bob"],
               [ "Huey", "Dewey", "Louie"],
               [ "Bonnie", "Clyde"] 
             ];
val everyone = List.concat groups;

(*Tuples *)
val person1 = ("Simon", 28, 3.14159);

(*Records are tuples with named slots *)
val rgb = { r=0.23, g=0.56, b=0.91};
val r = #r rgb;

```

