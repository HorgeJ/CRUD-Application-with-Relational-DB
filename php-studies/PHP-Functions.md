## PHP Functions
Blocks of code that we are able to reuse by just calling them. Made of up user defined functions and system functions.

### User Defined Functions
A function may be defined using syntax such as the following: 

```PHP
<?php
  function foo($arg_1, $arg_2, /* ..., */ $arg_n)
  {
      echo "Example function.\n";
      return $retval;
  }
?>
```

### Function Arguments
Information may be passed to functions via the argument list, which is a comma-delimited list of expressions.
The arguments are evaluated from left to right. 

PHP supports passing arguments by value (the default), passing by reference, and default argument values. 

Variable-length argument lists are also supported. 

Example #1 Passing arrays to functions:

```php
<?php
  function takes_array($input)
  {
      echo "$input[0] + $input[1] = ", $input[0]+$input[1];
  }
?>
```

### Passing Arguments by Reference
By default, function arguments are passed by value (so that if the value of the argument within the function is changed, it does not get changed outside of the function). To allow a function to modify its arguments, they must be passed by reference. 

To have an argument to a function always passed by reference, prepend an ampersand (&) to the argument name in the function definition: 

Example #2 Passing function parameters by reference:
```php
<?php
  function add_some_extra(&$string)
  {
      $string .= 'and something extra.';
  }
  $str = 'This is a string, ';
  add_some_extra($str);
  echo $str;    // outputs 'This is a string, and something extra.'
?> 
```

### Default Arguments
A function may define C++-style default values for scalar arguments as follows: 
```php
<?php
  function makecoffee($type = "cappuccino")
  {
      return "Making a cup of $type.\n";
  }
  echo makecoffee();
  echo makecoffee(null);
  echo makecoffee("espresso");
?> 
```
The above example will output:
```
Making a cup of cappuccino.
Making a cup of .
Making a cup of espresso.
```

### Returning Values
Values are returned by using the optional return statement. Any type may be returned, including arrays and objects. This causes the function to end its execution immediately and pass control back to the line from which it was called.

Note: If return is omitted, NULL is returned

```php
<?php
function square($num)
  {
      return $num * $num;
  }
  echo square(4);   // outputs '16'.
?> 
```

### print_r
print_r — Prints human-readable information about a variable 

print_r() displays information about a variable in a way that's readable by humans. 
print_r(), var_dump() and var_export() will also show protected and private properties of objects. Static class members will not be shown. 

If given a string, integer or float, the value itself will be printed. If given an array, values will be presented in a format that shows keys and elements. Similar notation is used for objects. 
When the return parameter is TRUE, this function will return a string. Otherwise, the return value is TRUE. 

print_r() example:
```php
<pre>
  <?php
    $a = array ('a' => 'apple', 'b' => 'banana', 'c' => array ('x', 'y', 'z'));
    print_r ($a);
  ?>
</pre> 
```
result:
```
<pre>
Array
(
    [a] => apple
    [b] => banana
    [c] => Array
        (
            [0] => x
            [1] => y
            [2] => z
        )
)
</pre>
```
