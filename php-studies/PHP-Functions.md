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

### Variable Functions
PHP supports the concept of variable functions. This means that if a variable name has parentheses appended to it, PHP will look for a function with the same name as whatever the variable evaluates to, and will attempt to execute it. Among other things, this can be used to implement callbacks, function tables, and so forth. 

```php
<?php
  function foo() {
      echo "In foo()<br />\n";
  }

  function bar($arg = '')
  {
      echo "In bar(); argument was '$arg'.<br />\n";
  }

  // This is a wrapper function around echo
  function echoit($string)
  {
      echo $string;
  }

  $func = 'foo';
  $func();        // This calls foo()

  $func = 'bar';
  $func('test');  // This calls bar()

  $func = 'echoit';
  $func('test');  // This calls echoit()
?> 
```

### Anonymous functions
Anonymous functions, also known as closures, allow the creation of functions which have no specified name. They are most useful as the value of callback parameters, but they have many other uses. 
Anonymous functions are implemented using the Closure class. 

Anonymous function example:
```
<?php
  echo preg_replace_callback('~-([a-z])~', function ($match) {
      return strtoupper($match[1]);
  }, 'hello-world');
  // outputs helloWorld
?> 
```

## Internal (built-in) Functions
PHP comes standard with many functions and constructs.

### strlen()
strlen — Get string length

Returns the length of the given string:
```
int strlen ( string $string );
```

ex:
```php
<?php
  $str = 'abcdef';
  echo strlen($str); // 6

  $str = ' ab cd ';
  echo strlen($str); // 7
?> 
```

### substr()
Returns the portion of string specified by the start and length parameters. 

```
string substr ( string $string , int $start [, int $length ] )
```

The input string. Must be one character or longer. 

If start is non-negative, the returned string will start at the start'th position in string, counting from zero. For instance, in the string 'abcdef', the character at position 0 is 'a', the character at position 2 is 'c', and so forth. 

If start is negative, the returned string will start at the start'th character from the end of string. 

If string is less than start characters long, FALSE will be returned.

Example #1 Using a negative start:
```php
<?php
  $rest = substr("abcdef", -1);    // returns "f"
  $rest = substr("abcdef", -2);    // returns "ef"
  $rest = substr("abcdef", -3, 1); // returns "d"
?> 
```

If length is given and is positive, the string returned will contain at most length characters beginning from start (depending on the length of string). 

If length is given and is negative, then that many characters will be omitted from the end of string (after the start position has been calculated when a start is negative). If start denotes the position of this truncation or beyond, FALSE will be returned.

If length is given and is 0, FALSE or NULL, an empty string will be returned. 

If length is omitted, the substring starting from start until the end of the string will be returned. 

Example #2 Using a negative length:
```php
<?php
  $rest = substr("abcdef", 0, -1);  // returns "abcde"
  $rest = substr("abcdef", 2, -1);  // returns "cde"
  $rest = substr("abcdef", 4, -4);  // returns false
  $rest = substr("abcdef", -3, -1); // returns "de"
?> 
```
