## PHP Arrays and Control Structures
Let's review conditionals, loops and the compound variable, arrays, all of which help you write more powerful and intelligent programs using less code.

### If Statements
The if construct is one of the most important features of many languages, PHP included. It allows for conditional execution of code fragments. PHP features an if structure that is similar to that of C: 

```
if (expr)
  statement
```

### Else Statement
else extends an if statement to execute a statement in case the expression in the if statement evaluates to FALSE. 

```php
<?php
if ($a > $b) {
  echo "a is greater than b";
} else {
  echo "a is NOT greater than b";
}
?> 
```

### elseif
lseif, as its name suggests, is a combination of if and else. Like else, it extends an if statement to execute a different statement in case the original if expression evaluates to FALSE. However, unlike else, it will execute that alternative expression only if the elseif conditional expression evaluates to TRUE.

ex:
```php
  <?php
if ($a > $b) {
    echo "a is bigger than b";
} elseif ($a == $b) {
    echo "a is equal to b";
} else {
    echo "a is smaller than b";
}
?> 
```

### Switch Statement
The switch statement is similar to a series of IF statements on the same expression. In many occasions, you may want to compare the same variable (or expression) with many different values, and execute a different piece of code depending on which value it equals to. This is exactly what the switch statement is for. 

ex:
```php
<?php
switch ($i) {
    case "apple":
        echo "i is apple";
        break;
    case "bar":
        echo "i is bar";
        break;
    case "cake":
        echo "i is cake";
        break;
}
?> 
```

### Arrays 
Arrays in PHP are actually ordered maps. A map is a type that associates values to keys. This type is optimized for several different uses; it can be treated as an array, list (vector), hash table (an implementation of a map), dictionary, collection, stack, queue, and probably more. As array values can be other arrays, trees and multidimensional arrays are also possible.

ex:
```php
<?php
    $a = [1, 2, 3, 4];
    print_r($a);
?>
```
The above example will output:
```
Array
(
    [0] => 1
    [1] => 2
    [2] => 3
    [3] => 4
)
```

### Adding Array Elements
three ways php gives us to add elements to an array -- two of which let you add elements to the end of the array, and one which lets you add elements to the beginning of the array. 

Add a new element to the end of an array using basic array object
```
 $array[] = 'New Element Value';  // will append new value to the end of the array, must use the brackets
```

##### array_push
array_push() treats array as a stack, and pushes the passed variables onto the end of array. The length of array increases by the number of variables pushed.

ex:
```php
<?php
  $stack = array("orange", "banana");
  array_push($stack, "apple", "raspberry");
  print_r($stack);
?> 
```
results:Array
(
    [0] => orange
    [1] => banana
    [2] => apple
    [3] => raspberry
)

