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
- Not Equals To (<> or !=)
- Not Identical (!==)
  
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

## Object Oriented Programming (OOP):

### Classes & Objects:

- A class is the definition of what an object looks like and what it can do, like a pattern for objects.
- A class is defined by the keyword class followed by a valid class name—that follows the same rules as any other PHP label, like variable names—and a block of code.

#### **Example:**
```php
  class Book {
  }

  class Customer {
  }
```

- Objects are representations of real-life elements. Each object has a set of attributes that differentiates it from the rest of the objects of the same class, and is capable of a set of actions.
- If we want to have a specific book, that is, an object Book—or instance of the class Book—we have to instantiate it. 
- To instantiate an object, we use the keyword new followed by the name of the class. 
- We assign the instance to a variable, as if it was a primitive type.
- We can create as many instances as we need, as long as we assign them to different variables.

#### **Example:**
```php
  $book = new Book();
  $customer = new Customer();

  $book1 = new Book();
  $book2 = new Book();
```

### Class Properties:

- Class properties are like variables inside the class.
- Property takes the type of the value assigned.
- When creating multiple instances of an object and assigning values to their properties, each object will have their own values.

#### **Example:**
```php
  class Book {
    public $isbn;
    public $title;
    public $author;
    public $available;
  }

  $book = new Book();
 
  $book->title = "1984";
  $book->author = "George Orwell";
  $book->available = true;
  
  var_dump($book);
```

### Class Methods:

- Methods are functions defined inside a class.
- Like functions, methods get some arguments and perform some actions, optionally returning a value.
- The advantage of methods is that they can use the properties of the object that invoked them.
- `$this` represents the object itself, and allows to access the properties and methods of that same object.

#### **Example:**
```php
  class Book {
    public $isbn;
    public $title;
    public $author;
    public $available;
    
    public function getCopy(): bool {
      if ($this->available < 1) {
        return false;
      } else {
        $this->available--;
        return true;
      }
    }
  }

  $book = new Book();
  
  $book->title = "1984";
  $book->author = "George Orwell";
  $book->isbn = 9785267006323;
  $book->available = 12;
  
  if ($book->getCopy()) {
    echo 'Here, your copy.';
  } else {
    echo 'I am afraid that book is not available.';
  }
```

### Class Constructors:

- Constructors are functions that are invoked when someone creates a new instance of the class.
- They look like normal methods, with the exception that their name is always `__construct`, and that they do not have a return statement, as they always have to return the new instance.
- As a constructor is still a function, it can use default arguments.

#### **Example:**
```php
  public function __construct(
    int $isbn,
    string $title,
    string $author,
    int $available = 0
  ) {
    $this->isbn = $isbn;
    $this->title = $title;
    $this->author = $author;
    $this->available = $available;
  }
  
  $book1 = new Book("1984", "George Orwell", 9785267006323, 12);
  $book2 = new Book("1984", "George Orwell", 9785267006323);
```

### Magic Methods:

- Magic Methods are a special group of methods that have a different behavior than the normal ones.
- They usually are triggered by the interaction of the class or object, and not by invocations.
- Magic methods start with `__`
- Some of the most used magic methods are - `__toString, __call, __get`.

### Properties & Methods Visibility:

- There are three types of visibility.
  - `private`: This type allows access only to members of the same class. If A and B are instances of the class C, A can access the properties and methods of B.
  - `protected`: This type allows access to members of the same class and instances from classes that inherit from that one only.
  - `public`: This type refers to a property or method that is accessible from anywhere. Any classes or code in general from outside the class can access it.

### Encapsulation:

- Encapsulation tries to group the data of the object with its methods in an attempt to hide the internal structure of the object from the rest of the world.
- The easiest way to implement this idea is by setting all the properties of the class as private and enabling two methods for each of the properties: one will get the current value (also known as getter), and the other will allow you to set a new value (known as setter). That's at least the most common and easy way to encapsulate data.

### Static Properties and Methods:

