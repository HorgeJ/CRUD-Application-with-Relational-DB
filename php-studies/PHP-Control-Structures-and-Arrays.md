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
results:
```
Array
(
    [0] => orange
    [1] => banana
    [2] => apple
    [3] => raspberry
)
```

#### array_unshift()
array_unshift() prepends passed elements to the front of the array. Note that the list of elements is prepended as a whole, so that the prepended elements stay in the same order. All numerical array keys will be modified to start counting from zero while literal keys won't be changed. 

ex: 
```php
<?php
  $queue = array("orange", "banana");
  array_unshift($queue, "apple", "raspberry");
  print_r($queue);
?> 
```
results:
```
Array
(
    [0] => apple
    [1] => raspberry
    [2] => orange
    [3] => banana
)
```

### Removing Array Elements
3 ways to remove items from an array

#### array_shift()
array_shift() shifts the first value of the array off and returns it, shortening the array by one element and moving everything down. All numerical array keys will be modified to start counting from zero while literal keys won't be touched. 

ex:
```php
<?php
  $stack = array("orange", "banana", "apple", "raspberry");
  $fruit = array_shift($stack);
  print_r($stack);
?> 
```
results:
```
Array
(
    [0] => banana
    [1] => apple
    [2] => raspberry
)
// orange will be assigned to $fruit
```

#### array_pop()
array_pop() pops and returns the value of the last element of array, shortening the array by one element. 

ex:
```php
<?php
  $stack = array("orange", "banana", "apple", "raspberry");
  $fruit = array_pop($stack);
  print_r($stack);
?> 
```
results:
```
Array
(
    [0] => orange
    [1] => banana
    [2] => apple
)
// raspberry will be assigned to $fruit
```

#### unset()
unset() destroys the specified variables. 
The behavior of unset() inside of a function can vary depending on what type of variable you are attempting to destroy. 
If a globalized variable is unset() inside of a function, only the local variable is destroyed. The variable in the calling environment will retain the same value as before unset() was called. 

unset($array); will remove your entire array.


### Modifying an Array
How to modify an element by specifying it's key.

#### array_splice()
Removes the elements designated by offset and length from the input array, and replaces them with the elements of the replacement array, if supplied. 

ex:
```
<?php
  $input = array("red", "green", "blue", "yellow");
  array_splice($input, 2);
  // $input is now array("red", "green")

  $input = array("red", "green", "blue", "yellow");
  array_splice($input, 1, -1);
  // $input is now array("red", "yellow")

  $input = array("red", "green", "blue", "yellow");
  array_splice($input, 1, count($input), "orange");
  // $input is now array("red", "orange")

  $input = array("red", "green", "blue", "yellow");
  array_splice($input, -1, 1, array("black", "maroon"));
  // $input is now array("red", "green",
  //          "blue", "black", "maroon")

  $input = array("red", "green", "blue", "yellow");
  array_splice($input, 3, 0, "purple");
  // $input is now array("red", "green",
  //          "blue", "purple", "yellow");
?> 
```

#### array_combine()
Creates an array by using the values from the keys array as keys and the values from the values array as the corresponding values. 

ex:
```php
<?php
  $a = array('green', 'red', 'yellow');
  $b = array('avocado', 'apple', 'banana');
  $c = array_combine($a, $b);
  print_r($c);
?> 
```
results:
```
Array
(
    [green]  => avocado
    [red]    => apple
    [yellow] => banana
)
```

#### array_merge
Merges the elements of one or more arrays together so that the values of one are appended to the end of the previous one. It returns the resulting array. 

ex:
```
<?php
  $array1 = array("color" => "red", 2, 4);
  $array2 = array("a", "b", "color" => "green", "shape" => "trapezoid", 4);
  $result = array_merge($array1, $array2);
  print_r($result);
?> 
```

results:
```
Array
(
    [color] => green
    [0] => 2
    [1] => 4
    [2] => a
    [3] => b
    [shape] => trapezoid
    [4] => 4
)
```

### Associative Arrays
You can assign your own keys to array elements -- and they don't have to be numbers. In fact, your code can be easier to read and understand if you use a name for a key. This is called an Associative Array, because a specific key is associated with a specific value.

Arrays are also referred to as a hash or dictionary 

Associative arrays are arrays that use named keys that you assign to them.

ex: Creating an associative array
```
$age = array("Peter"=>"35", "Ben"=>"37", "Joe"=>"43");
```
or:
```
$age['Peter'] = "35";
$age['Ben'] = "37";
$age['Joe'] = "43"; 
```

ex: using the keys in a script
```
<?php
  $age = array("Peter"=>"35", "Ben"=>"37", "Joe"=>"43");
  
  echo "Peter is " . &age['Peter'] . " years old.";
?>
```

#### Extract
You can use the extract function to extract the key value pairs as individual variables.

```
$var_array = array("color" => "blue",
                   "size"  => "medium",
                   "shape" => "sphere");
extract($var_array);
```

