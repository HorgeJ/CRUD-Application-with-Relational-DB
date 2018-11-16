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

### PHP Arithmetic Operators
```
+   Addition 	      $x + $y   Sum of $x and $y
- 	Subtraction 	  $x - $y 	Difference of $x and $y
* 	Multiplication 	$x * $y 	Product of $x and $y
/ 	Division 	      $x / $y 	Quotient of $x and $y
```

### PHP Assignment Operators
```
x = y 	x = y 	        The left operand gets set to the value of the expression on the right
x += y 	x = x + y 	    Addition
x -= y 	x = x - y 	    Subtraction
x *= y 	x = x * y 	Multiplication
x /= y 	x = x / y 	    Division
x %= y 	x = x % y 	    Modulus
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
