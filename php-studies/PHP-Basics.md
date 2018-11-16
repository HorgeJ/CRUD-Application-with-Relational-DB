## Basics of PHP study notes
This will contain my notes as I freshen up on my PHP skills and serve as a refrence guide as I build my crud application 

### PHP Tag
This triggers PHP commands and the echo 
```PHP
<?php
  echo "Hello World";
?>
```

### The $ Symbol
This symbol must be placed infront of all variables. It makes the PHP parser faster as it will instantly know when it comes across a variable.

```PHP
<?php
  $myCounter = 0;
  $myString = "Hello World"
?>
```

### String Variables
A string is defind as a series of characters encapsulated by a set of paranthesis
```PHP
$fullName = "John Denver"
echo $johnDenver;
```
This would display the contents of the fullName variable

### Escape Sequences
Used to signify that the character after the escape character should be treated specially. There are two types of escape sequences, distinguished based on the character following the escape character "backslash".

If the backslash is followed by an alphanumeric character, the entire escape sequence, including the backslash, is given a meaning. For example: \n will give you a new line, and \t will give you a tab.

If the backslash is followed by a special character, then the character following the backslash is parsed as it is in that location. This is the one we'll be using to show a dollar sign or a quote.

* \n (linefeed)
* \r (carriage return)
* \\ (backslash)
* \$ (dollar sign)
* \" (double quote)

### Quotes
* Single Quotes - Single quoted strings are the easiest way to specify string. This method in used when we want to the string to be exactly as it is written. When string is specified in single quotes PHP will not evaluate it or interpret escape characters except single quote with backslash (‘) and backslash(\) which has to be escaped.

* Double Quotes - In double quoted strings other escape sequences are interpreted as well any variable will be replaced by their value.

### PHP Arithmetic Operators
```PHP
+   //Addition 
- 	//Subtraction 	 
* 	//Multiplication
/ 	//Division 	      
```

### PHP Assignment Operators
```PHP
x = y 	x = y 	        //The left operand gets set to the value of the expression on the right
x += y 	x = x + y 	    //Addition
x -= y 	x = x - y 	    //Subtraction
x *= y 	x = x * y 	    //Multiplication
x /= y 	x = x / y 	    //Division
x %= y 	x = x % y 	    //Modulus
```

### PHP Comparison Operators
```
== 	  Equal 	        $x == $y 	Returns true if $x is equal to $y
=== 	Identical 	    $x === $y 	Returns true if $x is equal to $y, and they are of the same type
!= 	  Not equal 	    $x != $y 	Returns true if $x is not equal to $y
<> 	  Not equal 	    $x <> $y 	Returns true if $x is not equal to $y
!== 	Not identical 	$x !== $y 	Returns true if $x is not equal to $y, or they are not of the same type
> 	  Greater than 	  $x > $y 	Returns true if $x is greater than $y
< 	  Less than 	    $x < $y 	Returns true if $x is less than $y
>= 	  Greater than or equal to 	$x >= $y 	Returns true if $x is greater than or equal to $y
<= 	  Less than or equal to 	  $x <= $y 	Returns true if $x is less than or equal to $y
```

PHP Logical Operators
```
&& 	And 	$x && $y 	True if both $x and $y are true
|| 	Or 	  $x || $y 	True if either $x or $y is true
! 	Not 	!$x 	    True if $x is not true
```