- PHP allows to have properties and methods linked to the class itself rather than to the object. These properties and methods are defined with the keyword static.
- when referring to a static property, `self::` is used instead of `$this`, which is not tied to any instance but to the class itself.
- Static properties and methods can be referred by specifying the name of the class, followed by `::`, and the name of the property/method.

#### Example:
```php
  private static $lastId = 0;

  public static function getLastId(): int {
    return self::$lastId;
  }

  Customer::getLastId();
  $customer1::getLastId();
```

### Namespaces:

- Namespaces allows to use multiple classes with the same name.
- Namespaces and the file path will usually be the same. (Enforced by developer, not by the language)
- Specifying a namespace has to be the first thing in a file.
- The namespacing is achieved by the `namespace` keyword followed by the namespace. Each section of the namespace is separated by `\`, as if it was a different directory. If the namespace is not specified, the class will belong to the base namespace, or root.
- Keyword `use` allows to specify a full class name at the beginning of the file, and then use the simple name of the class in the rest of that file.
- The keyword `as` sets an alias to the particular class

#### Example:
```
  namespace Bookstore\Domain;

  use Bookstore\Domain\Book;
  use Library\Domain\Book as LibraryBook;
```

### Autoloading Classes:
- For loading several classes in several files Autoloading is the way.
- Autoloading is a PHP feature that allows your program to search and load files automatically given some set of predefined rules. Each time you reference a class that PHP does not know about, it will ask the autoloader. If the autoloader can figure out which file that class is in, it will load it, and the execution of the program will continue as normal. If it does not, PHP will stop the execution.
- There are two ways of implementing an autoloader: the `__autoload function` and the `spl_autoload_register`.

### Using the __autoload function:
- Defining a function named __autoload tells PHP that the function is the autoloader that it must use.

#### Example:
```
function __autoload($classname) {
  $lastSlash = strpos($classname, '\\') + 1;
  $classname = substr($classname, $lastSlash);
  $directory = str_replace('\\', '/', $classname);
  $filename = __DIR__ . '/' . $directory . '.php';
  require_once($filename);
}
```

### Using the spl_autoload_register function:
- What if there are multiple `__autoload` functions?
- PHP needs to be told to keep a list of possible implementations of the autoloader, so it can try all of them until one works.
- `spl_autoload_register` can be called multiple times.

#### Example:
```php
function autoloader($classname) {
  $lastSlash = strpos($classname, '\\') + 1;
  $classname = substr($classname, $lastSlash);
  $directory = str_replace('\\', '/', $classname);
  $filename = __DIR__ . '/' . $directory . '.php';
  require_once($filename);
}
spl_autoload_register('autoloader');
```

### Inheritance:
- Inheritance in OOP is the ability to pass the implementation of the class from parents to children.
- the technical way of referring to this feature is that a class `extends` from another class.
- When extending a class, all the properties and methods are available that are not defined as private, and the child class can use them as if they were its own.
- The limitation is that a class can only extend from one parent.
- To force PHP to use the parent's method, use the keyword parent:: instead of $this.

#### Example:
```php
class Person {
  protected $firstname;
  protected $surname;
  public function __construct(string $firstname, string $surname) {
    $this->firstname = $firstname;
    $this->surname = $surname;
  }
  public function getFirstname(): string {
    return $this->firstname;
  }
  public function getSurname(): string {
    return $this->surname;
  }
}

class Customer extends Person {
  private static $lastId = 0;
  private $id;
  private $email;
  
  parent::__construct($firstname, $surname);
  
  if (empty($id)) {
    $this->id = ++self::$lastId;
  } else {
    $this->id = $id;
    if ($id > self::$lastId) {
      self::$lastId = $id;
     }
  }

  $this->name = $name;
  $this->surname = $surname;
  $this->email = $email;
  
  
  public static function getLastId(): int {
    return self::$lastId;
  }
  
  public function getId(): int {
    return $this->id;
  }
  
  public function getEmail(): string {
    return $this->email;
  }
  
