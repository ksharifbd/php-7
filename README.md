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

### Operator Precedence:

The following table shows the order of precedence in the descending order-

| Operator                       | Type                  |
| :----------------------------: | :-------------------: |
| **                             | Arithmetic            |
| ++, --                         | Increasing/decreasing |
| !                              | Logical               |
| \*, /, %                       | Arithmetic            |
| +, -                           | Arithmetic            |
| <, <=, >, >=                   | Comparison            |
| ==, !=, ===, !==               | Comparison            |
| &&                             | Logical               |
| ||                             | Logical               |
| =, +=, -=, *=, /=, %=, \**=    | Assignment            |

- To perform operations in a specific order, different from the natural order of precedence, enclose the operation within parentheses.

## Strings:

- Strings can be concatenated using `(.)` operator.
- Single quotes `('')` represents strings as it is.
- Double quotes `("")` applies `Escape Characters` and `Variable Expanding`.

### Example:
```php
// Concatenation
$firstname = 'Hiro';
$surname = 'Nakamura';
echo 'I am ' . $firstname . ' ' . $surname . '!';

// Quotes
$firstname = 'Hiro';
$surname = 'Nakamura';
echo "My name is $firstname $surname.\nI am a master of time and
space. \"Yatta!\"";

/*
  My name is Hiro Nakamura.
  I am a master of time and space. "Yatta!"
*/
```

## Arrays:

- a PHP array is different from a similarly-named construct most other programming languages.
- What differentiates PHP arrays from those of other languages is that they aren’t exclusively a list-like data type. In PHP, there are what is called “associative arrays”, which can be linked “keys” to “values”. 
- An array in PHP is actually an ordered map.
- Even Non-Indexed Arrays Have Indexes.
- Arrays are not immutable.

### Initializing Arrays:

- A PHP array can be declared using `Short Array syntax - []` or `array()` function.
- For PHP version 5.4 and above the two syntaxes are identical.
- Arrays can be initialized empty or with data.
- Keys of an array can be any alphanumeric value, like strings or numbers. Values of an array can be anything: strings, numbers, Booleans, other arrays, and so on.

#### Example:
```php
// Initializing Empty array
$empty1 = [];
$empty2 = array();

// Initializing with data
$names1 = ['Harry', 'Ron', 'Hermione'];
$names2 = array('Harry', 'Ron', 'Hermione');

// More example
$status1 = [
'name' => 'James Potter',
'status' => 'dead'
];

$status2 = array(
'name' => 'James Potter',
'status' => 'dead'
);

$books = [
  '1984' => [
  'author' => 'George Orwell',
  'finished' => true,
  'rate' => 9.5
  ],

  'Romeo and Juliet' => [
  'author' => 'William Shakespeare',
  'finished' => false
  ]
];
```

### Adding elements to the Array:

- The content of an array can be changed either by treating it as a map or as a list.
- Treating it as a map means specifying the key that is to be overridden, whereas treating it as a list means appending another element to the end of the array.
- - Any key can be added to a given array, even if it previously consisted of numeric entries.
- When trying to append a value, PHP inserts it after the last numeric key.

#### Example:
```php
$names = ['Harry', 'Ron', 'Hermione'];
$status = [
'name' => 'James Potter',
'status' => 'dead'
];

$names[] = 'Neville';
$status['age'] = 32;
```

### Removing elements from an Array:

- `unset` function removes an element from the array.

```php
$status = [
'name' => 'James Potter',
'status' => 'dead'
];

unset($status['status']);
```
### Accessing arrays:

- Accessing an array is as easy as specifying the key.
- The first key is always 0; so, an array with n elements will have keys from 0 to n-1.
- Any part of the array can be printed by specifying its key.
- Trying to access a key that does not exist in an array will **return a null and throw a notice**, as PHP identifies something is done that is wrong in the code.

```php
$names = ['Harry', 'Ron', 'Hermione'];

print_r($names[1]); // prints 'Ron'
var_dump($names[4]); // null and a PHP notice
```
## Functions:

- PHP does not support overloaded functions. Overloading refers to the ability of declaring two or more functions with the same name but different arguments.
- The scope of variables declared inside the function is just the function itself. Furthermore, if a variable is declared outside the function, it would not be affected at all since the function cannot access that variable unless we send it as an argument.

### Example:
```php
  function addNumbers($a, $b) {
    $sum = $a + $b;
    return $sum;
  }

  $result = addNumbers(2, 3);
```

- A function may contain optional arguments. When declaring the function, a default value need to be provided for those arguments. So, in case the user does not provide a value, the function will use the default one.

### Example:
```php
  function addNumbers($a, $b, $printResult = false) {
    $sum = $a + $b;
    if ($printResult) {
      echo 'The result is ' . $sum;
    }
    return $sum;
  }
  
  $sum1 = addNumbers(1, 2);
  $sum1 = addNumbers(3, 4, false);
  $sum1 = addNumbers(5, 6, true); // it will print the result
```

- PHP7 allows to specify the type of argument that the function needs (type hinting), and the type of result the function will return (return type).

### Example:
```php
  function addNumbers(int $a, int $b, bool $printSum): int {
    $sum = $a + $b;
    
    if ($printSum) {
      echo 'The sum is ' . $sum;
    }
    
    return $sum;
  }

  addNumbers(1, 2, true);
  addNumbers(1, '2', true); // it fails when strict_types is 1
  addNumbers(1, 'something', true); // it always fails
```