Gives us the variables:
```
$color = "blue", $size = "medium", and $shape = "sphere".
```

### Multidimensional Arrays
In a multidimensional array, a key in the outer array contains a secondary inner array. Multidimensional arrays may have indexed or named keys.

ex:
```
$task1 = array(
   'title' => 'Laundry',
   'priority' => 2,
   'due' => '',
   'complete' => true,
);
```
ex: returning "Laundry"
```
$taskList = array($task1);
$taskNames['Task 1'] = $task1;
```

### Sorting Arrays 
One of the extra tools arrays give us is the ability to sort. Sorting allows us to organize large amounts of data. We can sort by key or value.

* Some sort based on the array keys, whereas others by the values: $array['key'] = 'value';
* Whether or not the correlation between the keys and values are maintained after the sort, which may mean the keys are reset numerically (0,1,2 ...)
* The order of the sort: alphabetical, low to high (ascending), high to low (descending), numerical, natural, random, or user defined
* Note: All of these sort functions act directly on the array variable itself, as opposed to returning a new sorted array
* If any of these sort functions evaluates two members as equal then the order is undefined (the sorting is not stable).

Documentation for sorting functions can be found at: http://php.net/manual/en/array.sorting.php

## Looping
In programming, a loop is a way to repeat the same actions a certain number of times, or until a certain condition is true. Instead of typing the exact same code, a loop will allow us to write that code one time then repeat that code WHILE a condition is true.

### While Loop
while loops are the simplest type of loop in PHP. They behave just like their C counterparts. The basic form of a while statement is:
```
while (expr)
    statement
```
The meaning of a while statement is simple. It tells PHP to execute the nested statement(s) repeatedly, as long as the while expression evaluates to TRUE. The value of the expression is checked each time at the beginning of the loop, so even if this value changes during the execution of the nested statement(s), execution will not stop until the end of the iteration (each time PHP runs the statements in the loop is one iteration). Sometimes, if the while expression evaluates to FALSE from the very beginning, the nested statement(s) won't even be run once. 

The following examples are identical, and both print the numbers 1 through 10: 
```PHP
<?php
/* example 1 */

$i = 1;
while ($i <= 10) {
    echo $i++;  /* the printed value would be
                   $i before the increment
                   (post-increment) */
}

/* example 2 */

$i = 1;
while ($i <= 10):
    echo $i;
    $i++;
endwhile;
?> 
```

### do-while
do-while loops are very similar to while loops, except the truth expression is checked at the end of each iteration instead of in the beginning. The main difference from regular while loops is that the first iteration of a do-while loop is guaranteed to run (the truth expression is only checked at the end of the iteration), whereas it may not necessarily run with a regular while loop (the truth expression is checked at the beginning of each iteration, if it evaluates to FALSE right from the beginning, the loop execution would end immediately). 

There is just one syntax for do-while loops: 
```php
<?php
$i = 0;
do {
    echo $i;
} while ($i > 0);
?> 
```
The above loop would run one time exactly, since after the first iteration, when truth expression is checked, it evaluates to FALSE ($i is not bigger than 0) and the loop execution ends. 

### Looping through arrays with each and list

```
$learn = array('Conditionals', 'Arrays', 'Loops');
$learn[] = 'Build something awesome!';
array_push($learn, 'Functions', 'Forms', 'Objects');
array_unshift($learn, 'HTML', 'CSS');
asort($learn);

$count = 0;
while((list($key, $val) = each($learn)) && $count++ < 2){
  echo "$key => $val\n"
} //this returns the first two items in the list
```

### For Loop
for loops are the most complex loops in PHP. They behave like their C counterparts. The syntax of a for loop is:
```
for (expr1; expr2; expr3)
    statement
```
The first expression (expr1) is evaluated (executed) once unconditionally at the beginning of the loop. 
In the beginning of each iteration, expr2 is evaluated. If it evaluates to TRUE, the loop continues and the nested statement(s) are executed. If it evaluates to FALSE, the execution of the loop ends. 

At the end of each iteration, expr3 is evaluated (executed). 

Each of the expressions can be empty or contain multiple expressions separated by commas. In expr2, all expressions separated by a comma are evaluated but the result is taken from the last part. expr2 being empty means the loop should be run indefinitely (PHP implicitly considers it as TRUE, like C). This may not be as useless as you might think, since often you'd want to end the loop using a conditional break statement instead of using the for truth expression. 

Consider the following examples. 
All of them display the numbers 1 through 10: 
```
<?php
/* example 1 */

  for ($i = 1; $i <= 10; $i++) {
    echo $i;
}

/* example 2 */

for ($i = 1; ; $i++) {
    if ($i > 10) {
        break;
    }
    echo $i;
  }
?> 
```
ex: Single line for loop
```
for($year = date('Y')-100; ++$year <= date('Y'); print $year."<br />");
```

ex: Looping through letters
```
for ($letter = 'A'; $letter != 'AA'; $letter++) {
   echo $letter."<br />";
}
```
