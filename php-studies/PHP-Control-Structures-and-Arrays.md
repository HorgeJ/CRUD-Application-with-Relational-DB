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

