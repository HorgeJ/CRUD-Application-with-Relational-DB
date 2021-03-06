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

### Variable Naming Rules
When naming PHP variable the follwing rules must be followed:
* Must start with a letter or underscore ( _ )
* Can contain only the characters  a-z,  A-Z,  0-9,  and  _(underscore).
* Cannot contain spaces
* Follow case sensitivity rules


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

### Arrays
An array stores multiple values in one single variable.

Declared as : `$phoneBook = (val1, val2, val...)`

In PHP there are three types of arrays:
* Indexed Array - Arrays with a numeric index
* Associative Array - Arrays with named keys
* Multidimensional Array - Arrays containing one or more arrays

```
<?php
  $cars = array("Volvo", "BMW", "Toyota");
  echo "I like " . $cars[0] . ", " . $cars[1] . " and " . $cars[2] . ".";
?> 
```
results: I like Volvo, BMW and Toyota. 

### PHP Indexed Arrays
The index can be assigned automatically (index always starts at 0), like this:
```
$cars = array("Volvo", "BMW", "Toyota");
```

or the index can be assigned manually:

```
$cars[0] = "Volvo";
$cars[1] = "BMW";
$cars[2] = "Toyota"; 
```

### PHP Associative Arrays
Associative arrays are arrays that use keys that you assign to them.

There are two ways to create an associative array: 
```
$age = array("Peter"=>"35", "Ben"=>"37", "Joe"=>"43");
```
or: 

```
$age['Peter'] = "35";
$age['Ben'] = "37";
$age['Joe'] = "43"; 
```

example:
```PHP
<?php
  $age = array("Bones" => 7, "Cat" => 11, "Horge" => 30);
  echo "Horge is " .$age.['Horge] . " years old.";
?>
```
output: Horge is 30 years old.

### Looping Through an Associative Array
```
<?php
  $age = array("Bones" => 7, "Cat" => 11, "Horge" => 30);
  
  foreach($age as $x => $x_value){
    echo "Key=" . $x . ", Value=" . $x_value;
  }
?>
```

### Two-Dimensional Arrays
A multidimensional array is an array containing one or more arrays

ex:
```SQL
<?php
   $oxo  =  array(array('x',  '  ',  'o'),
            array('o',  'o',  'x'),
            array('x',  'o',  '  '));
?>
```


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

### PHP Logical Operators
```
&& 	And 	$x && $y 	True if both $x and $y are true
|| 	Or 	  $x || $y 	True if either $x or $y is true
! 	Not 	!$x 	    True if $x is not true
```

### Concatination 
String concatination uses the period ( . ) character to append one string to another.

ex:
```PHP
echo "You have " . $msgs . " messages.";

$bulletin .= $nesFlash;     // similar to +=
``` 

### Booleans
 A boolean expresses a truth value. It can be either TRUE or FALSE.
 
 ```SQL
var_dump((bool) "");        // bool(false)
var_dump((bool) 0);        // bool(false)
var_dump((bool) 1);         // bool(true)
var_dump((bool) -2);        // bool(true)
var_dump((bool) "foo");     // bool(true)
var_dump((bool) 2.3e5);     // bool(true)
var_dump((bool) array(12)); // bool(true)
var_dump((bool) array());   // bool(false)
var_dump((bool) "false");   // bool(true)
 ```
 
 ### Functions
 Used to seprate sections of code made to do a certain task
 
 syntax:
 ```
 function functionName() {
    code to be executed;
} 
 ```
 
 ex:
 ```PHP
 <?php
function writeMsg() {
    echo "Hello world!";
}

writeMsg(); // call the function
?> 
 ```

### HTML and PHP

PHP was designed to make building web pages easier. PHP can easily be added to HTML by using the PHP tags in conjunction with an HTML file.

ex: Assuming we are using an index.html page, we should change the .html extension to .php so the server knows were working with PHP
```html
<div class="avatar">
            <img src="img/logo.png" alt="Alt For Image">
          </div>
          <h1><?php echo "Horge Jorge"; ?></h1>
          <p>Contact:<br />
          <a href="mailto:">EMAIL</a></p>
</div>
```

### PHP Date and Timestamps
Returns a string formatted according to the given format string using the given integer timestamp or the current time if no timestamp is given. In other words, timestamp is optional and defaults to the value of time(). 
```
time();
```

**Timestamps

* getlastmod() - Gets timestamp of last page modification of current page
* filemtime() - Allows you to get the timestamp of the last modification date of a specified file.
* mktime() - Allows you to get the timestamp for a specific date and time
* strtotime() - Parse about any English textual datetime description into a timestamp

ex: current year
```PHP
<section class="footer text-center">
  &copy; <?php echo date('Y'); ?>
</section>
```

ex: last date modified 
```PHP
<section class="footer text-center">
  &copy; 
  <?php echo 
     date('Y'); 
     echo " Last modified: " . date ("F d Y H:i:s.", getlastmod());
  ?>
</section>
```

ex: Use a SINGLE date function to display today's date in the message. Use the following format: full month, day of the month with leading 0, comma and 4 digit year.
```PHP
<?php
echo 'Today is ' . date("F d, Y");
?>
```

### Combining Multiple Files with Includes
 PHP allows us to INCLUDE other files, so they function as part of the current page, while keeping them separate. This is very useful for organization and not repeating code for things such as footers and navigation.
 
Included files act as if you had pasted the code directly into the file. Any variables that have already been defined in the main file such as display_name can be utilized and CHANGED. If the file cannot be included PHP will give an error, but continue to process the script. If you want to guarantee that the file is included before continuing on, you should use 'require'.

* [include][http://php.net/manual/en/function.include.php] - includes and evaluates the specified file.
* include_once - the only difference being that if the code from a file has already been included, it will not be included again, and include_once returns TRUE. As the name suggests, the file will be included just once.
* require - is identical to include except upon failure it will also produce a fatal error. In other words, it will stop the script whereas include only emits a warning which allows the script to continue.
* require_once - identical except PHP will check if the file has already been included, and if so, not include it.

ex:
```PHP
<?php include 'inc/units.php' ?> // runs and display the appropriate code from units.php
```
placing all our include files in an inc directory we can directly reference code blocks in our index file. 
Styling will have to be done in the included file.
