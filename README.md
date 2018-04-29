# PHP 7

## The `<?php ?>` tag:
- Should enclose PHP code with `<?php ?>`.
- Any code outside `<?php ?>` are interpreted as it is.
- Any HTML outside `<?php ?>` are interpreted by the browser.

### Exanmple:
```php
<?php
echo 'hello world';
?>
bye world
```

The above code will print both `hello world` and `bye world`.

## Comment:

- PHP supports two types of comment - single-line comments and multiple-line comments.

### Example:
```php
// This is the single-line comments

/*
  This is the multiple-line comments.
  second line.
*/
```

## Variable:

- PHP variables start with the $ sign followed by the variable name.
- The value of an unassigned variable is null.
- A valid variable name starts with a letter or an underscore followed by any combination of letters, numbers, and/or underscores.
- It is case sensitive. So, `$home` and `$Home` are two different variables.

### Example:
```php
$txt = "Hello world!";
```

## Data types:

- PHP has 8 primitive data types.
  * Integer
  * String
  * Float (also called double)
  * Boolean
  * Array
  * Object
  * NULL
  * Resource
  
## Operators:
  
- Operators do operations on the operands.
  
There are 5 types of operators:
- Arithmetic Operators
- Assignment Operators
- Comparison Operators
- Logical Operators
- Incrementing and decrementing operators
  
### Arithmetic Operators:

- Addition (+)
- Subtraction (-)
- Multiplication (*)
- Division (/)
- Modulus (%)
  * Gives the remainder of the division of two operands
- Exponentiation (**)
- Negation (-)
  * Negates the operand and is the only arithmetic operator that takes just one operand.
  
#### Example:
```php
<?php
  $a = 10;
  $b = 3;
  var_dump($a + $b); // 13
  var_dump($a - $b); // 7
  var_dump($a * $b); // 30
  var_dump($a / $b); // 3.333333...
  var_dump($a % $b); // 1
  var_dump($a ** $b); // 1000
  var_dump(-$a); // -10
?>
```

### Assignment Operator:

- Assigns the result of an expression to a variable.
- There are a series of assignment operators that work as shortcuts.

#### Example:
```php
// Assignment Operator
<?php
  $a = 3 + 4 + 5 - 2;
  var_dump($a); // 10
?>

// Shortcuts
<?php
  $a = 13;
  $a += 14; // same as $a = $a + 14;
  var_dump($a);
  $a -= 2; // same as $a = $a - 2;
  var_dump($a);
  $a *= 4; // same as $a = $a * 4;
  var_dump($a);
?>
```

### Comparison Operators:

- take two operands and compare them.
- Usually returns Boolean.

There 9 types of comparison operators
- Less Than (<)
- Greater Than (>)
- Less Than or Equal To (<=)
- Greater Than or Equal To (>=)
- Spaceship (<=>)
  * Compares both the operands and returns an integer instead of a Boolean.
  * When comparing a with b, the result will be less than 0 if a is less than b, 0 if a equals b, and greater than 0 if a is greater than b.
- Equals (==)
  * Evaluates two expressions *after* type juggling.
- Identical (===)
  * evaluates two expressions *without* type juggling
- Not Equals To (<> or !==)
- Not Identical (!===)
  
#### Example:
```php
<?php
  var_dump(2 < 3); // true
  var_dump(3 < 3); // false
  var_dump(3 <= 3); // true
  var_dump(4 <= 3); // false
  var_dump(2 > 3); // false
  var_dump(3 >= 3); // true
  var_dump(3 > 3); // false
  var_dump(1 <=> 2); // int less than 0
  var_dump(1 <=> 1); // 0
  var_dump(3 <=> 2); // int greater than 0
  
  $a = 3;
  $b = '3';
  $c = 5;

  var_dump($a == $b); // true
  var_dump($a === $b); // false
  var_dump($a != $b); // false
  var_dump($a !== $b); // true
  var_dump($a == $c); // false
  var_dump($a <> $c); // true
?>
```

### Logical Operators:

- or (||)
- and (&&)
- not (!)

#### Example:
```php
<?php
  var_dump(true && true); // true
  var_dump(true && false); // false
  var_dump(true || false); // true
  var_dump(false || false); // false
  var_dump(!false); // true
?>
```

### Incrementing and Decrementing Operators:

- they only work on variables

There are 4 types of these operators-

- (+=)
- (-=)
- (++)
- (--)

#### Example:
```php
$a = 2;
$b = $a++;

var_dump($a, $b);

/*
The operator on the right will return first the value of $a, which is 2, assign it to $b, and only then
increase $a by 1
*/
```