  public function setEmail($email): string {
    $this->email = $email;
  }
}
```

### Method Overriding:
- If a child class implements a method having same name or signature as in the parent class, then it's called `method overriding`.
- When overriding, the child method has to have at least as much visibility as the one inherited. That means that if we inherit a protected one, we can override it with another protected or a public one, but never with a private one.

#### Example:
```php
  // Example-1
  class Pops {
    public function sayHi() {
      echo "Hi, I am pops.";
    }
  }
  
  class Child extends Pops{
    public function sayHi() {
    echo "Hi, I am a child.";
    }
  }
  
  $pops = new Pops();
  $child = new Child();
  
  echo $pops->sayHi(); // Hi, I am pops.
  echo $child->sayHi(); // Hi, I am Child.
  
  // Example-2
  class Child extends Pops{
    public function sayHi() {
      echo "Hi, I am a child.";
      parent::sayHi();
    }
  }
  
  $child = new Child();
  echo $child->sayHi(); // Hi, I am Child. Hi I am pops.
  
  // Example-3 - This will throw error
  class Child extends Pops{
    protected function sayHi() {
      echo "Hi, I am a child.";
    }
  }
```

### Abstract Classes:
- An abstract class is a class that cannot be instantiated. Its sole purpose is to make sure that its children are correctly implemented.
- Declaring a class as abstract is done with the keyword abstract, followed by the definition of a normal class.
- Methods can be specified which children are forced to implement, without implementing them in the parent class. Those methods are called abstract methods, and are defined with the keyword abstract at the beginning.
- Any class that contains at least one abstract method must also be abstract.
- Methods defined as abstract simply declare the method's signature - they cannot define the implementation.
- When inheriting from an abstract class, all methods marked abstract in the parent's class declaration must be defined by the child; additionally, these methods must be defined with the same (or a less restricted) visibility. For example, if the abstract method is defined as protected, the function implementation must be defined as either protected or public, but not private.
- The signatures of the methods must match, i.e. the type hints and the number of required arguments must be the same. For example, if the child class defines an optional argument, where the abstract method's signature does not, there is no conflict in the signature.

#### Example:
```php
  // Example 1
  abstract class AbstractClass
  {
      // Force Extending class to define this method
      abstract protected function getValue();
      abstract protected function prefixValue($prefix);

      // Common method
      public function printOut() {
          print $this->getValue() . "\n";
      }
  }

  class ConcreteClass1 extends AbstractClass
  {
      protected function getValue() {
          return "ConcreteClass1";
      }

      public function prefixValue($prefix) {
          return "{$prefix}ConcreteClass1";
      }
  }

  class ConcreteClass2 extends AbstractClass
  {
      public function getValue() {
          return "ConcreteClass2";
      }

      public function prefixValue($prefix) {
          return "{$prefix}ConcreteClass2";
      }
  }

  $class1 = new ConcreteClass1;
  $class1->printOut();
  echo $class1->prefixValue('FOO_') ."\n";

  $class2 = new ConcreteClass2;
  $class2->printOut();
  echo $class2->prefixValue('FOO_') ."\n";

  //output
  ConcreteClass1
  FOO_ConcreteClass1
  ConcreteClass2
  FOO_ConcreteClass2

  // Example 2:
  abstract class AbstractClass
  {
      // Our abstract method only needs to define the required arguments
      abstract protected function prefixName($name);

  }

  class ConcreteClass extends AbstractClass
  {

      // Our child class may define optional arguments not in the parent's signature
      public function prefixName($name, $separator = ".") {
          if ($name == "Pacman") {
              $prefix = "Mr";
          } elseif ($name == "Pacwoman") {
              $prefix = "Mrs";
          } else {
              $prefix = "";
          }
          return "{$prefix}{$separator} {$name}";
      }
  }

  $class = new ConcreteClass;
  echo $class->prefixName("Pacman"), "\n";
  echo $class->prefixName("Pacwoman"), "\n";

  // output
  Mr. Pacman
  Mrs. Pacwoman
```
